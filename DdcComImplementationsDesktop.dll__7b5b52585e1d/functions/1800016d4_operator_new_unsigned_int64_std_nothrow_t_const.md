# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800016d4`
- end: `0x1800016f0`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023d0`
- `0x180002880`
- `0x180003520`

## callees

- `0x1800016d4`
- `0x180001c80`

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
0x1800016d4  sub     rsp, 38h
0x1800016d8  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800016e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800016e6  jmp     short loc_1800016EA
0x1800016e8  xor     eax, eax
0x1800016ea  add     rsp, 38h
0x1800016ee  retn
```
