# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x18000ede8`
- end: `0x18000eded`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ef0`
- `0x18000ad2c`
- `0x180019618`
- `0x1800197a0`
- `0x18001995c`
- `0x180019e18`

## callees

- `0x18000edc0`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  return operator new(a1, a2);
}

```

## disassembly

```asm
0x18000ede8  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
