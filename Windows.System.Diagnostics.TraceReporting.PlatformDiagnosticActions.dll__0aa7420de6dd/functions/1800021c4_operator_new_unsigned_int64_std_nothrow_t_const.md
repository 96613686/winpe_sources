# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800021c4`
- end: `0x1800021e0`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006730`
- `0x180007aa0`
- `0x180007de0`
- `0x180008370`

## callees

- `0x180002180`
- `0x1800021c4`

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
0x1800021c4  sub     rsp, 38h
0x1800021c8  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800021d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800021d6  jmp     short loc_1800021DA
0x1800021d8  xor     eax, eax
0x1800021da  add     rsp, 38h
0x1800021de  retn
```
