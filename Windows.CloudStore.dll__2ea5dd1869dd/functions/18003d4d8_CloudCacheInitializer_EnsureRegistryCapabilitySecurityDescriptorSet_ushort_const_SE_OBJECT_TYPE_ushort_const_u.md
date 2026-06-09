# CloudCacheInitializer::EnsureRegistryCapabilitySecurityDescriptorSet(ushort const *,_SE_OBJECT_TYPE,ushort const *,ushort const *,bool)

- ea: `0x18003d4d8`
- end: `0x18003e0c7`
- name: `?EnsureRegistryCapabilitySecurityDescriptorSet@CloudCacheInitializer@@AEAAJPEBGW4_SE_OBJECT_TYPE@@00_N@Z`
- size: `3055`
- prototype: `int(CloudCacheInitializer *__hidden this, const unsigned __int16 *, enum _SE_OBJECT_TYPE, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c9d8`

## callees

- `0x18003b254`
- `0x18003bf2c`
- `0x18003d4d8`
- `0x1800959d0`
- `0x1800c7f8c`
- `0x1800c8458`
- `0x1800d1d50`
- `0x1800fc644`
- `0x1800ff298`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dc05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dcbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dc05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dcbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dc18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dcd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dc18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dcd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dbda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dc10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dcc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dd1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dd2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dd3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dedc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003df12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003df74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003df84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003df94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dbda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dc10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dcc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dd1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dd2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dd3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dedc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003df12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003df74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003df84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003df94`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003dcff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003dcff`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003d579`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003d579`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18003dec0`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18003dec0`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18003dc58`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18003dc58`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18003de7e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18003de7e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003de43`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003de43`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003d5a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003d5a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18003dc94`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18003dc94`

## string_xrefs

