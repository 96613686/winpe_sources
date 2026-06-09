# Windows::Compat::Appraiser::BinaryEverything::WriteString(ushort const *,IStream *)

- ea: `0x1800e37b8`
- end: `0x1800e39b6`
- name: `?WriteString@BinaryEverything@Appraiser@Compat@Windows@@AEAAJPEBGPEAUIStream@@@Z`
- size: `510`
- prototype: `int(Windows::Compat::Appraiser::BinaryEverything *__hidden this, const unsigned __int16 *, struct IStream *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800e3480`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x1800e37b8`
- `0x18021f010`

## import_xrefs

- `KERNEL32!HeapReAlloc` at `0x1800e388c`
- `KERNEL32!HeapReAlloc` at `0x1800e388c`
- `KERNEL32!WideCharToMultiByte` at `0x1800e37ff`
- `KERNEL32!WideCharToMultiByte` at `0x1800e38d9`
- `KERNEL32!WideCharToMultiByte` at `0x1800e37ff`
- `KERNEL32!WideCharToMultiByte` at `0x1800e38d9`
- `KERNEL32!GetProcessHeap` at `0x1800e3875`
- `KERNEL32!GetProcessHeap` at `0x1800e3875`
- `KERNEL32!GetLastError` at `0x1800e380c`
- `KERNEL32!GetLastError` at `0x1800e382b`
- `KERNEL32!GetLastError` at `0x1800e38e6`
- `KERNEL32!GetLastError` at `0x1800e3905`
- `KERNEL32!GetLastError` at `0x1800e380c`
- `KERNEL32!GetLastError` at `0x1800e382b`
- `KERNEL32!GetLastError` at `0x1800e38e6`
- `KERNEL32!GetLastError` at `0x1800e3905`

## string_xrefs

- `0x1800e3846`: `onecore\base\appcompat\appraiser\outputters\binaryeverything.cpp`
- `0x1800e3953`: `onecore\base\appcompat\appraiser\outputters\binaryeverything.cpp`
- `0x1800e3997`: `onecore\base\appcompat\appraiser\outputters\binaryeverything.cpp`
- `0x1800e3852`: `Windows::Compat::Appraiser::BinaryEverything::WriteString`
- `0x1800e395a`: `Windows::Compat::Appraiser::BinaryEverything::WriteString`
- `0x1800e398b`: `Windows::Compat::Appraiser::BinaryEverything::WriteString`

## pseudocode

```c

```
