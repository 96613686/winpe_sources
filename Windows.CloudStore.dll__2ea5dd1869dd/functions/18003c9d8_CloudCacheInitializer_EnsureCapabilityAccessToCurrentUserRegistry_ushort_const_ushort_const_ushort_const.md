# CloudCacheInitializer::EnsureCapabilityAccessToCurrentUserRegistry(ushort const *,ushort const *,ushort const *)

- ea: `0x18003c9d8`
- end: `0x18003d4d1`
- name: `?EnsureCapabilityAccessToCurrentUserRegistry@CloudCacheInitializer@@AEAAJPEBG00@Z`
- size: `2809`
- prototype: `__int64 __fastcall(CloudCacheInitializer *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003c340`

## callees

- `0x18003c9d8`
- `0x18003d4d8`
- `0x18003e670`
- `0x18003f6c4`
- `0x1800c8458`
- `0x1800ff298`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d26f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d26f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d327`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d264`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d282`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d2aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d33a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d264`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d282`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d2aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d33a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ca60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cc04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cdae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cfe3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003d13a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ca60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cc04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cdae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cfe3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003d13a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cf0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cf69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cf71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d216`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d246`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d25c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d27a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d2a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d2db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d2ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d2fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d30a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d31a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d332`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cf0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cf69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cf71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d216`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d246`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d25c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d27a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d2a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d2db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d2ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d2fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d30a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d31a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d332`

## string_xrefs

- `0x18003cef4`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003cf21`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d1f9`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d225`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d356`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d380`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d3b3`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d3d5`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d3f5`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d417`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d437`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d456`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d473`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d492`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003d074`: `\Cache`
- `0x18003cfa7`: `Cache`

## pseudocode

```c
__int64 __fastcall CloudCacheInitializer::EnsureCapabilityAccessToCurrentUserRegistry(
        CloudCacheInitializer *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const WCHAR *v4; // r12
  const unsigned __int16 *v5; // rsi
  const unsigned __int16 *v6; // r9
  unsigned int v7; // r14d
  HKEY *v8; // rdi
  HKEY v9; // r15
  HKEY v10; // rsi
  __int64 v11; // r13
  const wchar_t *v12; // rcx
  unsigned __int16 *v13; // r8
  __int64 v14; // rax
  __int64 v15; // rdx
  unsigned __int16 *v16; // rcx
  unsigned int v17; // ebx
  __int64 v18; // rdx
  unsigned __int16 *v19; // rax
  __int64 v20; // r8
  __int64 v21; // rax
  bool v22; // zf
  __int64 v23; // rdx
  unsigned __int16 *v24; // r8
  CloudCacheInitializer *v25; // rcx
  int v26; // eax
  unsigned int v27; // r15d
  HKEY *v28; // rsi
  HKEY v29; // r12
  HKEY v30; // r14
  __int64 v31; // rax
  unsigned __int16 *v32; // rcx
  __int64 v33; // rdx
  unsigned __int16 *v34; // r8
  unsigned __int16 *v35; // rcx
  __int64 v36; // rdx
  unsigned __int16 *v37; // rax
  __int64 v38; // r8
  const wchar_t *v39; // rcx
  __int64 v40; // rax
  unsigned __int16 *v41; // r9
  __int64 v42; // rdx
  CloudCacheInitializer *v43; // rcx
  int v44; // eax
  unsigned int v45; // r15d
  HKEY *v46; // rsi
  HKEY v47; // r12
  HKEY v48; // r14
  __int64 v49; // rax
  unsigned __int16 *v50; // rcx
  __int64 v51; // rdx
  unsigned __int16 *v52; // r8
  unsigned __int16 *v53; // rcx
  __int64 v54; // rdx
  unsigned __int16 *v55; // rax
  __int64 v56; // r8
  const wchar_t *v57; // rcx
  __int64 v58; // rax
  unsigned __int16 *v59; // r9
  __int64 v60; // rdx
  CloudCacheInitializer *v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rdx
  int v65; // eax
  unsigned int v66; // r15d
  HKEY *v67; // rsi
  HKEY v68; // r12
  HKEY v69; // r14
  __int64 v70; // rdx
  unsigned __int16 *v71; // rax
  __int64 v72; // r8
  const wchar_t *v73; // rcx
  __int64 v74; // rax
  unsigned __int16 *v75; // r9
  __int64 v76; // rdx
  CloudCacheInitializer *v77; // rcx
  int v78; // eax
  unsigned int v79; // ebx
  const unsigned __int16 *v80; // r9
  __int64 v81; // rdx
  unsigned __int16 *v82; // rax
  __int64 v83; // r8
  unsigned __int16 *v84; // rdx
  const wchar_t *v85; // rax
  __int64 v86; // rdi
  CloudCacheInitializer *v87; // rcx
  DWORD LastError; // ebx
  DWORD v89; // ebx
  DWORD v90; // ebx
  int v91; // eax
  DWORD v92; // ebx
  __int64 v93; // rdx
  unsigned __int64 v94; // r9
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-E0h]
  int dwOptionsd; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionse; // [rsp+20h] [rbp-E0h]
  int dwOptionsf; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsg; // [rsp+20h] [rbp-E0h]
  int dwOptionsh; // [rsp+20h] [rbp-E0h]
  HKEY v104; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v106; // [rsp+60h] [rbp-A0h] BYREF
  HKEY *p_hKey; // [rsp+68h] [rbp-98h]
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  char v109; // [rsp+78h] [rbp-88h]
  HKEY v110; // [rsp+80h] [rbp-80h] BYREF
  HKEY v111; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v112; // [rsp+90h] [rbp-70h]
  WCHAR v113[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR v114[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR v115[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+728h] [rbp+628h]

  v112 = a4;
  p_hKey = &hKey;
  v4 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore";
  hKey = 0;
  v5 = a4;
  phkResult = 0;
  v109 = 1;
  v7 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &phkResult,
         0);
  if ( v109 )
  {
    v8 = p_hKey;
    v9 = phkResult;
    v10 = *p_hKey;
    if ( *p_hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v10);
      SetLastError(LastError);
    }
    v5 = v112;
    *v8 = v9;
  }
  if ( v7 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x44F,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            (const char *)v7,
            dwOptions);
