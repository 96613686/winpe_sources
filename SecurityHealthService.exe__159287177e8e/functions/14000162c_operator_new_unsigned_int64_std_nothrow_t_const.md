# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x14000162c`
- end: `0x140001648`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140002810`
- `0x1400039a4`
- `0x140005110`
- `0x14001010c`
- `0x140011cf0`

## callees

- `0x14000162c`
- `0x140001b9c`

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
0x14000162c  sub     rsp, 38h
0x140001630  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140001639  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000163e  jmp     short loc_140001642
0x140001640  xor     eax, eax
0x140001642  add     rsp, 38h
0x140001646  retn
```
