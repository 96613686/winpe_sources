# Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysDecompressFileWithoutValidation(ulong,void *,void *,Windows::Rtl::KtmTransactionInfoPointer,ulong *)

- ea: `0x180124d98`
- end: `0x18012548d`
- name: `?SysDecompressFileWithoutValidation@DirectFileSystemProvider@SystemImplementation@Rtl@Windows@@QEAAJKPEAX0UKtmTransactionInfoPointer@34@PEAK@Z`
- size: `1781`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180124b80`

## callees

- `0x1800031d0`
- `0x18000e098`
- `0x180030b68`
- `0x18003104c`
- `0x180049274`
- `0x1800497c0`
- `0x18004a05c`
- `0x18011c984`
- `0x180124d98`
- `0x180127440`
- `0x18012e494`
- `0x18012e8e8`
- `0x1801bd010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18012512a`
- `ntdll!RtlFreeHeap` at `0x1801251f8`
- `ntdll!RtlFreeHeap` at `0x180125279`
- `ntdll!RtlFreeHeap` at `0x180125313`
- `ntdll!RtlFreeHeap` at `0x18012542c`
- `ntdll!RtlFreeHeap` at `0x18012512a`
- `ntdll!RtlFreeHeap` at `0x1801251f8`
- `ntdll!RtlFreeHeap` at `0x180125279`
- `ntdll!RtlFreeHeap` at `0x180125313`
- `ntdll!RtlFreeHeap` at `0x18012542c`

## string_xrefs

- `0x1801250e9`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysDecompressFileWithoutValidation`
- `0x1801251b4`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysDecompressFileWithoutValidation`
- `0x1801250c9`: `Error: Failed to copy EA from source: {0} to destination: {1}.`
- `0x1801253b3`: `WOF: Not-beneficial-to-compress: {0}`
- `0x1801253c5`: `WOF: Compressed-file: {0}`
- `0x1801253aa`: `WOF: Cannot-Compress-file: {0} disposition:{1}`

## pseudocode

```c

```
