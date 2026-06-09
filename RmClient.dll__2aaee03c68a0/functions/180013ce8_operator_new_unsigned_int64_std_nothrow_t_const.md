# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180013ce8`
- end: `0x180013d07`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000166c`
- `0x180001780`
- `0x180002320`
- `0x18000a4b4`
- `0x18000a810`
- `0x18000ad70`
- `0x18000f4d8`
- `0x180013594`
- `0x180014900`
- `0x180017ecc`

## callees

- `0x180013ce8`
- `0x1800148c0`

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
0x180013ce8  sub     rsp, 38h
0x180013cec  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180013cf5  call    ??2@YAPEAX_K@Z
0x180013cfa  nop
0x180013cfb  jmp     short loc_180013D02
0x180013cfd  mov     rax, [rsp+38h+arg_10]
0x180013d02  add     rsp, 38h
0x180013d06  retn
```
