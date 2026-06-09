# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800028ec`
- end: `0x180002908`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a63c`
- `0x18000a6ec`
- `0x18000a7b8`
- `0x18000a884`
- `0x18000aa80`
- `0x18000b5f0`
- `0x18000b8c0`
- `0x18000bcb0`
- `0x18000c250`
- `0x18000c6d0`
- `0x180012b04`

## callees

- `0x1800024c0`
- `0x1800028ec`

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
0x1800028ec  sub     rsp, 38h
0x1800028f0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800028f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800028fe  jmp     short loc_180002902
0x180002900  xor     eax, eax
0x180002902  add     rsp, 38h
0x180002906  retn
```
