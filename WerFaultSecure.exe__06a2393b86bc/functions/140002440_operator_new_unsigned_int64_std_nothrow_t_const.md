# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x140002440`
- end: `0x14000245c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007350`
- `0x14000db78`
- `0x14000e12c`
- `0x14000e640`

## callees

- `0x140002440`
- `0x140002994`

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
0x140002440  sub     rsp, 38h
0x140002444  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000244d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002452  jmp     short loc_140002456
0x140002454  xor     eax, eax
0x140002456  add     rsp, 38h
0x14000245a  retn
```
