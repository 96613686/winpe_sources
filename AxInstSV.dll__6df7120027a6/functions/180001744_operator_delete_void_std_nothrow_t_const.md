# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001744`
- end: `0x180001749`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `31`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002774`
- `0x180002db0`
- `0x180002df0`
- `0x180002e30`
- `0x180007220`
- `0x18000831c`
- `0x180008930`
- `0x180008c40`
- `0x180008c80`
- `0x180008cc0`
- `0x180008cfc`
- `0x180008d30`
- `0x180008d70`
- `0x180008db0`
- `0x180008df0`
- `0x180008e30`
- `0x180008e80`
- `0x180008ec0`
- `0x180009270`
- `0x18000a03c`
- `0x18000c3d8`
- `0x180010154`
- `0x180011cb0`
- `0x180011ce0`
- `0x1800121e0`
- `0x18001449d`
- `0x18001462b`
- `0x180014781`
- `0x1800149af`
- `0x1800149d2`
- `0x180014acd`

## callees

- `0x180001704`

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
0x180001744  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
