## 1.10.0

- feature: trim input values
    - added a new configuration option **trimInput** (default: true)
    - if true all new input values will be trimmed
- feature: treat restarts as pause
    - added a new configuration option **restartEqualsPause** (default: true)
    - if true a pause entry will be written after a restart
- feature: auto update
    - for future releases TimeKeeper will show a update button if a new Version is available
    - this update will download the new TimeKeeper and replace the existing one

## 1.9.2

- fix: adjust window size & set minimum window size

## 1.9.1

- fix: selection in group view

## 1.9.0

- feature: **Open last log** - directly open the log of the last working day
- feature: Confirm reset configuration
- feature: Reset configuration stores backup
- feature: **Automated Update check**
    - TimeKeeper will check if a new Verison is available on startup
    - new Versions can be downloaded directly within TimeKeeper
- feature: **Show pause** 
    - show / hide pause entries
    - same restrictions as for show booked
- feature: **Book mode** - sets view mode to group, hides booked & pause entries
- refactor: restructered **View** Menu
    - **Book mode**
    - **View mode** - single toggle instead of two
    - **Show** - Booked & Pause as sub menu

## 1.8.0

- feature: open logs
    - in the toolbar section "Open" you can now open older logs
    - a log is read only
    - you can get back to the current day with the "today" action or if you hit "esc"
- feature: added action to mark a entry as pause
- feature: added regex support for buzzwords
- feature: booked entries can now be unbooked if you execute the book action again

## 1.7.1

- feature: added support to preset 0 min time bookings

## 1.7.0

- feature: preset booking date
    - if you add the property "date" to your configurations quickEntryParams the date of the entry will be presetted within the quick entry url

## 1.6.1

- fix: edit entries with booked hidden works now

## 1.6.0

- fix: edit now scrolls properly if the edit component is not fully displayed
- feature: delete entries
    - added a delete action - will delete all marked entries with time 0
    - delete all marked entries with DEL
- feature: show / hide booked
    - added a new option "Show booked" at Menu     - View
    - when unchecked no booked entry will be shown anymore
    - you can preset the checkbox with the configuration property "showBooked" (default: true)
    - you can't execute the merge actions when booked entries aren't shown
- feature: merge and split marks a entry as pause
- feature: Syntax Errors in configuration.json will be detected
    - if a error during parsing4 occurs the user will recieve a message with the error and the line & character where the error occured
    - the json file will be opened
- the buzzword list in the configuration will now be sorted on init / reload
- feature: multiple internal library refactorings
- feature: replace quick entry description
    - the configuration has now a new property "quickEntryReplacements"
    - you can configure multiple replacements which will be executed on the description of a quick entry link
    - a replacement has 3 params: [RegExp to search the replacement, Replacement, RegExp to check if the replacement should be executed]
    - make sure to escape js characters within a regexp string (eg. \ -    - \\) 
    - by default adito ticketcodes (7 digit number) will be replaced: ["\\d{7}", ""]
- fix: grouping is now case insensitive

## 1.5.2

- fix: time does not add up on a new entry

## 1.5.1

- fix: split with     -= 30min crushes the time / booked values
- fix: merge with last doesn't show the wrong time anymore

## 1.5.0

- feature: edit entries
    - added a contextmenu to edit entries, it contains 4 actions:
1. Edit description: allows you to edit the description of the selected entry
2. Merge with next: allows you to edit the description of the selected entry and merge it with the next entry
3. Merge with next: allows you to edit the description of the selected entry and merge it with the last entry
4. Split: allows you to set a description and select a time which will be moved from the selected entry to a new entry (only available if you have 30 minutes or more in your entry)
    - in additon to the save & cancel buttons you can do the same by hitting enter / esc
- fix: ticket quick entry time preset works now within groups as well
- internal: refactored the time full time calculations
- internal: refactored the buttons to seperate reusable views
- internal: removed unneccessary dependencies to keep the application small
- fix: removed broken about view
- feature: changed background color, font color & Button design for better optics

## 1.4.0

- feature: use ticket quick entry
    - a new configuration value "useQuickEntry" is added (default true)
    - when true a ticket code will no longer be opened via the indexsearch but instead it will directly open the ticket time entry and preset the ticket, time and description
    - you can now add ticketcodes as buzzwords instead of ticket URLs - in this case the ticket time quick entry will be used as well

## 1.3.0

- feature: select entries
    - mark a entry with click / ctrl + click / shift + click / ctrl + a
- feature: mark entries as booked
    - added booked button to mark entries as booked (you can use ctrl + b as well)
    - booked entries will be crossed out
    - the summed up booked time will be shown
- internal: refactored vue components
- internal: code refactored
- feature: switch viewmode
    - added viewmode "group" (default "list")
    - group will show all entries with summed up times (grouped by input text)
    - set default viewmode in configuration
- feature: configure information box

## 1.2.0

- feature: reorganised menu bar
- feature: moved log button to menu bar
- feature: added configuration file
- feature: added configuration buttons to menu bar
- feature: added buzzword logic for configuration
- fix: set folders for build

## 1.1.1

- fix: pause and restart can be choosen by history
- fix: running time resets at 1h

## 1.1.0

- fix: wrong displayed time at 01:00
- fix: \n after each entry in log
- fix: pause is added to full time
- fix: scroll to bottom after clicking a link
- feature: move through history with arrow up & down keys
- feature: running current and full times

## 1.0.0:

- initial release
