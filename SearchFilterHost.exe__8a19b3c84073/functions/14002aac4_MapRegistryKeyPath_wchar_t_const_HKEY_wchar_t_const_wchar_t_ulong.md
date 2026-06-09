# MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)

- ea: `0x14002aac4`
- end: `0x14002ab2c`
- name: `?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z`
- size: `104`
- prototype: `bool(const wchar_t *, HKEY, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140028588`
- `0x1400290b8`
- `0x14002a538`
- `0x14002acfc`

## callees

- `0x14002a98c`
- `0x14002aac4`
- `0x14002ab34`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x14002aaf0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14002aaf0`

## pseudocode

```c

```
