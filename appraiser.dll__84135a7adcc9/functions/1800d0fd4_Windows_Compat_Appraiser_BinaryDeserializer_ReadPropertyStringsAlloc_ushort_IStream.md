# Windows::Compat::Appraiser::BinaryDeserializer::ReadPropertyStringsAlloc(ushort * *,IStream *)

- ea: `0x1800d0fd4`
- end: `0x1800d12c1`
- name: `?ReadPropertyStringsAlloc@BinaryDeserializer@Appraiser@Compat@Windows@@AEAAJPEAPEAGPEAUIStream@@@Z`
- size: `749`
- prototype: `int(Windows::Compat::Appraiser::BinaryDeserializer *__hidden this, unsigned __int16 **, struct IStream *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d0d44`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x1800d0fd4`
- `0x1800d12c8`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1800d10de`
- `KERNEL32!MultiByteToWideChar` at `0x1800d1156`
- `KERNEL32!MultiByteToWideChar` at `0x1800d11db`
- `KERNEL32!MultiByteToWideChar` at `0x1800d1227`
- `KERNEL32!MultiByteToWideChar` at `0x1800d10de`
- `KERNEL32!MultiByteToWideChar` at `0x1800d1156`
- `KERNEL32!MultiByteToWideChar` at `0x1800d11db`
- `KERNEL32!MultiByteToWideChar` at `0x1800d1227`
- `KERNEL32!GetProcessHeap` at `0x1800d119a`
- `KERNEL32!GetProcessHeap` at `0x1800d1284`
- `KERNEL32!GetProcessHeap` at `0x1800d119a`
- `KERNEL32!GetProcessHeap` at `0x1800d1284`
- `KERNEL32!HeapAlloc` at `0x1800d11a8`
- `KERNEL32!HeapAlloc` at `0x1800d11a8`
- `KERNEL32!GetLastError` at `0x1800d10eb`
- `KERNEL32!GetLastError` at `0x1800d1167`
- `KERNEL32!GetLastError` at `0x1800d11e5`
- `KERNEL32!GetLastError` at `0x1800d1231`
- `KERNEL32!GetLastError` at `0x1800d10eb`
- `KERNEL32!GetLastError` at `0x1800d1167`
- `KERNEL32!GetLastError` at `0x1800d11e5`
- `KERNEL32!GetLastError` at `0x1800d1231`
- `KERNEL32!HeapFree` at `0x1800d1292`
- `KERNEL32!HeapFree` at `0x1800d1292`

## string_xrefs

- `0x1800d101c`: `onecore\base\appcompat\appraiser\inventory\binarydeserializer.cpp`
- `0x1800d1051`: `onecore\base\appcompat\appraiser\inventory\binarydeserializer.cpp`
- `0x1800d1010`: `Windows::Compat::Appraiser::BinaryDeserializer::ReadPropertyStringsAlloc`
- `0x1800d1045`: `Windows::Compat::Appraiser::BinaryDeserializer::ReadPropertyStringsAlloc`
- `0x1800d1003`: `Error reading string to buffer: [0x%x].`

## pseudocode

```c

```