LABEL_80:
    if ( hKey )
      RegCloseKey(hKey);
    return v17;
  }
  v11 = 2147483646;
  v12 = L"CURRENT_USER\\";
  v13 = v113;
  v14 = 2147483646;
  v15 = 260;
  do
  {
    if ( !v14 )
      break;
    v6 = (const unsigned __int16 *)*v12;
    if ( !(_WORD)v6 )
      break;
    *v13 = (unsigned __int16)v6;
    ++v12;
    ++v13;
    --v14;
    --v15;
  }
  while ( v15 );
  v16 = v13 - 1;
  v17 = v15 == 0 ? 0x8007007A : 0;
  if ( v15 )
    v16 = v13;
  *v16 = 0;
  if ( !v15 )
  {
    v93 = 1106;
    goto LABEL_136;
  }
  v18 = 260;
  v19 = v113;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  v17 = v18 == 0 ? 0x80070057 : 0;
  v20 = (260 - v18) & -(__int64)(v18 != 0);
  if ( !v18 )
    goto LABEL_135;
  v21 = 2147483646;
  v23 = 260 - v20;
  v22 = v20 == 260;
  v24 = &v113[v20];
  if ( !v22 )
  {
    do
    {
      if ( !v21 )
        break;
      if ( !*v4 )
        break;
      *v24++ = *v4++;
      --v21;
      --v23;
    }
    while ( v23 );
  }
  v25 = (CloudCacheInitializer *)(v24 - 1);
  v17 = v23 == 0 ? 0x8007007A : 0;
  if ( v23 )
    v25 = (CloudCacheInitializer *)v24;
  *(_WORD *)v25 = 0;
  if ( !v23 )
  {
LABEL_135:
    v93 = 1107;
LABEL_136:
    v94 = v17;
LABEL_137:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v93,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)v94,
      dwOptions);
LABEL_138:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v17;
  }
  v26 = CloudCacheInitializer::EnsureRegistryCapabilitySecurityDescriptorSet(
          v25,
          v113,
          (enum _SE_OBJECT_TYPE)v24,
          v6,
          v5,
          1);
  v17 = v26;
  if ( v26 < 0 )
  {
    v94 = (unsigned int)v26;
    v93 = 1108;
    goto LABEL_137;
  }
  p_hKey = &v104;
  v104 = 0;
  phkResult = 0;
  v109 = 1;
  v27 = RegCreateKeyExW(hKey, L"Store", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v109 )
  {
    v28 = p_hKey;
    v29 = phkResult;
    v30 = *p_hKey;
    if ( *p_hKey )
    {
      v89 = GetLastError();
      RegCloseKey(v30);
      SetLastError(v89);
    }
    *v28 = v29;
    v5 = v112;
  }
  if ( v27 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x459,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            (const char *)v27,
            dwOptionsa);