- `0x18003dbc1`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003ddf7`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003deee`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003df24`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003df3d`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003df56`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003dfcb`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003e012`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003e05c`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003e071`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003e0b6`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`

## pseudocode

```c
__int64 __fastcall CloudCacheInitializer::EnsureRegistryCapabilitySecurityDescriptorSet(
        CloudCacheInitializer *this,
        WCHAR *a2,
        enum _SE_OBJECT_TYPE a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        bool a6)
{
  __int64 v7; // rcx
  const wchar_t *v8; // rax
  unsigned __int64 v9; // r9
  int v10; // eax
  const char *v11; // r9
  BOOL v12; // r15d
  _QWORD *v13; // rdi
  LPWSTR v14; // r14
  void *v15; // rsi
  __int64 v16; // rdi
  const wchar_t *v17; // rcx
  WCHAR *v18; // r9
  __int64 v19; // rax
  __int64 v20; // r8
  WCHAR *v21; // rcx
  unsigned int v22; // ebx
  WCHAR *v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  const wchar_t *v26; // rcx
  bool v27; // zf
  __int64 v28; // r8
  __int64 v29; // rax
  WCHAR *v30; // r9
  WCHAR *v31; // rcx
  __int64 v32; // r8
  WCHAR *v33; // rax
  __int64 v34; // r9
  WCHAR *v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rax
  WCHAR *v38; // r9
  WCHAR *v39; // rcx
  __int64 v40; // r8
  WCHAR *v41; // rax
  __int64 v42; // r9
  const wchar_t *v43; // r11
  __int64 v44; // rax
  WCHAR *v45; // r10
  const wchar_t *v46; // rcx
  __int64 v47; // r8
  WCHAR *v48; // rcx
  __int64 v49; // r8
  WCHAR *v50; // rax
  __int64 v51; // r9
  const wchar_t *v52; // rcx
  __int64 v53; // rax
  WCHAR *v54; // r10
  __int64 v55; // r8
  WCHAR *v56; // rcx
  __int64 v57; // r8
  WCHAR *v58; // rax
  __int64 v59; // r9
  WCHAR *v61; // r10
  __int64 v62; // rax
  __int64 v63; // r8
  WCHAR *v64; // rcx
  __int64 v65; // r8
  WCHAR *v66; // rax
  __int64 v67; // r9
  __int64 v68; // rax
  __int64 v69; // r8
  WCHAR *v70; // r9
  WCHAR *v71; // rcx
  __int64 v72; // r8
  WCHAR *v73; // rax
  __int64 v74; // r9
  const wchar_t *v75; // rcx
  __int64 v76; // r8
  __int64 v77; // rax
  WCHAR *v78; // r9
  WCHAR *v79; // rcx
  __int64 v80; // r8
  WCHAR *v81; // rax
  __int64 v82; // r9
  const wchar_t *v83; // rcx
  __int64 v84; // r8
  __int64 v85; // rax
  WCHAR *v86; // r9
  WCHAR *v87; // rcx
  __int64 v88; // r8
  WCHAR *v89; // rax
  __int64 v90; // r9
  WCHAR *v91; // r8
  const wchar_t *v92; // rax
  __int64 v93; // rdx
  WCHAR *v94; // rcx
  __int64 v95; // rdx
  DWORD LastError; // ebx
  DWORD NamedSecurityInfoW; // eax
  const char *v99; // r9
  int v100; // edi
  _QWORD *v101; // rsi
  LPWSTR v102; // r15
  void *v103; // r14
  DWORD v104; // ebx
  int v105; // ecx
  __int64 v106; // r9
  const wchar_t *v107; // rcx
  __int64 v108; // r8
  __int64 v109; // rax
  WCHAR *v110; // r9
  WCHAR *v111; // rcx
  __int64 v112; // rdx
  BOOL v113; // ebx
  const char *v114; // r9
  DWORD v115; // eax
  __int64 v116; // rdx
  __int64 v117; // rdx
  int v118; // eax
  int ppsidGroup; // [rsp+20h] [rbp-E0h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-E0h]
  int ppsidGroupb; // [rsp+20h] [rbp-E0h]
  unsigned int ppsidGroupc; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  LPCWCH lpString1; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  void **p_hMem; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  char v129; // [rsp+70h] [rbp-90h]
  WINBOOL bDaclPresent; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+7Ch] [rbp-84h] BYREF
  PACL pDacl; // [rsp+80h] [rbp-80h] BYREF
  __int128 v133; // [rsp+88h] [rbp-78h] BYREF
  PACL ppDacl; // [rsp+98h] [rbp-68h] BYREF
  _BYTE Sid[48]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v136[48]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR String2[1024]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+958h] [rbp+858h]

  v133 = 0;
  v7 = 0x7FFF;
  v8 = L"cloudStore";
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0 ? 0xC000000D : 0;
  if ( !v7 )
  {
    v116 = 1144;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v116,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
             (const char *)v9,
             ppsidGroup);
  }
  *((_QWORD *)&v133 + 1) = L"cloudStore";
  LOWORD(v133) = -2 - 2 * v7;
  WORD1(v133) = -2 * v7;
  v10 = RtlDeriveCapabilitySidsFromName(&v133, v136, Sid, v9);
  if ( v10 < 0 )
  {
    v9 = (unsigned int)v10;
    v116 = 1151;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v116,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
             (const char *)v9,
             ppsidGroup);
  }
  hMem = 0;
  p_hMem = &hMem;
  StringSid = 0;
  v129 = 1;
  v12 = ConvertSidToStringSidW(Sid, &StringSid);
  if ( v129 )
  {
    v13 = p_hMem;
    v14 = StringSid;
    v15 = *p_hMem;
    if ( *p_hMem )
    {
      LastError = GetLastError();
      LocalFree(v15);
      SetLastError(LastError);
    }
    *v13 = v14;
  }
  if ( !v12 )
  {
    v22 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x483,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            v11);
    goto LABEL_176;
  }
  v16 = 2147483646;
  v17 = L"D:AI";
  v18 = String2;
  v19 = 2147483646;
  v20 = 1024;
  do
  {
    if ( !v19 )
      break;
    if ( !*v17 )
      break;
    *v18++ = *v17++;
    --v19;
    --v20;
  }
  while ( v20 );
  v21 = v18 - 1;
  v22 = v20 == 0 ? 0x8007007A : 0;
  if ( v20 )
    v21 = v18;
  *v21 = 0;
  if ( !v20 )
  {
    v112 = 1159;
    goto LABEL_175;
  }
  v23 = String2;
  v24 = 1024;
  if ( a6 )
  {
    do
    {
      if ( !*v23 )
        break;
      ++v23;
      --v24;
    }
    while ( v24 );
    v22 = v24 == 0 ? 0x80070057 : 0;
    v25 = (1024 - v24) & -(__int64)(v24 != 0);
    if ( v24 )
    {
      v26 = L"(A;CI;KA;;;";
      v28 = 1024 - v25;
      v27 = v25 == 1024;
      v29 = 2147483646;
      v30 = &String2[v25];
      if ( !v27 )
      {
        do
        {
          if ( !v29 )
            break;
          if ( !*v26 )
            break;
          *v30++ = *v26++;
          --v29;
          --v28;
        }
        while ( v28 );
      }
      v31 = v30 - 1;
      v22 = v28 == 0 ? 0x8007007A : 0;
      if ( v28 )
        v31 = v30;
      *v31 = 0;
      if ( v28 )
        goto LABEL_29;
    }
    v112 = 1164;
LABEL_175:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v112,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)v22,
      ppsidGroup);
