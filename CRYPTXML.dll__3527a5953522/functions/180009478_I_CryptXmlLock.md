# I_CryptXmlLock

- ea: `0x180009478`
- end: `0x180009490`
- name: `I_CryptXmlLock`
- size: `24`
- prototype: `__int64(void)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008dc0`
- `0x180008ffc`
- `0x1800094a0`
- `0x180012600`
- `0x180015ea0`
- `0x1800160e4`
- `0x180017170`
- `0x180017224`

## callees

- `0x180009478`
- `0x180019010`

## pseudocode

```c
__int64 (*__fastcall I_CryptXmlLock(__int64 a1))(void)
{
  __int64 (*result)(void); // rax

  result = *(__int64 (**)(void))(a1 + 120);
  if ( result )
    return (__int64 (*)(void))result();
  return result;
}

```

## disassembly

```asm
0x180009478  sub     rsp, 28h
0x18000947c  mov     rax, [rcx+78h]
0x180009480  test    rax, rax
0x180009483  jz      short loc_18000948A
0x180009485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000948a  add     rsp, 28h
0x18000948e  retn
```
