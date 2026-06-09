# OSIntegration::DEH::EventTracing::RegisterOrUnregisterEventManifest(bool,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180116798`
- end: `0x180116c6c`
- name: `?RegisterOrUnregisterEventManifest@EventTracing@DEH@OSIntegration@@YAJ_NPEBG111K@Z`
- size: `1236`
- prototype: `__int64 __fastcall(OSIntegration::DEH::EventTracing *this, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180072364`
- `0x180072e0c`

## callees

- `0x18004a838`
- `0x18005174c`
- `0x180061c78`
- `0x180064030`
- `0x180065acc`
- `0x180066780`
- `0x180072114`
- `0x180084eac`
- `0x1800a2aec`
- `0x1800aed10`
- `0x1800af918`
- `0x1800ef2ec`
- `0x180116798`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180116b70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180116b70`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180116bd4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180116bd4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180116b44`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180116b44`

## string_xrefs

- `0x1801168d3`: `install-manifest`
- `0x1801169cf`: `/messageFilePath:`
- `0x180116a39`: `/parameterFilePath:`
- `0x1801168e7`: `uninstall-manifest`
- `0x18011695a`: `/resourceFilePath:`

## pseudocode

```c

```
