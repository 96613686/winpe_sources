# ConnectedStorage::File::RecurseDeleteDirectory(ushort const *,bool,ConnectedStorage::VerifyFilePathHandler &)

- ea: `0x18004f948`
- end: `0x18004fbf9`
- name: `?RecurseDeleteDirectory@File@ConnectedStorage@@CAXPEBG_NAEAVVerifyFilePathHandler@2@@Z`
- size: `689`
- prototype: `void __fastcall(const unsigned __int16 *, char, struct ConnectedStorage::VerifyFilePathHandler *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18004e240`
- `0x18004f948`

## callees

- `0x180003c70`
- `0x180004754`
- `0x18000aae4`
- `0x18000b5b8`
- `0x180010e30`
- `0x18001c090`
- `0x180032674`
- `0x180033394`
- `0x1800333e8`
- `0x18004f1d0`
- `0x18004f948`
- `0x180050348`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004f9d0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004fab2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004fac9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004fb0e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004f9d0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004fab2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004fac9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004fb0e`

## string_xrefs

- `0x18004fa26`: `File::RecurseDeleteDirectory`
- `0x18004fbdb`: `StringCchCopyW(subdirectory, MAX_PATH, directory)`
- `0x18004fbea`: `StringCchCopyW(filename, MAX_PATH, directory)`

## pseudocode

```c

```
