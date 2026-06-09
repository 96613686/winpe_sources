# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x18000d0b8`
- end: `0x18000d649`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1425`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x18000ccfc`
- `0x18000d0b8`

## callees

- `0x180002300`
- `0x18000b29c`
- `0x18000b9a4`
- `0x18000ba14`
- `0x18000be6c`
- `0x18000bf84`
- `0x18000bfb0`
- `0x18000c2bc`
- `0x18000c5c8`
- `0x18000c740`
- `0x18000c8a0`
- `0x18000cbe8`
- `0x18000d0b8`
- `0x18000d860`
- `0x18000d930`
- `0x18003a060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000d476`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000d476`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000d134`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000d147`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000d21b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000d24a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000d134`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000d147`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000d21b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000d24a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000d30e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000d30e`

## string_xrefs

- `0x18000d13d`: `ForceRemove`
- `0x18000d211`: `NoRemove`
- `0x18000d12a`: `Delete`

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
  unsigned int v15; // eax
  wchar_t *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int HasSubKeys; // r14d
  unsigned int v27; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+58h] [rbp-A8h]
  HKEY v32[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v33[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v32, 0, 24);
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_78;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_78;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_78;
        if ( !v5 )
          break;
        hKey = 0;
        v30 = 0;
        v31 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_77:
          v10 = -2147352567;
          goto LABEL_78;
        }
        if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          hKey = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
          hKey = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_80;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v32[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_78;
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
          goto LABEL_78;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_77;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v32, a3, v7, v16, v27)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v32, 0, v7);
            if ( v10 < 0 )
              goto LABEL_78;
          }
          goto LABEL_40;
        }
