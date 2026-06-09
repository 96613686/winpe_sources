# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180002b38`
- end: `0x180002b54`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007990`
- `0x180009110`
- `0x1800098d0`

## callees

- `0x180002b38`
- `0x180002b5c`

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
0x180002b38  sub     rsp, 38h
0x180002b3c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002b45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002b4a  jmp     short loc_180002B4E
0x180002b4c  xor     eax, eax
0x180002b4e  add     rsp, 38h
0x180002b52  retn
```
