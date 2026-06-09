# ConnectedStorage::VerifyFilePathHandler::_VerifyPeers(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800508b4`
- end: `0x180050cb7`
- name: `?_VerifyPeers@VerifyFilePathHandler@ConnectedStorage@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1027`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callers

- `0x18004f820`
- `0x1800508b4`

## callees

- `0x180003c70`
- `0x180004754`
- `0x180005ae0`
- `0x18000aae4`
- `0x18000b5b8`
- `0x18000d6bc`
- `0x18000db98`
- `0x180010e30`
- `0x180012c98`
- `0x18001c090`
- `0x1800296a4`
- `0x180032674`
- `0x180033394`
- `0x1800333e8`
- `0x18004f1d0`
- `0x18004f7c8`
- `0x1800508b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180050a27`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180050b0a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180050b4d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180050c11`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180050a27`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180050b0a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180050b4d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180050c11`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180050c1f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180050c1f`

## string_xrefs

- `0x180050c6c`: `StringCchCopyW(pattern, MAX_PATH, peerPath.c_str())`
- `0x180050c88`: `StringCchCopyW(subdirectory, MAX_PATH, peerPath.c_str())`
- `0x180050c96`: `StringCchCopyW(filename, MAX_PATH, peerPath.c_str())`

## pseudocode

```c

```
