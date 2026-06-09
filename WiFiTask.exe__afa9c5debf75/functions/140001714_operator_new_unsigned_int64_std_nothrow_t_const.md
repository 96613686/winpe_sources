# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x140001714`
- end: `0x140001730`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400066e4`
- `0x14000728c`
- `0x14000e868`
- `0x1400101f8`

## callees

- `0x1400016d0`
- `0x140001714`

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
0x140001714  sub     rsp, 38h
0x140001718  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140001721  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001726  jmp     short loc_14000172A
0x140001728  xor     eax, eax
0x14000172a  add     rsp, 38h
0x14000172e  retn
```
