# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180001a40`
- end: `0x180001a5c`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002930`
- `0x180002dd0`
- `0x18000791c`

## callees

- `0x180001a40`
- `0x180001f8c`

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
0x180001a40  sub     rsp, 38h
0x180001a44  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001a4d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001a52  jmp     short loc_180001A56
0x180001a54  xor     eax, eax
0x180001a56  add     rsp, 38h
0x180001a5a  retn
```
