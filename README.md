# POCKET NATIVE PLUS

The ultimate way to play 3DS games on a budget handheld, such as the Anbernic RGDS! Based off Pocket Native, it has the ability to decompile 3DS games and recompile them as native Android applications you can run inside the app. Download from the latest Actions build. Every once in a while it is rebased to match upstream for compatibility fixes and speed upgrades. Want to decompile your ROM and run it in the emulator? No problem, here's a step by step guide!

# DECOMPILING

Assuming you don't feel like installing anything, make a Github codespace! If you're on Windows you have an easy .bat and on Linux... uhhhh... Well I'm on Mac so whatever just make a codespace.

Then run the following commands in order :
1. `pip3 install capstone`
2. `curl https://rustup.rs -sSf | sh -s -- -y`
3. `source "$HOME/.cargo/env"`

Now add your ROM to the root folder of the codespace. You can either upload it to Mediafire and then use `wget` or you can upload it directly. Name it "`game.3ds`". Now that that's done, run `cargo build --release` in your terminal. This may take about 1-2 minutes. Last but not least run `./scripts/build.sh "game.3ds"`. This will take a few minutes, so let it do its job. It should range between 5-10 minutes depending on the size of the game. Then run `find . -name "title.so"` to locate the output. Copy the full path, it should look something like "`./build/Pocket Native/pocket-native/games/000X0000XXXXXXXX/title.so`" Now you can just zip it and download it. Run `zip -r /workspaces/pocket-native/game.zip "YOUR-PATH-HERE"` (replace YOUR-PATH-HERE with the path you just copied) and then go to the root of your workspace. You should find game.zip. Right click it and download it. Now get it onto your device in any way or form and unzip it. I suggest putting it in the root folder and then another folder inside of it so you don't get permission errors. Then you can go back and you'll see your game!

# USAGE

If your game looks strange or the screens are swapped, try entering settings. You have plenty of options to hide the time and/or battery, swap the screens, disable the overlay, and more! More settings will be added in the future.

# REBASING

This project is rebased to match upstream every once in a while. MAKE SURE TO NOT TOUCH THE SETTINGS OR ANY NEW FEATURES. Only rebase game compatibility and other shi. Anything this fork adds should remain untouched unless needed to be touched.
