# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180001cc8`
- end: `0x180001ce4`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028b0`

## callees

- `0x180001cc8`
- `0x180001cec`

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
0x180001cc8  sub     rsp, 38h
0x180001ccc  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001cd5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001cda  jmp     short loc_180001CDE
0x180001cdc  xor     eax, eax
0x180001cde  add     rsp, 38h
0x180001ce2  retn
```
