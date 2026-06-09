# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1400021a8`
- end: `0x1400021c7`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1400021d0`
- `0x1400065e8`
- `0x140006680`
- `0x140006788`
- `0x1400068c4`

## callees

- `0x140001a10`
- `0x1400021a8`

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
0x1400021a8  sub     rsp, 38h
0x1400021ac  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400021b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400021ba  nop
0x1400021bb  jmp     short loc_1400021C2
0x1400021bd  mov     rax, [rsp+38h+arg_10]
0x1400021c2  add     rsp, 38h
0x1400021c6  retn
```
