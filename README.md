# Mantella-WT - the Mantella/xVASynth Optimizer-Launcher.
Status: Working, further development possible.

# Description
Drop-in files for Local-Model Optimization and Launching Mantella. The Mantella xVASynth Optimizer/Launcher is a command-line tool designed to automate and optimize the workflow for managing audio generation in Skyrim and Fallout 4 using the xVASynth software. The script facilitates pre-launch, configuration management and optimization, launches, xVASynth and/or your chosen game, if it is not already running, then it launches Mantella, making use throughout of the re-configured settings in `config.ini`. Mantella-WT also performs various tasks such as, cleaning configuration files and optimizing the mantella prompts. The Batch file manages the, communication between and launching, of the relevant programs/scripts, while the Python component of the script handles the heavy work, and displays an interactive menu for user selection of game and optimization options. It all goes together, the launcher and optimizations are as important as the drop-in files. Currently the drop-in (replacer) files includes, concise/standardized characters sheet for Fo4/Vr & Skyrim/Vr, and also refinement of printed lines.

# Features
1. **Batch Launcher for Automation**: Automates and runs xVASynth and Mantella with admin privileges.
2. **Standardized Character Details**: Standardizes character data for clarity and effective audio generation.
3. **Optimized Configuration Management**: Streamlines `config.ini` prompts and removes non-functional options.
4. **Interactive Python Script**: Cleans configuration files and offers an interactive menu for game and preset choices.
5. **Error Handling and Logging**: Tracks errors, logs execution, and backs up configuration files.
6. **Automatic Execution and Exit Handling**: If not already running, then runs, Fallout 4 and/or xVASynth, and then continues to Mantella for smooth operation.
7. **LM Studio Enhanced/Specific**: Switching models in LM Studio is detected, and then automatically updated in `config.ini`. 

# Preview
- The menu of much simplified optimization (Showing version 11.4.3 in development)...
```
=======================================================================================================================
                                          Mantella-WT Optimizer / Launcher
-----------------------------------------------------------------------------------------------------------------------





                                               1. Game Used: Fallout4

                                               2 Microphone On: False

                                               3. Optimization: Regular

                                               4. Token Count: 4096





-----------------------------------------------------------------------------------------------------------------------

                                   model = Lewdiculous/L3-8B-Stheno-v3.2-GGUF-IQ-Imatrix
                                   Fallout4_folder = D:\GamesVR\Fallout4_163
                                   xvasynth_folder = D:\GamesVR\xVASynth

=======================================================================================================================
Selection, Program Options = 1-4, Refresh Display = R, Begin Mantella/xVASynth = B, Exit and Save = X:

```
- The general running of things...
```
=======================================================================================================================
                                          Mantella-xVASynth Optimizer/Launcher
------------------------------------------------------------------------------------------------------------------------

Working Dir: D:\GamesVR\Mantella-WT-0.11.4
Running Mantella xVASynth Optimizer...
Script started
Working Folder: D:\GamesVR\Mantella-WT-0.11.4
Config File: D:\GamesVR\Mantella-WT-0.11.4\config.ini
Script execution started
Entering main function
Starting config cleaning...
Found 0 comment lines.
Config Already Clean.
Checking Prompts
Prompts Alrady Optimized.
Reading config file...
Read Keys: config.ini.
Writing config file...
Settings saved. Proceeding to run Mantella/xVASynth...
Writing output file: exit_code=0, xvasynth_path=D:\GamesVR\xVASynth
Output file written successfully: main-wt.txt
0,D:\GamesVR\xVASynth
Final output: exit_code=0, xvasynth_path=D:\GamesVR\xVASynth
Script execution ended
...Mantella/xVASynth Optimizer-Launcher Closed...
Checking for xVASynth...
Running Mantella...
Mantella-WT for Mantella version 0.11.4
Mantella currently running for Fallout4 (D:\GamesVR\Fallout4_163).
Mantella mod located in D:\GamesVR\Fallout4_163\Data.
21:33:50.151 INFO: Running Mantella with local language model
21:33:50.152 WARNING: L3-8B-Stheno-v3.2-GGUF-IQ-Imatrix is using token_limit of 4096
21:33:50.361 TTS: Connecting to xVASynth...
21:33:50.510 STT: Audio threshold set to 'auto'. Adjusting microphone for ambient noise...
21:33:50.510 STT: If mic input too low, edit audio_threshold value manually in .\config.ini.
Need help? See here: https://art-from-the-machine.github.io/Mantella/pages/issues_qna
Waiting for player to select an NPC for Communication...

```

