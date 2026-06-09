# operator delete(void *,std::nothrow_t const &)

- ea: `0x1400023f4`
- end: `0x1400023f9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003650`
- `0x140003690`
- `0x140006da8`
- `0x140006dd0`
- `0x140007350`
- `0x140008d3c`
- `0x140008e60`
- `0x140008ea0`
- `0x140008ee0`
- `0x140008f40`
- `0x14000cc0c`
- `0x14000cfc4`
- `0x14000d5b8`
- `0x14000dc44`
- `0x14000de94`
- `0x14000e12c`
- `0x14000e640`
- `0x14000e750`
- `0x14000e820`
- `0x14000e8c4`
- `0x14000f4b0`
- `0x14000f81c`
- `0x14000fdd8`
- `0x1400104f4`

## callees

- `0x140002988`

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
0x1400023f4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
