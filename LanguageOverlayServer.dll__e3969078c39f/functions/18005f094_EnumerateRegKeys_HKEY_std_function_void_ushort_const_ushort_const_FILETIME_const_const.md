# EnumerateRegKeys(HKEY__ *,std::function<void (ushort const *,ushort const *,_FILETIME const &)> const &)

- ea: `0x18005f094`
- end: `0x18005f265`
- name: `?EnumerateRegKeys@@YAXPEAUHKEY__@@AEBV?$function@$$A6AXPEBG0AEBU_FILETIME@@@Z@std@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038cfc`
- `0x1800412a8`
- `0x180059f50`

## callees

- `0x180003ea0`
- `0x1800044b8`
- `0x180005df8`
- `0x180011334`
- `0x18005f094`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005f1ca`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005f1ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005f101`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005f101`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005f234`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005f234`

## string_xrefs

- `0x18005f23e`: `onecore\base\languageoverlay\common\registryutils.cpp`
- `0x18005f253`: `onecore\base\languageoverlay\common\registryutils.cpp`

## pseudocode

```c

```
