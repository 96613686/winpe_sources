# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180004d50`
- end: `0x180004d6f`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001270`
- `0x1800015a0`
- `0x180001c20`
- `0x180003af0`
- `0x180004d78`
- `0x180004f98`
- `0x180005b70`

## callees

- `0x180004388`
- `0x180004d50`

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
0x180004d50  sub     rsp, 38h
0x180004d54  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180004d5d  call    ??2@YAPEAX_K@Z
0x180004d62  nop
0x180004d63  jmp     short loc_180004D6A
0x180004d65  mov     rax, [rsp+38h+arg_10]
0x180004d6a  add     rsp, 38h
0x180004d6e  retn
```
