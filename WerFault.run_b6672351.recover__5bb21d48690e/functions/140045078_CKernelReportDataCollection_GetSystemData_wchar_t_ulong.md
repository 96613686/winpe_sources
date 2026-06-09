# CKernelReportDataCollection::GetSystemData(wchar_t *,ulong)

- ea: `0x140045078`
- end: `0x140045a75`
- name: `?GetSystemData@CKernelReportDataCollection@@QEAAJPEA_WK@Z`
- size: `2557`
- prototype: `__int64 __fastcall(CKernelReportDataCollection *__hidden this, wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003c780`
- `0x14003d048`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x1400054e4`
- `0x1400083f0`
- `0x14000857c`
- `0x14000b448`
- `0x14000b580`
- `0x14000e658`
- `0x1400372dc`
- `0x14003b56c`
- `0x14003dc68`
- `0x1400428f0`
- `0x140043bd8`
- `0x140044974`
- `0x140045078`
- `0x140046774`
- `0x140046bbc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400459c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400459c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140045363`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140045363`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140045341`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140045341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004527c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400452fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004527c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400452fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14004516b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140045982`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14004516b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140045982`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14004517c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140045993`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14004517c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140045993`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x14004565c`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x14004565c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400459ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400459ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x14004525e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x14004525e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14004515f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14004515f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004570f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140045737`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140045783`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400457cf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400457f2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140045855`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400458a2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400458c6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140045923`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140045970`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004570f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140045737`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140045783`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400457cf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400457f2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140045855`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400458a2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400458c6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140045923`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140045970`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1400452ee`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1400452ee`

## string_xrefs

