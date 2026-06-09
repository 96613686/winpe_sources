# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001ce0`
- end: `0x180001cfc`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800029f0`
- `0x180002e50`

## callees

- `0x180001ce0`
- `0x1800022ac`

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
0x180001ce0  sub     rsp, 38h
0x180001ce4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001ced  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001cf2  jmp     short loc_180001CF6
0x180001cf4  xor     eax, eax
0x180001cf6  add     rsp, 38h
0x180001cfa  retn
```
