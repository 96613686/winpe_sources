# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x14000164c`
- end: `0x140001651`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001fac`
- `0x140003090`
- `0x14000369c`

## callees

- `0x140001558`

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
0x14000164c  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
