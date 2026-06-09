# CreateRandomAccessStreamOnFile_0

- ea: `0x1800a0387`
- end: `0x1800a038d`
- name: `CreateRandomAccessStreamOnFile_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
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
__int64 CreateRandomAccessStreamOnFile_0()
{
  return CreateRandomAccessStreamOnFile();
}

```

## disassembly

```asm
0x1800a0387  jmp     cs:__imp_CreateRandomAccessStreamOnFile
```
