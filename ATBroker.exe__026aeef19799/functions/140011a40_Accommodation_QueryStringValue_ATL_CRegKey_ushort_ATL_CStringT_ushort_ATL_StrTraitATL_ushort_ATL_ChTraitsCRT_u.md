# Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x140011a40`
- end: `0x140011c30`
- name: `?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z`
- size: `496`
- prototype: `__int64 __fastcall(HKEY *this, unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400116c4`

## callees

- `0x1400029a8`
- `0x140003ea0`
- `0x140007708`
- `0x14000cb50`
- `0x140011a40`
- `0x140015b00`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140011ab5`
- `ADVAPI32!RegQueryValueExW` at `0x140011ab5`
- `KERNEL32!RegLoadMUIStringW` at `0x140011ba7`
- `KERNEL32!RegLoadMUIStringW` at `0x140011ba7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140011bf9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140011bf9`

## pseudocode

```c
__int64 __fastcall Accommodation::QueryStringValue(HKEY *this, unsigned __int16 *a2, __int64 a3)
{
  __int64 v3; // r14
  const WCHAR *v4; // r13
  HKEY *v5; // r12
  __int64 v6; // rsi
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rdi
  unsigned int v9; // r15d
  __int64 v10; // r8
  DWORD Type; // [rsp+40h] [rbp-888h] BYREF
  DWORD cbData[2]; // [rsp+48h] [rbp-880h] BYREF
  __int64 v14; // [rsp+50h] [rbp-878h]
  ATL::CRegKey *v15; // [rsp+58h] [rbp-870h]
  unsigned __int16 *v16; // [rsp+60h] [rbp-868h]
  WCHAR pszOutBuf[1024]; // [rsp+70h] [rbp-858h] BYREF
  ATL::CAtlException *v18; // [rsp+870h] [rbp-58h] BYREF
  ATL::CAtlException *v19; // [rsp+878h] [rbp-50h] BYREF
  ATL::CAtlException *v20; // [rsp+880h] [rbp-48h] BYREF

  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v3 = a3;
    v4 = a2;
    v5 = this;
    v15 = (ATL::CRegKey *)this;
    v16 = a2;
    v14 = a3;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(a3);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v18) )
    {
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_140011C0B);
      return 0;
    }
  }
  Type = 0;
  cbData[0] = 0;
  if ( RegQueryValueExW(*v5, v4, 0, &Type, 0, cbData) )
    return 1;
  if ( Type - 1 > 1 )
    return 1;
  Type = cbData[0] >> 1;
  if ( !(cbData[0] >> 1) )
    return 1;
  v6 = -1;
  v7 = (unsigned __int16 *)operator new[](saturated_mul(cbData[0] >> 1, 2u));
  v8 = v7;
  *(_QWORD *)cbData = v7;
  if ( !v7 )
    return 0;
  v9 = 1;
  *v7 = 0;
  if ( !(unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v5, v4, v7, &Type) && Type )
  {
    if ( Type > 0x400 )
      v8[1023] = 0;
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      v10 = -1;
      do
        ++v10;
      while ( v8[v10] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(v3, v8, v10);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', &v19) )
      {
        v6 = -1;
        v9 = 0;
        v8 = *(unsigned __int16 **)cbData;
        v3 = v14;
        v5 = (HKEY *)v15;
        v4 = v16;
        __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_140011B5B);
      }
    }
  }
  if ( *v8 == 64 && v9 )
  {
    if ( RegLoadMUIStringW(*v5, v4, pszOutBuf, 0x400u, 0, 1u, 0) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v3);
    }
    else
    {
      pszOutBuf[1023] = 0;
      do
        ++v6;
      while ( pszOutBuf[v6] );
      if ( __eh34_try(-1, 4) )
      {
        __eh34_scope_strut(4);
        ATL::CSimpleStringT<unsigned short,0>::SetString(v3, pszOutBuf, (unsigned int)v6);
      }
      if ( __eh34_catch(4) )
      {
        if ( __eh34_catch_type(4, &ATL::CAtlException `RTTI Type Descriptor', &v20) )
        {
          Type = 0;
          v9 = 0;
          v8 = *(unsigned __int16 **)cbData;
          __eh34_try_continuation(4, &ATL::CAtlException `RTTI Type Descriptor', &loc_140011BEC);
        }
      }
    }
  }
  operator delete[](v8);
  return v9;
}

