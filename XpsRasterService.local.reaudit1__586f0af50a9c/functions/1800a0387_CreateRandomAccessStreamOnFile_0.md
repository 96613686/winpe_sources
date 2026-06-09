# CreateRandomAccessStreamOnFile_0

- ea: `0x1800a0387`
- end: `0x1800a038d`
- name: `CreateRandomAccessStreamOnFile_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180007960`

## import_xrefs

- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x1800a0387`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CreateRandomAccessStreamOnFile_0(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return CreateRandomAccessStreamOnFile(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800a0387  jmp     cs:__imp_CreateRandomAccessStreamOnFile
```
