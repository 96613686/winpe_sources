# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x18013ba2c`
- end: `0x18013c005`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18013b670`
- `0x18013ba2c`

## callees

- `0x18005bf7c`
- `0x180098238`
- `0x180098290`
- `0x1801244c0`
- `0x180134cbc`
- `0x180135504`
- `0x180135b80`
- `0x180137ce8`
- `0x1801397b8`
- `0x18013a418`
- `0x18013b55c`
- `0x18013ba2c`
- `0x18013db50`
- `0x18013dca4`
- `0x180222f70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18013be32`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18013be32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18013bd33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18013bd33`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18013bc81`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18013bc81`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013baa7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013baba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013bb8e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013bbbd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013baa7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013baba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013bb8e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013bbbd`

## string_xrefs

- `0x18013bab0`: `ForceRemove`
- `0x18013bb84`: `NoRemove`
- `0x18013ba9d`: `Delete`

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
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v33[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, sizeof(v30));
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
          v28 = 0;
          v29 = 0;
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
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            v30[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v33, 260, v7, -1);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v33) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, v33);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v33);
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
      v28 = 0;
      v29 = 0;
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
    v28 = 0;
    v29 = 0;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18013ba2c  push    rbp
0x18013ba2e  push    rbx
0x18013ba2f  push    rsi
0x18013ba30  push    rdi
0x18013ba31  push    r12
0x18013ba33  push    r13
0x18013ba35  push    r14
0x18013ba37  push    r15
0x18013ba39  lea     rbp, [rsp-21C8h]
0x18013ba41  mov     eax, 22C8h
0x18013ba46  call    _alloca_probe
0x18013ba4b  sub     rsp, rax
0x18013ba4e  mov     rax, cs:__security_cookie
0x18013ba55  xor     rax, rsp
0x18013ba58  mov     [rbp+2200h+var_50], rax
0x18013ba5f  mov     r15d, r9d
0x18013ba62  mov     [rsp+2300h+var_22B0], r9d
0x18013ba67  mov     r13, r8
0x18013ba6a  mov     rdi, rdx
0x18013ba6d  mov     rsi, rcx
0x18013ba70  xor     r14d, r14d
0x18013ba73  mov     [rsp+2300h+var_2290], r14
0x18013ba78  mov     [rsp+2300h+var_2288], r14
0x18013ba7d  mov     [rbp+2200h+var_2280], r14
0x18013ba81  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18013ba86  test    eax, eax
0x18013ba88  mov     ebx, eax
0x18013ba8a  js      loc_18013BFB9
0x18013ba90  xor     r12d, r12d
0x18013ba93  cmp     word ptr [rdi], 7Dh ; '}'
0x18013ba97  jz      loc_18013BFB9
0x18013ba9d  lea     rdx, aDelete_0; "Delete"
0x18013baa4  mov     rcx, rdi; lpString1
0x18013baa7  call    cs:__imp_lstrcmpiW
0x18013baad  mov     r14d, eax
0x18013bab0  lea     rdx, aForceremove; "ForceRemove"
0x18013bab7  mov     rcx, rdi; lpString1
0x18013baba  call    cs:__imp_lstrcmpiW
0x18013bac0  test    eax, eax
0x18013bac2  jz      short loc_18013BACD
0x18013bac4  test    r14d, r14d
0x18013bac7  jnz     loc_18013BB7E
0x18013bacd  mov     rdx, rdi; wchar_t *
0x18013bad0  mov     rcx, rsi; this
0x18013bad3  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18013bad8  mov     ebx, eax
0x18013bada  test    eax, eax
0x18013badc  js      loc_18013BFB9
0x18013bae2  test    r15d, r15d
0x18013bae5  jz      loc_18013BB7E
0x18013baeb  mov     [rsp+2300h+hKey], r12
0x18013baf0  mov     [rsp+2300h+var_22A0], r12
0x18013baf5  mov     [rsp+2300h+var_2298], r12
0x18013bafa  mov     edx, 5Ch ; '\'; wchar_t
0x18013baff  mov     rcx, rdi; lpsz
0x18013bb02  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18013bb07  test    rax, rax
0x18013bb0a  jnz     loc_18013BFAA
0x18013bb10  mov     rdx, rdi; wchar_t *
0x18013bb13  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x18013bb18  test    eax, eax
0x18013bb1a  jz      short loc_18013BB33
0x18013bb1c  mov     [rsp+2300h+hKey], r13
0x18013bb21  mov     rdx, rdi; wchar_t *
0x18013bb24  lea     rcx, [rsp+2300h+hKey]; this
0x18013bb29  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18013bb2e  mov     [rsp+2300h+hKey], r12
0x18013bb33  test    r14d, r14d
0x18013bb36  jnz     short loc_18013BB74
0x18013bb38  mov     rdx, rdi; wchar_t *
0x18013bb3b  mov     rcx, rsi; this
0x18013bb3e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18013bb43  mov     ebx, eax
0x18013bb45  xor     r14d, r14d
0x18013bb48  test    eax, eax
0x18013bb4a  js      loc_18013BFF1
0x18013bb50  mov     rdx, rdi; wchar_t *
0x18013bb53  mov     rcx, rsi; this
0x18013bb56  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18013bb5b  mov     ebx, eax
0x18013bb5d  test    eax, eax
0x18013bb5f  lea     rcx, [rsp+2300h+hKey]; this
0x18013bb64  js      loc_18013BFF6
0x18013bb6a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18013bb6f  jmp     loc_18013BD98
0x18013bb74  lea     rcx, [rsp+2300h+hKey]; this
0x18013bb79  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18013bb7e  mov     r12d, 1
0x18013bb84  lea     rdx, aNoremove; "NoRemove"
0x18013bb8b  mov     rcx, rdi; lpString1
0x18013bb8e  call    cs:__imp_lstrcmpiW
0x18013bb94  xor     r14d, r14d
0x18013bb97  test    eax, eax
0x18013bb99  jnz     short loc_18013BBB3
0x18013bb9b  mov     r12d, r14d
0x18013bb9e  mov     rdx, rdi; wchar_t *
0x18013bba1  mov     rcx, rsi; this
0x18013bba4  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18013bba9  mov     ebx, eax
0x18013bbab  test    eax, eax
0x18013bbad  js      loc_18013BFB9
0x18013bbb3  lea     rdx, aVal; "Val"
0x18013bbba  mov     rcx, rdi; lpString1
0x18013bbbd  call    cs:__imp_lstrcmpiW
0x18013bbc3  test    eax, eax
0x18013bbc5  jnz     loc_18013BCAC
0x18013bbcb  lea     rdx, [rbp+2200h+ValueName]; wchar_t *
0x18013bbd2  mov     rcx, rsi; this
0x18013bbd5  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18013bbda  mov     ebx, eax
0x18013bbdc  test    eax, eax
0x18013bbde  js      loc_18013BFB9
0x18013bbe4  mov     rdx, rdi; wchar_t *
0x18013bbe7  mov     rcx, rsi; this
0x18013bbea  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18013bbef  mov     ebx, eax
0x18013bbf1  test    eax, eax
0x18013bbf3  js      loc_18013BFB9
0x18013bbf9  cmp     word ptr [rdi], 3Dh ; '='
0x18013bbfd  jnz     loc_18013BFB4
0x18013bc03  test    r15d, r15d
0x18013bc06  jz      short loc_18013BC3A
0x18013bc08  mov     [rsp+2300h+var_22A0], r14
0x18013bc0d  mov     [rsp+2300h+var_2298], r14
0x18013bc12  mov     [rsp+2300h+hKey], r13
0x18013bc17  mov     r9, rdi; wchar_t *
0x18013bc1a  lea     r8, [rbp+2200h+ValueName]; wchar_t *
0x18013bc21  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18013bc26  mov     rcx, rsi; this
0x18013bc29  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18013bc2e  mov     ebx, eax
0x18013bc30  mov     [rsp+2300h+hKey], r14
0x18013bc35  jmp     loc_18013BB5D
0x18013bc3a  cmp     [rbp+2200h+arg_20], r14d
0x18013bc41  jnz     short loc_18013BC9C
0x18013bc43  test    r12d, r12d
0x18013bc46  jz      short loc_18013BC9C
0x18013bc48  mov     [rsp+2300h+hKey], r14
0x18013bc4d  mov     [rsp+2300h+var_22A0], r14
0x18013bc52  mov     [rsp+2300h+var_2298], r14
0x18013bc57  mov     r9d, 20006h; unsigned int
0x18013bc5d  xor     r8d, r8d; lpSubKey
0x18013bc60  mov     rdx, r13; hKey
0x18013bc63  lea     rcx, [rsp+2300h+hKey]; this
0x18013bc68  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18013bc6d  test    eax, eax
0x18013bc6f  jnz     loc_18013BFE8
0x18013bc75  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18013bc7c  mov     rcx, [rsp+2300h+hKey]; hKey
0x18013bc81  call    cs:__imp_RegDeleteValueW
0x18013bc87  test    eax, 0FFFFFFFDh
0x18013bc8c  jnz     loc_18013BFE8
0x18013bc92  lea     rcx, [rsp+2300h+hKey]; this
0x18013bc97  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18013bc9c  mov     rdx, rdi; wchar_t *
0x18013bc9f  mov     rcx, rsi; this
0x18013bca2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18013bca7  jmp     loc_18013BA86
0x18013bcac  mov     edx, 5Ch ; '\'; wchar_t
0x18013bcb1  mov     rcx, rdi; lpsz
0x18013bcb4  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18013bcb9  test    rax, rax
0x18013bcbc  jnz     loc_18013BFB4
0x18013bcc2  test    r15d, r15d
0x18013bcc5  jz      loc_18013BDE7
0x18013bccb  mov     ebx, 2001Fh
0x18013bcd0  mov     r9d, ebx; unsigned int
0x18013bcd3  mov     r8, rdi; lpSubKey
0x18013bcd6  mov     rdx, r13; hKey
0x18013bcd9  lea     rcx, [rsp+2300h+var_2290]; this
0x18013bcde  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18013bce3  test    eax, eax
0x18013bce5  jz      short loc_18013BD60
0x18013bce7  lea     r9d, [rbx-6]; unsigned int
0x18013bceb  mov     r8, rdi; lpSubKey
0x18013bcee  mov     rdx, r13; hKey
0x18013bcf1  lea     rcx, [rsp+2300h+var_2290]; this
0x18013bcf6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18013bcfb  test    eax, eax
0x18013bcfd  jz      short loc_18013BD60
0x18013bcff  mov     [rbp+2200h+dwDisposition], r14d
0x18013bd03  mov     [rbp+2200h+var_2270], r14
0x18013bd07  lea     rax, [rbp+2200h+dwDisposition]
0x18013bd0b  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18013bd10  lea     rax, [rbp+2200h+var_2270]
0x18013bd14  mov     [rsp+2300h+phkResult], rax; phkResult
0x18013bd19  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18013bd1e  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18013bd22  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18013bd27  xor     r9d, r9d; lpClass
0x18013bd2a  xor     r8d, r8d; Reserved
0x18013bd2d  mov     rdx, rdi; lpSubKey
0x18013bd30  mov     rcx, r13; hKey
0x18013bd33  call    cs:__imp_RegCreateKeyExW
0x18013bd39  mov     ecx, eax
0x18013bd3b  test    eax, eax
0x18013bd3d  jnz     loc_18013BEE7
0x18013bd43  lea     rcx, [rsp+2300h+var_2290]; this
0x18013bd48  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18013bd4d  mov     ecx, eax
0x18013bd4f  mov     rax, [rbp+2200h+var_2270]
0x18013bd53  mov     [rsp+2300h+var_2290], rax
0x18013bd58  test    ecx, ecx
0x18013bd5a  jnz     loc_18013BEE7
0x18013bd60  mov     rdx, rdi; wchar_t *
0x18013bd63  mov     rcx, rsi; this
0x18013bd66  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18013bd6b  mov     ebx, eax
0x18013bd6d  test    eax, eax
0x18013bd6f  js      loc_18013BFB9
0x18013bd75  cmp     word ptr [rdi], 3Dh ; '='
0x18013bd79  jnz     short loc_18013BD98
0x18013bd7b  mov     r9, rdi; wchar_t *
0x18013bd7e  xor     r8d, r8d; wchar_t *
0x18013bd81  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18013bd86  mov     rcx, rsi; this
0x18013bd89  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18013bd8e  mov     ebx, eax
0x18013bd90  test    eax, eax
0x18013bd92  js      loc_18013BFB9
0x18013bd98  cmp     word ptr [rdi], 7Bh ; '{'
0x18013bd9c  jnz     loc_18013BA90
0x18013bda2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18013bda6  inc     rax
0x18013bda9  cmp     [rdi+rax*2], r14w
0x18013bdae  jnz     short loc_18013BDA6
0x18013bdb0  cmp     rax, 1
0x18013bdb4  jnz     loc_18013BA90
0x18013bdba  mov     [rsp+2300h+dwOptions], r14d; int
0x18013bdbf  mov     r9d, r15d; int
0x18013bdc2  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18013bdc7  mov     rdx, rdi; wchar_t *
0x18013bdca  mov     rcx, rsi; this
0x18013bdcd  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18013bdd2  mov     ebx, eax
0x18013bdd4  test    eax, eax
0x18013bdd6  js      loc_18013BFB9
0x18013bddc  mov     rdx, rdi
0x18013bddf  mov     rcx, rsi
0x18013bde2  jmp     loc_18013BA81
0x18013bde7  cmp     [rbp+2200h+arg_20], r14d
0x18013bdee  jnz     short loc_18013BE0B
0x18013bdf0  mov     r9d, 20019h; unsigned int
0x18013bdf6  mov     r8, rdi; lpSubKey
0x18013bdf9  mov     rdx, r13; hKey
0x18013bdfc  lea     rcx, [rsp+2300h+var_2290]; this
0x18013be01  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18013be06  mov     r14d, eax
0x18013be09  jmp     short loc_18013BE11
0x18013be0b  mov     r14d, 2
0x18013be11  mov     r15d, 1
0x18013be17  test    r14d, r14d
0x18013be1a  cmovz   r15d, [rbp+2200h+arg_20]
0x18013be22  or      r9, 0FFFFFFFFFFFFFFFFh
0x18013be26  mov     r8, rdi
0x18013be29  mov     edx, 104h
0x18013be2e  lea     rcx, [rbp+2200h+var_2260]
0x18013be32  call    cs:__imp__o_wcsncpy_s
0x18013be38  mov     ecx, eax; int
0x18013be3a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18013be3f  mov     rdx, rdi; wchar_t *
0x18013be42  mov     rcx, rsi; this
0x18013be45  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18013be4a  mov     ebx, eax
0x18013be4c  test    eax, eax
0x18013be4e  js      loc_18013BFB9
0x18013be54  mov     rdx, rdi; wchar_t *
0x18013be57  mov     rcx, rsi; this
0x18013be5a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18013be5f  mov     ebx, eax
0x18013be61  xor     ecx, ecx
0x18013be63  test    eax, eax
0x18013be65  js      loc_18013BFB9
0x18013be6b  cmp     word ptr [rdi], 7Bh ; '{'
0x18013be6f  jnz     short loc_18013BEC0
0x18013be71  or      rax, 0FFFFFFFFFFFFFFFFh
0x18013be75  inc     rax
0x18013be78  cmp     [rdi+rax*2], cx
0x18013be7c  jnz     short loc_18013BE75
0x18013be7e  cmp     rax, 1
0x18013be82  jnz     short loc_18013BEC0
0x18013be84  mov     [rsp+2300h+dwOptions], r15d; int
0x18013be89  xor     r9d, r9d; int
0x18013be8c  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18013be91  mov     rdx, rdi; wchar_t *
0x18013be94  mov     rcx, rsi; this
0x18013be97  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18013be9c  mov     ebx, eax
0x18013be9e  test    eax, eax
0x18013bea0  jns     short loc_18013BEAB
0x18013bea2  test    r15d, r15d
0x18013bea5  jz      loc_18013BFB9
0x18013beab  mov     rdx, rdi; wchar_t *
0x18013beae  mov     rcx, rsi; this
0x18013beb1  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18013beb6  mov     ebx, eax
0x18013beb8  test    eax, eax
0x18013beba  js      loc_18013BFB9
0x18013bec0  cmp     r14d, 2
0x18013bec4  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
