# Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions(Windows::Compat::Appraiser::RunOptions *,ConX::Compatibility::ICompatibilityHost *,bool)

- ea: `0x180041020`
- end: `0x180041aa6`
- name: `?InitializeRunOptions@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJPEAURunOptions@234@PEAVICompatibilityHost@Compatibility@ConX@@_N@Z`
- size: `2694`
- prototype: `int(Windows::Compat::Appraiser::SetupAppraiser *__hidden this, struct Windows::Compat::Appraiser::RunOptions *, struct ConX::Compatibility::ICompatibilityHost *, bool)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180041b90`
- `0x1800450a0`

## callees

- `0x18000147c`
- `0x180008570`
- `0x1800092dc`
- `0x180013c7c`
- `0x180014ac8`
- `0x180014be8`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180039538`
- `0x180041020`
- `0x18004453c`
- `0x180082f0c`
- `0x18008ab68`
- `0x1801ac054`
- `0x1801b0af0`
- `0x1801fb6a4`
- `0x1801fd7e0`
- `0x18021f010`

## import_xrefs

- `ntdll!WinSqmIsOptedInEx` at `0x18004113d`
- `ntdll!WinSqmIsOptedInEx` at `0x18004113d`
- `KERNEL32!GetNativeSystemInfo` at `0x180041174`
- `KERNEL32!GetNativeSystemInfo` at `0x180041174`
- `KERNEL32!GetSystemTime` at `0x180041650`
- `KERNEL32!GetSystemTime` at `0x18004192c`
- `KERNEL32!GetSystemTime` at `0x180041650`
- `KERNEL32!GetSystemTime` at `0x18004192c`
- `SHLWAPI!PathFileExistsW` at `0x180041786`
- `SHLWAPI!PathFileExistsW` at `0x180041786`
- `acmigration!AcmEngineSetBaseWorkingDirectory` at `0x180041a25`
- `acmigration!AcmEngineSetBaseWorkingDirectory` at `0x180041a25`
- `acmigration!AcmEngineCreate` at `0x1800419ca`
- `acmigration!AcmEngineCreate` at `0x1800419ca`

## string_xrefs

- `0x1800411ad`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x1800411df`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180041738`: `Failed to combine SDB file path: [0x%x].`
- `0x180041764`: `Failed to combine SDB file path: [0x%x].`
- `0x18004180a`: `Failed to open appraiser database: %ls.`
- `0x180041a31`: `Error setting mig shim directory: [0x%x].`
- `0x180041a5d`: `Error setting mig shim directory: [0x%x].`
- `0x1800412dc`: `Failed to copy string: [0x%x].`
- `0x180041285`: `Failed to get working directory: [0x%x].`
- `0x1800412b1`: `Failed to get working directory: [0x%x].`
- `0x1800411b4`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions`
- `0x1800411d6`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions`
- `0x18004134f`: `Failed to get log directory: [0x%x].`
- `0x18004137b`: `Failed to get log directory: [0x%x].`
- `0x1800414d9`: `No driver install path available.`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct Windows::Compat::Appraiser::RunOptions *a2,
        struct ConX::Compatibility::ICompatibilityHost *a3,
        char a4)
{
  void (__fastcall **v7)(struct ConX::Compatibility::ICompatibilityHost *); // rax
  int v8; // ebx
  unsigned int v9; // ebx
  int v10; // eax
  Windows::Compat::Appraiser::SetupAppraiser *v11; // rcx
  char IsWin10TelemetryTypeAllowed; // al
  int v13; // eax
  unsigned int *v14; // r8
  char v15; // dl
  const wchar_t *v16; // rax
  void (__fastcall **v17)(struct ConX::Compatibility::ICompatibilityHost *); // rax
  int v18; // eax
  int v19; // eax
  void (__fastcall **v20)(struct ConX::Compatibility::ICompatibilityHost *); // rax
  int v21; // eax
  int v22; // eax
  void (__fastcall **v23)(struct ConX::Compatibility::ICompatibilityHost *); // rax
  int v24; // eax
  int v25; // eax
  void (__fastcall **v26)(struct ConX::Compatibility::ICompatibilityHost *); // rax
  int v27; // eax
  int AlternateData; // eax
  int v29; // r12d
  volatile signed __int64 *v30; // rcx
  void **v31; // rdx
  int v32; // ebx
  int v33; // r8d
  int v34; // r9d
  char v35; // al
  const WCHAR *v36; // r9
  const WCHAR *v37; // r8
  const unsigned __int16 **v38; // r13
  HRESULT v39; // eax
  void *inited; // rax
  int CustomSdbHandles; // eax
  int v42; // r12d
  volatile signed __int64 *v43; // rcx
  void **v44; // rdx
  int v45; // ebx
  int v46; // r8d
  int v47; // r9d
  int v48; // eax
  int v49; // eax
  const char *dwFlags; // [rsp+20h] [rbp-E0h]
  const char *v52; // [rsp+28h] [rbp-D8h]
  char *v53; // [rsp+30h] [rbp-D0h]
  int v54; // [rsp+60h] [rbp-A0h] BYREF
  int v55; // [rsp+64h] [rbp-9Ch] BYREF
  Windows::Compat::Appraiser::SetupAppraiser *v56; // [rsp+68h] [rbp-98h] BYREF
  char *v57; // [rsp+70h] [rbp-90h] BYREF
  const char *v58; // [rsp+78h] [rbp-88h] BYREF
  const char *v59; // [rsp+80h] [rbp-80h] BYREF
  const char *v60; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v61[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v64[804]; // [rsp+E0h] [rbp-20h] BYREF
  int v65; // [rsp+404h] [rbp+304h]
  struct _SYSTEMTIME v66; // [rsp+620h] [rbp+520h] BYREF
  char v67[144]; // [rsp+630h] [rbp+530h] BYREF
  char v68[144]; // [rsp+6C0h] [rbp+5C0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+750h] [rbp+650h] BYREF

  v56 = this;
  v54 = 0;
  memset_0(v64, 0, 0x540u);
  v7 = *(void (__fastcall ***)(struct ConX::Compatibility::ICompatibilityHost *))a3;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  v8 = ((__int64 (__fastcall *)(struct ConX::Compatibility::ICompatibilityHost *))v7[1])(a3);
  (**(void (__fastcall ***)(struct ConX::Compatibility::ICompatibilityHost *))a3)(a3);
  if ( (v8 & 0x1000219) != 0 )
  {
    if ( !a2 )
      return 0;
    *((_BYTE *)a2 + 4) = a4;
    *(_BYTE *)a2 = v8 & 1;
    *((_BYTE *)a2 + 1) = (v8 & 0x208) != 0;
    *((_BYTE *)a2 + 2) = (v8 & 0x10) != 0;
    *((_BYTE *)a2 + 3) = HIBYTE(v8) & 1;
    v10 = (*(__int64 (__fastcall **)(struct ConX::Compatibility::ICompatibilityHost *))(*(_QWORD *)a3 + 152LL))(a3);
    LOBYTE(v11) = v10 != 0;
    *((_BYTE *)a2 + 6) = v10 != 0;
    if ( v10
      || (`Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked
        ? (IsWin10TelemetryTypeAllowed = `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn)
        : (!IsWindowsVersionOrGreater(0xAu, 0, 0)
         ? (IsWin10TelemetryTypeAllowed = (unsigned int)WinSqmIsOptedInEx(4) == 1)
         : (IsWin10TelemetryTypeAllowed = Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(1u)),
           `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn = IsWin10TelemetryTypeAllowed,
           `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked = 1),
          IsWin10TelemetryTypeAllowed) )
    {
      IsWin10TelemetryTypeAllowed = 1;
    }
    *((_BYTE *)a2 + 5) = IsWin10TelemetryTypeAllowed;
    Windows::Compat::Appraiser::SetupAppraiser::SendContextEventForScanCategories(v11, a2);
    GetNativeSystemInfo(&SystemInfo);
    *((_WORD *)a2 + 44) = SystemInfo.wProcessorArchitecture;
    v13 = (*(__int64 (__fastcall **)(struct ConX::Compatibility::ICompatibilityHost *, _BYTE *))(*(_QWORD *)a3 + 16LL))(
            a3,
            v64);
    v9 = v13;
    if ( v13 < 0 )
    {
      LODWORD(v53) = v13;
      v52 = "Error getting target info: [0x%x].";
      v15 = 20;
LABEL_15:
      LODWORD(dwFlags) = v9;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v15,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
        dwFlags,
        (int)v52,
        v53);
      return v9;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x814u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
        "Error getting target info: [0x%x].",
        v13);
    if ( v65 )
    {
      switch ( v65 )
      {
        case 1:
          v16 = L"Client";
          goto LABEL_28;
        case 2:
          v16 = L"Server";
          goto LABEL_28;
        case 3:
          v16 = L"IotEnterprise";
          goto LABEL_28;
        case 4:
          v16 = L"IotEnterpriseLTSC";
LABEL_28:
          *((_QWORD *)a2 + 8) = v16;
          Windows::Compat::Appraiser::Utilities::GetMajorMinorServicepack(
            (unsigned int *)((char *)a2 + 9),
            (unsigned int *)((char *)a2 + 13),
            v14);
          v17 = *(void (__fastcall ***)(struct ConX::Compatibility::ICompatibilityHost *))a3;
          v54 = 260;
          v18 = ((__int64 (__fastcall *)(struct ConX::Compatibility::ICompatibilityHost *, WCHAR *, int *))v17[3])(
                  a3,
                  pszPathOut,
                  &v54);
          v9 = v18;
          if ( v18 < 0 )
          {
            LODWORD(v53) = v18;
            v52 = "Failed to get working directory: [0x%x].";
            v15 = 28;
            goto LABEL_15;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x81Cu,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              "Failed to get working directory: [0x%x].",
              v18);
          v19 = Windows::Compat::Appraiser::Utilities::CopyStringAlloc((const unsigned __int16 **)a2 + 5, pszPathOut);
          v9 = v19;
          if ( v19 < 0 )
          {
            LODWORD(v53) = v19;
            v52 = "Failed to copy string: [0x%x].";
            v15 = 31;
            goto LABEL_15;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x81Fu,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              "Failed to copy string: [0x%x].",
              v19);
          v20 = *(void (__fastcall ***)(struct ConX::Compatibility::ICompatibilityHost *))a3;
          v54 = 260;
          v21 = ((__int64 (__fastcall *)(struct ConX::Compatibility::ICompatibilityHost *, WCHAR *, int *))v20[4])(
                  a3,
                  pszPathOut,
                  &v54);
          v9 = v21;
          if ( v21 < 0 )
          {
            LODWORD(v53) = v21;
            v52 = "Failed to get log directory: [0x%x].";
            v15 = 35;
            goto LABEL_15;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x823u,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              "Failed to get log directory: [0x%x].",
              v21);
          v22 = Windows::Compat::Appraiser::Utilities::CopyStringAlloc((const unsigned __int16 **)a2 + 6, pszPathOut);
          v9 = v22;
          if ( v22 < 0 )
          {
            LODWORD(v53) = v22;
            v52 = "Failed to copy string: [0x%x].";
            v15 = 38;
            goto LABEL_15;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x826u,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              "Failed to copy string: [0x%x].",
              v22);
          v23 = *(void (__fastcall ***)(struct ConX::Compatibility::ICompatibilityHost *))a3;
          v54 = 260;
          v24 = ((__int64 (__fastcall *)(struct ConX::Compatibility::ICompatibilityHost *, WCHAR *, int *))v23[6])(
                  a3,
                  pszPathOut,
                  &v54);
          v9 = v24;
          if ( v24 < 0 )
          {
            LODWORD(v53) = v24;
            v52 = "Failed to get provider namespace: [0x%x].";
            v15 = 42;
            goto LABEL_15;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x82Au,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              "Failed to get provider namespace: [0x%x].",
              v24);
          v25 = Windows::Compat::Appraiser::Utilities::CopyStringAlloc((const unsigned __int16 **)a2 + 7, pszPathOut);
          v9 = v25;
          if ( v25 < 0 )
          {
            LODWORD(v53) = v25;
            v52 = "Failed to copy string: [0x%x].";
            v15 = 45;
            goto LABEL_15;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x82Du,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              "Failed to copy string: [0x%x].",
              v25);
          v26 = *(void (__fastcall ***)(struct ConX::Compatibility::ICompatibilityHost *))a3;
          v54 = 260;
          if ( ((int (__fastcall *)(struct ConX::Compatibility::ICompatibilityHost *, WCHAR *, int *))v26[21])(
                 a3,
                 pszPathOut,
                 &v54) >= 0 )
          {
            v27 = Windows::Compat::Appraiser::Utilities::CopyStringAlloc((const unsigned __int16 **)a2 + 9, pszPathOut);
            v9 = v27;
            if ( v27 < 0 )
            {
              LODWORD(v53) = v27;
              v52 = "Failed to copy string: [0x%x].";
              v15 = 56;
              goto LABEL_15;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x838u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
                "Failed to copy string: [0x%x].",
                v27);
          }
          else
          {
            Windows::Compat::Appraiser::WriteLog(
              0,
              51,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              0,
              (int)"No driver install path available.",
              v53);
          }
          AlternateData = Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData(v56, a2);
          v29 = AlternateData;
          if ( AlternateData >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x83Cu,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
                "Error checking for latest SDB, swallowing: [0x%x].",
                AlternateData);
          }
          else
          {
            LODWORD(v53) = AlternateData;
            LODWORD(dwFlags) = AlternateData;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              60,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              dwFlags,
              (int)"Error checking for latest SDB, swallowing: [0x%x].",
              v53);
            TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v67);
            v30 = (volatile signed __int64 *)v67;
            if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
              v30 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
            TraceLoggingCorrelationVector::ToStringImpl(
              (TraceLoggingCorrelationVector *)v30,
              _InterlockedExchangeAdd64(v30 + 17, 0),
              v68);
            if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
              UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v31);
            v32 = qword_1802C9628;
            if ( *(_DWORD *)qword_1802C9628 > 5u
              && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
              && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
            {
              v55 = v29;
              v57 = v68;
              v58 = "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions";
              v60 = (const char *)&szValueBuf;
              v59 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
              LODWORD(v56) = 2108;
              SystemTime = 0;
              GetSystemTime(&SystemTime);
              v61[0] = &v66;
              v66 = SystemTime;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v32,
                (unsigned int)&unk_18029E0FE,
                v33,
                v34,
                (__int64)v61,
                (__int64)&v60,
                (__int64)&v56,
                (__int64)&v59,
                (__int64)&v58,
                (__int64)&v55,
                (__int64)&v57);
            }
          }
          v35 = *((_BYTE *)a2 + 8);
          v36 = L"InboxAlternateData\\appraiser.sdb";
          if ( !v35 )
            v36 = L"appraiser.sdb";
          v54 = 260;
          if ( *((_BYTE *)a2 + 7) || v35 )
          {
            v38 = (const unsigned __int16 **)((char *)a2 + 48);
            v37 = (const WCHAR *)*((_QWORD *)a2 + 6);
          }
          else
          {
            v37 = (const WCHAR *)*((_QWORD *)a2 + 5);
            v38 = (const unsigned __int16 **)((char *)a2 + 48);
          }
          v39 = PathCchCombineEx(pszPathOut, 0x104u, v37, v36, (ULONG)dwFlags);
          v9 = v39;
          if ( v39 < 0 )
          {
            LODWORD(v53) = v39;
            v52 = "Failed to combine SDB file path: [0x%x].";
            v15 = 67;
            goto LABEL_15;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x843u,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              "Failed to combine SDB file path: [0x%x].",
              v39);
          if ( !PathFileExistsW(pszPathOut) )
          {
            v9 = -2138537982;
            v53 = (char *)pszPathOut;
            v52 = "Required Data Source file(s) do(es) not exist: %ls.";
            v15 = 72;
            goto LABEL_15;
          }
          g_ExpectedAlgorithm = 1;
          g_ExpandCallback = (__int64)Windows::Compat::Appraiser::SdbUtils::ZlibUnCompressBuffer;
          g_CompressCallback = 0;
          inited = (void *)SdbInitDatabase(3, pszPathOut);
          *((_QWORD *)a2 + 13) = inited;
          if ( !inited )
          {
            v9 = -2138546174;
            v53 = (char *)pszPathOut;
            v52 = "Failed to open appraiser database: %ls.";
            v15 = 81;
            goto LABEL_15;
          }
          Windows::Compat::Appraiser::SdbUtils::SendSdbInfoTelemetry(inited, pszPathOut);
          CustomSdbHandles = Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandles((char *)a2 + 112);
          v42 = CustomSdbHandles;
          if ( CustomSdbHandles >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x857u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
                "Error getting custom SDB handles, swallowing: [0x%x].",
                CustomSdbHandles);
          }
          else
          {
            LODWORD(v53) = CustomSdbHandles;
            LODWORD(dwFlags) = CustomSdbHandles;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              87,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              dwFlags,
              (int)"Error getting custom SDB handles, swallowing: [0x%x].",
              v53);
            TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v67);
            v43 = (volatile signed __int64 *)v67;
            if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
              v43 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
            TraceLoggingCorrelationVector::ToStringImpl(
              (TraceLoggingCorrelationVector *)v43,
              _InterlockedExchangeAdd64(v43 + 17, 0),
              v68);
            if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
              UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v44);
            v45 = qword_1802C9628;
            if ( *(_DWORD *)qword_1802C9628 > 5u
              && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
              && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
            {
              LODWORD(v56) = v42;
              v61[0] = v68;
              v60 = "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions";
              v58 = (const char *)&szValueBuf;
              v59 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
              v55 = 2135;
              SystemTime = 0;
              GetSystemTime(&SystemTime);
              v57 = (char *)&v66;
              v66 = SystemTime;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v45,
                (unsigned int)&unk_18029E09B,
                v46,
                v47,
                (__int64)&v57,
                (__int64)&v58,
                (__int64)&v55,
                (__int64)&v59,
                (__int64)&v60,
                (__int64)&v56,
                (__int64)v61);
            }
          }
          v48 = AcmEngineCreate((void **)a2 + 12);
          v9 = v48;
          if ( v48 < 0 )
          {
            LODWORD(v53) = v48;
            v52 = "Error creating mig shim engine: [0x%x].";
            v15 = 95;
            goto LABEL_15;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x85Fu,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              "Error creating mig shim engine: [0x%x].",
              v48);
          v49 = AcmEngineSetBaseWorkingDirectory(*((void **)a2 + 12), *v38);
          v9 = v49;
          if ( v49 < 0 )
          {
            LODWORD(v53) = v49;
            v52 = "Error setting mig shim directory: [0x%x].";
            v15 = 98;
            goto LABEL_15;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x862u,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions",
              "Error setting mig shim directory: [0x%x].",
              v49);
          return 0;
      }
    }
    v16 = L"Unknown";
    goto LABEL_28;
  }
  return 1;
}

```

## disassembly

```asm
0x180041020  mov     [rsp-8+arg_18], rbx
0x180041025  push    rbp
0x180041026  push    rsi
0x180041027  push    rdi
0x180041028  push    r12
0x18004102a  push    r13
0x18004102c  push    r14
0x18004102e  push    r15
0x180041030  lea     rbp, [rsp-870h]
0x180041038  sub     rsp, 970h
0x18004103f  mov     rax, cs:__security_cookie
0x180041046  xor     rax, rsp
0x180041049  mov     [rbp+8A0h+var_40], rax
0x180041050  mov     r13, r8
0x180041053  mov     [rsp+9A0h+var_938], rcx
0x180041058  mov     r15, rdx
0x18004105b  mov     [rsp+9A0h+var_940], 0
0x180041063  xor     edx, edx; Val
0x180041065  lea     rcx, [rbp+8A0h+var_8C0]; void *
0x180041069  mov     r8d, 540h; Size
0x18004106f  mov     sil, r9b
0x180041072  call    memset_0
0x180041077  mov     rax, [r13+0]
0x18004107b  xorps   xmm0, xmm0
0x18004107e  mov     rcx, r13
0x180041081  movups  xmmword ptr [rbp+8A0h+SystemInfo], xmm0
0x180041085  mov     rax, [rax+8]
0x180041089  movups  xmmword ptr [rbp+8A0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18004108d  movups  xmmword ptr [rbp+8A0h+SystemInfo.dwNumberOfProcessors], xmm0
0x180041091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041096  mov     rcx, [r13+0]
0x18004109a  mov     ebx, eax
0x18004109c  mov     rax, [rcx]
0x18004109f  mov     rcx, r13
0x1800410a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410a7  test    ebx, 1000219h
0x1800410ad  jnz     short loc_1800410B9
0x1800410af  mov     ebx, 1
0x1800410b4  jmp     loc_180041A7A
0x1800410b9  test    r15, r15
0x1800410bc  jz      loc_180041A78
0x1800410c2  mov     eax, ebx
0x1800410c4  mov     [r15+4], sil
0x1800410c8  mov     edi, 1
0x1800410cd  mov     rcx, r13
0x1800410d0  and     al, dil
0x1800410d3  mov     [r15], al
0x1800410d6  test    ebx, 208h
0x1800410dc  setnz   al
0x1800410df  mov     [r15+1], al
0x1800410e3  mov     eax, ebx
0x1800410e5  shr     eax, 4
0x1800410e8  and     al, dil
0x1800410eb  shr     ebx, 18h
0x1800410ee  mov     [r15+2], al
0x1800410f2  and     bl, dil
0x1800410f5  mov     [r15+3], bl
0x1800410f9  mov     rax, [r13+0]
0x1800410fd  mov     rax, [rax+98h]
0x180041104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041109  test    eax, eax
0x18004110b  setnz   cl; this
0x18004110e  mov     [r15+6], cl
0x180041112  test    eax, eax
0x180041114  jnz     short loc_180041161
0x180041116  cmp     cs:?AlreadyChecked@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, al; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x18004111c  jnz     short loc_180041157
0x18004111e  xor     r8d, r8d; unsigned __int16
0x180041121  lea     ecx, [rdi+9]; unsigned __int16
0x180041124  xor     edx, edx; unsigned __int16
0x180041126  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18004112b  test    al, al
0x18004112d  jz      short loc_180041138
0x18004112f  mov     ecx, edi; unsigned int
0x180041131  call    ?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)
0x180041136  jmp     short loc_180041148
0x180041138  mov     ecx, 4
0x18004113d  call    cs:__imp_WinSqmIsOptedInEx
0x180041143  cmp     eax, edi
0x180041145  setz    al
0x180041148  mov     cs:?IsOptedIn@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, al; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x18004114e  mov     cs:?AlreadyChecked@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, dil; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x180041155  jmp     short loc_18004115D
0x180041157  mov     al, cs:?IsOptedIn@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x18004115d  test    al, al
0x18004115f  jz      short loc_180041164
0x180041161  mov     al, dil
0x180041164  mov     rdx, r15; struct Windows::Compat::Appraiser::RunOptions *
0x180041167  mov     [r15+5], al
0x18004116b  call    ?SendContextEventForScanCategories@SetupAppraiser@Appraiser@Compat@Windows@@AEAAXPEAURunOptions@234@@Z; Windows::Compat::Appraiser::SetupAppraiser::SendContextEventForScanCategories(Windows::Compat::Appraiser::RunOptions *)
0x180041170  lea     rcx, [rbp+8A0h+SystemInfo]; lpSystemInfo
0x180041174  call    cs:__imp_GetNativeSystemInfo
0x18004117a  movzx   eax, word ptr [rbp+8A0h+SystemInfo]
0x18004117e  lea     rdx, [rbp+8A0h+var_8C0]
0x180041182  mov     [r15+58h], ax
0x180041187  mov     rcx, r13
0x18004118a  mov     rax, [r13+0]
0x18004118e  mov     rax, [rax+10h]
0x180041192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041197  mov     ebx, eax
0x180041199  test    eax, eax
0x18004119b  jns     short loc_1800411D0
0x18004119d  lea     r9, aErrorGettingTa_0; "Error getting target info: [0x%x]."
0x1800411a4  mov     dword ptr [rsp+9A0h+var_970], eax; char *
0x1800411a8  mov     qword ptr [rsp+9A0h+var_978], r9; int
0x1800411ad  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800411b4  lea     r9, aWindowsCompatA_626; "Windows::Compat::Appraiser::SetupApprai"...
0x1800411bb  mov     edx, 814h; bool
0x1800411c0  mov     ecx, edi; this
0x1800411c2  mov     [rsp+9A0h+dwFlags], ebx; char *
0x1800411c6  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800411cb  jmp     loc_180041A7A
0x1800411d0  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800411d6  lea     rsi, aWindowsCompatA_626; "Windows::Compat::Appraiser::SetupApprai"...
0x1800411dd  and     eax, edi
0x1800411df  lea     r14, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800411e6  test    al, al
0x1800411e8  jz      short loc_180041205
0x1800411ea  lea     r9, aErrorGettingTa_0; "Error getting target info: [0x%x]."
0x1800411f1  mov     [rsp+9A0h+dwFlags], ebx
0x1800411f5  mov     r8, rsi; char *
0x1800411f8  mov     rdx, r14; char *
0x1800411fb  mov     ecx, 814h; unsigned int
0x180041200  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180041205  mov     ecx, [rbp+8A0h+var_59C]
0x18004120b  test    ecx, ecx
0x18004120d  jz      short loc_180041243
0x18004120f  sub     ecx, edi
0x180041211  jz      short loc_18004123A
0x180041213  sub     ecx, edi
0x180041215  jz      short loc_180041231
0x180041217  sub     ecx, edi
0x180041219  jz      short loc_180041228
0x18004121b  cmp     ecx, edi
0x18004121d  jnz     short loc_180041243
0x18004121f  lea     rax, aIotenterprisel; "IotEnterpriseLTSC"
0x180041226  jmp     short loc_18004124A
0x180041228  lea     rax, aIotenterprise; "IotEnterprise"
0x18004122f  jmp     short loc_18004124A
0x180041231  lea     rax, aServer; "Server"
0x180041238  jmp     short loc_18004124A
0x18004123a  lea     rax, aClient; "Client"
0x180041241  jmp     short loc_18004124A
0x180041243  lea     rax, aUnknown; "Unknown"
0x18004124a  lea     rdx, [r15+0Dh]; unsigned int *
0x18004124e  mov     [r15+40h], rax
0x180041252  lea     rcx, [r15+9]; unsigned int *
0x180041256  call    ?GetMajorMinorServicepack@Utilities@Appraiser@Compat@Windows@@SAXPEAK00@Z; Windows::Compat::Appraiser::Utilities::GetMajorMinorServicepack(ulong *,ulong *,ulong *)
0x18004125b  mov     rax, [r13+0]
0x18004125f  lea     r8, [rsp+9A0h+var_940]
0x180041264  lea     rdx, [rbp+8A0h+pszPathOut]
0x18004126b  mov     [rsp+9A0h+var_940], 104h
0x180041273  mov     rcx, r13
0x180041276  mov     rax, [rax+18h]
0x18004127a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004127f  mov     ebx, eax
0x180041281  test    eax, eax
0x180041283  jns     short loc_1800412A5
0x180041285  lea     r9, aFailedToGetWor; "Failed to get working directory: [0x%x]"...
0x18004128c  mov     dword ptr [rsp+9A0h+var_970], eax
0x180041290  mov     qword ptr [rsp+9A0h+var_978], r9
0x180041295  mov     r8, r14
0x180041298  mov     r9, rsi
0x18004129b  mov     edx, 81Ch
0x1800412a0  jmp     loc_1800411C0
0x1800412a5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800412ab  and     eax, edi
0x1800412ad  test    al, al
0x1800412af  jz      short loc_1800412CC
0x1800412b1  lea     r9, aFailedToGetWor; "Failed to get working directory: [0x%x]"...
0x1800412b8  mov     [rsp+9A0h+dwFlags], ebx
0x1800412bc  mov     r8, rsi; char *
0x1800412bf  mov     rdx, r14; char *
0x1800412c2  mov     ecx, 81Ch; unsigned int
0x1800412c7  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800412cc  lea     rcx, [r15+28h]; unsigned __int16 **
0x1800412d0  lea     rdx, [rbp+8A0h+pszPathOut]; unsigned __int16 *
0x1800412d7  call    ?CopyStringAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEBGPEBG@Z; Windows::Compat::Appraiser::Utilities::CopyStringAlloc(ushort const * *,ushort const *)
0x1800412dc  lea     r12, aFailedToCopySt_0; "Failed to copy string: [0x%x]."
0x1800412e3  mov     ebx, eax
0x1800412e5  test    eax, eax
0x1800412e7  jns     short loc_180041302
0x1800412e9  mov     dword ptr [rsp+9A0h+var_970], eax
0x1800412ed  mov     r9, rsi
0x1800412f0  mov     qword ptr [rsp+9A0h+var_978], r12
0x1800412f5  mov     r8, r14
0x1800412f8  mov     edx, 81Fh
0x1800412fd  jmp     loc_1800411C0
0x180041302  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180041308  and     eax, edi
0x18004130a  test    al, al
0x18004130c  jz      short loc_180041325
0x18004130e  mov     r9, r12; char *
0x180041311  mov     [rsp+9A0h+dwFlags], ebx
0x180041315  mov     r8, rsi; char *
0x180041318  mov     rdx, r14; char *
0x18004131b  mov     ecx, 81Fh; unsigned int
0x180041320  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180041325  mov     rax, [r13+0]
0x180041329  lea     r8, [rsp+9A0h+var_940]
0x18004132e  lea     rdx, [rbp+8A0h+pszPathOut]
0x180041335  mov     [rsp+9A0h+var_940], 104h
0x18004133d  mov     rcx, r13
0x180041340  mov     rax, [rax+20h]
0x180041344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041349  mov     ebx, eax
0x18004134b  test    eax, eax
0x18004134d  jns     short loc_18004136F
0x18004134f  lea     r9, aFailedToGetLog; "Failed to get log directory: [0x%x]."
0x180041356  mov     dword ptr [rsp+9A0h+var_970], eax
0x18004135a  mov     qword ptr [rsp+9A0h+var_978], r9
0x18004135f  mov     r8, r14
0x180041362  mov     r9, rsi
0x180041365  mov     edx, 823h
0x18004136a  jmp     loc_1800411C0
0x18004136f  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180041375  and     eax, edi
0x180041377  test    al, al
0x180041379  jz      short loc_180041396
0x18004137b  lea     r9, aFailedToGetLog; "Failed to get log directory: [0x%x]."
0x180041382  mov     [rsp+9A0h+dwFlags], ebx
0x180041386  mov     r8, rsi; char *
0x180041389  mov     rdx, r14; char *
0x18004138c  mov     ecx, 823h; unsigned int
0x180041391  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180041396  lea     rcx, [r15+30h]; unsigned __int16 **
0x18004139a  lea     rdx, [rbp+8A0h+pszPathOut]; unsigned __int16 *
0x1800413a1  call    ?CopyStringAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEBGPEBG@Z; Windows::Compat::Appraiser::Utilities::CopyStringAlloc(ushort const * *,ushort const *)
0x1800413a6  mov     ebx, eax
0x1800413a8  test    eax, eax
0x1800413aa  jns     short loc_1800413C5
0x1800413ac  mov     dword ptr [rsp+9A0h+var_970], eax
0x1800413b0  mov     r9, rsi
0x1800413b3  mov     qword ptr [rsp+9A0h+var_978], r12
0x1800413b8  mov     r8, r14
0x1800413bb  mov     edx, 826h
0x1800413c0  jmp     loc_1800411C0
0x1800413c5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800413cb  and     eax, edi
0x1800413cd  test    al, al
0x1800413cf  jz      short loc_1800413E8
0x1800413d1  mov     r9, r12; char *
0x1800413d4  mov     [rsp+9A0h+dwFlags], ebx
0x1800413d8  mov     r8, rsi; char *
0x1800413db  mov     rdx, r14; char *
0x1800413de  mov     ecx, 826h; unsigned int
0x1800413e3  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800413e8  mov     rax, [r13+0]
0x1800413ec  lea     r8, [rsp+9A0h+var_940]
0x1800413f1  lea     rdx, [rbp+8A0h+pszPathOut]
0x1800413f8  mov     [rsp+9A0h+var_940], 104h
0x180041400  mov     rcx, r13
0x180041403  mov     rax, [rax+30h]
0x180041407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004140c  mov     ebx, eax
0x18004140e  test    eax, eax
0x180041410  jns     short loc_180041432
0x180041412  lea     r9, aFailedToGetPro; "Failed to get provider namespace: [0x%x"...
0x180041419  mov     dword ptr [rsp+9A0h+var_970], eax
0x18004141d  mov     qword ptr [rsp+9A0h+var_978], r9
0x180041422  mov     r8, r14
0x180041425  mov     r9, rsi
0x180041428  mov     edx, 82Ah
0x18004142d  jmp     loc_1800411C0
0x180041432  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180041438  and     eax, edi
0x18004143a  test    al, al
0x18004143c  jz      short loc_180041459
0x18004143e  lea     r9, aFailedToGetPro; "Failed to get provider namespace: [0x%x"...
0x180041445  mov     [rsp+9A0h+dwFlags], ebx
0x180041449  mov     r8, rsi; char *
0x18004144c  mov     rdx, r14; char *
0x18004144f  mov     ecx, 82Ah; unsigned int
0x180041454  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180041459  lea     rcx, [r15+38h]; unsigned __int16 **
0x18004145d  lea     rdx, [rbp+8A0h+pszPathOut]; unsigned __int16 *
0x180041464  call    ?CopyStringAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEBGPEBG@Z; Windows::Compat::Appraiser::Utilities::CopyStringAlloc(ushort const * *,ushort const *)
0x180041469  mov     ebx, eax
0x18004146b  test    eax, eax
0x18004146d  jns     short loc_180041488
0x18004146f  mov     dword ptr [rsp+9A0h+var_970], eax
0x180041473  mov     r9, rsi
0x180041476  mov     qword ptr [rsp+9A0h+var_978], r12
0x18004147b  mov     r8, r14
0x18004147e  mov     edx, 82Dh
0x180041483  jmp     loc_1800411C0
0x180041488  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004148e  and     eax, edi
0x180041490  test    al, al
0x180041492  jz      short loc_1800414AB
0x180041494  mov     r9, r12; char *
0x180041497  mov     [rsp+9A0h+dwFlags], ebx
0x18004149b  mov     r8, rsi; char *
0x18004149e  mov     rdx, r14; char *
0x1800414a1  mov     ecx, 82Dh; unsigned int
0x1800414a6  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800414ab  mov     rax, [r13+0]
0x1800414af  lea     r8, [rsp+9A0h+var_940]
0x1800414b4  lea     rdx, [rbp+8A0h+pszPathOut]
0x1800414bb  mov     [rsp+9A0h+var_940], 104h
  ... truncated ...
```
