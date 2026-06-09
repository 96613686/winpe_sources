# CSecurityManager::SetZoneMapping(ulong,ushort const *,ulong)

- ea: `0x18003a370`
- end: `0x18003ab73`
- name: `?SetZoneMapping@CSecurityManager@@UEAAJKPEBGK@Z`
- size: `2051`
- prototype: `__int64 __fastcall(CSecurityManager *__hidden this, unsigned int, LPCWSTR pwzURI, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180011c70`
- `0x180014600`
- `0x1800342d0`
- `0x180034300`
- `0x180038ca0`
- `0x18003a370`
- `0x18003b010`
- `0x180056d60`
- `0x180056ed0`
- `0x180066f40`
- `0x18007a624`
- `0x18007d64c`
- `0x18008d850`
- `0x1800fda88`
- `0x1800feca8`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x18003a471`
- `iertutil!CreateUri` at `0x18003a471`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x18003a703`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x18003a837`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x18003a703`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x18003a837`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18003a84a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18003a84a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa5a`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003a7cd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003a7cd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003a9dc`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003aa00`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003a9dc`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003aa00`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteEmptyUSKeyW` at `0x18003a825`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteEmptyUSKeyW` at `0x18003a8c7`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteEmptyUSKeyW` at `0x18003a825`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteEmptyUSKeyW` at `0x18003a8c7`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003a989`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003aa85`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003aa9f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003aaf6`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003ab10`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003a989`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003aa85`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003aa9f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003aaf6`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003ab10`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCreateUSKeyW` at `0x18003a94d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCreateUSKeyW` at `0x18003a94d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a52a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aab4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a52a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aab4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab25`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a534`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a53e`
- `OLEAUT32!__imp_SysFreeString` at `0x18003aabe`
- `OLEAUT32!__imp_SysFreeString` at `0x18003aac8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ab2f`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ab39`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a534`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a53e`
- `OLEAUT32!__imp_SysFreeString` at `0x18003aabe`
- `OLEAUT32!__imp_SysFreeString` at `0x18003aac8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ab2f`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ab39`

## pseudocode

```c
__int64 __fastcall CSecurityManager::SetZoneMapping(
        CSecurityManager *this,
        unsigned int a2,
        LPCWSTR pwzURI,
        unsigned int a4)
{
  int SecurityUrl; // edi
  __int64 v9; // rcx
  int v10; // eax
  BOOL v11; // r14d
  unsigned int v12; // r13d
  DWORD v13; // eax
  IUri *v14; // rbx
  struct IUri *v15; // rbx
  unsigned int v16; // r8d
  int v18; // edx
  BOOL v19; // r9d
  PWSTR v20; // rdx
  __int64 v21; // rax
  __int64 v22; // r9
  unsigned int i; // r8d
  __int64 v24; // rcx
  WCHAR v25; // ax
  LSTATUS v26; // eax
  bool v27; // cc
  PWSTR v28; // rdi
  PWSTR v29; // rax
  void *v30; // rdx
  int v31; // r9d
  void *v32; // r8
  void *v33; // rdi
  BOOL v34; // eax
  signed int LastError; // eax
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned int *v37; // [rsp+38h] [rbp-C8h] BYREF
  HUSKEY hUSKey; // [rsp+40h] [rbp-C0h]
  BOOL fIgnoreHKCU; // [rsp+48h] [rbp-B8h]
  int v40; // [rsp+4Ch] [rbp-B4h]
  int v41; // [rsp+50h] [rbp-B0h]
  HUSKEY phNewUSKey; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned int *v43; // [rsp+60h] [rbp-A0h] BYREF
  HUSKEY v44; // [rsp+68h] [rbp-98h]
  int v45; // [rsp+70h] [rbp-90h]
  int v46; // [rsp+74h] [rbp-8Ch]
  int v47; // [rsp+78h] [rbp-88h]
  IUri *ppURI; // [rsp+80h] [rbp-80h] BYREF
  IUri *ppSecUri; // [rsp+88h] [rbp-78h] BYREF
  int v50; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR pwzValue; // [rsp+98h] [rbp-68h]
  LPVOID pv; // [rsp+A0h] [rbp-60h]
  BSTR bstrString; // [rsp+B8h] [rbp-48h]
  BSTR v54; // [rsp+C0h] [rbp-40h]
  int v55; // [rsp+CCh] [rbp-34h]
  int v56; // [rsp+DCh] [rbp-24h]
  char v57; // [rsp+E4h] [rbp-1Ch]
  int v58; // [rsp+F8h] [rbp-8h]
  int v59; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v60[1468]; // [rsp+584h] [rbp+484h] BYREF
  WCHAR pszStart[264]; // [rsp+B40h] [rbp+A40h] BYREF

  CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 4u);
  if ( *((_QWORD *)this + 12) )
    return (unsigned int)-2147024891;
  v9 = *((_QWORD *)this + 11);
  if ( v9 || (v9 = *((_QWORD *)this + 10)) != 0 || (v9 = *((_QWORD *)this + 9)) != 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPCWSTR, _QWORD))(*(_QWORD *)v9 + 72LL))(v9, a2, pwzURI, a4);
    SecurityUrl = v10;
    if ( v10 != -2146697199 )
    {
      if ( !v10 )
        CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 0x14u);
      return (unsigned int)SecurityUrl;
    }
  }
  v11 = (a2 & 0x100) != 0 && a2 <= 0x3E7;
  ppURI = 0;
  v12 = a2 & 0xFFFFFEFF;
  ppSecUri = 0;
  if ( !v11 )
    v12 = a2;
  v13 = HelperAddUriDefaultFlags(0x3002B80u, 6u);
  SecurityUrl = CreateUri(pwzURI, v13, 0, &ppURI);
  if ( SecurityUrl < 0 )
    return (unsigned int)SecurityUrl;
  v14 = ppURI;
  SecurityUrl = CoInternetGetSecurityUrlEx(ppURI, &ppSecUri, PSU_DEFAULT, 0);
  ((void (__fastcall *)(IUri *))v14->lpVtbl->Release)(v14);
  if ( SecurityUrl < 0 )
    return (unsigned int)SecurityUrl;
  v15 = ppSecUri;
  memset_0(&v50, 0, 0x4E8u);
  SecurityUrl = ZONEMAP_COMPONENTS::Crack((ZONEMAP_COMPONENTS *)&v50, v15, v16, 1);
  if ( SecurityUrl )
    goto LABEL_18;
  memset_0(v60, 0, 0x5B0u);
  v59 = 1460;
  if ( (unsigned int)CSecurityManager::EnsureZoneManager(this) )
  {
    v18 = CSecurityManager::s_fESCEnabled;
    if ( (!v11 || v12 != 2 || CSecurityManager::s_fESCEnabled) && (a4 & 1) == 0 )
    {
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)this + 8) + 24LL))(
             *((_QWORD *)this + 8),
             v12,
             &v59) >= 0
        && (v60[1452] & 4) != 0
        && v50 != 11 )
      {
        ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)&v50);
        ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
        return 2147942405LL;
      }
      v18 = CSecurityManager::s_fESCEnabled;
    }
    if ( (v57 & 2) != 0 )
    {
      SecurityUrl = CSecurityManager::AddDeleteIPRule(this, (struct ZONEMAP_COMPONENTS *)&v50, v12, a4);
LABEL_18:
      ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)&v50);
