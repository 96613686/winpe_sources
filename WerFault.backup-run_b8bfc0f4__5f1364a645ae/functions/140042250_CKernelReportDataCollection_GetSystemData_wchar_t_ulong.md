# CKernelReportDataCollection::GetSystemData(wchar_t *,ulong)

- ea: `0x140042250`
- end: `0x140042bbc`
- name: `?GetSystemData@CKernelReportDataCollection@@QEAAJPEA_WK@Z`
- size: `2412`
- prototype: `__int64 __fastcall(CKernelReportDataCollection *__hidden this, wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003a0c0`
- `0x14003a8fc`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140005430`
- `0x140008498`
- `0x140008620`
- `0x14000b408`
- `0x14000b540`
- `0x14000e3c4`
- `0x140034d9c`
- `0x14003902c`
- `0x14003b3ac`
- `0x14003fd78`
- `0x140040ee4`
- `0x140041be8`
- `0x140042250`
- `0x1400437ec`
- `0x140043c14`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140042b15`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140042b15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004250b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004250b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400424ef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400424ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004243c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400424b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004243c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400424b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14004233d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140042ae2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14004233d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140042ae2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140042348`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140042aed`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140042348`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140042aed`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x1400427fe`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x1400427fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042b00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042b00`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140042424`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140042424`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x140042337`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x140042337`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400428ab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400428cd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042913`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042959`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042976`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400429d3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042a1a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042a38`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042a8f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042ad6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400428ab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400428cd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042913`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042959`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042976`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400429d3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042a1a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042a38`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042a8f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140042ad6`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1400424a8`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1400424a8`

## string_xrefs

- `0x14004236b`: `Unable to get the path for the file`
- `0x1400424e8`: `drvstore.dll`
- `0x14004270d`: `Communications Server`
- `0x140042861`: `<?xml version="1.0" encoding="UTF-16" ?>\n<SYSTEMINFO>\n<SYSTEM>\n	<OSNAME>%ls %ls</OSNAME>\n	<OSVER>%u.%u.%u %u.%u</OSVER>\n	<OSLANGUAGE>%u</OSLANGUAGE>\n	<ARCHITECTURE>%u</ARCHITECTURE>\n	<PRODUCTTYPE>%u</PRODUCTTYPE>\n`

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
    DriverData = CKernelReportDataCollection::GetDriverData(v56, (char *)v9, v34);
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
0x140042250  mov     [rsp-8+arg_10], rbx
0x140042255  push    rbp
0x140042256  push    rsi
0x140042257  push    rdi
0x140042258  push    r12
0x14004225a  push    r13
0x14004225c  push    r14
0x14004225e  push    r15
0x140042260  lea     rbp, [rsp-0BD0h]
0x140042268  sub     rsp, 0CD0h
0x14004226f  mov     rax, cs:__security_cookie
0x140042276  xor     rax, rsp
0x140042279  mov     [rbp+0C00h+var_40], rax
0x140042280  mov     rdi, rdx
0x140042283  mov     [rbp+0C00h+var_BC8], rdx
0x140042287  mov     [rbp+0C00h+var_C58], rcx
0x14004228b  xor     esi, esi
0x14004228d  mov     [rbp+0C00h+hFile], rsi
0x140042291  mov     r13d, esi
0x140042294  mov     [rbp+0C00h+var_BD8], rsi
0x140042298  mov     [rsp+0D00h+NumberOfBytesWritten], esi
0x14004229c  mov     r14d, 11Ch
0x1400422a2  mov     r8d, r14d; Size
0x1400422a5  xor     edx, edx; Val
0x1400422a7  lea     rcx, [rbp+0C00h+VersionInformation]; void *
0x1400422ae  call    memset_0
0x1400422b3  mov     [rbp+0C00h+var_C50], si
0x1400422b7  mov     [rbp+0C00h+var_C4C], esi
0x1400422ba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400422be  mov     [rbp+0C00h+var_C48], rbx
0x1400422c2  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400422ca  movdqa  [rbp+0C00h+var_C40], xmm0
0x1400422cf  lea     rax, [rbp+0C00h+var_C20]
0x1400422d3  mov     [rbp+0C00h+var_C30], rax
0x1400422d7  lea     rax, [rbp+0C00h+var_C20]
0x1400422db  mov     [rbp+0C00h+var_C28], rax
0x1400422df  mov     [rbp+0C00h+var_C20], si
0x1400422e3  lea     rax, [rbp+0C00h+var_C00]
0x1400422e7  mov     [rbp+0C00h+var_C10], rax
0x1400422eb  lea     rax, [rbp+0C00h+var_C00]
0x1400422ef  mov     [rbp+0C00h+var_C08], rax
0x1400422f3  mov     [rbp+0C00h+var_C00], si
0x1400422f7  mov     [rbp+0C00h+var_BF0], rsi
0x1400422fb  xorps   xmm0, xmm0
0x1400422fe  movups  xmmword ptr [rbp+0C00h+SystemInfo], xmm0
0x140042302  movups  xmmword ptr [rbp+0C00h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x140042306  movups  xmmword ptr [rbp+0C00h+SystemInfo.dwNumberOfProcessors], xmm0
0x14004230a  lea     rax, [rbp+0C00h+var_C78]
0x14004230e  mov     [rsp+0D00h+lpBuffer], rax
0x140042313  lea     rax, [rbp+0C00h+var_C78]
0x140042317  mov     [rbp+0C00h+var_C80], rax
0x14004231b  mov     [rbp+0C00h+var_C78], si
0x14004231f  mov     [rsp+0D00h+var_C8C], esi
0x140042323  mov     r12d, esi
0x140042326  mov     [rbp+0C00h+var_BE0], rsi
0x14004232a  test    rdi, rdi
0x14004232d  jz      loc_140042B8D
0x140042333  lea     rcx, [rbp+0C00h+SystemInfo]; lpSystemInfo
0x140042337  call    cs:__imp_GetSystemInfo
0x14004233d  call    cs:__imp_GetCurrentThread
0x140042343  mov     rcx, rax; hThread
0x140042346  mov     edx, ebx; nPriority
0x140042348  call    cs:__imp_SetThreadPriority
0x14004234e  lea     r9, [rbp+0C00h+hFile]
0x140042352  mov     rdx, rdi
0x140042355  call    ?GetExtraReportFilePath@CKernelReportDataCollection@@AEAAJPEA_WKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CKernelReportDataCollection::GetExtraReportFilePath(wchar_t *,ulong,tlx::unique_any<tlx::file_handle_traits> *)
0x14004235a  mov     ebx, eax
0x14004235c  mov     r15, [rbp+0C00h+hFile]
0x140042360  test    eax, eax
0x140042362  jns     short loc_140042398
0x140042364  mov     rcx, [rbp+0C08h]; this
0x14004236b  lea     rax, aUnableToGetThe; "Unable to get the path for the file"
0x140042372  mov     qword ptr [rsp+0D00h+var_CD8], rax; int
0x140042377  mov     dword ptr [rsp+0D00h+pdwReturnedProductType], ebx; wil::details *
0x14004237b  lea     r9, aCkernelreportd_1; "CKernelReportDataCollection::GetSystemD"...
0x140042382  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140042389  mov     edx, 0A71h; void *
0x14004238e  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140042393  jmp     loc_140042AE2
0x140042398  xor     edi, edi
0x14004239a  mov     [rbp+0C00h+var_C60], rdi
0x14004239e  mov     r8, r14; Size
0x1400423a1  xor     edx, edx; Val
0x1400423a3  lea     rcx, [rbp+0C00h+var_B90]; void *
0x1400423a7  call    memset_0
0x1400423ac  lea     rax, [rbp+0C00h+VersionInformation]
0x1400423b3  lea     rcx, [rbp+0C00h+var_B90]
0x1400423b7  lea     edx, [rdi+2]
0x1400423ba  lea     r8d, [rdx+7Eh]
0x1400423be  movups  xmm0, xmmword ptr [rcx]
0x1400423c1  movups  xmmword ptr [rax], xmm0
0x1400423c4  movups  xmm1, xmmword ptr [rcx+10h]
0x1400423c8  movups  xmmword ptr [rax+10h], xmm1
0x1400423cc  movups  xmm0, xmmword ptr [rcx+20h]
0x1400423d0  movups  xmmword ptr [rax+20h], xmm0
0x1400423d4  movups  xmm1, xmmword ptr [rcx+30h]
0x1400423d8  movups  xmmword ptr [rax+30h], xmm1
0x1400423dc  movups  xmm0, xmmword ptr [rcx+40h]
0x1400423e0  movups  xmmword ptr [rax+40h], xmm0
0x1400423e4  movups  xmm1, xmmword ptr [rcx+50h]
0x1400423e8  movups  xmmword ptr [rax+50h], xmm1
0x1400423ec  movups  xmm0, xmmword ptr [rcx+60h]
0x1400423f0  movups  xmmword ptr [rax+60h], xmm0
0x1400423f4  movups  xmm1, xmmword ptr [rcx+70h]
0x1400423f8  movups  xmmword ptr [rax+70h], xmm1
0x1400423fc  add     rax, r8
0x1400423ff  add     rcx, r8
0x140042402  sub     rdx, 1
0x140042406  jnz     short loc_1400423BE
0x140042408  movups  xmm0, xmmword ptr [rcx]
0x14004240b  movups  xmmword ptr [rax], xmm0
0x14004240e  movups  xmm1, xmmword ptr [rcx+0Ch]
0x140042412  movups  xmmword ptr [rax+0Ch], xmm1
0x140042416  mov     [rbp+0C00h+VersionInformation.dwOSVersionInfoSize], r14d
0x14004241d  lea     rcx, [rbp+0C00h+VersionInformation]; lpVersionInformation
0x140042424  call    cs:__imp_GetVersionExW
0x14004242a  lea     rsi, aCkernelreportd_1; "CKernelReportDataCollection::GetSystemD"...
0x140042431  lea     r14, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140042438  test    eax, eax
0x14004243a  jnz     short loc_140042482
0x14004243c  call    cs:__imp_GetLastError
0x140042442  mov     ebx, eax
0x140042444  test    eax, eax
0x140042446  jle     short loc_140042451
0x140042448  movzx   ebx, ax
0x14004244b  or      ebx, 80070000h
0x140042451  mov     eax, 80004005h
0x140042456  test    ebx, ebx
0x140042458  cmovns  ebx, eax
0x14004245b  mov     rcx, [rbp+0C08h]; this
0x140042462  lea     rax, aGetversionexFa; "GetVersionEx failed"
0x140042469  mov     qword ptr [rsp+0D00h+var_CD8], rax; int
0x14004246e  mov     dword ptr [rsp+0D00h+pdwReturnedProductType], ebx; wil::details *
0x140042472  mov     r9, rsi; char *
0x140042475  mov     r8, r14; unsigned int
0x140042478  mov     edx, 0A7Ch; void *
0x14004247d  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140042482  movzx   r9d, [rbp+0C00h+var_95A]; dwSpMinorVersion
0x14004248a  movzx   r8d, [rbp+0C00h+var_95C]; dwSpMajorVersion
0x140042492  lea     rax, [rsp+0D00h+var_C8C]
0x140042497  mov     [rsp+0D00h+pdwReturnedProductType], rax; pdwReturnedProductType
0x14004249c  mov     edx, [rbp+0C00h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x1400424a2  mov     ecx, [rbp+0C00h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x1400424a8  call    cs:__imp_GetProductInfo
0x1400424ae  test    eax, eax
0x1400424b0  jnz     short loc_1400424E3
0x1400424b2  call    cs:__imp_GetLastError
0x1400424b8  mov     rcx, [rbp+0C08h]; this
0x1400424bf  lea     rdx, aGetproductinfo; "GetProductInfo failed"
0x1400424c6  mov     qword ptr [rsp+0D00h+var_CD8], rdx; unsigned int
0x1400424cb  mov     dword ptr [rsp+0D00h+pdwReturnedProductType], eax; wil::details *
0x1400424cf  mov     r9, rsi; char *
0x1400424d2  mov     r8, r14; unsigned int
0x1400424d5  mov     edx, 0A85h; void *
0x1400424da  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x1400424df  mov     [rsp+0D00h+var_C8C], edi
0x1400424e3  xor     r8d, r8d; dwFlags
0x1400424e6  xor     edx, edx; hFile
0x1400424e8  lea     rcx, aDrvstoreDll; "drvstore.dll"
0x1400424ef  call    cs:__imp_LoadLibraryExW
0x1400424f5  mov     r12, rax
0x1400424f8  mov     [rbp+0C00h+var_BE0], rax
0x1400424fc  test    rax, rax
0x1400424ff  jz      short loc_140042515
0x140042501  lea     rdx, aDriverstoreget_2; "DriverStoreGetObjectPropertyW"
0x140042508  mov     rcx, rax; hModule
0x14004250b  call    cs:__imp_GetProcAddress
0x140042511  mov     [rbp+0C00h+var_C60], rax
0x140042515  mov     [rbp+0C00h+var_950], di
0x14004251c  mov     cl, byte ptr [rbp+0C00h+var_958]
0x140042522  test    cl, 40h
0x140042525  jz      short loc_140042570
0x140042527  lea     r8, aEmbedded; "Embedded"
0x14004252e  mov     edx, 80h; unsigned __int64
0x140042533  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x14004253a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14004253f  test    eax, eax
0x140042541  jns     short loc_14004256A
0x140042543  mov     rcx, [rbp+0C08h]; this
0x14004254a  lea     rax, aStringcchcatFa; "StringCchCat failed"
0x140042551  mov     qword ptr [rsp+0D00h+var_CD8], rax; int
0x140042556  mov     dword ptr [rsp+0D00h+pdwReturnedProductType], ebx; wil::details *
0x14004255a  mov     r9, rsi; char *
0x14004255d  mov     r8, r14; unsigned int
0x140042560  mov     edx, 0A9Fh; void *
0x140042565  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14004256a  mov     cl, byte ptr [rbp+0C00h+var_958]
0x140042570  mov     edx, 80h; unsigned __int64
0x140042575  cmp     [rbp+0C00h+var_956], 1
0x14004257c  jnz     short loc_1400425DD
0x14004257e  mov     eax, 200h
0x140042583  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x14004258a  test    [rbp+0C00h+var_958], ax
0x140042591  jz      short loc_1400425B8
0x140042593  lea     r8, aHomeEdition; "Home Edition"
0x14004259a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14004259f  mov     rcx, [rbp+0C08h]
0x1400425a6  test    eax, eax
0x1400425a8  jns     loc_140042756
0x1400425ae  mov     edx, 0AA9h
0x1400425b3  jmp     loc_140042747
0x1400425b8  lea     r8, aProfessional; "Professional"
0x1400425bf  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400425c4  mov     rcx, [rbp+0C08h]
0x1400425cb  test    eax, eax
0x1400425cd  jns     loc_140042756
0x1400425d3  mov     edx, 0AAFh
0x1400425d8  jmp     loc_140042747
0x1400425dd  test    dl, cl
0x1400425df  jz      short loc_14004260D
0x1400425e1  lea     r8, aDatacenterServ; "DataCenter Server"
0x1400425e8  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x1400425ef  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400425f4  mov     rcx, [rbp+0C08h]
0x1400425fb  test    eax, eax
0x1400425fd  jns     loc_140042756
0x140042603  mov     edx, 0AB8h
0x140042608  jmp     loc_140042747
0x14004260d  test    cl, 2
0x140042610  jz      short loc_14004263E
0x140042612  lea     r8, aAdvancedServer; "Advanced Server"
0x140042619  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x140042620  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140042625  mov     rcx, [rbp+0C08h]
0x14004262c  test    eax, eax
0x14004262e  jns     loc_140042756
0x140042634  mov     edx, 0ABEh
0x140042639  jmp     loc_140042747
0x14004263e  mov     eax, 400h
0x140042643  test    [rbp+0C00h+var_958], ax
0x14004264a  jz      short loc_140042678
0x14004264c  lea     r8, aWebServer; "Web Server"
0x140042653  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x14004265a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14004265f  mov     rcx, [rbp+0C08h]
0x140042666  test    eax, eax
0x140042668  jns     loc_140042756
0x14004266e  mov     edx, 0AC4h
0x140042673  jmp     loc_140042747
0x140042678  test    cl, 4
0x14004267b  jz      short loc_1400426A9
0x14004267d  lea     r8, aBackOfficeServ; "Back Office Server"
0x140042684  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x14004268b  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140042690  mov     rcx, [rbp+0C08h]
0x140042697  test    eax, eax
0x140042699  jns     loc_140042756
0x14004269f  mov     edx, 0ACAh
0x1400426a4  jmp     loc_140042747
0x1400426a9  test    cl, 1
0x1400426ac  jz      short loc_1400426D7
0x1400426ae  lea     r8, aSmallBusinessS; "Small Business Server"
0x1400426b5  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x1400426bc  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400426c1  mov     rcx, [rbp+0C08h]
0x1400426c8  test    eax, eax
0x1400426ca  jns     loc_140042756
0x1400426d0  mov     edx, 0AD0h
0x1400426d5  jmp     short loc_140042747
0x1400426d7  test    cl, 20h
0x1400426da  jz      short loc_140042701
0x1400426dc  lea     r8, aSmallBusinessS_0; "Small Business Server (restricted)"
0x1400426e3  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x1400426ea  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400426ef  mov     rcx, [rbp+0C08h]
0x1400426f6  test    eax, eax
0x1400426f8  jns     short loc_140042756
0x1400426fa  mov     edx, 0AD6h
0x1400426ff  jmp     short loc_140042747
0x140042701  test    cl, 8
0x140042704  lea     rcx, [rbp+0C00h+var_950]; wchar_t *
0x14004270b  jz      short loc_14004272B
0x14004270d  lea     r8, aCommunications; "Communications Server"
0x140042714  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140042719  mov     rcx, [rbp+0C08h]
0x140042720  test    eax, eax
0x140042722  jns     short loc_140042756
0x140042724  mov     edx, 0ADCh
0x140042729  jmp     short loc_140042747
0x14004272b  lea     r8, aServer; "Server"
0x140042732  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140042737  mov     rcx, [rbp+0C08h]; this
0x14004273e  test    eax, eax
0x140042740  jns     short loc_140042756
0x140042742  mov     edx, 0AE2h; void *
0x140042747  mov     dword ptr [rsp+0D00h+pdwReturnedProductType], eax; wil::details *
0x14004274b  mov     r9, rsi; char *
0x14004274e  mov     r8, r14; unsigned int
0x140042751  call    ?_Log_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::_Log_Hr(void *,uint,char const *,char const *,long)
0x140042756  mov     [rsp+0D00h+pdwReturnedProductType], rdi
0x14004275b  lea     r9, aProductname_0; "ProductName"
0x140042762  lea     r8, aSoftwareMicros_20; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140042769  mov     edx, 1
0x14004276e  lea     rcx, [rbp+0C00h+var_C50]
0x140042772  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x140042777  test    eax, eax
0x140042779  js      short loc_1400427EA
0x14004277b  xor     r8d, r8d; unsigned int
0x14004277e  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x140042785  lea     rcx, [rbp+0C00h+var_C50]; this
  ... truncated ...
```
