# PCPStorageProvider::GetKeyStorageLocation(uchar,uchar,uchar,ushort *)

- ea: `0x180012640`
- end: `0x1800133be`
- name: `?GetKeyStorageLocation@PCPStorageProvider@@QEAAJEEEPEAG@Z`
- size: `3454`
- prototype: `__int64 __fastcall(PCPStorageProvider *this, char, char, char, STRSAFE_LPWSTR pszDest)`
- caller_count: `5`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180021310`
- `0x180026b90`
- `0x18005aebc`
- `0x1800604d0`
- `0x18007f068`

## callees

- `0x18000f858`
- `0x180011bd0`
- `0x180011c60`
- `0x1800123f0`
- `0x180012640`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x18003cce0`
- `0x18004ddc8`
- `0x180068a8c`
- `0x1800764d0`
- `0x1800768a0`
- `0x180076998`
- `0x18007704c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001302b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001302b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013214`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800130cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001310e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013153`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001317a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800130cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001310e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013153`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001317a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180012c04`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180013200`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180012c04`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180013200`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013273`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013273`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001335a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001335a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180013323`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180013323`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180013398`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180013398`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180012700`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180012bc3`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180012fbd`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180012700`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180012bc3`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180012fbd`

## pseudocode

```c
__int64 __fastcall PCPStorageProvider::GetKeyStorageLocation(
        PCPStorageProvider *this,
        char a2,
        char a3,
        char a4,
        STRSAFE_LPWSTR pszDest)
{
  char v7; // r15
  STRSAFE_LPWSTR v9; // r14
  const unsigned __int16 *v10; // r8
  __int64 v11; // rsi
  int v12; // eax
  unsigned int v13; // ebx
  PCPStorageProvider *v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rcx
  WCHAR *p_FileName; // rax
  int v21; // edi
  __int64 v22; // rbx
  __int64 v23; // rdx
  const unsigned __int16 *v24; // r8
  unsigned __int16 *v25; // r9
  unsigned __int16 v26; // ax
  WCHAR *v27; // rax
  WCHAR *v28; // rdi
  __int64 v29; // rcx
  WCHAR *v30; // rdx
  __int64 v31; // r8
  WCHAR v32; // ax
  const char *v33; // r9
  __int64 result; // rax
  int v35; // eax
  unsigned int v36; // edi
  WCHAR *v37; // rcx
  WCHAR v38; // ax
  int v39; // eax
  PCPStorageProvider *v40; // rcx
  unsigned int v41; // ebx
  HLOCAL v42; // rbx
  unsigned __int16 *v43; // rdi
  int SrkPathQualifier; // eax
  unsigned int v45; // esi
  int v46; // eax
  unsigned int v47; // ebx
  wchar_t *v48; // rax
  int v49; // eax
  unsigned int v50; // ebx
  __int64 v51; // rbx
  wchar_t v52; // cx
  WCHAR *v53; // rax
  __int64 v54; // rcx
  WCHAR *v55; // rdx
  __int64 v56; // r8
  WCHAR v57; // ax
  unsigned __int16 *v58; // rcx
  int v59; // eax
  unsigned int v60; // ebx
  const unsigned __int16 *v61; // r8
  int v62; // eax
  unsigned int v63; // ebx
  int BasicProfileFolderPath; // eax
  unsigned int v65; // ebx
  DWORD LastError; // eax
  unsigned int v67; // ebx
  __int64 i; // rbx
  unsigned __int16 *v69; // rcx
  unsigned int v70; // ebx
  int v71; // eax
  unsigned int v72; // r15d
  DWORD v73; // eax
  unsigned int v74; // ebx
  const char *v75; // r9
  unsigned int v76; // ebx
  const char *v77; // r9
  const char *v78; // r9
  DWORD v79; // eax
  int psidGroup; // [rsp+20h] [rbp-728h]
  const char *psidGroupa; // [rsp+20h] [rbp-728h]
  int psidGroupb; // [rsp+20h] [rbp-728h]
  _BYTE v84[24]; // [rsp+48h] [rbp-700h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-6E8h] BYREF
  WINBOOL bDaclPresent[2]; // [rsp+68h] [rbp-6E0h] BYREF
  PACL pDacl; // [rsp+70h] [rbp-6D8h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+78h] [rbp-6D0h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+7Ch] [rbp-6CCh] BYREF
  _OWORD FileInformation[2]; // [rsp+80h] [rbp-6C8h] BYREF
  int v91; // [rsp+A0h] [rbp-6A8h]
  WCHAR StringSecurityDescriptor[28]; // [rsp+A8h] [rbp-6A0h] BYREF
  WCHAR PathName; // [rsp+E0h] [rbp-668h] BYREF
  char v94[526]; // [rsp+E2h] [rbp-666h] BYREF
  WCHAR FileName; // [rsp+2F0h] [rbp-458h] BYREF
  char v96[518]; // [rsp+2F2h] [rbp-456h] BYREF
  _BYTE v97[8]; // [rsp+4F8h] [rbp-250h] BYREF
  unsigned __int16 v98; // [rsp+500h] [rbp-248h] BYREF
  char v99[526]; // [rsp+502h] [rbp-246h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+748h] [rbp+0h]

  v7 = a2;
  v9 = pszDest;
  *(_QWORD *)bDaclPresent = pszDest;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v84, L"PCPStorageProvider::GetKeyStorageLocation", 1);
  *pszDest = 0;
  if ( *((_QWORD *)this + 16) )
  {
    hMem = (HLOCAL)260;
    v39 = StringCchPrintfExW(
            pszDest,
            0x104u,
            (unsigned __int16 **)bDaclPresent,
            (unsigned __int64 *)&hMem,
            0x800u,
            L"%s\\");
    v41 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v39,
        psidGroupb);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
      result = v41;
      goto LABEL_117;
    }
    v42 = hMem;
    if ( (unsigned __int64)hMem < 0x2A )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)0x8007007ALL,
        psidGroupb);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
      result = 2147942522LL;
      goto LABEL_117;
    }
    v43 = *(unsigned __int16 **)bDaclPresent;
    SrkPathQualifier = PCPStorageProvider::GetSrkPathQualifier(v40, *(unsigned __int16 **)bDaclPresent);
    v45 = SrkPathQualifier;
    if ( SrkPathQualifier < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB6,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)SrkPathQualifier,
        psidGroupb);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
      result = v45;
      goto LABEL_117;
    }
    v46 = StringCchPrintfW(v43 + 40, (unsigned __int64)v42 - 40, L"\\");
    v47 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v46,
        psidGroupb);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
      result = v47;
      goto LABEL_117;
    }
    goto LABEL_40;
  }
  PathName = 0;
  memset_0(v94, 0, 0x206u);
  if ( !v7 )
  {
    if ( a4 )
    {
      v61 = (const unsigned __int16 *)*((_QWORD *)this + 14);
      if ( v61 )
      {
        v62 = StringCchCopyW(pszDest, 0x104u, v61);
        v63 = v62;
        if ( v62 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFC,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)(unsigned int)v62,
            psidGroup);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
          result = v63;
          goto LABEL_117;
        }
        goto LABEL_40;
      }
      v11 = 260;
      BasicProfileFolderPath = GetBasicProfileFolderPath(8, 0, &PathName, 260);
      v65 = BasicProfileFolderPath;
      if ( BasicProfileFolderPath < 0 )
      {
        if ( BasicProfileFolderPath == -2147024891 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x109,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)0x80290408LL,
            psidGroup);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
          result = 2150171656LL;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10A,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)(unsigned int)BasicProfileFolderPath,
            psidGroup);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
          result = v65;
        }
        goto LABEL_117;
      }
    }
    else
    {
      v48 = (wchar_t *)*((_QWORD *)this + 13);
      v11 = 260;
      if ( v48 )
      {
        v51 = 2147483646;
        while ( v51 )
        {
          v52 = *v48;
          if ( !*v48 )
            break;
          ++v48;
          *v9++ = v52;
          --v51;
          if ( !--v11 )
          {
            *(v9 - 1) = 0;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE4,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
              (const char *)0x8007007ALL,
              psidGroup);
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
            result = 2147942522LL;
            goto LABEL_117;
          }
        }
LABEL_35:
        *v9 = 0;
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
        result = 0;
        goto LABEL_117;
      }
      v49 = GetBasicProfileFolderPath(6, 0, &PathName, 260);
      v50 = v49;
      if ( v49 < 0 )
      {
        if ( v49 == -2147024891 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF1,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)0x80290408LL,
            psidGroup);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
          result = 2150171656LL;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF2,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)(unsigned int)v49,
            psidGroup);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
          result = v50;
        }
        goto LABEL_117;
      }
    }
LABEL_5:
    v98 = 0;
    memset_0(v99, 0, 0x206u);
    v15 = PCPStorageProvider::GetSrkPathQualifier(v14, &v98);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v15,
        psidGroup);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
      result = v16;
      goto LABEL_117;
    }
    FileName = 0;
    memset_0(v96, 0, sizeof(v96));
    psidGroupa = L"Microsoft\\Crypto\\PCPKSP";
    v17 = StringCchPrintfW(&FileName, 0x104u, L"%s\\%s\\%s", &PathName);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v17,
        (int)L"Microsoft\\Crypto\\PCPKSP");
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
      result = v18;
      goto LABEL_117;
    }
    memset(FileInformation, 0, sizeof(FileInformation));
    v91 = 0;
    if ( !a4 && !GetFileAttributesExW(&FileName, GetFileExInfoStandard, FileInformation) )
    {
      LastError = GetLastError();
      if ( LastError - 2 > 1 )
      {
        if ( LastError )
        {
          v67 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x128,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  (const char *)LastError,
                  (unsigned int)L"Microsoft\\Crypto\\PCPKSP");
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
          result = v67;
          goto LABEL_117;
        }
        goto LABEL_40;
      }
      for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= 3 )
          v69 = &v98;
        else
          v69 = off_1800CFF50[i];
        v71 = StringCchPrintfW(&PathName, 0x104u, L"%s\\%s", &PathName, v69);
        v72 = v71;
        if ( v71 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x136,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)(unsigned int)v71,
            (int)psidGroupa);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
          result = v72;
          goto LABEL_117;
        }
        if ( !GetFileAttributesExW(&PathName, GetFileExInfoStandard, FileInformation) )
        {
          v73 = GetLastError();
          if ( v73 != 2 )
          {
            if ( v73 )
            {
              v74 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x13F,
                      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                      (const char *)v73,
                      (unsigned int)psidGroupa);
              KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
              result = v74;
              goto LABEL_117;
            }
LABEL_40:
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
            result = 0;
            goto LABEL_117;
          }
          if ( !CreateDirectoryW(&PathName, 0) )
          {
            v76 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x143,
                    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                    v75);
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
            result = v76;
            goto LABEL_117;
          }
          if ( (unsigned int)i >= 3 && !a3 )
          {
            wcscpy(StringSecurityDescriptor, L"D:(A;OICI;FR;;;S-1-15--9)");
            SecurityDescriptorSize = 0;
            hMem = 0;
            if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                    StringSecurityDescriptor,
                    1u,
                    &hMem,
                    &SecurityDescriptorSize) )
            {
              v70 = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x14F,
                      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                      v77);
              if ( !hMem )
                goto LABEL_97;
LABEL_96:
              LocalFree(hMem);
              goto LABEL_97;
            }
            pDacl = 0;
            bDaclPresent[0] = 0;
            bDaclDefaulted = 0;
            if ( !GetSecurityDescriptorDacl(hMem, bDaclPresent, &pDacl, &bDaclDefaulted) )
            {
              v70 = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x158,
                      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                      v78);
              if ( !hMem )
                goto LABEL_97;
              goto LABEL_96;
            }
            v79 = SetNamedSecurityInfoW(&PathName, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
            if ( v79 )
            {
              v70 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x162,
                      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                      (const char *)v79,
                      (unsigned int)psidGroupa);
              if ( hMem )
                goto LABEL_96;
LABEL_97:
              KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
              result = v70;
              goto LABEL_117;
            }
            if ( hMem )
              LocalFree(hMem);
          }
        }
      }
      v7 = a2;
    }
    v19 = 260;
    p_FileName = &FileName;
    while ( *p_FileName )
    {
      ++p_FileName;
      if ( !--v19 )
      {
        v21 = -2147024809;
LABEL_41:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16B,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)(unsigned int)v21,
          (int)psidGroupa);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
        result = (unsigned int)v21;
        goto LABEL_117;
      }
    }
    v22 = 2147483646;
    v23 = 2147483646;
    v24 = L"\\";
    v25 = (unsigned __int16 *)&v97[-2 * v19];
    v21 = 0;
    while ( v23 )
    {
      v26 = *v24;
      if ( !*v24 )
        break;
      ++v24;
      *v25++ = v26;
      --v23;
      if ( !--v19 )
      {
        --v25;
        v21 = -2147024774;
        break;
      }
    }
    *v25 = 0;
    if ( v21 < 0 )
      goto LABEL_41;
    if ( v7 )
    {
      if ( !*((_QWORD *)this + 15) )
      {
        operator delete(0, (const struct std::nothrow_t *)v23);
        *((_QWORD *)this + 15) = 0;
        v53 = (WCHAR *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
        v28 = v53;
        if ( v53 )
        {
          memset_0(v53, 0, 0x208u);
          *((_QWORD *)this + 15) = v28;
          v54 = 2147483646;
          v55 = &FileName;
          v56 = 260;
          while ( v54 )
          {
            v57 = *v55;
            if ( !*v55 )
              break;
            ++v55;
            *v28++ = v57;
            --v54;
            if ( !--v56 )
            {
              *(v28 - 1) = 0;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x189,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)0x8007007ALL,
                (int)psidGroupa);
              KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
              result = 2147942522LL;
              goto LABEL_117;
            }
          }
          goto LABEL_29;
        }
LABEL_68:
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
        result = 2147942408LL;
        goto LABEL_117;
      }
    }
    else
    {
      if ( !a4 )
      {
        if ( *((_QWORD *)this + 13) )
          goto LABEL_30;
        operator delete(0, (const struct std::nothrow_t *)v23);
        *((_QWORD *)this + 13) = 0;
        v27 = (WCHAR *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
        v28 = v27;
        if ( v27 )
        {
          memset_0(v27, 0, 0x208u);
          *((_QWORD *)this + 13) = v28;
          v29 = 2147483646;
          v30 = &FileName;
          v31 = 260;
          while ( v29 )
          {
            v32 = *v30;
            if ( !*v30 )
              break;
            ++v30;
            *v28++ = v32;
            --v29;
            if ( !--v31 )
            {
              *(v28 - 1) = 0;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x176,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)0x8007007ALL,
                (int)psidGroupa);
              KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
              result = 2147942522LL;
              goto LABEL_117;
            }
          }
LABEL_29:
          *v28 = 0;
          goto LABEL_30;
        }
        goto LABEL_68;
      }
      if ( !*((_QWORD *)this + 14) )
      {
        operator delete(0, (const struct std::nothrow_t *)v23);
        *((_QWORD *)this + 14) = 0;
        wil::make_unique_nothrow<unsigned short [0]>(&pDacl, 260);
        v58 = (unsigned __int16 *)pDacl;
        if ( pDacl )
        {
          *((_QWORD *)this + 14) = pDacl;
          v35 = StringCchCopyW(v58, 0x104u, &FileName);
          v36 = v35;
          if ( v35 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x180,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
              (const char *)(unsigned int)v35,
              (int)psidGroupa);
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
            result = v36;
            goto LABEL_117;
          }
          goto LABEL_30;
        }
        goto LABEL_68;
      }
    }
LABEL_30:
    v37 = &FileName;
    while ( v22 )
    {
      v38 = *v37;
      if ( !*v37 )
        break;
      ++v37;
      *v9++ = v38;
      --v22;
      if ( !--v11 )
      {
        *(v9 - 1) = 0;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18F,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)0x8007007ALL,
          (int)psidGroupa);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
        result = 2147942522LL;
        goto LABEL_117;
      }
    }
    goto LABEL_35;
  }
  v10 = (const unsigned __int16 *)*((_QWORD *)this + 15);
  if ( v10 )
  {
    v59 = StringCchCopyW(pszDest, 0x104u, v10);
    v60 = v59;
    if ( v59 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v59,
        psidGroup);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
      result = v60;
      goto LABEL_117;
    }
    goto LABEL_40;
  }
  v11 = 260;
  v12 = GetBasicProfileFolderPath(4, 0, &PathName, 260);
  v13 = v12;
  if ( v12 >= 0 )
    goto LABEL_5;
  if ( v12 == -2147024891 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)0x80290408LL,
      psidGroup);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
    result = 2150171656LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)(unsigned int)v12,
      psidGroup);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v84);
    result = v13;
  }
LABEL_117:
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      bDaclPresent[0] = wil::details::in1diag3::Return_CaughtException(
                          retaddr,
                          (void *)0x192,
                          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                          v33);
      result = (unsigned int)bDaclPresent[0];
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180012640  mov     [rsp+arg_8], rbx
0x180012645  mov     [rsp+arg_10], rsi
0x18001264a  push    rdi
0x18001264b  push    r12
0x18001264d  push    r13
0x18001264f  push    r14
0x180012651  push    r15
0x180012653  sub     rsp, 720h
0x18001265a  mov     rax, cs:__security_cookie
0x180012661  xor     rax, rsp
0x180012664  mov     [rsp+748h+var_38], rax
0x18001266c  movzx   r12d, r9b
0x180012670  movzx   edi, r8b
0x180012674  movzx   r15d, dl
0x180012678  mov     [rsp+748h+var_708], dl
0x18001267c  mov     r13, rcx
0x18001267f  mov     r14, [rsp+748h+pszDest]
0x180012687  mov     qword ptr [rsp+748h+bDaclPresent], r14
0x18001268c  mov     r8b, 1; bool
0x18001268f  lea     rdx, aPcpstorageprov_16; "PCPStorageProvider::GetKeyStorageLocati"...
0x180012696  lea     rcx, [rsp+748h+var_700]; this
0x18001269b  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x1800126a0  xor     eax, eax
0x1800126a2  mov     [r14], ax
0x1800126a6  mov     rax, [r13+80h]
0x1800126ad  test    rax, rax
0x1800126b0  jnz     loc_180012A7D
0x1800126b6  mov     [rsp+748h+PathName], ax
0x1800126be  xor     edx, edx; Val
0x1800126c0  mov     r8d, 206h; Size
0x1800126c6  lea     rcx, [rsp+748h+var_666]; void *
0x1800126ce  call    memset_0
0x1800126d3  test    r15b, r15b
0x1800126d6  jz      loc_180012B9A
0x1800126dc  mov     r8, [r13+78h]; unsigned __int16 *
0x1800126e0  test    r8, r8
0x1800126e3  jnz     loc_180012E44
0x1800126e9  mov     esi, 104h
0x1800126ee  mov     r9d, esi
0x1800126f1  lea     r8, [rsp+748h+PathName]
0x1800126f9  xor     edx, edx
0x1800126fb  mov     ecx, 4
0x180012700  call    cs:__imp_GetBasicProfileFolderPath
0x180012707  nop     dword ptr [rax+rax+00h]
0x18001270c  mov     ebx, eax
0x18001270e  test    eax, eax
0x180012710  js      loc_180012C69
0x180012716  xor     eax, eax
0x180012718  mov     [rsp+748h+var_248], ax
0x180012720  xor     edx, edx; Val
0x180012722  mov     r8d, 206h; Size
0x180012728  lea     rcx, [rsp+748h+var_246]; void *
0x180012730  call    memset_0
0x180012735  lea     rdx, [rsp+748h+var_248]; unsigned __int16 *
0x18001273d  call    ?GetSrkPathQualifier@PCPStorageProvider@@AEAAJPEAG@Z; PCPStorageProvider::GetSrkPathQualifier(ushort *)
0x180012742  mov     ebx, eax
0x180012744  test    eax, eax
0x180012746  js      loc_180012D42
0x18001274c  xor     eax, eax
0x18001274e  mov     [rsp+748h+FileName], ax
0x180012756  xor     edx, edx; Val
0x180012758  mov     r8d, 206h; Size
0x18001275e  lea     rcx, [rsp+748h+var_456]; void *
0x180012766  call    memset_0
0x18001276b  lea     rax, [rsp+748h+var_248]
0x180012773  mov     [rsp+748h+var_720], rax
0x180012778  lea     rax, aMicrosoftCrypt_1; "Microsoft\\Crypto\\PCPKSP"
0x18001277f  mov     [rsp+748h+psidGroup], rax; unsigned int
0x180012784  lea     r9, [rsp+748h+PathName]
0x18001278c  lea     r8, aSSS; "%s\\%s\\%s"
0x180012793  mov     rdx, rsi; unsigned __int64
0x180012796  lea     rcx, [rsp+748h+FileName]; unsigned __int16 *
0x18001279e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800127a3  mov     ebx, eax
0x1800127a5  test    eax, eax
0x1800127a7  js      loc_180012D6F
0x1800127ad  xorps   xmm0, xmm0
0x1800127b0  xor     eax, eax
0x1800127b2  movups  [rsp+748h+FileInformation], xmm0
0x1800127ba  movups  [rsp+748h+var_6B8], xmm0
0x1800127c2  mov     [rsp+748h+var_6A8], eax
0x1800127c9  test    r12b, r12b
0x1800127cc  jz      loc_180012BF2
0x1800127d2  mov     rcx, rsi
0x1800127d5  lea     rax, [rsp+748h+FileName]
0x1800127dd  nop     dword ptr [rax]
0x1800127e0  cmp     word ptr [rax], 0
0x1800127e4  jz      short loc_1800127FA
0x1800127e6  add     rax, 2
0x1800127ea  sub     rcx, 1
0x1800127ee  jnz     short loc_1800127E0
0x1800127f0  mov     edi, 80070057h
0x1800127f5  jmp     loc_180012B13
0x1800127fa  mov     ebx, 7FFFFFFEh
0x1800127ff  mov     edx, ebx; struct std::nothrow_t *
0x180012801  lea     r8, asc_1800D5B38; "\\"
0x180012808  lea     rax, [rcx+rcx]
0x18001280c  lea     r9, [rsp+748h+var_250]
0x180012814  sub     r9, rax
0x180012817  xor     edi, edi
0x180012819  test    rcx, rcx
0x18001281c  jz      short loc_180012843
0x18001281e  xchg    ax, ax
0x180012820  test    rdx, rdx
0x180012823  jz      short loc_180012853
0x180012825  movzx   eax, word ptr [r8]
0x180012829  test    ax, ax
0x18001282c  jz      short loc_18001284E
0x18001282e  add     r8, 2
0x180012832  mov     [r9], ax
0x180012836  add     r9, 2
0x18001283a  dec     rdx
0x18001283d  sub     rcx, 1
0x180012841  jnz     short loc_180012820
0x180012843  sub     r9, 2
0x180012847  mov     edi, 8007007Ah
0x18001284c  jmp     short loc_180012853
0x18001284e  test    rcx, rcx
0x180012851  jz      short loc_180012843
0x180012853  xor     eax, eax
0x180012855  mov     [r9], ax
0x180012859  test    edi, edi
0x18001285b  js      loc_180012B13
0x180012861  test    r15b, r15b
0x180012864  jnz     loc_180012CA2
0x18001286a  test    r12b, r12b
0x18001286d  jnz     loc_180012D9C
0x180012873  cmp     [r13+68h], rax
0x180012877  jnz     loc_180012A01
0x18001287d  xor     ecx, ecx; void *
0x18001287f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012884  mov     qword ptr [r13+68h], 0
0x18001288c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012893  mov     ecx, 208h; unsigned __int64
0x180012898  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001289d  mov     rdi, rax
0x1800128a0  test    rax, rax
0x1800128a3  jz      loc_180012BDE
0x1800128a9  xor     edx, edx; Val
0x1800128ab  mov     r8d, 208h; Size
0x1800128b1  mov     rcx, rax; void *
0x1800128b4  call    memset_0
0x1800128b9  mov     [r13+68h], rdi
0x1800128bd  mov     rcx, rbx
0x1800128c0  lea     rdx, [rsp+748h+FileName]
0x1800128c8  mov     r8, rsi
0x1800128cb  nop     dword ptr [rax+rax+00h]
0x1800128d0  test    rcx, rcx
0x1800128d3  jz      loc_1800129FC
0x1800128d9  movzx   eax, word ptr [rdx]
0x1800128dc  test    ax, ax
0x1800128df  jz      loc_1800129F3
0x1800128e5  add     rdx, 2
0x1800128e9  mov     [rdi], ax
0x1800128ec  add     rdi, 2
0x1800128f0  dec     rcx
0x1800128f3  sub     r8, 1
0x1800128f7  jnz     short loc_1800128D0
0x1800128f9  xor     eax, eax
0x1800128fb  mov     [rdi-2], ax
0x1800128ff  mov     rcx, [rsp+748h]; this
0x180012907  mov     r9d, 8007007Ah; char *
0x18001290d  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180012914  mov     edx, 176h; void *
0x180012919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001291e  lea     rcx, [rsp+748h+var_700]; this
0x180012923  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180012928  mov     eax, 8007007Ah
0x18001292d  jmp     loc_180012A4F
0x180012932  mov     [r13+70h], rcx
0x180012936  lea     r8, [rsp+748h+FileName]; unsigned __int16 *
0x18001293e  mov     rdx, rsi; unsigned __int64
0x180012941  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012946  mov     edi, eax
0x180012948  test    eax, eax
0x18001294a  jns     loc_180012A01
0x180012950  mov     rcx, [rsp+748h]; this
0x180012958  mov     r9d, eax; char *
0x18001295b  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180012962  mov     edx, 180h; void *
0x180012967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001296c  lea     rcx, [rsp+748h+var_700]; this
0x180012971  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180012976  mov     eax, edi
0x180012978  jmp     loc_180012A4F
0x18001297d  xor     eax, eax
0x18001297f  mov     [rdi-2], ax
0x180012983  mov     rcx, [rsp+748h]; this
0x18001298b  mov     r9d, 8007007Ah; char *
0x180012991  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180012998  mov     edx, 189h; void *
0x18001299d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129a2  lea     rcx, [rsp+748h+var_700]; this
0x1800129a7  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800129ac  mov     eax, 8007007Ah
0x1800129b1  jmp     loc_180012A4F
0x1800129b6  xor     eax, eax
0x1800129b8  mov     [r14-2], ax
0x1800129bd  mov     rcx, [rsp+748h]; this
0x1800129c5  mov     r9d, 8007007Ah; char *
0x1800129cb  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800129d2  mov     edx, 18Fh; void *
0x1800129d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129dc  lea     rcx, [rsp+748h+var_700]; this
0x1800129e1  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800129e6  mov     eax, 8007007Ah
0x1800129eb  jmp     short loc_180012A4F
0x1800129ed  mov     eax, [rsp+748h+bDaclPresent]
0x1800129f1  jmp     short loc_180012A4F
0x1800129f3  test    r8, r8
0x1800129f6  jz      loc_1800128F9
0x1800129fc  xor     eax, eax
0x1800129fe  mov     [rdi], ax
0x180012a01  lea     rcx, [rsp+748h+FileName]
0x180012a09  nop     dword ptr [rax+00000000h]
0x180012a10  test    rbx, rbx
0x180012a13  jz      short loc_180012A3D
0x180012a15  movzx   eax, word ptr [rcx]
0x180012a18  test    ax, ax
0x180012a1b  jz      short loc_180012A34
0x180012a1d  add     rcx, 2
0x180012a21  mov     [r14], ax
0x180012a25  add     r14, 2
0x180012a29  dec     rbx
0x180012a2c  sub     rsi, 1
0x180012a30  jnz     short loc_180012A10
0x180012a32  jmp     short loc_1800129B6
0x180012a34  test    rsi, rsi
0x180012a37  jz      loc_1800129B6
0x180012a3d  xor     eax, eax
0x180012a3f  mov     [r14], ax
0x180012a43  lea     rcx, [rsp+748h+var_700]; this
0x180012a48  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180012a4d  xor     eax, eax
0x180012a4f  mov     rcx, [rsp+748h+var_38]
0x180012a57  xor     rcx, rsp; StackCookie
0x180012a5a  call    __security_check_cookie
0x180012a5f  lea     r11, [rsp+748h+var_28]
0x180012a67  mov     rbx, [r11+38h]
0x180012a6b  mov     rsi, [r11+40h]
0x180012a6f  mov     rsp, r11
0x180012a72  pop     r15
0x180012a74  pop     r14
0x180012a76  pop     r13
0x180012a78  pop     r12
0x180012a7a  pop     rdi
0x180012a7b  retn
0x180012a7d  mov     esi, 104h
0x180012a82  mov     [rsp+748h+hMem], rsi
0x180012a87  mov     [rsp+748h+pSacl], rax
0x180012a8c  lea     rax, aS_0; "%s\\"
0x180012a93  mov     [rsp+748h+var_720], rax; unsigned __int16 *
0x180012a98  mov     dword ptr [rsp+748h+psidGroup], 800h; int
0x180012aa0  lea     r9, [rsp+748h+hMem]; unsigned __int64 *
0x180012aa5  lea     r8, [rsp+748h+bDaclPresent]; unsigned __int16 **
0x180012aaa  mov     edx, esi; unsigned __int64
0x180012aac  mov     rcx, r14; pszDest
0x180012aaf  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180012ab4  mov     ebx, eax
0x180012ab6  test    eax, eax
0x180012ab8  js      loc_180012B40
0x180012abe  mov     rbx, [rsp+748h+hMem]
0x180012ac3  cmp     rbx, 2Ah ; '*'
0x180012ac7  jb      loc_180012DE4
0x180012acd  mov     rdi, qword ptr [rsp+748h+bDaclPresent]
0x180012ad2  mov     rdx, rdi; unsigned __int16 *
0x180012ad5  call    ?GetSrkPathQualifier@PCPStorageProvider@@AEAAJPEAG@Z; PCPStorageProvider::GetSrkPathQualifier(ushort *)
0x180012ada  mov     esi, eax
0x180012adc  test    eax, eax
0x180012ade  js      loc_180012B6D
0x180012ae4  lea     rdx, [rbx-28h]; unsigned __int64
0x180012ae8  lea     rcx, [rdi+50h]; unsigned __int16 *
0x180012aec  lea     r8, asc_1800D5B38; "\\"
0x180012af3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012af8  mov     ebx, eax
0x180012afa  test    eax, eax
0x180012afc  js      loc_180012E17
0x180012b02  lea     rcx, [rsp+748h+var_700]; this
0x180012b07  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180012b0c  xor     eax, eax
0x180012b0e  jmp     loc_180012A4F
0x180012b13  mov     rcx, [rsp+748h]; this
0x180012b1b  mov     r9d, edi; char *
0x180012b1e  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180012b25  mov     edx, 16Bh; void *
0x180012b2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b2f  lea     rcx, [rsp+748h+var_700]; this
0x180012b34  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180012b39  mov     eax, edi
0x180012b3b  jmp     loc_180012A4F
0x180012b40  mov     rcx, [rsp+748h]; this
0x180012b48  mov     r9d, ebx; char *
0x180012b4b  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180012b52  mov     edx, 0B2h; void *
0x180012b57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b5c  lea     rcx, [rsp+748h+var_700]; this
0x180012b61  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180012b66  mov     eax, ebx
0x180012b68  jmp     loc_180012A4F
0x180012b6d  mov     rcx, [rsp+748h]; this
  ... truncated ...
```