LABEL_19:
      ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
      return (unsigned int)SecurityUrl;
    }
    if ( v58 )
    {
      ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)&v50);
      ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
      return 2147942487LL;
    }
    v37 = &CRegKey::`vftable';
    v43 = &CRegKey::`vftable';
    fIgnoreHKCU = g_bUseHKLMOnly;
    hUSKey = 0;
    v41 = 0;
    v40 = CSecurityManager::s_fUsePoliciesZoneMap;
    v45 = g_bUseHKLMOnly;
    v44 = 0;
    v47 = 0;
    v46 = CSecurityManager::s_fUsePoliciesZoneMap;
    if ( (a4 & 1) != 0 )
    {
      v19 = v11 || v18;
      SecurityUrl = CSecurityManager::GetDomainKeyNameForDeleting(
                      (const struct ZONEMAP_COMPONENTS *)&v50,
                      pszStart,
                      (unsigned int)&CRegKey::`vftable',
                      v19);
      if ( SecurityUrl < 0 )
      {
LABEL_43:
        v43 = &CRegKey::`vftable';
        CRegKey::Close((CRegKey *)&v43);
        v37 = &CRegKey::`vftable';
        CRegKey::Close((CRegKey *)&v37);
        goto LABEL_18;
      }
      if ( CRegKey::Open((CRegKey *)&v37, *((void **)this + 14), pszStart, 0x2001Fu) == 2 )
      {
        if ( v55 == 1 && *(_WORD *)pv == 42 )
        {
          v20 = StrRChrW(pszStart, 0, 0x5Cu);
          if ( v20 )
          {
            v21 = -1;
            do
              ++v21;
            while ( v20[v21] );
            if ( (unsigned int)v21 > 1 && v20[1] == 42 )
            {
              v22 = (unsigned int)(v21 - 2);
              for ( i = 1; i < (unsigned int)v22; v20[v24] = v25 )
              {
                v24 = i;
                v25 = v20[i + 2];
                ++i;
              }
              v20[v22] = 0;
            }
          }
        }
        if ( CRegKey::Open((CRegKey *)&v37, *((void **)this + 14), pszStart, 0x2001Fu) == 2 )
        {
LABEL_56:
          v43 = &CRegKey::`vftable';
          CRegKey::Close((CRegKey *)&v43);
          v37 = &CRegKey::`vftable';
          CRegKey::Close((CRegKey *)&v37);
          ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)&v50);
          ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
          return 0;
        }
      }
      v26 = SHRegDeleteUSValueW(hUSKey, pwzValue, (SHREGDEL_FLAGS)(fIgnoreHKCU ? SHREGDEL_HKLM : SHREGDEL_HKCU));
      SecurityUrl = v26;
      v27 = v26 <= 0;
      if ( !v26 )
      {
        v36 = 0;
        if ( !CRegKey::QuerySubKeyInfo((CRegKey *)&v37, 0, 0, &v36) && !v36 )
        {
          CRegKey::Close((CRegKey *)&v37);
          SHRegDeleteEmptyUSKeyW(
            *((HUSKEY *)this + 14),
            pszStart,
            (SHREGDEL_FLAGS)(*((_DWORD *)this + 30) != 0 ? SHREGDEL_HKLM : SHREGDEL_HKCU));
        }
        v28 = StrRChrW(pszStart, 0, 0x5Cu);
        v29 = StrChrW(pszStart, 0x5Cu);
        if ( v28 )
        {
          if ( v29 )
          {
            if ( v28 != v29 )
            {
              *v28 = 0;
              v30 = (void *)*((_QWORD *)this + 14);
              v36 = 0;
              if ( !CRegKey::Open((CRegKey *)&v43, v30, pszStart, 0x2001Fu)
                && !CRegKey::QuerySubKeyInfo((CRegKey *)&v43, 0, 0, &v36)
                && !v36 )
              {
                CRegKey::Close((CRegKey *)&v43);
                SHRegDeleteEmptyUSKeyW(
                  *((HUSKEY *)this + 14),
                  pszStart,
                  (SHREGDEL_FLAGS)(*((_DWORD *)this + 30) != 0 ? SHREGDEL_HKLM : SHREGDEL_HKCU));
              }
            }
          }
        }
        goto LABEL_68;
      }
LABEL_69:
      if ( !v27 )
      {
        SecurityUrl = (unsigned __int16)v26;
LABEL_99:
        SecurityUrl |= 0x80070000;
        goto LABEL_100;
      }
      goto LABEL_100;
    }
    if ( v11 || (v31 = 0, v18) )
      v31 = 1;
    SecurityUrl = CSecurityManager::GetDomainKeyNameForAdding(
                    (const struct ZONEMAP_COMPONENTS *)&v50,
                    pszStart,
                    (unsigned int)&CRegKey::`vftable',
                    v31);
    if ( SecurityUrl < 0 )
      goto LABEL_43;
    v32 = (void *)*((_QWORD *)this + 14);
    phNewUSKey = 0;
    SecurityUrl = SHRegCreateUSKeyW(pszStart, 0x2001Fu, v32, &phNewUSKey, fIgnoreHKCU ? 8 : 2);
    if ( SecurityUrl
      || (SecurityUrl = (*((__int64 (__fastcall **)(const unsigned int **))v37 + 2))(&v37),
          hUSKey = phNewUSKey,
          SecurityUrl) )
    {
      if ( SecurityUrl > 0 )
      {
        SecurityUrl = (unsigned __int16)SecurityUrl;
        goto LABEL_99;
      }
LABEL_100:
      v43 = &CRegKey::`vftable';
      if ( v44 )
      {
        SHRegCloseUSKey(v44);
        v44 = 0;
      }
      v37 = &CRegKey::`vftable';
      if ( hUSKey )
      {
        SHRegCloseUSKey(hUSKey);
        hUSKey = 0;
      }
      if ( v56 )
        CoTaskMemFree(pv);
      SysFreeString(bstrString);
      SysFreeString(v54);
      ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
      return (unsigned int)SecurityUrl;
    }
    if ( phNewUSKey )
    {
      SHRegCloseUSKey(phNewUSKey);
      hUSKey = 0;
    }
    v33 = (void *)*((_QWORD *)this + 22);
    phNewUSKey = 0;
    (*((void (__fastcall **)(const unsigned int **))v37 + 2))(&v37);
    if ( v40 )
    {
      v34 = fIgnoreHKCU;
      if ( fIgnoreHKCU )
        goto LABEL_83;
      if ( !SHRegOpenUSKeyW(pszStart, 0x2001Fu, v33, &phNewUSKey, 1) )
      {
LABEL_84:
        hUSKey = phNewUSKey;
        v36 = 0;
        if ( !CRegKey::QueryValue((CRegKey *)&v37, &v36, pwzValue) )
        {
          SecurityUrl = -2147024816;
          goto LABEL_100;
        }
        v26 = CRegKey::SetValue((CRegKey *)&v37, v12, pwzValue);
        SecurityUrl = v26;
        v27 = v26 <= 0;
        if ( !v26 )
        {
LABEL_68:
          CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 0x14u);
          goto LABEL_56;
        }
        goto LABEL_69;
      }
    }
    v34 = fIgnoreHKCU;
