# Move-to-monitor

Move the current window to the next monitor. 
This is useful for multi-monitor setups and window managers that don't have such a mapping by default.

Moves left/right when called with prev/next.

Only works on a horizontal monitor setup.
Also works only on one X screen (which is the most common case).

The idea and some code is taken from
http://icyrock.com/blog/2012/05/xubuntu-moving-windows-between-monitors/

Unfortunately, both "xdotool getwindowgeometry --shell $window_id" and
checking "-geometry" of "xwininfo -id $window_id" are not sufficient, as
the first command does not respect panel/decoration offsets and the second
will sometimes give a "-0-0" geometry. This is why we resort to "xwininfo".

You will need xwininfo xdotool wmctrl installed.

On opensuse: `zypper install xwininfo xdotool wmctrl`
