# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001ea8`
- end: `0x180001ec4`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a164`
- `0x18000a1fc`
- `0x18000b310`
- `0x18000c870`
- `0x18000dd2c`
- `0x18000de6c`
- `0x18000e0b4`
- `0x18000e2fc`
- `0x18000e544`
- `0x18000e78c`
- `0x18000ea14`
- `0x1800146b0`

## callees

- `0x180001ea8`
- `0x180001ed8`

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
0x180001ea8  sub     rsp, 38h
0x180001eac  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001eb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001eba  jmp     short loc_180001EBE
0x180001ebc  xor     eax, eax
0x180001ebe  add     rsp, 38h
0x180001ec2  retn
```
