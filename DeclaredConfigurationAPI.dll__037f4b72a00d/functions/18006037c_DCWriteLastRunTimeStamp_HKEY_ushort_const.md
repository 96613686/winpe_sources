# DCWriteLastRunTimeStamp(HKEY__ *,ushort const *)

- ea: `0x18006037c`
- end: `0x18006053d`
- name: `?DCWriteLastRunTimeStamp@@YAJPEAUHKEY__@@PEBG@Z`
- size: `449`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18007f370`
- `0x1800ac970`

## callees

- `0x18000b9e0`
- `0x1800117bc`
- `0x1800117dc`
- `0x18001ce5c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x18005ef7c`
- `0x18006037c`
- `0x1801011cc`
- `0x18010136c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800603bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800603bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006044a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800604ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006044a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800604ed`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800603cb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800603cb`
- `dmiso8601utils!FileTimeToISO8601String` at `0x180060406`
- `dmiso8601utils!FileTimeToISO8601String` at `0x180060406`

## string_xrefs

- `0x1800603d9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180060436`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800604b4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c

```
