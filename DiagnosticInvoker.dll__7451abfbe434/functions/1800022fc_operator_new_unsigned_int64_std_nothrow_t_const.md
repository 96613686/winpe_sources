# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800022fc`
- end: `0x180002318`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180006680`
- `0x1800072f0`
- `0x180007700`
- `0x18000795c`
- `0x180007a2c`
- `0x18000881c`
- `0x18000a4f8`
- `0x18000abb0`

## callees

- `0x1800022fc`
- `0x180002790`

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
0x1800022fc  sub     rsp, 38h
0x180002300  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002309  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000230e  jmp     short loc_180002312
0x180002310  xor     eax, eax
0x180002312  add     rsp, 38h
0x180002316  retn
```