- `0x1400451a5`: `Unable to get the path for the file`
- `0x14004533a`: `drvstore.dll`
- `0x14004556b`: `Communications Server`
- `0x1400456c5`: `<?xml version="1.0" encoding="UTF-16" ?>\n<SYSTEMINFO>\n<SYSTEM>\n	<OSNAME>%ls %ls</OSNAME>\n	<OSVER>%u.%u.%u %u.%u</OSVER>\n	<OSLANGUAGE>%u</OSLANGUAGE>\n	<ARCHITECTURE>%u</ARCHITECTURE>\n	<PRODUCTTYPE>%u</PRODUCTTYPE>\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CKernelReportDataCollection::GetSystemData(CKernelReportDataCollection *this, wchar_t *a2)
{
  wchar_t *v2; // rdi
  wchar_t *v3; // r13
  HMODULE v4; // r12
  HANDLE CurrentThread; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  signed int ExtraReportFilePath; // ebx
  HANDLE v9; // r15
  struct _OSVERSIONINFOW *p_VersionInformation; // rax
  _OWORD *v11; // rcx
  __int64 v12; // rdx
  signed int LastError; // eax
  HMODULE Library; // rax
  char v15; // cl
  int v16; // eax
  wil::details::in1diag4 *v17; // rcx
  __int64 v18; // rdx
  __int32 v19; // eax
  unsigned __int64 v20; // rbx
  wchar_t **unique_for; // rax
  const struct std::nothrow_t *v22; // rdx
  CKernelReportDataCollection *v23; // rcx
  wchar_t *v24; // rdx
  DWORD v25; // ebx
  int wProcessorArchitecture; // edi
  LANGID SystemDefaultLangID; // ax
  const wchar_t *v28; // r9
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  int (__high *v34)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int); // rdi
  int DeviceData; // eax
  int v36; // ebx
  int DriverData; // eax
  int v38; // ebx
  HANDLE v39; // rax
  const struct std::nothrow_t *v40; // rdx
  wil::details *pdwReturnedProductType; // [rsp+20h] [rbp-E0h]
  wil::details *pdwReturnedProductTypea; // [rsp+20h] [rbp-E0h]
  wil::details *pdwReturnedProductTypeb; // [rsp+20h] [rbp-E0h]
  wil::details *pdwReturnedProductTypec; // [rsp+20h] [rbp-E0h]
  unsigned int v46[2]; // [rsp+28h] [rbp-D8h]
  char *v47; // [rsp+30h] [rbp-D0h]
  char *v48; // [rsp+30h] [rbp-D0h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp-90h] BYREF
  DWORD v50; // [rsp+74h] [rbp-8Ch] BYREF
  LPCVOID lpBuffer; // [rsp+78h] [rbp-88h] BYREF
  char *v52; // [rsp+80h] [rbp-80h]
  _WORD v53[8]; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hFile; // [rsp+98h] [rbp-68h] BYREF
  int (__high *ProcAddress)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int); // [rsp+A0h] [rbp-60h]
  CKernelReportDataCollection *v56; // [rsp+A8h] [rbp-58h]
  _WORD v57[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v58; // [rsp+B4h] [rbp-4Ch]
  wchar_t *v59; // [rsp+B8h] [rbp-48h]
  __m128i si128; // [rsp+C0h] [rbp-40h]
  void *v61; // [rsp+D0h] [rbp-30h]
  _WORD *v62; // [rsp+D8h] [rbp-28h]
  _WORD v63[8]; // [rsp+E0h] [rbp-20h] BYREF
  void *v64; // [rsp+F0h] [rbp-10h]
  _WORD *v65; // [rsp+F8h] [rbp-8h]
  _WORD v66[8]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t *v67; // [rsp+110h] [rbp+10h]
  HMODULE v68; // [rsp+120h] [rbp+20h]
  wchar_t *v69; // [rsp+128h] [rbp+28h]
  void *v70; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *v71; // [rsp+138h] [rbp+38h]
  struct _SYSTEM_INFO SystemInfo; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v73[288]; // [rsp+170h] [rbp+70h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v75; // [rsp+3A4h] [rbp+2A4h]
  unsigned __int16 v76; // [rsp+3A6h] [rbp+2A6h]
  __int16 v77; // [rsp+3A8h] [rbp+2A8h]
  char v78; // [rsp+3AAh] [rbp+2AAh]
  wchar_t v79[128]; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int16 Buffer; // [rsp+4B0h] [rbp+3B0h] BYREF
  wchar_t v81[1031]; // [rsp+4B2h] [rbp+3B2h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+D08h] [rbp+C08h]

  v2 = a2;
  v71 = a2;
  v56 = this;
  hFile = 0;
  v3 = 0;
  v69 = 0;
  NumberOfBytesWritten = 0;
  memset_0(&VersionInformation, 0, 0x11Cu);
  v57[0] = 0;
  v58 = 0;
  v59 = (wchar_t *)-1LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v61 = v63;
  v62 = v63;
  v63[0] = 0;
  v64 = v66;
  v65 = v66;
  v66[0] = 0;
  v67 = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  lpBuffer = v53;
  v52 = (char *)v53;
  v53[0] = 0;
  v50 = 0;
  v4 = 0;
  v68 = 0;
  if ( !v2 )
    return 2147942487LL;
  GetSystemInfo(&SystemInfo);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, -1);
  ExtraReportFilePath = CKernelReportDataCollection::GetExtraReportFilePath(v6, v2, v7, &hFile);
  v9 = hFile;
  if ( ExtraReportFilePath >= 0 )
  {
    ProcAddress = 0;
    memset_0(v73, 0, 0x11Cu);
    p_VersionInformation = &VersionInformation;
    v11 = v73;
    v12 = 2;
    do
    {
      *(_OWORD *)&p_VersionInformation->dwOSVersionInfoSize = *v11;
      *(_OWORD *)&p_VersionInformation->dwPlatformId = v11[1];
      *(_OWORD *)&p_VersionInformation->szCSDVersion[6] = v11[2];
      *(_OWORD *)&p_VersionInformation->szCSDVersion[14] = v11[3];
      *(_OWORD *)&p_VersionInformation->szCSDVersion[22] = v11[4];
      *(_OWORD *)&p_VersionInformation->szCSDVersion[30] = v11[5];
      *(_OWORD *)&p_VersionInformation->szCSDVersion[38] = v11[6];
      *(_OWORD *)&p_VersionInformation->szCSDVersion[46] = v11[7];
      p_VersionInformation = (struct _OSVERSIONINFOW *)((char *)p_VersionInformation + 128);
      v11 += 8;
      --v12;
    }
    while ( v12 );
    *(_OWORD *)&p_VersionInformation->dwOSVersionInfoSize = *v11;
    *(_OWORD *)&p_VersionInformation->dwBuildNumber = *(_OWORD *)((char *)v11 + 12);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation) )
    {
      LastError = GetLastError();
      ExtraReportFilePath = LastError;
      if ( LastError > 0 )
        ExtraReportFilePath = (unsigned __int16)LastError | 0x80070000;
      if ( ExtraReportFilePath >= 0 )
        ExtraReportFilePath = -2147467259;
      LODWORD(pdwReturnedProductType) = ExtraReportFilePath;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0xA7C,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
        "CKernelReportDataCollection::GetSystemData",
        pdwReturnedProductType,
        (int)"GetVersionEx failed",
        v47);
    }
    if ( !GetProductInfo(VersionInformation.dwMajorVersion, VersionInformation.dwMinorVersion, v75, v76, &v50) )
    {
      LODWORD(pdwReturnedProductTypea) = GetLastError();
      wil::details::in1diag4::Log_Win32Msg(
        retaddr,
        (void *)0xA85,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
        "CKernelReportDataCollection::GetSystemData",
        pdwReturnedProductTypea,
        (unsigned int)"GetProductInfo failed",
        v47);
      v50 = 0;
    }
    Library = LoadLibraryExW(L"drvstore.dll", 0, 0);
    v4 = Library;
    v68 = Library;
    if ( Library )
      ProcAddress = (int (__high *)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))GetProcAddress(Library, "DriverStoreGetObjectPropertyW");
    v79[0] = 0;
    v15 = v77;
    if ( (v77 & 0x40) != 0 )
    {
      if ( (int)StringCchCatW(v79, 0x80u, L"Embedded") < 0 )
      {
        LODWORD(pdwReturnedProductTypea) = ExtraReportFilePath;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0xA9F,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
          "CKernelReportDataCollection::GetSystemData",
          pdwReturnedProductTypea,
          (int)"StringCchCat failed",
          v47);
      }
      v15 = v77;
    }
    if ( v78 == 1 )
    {
      if ( (v77 & 0x200) != 0 )
      {
        v16 = StringCchCatW(v79, 0x80u, L"Home Edition");
        v17 = retaddr;
        if ( v16 >= 0 )
          goto LABEL_50;
        v18 = 2729;
      }
      else
      {
        v16 = StringCchCatW(v79, 0x80u, L"Professional");
        v17 = retaddr;
        if ( v16 >= 0 )
          goto LABEL_50;
        v18 = 2735;
      }
    }
    else if ( v15 < 0 )
    {
      v16 = StringCchCatW(v79, 0x80u, L"DataCenter Server");
      v17 = retaddr;
      if ( v16 >= 0 )
        goto LABEL_50;
      v18 = 2744;
    }
    else if ( (v15 & 2) != 0 )
    {
      v16 = StringCchCatW(v79, 0x80u, L"Advanced Server");
      v17 = retaddr;
      if ( v16 >= 0 )
        goto LABEL_50;
      v18 = 2750;
    }
    else if ( (v77 & 0x400) != 0 )
    {
      v16 = StringCchCatW(v79, 0x80u, L"Web Server");
      v17 = retaddr;
      if ( v16 >= 0 )
        goto LABEL_50;
      v18 = 2756;
    }
    else if ( (v15 & 4) != 0 )
    {
      v16 = StringCchCatW(v79, 0x80u, L"Back Office Server");
      v17 = retaddr;
      if ( v16 >= 0 )
        goto LABEL_50;
      v18 = 2762;
    }
    else if ( (v15 & 1) != 0 )
    {
      v16 = StringCchCatW(v79, 0x80u, L"Small Business Server");
      v17 = retaddr;
      if ( v16 >= 0 )
        goto LABEL_50;
      v18 = 2768;
    }
    else if ( (v15 & 0x20) != 0 )
    {
      v16 = StringCchCatW(v79, 0x80u, L"Small Business Server (restricted)");
      v17 = retaddr;
      if ( v16 >= 0 )
        goto LABEL_50;
      v18 = 2774;
    }
    else if ( (v15 & 8) != 0 )
    {
      v16 = StringCchCatW(v79, 0x80u, L"Communications Server");
      v17 = retaddr;
      if ( v16 >= 0 )
        goto LABEL_50;
      v18 = 2780;
    }
    else
    {
      v16 = StringCchCatW(v79, 0x80u, L"Server");
      v17 = retaddr;
      if ( v16 >= 0 )
        goto LABEL_50;
      v18 = 2786;
    }
    LODWORD(pdwReturnedProductTypea) = v16;
    wil::details::in1diag4::_Log_Hr(
      v17,
      (void *)v18,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
      "CKernelReportDataCollection::GetSystemData",
      pdwReturnedProductTypea,
      v46[0]);
LABEL_50:
    if ( (int)CRegSetting::Initialize(v57, 1, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", L"ProductName", 0) >= 0
      && CRegSetting::Load((CRegSetting *)v57, HKEY_LOCAL_MACHINE, 0) >= 0 )
    {
      v19 = si128.m128i_i32[0] - (_DWORD)v59;
      if ( si128.m128i_i32[0] != (_DWORD)v59 )
      {
        v20 = (unsigned __int64)(unsigned int)(2 * v19) >> 1;
        if ( v20 < 0x10000 )
        {
          unique_for = (wchar_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(
                                     &v70,
                                     (unsigned __int64)(unsigned int)(2 * v19) >> 1);
          v3 = *unique_for;
          *unique_for = 0;
          v69 = v3;
          v23 = (CKernelReportDataCollection *)v70;
          if ( v70 )
            operator delete(v70, v22);
          if ( v3 )
          {
            v24 = v67;
            if ( LOBYTE(v57[0]) )
              v24 = v59;
            CKernelReportDataCollection::XMLEncodeString(v23, v24, v3, v20);
          }
        }
      }
    }
    Buffer = -257;
    v25 = v50;
    wProcessorArchitecture = SystemInfo.wProcessorArchitecture;
    SystemDefaultLangID = GetSystemDefaultLangID();
    v28 = L"(null)";
    if ( v3 )
      v28 = v3;
    LODWORD(v47) = VersionInformation.dwMinorVersion;
    v46[0] = VersionInformation.dwMajorVersion;
    if ( (int)StringCchPrintfW(
                v81,
                0x401u,
                L"<?xml version=\"1.0\" encoding=\"UTF-16\" ?>\r\n"
                 "<SYSTEMINFO>\r\n"
                 "<SYSTEM>\r\n"
                 "\t<OSNAME>%ls %ls</OSNAME>\r\n"
                 "\t<OSVER>%u.%u.%u %u.%u</OSVER>\r\n"
                 "\t<OSLANGUAGE>%u</OSLANGUAGE>\r\n"
                 "\t<ARCHITECTURE>%u</ARCHITECTURE>\r\n"
                 "\t<PRODUCTTYPE>%u</PRODUCTTYPE>\r\n",
                v28,
                v79,
                *(_QWORD *)v46,
                v47,
                VersionInformation.dwBuildNumber,
                v75,
                v76,
                SystemDefaultLangID,
                wProcessorArchitecture,
                v25) >= 0 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v81[v29 - 1] );
      WriteFile(v9, &Buffer, 2 * v29, &NumberOfBytesWritten, 0);
    }
    WriteFile(v9, L"</SYSTEM>\r\n", 0x16u, &NumberOfBytesWritten, 0);
    if ( (int)CKernelReportDataCollection::WriteRegistryKeyXML(
                v31,
                v30,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\MemoryDiagnostic",
                L"MEMORYDIAGNOSTIC",
                &lpBuffer) >= 0 )
      WriteFile(v9, lpBuffer, 2 * ((v52 - (_BYTE *)lpBuffer) >> 1), &NumberOfBytesWritten, 0);
    if ( (int)CKernelReportDataCollection::WriteRegistryKeyXML(
                v33,
                v32,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\CEIPRole\\RolesInWER",
                L"SERVERROLES",
                &lpBuffer) >= 0 )
      WriteFile(v9, lpBuffer, 2 * ((v52 - (_BYTE *)lpBuffer) >> 1), &NumberOfBytesWritten, 0);
    WriteFile(v9, L"<DEVICES>\r\n", 0x16u, &NumberOfBytesWritten, 0);
    v34 = ProcAddress;
    DeviceData = CKernelReportDataCollection::GetDeviceData(v56, v9, ProcAddress);
    v36 = DeviceData;
    if ( DeviceData < 0 )
    {
      tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        &lpBuffer,
        L"\r\n\t<ERROR>Failed at Step: %s with error 0x%x</ERROR>\r\n",
        L"GetDeviceData",
        (unsigned int)DeviceData);
      WriteFile(v9, lpBuffer, 2 * ((v52 - (_BYTE *)lpBuffer) >> 1), &NumberOfBytesWritten, 0);
      LODWORD(pdwReturnedProductTypeb) = v36;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0xB3F,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
        "CKernelReportDataCollection::GetSystemData",
        pdwReturnedProductTypeb,
        (int)"GetDeviceData failed",
        v48);
    }
    WriteFile(v9, L"</DEVICES>\r\n", 0x18u, &NumberOfBytesWritten, 0);
    WriteFile(v9, L"<DRIVERS>\r\n", 0x16u, &NumberOfBytesWritten, 0);
    DriverData = CKernelReportDataCollection::GetDriverData(v56, v9, v34);
    v38 = DriverData;
    if ( DriverData < 0 )
    {
      tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        &lpBuffer,
        L"\r\n\t<ERROR>Failed at Step: %s with error 0x%x</ERROR>\r\n",
        L"GetDriverData",
        (unsigned int)DriverData);
      WriteFile(v9, lpBuffer, 2 * ((v52 - (_BYTE *)lpBuffer) >> 1), &NumberOfBytesWritten, 0);
      LODWORD(pdwReturnedProductTypec) = v38;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0xB4F,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
        "CKernelReportDataCollection::GetSystemData",
        pdwReturnedProductTypec,
        (int)"GetDriverData failed",
        v48);
    }
    WriteFile(v9, L"</DRIVERS>\r\n</SYSTEMINFO>\r\n", 0x36u, &NumberOfBytesWritten, 0);
    ExtraReportFilePath = 0;
    v2 = v71;
    goto LABEL_75;
  }
  LODWORD(pdwReturnedProductType) = ExtraReportFilePath;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0xA71,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
    "CKernelReportDataCollection::GetSystemData",
    pdwReturnedProductType,
    (int)"Unable to get the path for the file",
    v47);
LABEL_75:
  v39 = GetCurrentThread();
  SetThreadPriority(v39, 0);
  if ( (unsigned __int64)v9 + 1 > 1 )
    CloseHandle(v9);
  if ( ExtraReportFilePath < 0 )
    *v2 = 0;
  if ( v4 )
    FreeLibrary(v4);
  if ( lpBuffer != v53 )
    operator delete((void *)lpBuffer, (const struct std::nothrow_t *)&std::nothrow);
  if ( v64 != v66 )
    operator delete(v64, (const struct std::nothrow_t *)&std::nothrow);
  if ( v61 != v63 )
    operator delete(v61, (const struct std::nothrow_t *)&std::nothrow);
  if ( v59 != (wchar_t *)-1LL )
  {
    si128.m128i_i64[0] = (__int64)v59;
    operator delete(v59, (const struct std::nothrow_t *)&std::nothrow);
  }
  if ( v3 )
    operator delete(v3, v40);
  return (unsigned int)ExtraReportFilePath;
}

```

