# PushButtonReset::WimArchive::GetCompressionType(PushButtonReset::WimArchive::Compression &)

- ea: `0x180054244`
- end: `0x18005438a`
- name: `?GetCompressionType@WimArchive@PushButtonReset@@QEAAJAEAW4Compression@12@@Z`
- size: `326`
- prototype: `__int64 __fastcall(PushButtonReset::WimArchive *__hidden this, enum PushButtonReset::WimArchive::Compression *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800204b8`

## callees

- `0x180037344`
- `0x180054244`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800542a3`
- `KERNEL32!GetLastError` at `0x1800542e5`
- `KERNEL32!GetLastError` at `0x1800542a3`
- `KERNEL32!GetLastError` at `0x1800542e5`
- `WIMGAPI!WIMGetAttributes` at `0x180054299`
- `WIMGAPI!WIMGetAttributes` at `0x180054299`

## string_xrefs

- `0x180054316`: `Unknown compression algorithm %u`
- `0x180054329`: `PbrFlagToWimCompression`
- `0x1800542d9`: `PushButtonReset::WimArchive::GetCompressionType`

## pseudocode

```c

```
