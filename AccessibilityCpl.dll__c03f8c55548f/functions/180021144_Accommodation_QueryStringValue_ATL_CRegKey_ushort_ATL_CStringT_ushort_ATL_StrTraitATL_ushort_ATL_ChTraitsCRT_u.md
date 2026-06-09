# Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180021144`
- end: `0x1800212fd`
- name: `?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z`
- size: `441`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180020edc`

## callees

- `0x180002018`
- `0x180002024`
- `0x180014b84`
- `0x18001855c`
- `0x1800206c0`
- `0x180021144`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18002127c`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18002127c`

## pseudocode

```c
__int64 __fastcall Accommodation::QueryStringValue(ATL::CRegKey *this, unsigned __int16 *a2, char **a3)
{
  char **v3; // r14
  const unsigned __int16 *v4; // r13
  ATL::CRegKey *v5; // r12
  int v6; // eax
  __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  unsigned int v10; // r15d
  __int64 v11; // r8
  unsigned int v13; // [rsp+40h] [rbp-888h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp-880h]
  ATL::CRegKey *v15; // [rsp+50h] [rbp-878h]
  unsigned __int16 *v16; // [rsp+58h] [rbp-870h]
  char **v17; // [rsp+60h] [rbp-868h]
  WCHAR pszOutBuf[1024]; // [rsp+70h] [rbp-858h] BYREF
  ATL::CAtlException *v19; // [rsp+870h] [rbp-58h] BYREF
  ATL::CAtlException *v20; // [rsp+878h] [rbp-50h] BYREF
  ATL::CAtlException *v21; // [rsp+880h] [rbp-48h] BYREF

  try
  {
    v3 = a3;
    v4 = a2;
    v5 = this;
    v15 = this;
    v16 = a2;
    v17 = a3;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(a3);
    v13 = 0;
    v6 = ATL::CRegKey::QueryStringValue(v5, v4, 0, &v13);
  }
  catch ( ATL::CAtlException *v19 )
  {
    return 0;
  }
  if ( v6 || !v13 )
    return 1;
  v7 = -1;
  v8 = (unsigned __int16 *)operator new[](saturated_mul(v13, 2u));
  v9 = v8;
  v14 = v8;
  if ( !v8 )
    return 0;
  v10 = 1;
  *v8 = 0;
  if ( !(unsigned int)ATL::CRegKey::QueryStringValue(v5, v4, v8, &v13) && v13 )
  {
    if ( v13 > 0x400 )
      v9[1023] = 0;
    v11 = -1;
    do
      ++v11;
    while ( v9[v11] );
    try
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(v3, v9, v11);
    }
    catch ( ATL::CAtlException *v20 )
    {
      v7 = -1;
      v10 = 0;
      v9 = v14;
      v5 = v15;
      v4 = v16;
      v3 = v17;
    }
  }
  if ( *v9 == 64 && v10 )
  {
    if ( RegLoadMUIStringW(*(HKEY *)v5, v4, pszOutBuf, 0x400u, 0, 1u, 0) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v3);
    }
    else
    {
      pszOutBuf[1023] = 0;
      do
        ++v7;
      while ( pszOutBuf[v7] );
      try
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v3, pszOutBuf, v7);
      }
      catch ( ATL::CAtlException *v21 )
      {
        v13 = 0;
        v10 = 0;
        v9 = v14;
      }
    }
  }
  operator delete[](v9);
  return v10;
}

