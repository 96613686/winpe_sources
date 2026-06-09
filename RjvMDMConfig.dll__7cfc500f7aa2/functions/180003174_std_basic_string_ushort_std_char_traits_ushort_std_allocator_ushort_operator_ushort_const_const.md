# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::operator+=(ushort const * const)

- ea: `0x180003174`
- end: `0x1800031f4`
- name: `??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z`
- size: `128`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003350`
- `0x180003480`

## callees

- `0x180002ec4`
- `0x180003174`
- `0x18001cf88`

## string_xrefs

- `0x1800031bc`: `\MDMConfig.dat`

## pseudocode

```c
const void **__fastcall std::wstring::operator+=(const void **Src, __int64 a2, __int64 a3, __int64 a4)
{
  const void **v4; // rbx
  const void *v5; // rcx
  bool v6; // cc
  __int64 v7; // rsi
  _WORD *v8; // rdi

  v4 = Src;
  v5 = Src[2];
  if ( (unsigned __int64)((_BYTE *)v4[3] - (_BYTE *)v5) < 0xE )
    return std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
             v4,
             0xEu,
             a3,
             a4,
             14);
  v6 = (unsigned __int64)v4[3] <= 7;
  v7 = (__int64)v5 + 14;
  v4[2] = (char *)v5 + 14;
  if ( v6 )
    v8 = v4;
  else
    v8 = *v4;
  memmove_0(&v8[(_QWORD)v5], L"\\MDMConfig.dat", 0x1Cu);
  v8[v7] = 0;
  return v4;
}

```

## disassembly

```asm
0x180003174  mov     [rsp+arg_0], rbx
0x180003179  mov     [rsp+arg_8], rsi
0x18000317e  push    rdi
0x18000317f  sub     rsp, 30h
0x180003183  mov     rbx, rcx
0x180003186  mov     edx, 0Eh
0x18000318b  mov     rcx, [rcx+10h]
0x18000318f  mov     rax, [rbx+18h]
0x180003193  sub     rax, rcx
0x180003196  cmp     rax, rdx
0x180003199  jb      short loc_1800031D0
0x18000319b  cmp     qword ptr [rbx+18h], 7
0x1800031a0  lea     rsi, [rcx+0Eh]
0x1800031a4  mov     [rbx+10h], rsi
0x1800031a8  jbe     short loc_1800031AF
0x1800031aa  mov     rdi, [rbx]
0x1800031ad  jmp     short loc_1800031B2
0x1800031af  mov     rdi, rbx
0x1800031b2  lea     rcx, [rdi+rcx*2]; void *
0x1800031b6  mov     r8d, 1Ch; Size
0x1800031bc  lea     rdx, aMdmconfigDat; "\\MDMConfig.dat"
0x1800031c3  call    memmove_0
0x1800031c8  xor     eax, eax
0x1800031ca  mov     [rdi+rsi*2], ax
0x1800031ce  jmp     short loc_1800031E0
0x1800031d0  mov     rcx, rbx; Src
0x1800031d3  mov     [rsp+38h+var_18], rdx; __int64
0x1800031d8  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x1800031dd  mov     rbx, rax
0x1800031e0  mov     rsi, [rsp+38h+arg_8]
0x1800031e5  mov     rax, rbx
0x1800031e8  mov     rbx, [rsp+38h+arg_0]
0x1800031ed  add     rsp, 30h
0x1800031f1  pop     rdi
0x1800031f2  retn
```
