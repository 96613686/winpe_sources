# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x14000289c`
- end: `0x1400028bb`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400044c0`
- `0x140006c94`
- `0x140006d04`
- `0x140006d74`
- `0x140006de4`
- `0x140008624`
- `0x1400086f8`

## callees

- `0x14000289c`
- `0x140012cdc`

## pseudocode

```c
void *__fastcall operator new(unsigned __int64 a1, const struct std::nothrow_t *a2)
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
0x14000289c  sub     rsp, 38h
0x1400028a0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400028a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400028ae  nop
0x1400028af  jmp     short loc_1400028B6
0x1400028b1  mov     rax, [rsp+38h+arg_10]
0x1400028b6  add     rsp, 38h
0x1400028ba  retn
```
