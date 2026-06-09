# operator delete(void *,std::nothrow_t const &)

- ea: `0x140001a0c`
- end: `0x140001a11`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000510c`
- `0x1400051c8`
- `0x1400055ec`
- `0x140006680`
- `0x140008700`
- `0x140008828`
- `0x140038164`
- `0x14003c494`
- `0x14003c5cc`

## callees

- `0x140001a00`

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
0x140001a0c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