## disassembly

```asm
0x140045078  mov     [rsp-8+arg_10], rbx
0x14004507d  push    rbp
0x14004507e  push    rsi
0x14004507f  push    rdi
0x140045080  push    r12
0x140045082  push    r13
0x140045084  push    r14
0x140045086  push    r15
0x140045088  lea     rbp, [rsp-0BD0h]
0x140045090  sub     rsp, 0CD0h
0x140045097  mov     rax, cs:__security_cookie
0x14004509e  xor     rax, rsp
0x1400450a1  mov     [rbp+0C00h+var_40], rax
0x1400450a8  mov     rdi, rdx
0x1400450ab  mov     [rbp+0C00h+var_BC8], rdx
0x1400450af  mov     [rbp+0C00h+var_C58], rcx
0x1400450b3  xor     esi, esi
0x1400450b5  mov     [rbp+0C00h+hFile], rsi
0x1400450b9  mov     r13d, esi
0x1400450bc  mov     [rbp+0C00h+var_BD8], rsi
0x1400450c0  mov     [rsp+0D00h+NumberOfBytesWritten], esi
0x1400450c4  mov     r14d, 11Ch
0x1400450ca  mov     r8d, r14d; Size
0x1400450cd  xor     edx, edx; Val
0x1400450cf  lea     rcx, [rbp+0C00h+VersionInformation]; void *
0x1400450d6  call    memset_0
0x1400450db  mov     [rbp+0C00h+var_C50], si
0x1400450df  mov     [rbp+0C00h+var_C4C], esi
0x1400450e2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400450e6  mov     [rbp+0C00h+var_C48], rbx
0x1400450ea  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400450f2  movdqa  [rbp+0C00h+var_C40], xmm0
0x1400450f7  lea     rax, [rbp+0C00h+var_C20]
0x1400450fb  mov     [rbp+0C00h+var_C30], rax
0x1400450ff  lea     rax, [rbp+0C00h+var_C20]
0x140045103  mov     [rbp+0C00h+var_C28], rax
0x140045107  mov     [rbp+0C00h+var_C20], si
0x14004510b  lea     rax, [rbp+0C00h+var_C00]
0x14004510f  mov     [rbp+0C00h+var_C10], rax
0x140045113  lea     rax, [rbp+0C00h+var_C00]
0x140045117  mov     [rbp+0C00h+var_C08], rax
0x14004511b  mov     [rbp+0C00h+var_C00], si
0x14004511f  mov     [rbp+0C00h+var_BF0], rsi
0x140045123  xorps   xmm0, xmm0
0x140045126  movups  xmmword ptr [rbp+0C00h+SystemInfo], xmm0
0x14004512a  movups  xmmword ptr [rbp+0C00h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x14004512e  movups  xmmword ptr [rbp+0C00h+SystemInfo.dwNumberOfProcessors], xmm0
0x140045132  lea     rax, [rbp+0C00h+var_C78]
0x140045136  mov     [rsp+0D00h+lpBuffer], rax
0x14004513b  lea     rax, [rbp+0C00h+var_C78]
0x14004513f  mov     [rbp+0C00h+var_C80], rax
0x140045143  mov     [rbp+0C00h+var_C78], si
0x140045147  mov     [rsp+0D00h+var_C8C], esi
0x14004514b  mov     r12d, esi
0x14004514e  mov     [rbp+0C00h+var_BE0], rsi
0x140045152  test    rdi, rdi
0x140045155  jz      loc_140045A45
0x14004515b  lea     rcx, [rbp+0C00h+SystemInfo]; lpSystemInfo
0x14004515f  call    cs:__imp_GetSystemInfo
0x140045166  nop     dword ptr [rax+rax+00h]
0x14004516b  call    cs:__imp_GetCurrentThread
0x140045172  nop     dword ptr [rax+rax+00h]
0x140045177  mov     rcx, rax; hThread
0x14004517a  mov     edx, ebx; nPriority
0x14004517c  call    cs:__imp_SetThreadPriority
0x140045183  nop     dword ptr [rax+rax+00h]
0x140045188  lea     r9, [rbp+0C00h+hFile]
0x14004518c  mov     rdx, rdi
0x14004518f  call    ?GetExtraReportFilePath@CKernelReportDataCollection@@AEAAJPEA_WKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CKernelReportDataCollection::GetExtraReportFilePath(wchar_t *,ulong,tlx::unique_any<tlx::file_handle_traits> *)
0x140045194  mov     ebx, eax
0x140045196  mov     r15, [rbp+0C00h+hFile]
0x14004519a  test    eax, eax
0x14004519c  jns     short loc_1400451D2
0x14004519e  mov     rcx, [rbp+0C08h]; this
0x1400451a5  lea     rax, aUnableToGetThe; "Unable to get the path for the file"
0x1400451ac  mov     qword ptr [rsp+0D00h+var_CD8], rax; int
0x1400451b1  mov     dword ptr [rsp+0D00h+pdwReturnedProductType], ebx; wil::details *
0x1400451b5  lea     r9, aCkernelreportd_1; "CKernelReportDataCollection::GetSystemD"...
0x1400451bc  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x1400451c3  mov     edx, 0A71h; void *
0x1400451c8  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400451cd  jmp     loc_140045982
0x1400451d2  xor     edi, edi
0x1400451d4  mov     [rbp+0C00h+var_C60], rdi
0x1400451d8  mov     r8, r14; Size
0x1400451db  xor     edx, edx; Val
0x1400451dd  lea     rcx, [rbp+0C00h+var_B90]; void *
0x1400451e1  call    memset_0
0x1400451e6  lea     rax, [rbp+0C00h+VersionInformation]
0x1400451ed  lea     rcx, [rbp+0C00h+var_B90]
0x1400451f1  lea     edx, [rdi+2]
0x1400451f4  lea     r8d, [rdx+7Eh]
0x1400451f8  movups  xmm0, xmmword ptr [rcx]
0x1400451fb  movups  xmmword ptr [rax], xmm0
0x1400451fe  movups  xmm1, xmmword ptr [rcx+10h]
0x140045202  movups  xmmword ptr [rax+10h], xmm1
0x140045206  movups  xmm0, xmmword ptr [rcx+20h]
0x14004520a  movups  xmmword ptr [rax+20h], xmm0
0x14004520e  movups  xmm1, xmmword ptr [rcx+30h]
0x140045212  movups  xmmword ptr [rax+30h], xmm1
0x140045216  movups  xmm0, xmmword ptr [rcx+40h]
0x14004521a  movups  xmmword ptr [rax+40h], xmm0
0x14004521e  movups  xmm1, xmmword ptr [rcx+50h]
0x140045222  movups  xmmword ptr [rax+50h], xmm1
0x140045226  movups  xmm0, xmmword ptr [rcx+60h]
0x14004522a  movups  xmmword ptr [rax+60h], xmm0
0x14004522e  movups  xmm1, xmmword ptr [rcx+70h]
0x140045232  movups  xmmword ptr [rax+70h], xmm1
0x140045236  add     rax, r8
0x140045239  add     rcx, r8
0x14004523c  sub     rdx, 1
0x140045240  jnz     short loc_1400451F8
0x140045242  movups  xmm0, xmmword ptr [rcx]
0x140045245  movups  xmmword ptr [rax], xmm0
0x140045248  movups  xmm1, xmmword ptr [rcx+0Ch]
0x14004524c  movups  xmmword ptr [rax+0Ch], xmm1
0x140045250  mov     [rbp+0C00h+VersionInformation.dwOSVersionInfoSize], r14d
0x140045257  lea     rcx, [rbp+0C00h+VersionInformation]; lpVersionInformation
0x14004525e  call    cs:__imp_GetVersionExW
0x140045265  nop     dword ptr [rax+rax+00h]
0x14004526a  lea     rsi, aCkernelreportd_1; "CKernelReportDataCollection::GetSystemD"...
0x140045271  lea     r14, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140045278  test    eax, eax
0x14004527a  jnz     short loc_1400452C8
0x14004527c  call    cs:__imp_GetLastError
0x140045283  nop     dword ptr [rax+rax+00h]
0x140045288  mov     ebx, eax
0x14004528a  test    eax, eax
0x14004528c  jle     short loc_140045297
0x14004528e  movzx   ebx, ax
0x140045291  or      ebx, 80070000h
0x140045297  mov     eax, 80004005h
0x14004529c  test    ebx, ebx
0x14004529e  cmovns  ebx, eax
0x1400452a1  mov     rcx, [rbp+0C08h]; this
0x1400452a8  lea     rax, aGetversionexFa; "GetVersionEx failed"
0x1400452af  mov     qword ptr [rsp+0D00h+var_CD8], rax; int
0x1400452b4  mov     dword ptr [rsp+0D00h+pdwReturnedProductType], ebx; wil::details *
0x1400452b8  mov     r9, rsi; char *
0x1400452bb  mov     r8, r14; unsigned int
0x1400452be  mov     edx, 0A7Ch; void *
0x1400452c3  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400452c8  movzx   r9d, [rbp+0C00h+var_95A]; dwSpMinorVersion
0x1400452d0  movzx   r8d, [rbp+0C00h+var_95C]; dwSpMajorVersion
0x1400452d8  lea     rax, [rsp+0D00h+var_C8C]
0x1400452dd  mov     [rsp+0D00h+pdwReturnedProductType], rax; pdwReturnedProductType
0x1400452e2  mov     edx, [rbp+0C00h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x1400452e8  mov     ecx, [rbp+0C00h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x1400452ee  call    cs:__imp_GetProductInfo
0x1400452f5  nop     dword ptr [rax+rax+00h]
0x1400452fa  test    eax, eax
0x1400452fc  jnz     short loc_140045335
0x1400452fe  call    cs:__imp_GetLastError
0x140045305  nop     dword ptr [rax+rax+00h]
0x14004530a  mov     rcx, [rbp+0C08h]; this
0x140045311  lea     rdx, aGetproductinfo; "GetProductInfo failed"
0x140045318  mov     qword ptr [rsp+0D00h+var_CD8], rdx; unsigned int
0x14004531d  mov     dword ptr [rsp+0D00h+pdwReturnedProductType], eax; wil::details *
0x140045321  mov     r9, rsi; char *
0x140045324  mov     r8, r14; unsigned int
0x140045327  mov     edx, 0A85h; void *
0x14004532c  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x140045331  mov     [rsp+0D00h+var_C8C], edi
0x140045335  xor     r8d, r8d; dwFlags
0x140045338  xor     edx, edx; hFile
0x14004533a  lea     rcx, aDrvstoreDll; "drvstore.dll"
0x140045341  call    cs:__imp_LoadLibraryExW
0x140045348  nop     dword ptr [rax+rax+00h]
0x14004534d  mov     r12, rax
0x140045350  mov     [rbp+0C00h+var_BE0], rax
0x140045354  test    rax, rax
0x140045357  jz      short loc_140045373
0x140045359  lea     rdx, aDriverstoreget_2; "DriverStoreGetObjectPropertyW"
0x140045360  mov     rcx, rax; hModule
0x140045363  call    cs:__imp_GetProcAddress
0x14004536a  nop     dword ptr [rax+rax+00h]
0x14004536f  mov     [rbp+0C00h+var_C60], rax
0x140045373  mov     [rbp+0C00h+var_950], di
0x14004537a  mov     cl, byte ptr [rbp+0C00h+var_958]
0x140045380  test    cl, 40h
0x140045383  jz      short loc_1400453CE
0x140045385  lea     r8, aEmbedded; "Embedded"
0x14004538c  mov     edx, 80h; unsigned __int64
0x140045391  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x140045398  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14004539d  test    eax, eax
0x14004539f  jns     short loc_1400453C8
0x1400453a1  mov     rcx, [rbp+0C08h]; this
0x1400453a8  lea     rax, aStringcchcatFa; "StringCchCat failed"
0x1400453af  mov     qword ptr [rsp+0D00h+var_CD8], rax; int
0x1400453b4  mov     dword ptr [rsp+0D00h+pdwReturnedProductType], ebx; wil::details *
0x1400453b8  mov     r9, rsi; char *
0x1400453bb  mov     r8, r14; unsigned int
0x1400453be  mov     edx, 0A9Fh; void *
0x1400453c3  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400453c8  mov     cl, byte ptr [rbp+0C00h+var_958]
0x1400453ce  mov     edx, 80h; unsigned __int64
0x1400453d3  cmp     [rbp+0C00h+var_956], 1
0x1400453da  jnz     short loc_14004543B
0x1400453dc  mov     eax, 200h
0x1400453e1  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x1400453e8  test    [rbp+0C00h+var_958], ax
0x1400453ef  jz      short loc_140045416
0x1400453f1  lea     r8, aHomeEdition; "Home Edition"
0x1400453f8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400453fd  mov     rcx, [rbp+0C08h]
0x140045404  test    eax, eax
0x140045406  jns     loc_1400455B4
0x14004540c  mov     edx, 0AA9h
0x140045411  jmp     loc_1400455A5
0x140045416  lea     r8, aProfessional; "Professional"
0x14004541d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140045422  mov     rcx, [rbp+0C08h]
0x140045429  test    eax, eax
0x14004542b  jns     loc_1400455B4
0x140045431  mov     edx, 0AAFh
0x140045436  jmp     loc_1400455A5
0x14004543b  test    dl, cl
0x14004543d  jz      short loc_14004546B
0x14004543f  lea     r8, aDatacenterServ; "DataCenter Server"
0x140045446  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x14004544d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140045452  mov     rcx, [rbp+0C08h]
0x140045459  test    eax, eax
0x14004545b  jns     loc_1400455B4
0x140045461  mov     edx, 0AB8h
0x140045466  jmp     loc_1400455A5
0x14004546b  test    cl, 2
0x14004546e  jz      short loc_14004549C
0x140045470  lea     r8, aAdvancedServer; "Advanced Server"
0x140045477  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x14004547e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140045483  mov     rcx, [rbp+0C08h]
0x14004548a  test    eax, eax
0x14004548c  jns     loc_1400455B4
0x140045492  mov     edx, 0ABEh
0x140045497  jmp     loc_1400455A5
0x14004549c  mov     eax, 400h
0x1400454a1  test    [rbp+0C00h+var_958], ax
0x1400454a8  jz      short loc_1400454D6
0x1400454aa  lea     r8, aWebServer; "Web Server"
0x1400454b1  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x1400454b8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400454bd  mov     rcx, [rbp+0C08h]
0x1400454c4  test    eax, eax
0x1400454c6  jns     loc_1400455B4
0x1400454cc  mov     edx, 0AC4h
0x1400454d1  jmp     loc_1400455A5
0x1400454d6  test    cl, 4
0x1400454d9  jz      short loc_140045507
0x1400454db  lea     r8, aBackOfficeServ; "Back Office Server"
0x1400454e2  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x1400454e9  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400454ee  mov     rcx, [rbp+0C08h]
0x1400454f5  test    eax, eax
0x1400454f7  jns     loc_1400455B4
0x1400454fd  mov     edx, 0ACAh
0x140045502  jmp     loc_1400455A5
0x140045507  test    cl, 1
0x14004550a  jz      short loc_140045535
0x14004550c  lea     r8, aSmallBusinessS; "Small Business Server"
0x140045513  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x14004551a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14004551f  mov     rcx, [rbp+0C08h]
0x140045526  test    eax, eax
0x140045528  jns     loc_1400455B4
0x14004552e  mov     edx, 0AD0h
0x140045533  jmp     short loc_1400455A5
0x140045535  test    cl, 20h
0x140045538  jz      short loc_14004555F
0x14004553a  lea     r8, aSmallBusinessS_0; "Small Business Server (restricted)"
0x140045541  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x140045548  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14004554d  mov     rcx, [rbp+0C08h]
0x140045554  test    eax, eax
0x140045556  jns     short loc_1400455B4
0x140045558  mov     edx, 0AD6h
0x14004555d  jmp     short loc_1400455A5
0x14004555f  test    cl, 8
0x140045562  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x140045569  jz      short loc_140045589
0x14004556b  lea     r8, aCommunications; "Communications Server"
0x140045572  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140045577  mov     rcx, [rbp+0C08h]
0x14004557e  test    eax, eax
0x140045580  jns     short loc_1400455B4
0x140045582  mov     edx, 0ADCh
0x140045587  jmp     short loc_1400455A5
0x140045589  lea     r8, aServer; "Server"
0x140045590  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140045595  mov     rcx, [rbp+0C08h]; this
0x14004559c  test    eax, eax
0x14004559e  jns     short loc_1400455B4
0x1400455a0  mov     edx, 0AE2h; void *
0x1400455a5  mov     dword ptr [rsp+0D00h+pdwReturnedProductType], eax; wil::details *
0x1400455a9  mov     r9, rsi; char *
0x1400455ac  mov     r8, r14; unsigned int
0x1400455af  call    ?_Log_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::_Log_Hr(void *,uint,char const *,char const *,long)
0x1400455b4  mov     [rsp+0D00h+pdwReturnedProductType], rdi
0x1400455b9  lea     r9, aProductname_0; "ProductName"
  ... truncated ...
```
