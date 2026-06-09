# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180002188`
- end: `0x1800021a7`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021b0`
- `0x180005f14`
- `0x180005f88`
- `0x180007dec`

## callees

- `0x18000126c`
- `0x180002188`

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
0x180002188  sub     rsp, 38h
0x18000218c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002195  call    ??2@YAPEAX_K@Z
0x18000219a  nop
0x18000219b  jmp     short loc_1800021A2
0x18000219d  mov     rax, [rsp+38h+arg_10]
0x1800021a2  add     rsp, 38h
0x1800021a6  retn
```
