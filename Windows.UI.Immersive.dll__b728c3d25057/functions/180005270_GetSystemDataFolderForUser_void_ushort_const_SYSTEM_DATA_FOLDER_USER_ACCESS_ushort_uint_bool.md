# GetSystemDataFolderForUser(void *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort *,uint,bool)

- ea: `0x180005270`
- end: `0x180006202`
- name: `?GetSystemDataFolderForUser@@YAJPEAXPEBGW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEAGI_N@Z`
- size: `3986`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004ae8`
- `0x18000b3cc`
- `0x18000b458`
- `0x18000bf20`

## callees

- `0x180005270`
- `0x180006210`
- `0x1800064d4`
- `0x18000d2b8`
- `0x18003aa84`
- `0x180050ba0`
- `0x180051524`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800053e4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800056c6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005a35`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005be6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800060c1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180006117`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000616d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800061ed`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800053e4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800056c6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005a35`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005be6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800060c1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180006117`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000616d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800061ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005483`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000574f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000589b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005ac8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005c89`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005f19`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005fce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005483`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000574f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000589b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005ac8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005c89`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005f19`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005fce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000562e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000598f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005fe0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000562e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000598f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005fe0`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005571`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005833`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800058d2`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005db6`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005eb1`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005f66`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005571`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005833`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800058d2`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005db6`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005eb1`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005f66`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800055d6`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180005937`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180005e1b`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800055d6`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180005937`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180005e1b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800053c8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800056aa`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180005a17`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180005bc7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800053c8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800056aa`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180005a17`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180005bc7`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005407`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800056e9`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005a58`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005c09`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005407`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800056e9`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005a58`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005c09`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005619`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000597a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005e5e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005619`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000597a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005e5e`
- `SHELL32!SHGetKnownFolderPath` at `0x1800052e4`
- `SHELL32!SHGetKnownFolderPath` at `0x1800052e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000558b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800058ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000558b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800058ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005ee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005ee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f9c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800055ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000591b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180005dff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800055ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000591b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180005dff`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800052bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800052bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000585c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180005eda`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180005f8f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000585c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180005eda`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180005f8f`

## pseudocode

```c
__int64 __fastcall GetSystemDataFolderForUser(
        void *a1,
        const WCHAR *a2,
        unsigned int a3,
        _WORD *a4,
        __int64 a5,
        char a6)
{
  _WORD *v6; // r14
  PWSTR v7; // rcx
  WCHAR *v8; // r9
  PWSTR v9; // r8
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // rbx
  WCHAR *v14; // rdx
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // r8
  WCHAR *v18; // r9
  WCHAR *v19; // rcx
  wchar_t *i; // rax
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  WCHAR *v24; // r9
  __int64 v25; // rdx
  WCHAR *v26; // r8
  WCHAR *v27; // rcx
  const wchar_t *v28; // rdx
  WCHAR *v29; // r9
  __int64 v30; // rcx
  __int64 v31; // r8
  WCHAR *v32; // rcx
  int Error; // ebx
  void *v34; // rax
  void *v35; // r15
  __int64 v36; // rcx
  WCHAR *v37; // rdx
  __int64 v38; // r8
  WCHAR *v39; // r9
  WCHAR *v40; // rcx
  wchar_t *j; // rax
  unsigned __int64 v42; // rbx
  unsigned __int64 v43; // rax
  __int64 v44; // rcx
  WCHAR *v45; // rdx
  __int64 v46; // r8
  WCHAR *v47; // r9
  WCHAR *v48; // rcx
  __int64 result; // rax
  bool v50; // r12
  size_t v51; // rax
  void *v52; // rax
  void *v53; // r15
  int v54; // ebx
  __int64 v55; // rcx
  WCHAR *v56; // rdx
  __int64 v57; // r8
  WCHAR *v58; // r9
  WCHAR *v59; // rcx
  LPWSTR v60; // r12
  __int64 v61; // r15
  HRESULT v62; // ebx
  wchar_t *v63; // rax
  unsigned __int64 v64; // rax
  unsigned __int64 v65; // rbx
  __int64 v66; // rcx
  WCHAR *v67; // rdx
  __int64 v68; // r8
  WCHAR *v69; // r9
  WCHAR *v70; // rcx
  const WCHAR *v71; // r10
  __int64 v72; // rcx
  WCHAR *v73; // r8
  __int64 v74; // rdx
  WCHAR *v75; // r9
  WCHAR *v76; // rcx
  HRESULT v77; // r15d
  LPWSTR v78; // r12
  wchar_t *v79; // rax
  unsigned __int64 v80; // rax
  unsigned __int64 v81; // rbx
  __int64 v82; // rax
  WCHAR *v83; // rdx
  __int64 v84; // r9
  WCHAR *v85; // r10
  WCHAR *v86; // rcx
  const wchar_t *v87; // rdx
  WCHAR *v88; // r9
  __int64 v89; // rcx
  __int64 v90; // r8
  WCHAR *v91; // rcx
  void *v92; // rax
  void *v93; // r15
  bool v94; // r12
  size_t v95; // rax
  bool v96; // r12
  size_t v97; // rax
  WCHAR *v98; // rcx
  _WORD *v99; // rcx
  const wchar_t *v100; // rdx
  WCHAR *v101; // r9
  __int64 v102; // rcx
  __int64 v103; // r8
  WCHAR *v104; // rcx
  DWORD nLengthNeeded[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v107; // [rsp+40h] [rbp-C0h]
  unsigned int v108; // [rsp+44h] [rbp-BCh]
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR ppszPath; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v112; // [rsp+70h] [rbp-90h]
  PCWSTR pszMore; // [rsp+78h] [rbp-88h]
  WCHAR String1[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPathOut[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR pszPath[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  pszMore = a2;
  *a4 = 0;
  StringSid = 0;
  v6 = a4;
  v112 = a4;
  v107 = a3;
  if ( ConvertSidToStringSidW(a1, &StringSid) )
  {
    v108 = 0;
LABEL_3:
    ppszPath = 0;
    if ( SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, &ppszPath) < 0 )
      goto LABEL_81;
    v7 = ppszPath;
    v8 = String1;
    v9 = ppszPath;
    v10 = 2147483646;
    v11 = 2147483646;
    v12 = 260;
    v13 = 260;
    do
    {
      if ( !v11 )
        break;
      if ( !*v9 )
        break;
      *v8++ = *v9++;
      --v11;
      --v13;
    }
    while ( v13 );
    v14 = v8 - 1;
    if ( v13 )
      v14 = v8;
    *v14 = 0;
    CoTaskMemFree(v7);
    ppszPath = 0;
    if ( !v13 )
      goto LABEL_81;
    v15 = 2147483646;
    v16 = String1;
    v17 = 260;
    v18 = pszPath;
    do
    {
      if ( !v15 )
        break;
      if ( !*v16 )
        break;
      *v18++ = *v16++;
      --v15;
      --v17;
    }
    while ( v17 );
    v19 = v18 - 1;
    if ( v17 )
      v19 = v18;
    *v19 = 0;
    if ( !v17 || PathCchAppend(pszPath, 0x104u, L"Microsoft\\Windows\\SystemData") < 0 )
      goto LABEL_81;
    for ( i = wcsstr(pszPath, L"/"); i; i = wcsstr(i, L"/") )
      *i = 92;
    if ( PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0) < 0 )
      goto LABEL_81;
    v21 = -1;
    do
      ++v21;
    while ( String1[v21] );
    if ( v21 > 0xFFFFFFFF )
      goto LABEL_81;
    v22 = -1;
    do
      ++v22;
    while ( pszPathOut[v22] );
    if ( v22 > 0xFFFFFFFF
      || (unsigned int)v22 <= (unsigned int)v21
      || CompareStringOrdinal(String1, v21, pszPathOut, v21, 0) != 2
      || pszPathOut[(unsigned int)v21] != 92 )
    {
      goto LABEL_81;
    }
    v23 = 2147483646;
    v24 = pszPathOut;
    v25 = 260;
    v26 = String1;
    do
    {
      if ( !v23 )
        break;
      if ( !*v24 )
        break;
      *v26++ = *v24++;
      --v23;
      --v25;
    }
    while ( v25 );
    v27 = v26 - 1;
    if ( v25 )
      v27 = v26;
    *v27 = 0;
    if ( !v25 )
      goto LABEL_81;
    if ( a6 )
    {
      v28 = L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)";
      v29 = pszPathOut;
      v30 = 2147483646;
      v31 = 260;
      do
      {
        if ( !v30 )
          break;
        if ( !*v28 )
          break;
        *v29++ = *v28++;
        --v30;
        --v31;
      }
      while ( v31 );
      v32 = v29 - 1;
      Error = -2147024774;
      if ( v31 )
      {
        v32 = v29;
        Error = 0;
      }
      *v32 = 0;
      if ( v31 )
      {
        nLengthNeeded[0] = 0;
        if ( GetFileSecurityW(String1, 7u, 0, 0, nLengthNeeded) )
          goto LABEL_48;
        if ( (unsigned int)ResultFromKnownLastError() != -2147024774 )
          goto LABEL_48;
        v34 = CoTaskMemAlloc(nLengthNeeded[0]);
        v35 = v34;
        if ( !v34 )
          goto LABEL_48;
        v50 = 0;
        v51 = CTCoAllocPolicy::_CoTaskMemSize(v34);
        memset_0(v35, 0, v51);
        if ( GetFileSecurityW(String1, 7u, v35, nLengthNeeded[0], nLengthNeeded) )
        {
          StringSecurityDescriptor = 0;
          if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v35, 1u, 7u, &StringSecurityDescriptor, 0) )
          {
            v50 = CompareStringOrdinal(StringSecurityDescriptor, -1, pszPathOut, -1, 1) == 2;
            LocalFree(StringSecurityDescriptor);
          }
        }
        CoTaskMemFree(v35);
        if ( !v50 )
        {
LABEL_48:
          *(_QWORD *)nLengthNeeded = 0;
          if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                 pszPathOut,
                 1u,
                 (PSECURITY_DESCRIPTOR *)nLengthNeeded,
                 0)
            || (Error = ResultFromKnownLastError(), Error >= 0) )
          {
            if ( SetFileSecurityW(String1, 7u, *(PSECURITY_DESCRIPTOR *)nLengthNeeded) )
            {
              Error = 0;
            }
            else
            {
              Error = ResultFromKnownLastError();
              if ( Error == -2147024894 )
              {
                SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)nLengthNeeded;
                *(_QWORD *)&SecurityAttributes.nLength = 24;
                *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
                if ( CreateDirectoryW(String1, &SecurityAttributes) )
                  Error = 0;
                else
                  Error = ResultFromKnownLastError();
              }
              else if ( Error == -2147024891 )
              {
                Error = 0;
              }
            }
            LocalFree(*(HLOCAL *)nLengthNeeded);
          }
        }
      }
      if ( Error < 0 )
        goto LABEL_81;
    }
    v36 = 2147483646;
    v37 = String1;
    v38 = 260;
    v39 = pszPath;
    do
    {
      if ( !v36 )
        break;
      if ( !*v37 )
        break;
      *v39++ = *v37++;
      --v36;
      --v38;
    }
    while ( v38 );
    v40 = v39 - 1;
    if ( v38 )
      v40 = v39;
    *v40 = 0;
    if ( !v38 || PathCchAppend(pszPath, 0x104u, StringSid) < 0 )
      goto LABEL_81;
    for ( j = wcsstr(pszPath, L"/"); j; j = wcsstr(j, L"/") )
      *j = 92;
    if ( PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0) < 0 )
      goto LABEL_81;
    v42 = -1;
    do
      ++v42;
    while ( String1[v42] );
    if ( v42 > 0xFFFFFFFF )
      goto LABEL_81;
    v43 = -1;
    do
      ++v43;
    while ( pszPathOut[v43] );
    if ( v43 > 0xFFFFFFFF
      || (unsigned int)v43 <= (unsigned int)v42
      || CompareStringOrdinal(String1, v42, pszPathOut, v42, 0) != 2
      || pszPathOut[(unsigned int)v42] != 92 )
    {
      goto LABEL_81;
    }
    v44 = 2147483646;
    v45 = pszPathOut;
    v46 = 260;
    v47 = String1;
    do
    {
      if ( !v44 )
        break;
      if ( !*v45 )
        break;
      *v47++ = *v45++;
      --v44;
      --v46;
    }
    while ( v46 );
    v48 = v47 - 1;
    if ( v46 )
      v48 = v47;
    *v48 = 0;
    if ( !v46 )
      goto LABEL_81;
    if ( a6 )
    {
      v100 = L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)";
      v101 = pszPathOut;
      v102 = 2147483646;
      v103 = 260;
      do
      {
        if ( !v102 )
          break;
        if ( !*v100 )
          break;
        *v101++ = *v100++;
        --v102;
        --v103;
      }
      while ( v103 );
      v104 = v101 - 1;
      v54 = -2147024774;
      if ( v103 )
      {
        v104 = v101;
        v54 = 0;
      }
      *v104 = 0;
      if ( v103 )
      {
        nLengthNeeded[0] = 0;
        if ( GetFileSecurityW(String1, 7u, 0, 0, nLengthNeeded) )
          goto LABEL_91;
        if ( (unsigned int)ResultFromKnownLastError() != -2147024774 )
          goto LABEL_91;
        v52 = CoTaskMemAlloc(nLengthNeeded[0]);
        v53 = v52;
        if ( !v52 )
          goto LABEL_91;
        v94 = 0;
        v95 = CTCoAllocPolicy::_CoTaskMemSize(v52);
        memset_0(v53, 0, v95);
        if ( GetFileSecurityW(String1, 7u, v53, nLengthNeeded[0], nLengthNeeded) )
        {
          StringSecurityDescriptor = 0;
          if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v53, 1u, 7u, &StringSecurityDescriptor, 0) )
          {
            v94 = CompareStringOrdinal(StringSecurityDescriptor, -1, pszPathOut, -1, 1) == 2;
            LocalFree(StringSecurityDescriptor);
          }
        }
        CoTaskMemFree(v53);
        if ( !v94 )
        {
LABEL_91:
          *(_QWORD *)nLengthNeeded = 0;
          if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                 pszPathOut,
                 1u,
                 (PSECURITY_DESCRIPTOR *)nLengthNeeded,
                 0)
            || (v54 = ResultFromKnownLastError(), v54 >= 0) )
          {
            if ( SetFileSecurityW(String1, 7u, *(PSECURITY_DESCRIPTOR *)nLengthNeeded) )
            {
              v54 = 0;
            }
            else
            {
              v54 = ResultFromKnownLastError();
              if ( v54 == -2147024894 )
              {
                SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)nLengthNeeded;
                *(_QWORD *)&SecurityAttributes.nLength = 24;
                *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
                if ( CreateDirectoryW(String1, &SecurityAttributes) )
                  v54 = 0;
                else
                  v54 = ResultFromKnownLastError();
              }
              else if ( v54 == -2147024891 )
              {
                v54 = 0;
              }
            }
            LocalFree(*(HLOCAL *)nLengthNeeded);
          }
        }
      }
      if ( v54 < 0 )
        goto LABEL_81;
    }
    v55 = 2147483646;
    v56 = String1;
    v57 = 260;
    v58 = pszPath;
    do
    {
      if ( !v55 )
        break;
      if ( !*v56 )
        break;
      *v58++ = *v56++;
      --v55;
      --v57;
    }
    while ( v57 );
    v59 = v58 - 1;
    if ( v57 )
      v59 = v58;
    *v59 = 0;
    if ( !v57 )
      goto LABEL_81;
    v60 = StringSid;
    v61 = 3LL * (int)v107;
    v62 = PathCchAppend(pszPath, 0x104u, (PCWSTR)qword_1800E6000[v61 + 1]);
    if ( v62 >= 0 )
    {
      v63 = wcsstr(pszPath, L"/");
      if ( v63 )
      {
        do
        {
          *v63 = 92;
          v63 = wcsstr(v63, L"/");
        }
        while ( v63 );
        v6 = v112;
      }
      v62 = PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0);
      if ( v62 >= 0 )
      {
        v64 = -1;
        v65 = -1;
        do
          ++v65;
        while ( String1[v65] );
        if ( v65 > 0xFFFFFFFF )
          goto LABEL_81;
        do
          ++v64;
        while ( pszPathOut[v64] );
        if ( v64 > 0xFFFFFFFF
          || (unsigned int)v64 <= (unsigned int)v65
          || CompareStringOrdinal(String1, v65, pszPathOut, v65, 0) != 2
          || pszPathOut[(unsigned int)v65] != 92 )
        {
          goto LABEL_81;
        }
        v66 = 2147483646;
        v67 = pszPathOut;
        v68 = 260;
        v69 = String1;
        do
        {
          if ( !v66 )
            break;
          if ( !*v67 )
            break;
          *v69++ = *v67++;
          --v66;
          --v68;
        }
        while ( v68 );
        v70 = v69 - 1;
        v62 = -2147024774;
        if ( v68 )
        {
          v70 = v69;
          v62 = 0;
        }
        *v70 = 0;
        if ( v68 )
        {
          if ( !a6 )
          {
LABEL_124:
            v71 = pszMore;
            if ( !pszMore || !*pszMore )
              goto LABEL_184;
            v72 = 2147483646;
            v73 = String1;
            v74 = 260;
            v75 = pszPath;
            do
            {
              if ( !v72 )
                break;
              if ( !*v73 )
                break;
              *v75++ = *v73++;
              --v72;
              --v74;
            }
            while ( v74 );
            v76 = v75 - 1;
            v77 = -2147024774;
            if ( v74 )
            {
              v76 = v75;
              v77 = 0;
            }
            *v76 = 0;
            if ( v74 )
            {
              v78 = StringSid;
              v77 = PathCchAppend(pszPath, 0x104u, v71);
              if ( v77 >= 0 )
              {
                v79 = wcsstr(pszPath, L"/");
                if ( v79 )
                {
                  do
                  {
                    *v79 = 92;
                    v79 = wcsstr(v79, L"/");
                  }
                  while ( v79 );
                  v6 = v112;
                }
                v77 = PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0);
                if ( v77 >= 0 )
                {
                  v80 = -1;
                  v81 = -1;
                  do
                    ++v81;
                  while ( String1[v81] );
                  if ( v81 > 0xFFFFFFFF )
                    goto LABEL_182;
                  do
                    ++v80;
                  while ( pszPathOut[v80] );
                  if ( v80 > 0xFFFFFFFF )
                  {
LABEL_182:
                    v77 = -2147024362;
                  }
                  else
                  {
                    v77 = -2147024809;
                    if ( (unsigned int)v80 > (unsigned int)v81
                      && CompareStringOrdinal(String1, v81, pszPathOut, v81, 0) == 2
                      && pszPathOut[(unsigned int)v81] == 92 )
                    {
                      v82 = 2147483646;
                      v83 = pszPathOut;
                      v84 = 260;
                      v85 = String1;
                      do
                      {
                        if ( !v82 )
                          break;
                        if ( !*v83 )
                          break;
                        *v85++ = *v83++;
                        --v82;
                        --v84;
                      }
                      while ( v84 );
                      v86 = v85 - 1;
                      v77 = -2147024774;
                      if ( v84 )
                      {
                        v86 = v85;
                        v77 = 0;
                      }
                      *v86 = 0;
                      if ( v84 && a6 )
                        v77 = _SetSecurityOnFileOrFolder(String1, v78, v107, 0);
                    }
                  }
                }
              }
            }
            if ( v77 >= 0 )
            {
LABEL_184:
              v98 = String1;
              do
              {
                if ( !v10 )
                  break;
                if ( !*v98 )
                  break;
                *v6++ = *v98++;
                --v10;
                --v12;
              }
              while ( v12 );
              v99 = v6 - 1;
              if ( v12 )
                v99 = v6;
              *v99 = 0;
            }
            goto LABEL_81;
          }
          if ( v107 )
          {
            v62 = StringCchPrintfW(pszPathOut, 0x104u, (const unsigned __int16 *)qword_1800E6000[v61 + 2], v60);
          }
          else
          {
            v87 = L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)";
            v88 = pszPathOut;
            v89 = 2147483646;
            v90 = 260;
            do
            {
              if ( !v89 )
                break;
              if ( !*v87 )
                break;
              *v88++ = *v87++;
              --v89;
              --v90;
            }
            while ( v90 );
            v91 = v88 - 1;
            v62 = -2147024774;
            if ( v90 )
            {
              v91 = v88;
              v62 = 0;
            }
            *v91 = 0;
          }
          if ( v62 < 0 )
            goto LABEL_81;
          nLengthNeeded[0] = 0;
          if ( GetFileSecurityW(String1, 7u, 0, 0, nLengthNeeded) )
            goto LABEL_166;
          if ( (unsigned int)ResultFromKnownLastError() != -2147024774 )
            goto LABEL_166;
          v92 = CoTaskMemAlloc(nLengthNeeded[0]);
          v93 = v92;
          if ( !v92 )
            goto LABEL_166;
          v96 = 0;
          v97 = CTCoAllocPolicy::_CoTaskMemSize(v92);
          memset_0(v93, 0, v97);
          if ( GetFileSecurityW(String1, 7u, v93, nLengthNeeded[0], nLengthNeeded) )
          {
            StringSecurityDescriptor = 0;
            if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v93, 1u, 7u, &StringSecurityDescriptor, 0) )
            {
              v96 = CompareStringOrdinal(StringSecurityDescriptor, -1, pszPathOut, -1, 1) == 2;
              LocalFree(StringSecurityDescriptor);
            }
          }
          CoTaskMemFree(v93);
          if ( !v96 )
          {
LABEL_166:
            *(_QWORD *)nLengthNeeded = 0;
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                   pszPathOut,
                   1u,
                   (PSECURITY_DESCRIPTOR *)nLengthNeeded,
                   0)
              || (v62 = ResultFromKnownLastError(), v62 >= 0) )
            {
              if ( SetFileSecurityW(String1, 7u, *(PSECURITY_DESCRIPTOR *)nLengthNeeded) )
              {
                v62 = 0;
              }
              else
              {
                v62 = ResultFromKnownLastError();
                if ( v62 == -2147024894 )
                {
                  SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)nLengthNeeded;
                  *(_QWORD *)&SecurityAttributes.nLength = 24;
                  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
                  if ( CreateDirectoryW(String1, &SecurityAttributes) )
                    v62 = 0;
                  else
                    v62 = ResultFromKnownLastError();
                }
                else if ( v62 == -2147024891 )
                {
                  v62 = 0;
                }
              }
              LocalFree(*(HLOCAL *)nLengthNeeded);
            }
          }
        }
      }
    }
    if ( v62 >= 0 )
      goto LABEL_124;
