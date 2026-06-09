# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800022c0`
- end: `0x1800022c5`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003a80`
- `0x180003ac0`
- `0x180006830`
- `0x1800071b0`
- `0x1800071e0`
- `0x180007700`
- `0x180009c00`
- `0x180009c40`
- `0x180009cc0`
- `0x180009cf4`
- `0x180009d30`
- `0x180009d70`
- `0x180009dd0`
- `0x180009e00`
- `0x180009e40`
- `0x180009e80`
- `0x180009ec0`
- `0x18000c540`
- `0x18000c650`
- `0x18000ef30`
- `0x18000ef70`
- `0x18000f0e0`
- `0x18001027c`

## callees

- `0x180002320`

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
0x1800022c0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
