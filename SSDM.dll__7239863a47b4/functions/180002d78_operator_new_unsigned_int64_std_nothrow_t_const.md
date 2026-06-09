# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180002d78`
- end: `0x180002d97`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007594`
- `0x18000a3d0`
- `0x18000d780`
- `0x18000dd40`

## callees

- `0x180002a88`
- `0x180002d78`

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
0x180002d78  sub     rsp, 38h
0x180002d7c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002d85  call    ??2@YAPEAX_K@Z
0x180002d8a  nop
0x180002d8b  jmp     short loc_180002D92
0x180002d8d  mov     rax, [rsp+38h+arg_10]
0x180002d92  add     rsp, 38h
0x180002d96  retn
```