LABEL_83:
    if ( SHRegOpenUSKeyW(pszStart, 0x2001Fu, v33, &phNewUSKey, v34) )
    {
      LastError = GetLastError();
      SecurityUrl = LastError;
      if ( LastError > 0 )
        SecurityUrl = (unsigned __int16)LastError | 0x80070000;
      v43 = &CRegKey::`vftable';
      if ( v44 )
      {
        SHRegCloseUSKey(v44);
        v44 = 0;
      }
      v37 = &CRegKey::`vftable';
      if ( hUSKey )
      {
        SHRegCloseUSKey(hUSKey);
        hUSKey = 0;
      }
      if ( v56 )
        CoTaskMemFree(pv);
      SysFreeString(bstrString);
      SysFreeString(v54);
      goto LABEL_19;
    }
    goto LABEL_84;
  }
  if ( v56 )
    CoTaskMemFree(pv);
  SysFreeString(bstrString);
  SysFreeString(v54);
  ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18003a370  push    rbp
0x18003a372  push    rbx
0x18003a373  push    rsi
0x18003a374  push    rdi
0x18003a375  push    r12
0x18003a377  push    r13
0x18003a379  push    r14
0x18003a37b  push    r15
0x18003a37d  lea     rbp, [rsp-0C68h]
0x18003a385  sub     rsp, 0D68h
0x18003a38c  mov     rax, cs:__security_cookie
0x18003a393  xor     rax, rsp
0x18003a396  mov     [rbp+0CA0h+var_50], rax
0x18003a39d  mov     ebx, edx
0x18003a39f  mov     rsi, rcx
0x18003a3a2  mov     edx, 4; unsigned int
0x18003a3a7  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x18003a3ae  mov     r15d, r9d
0x18003a3b1  mov     r12, r8
0x18003a3b4  call    ?IncrementCounter@CSharedMem@@QEAAHK@Z; CSharedMem::IncrementCounter(ulong)
0x18003a3b9  cmp     qword ptr [rsi+60h], 0
0x18003a3be  jz      short loc_18003A3CA
0x18003a3c0  mov     edi, 80070005h
0x18003a3c5  jmp     loc_18003AB4E
0x18003a3ca  mov     rcx, [rsi+58h]
0x18003a3ce  test    rcx, rcx
0x18003a3d1  jnz     short loc_18003A3E5
0x18003a3d3  mov     rcx, [rsi+50h]
0x18003a3d7  test    rcx, rcx
0x18003a3da  jnz     short loc_18003A3E5
0x18003a3dc  mov     rcx, [rsi+48h]
0x18003a3e0  test    rcx, rcx
0x18003a3e3  jz      short loc_18003A41E
0x18003a3e5  mov     rax, [rcx]
0x18003a3e8  mov     r9d, r15d
0x18003a3eb  mov     r8, r12
0x18003a3ee  mov     edx, ebx
0x18003a3f0  mov     rax, [rax+48h]
0x18003a3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3f9  mov     edi, eax
0x18003a3fb  cmp     eax, 800C0011h
0x18003a400  jz      short loc_18003A41E
0x18003a402  test    eax, eax
0x18003a404  jnz     loc_18003AB4E
0x18003a40a  lea     edx, [rax+14h]; unsigned int
0x18003a40d  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x18003a414  call    ?IncrementCounter@CSharedMem@@QEAAHK@Z; CSharedMem::IncrementCounter(ulong)
0x18003a419  jmp     loc_18003AB4E
0x18003a41e  bt      ebx, 8
0x18003a422  jnb     short loc_18003A434
0x18003a424  cmp     ebx, 3E7h
0x18003a42a  ja      short loc_18003A434
0x18003a42c  mov     r14d, 1
0x18003a432  jmp     short loc_18003A437
0x18003a434  xor     r14d, r14d
0x18003a437  mov     r13d, ebx
0x18003a43a  mov     [rbp+0CA0h+ppURI], 0
0x18003a442  btr     r13d, 8
0x18003a447  mov     [rbp+0CA0h+ppSecUri], 0
0x18003a44f  test    r14d, r14d
0x18003a452  mov     edx, 6; unsigned int
0x18003a457  mov     ecx, 3002B80h; unsigned int
0x18003a45c  cmovz   r13d, ebx
0x18003a460  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18003a465  mov     edx, eax; dwFlags
0x18003a467  lea     r9, [rbp+0CA0h+ppURI]; ppURI
0x18003a46b  mov     rcx, r12; pwzURI
0x18003a46e  xor     r8d, r8d; dwReserved
0x18003a471  call    cs:__imp_CreateUri
0x18003a477  xor     r12d, r12d
0x18003a47a  mov     edi, eax
0x18003a47c  test    eax, eax
0x18003a47e  js      loc_18003AB4E
0x18003a484  mov     rbx, [rbp+0CA0h+ppURI]
0x18003a488  lea     r8d, [r12+1]; psuAction
0x18003a48d  mov     rcx, rbx; pUri
0x18003a490  lea     rdx, [rbp+0CA0h+ppSecUri]; ppSecUri
0x18003a494  xor     r9d, r9d; dwReserved
0x18003a497  call    CoInternetGetSecurityUrlEx
0x18003a49c  mov     edi, eax
0x18003a49e  mov     rcx, rbx
0x18003a4a1  mov     rax, [rbx]
0x18003a4a4  mov     rax, [rax+10h]
0x18003a4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4ad  test    edi, edi
0x18003a4af  js      loc_18003AB4E
0x18003a4b5  mov     rbx, [rbp+0CA0h+ppSecUri]
0x18003a4b9  lea     rcx, [rbp+0CA0h+var_D10]; void *
0x18003a4bd  xor     edx, edx; Val
0x18003a4bf  mov     r8d, 4E8h; Size
0x18003a4c5  call    memset_0
0x18003a4ca  lea     r9d, [r12+1]; int
0x18003a4cf  mov     rdx, rbx; struct IUri *
0x18003a4d2  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003a4d6  call    ?Crack@ZONEMAP_COMPONENTS@@QEAAJPEAUIUri@@KH@Z; ZONEMAP_COMPONENTS::Crack(IUri *,ulong,int)
0x18003a4db  mov     edi, eax
0x18003a4dd  test    eax, eax
0x18003a4df  jz      short loc_18003A4F6
0x18003a4e1  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003a4e5  call    ??1ZONEMAP_COMPONENTS@@QEAA@XZ; ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS(void)
0x18003a4ea  mov     rcx, [rbx]
0x18003a4ed  mov     rax, [rcx+10h]
0x18003a4f1  jmp     loc_18003AB46
0x18003a4f6  xor     edx, edx; Val
0x18003a4f8  lea     rcx, [rbp+0CA0h+var_81C]; void *
0x18003a4ff  mov     r8d, 5B0h; Size
0x18003a505  call    memset_0
0x18003a50a  mov     rcx, rsi; this
0x18003a50d  mov     [rbp+0CA0h+var_820], 5B4h
0x18003a517  call    ?EnsureZoneManager@CSecurityManager@@IEAAHXZ; CSecurityManager::EnsureZoneManager(void)
0x18003a51c  test    eax, eax
0x18003a51e  jnz     short loc_18003A55D
0x18003a520  cmp     [rbp+0CA0h+var_CC4], r12d
0x18003a524  jz      short loc_18003A530
0x18003a526  mov     rcx, [rbp+0CA0h+pv]; pv
0x18003a52a  call    cs:__imp_CoTaskMemFree
0x18003a530  mov     rcx, [rbp+0CA0h+bstrString]; bstrString
0x18003a534  call    cs:__imp_SysFreeString
0x18003a53a  mov     rcx, [rbp+0CA0h+var_CE0]; bstrString
0x18003a53e  call    cs:__imp_SysFreeString
0x18003a544  mov     rax, [rbx]
0x18003a547  mov     rcx, rbx
0x18003a54a  mov     rax, [rax+10h]
0x18003a54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a553  mov     eax, 8007000Eh
0x18003a558  jmp     loc_18003AB50
0x18003a55d  mov     edx, cs:?s_fESCEnabled@CSecurityManager@@0HA; int CSecurityManager::s_fESCEnabled
0x18003a563  test    r14d, r14d
0x18003a566  jz      short loc_18003A572
0x18003a568  cmp     r13d, 2
0x18003a56c  jnz     short loc_18003A572
0x18003a56e  test    edx, edx
0x18003a570  jz      short loc_18003A5CD
0x18003a572  test    r15b, 1
0x18003a576  jnz     short loc_18003A5CD
0x18003a578  mov     rcx, [rsi+40h]
0x18003a57c  lea     r8, [rbp+0CA0h+var_820]
0x18003a583  mov     edx, r13d
0x18003a586  mov     rax, [rcx]
0x18003a589  mov     rax, [rax+18h]
0x18003a58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a592  test    eax, eax
0x18003a594  js      short loc_18003A5C7
0x18003a596  test    [rbp+0CA0h+var_270], 4
0x18003a59d  jz      short loc_18003A5C7
0x18003a59f  cmp     [rbp+0CA0h+var_D10], 0Bh
0x18003a5a3  jz      short loc_18003A5C7
0x18003a5a5  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003a5a9  call    ??1ZONEMAP_COMPONENTS@@QEAA@XZ; ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS(void)
0x18003a5ae  mov     rax, [rbx]
0x18003a5b1  mov     rcx, rbx
0x18003a5b4  mov     rax, [rax+10h]
0x18003a5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5bd  mov     eax, 80070005h
0x18003a5c2  jmp     loc_18003AB50
0x18003a5c7  mov     edx, cs:?s_fESCEnabled@CSecurityManager@@0HA; int CSecurityManager::s_fESCEnabled
0x18003a5cd  test    [rbp+0CA0h+var_CBC], 2
0x18003a5d1  jz      short loc_18003A5EC
0x18003a5d3  mov     r9d, r15d; unsigned int
0x18003a5d6  lea     rdx, [rbp+0CA0h+var_D10]; struct ZONEMAP_COMPONENTS *
0x18003a5da  mov     r8d, r13d; unsigned int
0x18003a5dd  mov     rcx, rsi; this
0x18003a5e0  call    ?AddDeleteIPRule@CSecurityManager@@IEAAJPEAVZONEMAP_COMPONENTS@@KK@Z; CSecurityManager::AddDeleteIPRule(ZONEMAP_COMPONENTS *,ulong,ulong)
0x18003a5e5  mov     edi, eax
0x18003a5e7  jmp     loc_18003A4E1
0x18003a5ec  cmp     [rbp+0CA0h+var_CA8], r12d
0x18003a5f0  jz      short loc_18003A614
0x18003a5f2  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003a5f6  call    ??1ZONEMAP_COMPONENTS@@QEAA@XZ; ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS(void)
0x18003a5fb  mov     rax, [rbx]
0x18003a5fe  mov     rcx, rbx
0x18003a601  mov     rax, [rax+10h]
0x18003a605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a60a  mov     eax, 80070057h
0x18003a60f  jmp     loc_18003AB50
0x18003a614  mov     ecx, cs:?g_bUseHKLMOnly@@3HA; int g_bUseHKLMOnly
0x18003a61a  lea     r8, ??_7CRegKey@@6B@; unsigned int
0x18003a621  mov     eax, cs:?s_fUsePoliciesZoneMap@CSecurityManager@@0HA; int CSecurityManager::s_fUsePoliciesZoneMap
0x18003a627  mov     [rsp+0DA0h+var_D68], r8
0x18003a62c  mov     [rsp+0DA0h+var_D40], r8
0x18003a631  mov     [rsp+0DA0h+fIgnoreHKCU], ecx
0x18003a635  mov     [rsp+0DA0h+hUSKey], r12
0x18003a63a  mov     [rsp+0DA0h+var_D50], r12d
0x18003a63f  mov     [rsp+0DA0h+var_D54], eax
0x18003a643  mov     [rsp+0DA0h+var_D30], ecx
0x18003a647  mov     [rsp+0DA0h+var_D38], r12
0x18003a64c  mov     [rsp+0DA0h+var_D28], r12d
0x18003a651  mov     [rsp+0DA0h+var_D2C], eax
0x18003a655  test    r15b, 1
0x18003a659  jz      loc_18003A8F1
0x18003a65f  test    r14d, r14d
0x18003a662  jnz     short loc_18003A671
0x18003a664  test    edx, edx
0x18003a666  jnz     short loc_18003A671
0x18003a668  mov     r9d, r12d
0x18003a66b  lea     r15d, [r14+1]
0x18003a66f  jmp     short loc_18003A67A
0x18003a671  mov     r15d, 1
0x18003a677  mov     r9d, r15d; int
0x18003a67a  lea     rdx, [rbp+0CA0h+pszStart]; unsigned __int16 *
0x18003a681  lea     rcx, [rbp+0CA0h+var_D10]; struct ZONEMAP_COMPONENTS *
0x18003a685  call    ?GetDomainKeyNameForDeleting@CSecurityManager@@KAJPEBVZONEMAP_COMPONENTS@@PEAGKH@Z; CSecurityManager::GetDomainKeyNameForDeleting(ZONEMAP_COMPONENTS const *,ushort *,ulong,int)
0x18003a68a  mov     edi, eax
0x18003a68c  test    eax, eax
0x18003a68e  jns     short loc_18003A6BA
0x18003a690  lea     rsi, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x18003a697  lea     rcx, [rsp+0DA0h+var_D40]; this
0x18003a69c  mov     [rsp+0DA0h+var_D40], rsi
0x18003a6a1  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003a6a6  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003a6ab  mov     [rsp+0DA0h+var_D68], rsi
0x18003a6b0  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003a6b5  jmp     loc_18003A4E1
0x18003a6ba  mov     rdx, [rsi+70h]; void *
0x18003a6be  lea     r8, [rbp+0CA0h+pszStart]; unsigned __int16 *
0x18003a6c5  mov     r14d, 2001Fh
0x18003a6cb  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003a6d0  mov     r9d, r14d; unsigned int
0x18003a6d3  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x18003a6d8  mov     r13d, 5Ch ; '\'
0x18003a6de  cmp     eax, 2
0x18003a6e1  jnz     loc_18003A7B4
0x18003a6e7  cmp     [rbp+0CA0h+var_CD4], r15d
0x18003a6eb  jnz     short loc_18003A753
0x18003a6ed  mov     rax, [rbp+0CA0h+pv]
0x18003a6f1  cmp     word ptr [rax], 2Ah ; '*'
0x18003a6f5  jnz     short loc_18003A753
0x18003a6f7  mov     r8d, r13d; wMatch
0x18003a6fa  lea     rcx, [rbp+0CA0h+pszStart]; pszStart
0x18003a701  xor     edx, edx; pszEnd
0x18003a703  call    cs:__imp_StrRChrW
0x18003a709  mov     rdx, rax
0x18003a70c  test    rax, rax
0x18003a70f  jz      short loc_18003A753
0x18003a711  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a715  inc     rax
0x18003a718  cmp     [rdx+rax*2], r12w
0x18003a71d  jnz     short loc_18003A715
0x18003a71f  cmp     eax, r15d
0x18003a722  jbe     short loc_18003A753
0x18003a724  cmp     word ptr [rdx+2], 2Ah ; '*'
0x18003a729  jnz     short loc_18003A753
0x18003a72b  lea     r9d, [rax-2]
0x18003a72f  mov     r8d, r15d
0x18003a732  cmp     r9d, r15d
0x18003a735  jbe     short loc_18003A74E
0x18003a737  mov     ecx, r8d
0x18003a73a  lea     eax, [r8+2]
0x18003a73e  movzx   eax, word ptr [rdx+rax*2]
0x18003a742  add     r8d, r15d
0x18003a745  mov     [rdx+rcx*2], ax
0x18003a749  cmp     r8d, r9d
0x18003a74c  jb      short loc_18003A737
0x18003a74e  mov     [rdx+r9*2], r12w
0x18003a753  mov     rdx, [rsi+70h]; void *
0x18003a757  lea     r8, [rbp+0CA0h+pszStart]; unsigned __int16 *
0x18003a75e  mov     r9d, r14d; unsigned int
0x18003a761  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003a766  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x18003a76b  cmp     eax, 2
0x18003a76e  jnz     short loc_18003A7B4
0x18003a770  lea     rsi, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x18003a777  lea     rcx, [rsp+0DA0h+var_D40]; this
0x18003a77c  mov     [rsp+0DA0h+var_D40], rsi
0x18003a781  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003a786  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003a78b  mov     [rsp+0DA0h+var_D68], rsi
0x18003a790  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003a795  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003a799  call    ??1ZONEMAP_COMPONENTS@@QEAA@XZ; ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS(void)
0x18003a79e  mov     rax, [rbx]
0x18003a7a1  mov     rcx, rbx
0x18003a7a4  mov     rax, [rax+10h]
0x18003a7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7ad  xor     eax, eax
0x18003a7af  jmp     loc_18003AB50
0x18003a7b4  mov     eax, [rsp+0DA0h+fIgnoreHKCU]
0x18003a7b8  mov     rdx, [rbp+0CA0h+pwzValue]; pwzValue
0x18003a7bc  neg     eax
0x18003a7be  mov     rcx, [rsp+0DA0h+hUSKey]; hUSKey
0x18003a7c3  sbb     r8d, r8d
0x18003a7c6  and     r8d, 0Fh
0x18003a7ca  add     r8d, r15d; delRegFlags
0x18003a7cd  call    cs:__imp_SHRegDeleteUSValueW
0x18003a7d3  mov     edi, eax
0x18003a7d5  test    eax, eax
0x18003a7d7  jnz     loc_18003A8E3
0x18003a7dd  lea     r9, [rsp+0DA0h+var_D70]; unsigned int *
0x18003a7e2  mov     [rsp+0DA0h+var_D70], r12d
0x18003a7e7  xor     r8d, r8d; unsigned int *
0x18003a7ea  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003a7ef  xor     edx, edx; unsigned int *
0x18003a7f1  call    ?QuerySubKeyInfo@CRegKey@@QEAAJPEAK00@Z; CRegKey::QuerySubKeyInfo(ulong *,ulong *,ulong *)
0x18003a7f6  test    eax, eax
0x18003a7f8  jnz     short loc_18003A82B
0x18003a7fa  cmp     [rsp+0DA0h+var_D70], r12d
0x18003a7ff  jnz     short loc_18003A82B
0x18003a801  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003a806  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003a80b  mov     eax, [rsi+78h]
  ... truncated ...
```