LABEL_176:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    return v22;
  }
  do
  {
    if ( !*v23 )
      break;
    ++v23;
    --v24;
  }
  while ( v24 );
  v22 = v24 == 0 ? 0x80070057 : 0;
  v106 = (1024 - v24) & -(__int64)(v24 != 0);
  if ( !v24 )
    goto LABEL_148;
  v107 = L"(A;CIID;KA;;;";
  v108 = 1024 - v106;
  v27 = v106 == 1024;
  v109 = 2147483646;
  v110 = &String2[v106];
  if ( !v27 )
  {
    do
    {
      if ( !v109 )
        break;
      if ( !*v107 )
        break;
      *v110++ = *v107++;
      --v109;
      --v108;
    }
    while ( v108 );
  }
  v111 = v110 - 1;
  v22 = v108 == 0 ? 0x8007007A : 0;
  if ( v108 )
    v111 = v110;
  *v111 = 0;
  if ( !v108 )
  {
LABEL_148:
    v112 = 1168;
    goto LABEL_175;
  }
LABEL_29:
  v32 = 1024;
  v33 = String2;
  do
  {
    if ( !*v33 )
      break;
    ++v33;
    --v32;
  }
  while ( v32 );
  v22 = v32 == 0 ? 0x80070057 : 0;
  v34 = (1024 - v32) & -(__int64)(v32 != 0);
  if ( !v32 )
    goto LABEL_149;
  v35 = (WCHAR *)hMem;
  v36 = 1024 - v34;
  v27 = v34 == 1024;
  v37 = 2147483646;
  v38 = &String2[v34];
  if ( !v27 )
  {
    do
    {
      if ( !v37 )
        break;
      if ( !*v35 )
        break;
      *v38++ = *v35++;
      --v37;
      --v36;
    }
    while ( v36 );
  }
  v39 = v38 - 1;
  v22 = v36 == 0 ? 0x8007007A : 0;
  if ( v36 )
    v39 = v38;
  *v39 = 0;
  if ( !v36 )
  {
LABEL_149:
    v95 = 1170;
    goto LABEL_118;
  }
  v40 = 1024;
  v41 = String2;
  do
  {
    if ( !*v41 )
      break;
    ++v41;
    --v40;
  }
  while ( v40 );
  v22 = v40 == 0 ? 0x80070057 : 0;
  v42 = (1024 - v40) & -(__int64)(v40 != 0);
  if ( !v40 )
    goto LABEL_179;
  v43 = L")";
  v44 = 2147483646;
  v45 = &String2[v42];
  v46 = L")";
  v47 = 1024 - v42;
  if ( v42 != 1024 )
  {
    do
    {
      if ( !v44 )
        break;
      if ( !*v46 )
        break;
      *v45++ = *v46++;
      --v44;
      --v47;
    }
    while ( v47 );
  }
  v48 = v45 - 1;
  v22 = v47 == 0 ? 0x8007007A : 0;
  if ( v47 )
    v48 = v45;
  *v48 = 0;
  if ( !v47 )
  {
LABEL_179:
    v112 = 1171;
    goto LABEL_175;
  }
  v49 = 1024;
  v50 = String2;
  do
  {
    if ( !*v50 )
      break;
    ++v50;
    --v49;
  }
  while ( v49 );
  v22 = v49 == 0 ? 0x80070057 : 0;
  v51 = (1024 - v49) & -(__int64)(v49 != 0);
  if ( !v49 )
    goto LABEL_172;
  v52 = L"(A;OICIID;KA;;;";
  v53 = 2147483646;
  v54 = &String2[v51];
  v55 = 1024 - v51;
  if ( v51 != 1024 )
  {
    do
    {
      if ( !v53 )
        break;
      if ( !*v52 )
        break;
      *v54++ = *v52++;
      --v53;
      --v55;
    }
    while ( v55 );
  }
  v56 = v54 - 1;
  v22 = v55 == 0 ? 0x8007007A : 0;
  if ( v55 )
    v56 = v54;
  *v56 = 0;
  if ( !v55 )
  {
LABEL_172:
    v95 = 1174;
    goto LABEL_118;
  }
  v57 = 1024;
  v58 = String2;
  do
  {
    if ( !*v58 )
      break;
    ++v58;
    --v57;
  }
  while ( v57 );
  v22 = v57 == 0 ? 0x80070057 : 0;
  v59 = (1024 - v57) & -(__int64)(v57 != 0);
  if ( !v57 )
    goto LABEL_173;
  v61 = &String2[v59];
  v62 = 2147483646;
  v63 = 1024 - v59;
  if ( v59 != 1024 )
  {
    do
    {
      if ( !v62 )
        break;
      if ( !*a5 )
        break;
      *v61++ = *a5++;
      --v62;
      --v63;
    }
    while ( v63 );
  }
  v64 = v61 - 1;
  v22 = v63 == 0 ? 0x8007007A : 0;
  if ( v63 )
    v64 = v61;
  *v64 = 0;
  if ( !v63 )
  {
LABEL_173:
    v95 = 1175;
    goto LABEL_118;
  }
  v65 = 1024;
  v66 = String2;
  do
  {
    if ( !*v66 )
      break;
    ++v66;
    --v65;
  }
  while ( v65 );
  v22 = v65 == 0 ? 0x80070057 : 0;
  v67 = (1024 - v65) & -(__int64)(v65 != 0);
  if ( !v65 )
    goto LABEL_178;
  v68 = 2147483646;
  v69 = 1024 - v67;
  v27 = v67 == 1024;
  v70 = &String2[v67];
  if ( !v27 )
  {
    do
    {
      if ( !v68 )
        break;
      if ( !*v43 )
        break;
      *v70++ = *v43++;
      --v68;
      --v69;
    }
    while ( v69 );
  }
  v71 = v70 - 1;
  v22 = v69 == 0 ? 0x8007007A : 0;
  if ( v69 )
    v71 = v70;
  *v71 = 0;
  if ( !v69 )
  {
LABEL_178:
    v112 = 1176;
    goto LABEL_175;
  }
  v72 = 1024;
  v73 = String2;
  do
  {
    if ( !*v73 )
      break;
    ++v73;
    --v72;
  }
  while ( v72 );
  v22 = v72 == 0 ? 0x80070057 : 0;
  v74 = (1024 - v72) & -(__int64)(v72 != 0);
  if ( !v72 )
    goto LABEL_171;
  v75 = L"(A;OICIID;KA;;;SY)";
  v76 = 1024 - v74;
  v27 = v74 == 1024;
  v77 = 2147483646;
  v78 = &String2[v74];
  if ( !v27 )
  {
    do
    {
      if ( !v77 )
        break;
      if ( !*v75 )
        break;
      *v78++ = *v75++;
      --v77;
      --v76;
    }
    while ( v76 );
  }
  v79 = v78 - 1;
  v22 = v76 == 0 ? 0x8007007A : 0;
  if ( v76 )
    v79 = v78;
  *v79 = 0;
  if ( !v76 )
  {
LABEL_171:
    v95 = 1179;
    goto LABEL_118;
  }
  v80 = 1024;
  v81 = String2;
  do
  {
    if ( !*v81 )
      break;
    ++v81;
    --v80;
  }
  while ( v80 );
  v22 = v80 == 0 ? 0x80070057 : 0;
  v82 = (1024 - v80) & -(__int64)(v80 != 0);
  if ( !v80 )
    goto LABEL_177;
  v83 = L"(A;OICIID;KA;;;BA)";
  v84 = 1024 - v82;
  v27 = v82 == 1024;
  v85 = 2147483646;
  v86 = &String2[v82];
  if ( !v27 )
  {
    do
    {
      if ( !v85 )
        break;
      if ( !*v83 )
        break;
      *v86++ = *v83++;
      --v85;
      --v84;
    }
    while ( v84 );
  }
  v87 = v86 - 1;
  v22 = v84 == 0 ? 0x8007007A : 0;
  if ( v84 )
    v87 = v86;
  *v87 = 0;
  if ( !v84 )
  {
LABEL_177:
    v112 = 1180;
    goto LABEL_175;
  }
  v88 = 1024;
  v89 = String2;
  do
  {
    if ( !*v89 )
      break;
    ++v89;
    --v88;
  }
  while ( v88 );
  v22 = v88 == 0 ? 0x80070057 : 0;
  v90 = (1024 - v88) & -(__int64)(v88 != 0);
  if ( !v88 )
    goto LABEL_117;
  v91 = &String2[v90];
  v92 = L"(A;OICIID;KR;;;RC)";
  v93 = 1024 - v90;
  if ( 1024 != v90 )
  {
    do
    {
      if ( !v16 )
        break;
      if ( !*v92 )
        break;
      *v91++ = *v92++;
      --v16;
      --v93;
    }
    while ( v93 );
  }
  v94 = v91 - 1;
  v22 = v93 == 0 ? 0x8007007A : 0;
  if ( v93 )
    v94 = v91;
  *v94 = 0;
  if ( !v93 )
  {
LABEL_117:
    v95 = 1181;
LABEL_118:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v95,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)v22,
      ppsidGroup);