```

## disassembly

```asm
0x140011a40  push    rbx
0x140011a42  push    rsi
0x140011a43  push    rdi
0x140011a44  push    r12
0x140011a46  push    r13
0x140011a48  push    r14
0x140011a4a  push    r15
0x140011a4c  sub     rsp, 890h
0x140011a53  mov     rax, cs:__security_cookie
0x140011a5a  xor     rax, rsp
0x140011a5d  mov     [rsp+8C8h+var_40], rax
0x140011a65  mov     r14, r8
0x140011a68  mov     r13, rdx
0x140011a6b  mov     r12, rcx
0x140011a6e  mov     [rsp+8C8h+var_870], rcx
0x140011a73  mov     [rsp+8C8h+var_868], rdx
0x140011a78  mov     [rsp+8C8h+var_878], r8
0x140011a7d  lea     rdx, word_140018C4A
0x140011a84  mov     rcx, r8
0x140011a87  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x140011a8c  nop
0x140011a8d  xor     ebx, ebx
0x140011a8f  mov     [rsp+8C8h+Type], ebx
0x140011a93  mov     [rsp+8C8h+cbData], ebx
0x140011a97  lea     rax, [rsp+8C8h+cbData]
0x140011a9c  mov     [rsp+8C8h+lpcbData], rax; lpcbData
0x140011aa1  mov     [rsp+8C8h+lpData], rbx; lpData
0x140011aa6  lea     r9, [rsp+8C8h+Type]; lpType
0x140011aab  xor     r8d, r8d; lpReserved
0x140011aae  mov     rdx, r13; lpValueName
0x140011ab1  mov     rcx, [r12]; hKey
0x140011ab5  call    cs:__imp_RegQueryValueExW
0x140011abb  test    eax, eax
0x140011abd  jnz     loc_140011C04
0x140011ac3  mov     eax, [rsp+8C8h+Type]
0x140011ac7  dec     eax
0x140011ac9  cmp     eax, 1
0x140011acc  ja      loc_140011C04
0x140011ad2  mov     eax, [rsp+8C8h+cbData]
0x140011ad6  shr     eax, 1
0x140011ad8  mov     [rsp+8C8h+Type], eax
0x140011adc  jz      loc_140011C04
0x140011ae2  mov     ecx, eax
0x140011ae4  lea     eax, [rbx+2]
0x140011ae7  mul     rcx
0x140011aea  lea     rsi, [rbx-1]
0x140011aee  cmovb   rax, rsi
0x140011af2  mov     rcx, rax; unsigned __int64
0x140011af5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140011afa  mov     rdi, rax
0x140011afd  mov     qword ptr [rsp+8C8h+cbData], rax
0x140011b02  test    rax, rax
0x140011b05  jz      loc_140011C0B
0x140011b0b  lea     r15d, [rbx+1]
0x140011b0f  mov     [rax], bx
0x140011b12  lea     r9, [rsp+8C8h+Type]; unsigned int *
0x140011b17  mov     r8, rax; unsigned __int16 *
0x140011b1a  mov     rdx, r13; unsigned __int16 *
0x140011b1d  mov     rcx, r12; this
0x140011b20  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140011b25  test    eax, eax
0x140011b27  jnz     short loc_140011B78
0x140011b29  cmp     [rsp+8C8h+Type], ebx
0x140011b2d  jbe     short loc_140011B78
0x140011b2f  cmp     [rsp+8C8h+Type], 400h
0x140011b37  jbe     short loc_140011B40
0x140011b39  mov     [rdi+7FEh], bx
0x140011b40  mov     r8, rsi
0x140011b43  inc     r8
0x140011b46  cmp     [rdi+r8*2], bx
0x140011b4b  jnz     short loc_140011B43
0x140011b4d  mov     rdx, rdi
0x140011b50  mov     rcx, r14
0x140011b53  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140011b58  nop
0x140011b59  jmp     short loc_140011B78
0x140011b5b  xor     ebx, ebx
0x140011b5d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140011b61  mov     r15d, ebx
0x140011b64  mov     rdi, qword ptr [rsp+8C8h+cbData]
0x140011b69  mov     r14, [rsp+8C8h+var_878]
0x140011b6e  mov     r12, [rsp+8C8h+var_870]
0x140011b73  mov     r13, [rsp+8C8h+var_868]
0x140011b78  cmp     word ptr [rdi], 40h ; '@'
0x140011b7c  jnz     short loc_140011BF6
0x140011b7e  test    r15d, r15d
0x140011b81  jz      short loc_140011BF6
0x140011b83  mov     [rsp+8C8h+pszDirectory], rbx; pszDirectory
0x140011b88  mov     dword ptr [rsp+8C8h+lpcbData], 1; Flags
0x140011b90  mov     [rsp+8C8h+lpData], rbx; pcbData
0x140011b95  mov     r9d, 400h; cbOutBuf
0x140011b9b  lea     r8, [rsp+8C8h+pszOutBuf]; pszOutBuf
0x140011ba0  mov     rdx, r13; pszValue
0x140011ba3  mov     rcx, [r12]; hKey
0x140011ba7  call    cs:__imp_RegLoadMUIStringW
0x140011bad  nop
0x140011bae  test    eax, eax
0x140011bb0  jnz     short loc_140011BDA
0x140011bb2  mov     [rsp+8C8h+var_5A], bx
0x140011bba  lea     rax, [rsp+8C8h+pszOutBuf]
0x140011bbf  inc     rsi
0x140011bc2  cmp     [rax+rsi*2], bx
0x140011bc6  jnz     short loc_140011BBF
0x140011bc8  mov     r8d, esi
0x140011bcb  lea     rdx, [rsp+8C8h+pszOutBuf]
0x140011bd0  mov     rcx, r14
0x140011bd3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140011bd8  jmp     short loc_140011BEA
0x140011bda  lea     rdx, word_140018C4A
0x140011be1  mov     rcx, r14
0x140011be4  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x140011be9  nop
0x140011bea  jmp     short loc_140011BF6
0x140011bec  mov     r15d, [rsp+8C8h+Type]
0x140011bf1  mov     rdi, qword ptr [rsp+8C8h+cbData]
0x140011bf6  mov     rcx, rdi
0x140011bf9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140011bff  mov     eax, r15d
0x140011c02  jmp     short loc_140011C0D
0x140011c04  mov     eax, 1
0x140011c09  jmp     short loc_140011C0D
0x140011c0b  xor     eax, eax
0x140011c0d  mov     rcx, [rsp+8C8h+var_40]
0x140011c15  xor     rcx, rsp; StackCookie
0x140011c18  call    __security_check_cookie
0x140011c1d  add     rsp, 890h
0x140011c24  pop     r15
0x140011c26  pop     r14
0x140011c28  pop     r13
0x140011c2a  pop     r12
0x140011c2c  pop     rdi
0x140011c2d  pop     rsi
0x140011c2e  pop     rbx
0x140011c2f  retn
```
