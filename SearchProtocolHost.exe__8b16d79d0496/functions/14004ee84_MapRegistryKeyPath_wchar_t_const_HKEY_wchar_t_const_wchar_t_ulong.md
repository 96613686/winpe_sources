# MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)

- ea: `0x14004ee84`
- end: `0x14004eeec`
- name: `?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z`
- size: `104`
- prototype: `bool(const wchar_t *, HKEY, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140012738`
- `0x14001cf94`
- `0x140048f14`
- `0x140049014`
- `0x140049bdc`
- `0x14004cbac`
- `0x14004f050`

## callees

- `0x14004ed4c`
- `0x14004ee84`
- `0x14004eef4`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x14004eeb0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14004eeb0`

## pseudocode

```c

```
