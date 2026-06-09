# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x140001360`
- end: `0x14000137c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002190`
- `0x140002430`

## callees

- `0x140001360`
- `0x14000192c`

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
0x140001360  sub     rsp, 38h
0x140001364  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000136d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001372  jmp     short loc_140001376
0x140001374  xor     eax, eax
0x140001376  add     rsp, 38h
0x14000137a  retn
```
