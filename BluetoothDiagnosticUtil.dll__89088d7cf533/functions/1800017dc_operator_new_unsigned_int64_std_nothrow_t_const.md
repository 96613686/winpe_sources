# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800017dc`
- end: `0x1800017fb`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b50`
- `0x180002df8`
- `0x1800030a0`
- `0x1800087a0`
- `0x180008f80`

## callees

- `0x180001184`
- `0x1800017dc`

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
0x1800017dc  sub     rsp, 38h
0x1800017e0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800017e9  call    ??2@YAPEAX_K@Z
0x1800017ee  nop
0x1800017ef  jmp     short loc_1800017F6
0x1800017f1  mov     rax, [rsp+38h+arg_10]
0x1800017f6  add     rsp, 38h
0x1800017fa  retn
```
