# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x140002600`
- end: `0x140002605`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000731c`
- `0x1400082d4`
- `0x14000bf90`

## callees

- `0x1400025d8`

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
0x140002600  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
