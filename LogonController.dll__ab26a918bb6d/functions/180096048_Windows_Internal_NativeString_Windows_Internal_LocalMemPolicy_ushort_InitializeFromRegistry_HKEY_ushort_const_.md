# Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x180096048`
- end: `0x180096201`
- name: `?_InitializeFromRegistry@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `441`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180095ca8`
- `0x180099420`

## callees

- `0x1800926c4`
- `0x180096048`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800960dd`
- `KERNEL32!LocalAlloc` at `0x180096152`
- `KERNEL32!LocalAlloc` at `0x1800960dd`
- `KERNEL32!LocalAlloc` at `0x180096152`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18009613f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180096170`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18009613f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180096170`
- `KERNEL32!LocalFree` at `0x180096187`
- `KERNEL32!LocalFree` at `0x1800961d2`
- `KERNEL32!LocalFree` at `0x1800961e2`
- `KERNEL32!LocalFree` at `0x180096187`
- `KERNEL32!LocalFree` at `0x1800961d2`
- `KERNEL32!LocalFree` at `0x1800961e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180096093`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009610b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180096093`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009610b`

## pseudocode

```c

```
