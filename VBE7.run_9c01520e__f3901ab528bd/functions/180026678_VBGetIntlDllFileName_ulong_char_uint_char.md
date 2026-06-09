# VBGetIntlDllFileName(ulong,char *,uint,char *)

- ea: `0x180026678`
- end: `0x1800267f0`
- name: `?VBGetIntlDllFileName@@YAJKPEADI0@Z`
- size: `376`
- prototype: `__int64 __fastcall(unsigned int, char *, unsigned int, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002518c`

## callees

- `0x180026678`
- `0x18003ad54`
- `0x18005aa78`
- `0x18006b7e0`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!strcpy_s` at `0x1800266c7`
- `MSVCR100!strcpy_s` at `0x1800267cb`
- `MSVCR100!strcpy_s` at `0x1800266c7`
- `MSVCR100!strcpy_s` at `0x1800267cb`
- `MSVCR100!strcat_s` at `0x180026710`
- `MSVCR100!strcat_s` at `0x180026723`
- `MSVCR100!strcat_s` at `0x180026732`
- `MSVCR100!strcat_s` at `0x180026710`
- `MSVCR100!strcat_s` at `0x180026723`
- `MSVCR100!strcat_s` at `0x180026732`
- `MSVCR100!_ultoa_s` at `0x180026700`
- `MSVCR100!_ultoa_s` at `0x180026700`
- `KERNEL32!GetSystemDefaultLCID` at `0x1800266e0`
- `KERNEL32!GetSystemDefaultLCID` at `0x1800266e0`
- `KERNEL32!GetUserDefaultLCID` at `0x1800266e8`
- `KERNEL32!GetUserDefaultLCID` at `0x1800266e8`

## string_xrefs

- `0x1800266bd`: `VBE7INTL.DLL`

## pseudocode

```c

```
