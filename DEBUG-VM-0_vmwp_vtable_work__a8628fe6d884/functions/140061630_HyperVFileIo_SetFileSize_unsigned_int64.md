# HyperVFileIo::SetFileSize(unsigned __int64)

- ea: `0x140061630`
- end: `0x140061741`
- name: `?SetFileSize@HyperVFileIo@@UEAAX_K@Z`
- size: `273`
- prototype: `void(HyperVFileIo *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400612b0`

## callees

- `0x1400281f8`
- `0x140061630`
- `0x14006af38`
- `0x1400db600`
- `0x1401cbe90`
- `0x1401cca18`
- `0x1401ccbb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006168b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400616ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006168b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400616ef`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1400616db`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1400616db`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140061677`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140061677`

## string_xrefs

- `0x140061652`: `onecore\vm\common\hypervstorage\hypervfileio.cpp`

## pseudocode

```c

```