LABEL_152:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v104);
    goto LABEL_138;
  }
  v31 = 2147483646;
  v32 = v113;
  v33 = 260;
  v34 = v114;
  do
  {
    if ( !v31 )
      break;
    if ( !*v32 )
      break;
    *v34++ = *v32++;
    --v31;
    --v33;
  }
  while ( v33 );
  v35 = v34 - 1;
  v17 = v33 == 0 ? 0x8007007A : 0;
  if ( v33 )
    v35 = v34;
  *v35 = 0;
  if ( !v33 )
  {
    v63 = 1114;
LABEL_77:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v63,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)v17,
      dwOptionsa);
LABEL_78:
    if ( v104 )
      RegCloseKey(v104);
    goto LABEL_80;
  }
  v36 = 260;
  v37 = v114;
  do
  {
    if ( !*v37 )
      break;
    ++v37;
    --v36;
  }
  while ( v36 );
  v17 = v36 == 0 ? 0x80070057 : 0;
  v38 = (260 - v36) & -(__int64)(v36 != 0);
  if ( !v36 )
    goto LABEL_120;
  v39 = L"\\Store";
  v40 = 2147483646;
  v41 = &v114[v38];
  v42 = 260 - v38;
  if ( v38 != 260 )
  {
    do
    {
      if ( !v40 )
        break;
      LODWORD(v38) = *v39;
      if ( !(_WORD)v38 )
        break;
      *v41 = v38;
      ++v39;
      ++v41;
      --v40;
      --v42;
    }
    while ( v42 );
  }
  v43 = (CloudCacheInitializer *)(v41 - 1);
  v17 = v42 == 0 ? 0x8007007A : 0;
  if ( v42 )
    v43 = (CloudCacheInitializer *)v41;
  *(_WORD *)v43 = 0;
  if ( !v42 )
  {
LABEL_120:
    v63 = 1115;
    goto LABEL_77;
  }
  v44 = CloudCacheInitializer::EnsureRegistryCapabilitySecurityDescriptorSet(
          v43,
          v114,
          (enum _SE_OBJECT_TYPE)v38,
          v41,
          v5,
          0);
  v17 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45C,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)(unsigned int)v44,
      dwOptionsb);
    goto LABEL_152;
  }
  p_hKey = &v106;
  v106 = 0;
  phkResult = 0;
  v109 = 1;
  v45 = RegCreateKeyExW(hKey, L"SystemMetaData", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v109 )
  {
    v46 = p_hKey;
    v47 = phkResult;
    v48 = *p_hKey;
    if ( *p_hKey )
    {
      v90 = GetLastError();
      RegCloseKey(v48);
      SetLastError(v90);
    }
    *v46 = v47;
    v5 = v112;
  }
  if ( v45 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x461,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            (const char *)v45,
            dwOptionsc);
LABEL_151:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
    goto LABEL_152;
  }
  v49 = 2147483646;
  v50 = v113;
  v51 = 260;
  v52 = v115;
  do
  {
    if ( !v49 )
      break;
    if ( !*v50 )
      break;
    *v52++ = *v50++;
    --v49;
    --v51;
  }
  while ( v51 );
  v53 = v52 - 1;
  v17 = v51 == 0 ? 0x8007007A : 0;
  if ( v51 )
    v53 = v52;
  *v53 = 0;
  if ( !v51 )
  {
    v62 = 1122;
    goto LABEL_73;
  }
  v54 = 260;
  v55 = v115;
  do
  {
    if ( !*v55 )
      break;
    ++v55;
    --v54;
  }
  while ( v54 );
  v17 = v54 == 0 ? 0x80070057 : 0;
  v56 = (260 - v54) & -(__int64)(v54 != 0);
  if ( !v54 )
    goto LABEL_72;
  v57 = L"\\SystemMetaData";
  v58 = 2147483646;
  v59 = &v115[v56];
  v60 = 260 - v56;
  if ( v56 != 260 )
  {
    do
    {
      if ( !v58 )
        break;
      LODWORD(v56) = *v57;
      if ( !(_WORD)v56 )
        break;
      *v59 = v56;
      ++v57;
      ++v59;
      --v58;
      --v60;
    }
    while ( v60 );
  }
  v61 = (CloudCacheInitializer *)(v59 - 1);
  v17 = v60 == 0 ? 0x8007007A : 0;
  if ( v60 )
    v61 = (CloudCacheInitializer *)v59;
  *(_WORD *)v61 = 0;
  if ( !v60 )
  {
LABEL_72:
    v62 = 1123;
LABEL_73:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v62,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)v17,
      dwOptionsc);
