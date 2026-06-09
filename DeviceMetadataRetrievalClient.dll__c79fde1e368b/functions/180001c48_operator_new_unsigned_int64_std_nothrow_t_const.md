# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001c48`
- end: `0x180001c67`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004320`
- `0x180005588`
- `0x18000f154`
- `0x1800107e4`

## callees

- `0x18000152c`
- `0x180001c48`

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
0x180001c48  sub     rsp, 38h
0x180001c4c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001c55  call    ??2@YAPEAX_K@Z
0x180001c5a  nop
0x180001c5b  jmp     short loc_180001C62
0x180001c5d  mov     rax, [rsp+38h+arg_10]
0x180001c62  add     rsp, 38h
0x180001c66  retn
```
