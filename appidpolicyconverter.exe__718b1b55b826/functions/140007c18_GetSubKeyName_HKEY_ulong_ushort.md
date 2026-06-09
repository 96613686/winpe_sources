# GetSubKeyName(HKEY__ *,ulong,ushort * *)

- ea: `0x140007c18`
- end: `0x140007cf8`
- name: `?GetSubKeyName@@YAKPEAUHKEY__@@KPEAPEAG@Z`
- size: `224`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD dwIndex, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400022ac`
- `0x1400023d0`
- `0x1400024d4`
- `0x140003bc0`
- `0x14000458c`

## callees

- `0x140007c18`
- `0x140008d30`
- `0x140008ef4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007ca7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007ca7`

## pseudocode

```c

```