LABEL_81:
    LocalFree(StringSid);
    return v108;
  }
  result = ResultFromKnownLastError();
  v108 = result;
  if ( (int)result >= 0 )
    goto LABEL_3;
  return result;
}

```

## disassembly

```asm
0x180005270  push    rbp
0x180005272  push    r12
0x180005274  push    r13
0x180005276  push    r14
0x180005278  lea     rbp, [rsp-5E8h]
0x180005280  sub     rsp, 6E8h
0x180005287  mov     rax, cs:__security_cookie
0x18000528e  xor     rax, rsp
0x180005291  mov     [rbp+600h+var_50], rax
0x180005298  mov     [rsp+700h+pszMore], rdx
0x18000529d  xor     r13d, r13d
0x1800052a0  lea     rdx, [rsp+700h+StringSid]; StringSid
0x1800052a5  mov     [r9], r13w
0x1800052a9  mov     [rsp+700h+StringSid], r13
0x1800052ae  mov     r14, r9
0x1800052b1  mov     [rsp+700h+var_690], r9
0x1800052b6  mov     [rsp+700h+var_6C0], r8d
0x1800052bb  call    cs:__imp_ConvertSidToStringSidW
0x1800052c1  test    eax, eax
0x1800052c3  jz      loc_18000609C
0x1800052c9  mov     [rsp+700h+var_6BC], r13d
0x1800052ce  lea     r9, [rsp+700h+ppszPath]; ppszPath
0x1800052d3  mov     [rsp+700h+ppszPath], r13
0x1800052d8  xor     r8d, r8d; hToken
0x1800052db  lea     rcx, FOLDERID_ProgramData; rfid
0x1800052e2  xor     edx, edx; dwFlags
0x1800052e4  call    cs:__imp_SHGetKnownFolderPath
0x1800052ea  test    eax, eax
0x1800052ec  js      loc_1800057D3
0x1800052f2  mov     rcx, [rsp+700h+ppszPath]; pv
0x1800052f7  lea     r9, [rbp+600h+String1]
0x1800052fb  mov     [rsp+700h+var_20], rbx
0x180005303  mov     r8, rcx
0x180005306  mov     [rsp+700h+var_28], rsi
0x18000530e  mov     esi, 7FFFFFFEh
0x180005313  mov     [rsp+700h+var_30], rdi
0x18000531b  mov     edx, esi
0x18000531d  mov     edi, 104h
0x180005322  mov     ebx, edi
0x180005324  test    rdx, rdx
0x180005327  jz      short loc_180005347
0x180005329  movzx   eax, word ptr [r8]
0x18000532d  test    ax, ax
0x180005330  jz      short loc_180005347
0x180005332  mov     [r9], ax
0x180005336  add     r8, 2
0x18000533a  add     r9, 2
0x18000533e  dec     rdx
0x180005341  sub     rbx, 1
0x180005345  jnz     short loc_180005324
0x180005347  lea     rdx, [r9-2]
0x18000534b  test    rbx, rbx
0x18000534e  cmovnz  rdx, r9
0x180005352  mov     [rdx], r13w
0x180005356  call    cs:__imp_CoTaskMemFree
0x18000535c  mov     [rsp+700h+ppszPath], r13
0x180005361  test    rbx, rbx
0x180005364  jz      loc_1800057BB
0x18000536a  mov     rcx, rsi
0x18000536d  lea     rdx, [rbp+600h+String1]
0x180005371  mov     r8, rdi
0x180005374  lea     r9, [rbp+600h+pszPath]
0x18000537b  nop     dword ptr [rax+rax+00h]
0x180005380  test    rcx, rcx
0x180005383  jz      short loc_1800053A2
0x180005385  movzx   eax, word ptr [rdx]
0x180005388  test    ax, ax
0x18000538b  jz      short loc_1800053A2
0x18000538d  mov     [r9], ax
0x180005391  add     rdx, 2
0x180005395  add     r9, 2
0x180005399  dec     rcx
0x18000539c  sub     r8, 1
0x1800053a0  jnz     short loc_180005380
0x1800053a2  test    r8, r8
0x1800053a5  lea     rcx, [r9-2]
0x1800053a9  cmovnz  rcx, r9
0x1800053ad  mov     [rcx], r13w
0x1800053b1  jz      loc_1800057BB
0x1800053b7  lea     r8, pszMore; "Microsoft\\Windows\\SystemData"
0x1800053be  mov     rdx, rdi; cchPath
0x1800053c1  lea     rcx, [rbp+600h+pszPath]; pszPath
0x1800053c8  call    cs:__imp_PathCchAppend
0x1800053ce  test    eax, eax
0x1800053d0  js      loc_1800057BB
0x1800053d6  lea     rdx, SubStr; "/"
0x1800053dd  lea     rcx, [rbp+600h+pszPath]; Str
0x1800053e4  call    cs:__imp_wcsstr
0x1800053ea  test    rax, rax
0x1800053ed  jnz     loc_1800060B2
0x1800053f3  xor     r9d, r9d; dwFlags
0x1800053f6  lea     r8, [rbp+600h+pszPath]; pszPathIn
0x1800053fd  mov     rdx, rdi; cchPathOut
0x180005400  lea     rcx, [rbp+600h+pszPathOut]; pszPathOut
0x180005407  call    cs:__imp_PathCchCanonicalizeEx
0x18000540d  test    eax, eax
0x18000540f  js      loc_1800057BB
0x180005415  mov     [rsp+700h+var_38], r15
0x18000541d  lea     rax, [rbp+600h+String1]
0x180005421  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180005428  mov     rbx, r15
0x18000542b  nop     dword ptr [rax+rax+00h]
0x180005430  inc     rbx
0x180005433  cmp     [rax+rbx*2], r13w
0x180005438  jnz     short loc_180005430
0x18000543a  mov     r12d, 0FFFFFFFFh
0x180005440  cmp     rbx, r12
0x180005443  ja      loc_1800057B3
0x180005449  lea     rcx, [rbp+600h+pszPathOut]
0x180005450  mov     rax, r15
0x180005453  inc     rax
0x180005456  cmp     [rcx+rax*2], r13w
0x18000545b  jnz     short loc_180005453
0x18000545d  cmp     rax, r12
0x180005460  ja      loc_1800057B3
0x180005466  cmp     eax, ebx
0x180005468  jbe     loc_1800057B3
0x18000546e  mov     r9d, ebx; cchCount2
0x180005471  mov     [rsp+700h+bIgnoreCase], r13d; bIgnoreCase
0x180005476  lea     r8, [rbp+600h+pszPathOut]; lpString2
0x18000547d  mov     edx, ebx; cchCount1
0x18000547f  lea     rcx, [rbp+600h+String1]; lpString1
0x180005483  call    cs:__imp_CompareStringOrdinal
0x180005489  cmp     eax, 2
0x18000548c  jnz     loc_1800057B3
0x180005492  mov     eax, ebx
0x180005494  cmp     [rbp+rax*2+600h+pszPathOut], 5Ch ; '\'
0x18000549d  jnz     loc_1800057B3
0x1800054a3  mov     rcx, rsi
0x1800054a6  lea     r9, [rbp+600h+pszPathOut]
0x1800054ad  mov     rdx, rdi
0x1800054b0  lea     r8, [rbp+600h+String1]
0x1800054b4  test    rcx, rcx
0x1800054b7  jz      short loc_1800054D7
0x1800054b9  movzx   eax, word ptr [r9]
0x1800054bd  test    ax, ax
0x1800054c0  jz      short loc_1800054D7
0x1800054c2  mov     [r8], ax
0x1800054c6  add     r9, 2
0x1800054ca  add     r8, 2
0x1800054ce  dec     rcx
0x1800054d1  sub     rdx, 1
0x1800054d5  jnz     short loc_1800054B4
0x1800054d7  test    rdx, rdx
0x1800054da  lea     rcx, [r8-2]
0x1800054de  cmovnz  rcx, r8
0x1800054e2  mov     [rcx], r13w
0x1800054e6  jz      loc_1800057B3
0x1800054ec  movzx   r13d, [rbp+600h+arg_28]
0x1800054f4  test    r13b, r13b
0x1800054f7  jz      loc_180005649
0x1800054fd  mov     rdx, cs:off_1800E6010; "O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-"...
0x180005504  lea     r9, [rbp+600h+pszPathOut]
0x18000550b  mov     rcx, rsi
0x18000550e  mov     r8, rdi
0x180005511  test    rcx, rcx
0x180005514  jz      short loc_180005533
0x180005516  movzx   eax, word ptr [rdx]
0x180005519  test    ax, ax
0x18000551c  jz      short loc_180005533
0x18000551e  mov     [r9], ax
0x180005522  add     rdx, 2
0x180005526  add     r9, 2
0x18000552a  dec     rcx
0x18000552d  sub     r8, 1
0x180005531  jnz     short loc_180005511
0x180005533  test    r8, r8
0x180005536  lea     rcx, [r9-2]
0x18000553a  mov     ebx, 8007007Ah
0x18000553f  cmovnz  rcx, r9
0x180005543  xor     eax, eax
0x180005545  test    r8, r8
0x180005548  cmovnz  ebx, eax
0x18000554b  mov     [rcx], ax
0x18000554e  jz      loc_180005634
0x180005554  mov     [rsp+700h+nLengthNeeded], eax
0x180005558  lea     rcx, [rbp+600h+String1]; lpFileName
0x18000555c  lea     rax, [rsp+700h+nLengthNeeded]
0x180005561  xor     r9d, r9d; nLength
0x180005564  xor     r8d, r8d; pSecurityDescriptor
0x180005567  mov     qword ptr [rsp+700h+bIgnoreCase], rax; lpnLengthNeeded
0x18000556c  mov     edx, 7; RequestedInformation
0x180005571  call    cs:__imp_GetFileSecurityW
0x180005577  test    eax, eax
0x180005579  jnz     short loc_18000559D
0x18000557b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005580  cmp     eax, 8007007Ah
0x180005585  jnz     short loc_18000559D
0x180005587  mov     ecx, [rsp+700h+nLengthNeeded]; cb
0x18000558b  call    cs:__imp_CoTaskMemAlloc
0x180005591  mov     r15, rax
0x180005594  test    rax, rax
0x180005597  jnz     loc_180005800
0x18000559d  xor     r9d, r9d; SecurityDescriptorSize
0x1800055a0  mov     qword ptr [rsp+700h+nLengthNeeded], 0
0x1800055a9  lea     r8, [rsp+700h+nLengthNeeded]; SecurityDescriptor
0x1800055ae  mov     edx, 1; StringSDRevision
0x1800055b3  lea     rcx, [rbp+600h+pszPathOut]; StringSecurityDescriptor
0x1800055ba  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800055c0  test    eax, eax
0x1800055c2  jz      loc_1800060D1
0x1800055c8  mov     r8, qword ptr [rsp+700h+nLengthNeeded]; pSecurityDescriptor
0x1800055cd  lea     rcx, [rbp+600h+String1]; lpFileName
0x1800055d1  mov     edx, 7; SecurityInformation
0x1800055d6  call    cs:__imp_SetFileSecurityW
0x1800055dc  test    eax, eax
0x1800055de  jnz     loc_1800060E5
0x1800055e4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800055e9  mov     ebx, eax
0x1800055eb  cmp     eax, 80070002h
0x1800055f0  jnz     loc_1800060F8
0x1800055f6  mov     rax, qword ptr [rsp+700h+nLengthNeeded]
0x1800055fb  lea     rdx, [rsp+700h+SecurityAttributes]; lpSecurityAttributes
0x180005600  mov     [rsp+700h+SecurityAttributes.lpSecurityDescriptor], rax
0x180005605  lea     rcx, [rbp+600h+String1]; lpPathName
0x180005609  xor     eax, eax
0x18000560b  mov     qword ptr [rsp+700h+SecurityAttributes.nLength], 18h
0x180005614  mov     qword ptr [rsp+700h+SecurityAttributes.bInheritHandle], rax
0x180005619  call    cs:__imp_CreateDirectoryW
0x18000561f  test    eax, eax
0x180005621  jz      loc_1800060EC
0x180005627  xor     ebx, ebx
0x180005629  mov     rcx, qword ptr [rsp+700h+nLengthNeeded]; hMem
0x18000562e  call    cs:__imp_LocalFree
0x180005634  test    ebx, ebx
0x180005636  js      loc_1800057B3
0x18000563c  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180005643  mov     r12d, 0FFFFFFFFh
0x180005649  mov     rcx, rsi
0x18000564c  lea     rdx, [rbp+600h+String1]
0x180005650  mov     r8, rdi
0x180005653  lea     r9, [rbp+600h+pszPath]
0x18000565a  nop     word ptr [rax+rax+00h]
0x180005660  test    rcx, rcx
0x180005663  jz      short loc_180005682
0x180005665  movzx   eax, word ptr [rdx]
0x180005668  test    ax, ax
0x18000566b  jz      short loc_180005682
0x18000566d  mov     [r9], ax
0x180005671  add     rdx, 2
0x180005675  add     r9, 2
0x180005679  dec     rcx
0x18000567c  sub     r8, 1
0x180005680  jnz     short loc_180005660
0x180005682  test    r8, r8
0x180005685  lea     rcx, [r9-2]
0x180005689  cmovnz  rcx, r9
0x18000568d  xor     eax, eax
0x18000568f  mov     [rcx], ax
0x180005692  test    r8, r8
0x180005695  jz      loc_1800057B3
0x18000569b  mov     r8, [rsp+700h+StringSid]; pszMore
0x1800056a0  lea     rcx, [rbp+600h+pszPath]; pszPath
0x1800056a7  mov     rdx, rdi; cchPath
0x1800056aa  call    cs:__imp_PathCchAppend
0x1800056b0  test    eax, eax
0x1800056b2  js      loc_1800057B3
0x1800056b8  lea     rdx, SubStr; "/"
0x1800056bf  lea     rcx, [rbp+600h+pszPath]; Str
0x1800056c6  call    cs:__imp_wcsstr
0x1800056cc  test    rax, rax
0x1800056cf  jnz     loc_180006108
0x1800056d5  xor     r9d, r9d; dwFlags
0x1800056d8  lea     r8, [rbp+600h+pszPath]; pszPathIn
0x1800056df  mov     rdx, rdi; cchPathOut
0x1800056e2  lea     rcx, [rbp+600h+pszPathOut]; pszPathOut
0x1800056e9  call    cs:__imp_PathCchCanonicalizeEx
0x1800056ef  test    eax, eax
0x1800056f1  js      loc_1800057B3
0x1800056f7  lea     rax, [rbp+600h+String1]
0x1800056fb  mov     rbx, r15
0x1800056fe  xchg    ax, ax
0x180005700  inc     rbx
0x180005703  cmp     word ptr [rax+rbx*2], 0
0x180005708  jnz     short loc_180005700
0x18000570a  cmp     rbx, r12
0x18000570d  ja      loc_1800057B3
0x180005713  lea     rcx, [rbp+600h+pszPathOut]
0x18000571a  mov     rax, r15
0x18000571d  nop     dword ptr [rax]
0x180005720  inc     rax
0x180005723  cmp     word ptr [rcx+rax*2], 0
0x180005728  jnz     short loc_180005720
0x18000572a  cmp     rax, r12
0x18000572d  ja      loc_1800057B3
0x180005733  cmp     eax, ebx
0x180005735  jbe     short loc_1800057B3
0x180005737  mov     r9d, ebx; cchCount2
0x18000573a  mov     [rsp+700h+bIgnoreCase], 0; bIgnoreCase
0x180005742  lea     r8, [rbp+600h+pszPathOut]; lpString2
0x180005749  mov     edx, ebx; cchCount1
0x18000574b  lea     rcx, [rbp+600h+String1]; lpString1
0x18000574f  call    cs:__imp_CompareStringOrdinal
0x180005755  cmp     eax, 2
0x180005758  jnz     short loc_1800057B3
0x18000575a  mov     eax, ebx
0x18000575c  cmp     [rbp+rax*2+600h+pszPathOut], 5Ch ; '\'
0x180005765  jnz     short loc_1800057B3
0x180005767  mov     rcx, rsi
0x18000576a  lea     rdx, [rbp+600h+pszPathOut]
  ... truncated ...
```
