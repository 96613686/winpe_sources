# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x140121218`
- end: `0x140121867`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1615`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x140120d48`
- `0x140121218`

## callees

- `0x14001193c`
- `0x1400408d0`
- `0x140056ac0`
- `0x14011c324`
- `0x14011cb38`
- `0x14011cff0`
- `0x14011d430`
- `0x14011e604`
- `0x14011e9e0`
- `0x14011f088`
- `0x140120a50`
- `0x140120b88`
- `0x140121218`
- `0x1401226a0`
- `0x14012276c`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x14012129d`
- `KERNEL32!lstrcmpiW` at `0x1401212b0`
- `KERNEL32!lstrcmpiW` at `0x140121366`
- `KERNEL32!lstrcmpiW` at `0x140121392`
- `KERNEL32!lstrcmpiW` at `0x14012129d`
- `KERNEL32!lstrcmpiW` at `0x1401212b0`
- `KERNEL32!lstrcmpiW` at `0x140121366`
- `KERNEL32!lstrcmpiW` at `0x140121392`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1401216a4`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1401216a4`
- `ADVAPI32!RegCloseKey` at `0x140121475`
- `ADVAPI32!RegCloseKey` at `0x140121498`
- `ADVAPI32!RegCloseKey` at `0x140121596`
- `ADVAPI32!RegCloseKey` at `0x1401217b8`
- `ADVAPI32!RegCloseKey` at `0x140121843`
- `ADVAPI32!RegCloseKey` at `0x140121856`
- `ADVAPI32!RegCloseKey` at `0x140121475`
- `ADVAPI32!RegCloseKey` at `0x140121498`
- `ADVAPI32!RegCloseKey` at `0x140121596`
- `ADVAPI32!RegCloseKey` at `0x1401217b8`
- `ADVAPI32!RegCloseKey` at `0x140121843`
- `ADVAPI32!RegCloseKey` at `0x140121856`
- `ADVAPI32!RegCreateKeyExW` at `0x14012157f`
- `ADVAPI32!RegCreateKeyExW` at `0x14012157f`
- `ADVAPI32!RegDeleteValueW` at `0x14012145c`
- `ADVAPI32!RegDeleteValueW` at `0x14012145c`

## string_xrefs

- `0x14012135c`: `NoRemove`
- `0x140121293`: `Delete`
- `0x1401212a6`: `ForceRemove`

## pseudocode

```c

```
