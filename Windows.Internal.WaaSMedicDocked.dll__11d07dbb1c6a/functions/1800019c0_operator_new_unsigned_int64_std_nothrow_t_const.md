# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800019c0`
- end: `0x1800019dc`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000799c`
- `0x180008bf0`
- `0x180009558`
- `0x1800098e8`
- `0x1800099b8`

## callees

- `0x18000197c`
- `0x1800019c0`

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
0x1800019c0  sub     rsp, 38h
0x1800019c4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800019cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800019d2  jmp     short loc_1800019D6
0x1800019d4  xor     eax, eax
0x1800019d6  add     rsp, 38h
0x1800019da  retn
```
