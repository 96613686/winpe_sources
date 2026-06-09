# CreateStreamOverRandomAccessStream_0

- ea: `0x1800a0393`
- end: `0x1800a0399`
- name: `CreateStreamOverRandomAccessStream_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180017400`
- `0x180017630`

## import_xrefs

- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1800a0393`

## pseudocode

```c
// attributes: thunk
__int64 CreateStreamOverRandomAccessStream_0()
{
  return CreateStreamOverRandomAccessStream();
}

```

## disassembly

```asm
0x1800a0393  jmp     cs:__imp_CreateStreamOverRandomAccessStream
```
