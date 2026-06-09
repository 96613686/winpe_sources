# CReaderWriterLock::ClassName(void)

- ea: `0x1800029e0`
- end: `0x1800029e8`
- name: `?ClassName@CReaderWriterLock@@SAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x1800029e0`: `CReaderWriterLock`

## pseudocode

```c
const unsigned __int16 *CReaderWriterLock::ClassName(void)
{
  return L"CReaderWriterLock";
}

```

## disassembly

```asm
0x1800029e0  lea     rax, aCreaderwriterl_1; "CReaderWriterLock"
0x1800029e7  retn
```
