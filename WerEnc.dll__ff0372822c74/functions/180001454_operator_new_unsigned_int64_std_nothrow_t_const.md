# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180001454`
- end: `0x180001470`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800027e0`
- `0x180002a00`

## callees

- `0x180001454`
- `0x180001a10`

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
0x180001454  sub     rsp, 38h
0x180001458  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001461  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001466  jmp     short loc_18000146A
0x180001468  xor     eax, eax
0x18000146a  add     rsp, 38h
0x18000146e  retn
```