LABEL_119:
    if ( hMem )
      LocalFree(hMem);
    return v22;
  }
  ppDacl = 0;
  SecurityDescriptor = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a2, SE_REGISTRY_KEY, 4u, 0, 0, &ppDacl, 0, &SecurityDescriptor);
  if ( NamedSecurityInfoW )
  {
    v22 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4A2,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            (const char *)NamedSecurityInfoW,
            ppsidGroupa);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_119;
  }
  p_hMem = (void **)&lpString1;
  lpString1 = 0;
  v129 = 1;
  StringSid = 0;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(SecurityDescriptor, 1u, 4u, &StringSid, 0) )
    v100 = 0;
  else
    v100 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5B7,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
             v99);
  if ( v129 )
  {
    v101 = p_hMem;
    v102 = StringSid;
    v103 = *p_hMem;
    if ( *p_hMem )
    {
      v104 = GetLastError();
      LocalFree(v103);
      SetLastError(v104);
    }
    *v101 = v102;
  }
  if ( v100 >= 0 )
  {
    if ( CompareStringOrdinal(lpString1, -1, String2, -1, 0) == 2 )
    {
LABEL_131:
      if ( lpString1 )
        LocalFree((HLOCAL)lpString1);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      if ( hMem )
        LocalFree(hMem);
      return 0;
    }
    if ( (Microsoft_Windows_CloudStoreEnableBits & 2) != 0 )
      McTemplateU0zzz_EventWriteTransfer(v105, 2, (_DWORD)a2, (_DWORD)lpString1, (__int64)String2);
    pSecurityDescriptor = 0;
    p_hMem = &pSecurityDescriptor;
    StringSid = 0;
    v129 = 1;
    v113 = ConvertStringSecurityDescriptorToSecurityDescriptorW(String2, 1u, (PSECURITY_DESCRIPTOR *)&StringSid, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_hMem);
    if ( v113 )
    {
      bDaclPresent = 0;
      pDacl = 0;
      bDaclDefaulted = 0;
      if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        if ( !bDaclPresent )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x4B2,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            v114);
        if ( bDaclDefaulted )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x4B3,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            v114);
        v115 = SetNamedSecurityInfoW(a2, SE_REGISTRY_KEY, 4u, 0, 0, pDacl, 0);
        if ( !v115 )
        {
          if ( pSecurityDescriptor )
            LocalFree(pSecurityDescriptor);
          goto LABEL_131;
        }
        v118 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x4B4,
                 (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
                 (const char *)v115,
                 ppsidGroupc);
        goto LABEL_187;
      }
      v117 = 1201;
    }
    else
    {
      v117 = 1196;
    }
    v118 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v117,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
             v114);
