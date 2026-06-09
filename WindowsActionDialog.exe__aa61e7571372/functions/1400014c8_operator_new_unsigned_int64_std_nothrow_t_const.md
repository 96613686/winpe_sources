# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1400014c8`
- end: `0x1400014e4`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002b70`
- `0x140007d6c`
- `0x140008fb0`

## callees

- `0x140001484`
- `0x1400014c8`

## pseudocode

```c
void *__fastcall operator new(size_t a1, const struct std::nothrow_t *a2)
{
  void *result; // rax

  try
  {
    result = operator new(a1);
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400014c8  sub     rsp, 38h
0x1400014cc  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400014d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400014da  jmp     short loc_1400014DE
0x1400014dc  xor     eax, eax
0x1400014de  add     rsp, 38h
0x1400014e2  retn
```
