# operator delete(void *,std::nothrow_t const &)

- ea: `0x1400025a4`
- end: `0x1400025a9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `31`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400062a0`
- `0x140006300`
- `0x140006340`
- `0x140006370`
- `0x1400063b0`
- `0x1400063e0`
- `0x140006514`
- `0x140007004`
- `0x140007758`
- `0x1400079e8`
- `0x140007eb8`
- `0x140009210`
- `0x140009270`
- `0x1400092b0`
- `0x1400092f0`
- `0x14000a3a0`
- `0x14000a3e0`
- `0x14000eb90`
- `0x140011d0c`
- `0x140012678`
- `0x140013d48`
- `0x140014490`
- `0x1400149ec`
- `0x1400163a0`
- `0x1400163e0`
- `0x140016d8c`
- `0x14001726c`
- `0x1400241d0`
- `0x140024210`
- `0x14002606c`
- `0x140027030`

## callees

- `0x140002b10`

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
0x1400025a4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
