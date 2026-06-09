# AttachHandleToThreadPool_0

- ea: `0x140004f06`
- end: `0x140004f0c`
- name: `AttachHandleToThreadPool_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001de4`
- `0x140001f74`
- `0x140003774`

## import_xrefs

- `webengine4!AttachHandleToThreadPool` at `0x140004f06`

## pseudocode

```c
// attributes: thunk
__int64 AttachHandleToThreadPool_0()
{
  return AttachHandleToThreadPool();
}

```

## disassembly

```asm
0x140004f06  jmp     cs:__imp_AttachHandleToThreadPool
```
