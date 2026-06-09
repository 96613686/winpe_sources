# AppxAllUserStore::DependencyPackageHasOtherDependents(HKEY__ * const,ushort const *,ushort const *,Common::COMMON_STRING const *,bool *)

- ea: `0x180021c50`
- end: `0x180021ea1`
- name: `?DependencyPackageHasOtherDependents@AppxAllUserStore@@YAJQEAUHKEY__@@PEBG1PEBUCOMMON_STRING@Common@@PEA_N@Z`
- size: `593`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY lpSubKey, wchar_t *String2, struct Common::COMMON_STRING *, const struct Common::COMMON_STRING *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800348b8`

## callees

- `0x180004920`
- `0x180004940`
- `0x180004968`
- `0x180004b18`
- `0x180007a10`
- `0x18000ce40`
- `0x18000d6a0`
- `0x18000d710`
- `0x180017f50`
- `0x180021c50`
- `0x180021ea8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180021d0f`
- `msvcrt!_wcsicmp` at `0x180021d23`
- `msvcrt!_wcsicmp` at `0x180021d0f`
- `msvcrt!_wcsicmp` at `0x180021d23`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180021cf8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180021cf8`

## pseudocode

```c

```
