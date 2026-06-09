# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x140022e00`
- end: `0x1400233e1`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1505`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x140022ad0`
- `0x140022e00`

## callees

- `0x1400030a0`
- `0x14001cd84`
- `0x14001d49c`
- `0x14001d50c`
- `0x14001d710`
- `0x14001d910`
- `0x14001e208`
- `0x14002136c`
- `0x140021cc4`
- `0x1400223bc`
- `0x1400229bc`
- `0x140022e00`
- `0x140023fd0`
- `0x1400247b8`
- `0x140049bf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14002320e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14002320e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14002305d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14002305d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002310f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002310f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022e83`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022e96`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022f6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022f99`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022e83`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022e96`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022f6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022f99`

## string_xrefs

- `0x140022e8c`: `ForceRemove`
- `0x140022f60`: `NoRemove`
- `0x140022e79`: `Delete`

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
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
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
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
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
0x140022e00  push    rbp
0x140022e02  push    rbx
0x140022e03  push    rsi
0x140022e04  push    rdi
0x140022e05  push    r12
0x140022e07  push    r13
0x140022e09  push    r14
0x140022e0b  push    r15
0x140022e0d  lea     rbp, [rsp-21C8h]
0x140022e15  mov     eax, 22C8h
0x140022e1a  call    _alloca_probe
0x140022e1f  sub     rsp, rax
0x140022e22  mov     [rbp+2200h+var_2268], 0FFFFFFFFFFFFFFFEh
0x140022e2a  mov     rax, cs:__security_cookie
0x140022e31  xor     rax, rsp
0x140022e34  mov     [rbp+2200h+var_50], rax
0x140022e3b  mov     r15d, r9d
0x140022e3e  mov     [rsp+2300h+var_22B0], r9d
0x140022e43  mov     r13, r8
0x140022e46  mov     rdi, rdx
0x140022e49  mov     rsi, rcx
0x140022e4c  xor     r14d, r14d
0x140022e4f  mov     [rsp+2300h+var_2290], r14
0x140022e54  mov     [rsp+2300h+var_2288], r14
0x140022e59  mov     [rbp+2200h+var_2280], r14
0x140022e5d  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140022e62  test    eax, eax
0x140022e64  mov     ebx, eax
0x140022e66  js      loc_140023395
0x140022e6c  xor     r12d, r12d
0x140022e6f  cmp     word ptr [rdi], 7Dh ; '}'
0x140022e73  jz      loc_140023395
0x140022e79  lea     rdx, String2; "Delete"
0x140022e80  mov     rcx, rdi; lpString1
0x140022e83  call    cs:__imp_lstrcmpiW
0x140022e89  mov     r14d, eax
0x140022e8c  lea     rdx, aForceremove; "ForceRemove"
0x140022e93  mov     rcx, rdi; lpString1
0x140022e96  call    cs:__imp_lstrcmpiW
0x140022e9c  test    eax, eax
0x140022e9e  jz      short loc_140022EA9
0x140022ea0  test    r14d, r14d
0x140022ea3  jnz     loc_140022F5A
0x140022ea9  mov     rdx, rdi; wchar_t *
0x140022eac  mov     rcx, rsi; this
0x140022eaf  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140022eb4  mov     ebx, eax
0x140022eb6  test    eax, eax
0x140022eb8  js      loc_140023395
0x140022ebe  test    r15d, r15d
0x140022ec1  jz      loc_140022F5A
0x140022ec7  mov     [rsp+2300h+hKey], r12
0x140022ecc  mov     [rsp+2300h+var_22A0], r12
0x140022ed1  mov     [rsp+2300h+var_2298], r12
0x140022ed6  mov     edx, 5Ch ; '\'; wchar_t
0x140022edb  mov     rcx, rdi; lpsz
0x140022ede  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x140022ee3  test    rax, rax
0x140022ee6  jnz     loc_140023386
0x140022eec  mov     rdx, rdi; wchar_t *
0x140022eef  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x140022ef4  test    eax, eax
0x140022ef6  jz      short loc_140022F0F
0x140022ef8  mov     [rsp+2300h+hKey], r13
0x140022efd  mov     rdx, rdi; wchar_t *
0x140022f00  lea     rcx, [rsp+2300h+hKey]; this
0x140022f05  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x140022f0a  mov     [rsp+2300h+hKey], r12
0x140022f0f  test    r14d, r14d
0x140022f12  jnz     short loc_140022F50
0x140022f14  mov     rdx, rdi; wchar_t *
0x140022f17  mov     rcx, rsi; this
0x140022f1a  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140022f1f  mov     ebx, eax
0x140022f21  xor     r14d, r14d
0x140022f24  test    eax, eax
0x140022f26  js      loc_1400233CD
0x140022f2c  mov     rdx, rdi; wchar_t *
0x140022f2f  mov     rcx, rsi; this
0x140022f32  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x140022f37  mov     ebx, eax
0x140022f39  test    eax, eax
0x140022f3b  lea     rcx, [rsp+2300h+hKey]; this
0x140022f40  js      loc_1400233D2
0x140022f46  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140022f4b  jmp     loc_140023174
0x140022f50  lea     rcx, [rsp+2300h+hKey]; this
0x140022f55  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140022f5a  mov     r12d, 1
0x140022f60  lea     rdx, aNoremove; "NoRemove"
0x140022f67  mov     rcx, rdi; lpString1
0x140022f6a  call    cs:__imp_lstrcmpiW
0x140022f70  xor     r14d, r14d
0x140022f73  test    eax, eax
0x140022f75  jnz     short loc_140022F8F
0x140022f77  mov     r12d, r14d
0x140022f7a  mov     rdx, rdi; wchar_t *
0x140022f7d  mov     rcx, rsi; this
0x140022f80  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140022f85  mov     ebx, eax
0x140022f87  test    eax, eax
0x140022f89  js      loc_140023395
0x140022f8f  lea     rdx, aVal; "Val"
0x140022f96  mov     rcx, rdi; lpString1
0x140022f99  call    cs:__imp_lstrcmpiW
0x140022f9f  test    eax, eax
0x140022fa1  jnz     loc_140023088
0x140022fa7  lea     rdx, [rbp+2200h+ValueName]; wchar_t *
0x140022fae  mov     rcx, rsi; this
0x140022fb1  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140022fb6  mov     ebx, eax
0x140022fb8  test    eax, eax
0x140022fba  js      loc_140023395
0x140022fc0  mov     rdx, rdi; wchar_t *
0x140022fc3  mov     rcx, rsi; this
0x140022fc6  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140022fcb  mov     ebx, eax
0x140022fcd  test    eax, eax
0x140022fcf  js      loc_140023395
0x140022fd5  cmp     word ptr [rdi], 3Dh ; '='
0x140022fd9  jnz     loc_140023390
0x140022fdf  test    r15d, r15d
0x140022fe2  jz      short loc_140023016
0x140022fe4  mov     [rsp+2300h+var_22A0], r14
0x140022fe9  mov     [rsp+2300h+var_2298], r14
0x140022fee  mov     [rsp+2300h+hKey], r13
0x140022ff3  mov     r9, rdi; wchar_t *
0x140022ff6  lea     r8, [rbp+2200h+ValueName]; wchar_t *
0x140022ffd  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x140023002  mov     rcx, rsi; this
0x140023005  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x14002300a  mov     ebx, eax
0x14002300c  mov     [rsp+2300h+hKey], r14
0x140023011  jmp     loc_140022F39
0x140023016  cmp     [rbp+2200h+arg_20], r14d
0x14002301d  jnz     short loc_140023078
0x14002301f  test    r12d, r12d
0x140023022  jz      short loc_140023078
0x140023024  mov     [rsp+2300h+hKey], r14
0x140023029  mov     [rsp+2300h+var_22A0], r14
0x14002302e  mov     [rsp+2300h+var_2298], r14
0x140023033  mov     r9d, 20006h; unsigned int
0x140023039  xor     r8d, r8d; lpSubKey
0x14002303c  mov     rdx, r13; hKey
0x14002303f  lea     rcx, [rsp+2300h+hKey]; this
0x140023044  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x140023049  test    eax, eax
0x14002304b  jnz     loc_1400233C4
0x140023051  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x140023058  mov     rcx, [rsp+2300h+hKey]; hKey
0x14002305d  call    cs:__imp_RegDeleteValueW
0x140023063  test    eax, 0FFFFFFFDh
0x140023068  jnz     loc_1400233C4
0x14002306e  lea     rcx, [rsp+2300h+hKey]; this
0x140023073  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140023078  mov     rdx, rdi; wchar_t *
0x14002307b  mov     rcx, rsi; this
0x14002307e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x140023083  jmp     loc_140022E62
0x140023088  mov     edx, 5Ch ; '\'; wchar_t
0x14002308d  mov     rcx, rdi; lpsz
0x140023090  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x140023095  test    rax, rax
0x140023098  jnz     loc_140023390
0x14002309e  test    r15d, r15d
0x1400230a1  jz      loc_1400231C3
0x1400230a7  mov     ebx, 2001Fh
0x1400230ac  mov     r9d, ebx; unsigned int
0x1400230af  mov     r8, rdi; lpSubKey
0x1400230b2  mov     rdx, r13; hKey
0x1400230b5  lea     rcx, [rsp+2300h+var_2290]; this
0x1400230ba  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1400230bf  test    eax, eax
0x1400230c1  jz      short loc_14002313C
0x1400230c3  lea     r9d, [rbx-6]; unsigned int
0x1400230c7  mov     r8, rdi; lpSubKey
0x1400230ca  mov     rdx, r13; hKey
0x1400230cd  lea     rcx, [rsp+2300h+var_2290]; this
0x1400230d2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1400230d7  test    eax, eax
0x1400230d9  jz      short loc_14002313C
0x1400230db  mov     [rbp+2200h+dwDisposition], r14d
0x1400230df  mov     [rbp+2200h+var_2270], r14
0x1400230e3  lea     rax, [rbp+2200h+dwDisposition]
0x1400230e7  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x1400230ec  lea     rax, [rbp+2200h+var_2270]
0x1400230f0  mov     [rsp+2300h+phkResult], rax; phkResult
0x1400230f5  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1400230fa  mov     [rsp+2300h+samDesired], ebx; samDesired
0x1400230fe  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x140023103  xor     r9d, r9d; lpClass
0x140023106  xor     r8d, r8d; Reserved
0x140023109  mov     rdx, rdi; lpSubKey
0x14002310c  mov     rcx, r13; hKey
0x14002310f  call    cs:__imp_RegCreateKeyExW
0x140023115  mov     ecx, eax
0x140023117  test    eax, eax
0x140023119  jnz     loc_1400232C3
0x14002311f  lea     rcx, [rsp+2300h+var_2290]; this
0x140023124  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140023129  mov     ecx, eax
0x14002312b  mov     rax, [rbp+2200h+var_2270]
0x14002312f  mov     [rsp+2300h+var_2290], rax
0x140023134  test    ecx, ecx
0x140023136  jnz     loc_1400232C3
0x14002313c  mov     rdx, rdi; wchar_t *
0x14002313f  mov     rcx, rsi; this
0x140023142  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140023147  mov     ebx, eax
0x140023149  test    eax, eax
0x14002314b  js      loc_140023395
0x140023151  cmp     word ptr [rdi], 3Dh ; '='
0x140023155  jnz     short loc_140023174
0x140023157  mov     r9, rdi; wchar_t *
0x14002315a  xor     r8d, r8d; wchar_t *
0x14002315d  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x140023162  mov     rcx, rsi; this
0x140023165  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x14002316a  mov     ebx, eax
0x14002316c  test    eax, eax
0x14002316e  js      loc_140023395
0x140023174  cmp     word ptr [rdi], 7Bh ; '{'
0x140023178  jnz     loc_140022E6C
0x14002317e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140023182  inc     rax
0x140023185  cmp     [rdi+rax*2], r14w
0x14002318a  jnz     short loc_140023182
0x14002318c  cmp     rax, 1
0x140023190  jnz     loc_140022E6C
0x140023196  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x14002319b  mov     r9d, r15d; int
0x14002319e  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1400231a3  mov     rdx, rdi; wchar_t *
0x1400231a6  mov     rcx, rsi; this
0x1400231a9  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x1400231ae  mov     ebx, eax
0x1400231b0  test    eax, eax
0x1400231b2  js      loc_140023395
0x1400231b8  mov     rdx, rdi
0x1400231bb  mov     rcx, rsi
0x1400231be  jmp     loc_140022E5D
0x1400231c3  cmp     [rbp+2200h+arg_20], r14d
0x1400231ca  jnz     short loc_1400231E7
0x1400231cc  mov     r9d, 20019h; unsigned int
0x1400231d2  mov     r8, rdi; lpSubKey
0x1400231d5  mov     rdx, r13; hKey
0x1400231d8  lea     rcx, [rsp+2300h+var_2290]; this
0x1400231dd  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1400231e2  mov     r14d, eax
0x1400231e5  jmp     short loc_1400231ED
0x1400231e7  mov     r14d, 2
0x1400231ed  mov     r15d, 1
0x1400231f3  test    r14d, r14d
0x1400231f6  cmovz   r15d, [rbp+2200h+arg_20]
0x1400231fe  or      r9, 0FFFFFFFFFFFFFFFFh
0x140023202  mov     r8, rdi
0x140023205  mov     edx, 104h
0x14002320a  lea     rcx, [rbp+2200h+var_2260]
0x14002320e  call    cs:__imp__o_wcsncpy_s
0x140023214  mov     ecx, eax; int
0x140023216  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14002321b  mov     rdx, rdi; wchar_t *
0x14002321e  mov     rcx, rsi; this
0x140023221  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140023226  mov     ebx, eax
0x140023228  test    eax, eax
0x14002322a  js      loc_140023395
0x140023230  mov     rdx, rdi; wchar_t *
0x140023233  mov     rcx, rsi; this
0x140023236  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x14002323b  mov     ebx, eax
0x14002323d  xor     ecx, ecx
0x14002323f  test    eax, eax
0x140023241  js      loc_140023395
0x140023247  cmp     word ptr [rdi], 7Bh ; '{'
0x14002324b  jnz     short loc_14002329C
0x14002324d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140023251  inc     rax
0x140023254  cmp     [rdi+rax*2], cx
0x140023258  jnz     short loc_140023251
0x14002325a  cmp     rax, 1
0x14002325e  jnz     short loc_14002329C
0x140023260  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x140023265  xor     r9d, r9d; int
0x140023268  mov     r8, [rsp+2300h+var_2290]; HKEY
0x14002326d  mov     rdx, rdi; wchar_t *
0x140023270  mov     rcx, rsi; this
0x140023273  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x140023278  mov     ebx, eax
0x14002327a  test    eax, eax
0x14002327c  jns     short loc_140023287
0x14002327e  test    r15d, r15d
0x140023281  jz      loc_140023395
0x140023287  mov     rdx, rdi; wchar_t *
0x14002328a  mov     rcx, rsi; this
0x14002328d  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140023292  mov     ebx, eax
0x140023294  test    eax, eax
0x140023296  js      loc_140023395
0x14002329c  cmp     r14d, 2
  ... truncated ...
```
