# ComTrace::IsEnabled(uchar,unsigned __int64)

- ea: `0x14000df04`
- end: `0x14000df39`
- name: `?IsEnabled@ComTrace@@SA_NE_K@Z`
- size: `53`
- prototype: `bool __fastcall(unsigned __int8, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000e7cc`
- `0x14000eb14`

## callees

- `0x14000108c`
- `0x14000df04`
- `0x14000e98c`

## pseudocode

```c
bool __fastcall ComTrace::IsEnabled(__int64 a1)
{
  _DWORD *v1; // rcx

  v1 = (_DWORD *)wil::details::static_lazy<ComTrace>::get(
                   a1,
                   (void (__cdecl *)())_lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_)[1];
  return v1 && *v1 && (unsigned __int8)tlgKeywordOn(v1, 0);
}

```

## disassembly

```asm
0x14000df04  sub     rsp, 28h
0x14000df08  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f8a79a44bba2ee3470b25df359f31864_@@CA@XZ; _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_(void)
0x14000df0f  call    ?get@?$static_lazy@VComTrace@@@details@wil@@QEAAPEAVComTrace@@P6AXXZ@Z; wil::details::static_lazy<ComTrace>::get(void (*)(void))
0x14000df14  mov     rcx, [rax+8]
0x14000df18  test    rcx, rcx
0x14000df1b  jz      short loc_14000DF32
0x14000df1d  mov     eax, [rcx]
0x14000df1f  test    eax, eax
0x14000df21  jz      short loc_14000DF32
0x14000df23  xor     edx, edx
0x14000df25  call    _tlgKeywordOn
0x14000df2a  test    al, al
0x14000df2c  jz      short loc_14000DF32
0x14000df2e  mov     al, 1
0x14000df30  jmp     short loc_14000DF34
0x14000df32  xor     al, al
0x14000df34  add     rsp, 28h
0x14000df38  retn
```
