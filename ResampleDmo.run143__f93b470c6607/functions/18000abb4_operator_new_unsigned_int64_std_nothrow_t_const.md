# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x18000abb4`
- end: `0x18000abd0`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800086f4`
- `0x1800087e0`
- `0x180009b00`
- `0x180009b48`
- `0x18006d980`
- `0x18006dd10`
- `0x18006ec00`

## callees

- `0x18000abb4`
- `0x18000abfc`

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
0x18000abb4  sub     rsp, 38h
0x18000abb8  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000abc1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000abc6  jmp     short loc_18000ABCA
0x18000abc8  xor     eax, eax
0x18000abca  add     rsp, 38h
0x18000abce  retn
```
