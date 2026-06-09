# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18002d414`
- end: `0x18002d9b1`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1437`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002d03c`
- `0x18002d414`

## callees

- `0x1800277b0`
- `0x18002a870`
- `0x18002b160`
- `0x18002b1d0`
- `0x18002ba4c`
- `0x18002bbe4`
- `0x18002bc10`
- `0x18002bec4`
- `0x18002c478`
- `0x18002ca80`
- `0x18002cbe0`
- `0x18002cf28`
- `0x18002d414`
- `0x18002db64`
- `0x18002dc34`
- `0x18005b620`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002d7e2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002d7e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002d67a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002d67a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002d498`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002d4ab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002d57f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002d5ae`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002d498`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002d4ab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002d57f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002d5ae`

## string_xrefs

- `0x18002d4a1`: `ForceRemove`
- `0x18002d575`: `NoRemove`
- `0x18002d48e`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int HasSubKeys; // r14d
  __int64 v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v29; // [rsp+30h] [rbp-D0h]
  unsigned int *v30; // [rsp+38h] [rbp-C8h]
  HKEY hKey[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h]
  HKEY v34[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h]
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  v34[0] = 0;
  v34[1] = 0;
  v35 = 0;
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_77;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_77;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_77;
        if ( !v5 )
          break;
        hKey[0] = 0;
        hKey[1] = 0;
        v33 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_76:
          v10 = -2147352567;
          goto LABEL_77;
        }
        if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          hKey[0] = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, v7);
          hKey[0] = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_79;
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_77;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_77;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_76;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v34, a3, v7, v16, v27, v28, v29, v30)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_77;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v34, 0, v7);
            if ( v10 < 0 )
              goto LABEL_77;
          }
          goto LABEL_40;
        }