```

## disassembly

```asm
0x180021144  push    rbx
0x180021146  push    rsi
0x180021147  push    rdi
0x180021148  push    r12
0x18002114a  push    r13
0x18002114c  push    r14
0x18002114e  push    r15
0x180021150  sub     rsp, 890h
0x180021157  mov     rax, cs:__security_cookie
0x18002115e  xor     rax, rsp
0x180021161  mov     [rsp+8C8h+var_40], rax
0x180021169  mov     r14, r8
0x18002116c  mov     r13, rdx
0x18002116f  mov     r12, rcx
0x180021172  mov     [rsp+8C8h+var_878], rcx
0x180021177  mov     [rsp+8C8h+var_870], rdx
0x18002117c  mov     [rsp+8C8h+var_868], r8
0x180021181  mov     rcx, r8
0x180021184  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x180021189  nop
0x18002118a  xor     ebx, ebx
0x18002118c  mov     [rsp+8C8h+var_888], ebx
0x180021190  lea     r9, [rsp+8C8h+var_888]; unsigned int *
0x180021195  xor     r8d, r8d; unsigned __int16 *
0x180021198  mov     rdx, r13; unsigned __int16 *
0x18002119b  mov     rcx, r12; this
0x18002119e  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1800211a3  test    eax, eax
0x1800211a5  jnz     loc_1800212D1
0x1800211ab  cmp     [rsp+8C8h+var_888], ebx
0x1800211af  jz      loc_1800212D1
0x1800211b5  mov     ecx, [rsp+8C8h+var_888]
0x1800211b9  lea     eax, [rbx+2]
0x1800211bc  mul     rcx
0x1800211bf  lea     rsi, [rbx-1]
0x1800211c3  cmovb   rax, rsi
0x1800211c7  mov     rcx, rax; unsigned __int64
0x1800211ca  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800211cf  mov     rdi, rax
0x1800211d2  mov     [rsp+8C8h+var_880], rax
0x1800211d7  test    rax, rax
0x1800211da  jz      loc_1800212D8
0x1800211e0  lea     r15d, [rbx+1]
0x1800211e4  mov     [rax], bx
0x1800211e7  lea     r9, [rsp+8C8h+var_888]; unsigned int *
0x1800211ec  mov     r8, rax; unsigned __int16 *
0x1800211ef  mov     rdx, r13; unsigned __int16 *
0x1800211f2  mov     rcx, r12; this
0x1800211f5  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1800211fa  test    eax, eax
0x1800211fc  jnz     short loc_18002124D
0x1800211fe  cmp     [rsp+8C8h+var_888], ebx
0x180021202  jbe     short loc_18002124D
0x180021204  cmp     [rsp+8C8h+var_888], 400h
0x18002120c  jbe     short loc_180021215
0x18002120e  mov     [rdi+7FEh], bx
0x180021215  mov     r8, rsi
0x180021218  inc     r8
0x18002121b  cmp     [rdi+r8*2], bx
0x180021220  jnz     short loc_180021218
0x180021222  mov     rdx, rdi
0x180021225  mov     rcx, r14
0x180021228  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002122d  nop
0x18002122e  jmp     short loc_18002124D
0x180021230  xor     ebx, ebx
0x180021232  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180021236  mov     r15d, ebx
0x180021239  mov     rdi, [rsp+8C8h+var_880]
0x18002123e  mov     r12, [rsp+8C8h+var_878]
0x180021243  mov     r13, [rsp+8C8h+var_870]
0x180021248  mov     r14, [rsp+8C8h+var_868]
0x18002124d  cmp     word ptr [rdi], 40h ; '@'
0x180021251  jnz     short loc_1800212C4
0x180021253  test    r15d, r15d
0x180021256  jz      short loc_1800212C4
0x180021258  mov     [rsp+8C8h+pszDirectory], rbx; pszDirectory
0x18002125d  mov     [rsp+8C8h+Flags], 1; Flags
0x180021265  mov     [rsp+8C8h+pcbData], rbx; pcbData
0x18002126a  mov     r9d, 400h; cbOutBuf
0x180021270  lea     r8, [rsp+8C8h+pszOutBuf]; pszOutBuf
0x180021275  mov     rdx, r13; pszValue
0x180021278  mov     rcx, [r12]; hKey
0x18002127c  call    cs:__imp_RegLoadMUIStringW
0x180021282  nop
0x180021283  test    eax, eax
0x180021285  jnz     short loc_1800212AF
0x180021287  mov     [rsp+8C8h+var_5A], bx
0x18002128f  lea     rax, [rsp+8C8h+pszOutBuf]
0x180021294  inc     rsi
0x180021297  cmp     [rax+rsi*2], bx
0x18002129b  jnz     short loc_180021294
0x18002129d  mov     r8d, esi
0x1800212a0  lea     rdx, [rsp+8C8h+pszOutBuf]
0x1800212a5  mov     rcx, r14
0x1800212a8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800212ad  jmp     short loc_1800212B8
0x1800212af  mov     rcx, r14
0x1800212b2  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x1800212b7  nop
0x1800212b8  jmp     short loc_1800212C4
0x1800212ba  mov     r15d, [rsp+8C8h+var_888]
0x1800212bf  mov     rdi, [rsp+8C8h+var_880]
0x1800212c4  mov     rcx, rdi; void *
0x1800212c7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800212cc  mov     eax, r15d
0x1800212cf  jmp     short loc_1800212DA
0x1800212d1  mov     eax, 1
0x1800212d6  jmp     short loc_1800212DA
0x1800212d8  xor     eax, eax
0x1800212da  mov     rcx, [rsp+8C8h+var_40]
0x1800212e2  xor     rcx, rsp; StackCookie
0x1800212e5  call    __security_check_cookie
0x1800212ea  add     rsp, 890h
0x1800212f1  pop     r15
0x1800212f3  pop     r14
0x1800212f5  pop     r13
0x1800212f7  pop     r12
0x1800212f9  pop     rdi
0x1800212fa  pop     rsi
0x1800212fb  pop     rbx
0x1800212fc  retn
```
