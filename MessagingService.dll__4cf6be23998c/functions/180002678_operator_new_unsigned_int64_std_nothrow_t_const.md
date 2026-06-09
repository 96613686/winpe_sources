# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180002678`
- end: `0x180002697`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002bd8`
- `0x180005030`
- `0x180005c68`
- `0x1800093e4`

## callees

- `0x180001730`
- `0x180002678`

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
0x180002678  sub     rsp, 38h
0x18000267c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002685  call    ??2@YAPEAX_K@Z
0x18000268a  nop
0x18000268b  jmp     short loc_180002692
0x18000268d  mov     rax, [rsp+38h+arg_10]
0x180002692  add     rsp, 38h
0x180002696  retn
```
