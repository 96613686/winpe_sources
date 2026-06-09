# MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)

- ea: `0x18002b944`
- end: `0x18002b9ac`
- name: `?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z`
- size: `104`
- prototype: `bool(const wchar_t *, HKEY, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002a18c`
- `0x18002a280`
- `0x18002add0`
- `0x18002bb88`

## callees

- `0x18002b80c`
- `0x18002b944`
- `0x18002b9b4`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18002b970`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002b970`

## pseudocode

```c

```
