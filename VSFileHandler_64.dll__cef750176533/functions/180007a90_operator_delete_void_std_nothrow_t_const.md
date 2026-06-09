# operator delete(void *,std::nothrow_t const &)

- ea: `0x180007a90`
- end: `0x180007a95`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `18`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800011b0`
- `0x18000226c`
- `0x1800025c0`
- `0x180002810`
- `0x180002d30`
- `0x180003190`
- `0x180003380`
- `0x180003410`
- `0x1800035c0`
- `0x180003840`
- `0x1800038c4`
- `0x18000396c`
- `0x180003988`
- `0x18000572c`
- `0x180007aa0`
- `0x180008450`
- `0x180024d3c`
- `0x180024d89`

## callees

- `0x1800076e0`

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
0x180007a90  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
