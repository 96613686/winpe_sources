# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800033bc`
- end: `0x1800033d8`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d940`
- `0x180010120`
- `0x1800114f0`
- `0x18001176c`
- `0x1800118bc`

## callees

- `0x180002ec0`
- `0x1800033bc`

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
0x1800033bc  sub     rsp, 38h
0x1800033c0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800033c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800033ce  jmp     short loc_1800033D2
0x1800033d0  xor     eax, eax
0x1800033d2  add     rsp, 38h
0x1800033d6  retn
```
