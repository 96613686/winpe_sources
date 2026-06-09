# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001e68`
- end: `0x180001e87`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180005f80`
- `0x1800062f0`
- `0x1800065a0`
- `0x1800073b0`
- `0x1800074f0`
- `0x180007630`
- `0x180007770`
- `0x1800078b0`
- `0x1800079f0`
- `0x180007b30`
- `0x180007c78`
- `0x180007e30`
- `0x180007f30`
- `0x180008030`
- `0x180008140`
- `0x1800081c0`
- `0x18000f1c0`
- `0x18000f2c0`

## callees

- `0x1800015c0`
- `0x180001e68`

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
0x180001e68  sub     rsp, 38h
0x180001e6c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001e75  call    ??2@YAPEAX_K@Z
0x180001e7a  nop
0x180001e7b  jmp     short loc_180001E82
0x180001e7d  mov     rax, [rsp+38h+arg_10]
0x180001e82  add     rsp, 38h
0x180001e86  retn
```
