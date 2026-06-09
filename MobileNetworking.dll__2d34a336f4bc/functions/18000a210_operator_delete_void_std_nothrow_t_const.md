# operator delete(void *,std::nothrow_t const &)

- ea: `0x18000a210`
- end: `0x18000a215`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006340`
- `0x180008070`
- `0x180011970`

## callees

- `0x18000a1a8`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18000a210  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
