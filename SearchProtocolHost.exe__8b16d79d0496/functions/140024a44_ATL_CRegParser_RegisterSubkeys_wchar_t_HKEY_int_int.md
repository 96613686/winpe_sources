# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x140024a44`
- end: `0x140025025`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1505`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x140024714`
- `0x140024a44`

## callees

- `0x140005240`
- `0x140011c54`
- `0x140012480`
- `0x1400124f0`
- `0x1400126e8`
- `0x140012b60`
- `0x140014704`
- `0x14001e72c`
- `0x140020960`
- `0x14002147c`
- `0x1400245bc`
- `0x140024a44`
- `0x140028ef0`
- `0x140029948`
- `0x140069b10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140024e52`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140024e52`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140024ca1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140024ca1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140024d53`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140024d53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140024ac7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140024ada`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140024bae`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140024bdd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140024ac7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140024ada`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140024bae`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140024bdd`

## string_xrefs

- `0x140024ad0`: `ForceRemove`
- `0x140024ba4`: `NoRemove`
- `0x140024abd`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(ATL::CRegParser *this, wchar_t *a2, HKEY a3, int a4, int a5)
{
  int v5; // r15d
  wchar_t *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  HKEY v31[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult[2]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v34[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  phkResult[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v31, 0, sizeof(v31));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_79;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( v5 )
        {
          hKey = 0;
          v29 = 0;
          v30 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_81;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult[0] = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            v31[0] = phkResult[0];
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v34, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !a5 )
            {
              v16 = v18;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v31[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, v34);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v31[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v29 = 0;
              v30 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v34);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_79;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v29 = 0;
      v30 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v29 = 0;
    v30 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140024a44  push    rbp
0x140024a46  push    rbx
0x140024a47  push    rsi
0x140024a48  push    rdi
0x140024a49  push    r12
0x140024a4b  push    r13
0x140024a4d  push    r14
0x140024a4f  push    r15
0x140024a51  lea     rbp, [rsp-21C8h]
0x140024a59  mov     eax, 22C8h
0x140024a5e  call    _alloca_probe
0x140024a63  sub     rsp, rax
0x140024a66  mov     [rbp+2200h+var_2268], 0FFFFFFFFFFFFFFFEh
0x140024a6e  mov     rax, cs:__security_cookie
0x140024a75  xor     rax, rsp
0x140024a78  mov     [rbp+2200h+var_50], rax
0x140024a7f  mov     r15d, r9d
0x140024a82  mov     [rsp+2300h+var_22B0], r9d
0x140024a87  mov     r13, r8
0x140024a8a  mov     rdi, rdx
0x140024a8d  mov     rsi, rcx
0x140024a90  xor     r14d, r14d
0x140024a93  mov     [rsp+2300h+var_2290], r14
0x140024a98  mov     [rsp+2300h+var_2288], r14
0x140024a9d  mov     [rbp+2200h+var_2280], r14
0x140024aa1  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140024aa6  test    eax, eax
0x140024aa8  mov     ebx, eax
0x140024aaa  js      loc_140024FD9
0x140024ab0  xor     r12d, r12d
0x140024ab3  cmp     word ptr [rdi], 7Dh ; '}'
0x140024ab7  jz      loc_140024FD9
0x140024abd  lea     rdx, String2; "Delete"
0x140024ac4  mov     rcx, rdi; lpString1
0x140024ac7  call    cs:__imp_lstrcmpiW
0x140024acd  mov     r14d, eax
0x140024ad0  lea     rdx, aForceremove; "ForceRemove"
0x140024ad7  mov     rcx, rdi; lpString1
0x140024ada  call    cs:__imp_lstrcmpiW
0x140024ae0  test    eax, eax
0x140024ae2  jz      short loc_140024AED
0x140024ae4  test    r14d, r14d
0x140024ae7  jnz     loc_140024B9E
0x140024aed  mov     rdx, rdi; wchar_t *
0x140024af0  mov     rcx, rsi; this
0x140024af3  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140024af8  mov     ebx, eax
0x140024afa  test    eax, eax
0x140024afc  js      loc_140024FD9
0x140024b02  test    r15d, r15d
0x140024b05  jz      loc_140024B9E
0x140024b0b  mov     [rsp+2300h+hKey], r12
0x140024b10  mov     [rsp+2300h+var_22A0], r12
0x140024b15  mov     [rsp+2300h+var_2298], r12
0x140024b1a  mov     edx, 5Ch ; '\'; wchar_t
0x140024b1f  mov     rcx, rdi; lpsz
0x140024b22  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x140024b27  test    rax, rax
0x140024b2a  jnz     loc_140024FCA
0x140024b30  mov     rdx, rdi; wchar_t *
0x140024b33  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x140024b38  test    eax, eax
0x140024b3a  jz      short loc_140024B53
0x140024b3c  mov     [rsp+2300h+hKey], r13
0x140024b41  mov     rdx, rdi; wchar_t *
0x140024b44  lea     rcx, [rsp+2300h+hKey]; this
0x140024b49  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x140024b4e  mov     [rsp+2300h+hKey], r12
0x140024b53  test    r14d, r14d
0x140024b56  jnz     short loc_140024B94
0x140024b58  mov     rdx, rdi; wchar_t *
0x140024b5b  mov     rcx, rsi; this
0x140024b5e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140024b63  mov     ebx, eax
0x140024b65  xor     r14d, r14d
0x140024b68  test    eax, eax
0x140024b6a  js      loc_140025011
0x140024b70  mov     rdx, rdi; wchar_t *
0x140024b73  mov     rcx, rsi; this
0x140024b76  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x140024b7b  mov     ebx, eax
0x140024b7d  test    eax, eax
0x140024b7f  lea     rcx, [rsp+2300h+hKey]; this
0x140024b84  js      loc_140025016
0x140024b8a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140024b8f  jmp     loc_140024DB8
0x140024b94  lea     rcx, [rsp+2300h+hKey]; this
0x140024b99  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140024b9e  mov     r12d, 1
0x140024ba4  lea     rdx, aNoremove; "NoRemove"
0x140024bab  mov     rcx, rdi; lpString1
0x140024bae  call    cs:__imp_lstrcmpiW
0x140024bb4  xor     r14d, r14d
0x140024bb7  test    eax, eax
0x140024bb9  jnz     short loc_140024BD3
0x140024bbb  mov     r12d, r14d
0x140024bbe  mov     rdx, rdi; wchar_t *
0x140024bc1  mov     rcx, rsi; this
0x140024bc4  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140024bc9  mov     ebx, eax
0x140024bcb  test    eax, eax
0x140024bcd  js      loc_140024FD9
0x140024bd3  lea     rdx, aVal; "Val"
0x140024bda  mov     rcx, rdi; lpString1
0x140024bdd  call    cs:__imp_lstrcmpiW
0x140024be3  test    eax, eax
0x140024be5  jnz     loc_140024CCC
0x140024beb  lea     rdx, [rbp+2200h+ValueName]; wchar_t *
0x140024bf2  mov     rcx, rsi; this
0x140024bf5  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140024bfa  mov     ebx, eax
0x140024bfc  test    eax, eax
0x140024bfe  js      loc_140024FD9
0x140024c04  mov     rdx, rdi; wchar_t *
0x140024c07  mov     rcx, rsi; this
0x140024c0a  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140024c0f  mov     ebx, eax
0x140024c11  test    eax, eax
0x140024c13  js      loc_140024FD9
0x140024c19  cmp     word ptr [rdi], 3Dh ; '='
0x140024c1d  jnz     loc_140024FD4
0x140024c23  test    r15d, r15d
0x140024c26  jz      short loc_140024C5A
0x140024c28  mov     [rsp+2300h+var_22A0], r14
0x140024c2d  mov     [rsp+2300h+var_2298], r14
0x140024c32  mov     [rsp+2300h+hKey], r13
0x140024c37  mov     r9, rdi; wchar_t *
0x140024c3a  lea     r8, [rbp+2200h+ValueName]; wchar_t *
0x140024c41  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x140024c46  mov     rcx, rsi; this
0x140024c49  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x140024c4e  mov     ebx, eax
0x140024c50  mov     [rsp+2300h+hKey], r14
0x140024c55  jmp     loc_140024B7D
0x140024c5a  cmp     [rbp+2200h+arg_20], r14d
0x140024c61  jnz     short loc_140024CBC
0x140024c63  test    r12d, r12d
0x140024c66  jz      short loc_140024CBC
0x140024c68  mov     [rsp+2300h+hKey], r14
0x140024c6d  mov     [rsp+2300h+var_22A0], r14
0x140024c72  mov     [rsp+2300h+var_2298], r14
0x140024c77  mov     r9d, 20006h; unsigned int
0x140024c7d  xor     r8d, r8d; lpSubKey
0x140024c80  mov     rdx, r13; hKey
0x140024c83  lea     rcx, [rsp+2300h+hKey]; this
0x140024c88  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x140024c8d  test    eax, eax
0x140024c8f  jnz     loc_140025008
0x140024c95  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x140024c9c  mov     rcx, [rsp+2300h+hKey]; hKey
0x140024ca1  call    cs:__imp_RegDeleteValueW
0x140024ca7  test    eax, 0FFFFFFFDh
0x140024cac  jnz     loc_140025008
0x140024cb2  lea     rcx, [rsp+2300h+hKey]; this
0x140024cb7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140024cbc  mov     rdx, rdi; wchar_t *
0x140024cbf  mov     rcx, rsi; this
0x140024cc2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x140024cc7  jmp     loc_140024AA6
0x140024ccc  mov     edx, 5Ch ; '\'; wchar_t
0x140024cd1  mov     rcx, rdi; lpsz
0x140024cd4  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x140024cd9  test    rax, rax
0x140024cdc  jnz     loc_140024FD4
0x140024ce2  test    r15d, r15d
0x140024ce5  jz      loc_140024E07
0x140024ceb  mov     ebx, 2001Fh
0x140024cf0  mov     r9d, ebx; unsigned int
0x140024cf3  mov     r8, rdi; lpSubKey
0x140024cf6  mov     rdx, r13; hKey
0x140024cf9  lea     rcx, [rsp+2300h+var_2290]; this
0x140024cfe  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x140024d03  test    eax, eax
0x140024d05  jz      short loc_140024D80
0x140024d07  lea     r9d, [rbx-6]; unsigned int
0x140024d0b  mov     r8, rdi; lpSubKey
0x140024d0e  mov     rdx, r13; hKey
0x140024d11  lea     rcx, [rsp+2300h+var_2290]; this
0x140024d16  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x140024d1b  test    eax, eax
0x140024d1d  jz      short loc_140024D80
0x140024d1f  mov     [rbp+2200h+dwDisposition], r14d
0x140024d23  mov     [rbp+2200h+var_2270], r14
0x140024d27  lea     rax, [rbp+2200h+dwDisposition]
0x140024d2b  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x140024d30  lea     rax, [rbp+2200h+var_2270]
0x140024d34  mov     [rsp+2300h+phkResult], rax; phkResult
0x140024d39  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x140024d3e  mov     [rsp+2300h+samDesired], ebx; samDesired
0x140024d42  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x140024d47  xor     r9d, r9d; lpClass
0x140024d4a  xor     r8d, r8d; Reserved
0x140024d4d  mov     rdx, rdi; lpSubKey
0x140024d50  mov     rcx, r13; hKey
0x140024d53  call    cs:__imp_RegCreateKeyExW
0x140024d59  mov     ecx, eax
0x140024d5b  test    eax, eax
0x140024d5d  jnz     loc_140024F07
0x140024d63  lea     rcx, [rsp+2300h+var_2290]; this
0x140024d68  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140024d6d  mov     ecx, eax
0x140024d6f  mov     rax, [rbp+2200h+var_2270]
0x140024d73  mov     [rsp+2300h+var_2290], rax
0x140024d78  test    ecx, ecx
0x140024d7a  jnz     loc_140024F07
0x140024d80  mov     rdx, rdi; wchar_t *
0x140024d83  mov     rcx, rsi; this
0x140024d86  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140024d8b  mov     ebx, eax
0x140024d8d  test    eax, eax
0x140024d8f  js      loc_140024FD9
0x140024d95  cmp     word ptr [rdi], 3Dh ; '='
0x140024d99  jnz     short loc_140024DB8
0x140024d9b  mov     r9, rdi; wchar_t *
0x140024d9e  xor     r8d, r8d; wchar_t *
0x140024da1  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x140024da6  mov     rcx, rsi; this
0x140024da9  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x140024dae  mov     ebx, eax
0x140024db0  test    eax, eax
0x140024db2  js      loc_140024FD9
0x140024db8  cmp     word ptr [rdi], 7Bh ; '{'
0x140024dbc  jnz     loc_140024AB0
0x140024dc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024dc6  inc     rax
0x140024dc9  cmp     [rdi+rax*2], r14w
0x140024dce  jnz     short loc_140024DC6
0x140024dd0  cmp     rax, 1
0x140024dd4  jnz     loc_140024AB0
0x140024dda  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x140024ddf  mov     r9d, r15d; int
0x140024de2  mov     r8, [rsp+2300h+var_2290]; HKEY
0x140024de7  mov     rdx, rdi; wchar_t *
0x140024dea  mov     rcx, rsi; this
0x140024ded  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x140024df2  mov     ebx, eax
0x140024df4  test    eax, eax
0x140024df6  js      loc_140024FD9
0x140024dfc  mov     rdx, rdi
0x140024dff  mov     rcx, rsi
0x140024e02  jmp     loc_140024AA1
0x140024e07  cmp     [rbp+2200h+arg_20], r14d
0x140024e0e  jnz     short loc_140024E2B
0x140024e10  mov     r9d, 20019h; unsigned int
0x140024e16  mov     r8, rdi; lpSubKey
0x140024e19  mov     rdx, r13; hKey
0x140024e1c  lea     rcx, [rsp+2300h+var_2290]; this
0x140024e21  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x140024e26  mov     r14d, eax
0x140024e29  jmp     short loc_140024E31
0x140024e2b  mov     r14d, 2
0x140024e31  mov     r15d, 1
0x140024e37  test    r14d, r14d
0x140024e3a  cmovz   r15d, [rbp+2200h+arg_20]
0x140024e42  or      r9, 0FFFFFFFFFFFFFFFFh
0x140024e46  mov     r8, rdi
0x140024e49  mov     edx, 104h
0x140024e4e  lea     rcx, [rbp+2200h+var_2260]
0x140024e52  call    cs:__imp__o_wcsncpy_s
0x140024e58  mov     ecx, eax; int
0x140024e5a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140024e5f  mov     rdx, rdi; wchar_t *
0x140024e62  mov     rcx, rsi; this
0x140024e65  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140024e6a  mov     ebx, eax
0x140024e6c  test    eax, eax
0x140024e6e  js      loc_140024FD9
0x140024e74  mov     rdx, rdi; wchar_t *
0x140024e77  mov     rcx, rsi; this
0x140024e7a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x140024e7f  mov     ebx, eax
0x140024e81  xor     ecx, ecx
0x140024e83  test    eax, eax
0x140024e85  js      loc_140024FD9
0x140024e8b  cmp     word ptr [rdi], 7Bh ; '{'
0x140024e8f  jnz     short loc_140024EE0
0x140024e91  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024e95  inc     rax
0x140024e98  cmp     [rdi+rax*2], cx
0x140024e9c  jnz     short loc_140024E95
0x140024e9e  cmp     rax, 1
0x140024ea2  jnz     short loc_140024EE0
0x140024ea4  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x140024ea9  xor     r9d, r9d; int
0x140024eac  mov     r8, [rsp+2300h+var_2290]; HKEY
0x140024eb1  mov     rdx, rdi; wchar_t *
0x140024eb4  mov     rcx, rsi; this
0x140024eb7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x140024ebc  mov     ebx, eax
0x140024ebe  test    eax, eax
0x140024ec0  jns     short loc_140024ECB
0x140024ec2  test    r15d, r15d
0x140024ec5  jz      loc_140024FD9
0x140024ecb  mov     rdx, rdi; wchar_t *
0x140024ece  mov     rcx, rsi; this
0x140024ed1  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140024ed6  mov     ebx, eax
0x140024ed8  test    eax, eax
0x140024eda  js      loc_140024FD9
0x140024ee0  cmp     r14d, 2
  ... truncated ...
```
