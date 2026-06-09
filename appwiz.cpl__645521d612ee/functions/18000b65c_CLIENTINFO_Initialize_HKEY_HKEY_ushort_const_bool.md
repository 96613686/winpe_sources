# CLIENTINFO::Initialize(HKEY__ *,HKEY__ *,ushort const *,bool)

- ea: `0x18000b65c`
- end: `0x18000b8a6`
- name: `?Initialize@CLIENTINFO@@AEAA_NPEAUHKEY__@@0PEBG_N@Z`
- size: `586`
- prototype: `bool __fastcall(CLIENTINFO *__hidden this, HKEY hkey, HKEY, PCWSTR pszSrch, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a460`

## callees

- `0x18000af30`
- `0x18000b65c`
- `0x18000d25c`
- `0x1800582e0`

## import_xrefs

- `SHCORE!SHGetValueW` at `0x18000b853`
- `SHCORE!SHGetValueW` at `0x18000b853`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x18000b7d8`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x18000b7fe`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x18000b7d8`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x18000b7fe`
- `SHLWAPI!StrDupW` at `0x18000b6a4`
- `SHLWAPI!StrDupW` at `0x18000b816`
- `SHLWAPI!StrDupW` at `0x18000b871`
- `SHLWAPI!StrDupW` at `0x18000b6a4`
- `SHLWAPI!StrDupW` at `0x18000b816`
- `SHLWAPI!StrDupW` at `0x18000b871`

## string_xrefs

- `0x18000b705`: `ReinstallCommand`
- `0x18000b734`: `HideIconsCommand`
- `0x18000b758`: `ShowIconsCommand`

## pseudocode

```c

```
