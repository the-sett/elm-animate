**Contacts for Support**
- @rupertlssmith on https://elmlang.slack.com
- @rupert on https://discourse.elm-lang.org

# elm-animate

`elm-animate` is a simple and minimal animation sequencer that helps to animate
properties of some model.

A property to be animated is wrapped in a `Timeline`. This interpolates the property
based on a progress value that runs from 0.0 to 1.0, in a given length of time. In
this version only the simple timelines are supported.

The user provides an interpolation function to blend between a start and end value using the eased progress value. Anything you can think of that can be interpolated 
in this way can be animated.

Easing functions can be applied to the timelines. An easing function should map 
0.0 to 0.0 and 1.0 to 1.0, but does not have to remain between these values for all
other inputs. An easing function can produce negative values or ones greater than 1.0.
For example an easing may overshoot the end value and then come back again, if it is
emulating a spring.

Several timelines can be combined inside an `Animator` container. A subscription can be
generated for the animator that will only be active when it contains a timeline that
has not completed all of its progress. When the subscription is active is will produce
messages with timestamps provided by `Browser.Events.onAnimationFrame`.

# Acknowledgements

`elm-animate` was developed from scratch, but influenced by `mdgriffith/elm-animator`.
In particular the `Timeline` and `Animator` concepts are similar. This package is
smaller and less complex and sufficient for many simple animation needs.
