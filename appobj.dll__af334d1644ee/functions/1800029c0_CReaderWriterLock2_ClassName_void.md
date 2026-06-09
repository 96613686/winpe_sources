# CReaderWriterLock2::ClassName(void)

- ea: `0x1800029c0`
- end: `0x1800029c8`
- name: `?ClassName@CReaderWriterLock2@@SAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x1800029c0`: `CReaderWriterLock2`

## pseudocode

```c
const unsigned __int16 *CReaderWriterLock2::ClassName(void)
{
  return L"CReaderWriterLock2";
}

```

## disassembly

```asm
0x1800029c0  lea     rax, aCreaderwriterl; "CReaderWriterLock2"
0x1800029c7  retn
```
