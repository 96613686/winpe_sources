# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x14000190c`
- end: `0x140001928`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003a80`
- `0x140004200`
- `0x14000ebf8`

## callees

- `0x14000164c`
- `0x14000190c`

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
0x14000190c  sub     rsp, 38h
0x140001910  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140001919  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000191e  jmp     short loc_140001922
0x140001920  xor     eax, eax
0x140001922  add     rsp, 38h
0x140001926  retn
```
