# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001e08`
- end: `0x180001e27`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002590`
- `0x18000266c`
- `0x18000e184`
- `0x180010750`

## callees

- `0x1800018f4`
- `0x180001e08`

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
0x180001e08  sub     rsp, 38h
0x180001e0c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001e15  call    ??2@YAPEAX_K@Z
0x180001e1a  nop
0x180001e1b  jmp     short loc_180001E22
0x180001e1d  mov     rax, [rsp+38h+arg_10]
0x180001e22  add     rsp, 38h
0x180001e26  retn
```
