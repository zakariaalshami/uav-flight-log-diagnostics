# UAV flight-log event report

## Event summary

| Metric | Value |
|---|---:|
| event_start_s | 2.5 |
| event_end_s | 7 |
| peak_abs_roll_deg | 22.176783 |
| peak_abs_pitch_deg | 8.846478 |
| peak_abs_yaw_deg | 48.003304 |
| roll_min_deg | -22.176783 |
| roll_max_deg | 21.269093 |
| pitch_min_deg | -8.846478 |
| pitch_max_deg | 7.617647 |
| yaw_min_deg | -48.003304 |
| yaw_max_deg | -20.308102 |
| x_drift | 0 |
| y_drift | 0 |
| z_drift | -0.00365 |
| vx_delta | 0 |
| vy_delta | 0 |
| vz_delta | -0.04282 |
| control[0]_peak_abs | 0.5 |
| control[1]_peak_abs | 0.4 |
| control[2]_peak_abs | 0.3 |
| control[3]_peak_abs | 0 |

## Interpretation

The log shows a short maneuver window from 2.5 s to 7.0 s, with roll as the dominant motion and smaller pitch and yaw changes.
The control inputs move in the same window as the attitude angles, which indicates a commanded or actively corrected event rather than a persistent fault.
Position drift is negligible in x and y, with only a small vertical change, so the aircraft remained broadly stable outside the maneuver.


## Key findings

- The main event occurs between 2.5 s and 7.0 s.
- Roll is the dominant motion, with a peak absolute angle of 22.176783 deg.
- Pitch is smaller than roll, with a peak absolute angle of 8.846478 deg.
- Yaw changes substantially during the same window, with a peak absolute angle of 48.003304 deg.
- Horizontal drift is negligible, with x and y drift equal to 0.
- Vertical drift is small, with z drift of -0.003650032 and vz delta of -0.042820238.
- Control inputs align with the attitude event window, supporting a commanded maneuver or active closed-loop correction.

## Conclusion

The flight log indicates a short, concentrated maneuver followed by stable behavior. The strongest motion appears in roll, while pitch and yaw also change during the same interval. Because the control inputs and attitude response align in time, the event is more consistent with an intentional command or normal controller action than with a persistent fault.


## How to reproduce

1. Open the notebook and load `sample.ulg`.
2. Extract `vehicle_attitude`, `vehicle_local_position`, and `actuator_controls_0`.
3. Convert quaternion values to roll, pitch, and yaw.
4. Restrict the analysis to the 2.5 s to 7.0 s window.
5. Compare control inputs with the attitude response.
