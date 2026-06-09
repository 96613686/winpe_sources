# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x1400021d0`
- end: `0x1400021d5`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400069fc`
- `0x140006d44`
- `0x140008d1c`

## callees

- `0x1400021a8`

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
0x1400021d0  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