LABEL_74:
    if ( v106 )
      RegCloseKey(v106);
    goto LABEL_78;
  }
  v65 = CloudCacheInitializer::EnsureRegistryCapabilitySecurityDescriptorSet(
          v61,
          v115,
          (enum _SE_OBJECT_TYPE)v56,
          v59,
          v5,
          0);
  v17 = v65;
  if ( v65 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x464,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)(unsigned int)v65,
      dwOptionsd);
    goto LABEL_151;
  }
  p_hKey = &v110;
  v110 = 0;
  phkResult = 0;
  v109 = 1;
  v66 = RegCreateKeyExW(v104, L"Cache", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v109 )
  {
    v67 = p_hKey;
    v68 = phkResult;
    v69 = *p_hKey;
    if ( *p_hKey )
    {
      v92 = GetLastError();
      RegCloseKey(v69);
      SetLastError(v92);
    }
    *v67 = v68;
    v5 = v112;
  }
  if ( v66 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x469,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            (const char *)v66,
            dwOptionse);
LABEL_150:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v110);
    goto LABEL_151;
  }
  v70 = 260;
  v71 = v114;
  do
  {
    if ( !*v71 )
      break;
    ++v71;
    --v70;
  }
  while ( v70 );
  v17 = v70 == 0 ? 0x80070057 : 0;
  v72 = (260 - v70) & -(__int64)(v70 != 0);
  if ( !v70 )
    goto LABEL_117;
  v73 = L"\\Cache";
  v74 = 2147483646;
  v75 = &v114[v72];
  v76 = 260 - v72;
  if ( v72 != 260 )
  {
    do
    {
      if ( !v74 )
        break;
      LODWORD(v72) = *v73;
      if ( !(_WORD)v72 )
        break;
      *v75 = v72;
      ++v73;
      ++v75;
      --v74;
      --v76;
    }
    while ( v76 );
  }
  v77 = (CloudCacheInitializer *)(v75 - 1);
  v17 = v76 == 0 ? 0x8007007A : 0;
  if ( v76 )
    v77 = (CloudCacheInitializer *)v75;
  *(_WORD *)v77 = 0;
  if ( !v76 )
  {
LABEL_117:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46A,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)v17,
      dwOptionse);
LABEL_118:
    if ( v110 )
      RegCloseKey(v110);
    goto LABEL_74;
  }
  v78 = CloudCacheInitializer::EnsureRegistryCapabilitySecurityDescriptorSet(
          v77,
          v114,
          (enum _SE_OBJECT_TYPE)v72,
          v75,
          v5,
          0);
  v17 = v78;
  if ( v78 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46B,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)(unsigned int)v78,
      dwOptionsf);
    goto LABEL_150;
  }
  p_hKey = &v111;
  v111 = 0;
  phkResult = 0;
  v109 = 1;
  v79 = RegCreateKeyExW(hKey, L"StoreInit", 0, 0, 1u, 0xF003Fu, 0, &phkResult, 0);
  if ( v109 )
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      p_hKey,
      phkResult);
  if ( v79 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x46F,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            (const char *)v79,
            dwOptionsg);
LABEL_149:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v111);
    goto LABEL_150;
  }
  v81 = 260;
  v82 = v113;
  do
  {
    if ( !*v82 )
      break;
    ++v82;
    --v81;
  }
  while ( v81 );
  v17 = v81 == 0 ? 0x80070057 : 0;
  v83 = (260 - v81) & -(__int64)(v81 != 0);
  if ( !v81 )
    goto LABEL_115;
  v84 = &v113[v83];
  v85 = L"\\StoreInit";
  v86 = 260 - v83;
  if ( 260 != v83 )
  {
    do
    {
      if ( !v11 )
        break;
      if ( !*v85 )
        break;
      *v84++ = *v85++;
      --v11;
      --v86;
    }
    while ( v86 );
  }
  v87 = (CloudCacheInitializer *)(v84 - 1);
  v17 = v86 == 0 ? 0x8007007A : 0;
  if ( v86 )
    v87 = (CloudCacheInitializer *)v84;
  *(_WORD *)v87 = 0;
  if ( !v86 )
  {
LABEL_115:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x470,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)v17,
      dwOptionsg);
    if ( v111 )
      RegCloseKey(v111);
    goto LABEL_118;
  }
  v91 = CloudCacheInitializer::EnsureRegistryCapabilitySecurityDescriptorSet(
          v87,
          v113,
          (enum _SE_OBJECT_TYPE)v83,
          v80,
          v5,
          0);
  v17 = v91;
  if ( v91 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x471,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)(unsigned int)v91,
      dwOptionsh);
    goto LABEL_149;
  }
  if ( v111 )
    RegCloseKey(v111);
  if ( v110 )
    RegCloseKey(v110);
  if ( v106 )
    RegCloseKey(v106);
  if ( v104 )
    RegCloseKey(v104);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18003c9d8  push    rbp
