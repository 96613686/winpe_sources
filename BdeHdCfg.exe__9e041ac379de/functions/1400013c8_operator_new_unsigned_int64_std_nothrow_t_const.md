# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1400013c8`
- end: `0x1400013e7`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001aa4`
- `0x140001bf4`
- `0x140002014`
- `0x140002480`

## callees

- `0x1400013c8`
- `0x140001918`

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
0x1400013c8  sub     rsp, 38h
0x1400013cc  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400013d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400013da  nop
0x1400013db  jmp     short loc_1400013E2
0x1400013dd  mov     rax, [rsp+38h+arg_10]
0x1400013e2  add     rsp, 38h
0x1400013e6  retn
```
