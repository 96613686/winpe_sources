# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001e6c`
- end: `0x180001e8b`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c218`
- `0x18000dc80`
- `0x18000e038`
- `0x180011a40`

## callees

- `0x180001e6c`
- `0x1800022a8`

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
0x180001e6c  sub     rsp, 38h
0x180001e70  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001e79  call    ??2@YAPEAX_K@Z
0x180001e7e  nop
0x180001e7f  jmp     short loc_180001E86
0x180001e81  mov     rax, [rsp+38h+arg_10]
0x180001e86  add     rsp, 38h
0x180001e8a  retn
```
