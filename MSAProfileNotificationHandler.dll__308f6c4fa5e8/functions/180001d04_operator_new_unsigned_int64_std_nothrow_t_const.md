# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180001d04`
- end: `0x180001d20`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ae0`
- `0x18000789c`

## callees

- `0x180001d04`
- `0x1800022f0`

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
0x180001d04  sub     rsp, 38h
0x180001d08  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001d11  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001d16  jmp     short loc_180001D1A
0x180001d18  xor     eax, eax
0x180001d1a  add     rsp, 38h
0x180001d1e  retn
```
