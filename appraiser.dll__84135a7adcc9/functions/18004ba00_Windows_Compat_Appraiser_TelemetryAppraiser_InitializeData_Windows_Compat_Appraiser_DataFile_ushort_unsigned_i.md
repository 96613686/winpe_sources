# Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData(Windows::Compat::Appraiser::DataFile &,ushort *,unsigned __int64,Windows::Compat::Appraiser::PropertyBag &,Windows::Compat::Appraiser::TelemetryRunHealth &)

- ea: `0x18004ba00`
- end: `0x18004c2c4`
- name: `?InitializeData@TelemetryAppraiser@Appraiser@Compat@Windows@@CAJAEAVDataFile@234@PEAG_KAEAVPropertyBag@234@AEAUTelemetryRunHealth@234@@Z`
- size: `2244`
- prototype: `__int64 __fastcall(struct Windows::Compat::Appraiser::DataFile *, unsigned __int16 *, unsigned __int64, struct Windows::Compat::Appraiser::PropertyBag *, struct Windows::Compat::Appraiser::TelemetryRunHealth *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800489d4`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180011d20`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002d06c`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18004ba00`
- `0x180068ce0`
- `0x180083f24`
- `0x1800858c8`
- `0x180087108`
- `0x180087a0c`
- `0x180093cfc`
- `0x180097f20`
- `0x18009b550`
- `0x1801abfd8`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x18004bb9d`
- `KERNEL32!InitOnceExecuteOnce` at `0x18004c0a3`
- `KERNEL32!InitOnceExecuteOnce` at `0x18004bb9d`
- `KERNEL32!InitOnceExecuteOnce` at `0x18004c0a3`
- `KERNEL32!GetSystemTime` at `0x18004bdda`
- `KERNEL32!GetSystemTime` at `0x18004bdda`
- `KERNEL32!LoadLibraryExW` at `0x18004c02f`
- `KERNEL32!LoadLibraryExW` at `0x18004c02f`
- `KERNEL32!FreeLibrary` at `0x18004c292`
- `KERNEL32!FreeLibrary` at `0x18004c292`
- `KERNEL32!GetProcAddress` at `0x18004c04c`
- `KERNEL32!GetProcAddress` at `0x18004c04c`

## string_xrefs

- `0x18004c022`: `ntdll.dll`
- `0x18004ba82`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x18004bab3`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x18004bfdb`: `Appraiser_TelemetryRunList.xml`
- `0x18004ba65`: `Error expanding inbox input directory: [0x%x].`
- `0x18004ba37`: `%WINDIR%\system32\appraiser\`
- `0x18004bee0`: `%WINDIR%\system32\appraiser\`
- `0x18004bb45`: `Error setting inbox data file path: [0x%x].`
- `0x18004bb68`: `Error setting inbox data file path: [0x%x].`
- `0x18004ba76`: `Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData`
- `0x18004baa7`: `Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData`
- `0x18004bc7b`: `Error expanding cab file path: [0x%x].`
- `0x18004bca1`: `Error expanding cab file path: [0x%x].`
- `0x18004bf54`: `Error copying string: [0x%x].`
- `0x18004bf7a`: `Error copying string: [0x%x].`
- `0x18004c247`: `Error reading data file: [0x%x].`
- `0x18004c26d`: `Error reading data file: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData(
        struct Windows::Compat::Appraiser::DataFile *a1,
        unsigned __int16 *a2,
        __int64 a3,
        struct Windows::Compat::Appraiser::PropertyBag *a4,
        struct Windows::Compat::Appraiser::TelemetryRunHealth *a5)
{
  int v6; // eax
  HRESULT Catalog; // ebx
  char v8; // dl
  int v9; // eax
  int v10; // eax
  const wchar_t *v11; // rax
  unsigned int v12; // edx
  const unsigned __int16 *v13; // r8
  char v14; // al
  wchar_t *v15; // r12
  int v16; // eax
  int v17; // eax
  int v18; // ebx
  volatile signed __int64 *v19; // rcx
  void **v20; // rdx
  int v21; // r12d
  int v22; // r8d
  int v23; // r9d
  int appended; // eax
  unsigned int v25; // edx
  const unsigned __int16 *v26; // r8
  int v27; // eax
  WCHAR *v28; // r12
  int v29; // eax
  HMODULE Library; // rax
  HMODULE v31; // r13
  unsigned __int8 (*ProcAddress)(void); // rbx
  bool v33; // bl
  unsigned __int64 v34; // rdx
  WCHAR *v35; // rax
  char v36; // dl
  unsigned __int64 v37; // rdx
  char v38; // dl
  int v39; // eax
  char *v41; // [rsp+20h] [rbp-E0h]
  const char *v42; // [rsp+28h] [rbp-D8h]
  const char *v43; // [rsp+28h] [rbp-D8h]
  char *v44; // [rsp+30h] [rbp-D0h]
  __int64 v45; // [rsp+38h] [rbp-C8h]
  bool v46; // [rsp+60h] [rbp-A0h] BYREF
  bool v47; // [rsp+61h] [rbp-9Fh] BYREF
  PWSTR v48; // [rsp+68h] [rbp-98h]
  int v49; // [rsp+70h] [rbp-90h] BYREF
  int v50; // [rsp+74h] [rbp-8Ch] BYREF
  char *v51; // [rsp+78h] [rbp-88h] BYREF
  const char *v52; // [rsp+80h] [rbp-80h] BYREF
  const char *v53; // [rsp+88h] [rbp-78h] BYREF
  const size_t *v54; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME *v55; // [rsp+98h] [rbp-68h] BYREF
  struct Windows::Compat::Appraiser::TelemetryRunHealth *v56; // [rsp+A0h] [rbp-60h]
  Windows::Compat::Appraiser::PropertyBag *v57; // [rsp+A8h] [rbp-58h]
  Windows::Compat::Appraiser::DataFile *v58; // [rsp+B0h] [rbp-50h]
  struct _SYSTEMTIME SystemTime; // [rsp+C0h] [rbp-40h] BYREF
  struct _SYSTEMTIME v60; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v61[144]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pszPath[264]; // [rsp+170h] [rbp+70h] BYREF
  char v63[144]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v64[264]; // [rsp+410h] [rbp+310h] BYREF
  WCHAR Dst[264]; // [rsp+620h] [rbp+520h] BYREF

