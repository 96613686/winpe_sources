# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x140001558`
- end: `0x140001577`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000164c`
- `0x140001dc0`
- `0x140001e98`

## callees

- `0x140001558`
- `0x140001ba8`

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
0x140001558  sub     rsp, 38h
0x14000155c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140001565  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000156a  nop
0x14000156b  jmp     short loc_140001572
0x14000156d  mov     rax, [rsp+38h+arg_10]
0x140001572  add     rsp, 38h
0x140001576  retn
```
