# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180001fcc`
- end: `0x180001fe8`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006740`
- `0x1800073c0`
- `0x1800074b0`

## callees

- `0x180001fc0`
- `0x180001fcc`

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
0x180001fcc  sub     rsp, 38h
0x180001fd0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001fd9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001fde  jmp     short loc_180001FE2
0x180001fe0  xor     eax, eax
0x180001fe2  add     rsp, 38h
0x180001fe6  retn
```