0x18003c9da  push    rbx
0x18003c9db  push    rsi
0x18003c9dc  push    rdi
0x18003c9dd  push    r12
0x18003c9df  push    r13
0x18003c9e1  push    r14
0x18003c9e3  push    r15
0x18003c9e5  lea     rbp, [rsp-5E8h]
0x18003c9ed  sub     rsp, 6E8h
0x18003c9f4  mov     rax, cs:__security_cookie
0x18003c9fb  xor     rax, rsp
0x18003c9fe  mov     [rbp+620h+var_50], rax
0x18003ca05  xor     r13d, r13d
0x18003ca08  mov     [rbp+620h+var_690], r9
0x18003ca0c  mov     [rsp+720h+lpdwDisposition], r13; lpdwDisposition
0x18003ca11  lea     rax, [rsp+720h+hKey]
0x18003ca16  mov     [rsp+720h+var_6B8], rax
0x18003ca1b  lea     r12, pszPathIn; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003ca22  lea     rax, [rsp+720h+var_6B0]
0x18003ca27  mov     [rsp+720h+hKey], r13
0x18003ca2c  mov     [rsp+720h+phkResult], rax; phkResult
0x18003ca31  mov     rsi, r9
0x18003ca34  mov     [rsp+720h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18003ca39  xor     r9d, r9d; lpClass
0x18003ca3c  mov     [rsp+720h+samDesired], 0F003Fh; samDesired
0x18003ca44  xor     r8d, r8d; Reserved
0x18003ca47  mov     rdx, r12; lpSubKey
0x18003ca4a  mov     [rsp+720h+dwOptions], r13d; int
0x18003ca4f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003ca56  mov     [rsp+720h+var_6B0], r13
0x18003ca5b  mov     [rsp+720h+var_6A8], 1
0x18003ca60  call    cs:__imp_RegCreateKeyExW
0x18003ca66  mov     r14d, eax
0x18003ca69  cmp     [rsp+720h+var_6A8], r13b
0x18003ca6e  jz      short loc_18003CA8D
0x18003ca70  mov     rdi, [rsp+720h+var_6B8]
0x18003ca75  mov     r15, [rsp+720h+var_6B0]
0x18003ca7a  mov     rsi, [rdi]
0x18003ca7d  test    rsi, rsi
0x18003ca80  jnz     loc_18003D251
0x18003ca86  mov     rsi, [rbp+620h+var_690]
0x18003ca8a  mov     [rdi], r15
0x18003ca8d  test    r14d, r14d
0x18003ca90  jnz     loc_18003D34F
0x18003ca96  mov     r13d, 7FFFFFFEh
0x18003ca9c  lea     rcx, aCurrentUser; "CURRENT_USER\\"
0x18003caa3  mov     edi, 104h
0x18003caa8  lea     r8, [rbp+620h+var_680]
0x18003caac  mov     eax, r13d
0x18003caaf  mov     edx, edi
0x18003cab1  xor     r14d, r14d
0x18003cab4  test    rax, rax
0x18003cab7  jz      short loc_18003CAD8
0x18003cab9  movzx   r9d, word ptr [rcx]; unsigned __int16 *
0x18003cabd  test    r9w, r9w
0x18003cac1  jz      short loc_18003CAD8
0x18003cac3  mov     [r8], r9w
0x18003cac7  add     rcx, 2
0x18003cacb  add     r8, 2
0x18003cacf  dec     rax
0x18003cad2  sub     rdx, 1
0x18003cad6  jnz     short loc_18003CAB4
0x18003cad8  mov     rax, rdx
0x18003cadb  lea     rcx, [r8-2]
0x18003cadf  neg     rax
0x18003cae2  sbb     ebx, ebx
0x18003cae4  not     ebx
0x18003cae6  and     ebx, 8007007Ah
0x18003caec  test    rdx, rdx
0x18003caef  cmovnz  rcx, r8
0x18003caf3  mov     [rcx], r14w
0x18003caf7  jz      loc_18003D39B
0x18003cafd  mov     rdx, rdi
0x18003cb00  lea     rax, [rbp+620h+var_680]
0x18003cb04  cmp     [rax], r14w
0x18003cb08  jz      short loc_18003CB14
0x18003cb0a  add     rax, 2
0x18003cb0e  sub     rdx, 1
0x18003cb12  jnz     short loc_18003CB04
0x18003cb14  mov     rax, rdx
0x18003cb17  mov     rcx, rdi
0x18003cb1a  neg     rax
0x18003cb1d  mov     rax, rdx
0x18003cb20  sbb     ebx, ebx
0x18003cb22  sub     rcx, rdx
0x18003cb25  not     ebx
0x18003cb27  and     ebx, 80070057h
0x18003cb2d  neg     rax
0x18003cb30  sbb     r8, r8
0x18003cb33  and     r8, rcx
0x18003cb36  test    rdx, rdx
0x18003cb39  jz      loc_18003D371
0x18003cb3f  mov     rdx, rdi
0x18003cb42  mov     rax, r13
0x18003cb45  sub     rdx, r8
0x18003cb48  lea     r8, [rbp+r8*2+620h+var_680]
0x18003cb4d  jz      short loc_18003CB73
0x18003cb4f  test    rax, rax
0x18003cb52  jz      short loc_18003CB73
0x18003cb54  movzx   ecx, word ptr [r12]
0x18003cb59  test    cx, cx
0x18003cb5c  jz      short loc_18003CB73
0x18003cb5e  mov     [r8], cx
0x18003cb62  add     r12, 2
0x18003cb66  add     r8, 2; enum _SE_OBJECT_TYPE
0x18003cb6a  dec     rax
0x18003cb6d  sub     rdx, 1
0x18003cb71  jnz     short loc_18003CB4F
0x18003cb73  mov     rax, rdx
0x18003cb76  lea     rcx, [r8-2]
0x18003cb7a  neg     rax
0x18003cb7d  mov     r12d, 8007007Ah
0x18003cb83  sbb     ebx, ebx
0x18003cb85  not     ebx
0x18003cb87  and     ebx, r12d
0x18003cb8a  test    rdx, rdx
0x18003cb8d  cmovnz  rcx, r8; this
0x18003cb91  mov     [rcx], r14w
0x18003cb95  jz      loc_18003D371
0x18003cb9b  mov     byte ptr [rsp+720h+samDesired], 1; bool
0x18003cba0  lea     rdx, [rbp+620h+var_680]; unsigned __int16 *
0x18003cba4  mov     qword ptr [rsp+720h+dwOptions], rsi; unsigned __int16 *
0x18003cba9  call    ?EnsureRegistryCapabilitySecurityDescriptorSet@CloudCacheInitializer@@AEAAJPEBGW4_SE_OBJECT_TYPE@@00_N@Z; CloudCacheInitializer::EnsureRegistryCapabilitySecurityDescriptorSet(ushort const *,_SE_OBJECT_TYPE,ushort const *,ushort const *,bool)
0x18003cbae  mov     ebx, eax
0x18003cbb0  test    eax, eax
0x18003cbb2  js      loc_18003D3A2
0x18003cbb8  mov     rcx, [rsp+720h+hKey]; hKey
0x18003cbbd  lea     rax, [rsp+720h+var_6D0]
0x18003cbc2  mov     [rsp+720h+lpdwDisposition], r14; lpdwDisposition
0x18003cbc7  lea     rdx, aStore_1; "Store"
0x18003cbce  mov     [rsp+720h+var_6B8], rax
0x18003cbd3  xor     r9d, r9d; lpClass
0x18003cbd6  lea     rax, [rsp+720h+var_6B0]
0x18003cbdb  mov     [rsp+720h+var_6D0], r14
0x18003cbe0  mov     [rsp+720h+phkResult], rax; phkResult
0x18003cbe5  xor     r8d, r8d; Reserved
0x18003cbe8  mov     [rsp+720h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003cbed  mov     [rsp+720h+samDesired], 0F003Fh; samDesired
0x18003cbf5  mov     [rsp+720h+dwOptions], r14d; unsigned int
0x18003cbfa  mov     [rsp+720h+var_6B0], r14
0x18003cbff  mov     [rsp+720h+var_6A8], 1
0x18003cc04  call    cs:__imp_RegCreateKeyExW
0x18003cc0a  mov     r15d, eax
0x18003cc0d  cmp     [rsp+720h+var_6A8], r14b
0x18003cc12  jz      short loc_18003CC3A
0x18003cc14  mov     rsi, [rsp+720h+var_6B8]
0x18003cc19  mov     r12, [rsp+720h+var_6B0]
0x18003cc1e  mov     r14, [rsi]
0x18003cc21  test    r14, r14
0x18003cc24  jnz     loc_18003D26F
0x18003cc2a  mov     [rsi], r12
0x18003cc2d  xor     r14d, r14d
0x18003cc30  mov     rsi, [rbp+620h+var_690]
0x18003cc34  mov     r12d, 8007007Ah
0x18003cc3a  test    r15d, r15d
0x18003cc3d  jnz     loc_18003D3AC
0x18003cc43  mov     rax, r13
0x18003cc46  lea     rcx, [rbp+620h+var_680]
0x18003cc4a  mov     rdx, rdi
0x18003cc4d  lea     r8, [rbp+620h+var_470]
0x18003cc54  test    rax, rax
0x18003cc57  jz      short loc_18003CC78
0x18003cc59  movzx   r9d, word ptr [rcx]
0x18003cc5d  test    r9w, r9w
0x18003cc61  jz      short loc_18003CC78
0x18003cc63  mov     [r8], r9w
0x18003cc67  add     rcx, 2
0x18003cc6b  add     r8, 2
0x18003cc6f  dec     rax
0x18003cc72  sub     rdx, 1
0x18003cc76  jnz     short loc_18003CC54
0x18003cc78  mov     rax, rdx
0x18003cc7b  lea     rcx, [r8-2]
0x18003cc7f  neg     rax
0x18003cc82  sbb     ebx, ebx
0x18003cc84  not     ebx
0x18003cc86  and     ebx, r12d
0x18003cc89  test    rdx, rdx
0x18003cc8c  cmovnz  rcx, r8
0x18003cc90  mov     [rcx], r14w
0x18003cc94  jz      loc_18003CF15
0x18003cc9a  mov     rdx, rdi
0x18003cc9d  lea     rax, [rbp+620h+var_470]
0x18003cca4  cmp     [rax], r14w
0x18003cca8  jz      short loc_18003CCB4
0x18003ccaa  add     rax, 2
0x18003ccae  sub     rdx, 1
0x18003ccb2  jnz     short loc_18003CCA4
0x18003ccb4  mov     rax, rdx
0x18003ccb7  mov     rcx, rdi
0x18003ccba  neg     rax
0x18003ccbd  mov     rax, rdx
0x18003ccc0  sbb     ebx, ebx
0x18003ccc2  sub     rcx, rdx
0x18003ccc5  not     ebx
0x18003ccc7  and     ebx, 80070057h
0x18003cccd  neg     rax
0x18003ccd0  sbb     r8, r8
0x18003ccd3  and     r8, rcx
0x18003ccd6  test    rdx, rdx
0x18003ccd9  jz      loc_18003D28D
0x18003ccdf  mov     rdx, rdi
0x18003cce2  lea     r9, [rbp+620h+var_470]
0x18003cce9  lea     rcx, aStore; "\\Store"
0x18003ccf0  mov     rax, r13
0x18003ccf3  lea     r9, [r9+r8*2]
0x18003ccf7  sub     rdx, r8
0x18003ccfa  jz      short loc_18003CD20
0x18003ccfc  test    rax, rax
0x18003ccff  jz      short loc_18003CD20
0x18003cd01  movzx   r8d, word ptr [rcx]; enum _SE_OBJECT_TYPE
0x18003cd05  test    r8w, r8w
0x18003cd09  jz      short loc_18003CD20
0x18003cd0b  mov     [r9], r8w
0x18003cd0f  add     rcx, 2
0x18003cd13  add     r9, 2; unsigned __int16 *
0x18003cd17  dec     rax
0x18003cd1a  sub     rdx, 1
0x18003cd1e  jnz     short loc_18003CCFC
0x18003cd20  mov     rax, rdx
0x18003cd23  lea     rcx, [r9-2]
0x18003cd27  neg     rax
0x18003cd2a  sbb     ebx, ebx
0x18003cd2c  not     ebx
0x18003cd2e  and     ebx, r12d
0x18003cd31  test    rdx, rdx
0x18003cd34  cmovnz  rcx, r9; this
0x18003cd38  mov     [rcx], r14w
0x18003cd3c  jz      loc_18003D28D
0x18003cd42  mov     byte ptr [rsp+720h+samDesired], r14b; bool
0x18003cd47  lea     rdx, [rbp+620h+var_470]; unsigned __int16 *
0x18003cd4e  mov     qword ptr [rsp+720h+dwOptions], rsi; int
0x18003cd53  call    ?EnsureRegistryCapabilitySecurityDescriptorSet@CloudCacheInitializer@@AEAAJPEBGW4_SE_OBJECT_TYPE@@00_N@Z; CloudCacheInitializer::EnsureRegistryCapabilitySecurityDescriptorSet(ushort const *,_SE_OBJECT_TYPE,ushort const *,ushort const *,bool)
0x18003cd58  mov     ebx, eax
0x18003cd5a  test    eax, eax
0x18003cd5c  js      loc_18003D3CE
0x18003cd62  mov     rcx, [rsp+720h+hKey]; hKey
0x18003cd67  lea     rax, [rsp+720h+var_6C0]
0x18003cd6c  mov     [rsp+720h+lpdwDisposition], r14; lpdwDisposition
0x18003cd71  lea     rdx, aSystemmetadata; "SystemMetaData"
0x18003cd78  mov     [rsp+720h+var_6B8], rax
0x18003cd7d  xor     r9d, r9d; lpClass
0x18003cd80  lea     rax, [rsp+720h+var_6B0]
0x18003cd85  mov     [rsp+720h+var_6C0], r14
0x18003cd8a  mov     [rsp+720h+phkResult], rax; phkResult
0x18003cd8f  xor     r8d, r8d; Reserved
0x18003cd92  mov     [rsp+720h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003cd97  mov     [rsp+720h+samDesired], 0F003Fh; samDesired
0x18003cd9f  mov     [rsp+720h+dwOptions], r14d; unsigned int
0x18003cda4  mov     [rsp+720h+var_6B0], r14
0x18003cda9  mov     [rsp+720h+var_6A8], 1
0x18003cdae  call    cs:__imp_RegCreateKeyExW
0x18003cdb4  mov     r15d, eax
0x18003cdb7  cmp     [rsp+720h+var_6A8], r14b
0x18003cdbc  jz      short loc_18003CDE4
0x18003cdbe  mov     rsi, [rsp+720h+var_6B8]
0x18003cdc3  mov     r12, [rsp+720h+var_6B0]
0x18003cdc8  mov     r14, [rsi]
0x18003cdcb  test    r14, r14
0x18003cdce  jnz     loc_18003D297
0x18003cdd4  mov     [rsi], r12
0x18003cdd7  xor     r14d, r14d
0x18003cdda  mov     rsi, [rbp+620h+var_690]
0x18003cdde  mov     r12d, 8007007Ah
0x18003cde4  test    r15d, r15d
0x18003cde7  jnz     loc_18003D3EE
0x18003cded  mov     rax, r13
0x18003cdf0  lea     rcx, [rbp+620h+var_680]
0x18003cdf4  mov     rdx, rdi
0x18003cdf7  lea     r8, [rbp+620h+var_260]
0x18003cdfe  test    rax, rax
0x18003ce01  jz      short loc_18003CE22
0x18003ce03  movzx   r9d, word ptr [rcx]
0x18003ce07  test    r9w, r9w
0x18003ce0b  jz      short loc_18003CE22
0x18003ce0d  mov     [r8], r9w
0x18003ce11  add     rcx, 2
0x18003ce15  add     r8, 2
0x18003ce19  dec     rax
0x18003ce1c  sub     rdx, 1
0x18003ce20  jnz     short loc_18003CDFE
0x18003ce22  mov     rax, rdx
0x18003ce25  lea     rcx, [r8-2]
0x18003ce29  neg     rax
0x18003ce2c  sbb     ebx, ebx
0x18003ce2e  not     ebx
0x18003ce30  and     ebx, r12d
0x18003ce33  test    rdx, rdx
0x18003ce36  cmovnz  rcx, r8
0x18003ce3a  mov     [rcx], r14w
0x18003ce3e  jz      loc_18003D345
0x18003ce44  mov     rdx, rdi
0x18003ce47  lea     rax, [rbp+620h+var_260]
0x18003ce4e  cmp     [rax], r14w
0x18003ce52  jz      short loc_18003CE5E
0x18003ce54  add     rax, 2
0x18003ce58  sub     rdx, 1
0x18003ce5c  jnz     short loc_18003CE4E
0x18003ce5e  mov     rax, rdx
  ... truncated ...
```
