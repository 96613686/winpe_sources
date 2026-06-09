# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180002188`
- end: `0x1800021a4`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037b8`
- `0x180003c58`
- `0x1800065cc`
- `0x18000ae98`
- `0x18000b11c`
- `0x18000dc70`
- `0x18000e90c`

## callees

- `0x180002188`
- `0x1800022b4`

## pseudocode

```c
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  void *result; // rax

  try
  {
    result = operator new[](a1);
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
0x180002188  sub     rsp, 38h
0x18000218c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002195  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000219a  jmp     short loc_18000219E
0x18000219c  xor     eax, eax
0x18000219e  add     rsp, 38h
0x1800021a2  retn
```
