# Configs
Disable intrusive animations
`./desktop_environment/disable_animations.sh`

## System Preferences->Keyboard
* Touchbar shows F1, F2, etc. Keys
* Use F1, F2, etc. keys as standard function keys on external keyboards.

## System Preferences->Keyboard->shortcuts
Configure only necessary shortcuts, disable others.

### Mission Control
|                                        |                        |
|----------------------------------------|------------------------|
|Mission Control                         |^ up                    |
|____Move left a space                   |^ option shift cmd left |                   
|____Move right a space                  |^ option shift cmd right|                    
|Application windows                     |^ down                  |  
                   
### Keyboard
|                                        |                        |
|----------------------------------------|------------------------|
|Move focus to the menu bar              |^ F2                    |   
|Move focus to the Dock                  |^ `                     |  
|Move focus to the status menus          |^ F8                    |   

### Spotlight
|                                        |                        |
|----------------------------------------|------------------------|
|Show Spotlight search                   |option Space            |

## KeyBindings
Remap the key bindings of a single user on MacOS to more closely match default behavior on PC systems. 
This makes the Command key behave like PC Control key. 

```
curl https://gist.githubusercontent.com/zaz968m/86c7c32b54743b725fb4a86f2335b4b3/raw/ab7c868a8354219782b37971f984564c66a53d78/DefaultKeyBinding.dict \
    -o ~/Library/KeyBindings/DefaultKeyBinding.dict
```

## Taskbar
As no better solution found so far utilize the built-in dock.
* move to the left side
* hide by default
* utilize shortcut Move focus to the Dock
* done via disable_animations.sh
    * show immediately and without delay
    * mark hidden and open apps
    
# Apps

* https://brew.sh package manager
* https://karabiner-elements.pqrs.org/ keyboard customizer
* https://alt-tab-macos.netlify.app/ window-manager, task-switcher
* https://github.com/rxhanson/Rectangle move and resize windows with keyboard shortcuts and snap areas
* https://fman.io/ dual-pane file manager
* https://maccy.app/ clipboard manager
* https://www.iterm2.com/ terminal

## Install

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
brew cask install karabiner-elements
brew cask install alt-tab
brew cask install rectangle
brew cask install fman
brew cask install maccy
brew cask install iterm2
```

## karabiner
map the most bottom keyboard row to default PC sequence
```
cmd fn control option space option command
```
example configuration `./karabiner/config/karabiner.json`
config location: `~/.config/karabiner`

alt within intellij does not work:
https://github.com/pqrs-org/Karabiner-Elements/issues/1160

## alt-tab
Configure to show list of open windows

|                                        |                        |
|----------------------------------------|------------------------|
|Hide window thumbnails                  |yes                     |
|Window min width in row                 |51%                     | 

## maccy
|                                        |                        |
|----------------------------------------|------------------------|
|Hotkey                                  |^V                      |
|Paste automatically                     |yes                     |                               
|paste without formatting                |yes                     |                
|Show menu icon                          |no                      |      
|Show title before search field          |no                      |                      
|Show footer                             |no                      |   

## terminal
https://coderwall.com/p/h6yfda/use-and-to-jump-forwards-backwards-words-in-iterm-2-on-os-x

## intellij 
Layout based on default XWin with changed control -> meta

copy `./intellij/keymap/My_Macos_XWin.xml` to
keymap location:
`~/Library/Application Support/JetBrains/IntelliJIdea2020.2/jba_config/mac.keymaps`

# Unresolved questions

* taskbar - array, linked list of opened windows 
(alt-tab is priority queue, stack) 

* Increase text size like Ctrl + + but with mouse scroll