  v58 = a1;
  v56 = a5;
  v57 = a4;
  v48 = a2;
  v46 = 0;
  v47 = 0;
  v6 = Windows::Compat::Appraiser::Utilities::ExpandDirectory(
         pszPath,
         (unsigned int)a2,
         L"%WINDIR%\\system32\\appraiser\\");
  Catalog = v6;
  if ( v6 < 0 )
  {
    LODWORD(v44) = v6;
    v42 = "Error expanding inbox input directory: [0x%x].";
    v8 = -34;
LABEL_3:
    LODWORD(v41) = Catalog;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v8,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      v41,
      (int)v42,
      v44);
    return (unsigned int)Catalog;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4DEu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      "Error expanding inbox input directory: [0x%x].",
      v6);
  Catalog = PathCchAppend(pszPath, 0x104u, L"Appraiser_Data.ini");
  if ( Catalog < 0 )
  {
    v8 = -31;
LABEL_8:
    LODWORD(v44) = Catalog;
    v42 = "Error appending: [0x%x].";
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4E1u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      "Error appending: [0x%x].",
      Catalog);
  v9 = Windows::Compat::Appraiser::DataFile::UseAlternateInboxDataPath(pszPath, 0);
  Catalog = v9;
  if ( v9 < 0 )
  {
    LODWORD(v44) = v9;
    v42 = "Error setting inbox data file path: [0x%x].";
    v8 = -28;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4E4u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      "Error setting inbox data file path: [0x%x].",
      v9);
  pszPath[0] = 0;
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
    Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
    0,
    0);
  if ( Windows::Compat::Appraiser::AppraiserTestHooks::TestHookForceDeleteUnzippedAdl )
  {
    v10 = Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder(
            Windows::Compat::Appraiser::WicaFactory::InboxDirectoryWorkingAlternate,
            0,
            0,
            0,
            0);
    Catalog = v10;
    if ( v10 < 0 )
    {
      LODWORD(v44) = v10;
      v42 = "Failed to clean telemetry output files folder: [0x%x].";
      v8 = -13;
      goto LABEL_3;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x4F3u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
        "Failed to clean telemetry output files folder: [0x%x].",
        v10);
  }
  v11 = (const wchar_t *)(*(__int64 (__fastcall **)(char *, const unsigned __int16 *))(*((_QWORD *)a4 + 1) + 40LL))(
                           (char *)a4 + 8,
                           L"ExpressMode");
  if ( v11 && !wcscmp_0(L"TRUE", v11) )
  {
    v13 = Windows::Compat::Appraiser::WicaFactory::InboxDirectoryPathInputAlternateDataOobeCab;
    v14 = 1;
  }
  else
  {
    v13 = Windows::Compat::Appraiser::WicaFactory::InboxDirectoryPathInputAlternateDataCab;
    v14 = 0;
  }
  v15 = L"AlternateDownloadOobeVersion";
  if ( !v14 )
    v15 = (wchar_t *)L"AlternateDownloadVersion";
  v16 = Windows::Compat::Appraiser::Utilities::ExpandDirectory(Dst, v12, v13);
  Catalog = v16;
  if ( v16 < 0 )
  {
    LODWORD(v44) = v16;
    v42 = "Error expanding cab file path: [0x%x].";
    v8 = 10;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x50Au,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      "Error expanding cab file path: [0x%x].",
      v16);
  v17 = Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded(
          &v46,
          Dst,
          v15,
          Windows::Compat::Appraiser::WicaFactory::InboxDirectoryPathInputTempDataCab,
          Windows::Compat::Appraiser::WicaFactory::InboxDirectoryWorkingAlternate,
          &v47);
  v18 = v17;
  if ( v17 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x512u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
        "Error getting alternate data files, swallowing: [0x%x].",
        v17);
  }
  else
  {
    LODWORD(v44) = v17;
    LODWORD(v41) = v17;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      18,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      v41,
      (int)"Error getting alternate data files, swallowing: [0x%x].",
      v44);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v61);
    v19 = (volatile signed __int64 *)v61;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v19 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v19,
      _InterlockedExchangeAdd64(v19 + 17, 0),
      v63);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v20);
    v21 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v49 = v18;
      v51 = v63;
      v52 = "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData";
      v54 = &szValueBuf;
      v53 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp";
      v50 = 1298;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v55 = &v60;
      v60 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v21,
        (unsigned int)&unk_18029F89F,
        v22,
        v23,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v50,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v49,
        (__int64)&v51);
    }
    v46 = 0;
  }
  *((_BYTE *)v56 + 16) = v47;
  appended = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
               v57,
               L"AdlInUseOrNotRequestedByOnesettings",
               v18 >= 0);
  Catalog = appended;
  if ( appended < 0 )
  {
    LODWORD(v44) = appended;
    v42 = "Error adding init property to bag: [0x%x].";
    v8 = 27;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x51Bu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      "Error adding init property to bag: [0x%x].",
      appended);
  v26 = L"%WINDIR%\\system32\\appraiser\\";
  if ( v46 )
    v26 = Windows::Compat::Appraiser::WicaFactory::InboxDirectoryWorkingAlternate;
  v27 = Windows::Compat::Appraiser::Utilities::ExpandDirectory(pszPath, v25, v26);
  Catalog = v27;
  if ( v27 < 0 )
  {
    LODWORD(v44) = v27;
    v8 = 34;
    v42 = "Error expanding inbox input directory: [0x%x].";
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x522u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      "Error expanding inbox input directory: [0x%x].",
      v27);
  v28 = v48;
  v29 = StringCchCopyW(v48, 0x104u, pszPath);
  Catalog = v29;
  if ( v29 < 0 )
  {
    LODWORD(v44) = v29;
    v42 = "Error copying string: [0x%x].";
    v8 = 37;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x525u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      "Error copying string: [0x%x].",
      v29);
  Catalog = PathCchAppend(pszPath, 0x104u, L"Appraiser_Data.ini");
  if ( Catalog < 0 )
  {
    v8 = 40;
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x528u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      "Error appending: [0x%x].",
      Catalog);
  Catalog = PathCchAppend(v28, 0x104u, L"Appraiser_TelemetryRunList.xml");
  if ( Catalog < 0 )
  {
    v8 = 43;
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x52Bu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      "Error appending: [0x%x].",
      Catalog);
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v31 = Library;
  v33 = 0;
  if ( (unsigned __int64)Library - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ProcAddress = (unsigned __int8 (*)(void))GetProcAddress(Library, "RtlIsStateSeparationEnabled");
    if ( ProcAddress )
    {
      if ( IsWindowsVersionOrGreaterEx(0xAu, 0, 0, 0x3FABu) && ProcAddress() )
        v33 = 1;
    }
  }
  if ( v46 )
    goto LABEL_92;
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
    Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
    0,
    0);
  if ( Windows::Compat::Appraiser::AppraiserTestHooks::TestHookSkipSignatureCheck || v33 )
    goto LABEL_92;
  Catalog = Windows::Compat::Appraiser::Utilities::FindCatalog(v64, v34, pszPath);
  if ( Catalog < 0 )
  {
    v35 = pszPath;
    v36 = 62;
LABEL_75:
    LODWORD(v45) = Catalog;
    LODWORD(v41) = Catalog;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v36,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      v41,
      (int)"Error finding catalog containing %ls: [0x%x].",
      (const char *)v35,
      v45);
    goto LABEL_97;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x53Eu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
      "Error finding catalog containing %ls: [0x%x].",
      pszPath,
      Catalog);
  Catalog = Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, v64, 0);
  if ( Catalog >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x541u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
        "Error verifying catalog file signature: [0x%x].",
        Catalog);
    Catalog = Windows::Compat::Appraiser::Utilities::FindCatalog(v64, v37, v48);
    if ( Catalog < 0 )
    {
      v35 = v48;
      v36 = 68;
      goto LABEL_75;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x544u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
        "Error finding catalog containing %ls: [0x%x].",
        v48,
        Catalog);
    Catalog = Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, v64, 0);
    if ( Catalog < 0 )
    {
      v38 = 71;
      goto LABEL_80;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x547u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
        "Error verifying catalog file signature: [0x%x].",
        Catalog);
