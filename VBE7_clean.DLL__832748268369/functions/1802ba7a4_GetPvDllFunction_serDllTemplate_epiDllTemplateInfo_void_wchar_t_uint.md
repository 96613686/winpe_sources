# GetPvDllFunction(serDllTemplate *,epiDllTemplateInfo *,void * *,wchar_t * *,uint *)

- ea: `0x1802ba7a4`
- end: `0x1802baa4a`
- name: `?GetPvDllFunction@@YAJPEAUserDllTemplate@@PEAUepiDllTemplateInfo@@PEAPEAXPEAPEA_WPEAI@Z`
- size: `678`
- prototype: `__int64 __fastcall(struct serDllTemplate *, struct epiDllTemplateInfo *, void **, wchar_t **, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1802ba52c`
- `0x1802ba63c`

## callees

- `0x180024478`
- `0x18002be9c`
- `0x1800e1bf0`
- `0x1801487bc`
- `0x180174f88`
- `0x18018d470`
- `0x1801b0dd0`
- `0x1801b0e54`
- `0x1801b0e90`
- `0x1801b0eb4`
- `0x1802ba610`
- `0x1802ba7a4`
- `0x1802baa50`
- `0x1802cbf28`
- `0x180379520`

## import_xrefs

- `MSVCR100!_itoa_s` at `0x1802ba93a`
- `MSVCR100!_itoa_s` at `0x1802ba93a`
- `MSVCR100!_stricmp` at `0x1802ba827`
- `MSVCR100!_stricmp` at `0x1802ba827`
- `KERNEL32!GetProcAddress` at `0x1802ba903`
- `KERNEL32!GetProcAddress` at `0x1802ba9a5`
- `KERNEL32!GetProcAddress` at `0x1802ba903`
- `KERNEL32!GetProcAddress` at `0x1802ba9a5`
- `KERNEL32!SetErrorMode` at `0x1802ba802`
- `KERNEL32!SetErrorMode` at `0x1802ba878`
- `KERNEL32!SetErrorMode` at `0x1802ba8c0`
- `KERNEL32!SetErrorMode` at `0x1802ba802`
- `KERNEL32!SetErrorMode` at `0x1802ba878`
- `KERNEL32!SetErrorMode` at `0x1802ba8c0`

## string_xrefs

- `0x1802ba81b`: `VBE6.DLL`
- `0x1802ba831`: `VBE7.DLL`

## pseudocode

```c

```
