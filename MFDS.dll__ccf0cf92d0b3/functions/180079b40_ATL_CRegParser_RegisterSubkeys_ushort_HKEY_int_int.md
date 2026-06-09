# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180079b40`
- end: `0x18007a16d`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1581`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18007976c`
- `0x180079b40`

## callees

- `0x180029314`
- `0x180074160`
- `0x180077248`
- `0x180077914`
- `0x180077c68`
- `0x180077e10`
- `0x1800783c0`
- `0x180078f84`
- `0x1800790f4`
- `0x180079284`
- `0x18007964c`
- `0x180079b40`
- `0x18007a804`
- `0x18007a8dc`
- `0x1800c8220`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180079ef5`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180079fc9`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180079ef5`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180079fc9`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180079f83`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180079f83`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180079db3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180079db3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180079e7d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180079e7d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079bb3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079bcc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079cb6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079ceb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079bb3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079bcc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079cb6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079ceb`

## string_xrefs

- `0x180079bbf`: `ForceRemove`
- `0x180079ca6`: `NoRemove`
- `0x180079ba9`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *i; // rsi
  int Token; // eax
  int v10; // r14d
  int v11; // ebx
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ebx
  unsigned int v17; // r14d
  int v18; // r15d
  int v19; // eax
  ATL::CRegParser *v20; // rcx
  int HasSubKeys; // r15d
  unsigned int v22; // r14d
  unsigned int v24; // ecx
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v33[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset(v30, 0, sizeof(v30));
  v5 = a4;
  v7 = a2;
  for ( i = this; ; this = i )
  {
    Token = ATL::CRegParser::NextToken(this, a2);
LABEL_31:
    v11 = Token;
    if ( Token < 0 )
      break;
    do
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_75;
        v10 = lstrcmpiW(v7, L"Delete");
        if ( !lstrcmpiW(v7, L"ForceRemove") || !v10 )
        {
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_75;
          if ( v5 )
          {
            hKey = 0;
            v28 = 0;
            v29 = 0;
            if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_74:
              v11 = -2147352567;
              goto LABEL_75;
            }
            if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
            {
              hKey = a3;
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
              hKey = 0;
            }
            if ( !v10 )
            {
              v11 = ATL::CRegParser::NextToken(i, v7);
              if ( v11 < 0 )
                goto LABEL_77;
              v13 = ATL::CRegParser::SkipAssignment(i, v7);
LABEL_14:
              v11 = v13;
              if ( v13 < 0 )
                goto LABEL_77;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              goto LABEL_42;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
        v14 = 1;
        if ( !lstrcmpiW(v7, L"NoRemove") )
        {
          v14 = 0;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_75;
        }
        if ( !lstrcmpiW(v7, L"Val") )
        {
          v11 = ATL::CRegParser::NextToken(i, ValueName);
          if ( v11 < 0 )
            goto LABEL_75;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_75;
          if ( *v7 != 61 )
            goto LABEL_74;
          if ( !v5 )
          {
            if ( a5 || !v14 )
              goto LABEL_30;
            hKey = 0;
            v28 = 0;
            v29 = 0;
            v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
            if ( !v15 )
            {
              v15 = RegDeleteValueW(hKey, ValueName);
              if ( (v15 & 0xFFFFFFFD) == 0 )
              {
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_30:
                Token = ATL::CRegParser::SkipAssignment(i, v7);
                goto LABEL_31;
              }
            }
LABEL_76:
            v11 = ATL::AtlHresultFromWin32(v15);
LABEL_77:
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            goto LABEL_75;
          }
          v28 = 0;
          v29 = 0;
          hKey = a3;
          v13 = ATL::CRegParser::AddValue(i, &hKey, ValueName, v7);
          hKey = 0;
          goto LABEL_14;
        }
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          goto LABEL_74;
        if ( v5 )
          break;
        if ( a5 )
          v17 = 2;
        else
          v17 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
        v18 = 1;
        if ( !v17 )
          v18 = a5;
        v19 = _o_wcsncpy_s(v33, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v19);
        v11 = ATL::CRegParser::NextToken(i, v7);
        if ( v11 < 0 )
          goto LABEL_75;
        v11 = ATL::CRegParser::SkipAssignment(i, v7);
        if ( v11 < 0 )
          goto LABEL_75;
        if ( *v7 == 123 && wcslen(v7) == 1 )
        {
          v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v30[0], 0, v18);
          if ( v11 < 0 && !v18 )
            goto LABEL_75;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_75;
        }
        v5 = a4;
        if ( v17 != 2 )
        {
          if ( v17 )
          {
            if ( !a5 )
            {
              v11 = ATL::AtlHresultFromWin32(v17);
              goto LABEL_75;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v20, v30[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v20, v33) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, v33);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v20, v30[0]);
            v22 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            if ( v22 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v30);
              v24 = v22;
              return ATL::AtlHresultFromWin32(v24);
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v33);
              hKey = 0;
              if ( v15 )
                goto LABEL_76;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            v5 = a4;
          }
        }
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
        {
          dwDisposition = 0;
          phkResult = 0;
          v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( v16 || (v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30), v30[0] = phkResult, v16) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v30);
            v24 = v16;
            return ATL::AtlHresultFromWin32(v24);
          }
        }
      }
      v11 = ATL::CRegParser::NextToken(i, v7);
      if ( v11 < 0 )
        goto LABEL_75;
      if ( *v7 == 61 )
      {
        v11 = ATL::CRegParser::AddValue(i, v30, 0, v7);
        if ( v11 < 0 )
          goto LABEL_75;
      }
LABEL_42:
      ;
    }
    while ( *v7 != 123 || wcslen(v7) != 1 );
    v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v30[0], v5, 0);
    if ( v11 < 0 )
      break;
    a2 = v7;
  }
LABEL_75:
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180079b40  push    rbp
0x180079b42  push    rbx
0x180079b43  push    rsi
0x180079b44  push    rdi
0x180079b45  push    r12
0x180079b47  push    r13
0x180079b49  push    r14
0x180079b4b  push    r15
0x180079b4d  lea     rbp, [rsp-21C8h]
0x180079b55  mov     eax, 22C8h
0x180079b5a  call    _alloca_probe
0x180079b5f  sub     rsp, rax
0x180079b62  mov     rax, cs:__security_cookie
0x180079b69  xor     rax, rsp
0x180079b6c  mov     [rbp+2200h+var_50], rax
0x180079b73  xor     r14d, r14d
0x180079b76  mov     [rsp+2300h+var_22B0], r9d
0x180079b7b  mov     [rsp+2300h+var_2290], r14
0x180079b80  mov     r15d, r9d
0x180079b83  mov     [rsp+2300h+var_2288], r14
0x180079b88  mov     r13, r8
0x180079b8b  mov     [rbp+2200h+var_2280], r14
0x180079b8f  mov     rdi, rdx
0x180079b92  mov     rsi, rcx
0x180079b95  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079b9a  jmp     loc_180079DDF
0x180079b9f  cmp     word ptr [rdi], 7Dh ; '}'
0x180079ba3  jz      loc_18007A106
0x180079ba9  lea     rdx, aDelete; "Delete"
0x180079bb0  mov     rcx, rdi; lpString1
0x180079bb3  call    cs:__imp_lstrcmpiW
0x180079bba  nop     dword ptr [rax+rax+00h]
0x180079bbf  lea     rdx, aForceremove; "ForceRemove"
0x180079bc6  mov     rcx, rdi; lpString1
0x180079bc9  mov     r14d, eax
0x180079bcc  call    cs:__imp_lstrcmpiW
0x180079bd3  nop     dword ptr [rax+rax+00h]
0x180079bd8  test    eax, eax
0x180079bda  jz      short loc_180079BE5
0x180079bdc  test    r14d, r14d
0x180079bdf  jnz     loc_180079CA6
0x180079be5  mov     rdx, rdi; unsigned __int16 *
0x180079be8  mov     rcx, rsi; this
0x180079beb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079bf0  mov     ebx, eax
0x180079bf2  test    eax, eax
0x180079bf4  js      loc_18007A106
0x180079bfa  test    r15d, r15d
0x180079bfd  jz      loc_180079CA6
0x180079c03  mov     edx, 5Ch ; '\'; unsigned __int16
0x180079c08  mov     [rsp+2300h+hKey], 0
0x180079c11  mov     rcx, rdi; lpsz
0x180079c14  mov     [rsp+2300h+var_22A0], 0
0x180079c1d  mov     [rsp+2300h+var_2298], 0
0x180079c26  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180079c2b  test    rax, rax
0x180079c2e  jnz     loc_18007A0F7
0x180079c34  mov     rdx, rdi; unsigned __int16 *
0x180079c37  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180079c3c  test    eax, eax
0x180079c3e  jz      short loc_180079C5B
0x180079c40  mov     rdx, rdi; unsigned __int16 *
0x180079c43  mov     [rsp+2300h+hKey], r13
0x180079c48  lea     rcx, [rsp+2300h+hKey]; this
0x180079c4d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180079c52  mov     [rsp+2300h+hKey], 0
0x180079c5b  test    r14d, r14d
0x180079c5e  jnz     short loc_180079C9C
0x180079c60  mov     rdx, rdi; unsigned __int16 *
0x180079c63  mov     rcx, rsi; this
0x180079c66  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079c6b  xor     r14d, r14d
0x180079c6e  mov     ebx, eax
0x180079c70  test    eax, eax
0x180079c72  js      loc_18007A13F
0x180079c78  mov     rdx, rdi; unsigned __int16 *
0x180079c7b  mov     rcx, rsi; this
0x180079c7e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180079c83  lea     rcx, [rsp+2300h+hKey]; this
0x180079c88  mov     ebx, eax
0x180079c8a  test    eax, eax
0x180079c8c  js      loc_18007A144
0x180079c92  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180079c97  jmp     loc_180079EE8
0x180079c9c  lea     rcx, [rsp+2300h+hKey]; this
0x180079ca1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180079ca6  lea     rdx, aNoremove; "NoRemove"
0x180079cad  mov     rcx, rdi; lpString1
0x180079cb0  mov     r12d, 1
0x180079cb6  call    cs:__imp_lstrcmpiW
0x180079cbd  nop     dword ptr [rax+rax+00h]
0x180079cc2  xor     r14d, r14d
0x180079cc5  test    eax, eax
0x180079cc7  jnz     short loc_180079CE1
0x180079cc9  mov     rdx, rdi; unsigned __int16 *
0x180079ccc  mov     rcx, rsi; this
0x180079ccf  mov     r12d, r14d
0x180079cd2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079cd7  mov     ebx, eax
0x180079cd9  test    eax, eax
0x180079cdb  js      loc_18007A106
0x180079ce1  lea     rdx, aVal; "Val"
0x180079ce8  mov     rcx, rdi; lpString1
0x180079ceb  call    cs:__imp_lstrcmpiW
0x180079cf2  nop     dword ptr [rax+rax+00h]
0x180079cf7  test    eax, eax
0x180079cf9  jnz     loc_180079DEE
0x180079cff  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180079d06  mov     rcx, rsi; this
0x180079d09  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079d0e  mov     ebx, eax
0x180079d10  test    eax, eax
0x180079d12  js      loc_18007A106
0x180079d18  mov     rdx, rdi; unsigned __int16 *
0x180079d1b  mov     rcx, rsi; this
0x180079d1e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079d23  mov     ebx, eax
0x180079d25  test    eax, eax
0x180079d27  js      loc_18007A106
0x180079d2d  cmp     word ptr [rdi], 3Dh ; '='
0x180079d31  jnz     loc_18007A101
0x180079d37  test    r15d, r15d
0x180079d3a  jz      short loc_180079D6C
0x180079d3c  mov     r9, rdi; unsigned __int16 *
0x180079d3f  mov     [rsp+2300h+var_22A0], r14
0x180079d44  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180079d4b  mov     [rsp+2300h+var_2298], r14
0x180079d50  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180079d55  mov     [rsp+2300h+hKey], r13
0x180079d5a  mov     rcx, rsi; this
0x180079d5d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180079d62  mov     [rsp+2300h+hKey], r14
0x180079d67  jmp     loc_180079C83
0x180079d6c  cmp     [rbp+2200h+arg_20], r14d
0x180079d73  jnz     short loc_180079DD4
0x180079d75  test    r12d, r12d
0x180079d78  jz      short loc_180079DD4
0x180079d7a  mov     r9d, 20006h; unsigned int
0x180079d80  mov     [rsp+2300h+hKey], r14
0x180079d85  xor     r8d, r8d; lpSubKey
0x180079d88  mov     [rsp+2300h+var_22A0], r14
0x180079d8d  mov     rdx, r13; hKey
0x180079d90  mov     [rsp+2300h+var_2298], r14
0x180079d95  lea     rcx, [rsp+2300h+hKey]; this
0x180079d9a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180079d9f  test    eax, eax
0x180079da1  jnz     loc_18007A136
0x180079da7  mov     rcx, [rsp+2300h+hKey]; hKey
0x180079dac  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180079db3  call    cs:__imp_RegDeleteValueW
0x180079dba  nop     dword ptr [rax+rax+00h]
0x180079dbf  test    eax, 0FFFFFFFDh
0x180079dc4  jnz     loc_18007A136
0x180079dca  lea     rcx, [rsp+2300h+hKey]; this
0x180079dcf  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180079dd4  mov     rdx, rdi; unsigned __int16 *
0x180079dd7  mov     rcx, rsi; this
0x180079dda  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180079ddf  mov     ebx, eax
0x180079de1  test    eax, eax
0x180079de3  jns     loc_180079B9F
0x180079de9  jmp     loc_18007A106
0x180079dee  mov     edx, 5Ch ; '\'; unsigned __int16
0x180079df3  mov     rcx, rdi; lpsz
0x180079df6  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180079dfb  test    rax, rax
0x180079dfe  jnz     loc_18007A101
0x180079e04  test    r15d, r15d
0x180079e07  jz      loc_180079F38
0x180079e0d  mov     r9d, 2001Fh; unsigned int
0x180079e13  lea     rcx, [rsp+2300h+var_2290]; this
0x180079e18  mov     r8, rdi; lpSubKey
0x180079e1b  mov     rdx, r13; hKey
0x180079e1e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180079e23  test    eax, eax
0x180079e25  jz      loc_180079EB0
0x180079e2b  mov     r9d, 20019h; unsigned int
0x180079e31  lea     rcx, [rsp+2300h+var_2290]; this
0x180079e36  mov     r8, rdi; lpSubKey
0x180079e39  mov     rdx, r13; hKey
0x180079e3c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180079e41  test    eax, eax
0x180079e43  jz      short loc_180079EB0
0x180079e45  lea     rax, [rbp+2200h+dwDisposition]
0x180079e49  mov     [rbp+2200h+dwDisposition], r14d
0x180079e4d  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180079e52  xor     r9d, r9d; lpClass
0x180079e55  lea     rax, [rbp+2200h+var_2270]
0x180079e59  mov     [rbp+2200h+var_2270], r14
0x180079e5d  mov     [rsp+2300h+phkResult], rax; phkResult
0x180079e62  xor     r8d, r8d; Reserved
0x180079e65  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180079e6a  mov     rdx, rdi; lpSubKey
0x180079e6d  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x180079e75  mov     rcx, r13; hKey
0x180079e78  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x180079e7d  call    cs:__imp_RegCreateKeyExW
0x180079e84  nop     dword ptr [rax+rax+00h]
0x180079e89  mov     ebx, eax
0x180079e8b  test    eax, eax
0x180079e8d  jnz     loc_18007A14B
0x180079e93  lea     rcx, [rsp+2300h+var_2290]; this
0x180079e98  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180079e9d  mov     ebx, eax
0x180079e9f  mov     rax, [rbp+2200h+var_2270]
0x180079ea3  mov     [rsp+2300h+var_2290], rax
0x180079ea8  test    ebx, ebx
0x180079eaa  jnz     loc_18007A14B
0x180079eb0  mov     rdx, rdi; unsigned __int16 *
0x180079eb3  mov     rcx, rsi; this
0x180079eb6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079ebb  mov     ebx, eax
0x180079ebd  test    eax, eax
0x180079ebf  js      loc_18007A106
0x180079ec5  cmp     word ptr [rdi], 3Dh ; '='
0x180079ec9  jnz     short loc_180079EE8
0x180079ecb  mov     r9, rdi; unsigned __int16 *
0x180079ece  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180079ed3  xor     r8d, r8d; unsigned __int16 *
0x180079ed6  mov     rcx, rsi; this
0x180079ed9  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180079ede  mov     ebx, eax
0x180079ee0  test    eax, eax
0x180079ee2  js      loc_18007A106
0x180079ee8  cmp     word ptr [rdi], 7Bh ; '{'
0x180079eec  jnz     loc_180079B9F
0x180079ef2  mov     rcx, rdi; String
0x180079ef5  call    cs:__imp_wcslen
0x180079efc  nop     dword ptr [rax+rax+00h]
0x180079f01  cmp     rax, 1
0x180079f05  jnz     loc_180079B9F
0x180079f0b  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180079f10  mov     r9d, r15d; int
0x180079f13  mov     rdx, rdi; unsigned __int16 *
0x180079f16  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180079f1b  mov     rcx, rsi; this
0x180079f1e  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180079f23  mov     ebx, eax
0x180079f25  test    eax, eax
0x180079f27  js      loc_18007A106
0x180079f2d  mov     rdx, rdi
0x180079f30  mov     rcx, rsi
0x180079f33  jmp     loc_180079B95
0x180079f38  cmp     [rbp+2200h+arg_20], r14d
0x180079f3f  jnz     short loc_180079F5C
0x180079f41  mov     r9d, 20019h; unsigned int
0x180079f47  lea     rcx, [rsp+2300h+var_2290]; this
0x180079f4c  mov     r8, rdi; lpSubKey
0x180079f4f  mov     rdx, r13; hKey
0x180079f52  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180079f57  mov     r14d, eax
0x180079f5a  jmp     short loc_180079F62
0x180079f5c  mov     r14d, 2
0x180079f62  test    r14d, r14d
0x180079f65  lea     rcx, [rbp+2200h+var_2260]
0x180079f69  mov     r15d, 1
0x180079f6f  mov     r8, rdi
0x180079f72  cmovz   r15d, [rbp+2200h+arg_20]
0x180079f7a  mov     edx, 104h
0x180079f7f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180079f83  call    cs:__imp__o_wcsncpy_s
0x180079f8a  nop     dword ptr [rax+rax+00h]
0x180079f8f  mov     ecx, eax; int
0x180079f91  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180079f96  mov     rdx, rdi; unsigned __int16 *
0x180079f99  mov     rcx, rsi; this
0x180079f9c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079fa1  mov     ebx, eax
0x180079fa3  test    eax, eax
0x180079fa5  js      loc_18007A106
0x180079fab  mov     rdx, rdi; unsigned __int16 *
0x180079fae  mov     rcx, rsi; this
0x180079fb1  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180079fb6  mov     ebx, eax
0x180079fb8  test    eax, eax
0x180079fba  js      loc_18007A106
0x180079fc0  cmp     word ptr [rdi], 7Bh ; '{'
0x180079fc4  jnz     short loc_18007A017
0x180079fc6  mov     rcx, rdi; String
0x180079fc9  call    cs:__imp_wcslen
0x180079fd0  nop     dword ptr [rax+rax+00h]
0x180079fd5  cmp     rax, 1
0x180079fd9  jnz     short loc_18007A017
0x180079fdb  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180079fe0  xor     r9d, r9d; int
0x180079fe3  mov     rdx, rdi; unsigned __int16 *
0x180079fe6  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180079feb  mov     rcx, rsi; this
0x180079fee  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180079ff3  mov     ebx, eax
0x180079ff5  test    eax, eax
0x180079ff7  jns     short loc_18007A002
0x180079ff9  test    r15d, r15d
0x180079ffc  jz      loc_18007A106
0x18007a002  mov     rdx, rdi; unsigned __int16 *
0x18007a005  mov     rcx, rsi; this
0x18007a008  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18007a00d  mov     ebx, eax
0x18007a00f  test    eax, eax
0x18007a011  js      loc_18007A106
  ... truncated ...
```