LABEL_81:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_78;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v33, 260, v7, -1);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_78;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_78;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v32[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_78;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
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
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v32[0]) )
        {
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v22, v33) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v32, v33);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v32[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v32);
          if ( v17 )
            goto LABEL_81;
          if ( v14 && !HasSubKeys )
          {
            v30 = 0;
            v31 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v33);
            hKey = 0;
            if ( v15 )
              goto LABEL_79;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_78;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_78;
    if ( *v7 != 61 )
      goto LABEL_77;
    if ( v5 )
    {
      v30 = 0;
      v31 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v30 = 0;
    v31 = 0;
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
LABEL_79:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
  ATL::CRegKey::Close((ATL::CRegKey *)v32);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000d0b8  push    rbp
0x18000d0ba  push    rbx
0x18000d0bb  push    rsi
0x18000d0bc  push    rdi
0x18000d0bd  push    r12
0x18000d0bf  push    r13
0x18000d0c1  push    r14
0x18000d0c3  push    r15
0x18000d0c5  lea     rbp, [rsp-21A8h]
0x18000d0cd  mov     eax, 22A8h
0x18000d0d2  call    _alloca_probe
0x18000d0d7  sub     rsp, rax
0x18000d0da  mov     rax, cs:__security_cookie
0x18000d0e1  xor     rax, rsp
0x18000d0e4  mov     [rbp+21E0h+var_50], rax
0x18000d0eb  mov     r15d, r9d
0x18000d0ee  mov     [rsp+22E0h+var_22A0], r9d
0x18000d0f3  mov     r13, r8
0x18000d0f6  mov     rdi, rdx
0x18000d0f9  mov     rsi, rcx
0x18000d0fc  xor     r14d, r14d
0x18000d0ff  mov     [rsp+22E0h+var_2280], r14
0x18000d104  mov     [rsp+22E0h+var_2278], r14
0x18000d109  mov     [rsp+22E0h+var_2270], r14
0x18000d10e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000d113  test    eax, eax
0x18000d115  mov     ebx, eax
0x18000d117  js      loc_18000D5FD
0x18000d11d  xor     r12d, r12d
0x18000d120  cmp     word ptr [rdi], 7Dh ; '}'
0x18000d124  jz      loc_18000D5FD
0x18000d12a  lea     rdx, String2; "Delete"
0x18000d131  mov     rcx, rdi; lpString1
0x18000d134  call    cs:__imp_lstrcmpiW
0x18000d13a  mov     r14d, eax
0x18000d13d  lea     rdx, aForceremove; "ForceRemove"
0x18000d144  mov     rcx, rdi; lpString1
0x18000d147  call    cs:__imp_lstrcmpiW
0x18000d14d  test    eax, eax
0x18000d14f  jz      short loc_18000D15A
0x18000d151  test    r14d, r14d
0x18000d154  jnz     loc_18000D20B
0x18000d15a  mov     rdx, rdi; wchar_t *
0x18000d15d  mov     rcx, rsi; this
0x18000d160  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000d165  mov     ebx, eax
0x18000d167  test    eax, eax
0x18000d169  js      loc_18000D5FD
0x18000d16f  test    r15d, r15d
0x18000d172  jz      loc_18000D20B
0x18000d178  mov     [rsp+22E0h+hKey], r12
0x18000d17d  mov     [rsp+22E0h+var_2290], r12
0x18000d182  mov     [rsp+22E0h+var_2288], r12
0x18000d187  mov     edx, 5Ch ; '\'; wchar_t
0x18000d18c  mov     rcx, rdi; lpsz
0x18000d18f  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18000d194  test    rax, rax
0x18000d197  jnz     loc_18000D5EE
0x18000d19d  mov     rdx, rdi; wchar_t *
0x18000d1a0  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x18000d1a5  test    eax, eax
0x18000d1a7  jz      short loc_18000D1C0
0x18000d1a9  mov     [rsp+22E0h+hKey], r13
0x18000d1ae  mov     rdx, rdi; wchar_t *
0x18000d1b1  lea     rcx, [rsp+22E0h+hKey]; this
0x18000d1b6  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18000d1bb  mov     [rsp+22E0h+hKey], r12
0x18000d1c0  test    r14d, r14d
0x18000d1c3  jnz     short loc_18000D201
0x18000d1c5  mov     rdx, rdi; wchar_t *
0x18000d1c8  mov     rcx, rsi; this
0x18000d1cb  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000d1d0  mov     ebx, eax
0x18000d1d2  xor     r14d, r14d
0x18000d1d5  test    eax, eax
0x18000d1d7  js      loc_18000D635
0x18000d1dd  mov     rdx, rdi; wchar_t *
0x18000d1e0  mov     rcx, rsi; this
0x18000d1e3  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18000d1e8  mov     ebx, eax
0x18000d1ea  test    eax, eax
0x18000d1ec  lea     rcx, [rsp+22E0h+hKey]; this
0x18000d1f1  js      loc_18000D63A
0x18000d1f7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d1fc  jmp     loc_18000D3DC
0x18000d201  lea     rcx, [rsp+22E0h+hKey]; this
0x18000d206  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d20b  mov     r12d, 1
0x18000d211  lea     rdx, aNoremove; "NoRemove"
0x18000d218  mov     rcx, rdi; lpString1
0x18000d21b  call    cs:__imp_lstrcmpiW
0x18000d221  xor     r14d, r14d
0x18000d224  test    eax, eax
0x18000d226  jnz     short loc_18000D240
0x18000d228  mov     r12d, r14d
0x18000d22b  mov     rdx, rdi; wchar_t *
0x18000d22e  mov     rcx, rsi; this
0x18000d231  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000d236  mov     ebx, eax
0x18000d238  test    eax, eax
0x18000d23a  js      loc_18000D5FD
0x18000d240  lea     rdx, aVal; "Val"
0x18000d247  mov     rcx, rdi; lpString1
0x18000d24a  call    cs:__imp_lstrcmpiW
0x18000d250  test    eax, eax
0x18000d252  jnz     loc_18000D339
0x18000d258  lea     rdx, [rbp+21E0h+ValueName]; wchar_t *
0x18000d25f  mov     rcx, rsi; this
0x18000d262  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000d267  mov     ebx, eax
0x18000d269  test    eax, eax
0x18000d26b  js      loc_18000D5FD
0x18000d271  mov     rdx, rdi; wchar_t *
0x18000d274  mov     rcx, rsi; this
0x18000d277  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000d27c  mov     ebx, eax
0x18000d27e  test    eax, eax
0x18000d280  js      loc_18000D5FD
0x18000d286  cmp     word ptr [rdi], 3Dh ; '='
0x18000d28a  jnz     loc_18000D5F8
0x18000d290  test    r15d, r15d
0x18000d293  jz      short loc_18000D2C7
0x18000d295  mov     [rsp+22E0h+var_2290], r14
0x18000d29a  mov     [rsp+22E0h+var_2288], r14
0x18000d29f  mov     [rsp+22E0h+hKey], r13
0x18000d2a4  mov     r9, rdi; wchar_t *
0x18000d2a7  lea     r8, [rbp+21E0h+ValueName]; wchar_t *
0x18000d2ae  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18000d2b3  mov     rcx, rsi; this
0x18000d2b6  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18000d2bb  mov     ebx, eax
0x18000d2bd  mov     [rsp+22E0h+hKey], r14
0x18000d2c2  jmp     loc_18000D1EA
0x18000d2c7  cmp     [rbp+21E0h+arg_20], r14d
0x18000d2ce  jnz     short loc_18000D329
0x18000d2d0  test    r12d, r12d
0x18000d2d3  jz      short loc_18000D329
0x18000d2d5  mov     [rsp+22E0h+hKey], r14
0x18000d2da  mov     [rsp+22E0h+var_2290], r14
0x18000d2df  mov     [rsp+22E0h+var_2288], r14
0x18000d2e4  mov     r9d, 20006h; unsigned int
0x18000d2ea  xor     r8d, r8d; lpSubKey
0x18000d2ed  mov     rdx, r13; hKey
0x18000d2f0  lea     rcx, [rsp+22E0h+hKey]; this
0x18000d2f5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000d2fa  test    eax, eax
0x18000d2fc  jnz     loc_18000D62C
0x18000d302  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18000d309  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18000d30e  call    cs:__imp_RegDeleteValueW
0x18000d314  test    eax, 0FFFFFFFDh
0x18000d319  jnz     loc_18000D62C
0x18000d31f  lea     rcx, [rsp+22E0h+hKey]; this
0x18000d324  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d329  mov     rdx, rdi; wchar_t *
0x18000d32c  mov     rcx, rsi; this
0x18000d32f  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18000d334  jmp     loc_18000D113
0x18000d339  mov     edx, 5Ch ; '\'; wchar_t
0x18000d33e  mov     rcx, rdi; lpsz
0x18000d341  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18000d346  test    rax, rax
0x18000d349  jnz     loc_18000D5F8
0x18000d34f  test    r15d, r15d
0x18000d352  jz      loc_18000D42B
0x18000d358  mov     r9d, 2001Fh; unsigned int
0x18000d35e  mov     r8, rdi; lpSubKey
0x18000d361  mov     rdx, r13; hKey
0x18000d364  lea     rcx, [rsp+22E0h+var_2280]; this
0x18000d369  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000d36e  test    eax, eax
0x18000d370  jz      short loc_18000D3A4
0x18000d372  mov     r9d, 20019h; unsigned int
0x18000d378  mov     r8, rdi; lpSubKey
0x18000d37b  mov     rdx, r13; hKey
0x18000d37e  lea     rcx, [rsp+22E0h+var_2280]; this
0x18000d383  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000d388  test    eax, eax
0x18000d38a  jz      short loc_18000D3A4
0x18000d38c  mov     r8, rdi; lpSubKey
0x18000d38f  mov     rdx, r13; hKey
0x18000d392  lea     rcx, [rsp+22E0h+var_2280]; this
0x18000d397  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WPEA_WKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,wchar_t const *,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000d39c  test    eax, eax
0x18000d39e  jnz     loc_18000D641
0x18000d3a4  mov     rdx, rdi; wchar_t *
0x18000d3a7  mov     rcx, rsi; this
0x18000d3aa  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000d3af  mov     ebx, eax
0x18000d3b1  test    eax, eax
0x18000d3b3  js      loc_18000D5FD
0x18000d3b9  cmp     word ptr [rdi], 3Dh ; '='
0x18000d3bd  jnz     short loc_18000D3DC
0x18000d3bf  mov     r9, rdi; wchar_t *
0x18000d3c2  xor     r8d, r8d; wchar_t *
0x18000d3c5  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18000d3ca  mov     rcx, rsi; this
0x18000d3cd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18000d3d2  mov     ebx, eax
0x18000d3d4  test    eax, eax
0x18000d3d6  js      loc_18000D5FD
0x18000d3dc  cmp     word ptr [rdi], 7Bh ; '{'
0x18000d3e0  jnz     loc_18000D11D
0x18000d3e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d3ea  inc     rax
0x18000d3ed  cmp     [rdi+rax*2], r14w
0x18000d3f2  jnz     short loc_18000D3EA
0x18000d3f4  cmp     rax, 1
0x18000d3f8  jnz     loc_18000D11D
0x18000d3fe  mov     [rsp+22E0h+var_22C0], r14d; int
0x18000d403  mov     r9d, r15d; int
0x18000d406  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18000d40b  mov     rdx, rdi; wchar_t *
0x18000d40e  mov     rcx, rsi; this
0x18000d411  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000d416  mov     ebx, eax
0x18000d418  test    eax, eax
0x18000d41a  js      loc_18000D5FD
0x18000d420  mov     rdx, rdi
0x18000d423  mov     rcx, rsi
0x18000d426  jmp     loc_18000D10E
0x18000d42b  cmp     [rbp+21E0h+arg_20], r14d
0x18000d432  jnz     short loc_18000D44F
0x18000d434  mov     r9d, 20019h; unsigned int
0x18000d43a  mov     r8, rdi; lpSubKey
0x18000d43d  mov     rdx, r13; hKey
0x18000d440  lea     rcx, [rsp+22E0h+var_2280]; this
0x18000d445  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000d44a  mov     r14d, eax
0x18000d44d  jmp     short loc_18000D455
0x18000d44f  mov     r14d, 2
0x18000d455  mov     r15d, 1
0x18000d45b  test    r14d, r14d
0x18000d45e  cmovz   r15d, [rbp+21E0h+arg_20]
0x18000d466  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000d46a  mov     r8, rdi
0x18000d46d  mov     edx, 104h
0x18000d472  lea     rcx, [rbp+21E0h+var_2260]
0x18000d476  call    cs:__imp__o_wcsncpy_s
0x18000d47c  mov     ecx, eax; int
0x18000d47e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000d483  mov     rdx, rdi; wchar_t *
0x18000d486  mov     rcx, rsi; this
0x18000d489  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000d48e  mov     ebx, eax
0x18000d490  test    eax, eax
0x18000d492  js      loc_18000D5FD
0x18000d498  mov     rdx, rdi; wchar_t *
0x18000d49b  mov     rcx, rsi; this
0x18000d49e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18000d4a3  mov     ebx, eax
0x18000d4a5  xor     ecx, ecx
0x18000d4a7  test    eax, eax
0x18000d4a9  js      loc_18000D5FD
0x18000d4af  cmp     word ptr [rdi], 7Bh ; '{'
0x18000d4b3  jnz     short loc_18000D504
0x18000d4b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d4b9  inc     rax
0x18000d4bc  cmp     [rdi+rax*2], cx
0x18000d4c0  jnz     short loc_18000D4B9
0x18000d4c2  cmp     rax, 1
0x18000d4c6  jnz     short loc_18000D504
0x18000d4c8  mov     [rsp+22E0h+var_22C0], r15d; int
0x18000d4cd  xor     r9d, r9d; int
0x18000d4d0  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18000d4d5  mov     rdx, rdi; wchar_t *
0x18000d4d8  mov     rcx, rsi; this
0x18000d4db  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000d4e0  mov     ebx, eax
0x18000d4e2  test    eax, eax
0x18000d4e4  jns     short loc_18000D4EF
0x18000d4e6  test    r15d, r15d
0x18000d4e9  jz      loc_18000D5FD
0x18000d4ef  mov     rdx, rdi; wchar_t *
0x18000d4f2  mov     rcx, rsi; this
0x18000d4f5  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000d4fa  mov     ebx, eax
0x18000d4fc  test    eax, eax
0x18000d4fe  js      loc_18000D5FD
0x18000d504  cmp     r14d, 2
0x18000d508  mov     r15d, [rsp+22E0h+var_22A0]
0x18000d50d  jz      loc_18000D11D
0x18000d513  test    r14d, r14d
0x18000d516  jz      short loc_18000D537
0x18000d518  xor     r12d, r12d
0x18000d51b  cmp     [rbp+21E0h+arg_20], r12d
0x18000d522  jnz     loc_18000D120
0x18000d528  mov     ecx, r14d; unsigned int
0x18000d52b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000d530  mov     ebx, eax
0x18000d532  jmp     loc_18000D5FD
0x18000d537  xor     r14d, r14d
0x18000d53a  cmp     [rbp+21E0h+arg_20], r14d
0x18000d541  jz      short loc_18000D581
0x18000d543  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x18000d548  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x18000d54d  test    eax, eax
0x18000d54f  jz      short loc_18000D581
0x18000d551  lea     rdx, [rbp+21E0h+var_2260]; wchar_t *
0x18000d555  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
  ... truncated ...
```