## Requirements
1. **Python Environment**: Requires Python 3.11 and dependencies from the Mantella requirements file.
2. **Language Model**: Use [Lewdiculous L3-8B-Stheno-v3.2-GGUF-IQ-Imatrix](https://huggingface.co/Lewdiculous/L3-8B-Stheno-v3.2-GGUF-IQ-Imatrix) with Q3 or Q4 VRAM specifications.
3. **Operating System**: Compatible with Windows 7 through Windows 11; administrative privileges may be needed.
4. **xVASynth Installation**: Must be installed and correctly configured in the specified directory.
5. **Configuration File**: Requires a `config.ini` with `Game`, `Paths`, and `LanguageModel.Advanced` sections.
6. **LM Studio**: Obtain model folder/name and foolproofs api config, Mantella-WT will not work on, Ollama or GPT.

# Usage / Install
1. Ensure the [Mantella Mod](https://www.nexusmods.com/fallout4/mods/79747) is installed for Fallout/Skyrim from the Nexus mods site, follow the guide, this will, at some point, require install [Mantella 11.4](https://github.com/art-from-the-machine/Mantella/releases/tag/v0.11.4) to a suitable directory.
2. After completing Mantella 11.4 install, then download the [Latest working Mantella-WT release](https://github.com/wiseman-timelord/Mantella-WT/releases/), drop the files into the main Mantella folder, preserving folders.
4. Ensure you have LM Studio loaded and configured and serving, and ensure to offload a suitable number of layers to the GPU depending upon free VRAM.
5. Configure the ".\config.ini", ensure you have entered things like, "fallout4_folder" and "fallout4_mod_folder" and "llm_api" and "tts_service".
6. Run Fallout 4/Skyrim, and then run the `Mantella-WT.Bat` batch, the "config.ini" will be cleaned/backup, and then you will be presented with the menu.
- Hopefully you have, Admin rights and sensible system settings, but click allow on firewall as required, I am guessing its the interaction between Mantella and the Mantella Mod.

## Notes
- all options for Optimization are shown...
```
Default: max_tokens = 250, max_response_sentences = 999, temperature = 1
Faster: max_tokens = 100,max_response_sentences = 1, temperature = 0.4
Medium: max_tokens = 150, max_response_sentences = 2, temperature = 0.5
Quality: max_tokens = 200, max_response_sentences = 3, temperature = 0.6
```
- the "Offended" and "Forgiven", commands are removed, this is because, offended will depend on the model, and most likely on local models, asking for forgiveness would not have a result before the player is dead? So, I find these things a nice idea, but a bit naff. I would prefer commands like "Attack" and "Hold Back", to switch between, Aggressive and Cautious. Either way, it was additional weight, and I wanted the prompts to work, correctly and fast, on Q3_M Local Models.
- a Llama 3 Q3_m model with fallout 4 dlc & ~300 mods including PhyOp performance texture pack, utilizes all of the 8GB on a single card, if you want to use =>Q4 and/or hd textures, then I suggest 10-12GB free VRam or, sharing processing with the cpu. If you need more VRam, try the "PhyOp" Performance/Regular Textures on Nexus, ensure it loads after things like, for example, CBBE and BodyTalk.
- Because LM Studio has a curl command to request the model folder/name, and Ollama does not, so there will be no Ollama Support, because it would require interference with models in a launcher app. Additionally, Ollama does not support AMD Vulkan, and it did not support OpenCL before. This information shown below from command "Ollama Ps" after running "Ollama Serve", its endless non-sense...
```
NAME                    ID              SIZE    PROCESSOR       UNTIL
qwen2_57b:latest        9dbf41c98d9e    48 GB   100% CPU        4 minutes from now
```
- No, GPT/Online or Ollama, support! GPT will always be filtered response, despite being fast. I cant see it being used when local models are finally figured out, and GPT/Online models are not private either. Ollama has no curl model folder/name request, I would have to do interference in a Launcher to get the model info, and Ollama has no AMD GPU OpenCL/Vulkan support.

# Development
- Noticing the improvements in Language models, 1 token per word? it used to be 5 tokens for every 4 letters, and 4 tokens for every 3 tokens, or something was the calculation, when we were at llama 1 stage, if I am not hallucinating, this is highly impressive advancements, but requires re-assessment of what is a "Required number of Tokens".
- Possibly requires advance of my project for utilizing llama.cpp pre-compiled binaries for vulkan, to host models with OhLlama/LmStudio compatibility for apps, as they are not utilizing threads properly or vulkan at all, currently.
- tuned towards, windows and local models, scripts will be streamlined, people whom use online should still have the benifit from the larger context, hence need to make, 1, 2, 3, sentence processed verions of characters.csv, this would be, characters_1.csv, characters_2.csv, characters_3.csv and use them in tandem with the relating setting for custom_context_length, 2048, 4096, 8192. 
-  When they release v12, I am assuming i will have completed/tested this project, so at that point, I will upgrade the main v12 scripts, and push it to main, but whatever code I do push, must, remain compatibly with or expand upon, the Authors intended features, so nothing, local only or 4k context optimized, it will have to be for, local/non-local AND 4k/8k.

# Disclaimer
- The extension `-WT` means that this project does not originate from Wiseman-Timelord, it is the "Wiseman-Timelord's" own, "Hack" or "Version", of the relating "Official" software. Any issues regarding the "Original" code, stop with the Author's of the "Original" code.
