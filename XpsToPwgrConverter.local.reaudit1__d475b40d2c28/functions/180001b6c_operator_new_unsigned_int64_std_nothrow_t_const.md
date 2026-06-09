# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001b6c`
- end: `0x180001b88`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180008b34`
- `0x180008d60`
- `0x18000ecb0`
- `0x18000f12c`
- `0x18000f220`

## callees

- `0x180001b6c`
- `0x18000200c`

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
0x180001b6c  sub     rsp, 38h
0x180001b70  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001b79  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001b7e  jmp     short loc_180001B82
0x180001b80  xor     eax, eax
0x180001b82  add     rsp, 38h
0x180001b86  retn
```
