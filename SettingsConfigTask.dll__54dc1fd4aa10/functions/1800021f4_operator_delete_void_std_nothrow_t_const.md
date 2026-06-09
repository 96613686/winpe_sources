# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800021f4`
- end: `0x1800021f9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004b50`
- `0x180004b90`
- `0x180004bd0`
- `0x180004c10`
- `0x180004c50`
- `0x180004c90`
- `0x180004ce0`
- `0x180004d20`
- `0x180004d60`
- `0x18000e0b8`
- `0x1800134f0`
- `0x180013530`
- `0x180013588`
- `0x18001a4b0`
- `0x18001a500`
- `0x18001a610`
- `0x180022acf`

## callees

- `0x1800027f0`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1800021f4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