LABEL_80:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_77;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v36, 260, v7, -1, v27);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_77;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_77;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_77;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_77;
        }
      }
      v5 = a4;
      if ( v19 != 2 )
      {
        if ( v19 )
        {
          if ( !a5 )
          {
            v24 = v19;
            goto LABEL_64;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v34[0]) )
        {
          if ( ATL::CRegParser::CanForceRemoveKey(v22, v36) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, v36);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v34[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v34);
          if ( v17 )
            goto LABEL_80;
          if ( v14 && !HasSubKeys )
          {
            hKey[1] = 0;
            v33 = 0;
            hKey[0] = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)hKey, v36);
            hKey[0] = 0;
            if ( v15 )
              goto LABEL_78;
            ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_77;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_77;
    if ( *v7 != 61 )
      goto LABEL_76;
    if ( v5 )
    {
      hKey[1] = 0;
      v33 = 0;
      hKey[0] = a3;
      v13 = ATL::CRegParser::AddValue(v8, hKey, ValueName, v7);
      v10 = v13;
      hKey[0] = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey[0] = 0;
    hKey[1] = 0;
    v33 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey[0], ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_78:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_77:
  ATL::CRegKey::Close((ATL::CRegKey *)v34);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002d414  push    rbp
0x18002d416  push    rbx
0x18002d417  push    rsi
0x18002d418  push    rdi
0x18002d419  push    r12
0x18002d41b  push    r13
0x18002d41d  push    r14
0x18002d41f  push    r15
0x18002d421  lea     rbp, [rsp-21A8h]
0x18002d429  mov     eax, 22A8h
0x18002d42e  call    _alloca_probe
0x18002d433  sub     rsp, rax
0x18002d436  mov     rax, cs:__security_cookie
0x18002d43d  xor     rax, rsp
0x18002d440  mov     [rbp+21E0h+var_50], rax
0x18002d447  mov     r15d, r9d
0x18002d44a  mov     [rsp+22E0h+var_22A0], r9d
0x18002d44f  mov     r13, r8
0x18002d452  mov     rdi, rdx
0x18002d455  mov     rsi, rcx
0x18002d458  xorps   xmm0, xmm0
0x18002d45b  movups  xmmword ptr [rsp+22E0h+var_2280], xmm0
0x18002d460  xor     r14d, r14d
0x18002d463  mov     [rsp+22E0h+var_2280], r14
0x18002d468  mov     [rsp+22E0h+var_2280+8], r14
0x18002d46d  mov     [rsp+22E0h+var_2270], r14
0x18002d472  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002d477  test    eax, eax
0x18002d479  mov     ebx, eax
0x18002d47b  js      loc_18002D965
0x18002d481  xor     r12d, r12d
0x18002d484  cmp     word ptr [rdi], 7Dh ; '}'
0x18002d488  jz      loc_18002D965
0x18002d48e  lea     rdx, aDelete; "Delete"
0x18002d495  mov     rcx, rdi; lpString1
0x18002d498  call    cs:__imp_lstrcmpiW
0x18002d49e  mov     r14d, eax
0x18002d4a1  lea     rdx, aForceremove; "ForceRemove"
0x18002d4a8  mov     rcx, rdi; lpString1
0x18002d4ab  call    cs:__imp_lstrcmpiW
0x18002d4b1  test    eax, eax
0x18002d4b3  jz      short loc_18002D4BE
0x18002d4b5  test    r14d, r14d
0x18002d4b8  jnz     loc_18002D56F
0x18002d4be  mov     rdx, rdi; unsigned __int16 *
0x18002d4c1  mov     rcx, rsi; this
0x18002d4c4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002d4c9  mov     ebx, eax
0x18002d4cb  test    eax, eax
0x18002d4cd  js      loc_18002D965
0x18002d4d3  test    r15d, r15d
0x18002d4d6  jz      loc_18002D56F
0x18002d4dc  mov     [rsp+22E0h+hKey], r12
0x18002d4e1  mov     [rsp+22E0h+hKey+8], r12
0x18002d4e6  mov     [rsp+22E0h+var_2288], r12
0x18002d4eb  mov     edx, 5Ch ; '\'; unsigned __int16
0x18002d4f0  mov     rcx, rdi; lpsz
0x18002d4f3  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002d4f8  test    rax, rax
0x18002d4fb  jnz     loc_18002D956
0x18002d501  mov     rdx, rdi; unsigned __int16 *
0x18002d504  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18002d509  test    eax, eax
0x18002d50b  jz      short loc_18002D524
0x18002d50d  mov     [rsp+22E0h+hKey], r13
0x18002d512  mov     rdx, rdi; unsigned __int16 *
0x18002d515  lea     rcx, [rsp+22E0h+hKey]; this
0x18002d51a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18002d51f  mov     [rsp+22E0h+hKey], r12
0x18002d524  test    r14d, r14d
0x18002d527  jnz     short loc_18002D565
0x18002d529  mov     rdx, rdi; unsigned __int16 *
0x18002d52c  mov     rcx, rsi; this
0x18002d52f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002d534  mov     ebx, eax
0x18002d536  xor     r14d, r14d
0x18002d539  test    eax, eax
0x18002d53b  js      loc_18002D99D
0x18002d541  mov     rdx, rdi; unsigned __int16 *
0x18002d544  mov     rcx, rsi; this
0x18002d547  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002d54c  mov     ebx, eax
0x18002d54e  test    eax, eax
0x18002d550  lea     rcx, [rsp+22E0h+hKey]; this
0x18002d555  js      loc_18002D9A2
0x18002d55b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d560  jmp     loc_18002D748
0x18002d565  lea     rcx, [rsp+22E0h+hKey]; this
0x18002d56a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d56f  mov     r12d, 1
0x18002d575  lea     rdx, aNoremove; "NoRemove"
0x18002d57c  mov     rcx, rdi; lpString1
0x18002d57f  call    cs:__imp_lstrcmpiW
0x18002d585  xor     r14d, r14d
0x18002d588  test    eax, eax
0x18002d58a  jnz     short loc_18002D5A4
0x18002d58c  mov     r12d, r14d
0x18002d58f  mov     rdx, rdi; unsigned __int16 *
0x18002d592  mov     rcx, rsi; this
0x18002d595  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002d59a  mov     ebx, eax
0x18002d59c  test    eax, eax
0x18002d59e  js      loc_18002D965
0x18002d5a4  lea     rdx, aVal; "Val"
0x18002d5ab  mov     rcx, rdi; lpString1
0x18002d5ae  call    cs:__imp_lstrcmpiW
0x18002d5b4  test    eax, eax
0x18002d5b6  jnz     loc_18002D6A5
0x18002d5bc  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18002d5c3  mov     rcx, rsi; this
0x18002d5c6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002d5cb  mov     ebx, eax
0x18002d5cd  test    eax, eax
0x18002d5cf  js      loc_18002D965
0x18002d5d5  mov     rdx, rdi; unsigned __int16 *
0x18002d5d8  mov     rcx, rsi; this
0x18002d5db  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002d5e0  mov     ebx, eax
0x18002d5e2  test    eax, eax
0x18002d5e4  js      loc_18002D965
0x18002d5ea  cmp     word ptr [rdi], 3Dh ; '='
0x18002d5ee  jnz     loc_18002D960
0x18002d5f4  test    r15d, r15d
0x18002d5f7  jz      short loc_18002D633
0x18002d5f9  xorps   xmm0, xmm0
0x18002d5fc  movups  xmmword ptr [rsp+22E0h+hKey], xmm0
0x18002d601  mov     [rsp+22E0h+hKey+8], r14
0x18002d606  mov     [rsp+22E0h+var_2288], r14
0x18002d60b  mov     [rsp+22E0h+hKey], r13
0x18002d610  mov     r9, rdi; unsigned __int16 *
0x18002d613  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18002d61a  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18002d61f  mov     rcx, rsi; this
0x18002d622  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18002d627  mov     ebx, eax
0x18002d629  mov     [rsp+22E0h+hKey], r14
0x18002d62e  jmp     loc_18002D54E
0x18002d633  cmp     [rbp+21E0h+arg_20], r14d
0x18002d63a  jnz     short loc_18002D695
0x18002d63c  test    r12d, r12d
0x18002d63f  jz      short loc_18002D695
0x18002d641  mov     [rsp+22E0h+hKey], r14
0x18002d646  mov     [rsp+22E0h+hKey+8], r14
0x18002d64b  mov     [rsp+22E0h+var_2288], r14
0x18002d650  mov     r9d, 20006h; unsigned int
0x18002d656  xor     r8d, r8d; lpSubKey
0x18002d659  mov     rdx, r13; hKey
0x18002d65c  lea     rcx, [rsp+22E0h+hKey]; this
0x18002d661  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002d666  test    eax, eax
0x18002d668  jnz     loc_18002D994
0x18002d66e  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18002d675  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18002d67a  call    cs:__imp_RegDeleteValueW
0x18002d680  test    eax, 0FFFFFFFDh
0x18002d685  jnz     loc_18002D994
0x18002d68b  lea     rcx, [rsp+22E0h+hKey]; this
0x18002d690  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d695  mov     rdx, rdi; unsigned __int16 *
0x18002d698  mov     rcx, rsi; this
0x18002d69b  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002d6a0  jmp     loc_18002D477
0x18002d6a5  mov     edx, 5Ch ; '\'; unsigned __int16
0x18002d6aa  mov     rcx, rdi; lpsz
0x18002d6ad  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002d6b2  test    rax, rax
0x18002d6b5  jnz     loc_18002D960
0x18002d6bb  test    r15d, r15d
0x18002d6be  jz      loc_18002D797
0x18002d6c4  mov     r9d, 2001Fh; unsigned int
0x18002d6ca  mov     r8, rdi; lpSubKey
0x18002d6cd  mov     rdx, r13; hKey
0x18002d6d0  lea     rcx, [rsp+22E0h+var_2280]; this
0x18002d6d5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002d6da  test    eax, eax
0x18002d6dc  jz      short loc_18002D710
0x18002d6de  mov     r9d, 20019h; unsigned int
0x18002d6e4  mov     r8, rdi; lpSubKey
0x18002d6e7  mov     rdx, r13; hKey
0x18002d6ea  lea     rcx, [rsp+22E0h+var_2280]; this
0x18002d6ef  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002d6f4  test    eax, eax
0x18002d6f6  jz      short loc_18002D710
0x18002d6f8  mov     r8, rdi; lpSubKey
0x18002d6fb  mov     rdx, r13; hKey
0x18002d6fe  lea     rcx, [rsp+22E0h+var_2280]; this
0x18002d703  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18002d708  test    eax, eax
0x18002d70a  jnz     loc_18002D9A9
0x18002d710  mov     rdx, rdi; unsigned __int16 *
0x18002d713  mov     rcx, rsi; this
0x18002d716  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002d71b  mov     ebx, eax
0x18002d71d  test    eax, eax
0x18002d71f  js      loc_18002D965
0x18002d725  cmp     word ptr [rdi], 3Dh ; '='
0x18002d729  jnz     short loc_18002D748
0x18002d72b  mov     r9, rdi; unsigned __int16 *
0x18002d72e  xor     r8d, r8d; unsigned __int16 *
0x18002d731  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18002d736  mov     rcx, rsi; this
0x18002d739  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18002d73e  mov     ebx, eax
0x18002d740  test    eax, eax
0x18002d742  js      loc_18002D965
0x18002d748  cmp     word ptr [rdi], 7Bh ; '{'
0x18002d74c  jnz     loc_18002D481
0x18002d752  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d756  inc     rax
0x18002d759  cmp     [rdi+rax*2], r14w
0x18002d75e  jnz     short loc_18002D756
0x18002d760  cmp     rax, 1
0x18002d764  jnz     loc_18002D481
0x18002d76a  mov     dword ptr [rsp+22E0h+var_22C0], r14d; int
0x18002d76f  mov     r9d, r15d; int
0x18002d772  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18002d777  mov     rdx, rdi; unsigned __int16 *
0x18002d77a  mov     rcx, rsi; this
0x18002d77d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002d782  mov     ebx, eax
0x18002d784  test    eax, eax
0x18002d786  js      loc_18002D965
0x18002d78c  mov     rdx, rdi
0x18002d78f  mov     rcx, rsi
0x18002d792  jmp     loc_18002D472
0x18002d797  cmp     [rbp+21E0h+arg_20], r14d
0x18002d79e  jnz     short loc_18002D7BB
0x18002d7a0  mov     r9d, 20019h; unsigned int
0x18002d7a6  mov     r8, rdi; lpSubKey
0x18002d7a9  mov     rdx, r13; hKey
0x18002d7ac  lea     rcx, [rsp+22E0h+var_2280]; this
0x18002d7b1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002d7b6  mov     r14d, eax
0x18002d7b9  jmp     short loc_18002D7C1
0x18002d7bb  mov     r14d, 2
0x18002d7c1  mov     r15d, 1
0x18002d7c7  test    r14d, r14d
0x18002d7ca  cmovz   r15d, [rbp+21E0h+arg_20]
0x18002d7d2  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002d7d6  mov     r8, rdi
0x18002d7d9  mov     edx, 104h
0x18002d7de  lea     rcx, [rbp+21E0h+var_2260]
0x18002d7e2  call    cs:__imp__o_wcsncpy_s
0x18002d7e8  mov     ecx, eax; int
0x18002d7ea  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002d7ef  mov     rdx, rdi; unsigned __int16 *
0x18002d7f2  mov     rcx, rsi; this
0x18002d7f5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002d7fa  mov     ebx, eax
0x18002d7fc  test    eax, eax
0x18002d7fe  js      loc_18002D965
0x18002d804  mov     rdx, rdi; unsigned __int16 *
0x18002d807  mov     rcx, rsi; this
0x18002d80a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002d80f  mov     ebx, eax
0x18002d811  xor     ecx, ecx
0x18002d813  test    eax, eax
0x18002d815  js      loc_18002D965
0x18002d81b  cmp     word ptr [rdi], 7Bh ; '{'
0x18002d81f  jnz     short loc_18002D870
0x18002d821  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d825  inc     rax
0x18002d828  cmp     [rdi+rax*2], cx
0x18002d82c  jnz     short loc_18002D825
0x18002d82e  cmp     rax, 1
0x18002d832  jnz     short loc_18002D870
0x18002d834  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x18002d839  xor     r9d, r9d; int
0x18002d83c  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18002d841  mov     rdx, rdi; unsigned __int16 *
0x18002d844  mov     rcx, rsi; this
0x18002d847  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002d84c  mov     ebx, eax
0x18002d84e  test    eax, eax
0x18002d850  jns     short loc_18002D85B
0x18002d852  test    r15d, r15d
0x18002d855  jz      loc_18002D965
0x18002d85b  mov     rdx, rdi; unsigned __int16 *
0x18002d85e  mov     rcx, rsi; this
0x18002d861  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002d866  mov     ebx, eax
0x18002d868  test    eax, eax
0x18002d86a  js      loc_18002D965
0x18002d870  cmp     r14d, 2
0x18002d874  mov     r15d, [rsp+22E0h+var_22A0]
0x18002d879  jz      loc_18002D481
0x18002d87f  test    r14d, r14d
0x18002d882  jz      short loc_18002D8A3
0x18002d884  xor     r12d, r12d
0x18002d887  cmp     [rbp+21E0h+arg_20], r12d
0x18002d88e  jnz     loc_18002D484
0x18002d894  mov     ecx, r14d; unsigned int
0x18002d897  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002d89c  mov     ebx, eax
0x18002d89e  jmp     loc_18002D965
0x18002d8a3  xor     r14d, r14d
0x18002d8a6  cmp     [rbp+21E0h+arg_20], r14d
0x18002d8ad  jz      short loc_18002D8ED
0x18002d8af  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x18002d8b4  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
  ... truncated ...
```
