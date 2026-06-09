# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001d0c`
- end: `0x180001d28`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008050`
- `0x180008130`
- `0x180008208`
- `0x1800082fc`

## callees

- `0x180001cbc`
- `0x180001d0c`

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
0x180001d0c  sub     rsp, 38h
0x180001d10  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001d19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001d1e  jmp     short loc_180001D22
0x180001d20  xor     eax, eax
0x180001d22  add     rsp, 38h
0x180001d26  retn
```
