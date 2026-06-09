# FSPropertyBag::GetDateTimeString(_FILETIME const &,ushort * *)

- ea: `0x1800bc078`
- end: `0x1800bc2f3`
- name: `?GetDateTimeString@FSPropertyBag@@AEAAJAEBU_FILETIME@@PEAPEAG@Z`
- size: `635`
- prototype: `int(FSPropertyBag *__hidden this, const struct _FILETIME *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ba304`
- `0x1800bcd58`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001f01c`
- `0x1800254ac`
- `0x180046664`
- `0x1800bc078`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc0bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc17b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc0bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc17b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc255`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800bc0af`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800bc0af`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1800bc121`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1800bc171`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1800bc121`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1800bc171`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1800bc1e3`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1800bc24b`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1800bc1e3`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1800bc24b`

## string_xrefs

- `0x1800bc0e0`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc1a0`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc213`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`

## pseudocode

```c

```
