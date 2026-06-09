# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180004d78`
- end: `0x180004d7d`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005474`
- `0x1800056d4`
- `0x180005b70`

## callees

- `0x180004d50`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](size_t a1, const struct std::nothrow_t *a2)
{
  return operator new(a1, a2);
}

```

## disassembly

```asm
0x180004d78  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