LABEL_92:
    v39 = Windows::Compat::Appraiser::DataFile::Initialize(v58, pszPath);
    Catalog = v39;
    if ( v39 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x54Fu,
          "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
          "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
          "Error reading data file: [0x%x].",
          v39);
      Catalog = 0;
      goto LABEL_97;
    }
    LODWORD(v44) = v39;
    v43 = "Error reading data file: [0x%x].";
    v38 = 79;
    goto LABEL_81;
  }
  v38 = 65;
LABEL_80:
  LODWORD(v44) = Catalog;
  v43 = "Error verifying catalog file signature: [0x%x].";
LABEL_81:
  LODWORD(v41) = Catalog;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v38,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
    "Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData",
    v41,
    (int)v43,
    v44);
LABEL_97:
  if ( v31 )
    FreeLibrary(v31);
  return (unsigned int)Catalog;
}

```

## disassembly

```asm
0x18004ba00  mov     [rsp-8+arg_10], rbx
0x18004ba05  push    rbp
0x18004ba06  push    rsi
0x18004ba07  push    rdi
0x18004ba08  push    r12
0x18004ba0a  push    r13
0x18004ba0c  push    r14
0x18004ba0e  push    r15
0x18004ba10  lea     rbp, [rsp-740h]
0x18004ba18  sub     rsp, 840h
0x18004ba1f  mov     rax, cs:__security_cookie
0x18004ba26  xor     rax, rsp
0x18004ba29  mov     [rbp+770h+var_40], rax
0x18004ba30  mov     rax, [rbp+770h+arg_20]
0x18004ba37  lea     r8, aWindirSystem32; "%WINDIR%\\system32\\appraiser\\"
0x18004ba3e  mov     [rbp+770h+var_7C0], rcx
0x18004ba42  mov     r12, r9
0x18004ba45  lea     rcx, [rbp+770h+pszPath]; lpDst
0x18004ba49  mov     [rbp+770h+var_7D0], rax
0x18004ba4d  mov     [rbp+770h+var_7C8], r9
0x18004ba51  mov     [rsp+870h+var_808], rdx
0x18004ba56  mov     [rsp+870h+var_810], 0
0x18004ba5b  mov     [rsp+870h+var_80F], 0
0x18004ba60  call    ?ExpandDirectory@Utilities@Appraiser@Compat@Windows@@SAJPEAGKPEBG@Z; Windows::Compat::Appraiser::Utilities::ExpandDirectory(ushort *,ulong,ushort const *)
0x18004ba65  lea     r13, aErrorExpanding_1; "Error expanding inbox input directory: "...
0x18004ba6c  mov     ebx, eax
0x18004ba6e  test    eax, eax
0x18004ba70  jns     short loc_18004BAA1
0x18004ba72  mov     dword ptr [rsp+870h+var_840], eax; char *
0x18004ba76  lea     r9, aWindowsCompatA_668; "Windows::Compat::Appraiser::TelemetryAp"...
0x18004ba7d  mov     [rsp+870h+var_848], r13; int
0x18004ba82  lea     r8, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x18004ba89  mov     edx, 4DEh; bool
0x18004ba8e  mov     ecx, 1; this
0x18004ba93  mov     dword ptr [rsp+870h+var_850], ebx; char *
0x18004ba97  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18004ba9c  jmp     loc_18004C298
0x18004baa1  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004baa7  lea     rsi, aWindowsCompatA_668; "Windows::Compat::Appraiser::TelemetryAp"...
0x18004baae  mov     edi, 1
0x18004bab3  lea     r14, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x18004baba  and     eax, edi
0x18004babc  test    al, al
0x18004babe  jz      short loc_18004BAD7
0x18004bac0  mov     r9, r13; char *
0x18004bac3  mov     dword ptr [rsp+870h+var_850], ebx
0x18004bac7  mov     r8, rsi; char *
0x18004baca  mov     rdx, r14; char *
0x18004bacd  mov     ecx, 4DEh; unsigned int
0x18004bad2  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18004bad7  lea     r8, aAppraiserDataI; "Appraiser_Data.ini"
0x18004bade  mov     edx, 104h; cchPath
0x18004bae3  lea     rcx, [rbp+770h+pszPath]; pszPath
0x18004bae7  call    PathCchAppend
0x18004baec  lea     r15, aErrorAppending_0; "Error appending: [0x%x]."
0x18004baf3  mov     ebx, eax
0x18004baf5  test    eax, eax
0x18004baf7  jns     short loc_18004BB11
0x18004baf9  mov     edx, 4E1h
0x18004bafe  mov     dword ptr [rsp+870h+var_840], ebx
0x18004bb02  mov     [rsp+870h+var_848], r15
0x18004bb07  mov     r9, rsi
0x18004bb0a  mov     r8, r14
0x18004bb0d  mov     ecx, edi
0x18004bb0f  jmp     short loc_18004BA93
0x18004bb11  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004bb17  and     eax, edi
0x18004bb19  test    al, al
0x18004bb1b  jz      short loc_18004BB34
0x18004bb1d  mov     r9, r15; char *
0x18004bb20  mov     dword ptr [rsp+870h+var_850], ebx
0x18004bb24  mov     r8, rsi; char *
0x18004bb27  mov     rdx, r14; char *
0x18004bb2a  mov     ecx, 4E1h; unsigned int
0x18004bb2f  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18004bb34  xor     edx, edx; bool
0x18004bb36  lea     rcx, [rbp+770h+pszPath]; unsigned __int16 *
0x18004bb3a  call    ?UseAlternateInboxDataPath@DataFile@Appraiser@Compat@Windows@@SAJPEBG_N@Z; Windows::Compat::Appraiser::DataFile::UseAlternateInboxDataPath(ushort const *,bool)
0x18004bb3f  mov     ebx, eax
0x18004bb41  test    eax, eax
0x18004bb43  jns     short loc_18004BB5C
0x18004bb45  lea     r9, aErrorSettingIn_0; "Error setting inbox data file path: [0x"...
0x18004bb4c  mov     dword ptr [rsp+870h+var_840], eax
0x18004bb50  mov     [rsp+870h+var_848], r9
0x18004bb55  mov     edx, 4E4h
0x18004bb5a  jmp     short loc_18004BB07
0x18004bb5c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004bb62  and     eax, edi
0x18004bb64  test    al, al
0x18004bb66  jz      short loc_18004BB83
0x18004bb68  lea     r9, aErrorSettingIn_0; "Error setting inbox data file path: [0x"...
0x18004bb6f  mov     dword ptr [rsp+870h+var_850], ebx
0x18004bb73  mov     r8, rsi; char *
0x18004bb76  mov     rdx, r14; char *
0x18004bb79  mov     ecx, 4E4h; unsigned int
0x18004bb7e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18004bb83  xor     eax, eax
0x18004bb85  lea     rdx, ?InitOnceCallback@AppraiserTestHooks@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18004bb8c  xor     r9d, r9d; Context
0x18004bb8f  mov     [rbp+770h+pszPath], ax
0x18004bb93  xor     r8d, r8d; Parameter
0x18004bb96  lea     rcx, ?InitOnce@AppraiserTestHooks@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x18004bb9d  call    cs:__imp_InitOnceExecuteOnce
0x18004bba3  cmp     cs:?TestHookForceDeleteUnzippedAdl@AppraiserTestHooks@Appraiser@Compat@Windows@@0_NA, 0; bool Windows::Compat::Appraiser::AppraiserTestHooks::TestHookForceDeleteUnzippedAdl
0x18004bbaa  jz      short loc_18004BC10
0x18004bbac  mov     rcx, cs:?InboxDirectoryWorkingAlternate@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; unsigned __int16 *
0x18004bbb3  xor     r9d, r9d; unsigned __int16 **
0x18004bbb6  xor     r8d, r8d; unsigned __int64
0x18004bbb9  mov     [rsp+870h+var_850], 0; unsigned __int64
0x18004bbc2  xor     edx, edx; unsigned __int16 **
0x18004bbc4  call    ?DeleteFilesInFolder@Utilities@Appraiser@Compat@Windows@@SAJPEBGPEAPEBG_K12@Z; Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder(ushort const *,ushort const * *,unsigned __int64,ushort const * *,unsigned __int64)
0x18004bbc9  mov     ebx, eax
0x18004bbcb  test    eax, eax
0x18004bbcd  jns     short loc_18004BBE9
0x18004bbcf  lea     r9, aFailedToCleanT; "Failed to clean telemetry output files "...
0x18004bbd6  mov     dword ptr [rsp+870h+var_840], eax
0x18004bbda  mov     [rsp+870h+var_848], r9
0x18004bbdf  mov     edx, 4F3h
0x18004bbe4  jmp     loc_18004BB07
0x18004bbe9  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004bbef  and     eax, edi
0x18004bbf1  test    al, al
0x18004bbf3  jz      short loc_18004BC10
0x18004bbf5  lea     r9, aFailedToCleanT; "Failed to clean telemetry output files "...
0x18004bbfc  mov     dword ptr [rsp+870h+var_850], ebx
0x18004bc00  mov     r8, rsi; char *
0x18004bc03  mov     rdx, r14; char *
0x18004bc06  mov     ecx, 4F3h; unsigned int
0x18004bc0b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18004bc10  lea     rcx, [r12+8]
0x18004bc15  mov     rax, [rcx]
0x18004bc18  lea     rdx, aExpressmode; "ExpressMode"
0x18004bc1f  mov     rax, [rax+28h]
0x18004bc23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc28  test    rax, rax
0x18004bc2b  jz      short loc_18004BC4C
0x18004bc2d  mov     rdx, rax; String2
0x18004bc30  lea     rcx, aTrue_2; "TRUE"
0x18004bc37  call    wcscmp_0
0x18004bc3c  test    eax, eax
0x18004bc3e  jnz     short loc_18004BC4C
0x18004bc40  mov     r8, cs:?InboxDirectoryPathInputAlternateDataOobeCab@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::InboxDirectoryPathInputAlternateDataOobeCab
0x18004bc47  mov     al, dil
0x18004bc4a  jmp     short loc_18004BC55
0x18004bc4c  mov     r8, cs:?InboxDirectoryPathInputAlternateDataCab@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; unsigned __int16 *
0x18004bc53  xor     al, al
0x18004bc55  test    al, al
0x18004bc57  lea     rcx, aAlternatedownl; "AlternateDownloadVersion"
0x18004bc5e  lea     r12, aAlternatedownl_0; "AlternateDownloadOobeVersion"
0x18004bc65  cmovz   r12, rcx
0x18004bc69  lea     rcx, [rbp+770h+Dst]; lpDst
0x18004bc70  call    ?ExpandDirectory@Utilities@Appraiser@Compat@Windows@@SAJPEAGKPEBG@Z; Windows::Compat::Appraiser::Utilities::ExpandDirectory(ushort *,ulong,ushort const *)
0x18004bc75  mov     ebx, eax
0x18004bc77  test    eax, eax
0x18004bc79  jns     short loc_18004BC95
0x18004bc7b  lea     r9, aErrorExpanding; "Error expanding cab file path: [0x%x]."
0x18004bc82  mov     dword ptr [rsp+870h+var_840], eax
0x18004bc86  mov     [rsp+870h+var_848], r9
0x18004bc8b  mov     edx, 50Ah
0x18004bc90  jmp     loc_18004BB07
0x18004bc95  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004bc9b  and     eax, edi
0x18004bc9d  test    al, al
0x18004bc9f  jz      short loc_18004BCBC
0x18004bca1  lea     r9, aErrorExpanding; "Error expanding cab file path: [0x%x]."
0x18004bca8  mov     dword ptr [rsp+870h+var_850], ebx
0x18004bcac  mov     r8, rsi; char *
0x18004bcaf  mov     rdx, r14; char *
0x18004bcb2  mov     ecx, 50Ah; unsigned int
0x18004bcb7  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18004bcbc  mov     r9, cs:?InboxDirectoryPathInputTempDataCab@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; unsigned __int16 *
0x18004bcc3  lea     rax, [rsp+870h+var_80F]
0x18004bcc8  mov     [rsp+870h+var_848], rax; bool *
0x18004bccd  lea     rdx, [rbp+770h+Dst]; unsigned __int16 *
0x18004bcd4  mov     rax, cs:?InboxDirectoryWorkingAlternate@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::InboxDirectoryWorkingAlternate
0x18004bcdb  lea     rcx, [rsp+870h+var_810]; bool *
0x18004bce0  mov     r8, r12; unsigned __int16 *
0x18004bce3  mov     [rsp+870h+var_850], rax; unsigned __int16 *
0x18004bce8  call    ?EnsureAlternateCabUpToDateAndExtractIfNeeded@Utilities@Appraiser@Compat@Windows@@SAJAEA_NPEBG111PEA_N@Z; Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded(bool &,ushort const *,ushort const *,ushort const *,ushort const *,bool *)
0x18004bced  mov     ebx, eax
0x18004bcef  test    eax, eax
0x18004bcf1  jns     loc_18004BE49
0x18004bcf7  mov     dword ptr [rsp+870h+var_840], eax; char *
0x18004bcfb  lea     r9, aErrorGettingAl_0; "Error getting alternate data files, swa"...
0x18004bd02  mov     [rsp+870h+var_848], r9; int
0x18004bd07  mov     r8, r14; unsigned int
0x18004bd0a  mov     r9, rsi; char *
0x18004bd0d  mov     dword ptr [rsp+870h+var_850], eax; char *
0x18004bd11  mov     edx, 512h; bool
0x18004bd16  mov     ecx, edi; this
0x18004bd18  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18004bd1d  lea     rcx, [rbp+770h+var_790]; this
0x18004bd21  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18004bd26  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18004bd2d  lea     rcx, [rbp+770h+var_790]
0x18004bd31  test    rax, rax
0x18004bd34  cmovnz  rcx, rax; this
0x18004bd38  xor     edx, edx
0x18004bd3a  lock xadd [rcx+88h], rdx; unsigned __int64
0x18004bd43  lea     r8, [rbp+770h+var_4F0]; char *
0x18004bd4a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18004bd4f  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18004bd56  jz      short loc_18004BD64
0x18004bd58  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18004bd5f  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18004bd64  mov     r12, cs:qword_1802C9628
0x18004bd6b  mov     eax, [r12]
0x18004bd6f  cmp     eax, 5
0x18004bd72  jbe     loc_18004BE42
0x18004bd78  mov     rcx, [r12+18h]
0x18004bd7d  mov     rdx, 200000000000h
0x18004bd87  mov     rax, [r12+10h]
0x18004bd8c  test    rdx, rax
0x18004bd8f  jz      loc_18004BE42
0x18004bd95  mov     rax, rcx
0x18004bd98  and     rax, rdx
0x18004bd9b  cmp     rax, rcx
0x18004bd9e  jnz     loc_18004BE42
0x18004bda4  lea     rax, [rbp+770h+var_4F0]
0x18004bdab  mov     [rsp+870h+var_800], ebx
0x18004bdaf  mov     [rsp+870h+var_7F8], rax
0x18004bdb4  lea     rcx, [rbp+770h+SystemTime]; lpSystemTime
0x18004bdb8  lea     rax, szValueBuf
0x18004bdbf  mov     [rbp+770h+var_7F0], rsi
0x18004bdc3  xorps   xmm0, xmm0
0x18004bdc6  mov     [rbp+770h+var_7E0], rax
0x18004bdca  mov     [rbp+770h+var_7E8], r14
0x18004bdce  mov     [rsp+870h+var_7FC], 512h
0x18004bdd6  movups  xmmword ptr [rbp+770h+SystemTime.wYear], xmm0
0x18004bdda  call    cs:__imp_GetSystemTime
0x18004bde0  movaps  xmm0, xmmword ptr [rbp+770h+SystemTime.wYear]
0x18004bde4  lea     rax, [rbp+770h+var_7A0]
0x18004bde8  mov     [rbp+770h+var_7D8], rax
0x18004bdec  lea     rdx, unk_18029F89F
0x18004bdf3  lea     rax, [rsp+870h+var_7F8]
0x18004bdf8  movdqa  [rbp+770h+var_7A0], xmm0
0x18004bdfd  mov     [rsp+870h+var_820], rax
0x18004be02  mov     rcx, r12
0x18004be05  lea     rax, [rsp+870h+var_800]
0x18004be0a  mov     [rsp+870h+var_828], rax
0x18004be0f  lea     rax, [rbp+770h+var_7F0]
0x18004be13  mov     [rsp+870h+var_830], rax
0x18004be18  lea     rax, [rbp+770h+var_7E8]
0x18004be1c  mov     [rsp+870h+var_838], rax
0x18004be21  lea     rax, [rsp+870h+var_7FC]
0x18004be26  mov     [rsp+870h+var_840], rax
0x18004be2b  lea     rax, [rbp+770h+var_7E0]
0x18004be2f  mov     [rsp+870h+var_848], rax
0x18004be34  lea     rax, [rbp+770h+var_7D8]
0x18004be38  mov     [rsp+870h+var_850], rax
0x18004be3d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004be42  mov     [rsp+870h+var_810], 0
0x18004be47  jmp     short loc_18004BE70
0x18004be49  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004be4f  and     eax, edi
0x18004be51  test    al, al
0x18004be53  jz      short loc_18004BE70
0x18004be55  lea     r9, aErrorGettingAl_0; "Error getting alternate data files, swa"...
0x18004be5c  mov     dword ptr [rsp+870h+var_850], ebx
0x18004be60  mov     r8, rsi; char *
0x18004be63  mov     rdx, r14; char *
0x18004be66  mov     ecx, 512h; unsigned int
0x18004be6b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18004be70  mov     rcx, [rbp+770h+var_7D0]
0x18004be74  lea     rdx, aAdlinuseornotr; "AdlInUseOrNotRequestedByOnesettings"
0x18004be7b  mov     al, [rsp+870h+var_80F]
0x18004be7f  shr     ebx, 1Fh
0x18004be82  xor     bl, dil
0x18004be85  mov     [rcx+10h], al
0x18004be88  mov     r8b, bl; bool
0x18004be8b  mov     rcx, [rbp+770h+var_7C8]; this
0x18004be8f  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBG_N@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,bool)
0x18004be94  mov     ebx, eax
0x18004be96  test    eax, eax
0x18004be98  jns     short loc_18004BEB4
0x18004be9a  lea     r9, aErrorAddingIni; "Error adding init property to bag: [0x%"...
0x18004bea1  mov     dword ptr [rsp+870h+var_840], eax
0x18004bea5  mov     [rsp+870h+var_848], r9
0x18004beaa  mov     edx, 51Bh
0x18004beaf  jmp     loc_18004BB07
0x18004beb4  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004beba  and     eax, edi
0x18004bebc  test    al, al
0x18004bebe  jz      short loc_18004BEDB
0x18004bec0  lea     r9, aErrorAddingIni; "Error adding init property to bag: [0x%"...
0x18004bec7  mov     dword ptr [rsp+870h+var_850], ebx
0x18004becb  mov     r8, rsi; char *
0x18004bece  mov     rdx, r14; char *
0x18004bed1  mov     ecx, 51Bh; unsigned int
0x18004bed6  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18004bedb  cmp     [rsp+870h+var_810], 0
0x18004bee0  lea     r8, aWindirSystem32; "%WINDIR%\\system32\\appraiser\\"
0x18004bee7  lea     rcx, [rbp+770h+pszPath]; lpDst
0x18004beeb  cmovnz  r8, cs:?InboxDirectoryWorkingAlternate@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; unsigned __int16 *
0x18004bef3  call    ?ExpandDirectory@Utilities@Appraiser@Compat@Windows@@SAJPEAGKPEBG@Z; Windows::Compat::Appraiser::Utilities::ExpandDirectory(ushort *,ulong,ushort const *)
0x18004bef8  mov     ebx, eax
0x18004befa  test    eax, eax
0x18004befc  jns     short loc_18004BF11
0x18004befe  mov     dword ptr [rsp+870h+var_840], eax
0x18004bf02  mov     edx, 522h
  ... truncated ...
```
