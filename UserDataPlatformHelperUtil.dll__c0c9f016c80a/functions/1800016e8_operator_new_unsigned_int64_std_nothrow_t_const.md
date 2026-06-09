# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800016e8`
- end: `0x180001707`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002744`
- `0x180002c0c`
- `0x180002d98`
- `0x1800035f8`
- `0x180007344`

## callees

- `0x180001184`
- `0x1800016e8`

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
0x1800016e8  sub     rsp, 38h
0x1800016ec  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800016f5  call    ??2@YAPEAX_K@Z
0x1800016fa  nop
0x1800016fb  jmp     short loc_180001702
0x1800016fd  mov     rax, [rsp+38h+arg_10]
0x180001702  add     rsp, 38h
0x180001706  retn
```
