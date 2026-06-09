# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001d84`
- end: `0x180001da0`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180003184`
- `0x180003244`
- `0x1800032fc`
- `0x180003400`
- `0x180003498`
- `0x180006d10`
- `0x180007370`
- `0x180009474`

## callees

- `0x180001d84`
- `0x180002360`

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
0x180001d84  sub     rsp, 38h
0x180001d88  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001d91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001d96  jmp     short loc_180001D9A
0x180001d98  xor     eax, eax
0x180001d9a  add     rsp, 38h
0x180001d9e  retn
```