LABEL_187:
    v22 = v118;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
    goto LABEL_176;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4A6,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
    (const char *)(unsigned int)v100,
    ppsidGroupb);
  if ( lpString1 )
    LocalFree((HLOCAL)lpString1);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v100;
}

```

## disassembly

```asm
0x18003d4d8  push    rbp
0x18003d4da  push    rbx
0x18003d4db  push    rsi
0x18003d4dc  push    rdi
0x18003d4dd  push    r12
0x18003d4df  push    r13
0x18003d4e1  push    r14
0x18003d4e3  push    r15
0x18003d4e5  lea     rbp, [rsp-818h]
0x18003d4ed  sub     rsp, 918h
0x18003d4f4  mov     rax, cs:__security_cookie
0x18003d4fb  xor     rax, rsp
0x18003d4fe  mov     [rbp+850h+var_50], rax
0x18003d505  xor     r13d, r13d
0x18003d508  lea     r8, aCloudstore; "cloudStore"
0x18003d50f  xorps   xmm0, xmm0
0x18003d512  mov     r12, rdx
0x18003d515  movups  [rbp+850h+var_8C8], xmm0
0x18003d519  mov     ecx, 7FFFh
0x18003d51e  mov     rax, r8
0x18003d521  lea     edx, [r13+2]
0x18003d525  lea     r14d, [r13+1]
0x18003d529  cmp     [rax], r13w
0x18003d52d  jz      short loc_18003D537
0x18003d52f  add     rax, rdx
0x18003d532  sub     rcx, r14
0x18003d535  jnz     short loc_18003D529
0x18003d537  mov     rax, rcx
0x18003d53a  neg     rax
0x18003d53d  sbb     r9d, r9d
0x18003d540  not     r9d
0x18003d543  and     r9d, 0C000000Dh; char *
0x18003d54a  test    rcx, rcx
0x18003d54d  jz      loc_18003E0AA
0x18003d553  add     cx, cx
0x18003d556  mov     qword ptr [rbp+850h+var_8C8+8], r8
0x18003d55a  mov     eax, 0FFFEh
0x18003d55f  lea     r8, [rbp+850h+Sid]
0x18003d563  sub     ax, cx
0x18003d566  lea     rcx, [rbp+850h+var_8C8]
0x18003d56a  mov     word ptr [rbp+850h+var_8C8], ax
0x18003d56e  add     ax, dx
0x18003d571  lea     rdx, [rbp+850h+var_880]
0x18003d575  mov     word ptr [rbp+850h+var_8C8+2], ax
0x18003d579  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18003d57f  test    eax, eax
0x18003d581  js      loc_18003DFFE
0x18003d587  lea     rax, [rsp+950h+hMem]
0x18003d58c  mov     [rsp+950h+hMem], r13
0x18003d591  lea     rdx, [rsp+950h+StringSid]; StringSid
0x18003d596  mov     [rsp+950h+var_8F0], rax
0x18003d59b  lea     rcx, [rbp+850h+Sid]; Sid
0x18003d59f  mov     [rsp+950h+StringSid], r13
0x18003d5a4  mov     [rsp+950h+var_8E0], r14b
0x18003d5a9  call    cs:__imp_ConvertSidToStringSidW
0x18003d5af  mov     r15d, eax
0x18003d5b2  cmp     [rsp+950h+var_8E0], r13b
0x18003d5b7  jz      short loc_18003D5D8
0x18003d5b9  mov     rdi, [rsp+950h+var_8F0]
0x18003d5be  mov     r14, [rsp+950h+StringSid]
0x18003d5c3  mov     rsi, [rdi]
0x18003d5c6  test    rsi, rsi
0x18003d5c9  jnz     loc_18003DC05
0x18003d5cf  mov     [rdi], r14
0x18003d5d2  mov     r14d, 1
0x18003d5d8  test    r15d, r15d
0x18003d5db  jz      loc_18003E00B
0x18003d5e1  mov     edi, 7FFFFFFEh
0x18003d5e6  lea     rcx, aDAi; "D:AI"
0x18003d5ed  mov     edx, 400h
0x18003d5f2  lea     r9, [rbp+850h+String2]
0x18003d5f6  mov     eax, edi
0x18003d5f8  mov     r8d, edx
0x18003d5fb  mov     r15d, 2
0x18003d601  test    rax, rax
0x18003d604  jz      short loc_18003D622
0x18003d606  movzx   r10d, word ptr [rcx]
0x18003d60a  test    r10w, r10w
0x18003d60e  jz      short loc_18003D622
0x18003d610  mov     [r9], r10w
0x18003d614  add     rcx, r15
0x18003d617  add     r9, r15
0x18003d61a  sub     rax, r14
0x18003d61d  sub     r8, r14
0x18003d620  jnz     short loc_18003D601
0x18003d622  mov     rax, r8
0x18003d625  lea     rcx, [r9-2]
0x18003d629  neg     rax
0x18003d62c  sbb     ebx, ebx
0x18003d62e  not     ebx
0x18003d630  and     ebx, 8007007Ah
0x18003d636  test    r8, r8
0x18003d639  cmovnz  rcx, r9
0x18003d63d  mov     [rcx], r13w
0x18003d641  jz      loc_18003E027
0x18003d647  lea     rax, [rbp+850h+String2]
0x18003d64b  mov     r8, rdx
0x18003d64e  cmp     [rbp+850h+arg_28], r13b
0x18003d655  jz      loc_18003DD49
0x18003d65b  cmp     [rax], r13w
0x18003d65f  jz      short loc_18003D669
0x18003d661  add     rax, r15
0x18003d664  sub     r8, r14
0x18003d667  jnz     short loc_18003D65B
0x18003d669  mov     rax, r8
0x18003d66c  mov     esi, 80070057h
0x18003d671  neg     rax
0x18003d674  mov     rcx, rdx
0x18003d677  mov     rax, r8
0x18003d67a  sbb     ebx, ebx
0x18003d67c  sub     rcx, r8
0x18003d67f  not     ebx
0x18003d681  and     ebx, esi
0x18003d683  neg     rax
0x18003d686  sbb     r9, r9
0x18003d689  and     r9, rcx
0x18003d68c  test    r8, r8
0x18003d68f  jz      loc_18003DFBF
0x18003d695  mov     r8, rdx
0x18003d698  lea     rcx, aACiKa; "(A;CI;KA;;;"
0x18003d69f  sub     r8, r9
0x18003d6a2  mov     rax, rdi
0x18003d6a5  lea     r9, [rbp+r9*2+850h+String2]
0x18003d6aa  jz      short loc_18003D6CD
0x18003d6ac  test    rax, rax
0x18003d6af  jz      short loc_18003D6CD
0x18003d6b1  movzx   r10d, word ptr [rcx]
0x18003d6b5  test    r10w, r10w
0x18003d6b9  jz      short loc_18003D6CD
0x18003d6bb  mov     [r9], r10w
0x18003d6bf  add     rcx, r15
0x18003d6c2  add     r9, r15
0x18003d6c5  sub     rax, r14
0x18003d6c8  sub     r8, r14
0x18003d6cb  jnz     short loc_18003D6AC
0x18003d6cd  mov     rax, r8
0x18003d6d0  lea     rcx, [r9-2]
0x18003d6d4  neg     rax
0x18003d6d7  sbb     ebx, ebx
0x18003d6d9  not     ebx
0x18003d6db  and     ebx, 8007007Ah
0x18003d6e1  test    r8, r8
0x18003d6e4  cmovnz  rcx, r9
0x18003d6e8  mov     [rcx], r13w
0x18003d6ec  jz      loc_18003DFBF
0x18003d6f2  mov     r8, rdx
0x18003d6f5  lea     rax, [rbp+850h+String2]
0x18003d6f9  cmp     [rax], r13w
0x18003d6fd  jz      short loc_18003D707
0x18003d6ff  add     rax, r15
0x18003d702  sub     r8, r14
0x18003d705  jnz     short loc_18003D6F9
0x18003d707  mov     rax, r8
0x18003d70a  mov     rcx, rdx
0x18003d70d  neg     rax
0x18003d710  mov     rax, r8
0x18003d713  sbb     ebx, ebx
0x18003d715  sub     rcx, r8
0x18003d718  not     ebx
0x18003d71a  and     ebx, esi
0x18003d71c  neg     rax
0x18003d71f  sbb     r9, r9
0x18003d722  and     r9, rcx
0x18003d725  test    r8, r8
0x18003d728  jz      loc_18003DDE6
0x18003d72e  mov     rcx, [rsp+950h+hMem]
0x18003d733  mov     r8, rdx
0x18003d736  sub     r8, r9
0x18003d739  mov     rax, rdi
0x18003d73c  lea     r9, [rbp+r9*2+850h+String2]
0x18003d741  jz      short loc_18003D764
0x18003d743  test    rax, rax
0x18003d746  jz      short loc_18003D764
0x18003d748  movzx   r10d, word ptr [rcx]
0x18003d74c  test    r10w, r10w
0x18003d750  jz      short loc_18003D764
0x18003d752  mov     [r9], r10w
0x18003d756  add     rcx, r15
0x18003d759  add     r9, r15
0x18003d75c  sub     rax, r14
0x18003d75f  sub     r8, r14
0x18003d762  jnz     short loc_18003D743
0x18003d764  mov     rax, r8
0x18003d767  lea     rcx, [r9-2]
0x18003d76b  neg     rax
0x18003d76e  sbb     ebx, ebx
0x18003d770  not     ebx
0x18003d772  and     ebx, 8007007Ah
0x18003d778  test    r8, r8
0x18003d77b  cmovnz  rcx, r9
0x18003d77f  mov     [rcx], r13w
0x18003d783  jz      loc_18003DDE6
0x18003d789  mov     r8, rdx
0x18003d78c  lea     rax, [rbp+850h+String2]
0x18003d790  cmp     [rax], r13w
0x18003d794  jz      short loc_18003D79E
0x18003d796  add     rax, r15
0x18003d799  sub     r8, r14
0x18003d79c  jnz     short loc_18003D790
0x18003d79e  mov     rax, r8
0x18003d7a1  mov     rcx, rdx
0x18003d7a4  neg     rax
0x18003d7a7  mov     rax, r8
0x18003d7aa  sbb     ebx, ebx
0x18003d7ac  sub     rcx, r8
0x18003d7af  not     ebx
0x18003d7b1  and     ebx, esi
0x18003d7b3  neg     rax
0x18003d7b6  sbb     r9, r9
0x18003d7b9  and     r9, rcx
0x18003d7bc  test    r8, r8
0x18003d7bf  jz      loc_18003DFF7
0x18003d7c5  mov     r8, rdx
0x18003d7c8  lea     r11, asc_180229024; ")"
0x18003d7cf  lea     r10, [rbp+850h+String2]
0x18003d7d3  mov     rax, rdi
0x18003d7d6  lea     r10, [r10+r9*2]
0x18003d7da  mov     rcx, r11
0x18003d7dd  sub     r8, r9
0x18003d7e0  jz      short loc_18003D803
0x18003d7e2  test    rax, rax
0x18003d7e5  jz      short loc_18003D803
0x18003d7e7  movzx   r9d, word ptr [rcx]
0x18003d7eb  test    r9w, r9w
0x18003d7ef  jz      short loc_18003D803
0x18003d7f1  mov     [r10], r9w
0x18003d7f5  add     rcx, r15
0x18003d7f8  add     r10, r15
0x18003d7fb  sub     rax, r14
0x18003d7fe  sub     r8, r14
0x18003d801  jnz     short loc_18003D7E2
0x18003d803  mov     rax, r8
0x18003d806  lea     rcx, [r10-2]
0x18003d80a  neg     rax
0x18003d80d  sbb     ebx, ebx
0x18003d80f  not     ebx
0x18003d811  and     ebx, 8007007Ah
0x18003d817  test    r8, r8
0x18003d81a  cmovnz  rcx, r10
0x18003d81e  mov     [rcx], r13w
0x18003d822  jz      loc_18003DFF7
0x18003d828  mov     r8, rdx
0x18003d82b  lea     rax, [rbp+850h+String2]
0x18003d82f  cmp     [rax], r13w
0x18003d833  jz      short loc_18003D83D
0x18003d835  add     rax, r15
0x18003d838  sub     r8, r14
0x18003d83b  jnz     short loc_18003D82F
0x18003d83d  mov     rax, r8
0x18003d840  mov     rcx, rdx
0x18003d843  neg     rax
0x18003d846  mov     rax, r8
0x18003d849  sbb     ebx, ebx
0x18003d84b  sub     rcx, r8
0x18003d84e  not     ebx
0x18003d850  and     ebx, esi
0x18003d852  neg     rax
0x18003d855  sbb     r9, r9
0x18003d858  and     r9, rcx
0x18003d85b  test    r8, r8
0x18003d85e  jz      loc_18003DFAB
0x18003d864  mov     r8, rdx
0x18003d867  lea     r10, [rbp+850h+String2]
0x18003d86b  lea     rcx, aAOiciidKa; "(A;OICIID;KA;;;"
0x18003d872  mov     rax, rdi
0x18003d875  lea     r10, [r10+r9*2]
0x18003d879  sub     r8, r9
0x18003d87c  jz      short loc_18003D89F
0x18003d87e  test    rax, rax
0x18003d881  jz      short loc_18003D89F
0x18003d883  movzx   r9d, word ptr [rcx]
0x18003d887  test    r9w, r9w
0x18003d88b  jz      short loc_18003D89F
0x18003d88d  mov     [r10], r9w
0x18003d891  add     rcx, r15
0x18003d894  add     r10, r15
0x18003d897  sub     rax, r14
0x18003d89a  sub     r8, r14
0x18003d89d  jnz     short loc_18003D87E
0x18003d89f  mov     rax, r8
0x18003d8a2  lea     rcx, [r10-2]
0x18003d8a6  neg     rax
0x18003d8a9  sbb     ebx, ebx
0x18003d8ab  not     ebx
0x18003d8ad  and     ebx, 8007007Ah
0x18003d8b3  test    r8, r8
0x18003d8b6  cmovnz  rcx, r10
0x18003d8ba  mov     [rcx], r13w
0x18003d8be  jz      loc_18003DFAB
0x18003d8c4  mov     r8, rdx
0x18003d8c7  lea     rax, [rbp+850h+String2]
0x18003d8cb  cmp     [rax], r13w
0x18003d8cf  jz      short loc_18003D8D9
0x18003d8d1  add     rax, r15
0x18003d8d4  sub     r8, r14
0x18003d8d7  jnz     short loc_18003D8CB
0x18003d8d9  mov     rax, r8
0x18003d8dc  mov     rcx, rdx
0x18003d8df  neg     rax
0x18003d8e2  mov     rax, r8
  ... truncated ...
```
