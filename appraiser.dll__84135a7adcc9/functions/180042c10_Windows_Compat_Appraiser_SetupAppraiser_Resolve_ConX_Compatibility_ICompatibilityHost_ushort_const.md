# Windows::Compat::Appraiser::SetupAppraiser::Resolve(ConX::Compatibility::ICompatibilityHost *,ushort const *)

- ea: `0x180042c10`
- end: `0x18004376d`
- name: `?Resolve@SetupAppraiser@Appraiser@Compat@Windows@@UEAAJPEAVICompatibilityHost@Compatibility@ConX@@PEBG@Z`
- size: `2909`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::SetupAppraiser *__hidden this, struct ConX::Compatibility::ICompatibilityHost *, char *)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000147c`
- `0x1800018a0`
- `0x180001990`
- `0x180001b94`
- `0x180001cc0`
- `0x180008570`
- `0x180013c7c`
- `0x180014894`
- `0x1800151f4`
- `0x180029258`
- `0x18002a8b4`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18003945c`
- `0x180042c10`
- `0x180043774`
- `0x180043a34`
- `0x180043d28`
- `0x1800466a0`
- `0x1800467cc`
- `0x180046cd4`
- `0x1800470f8`
- `0x180088980`
- `0x180088c0c`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180042d17`
- `KERNEL32!ResetEvent` at `0x180042d17`
- `KERNEL32!TryEnterCriticalSection` at `0x180042cee`
- `KERNEL32!TryEnterCriticalSection` at `0x180042cee`
- `KERNEL32!GetSystemTime` at `0x180042de4`
- `KERNEL32!GetSystemTime` at `0x180042ee8`
- `KERNEL32!GetSystemTime` at `0x1800430ff`
- `KERNEL32!GetSystemTime` at `0x1800433a2`
- `KERNEL32!GetSystemTime` at `0x180043517`
- `KERNEL32!GetSystemTime` at `0x1800436b4`
- `KERNEL32!GetSystemTime` at `0x180042de4`
- `KERNEL32!GetSystemTime` at `0x180042ee8`
- `KERNEL32!GetSystemTime` at `0x1800430ff`
- `KERNEL32!GetSystemTime` at `0x1800433a2`
- `KERNEL32!GetSystemTime` at `0x180043517`
- `KERNEL32!GetSystemTime` at `0x1800436b4`
- `KERNEL32!LeaveCriticalSection` at `0x1800435ad`
- `KERNEL32!LeaveCriticalSection` at `0x1800435ad`

## string_xrefs

- `0x180042caf`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180042d04`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180042f55`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180042f99`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180042fe4`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18004318c`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x1800431db`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180043230`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180042f86`: `Error reading stored data: [0x%x].`
- `0x180042fcd`: `Error reading stored data: [0x%x].`
- `0x180042c96`: `Windows::Compat::Appraiser::SetupAppraiser::Resolve`
- `0x180042cfd`: `Windows::Compat::Appraiser::SetupAppraiser::Resolve`
- `0x180042f4e`: `Windows::Compat::Appraiser::SetupAppraiser::Resolve`
- `0x180042f92`: `Windows::Compat::Appraiser::SetupAppraiser::Resolve`
- `0x180042fd8`: `Windows::Compat::Appraiser::SetupAppraiser::Resolve`
- `0x180043183`: `Windows::Compat::Appraiser::SetupAppraiser::Resolve`
- `0x1800431d2`: `Windows::Compat::Appraiser::SetupAppraiser::Resolve`
- `0x180043227`: `Windows::Compat::Appraiser::SetupAppraiser::Resolve`
- `0x180042ccf`: `RemoveAllDismissibleHB`
- `0x180042cbb`: `UninstallAllHBApp`
- `0x180043197`: `Error (or cancel) resolving all uninstalls: [0x%x].`
- `0x1800431b7`: `Error (or cancel) resolving all uninstalls: [0x%x].`
- `0x18004323f`: `Error finding uninstall path for %ls: [0x%x].`
- `0x18004327d`: `Error finding uninstall path for %ls: [0x%x].`
- `0x1800435d8`: `Error setting resolve complete: [0x%x].`
- `0x180043726`: `Error setting resolve complete: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::SetupAppraiser::Resolve(
        HANDLE *this,
        struct ConX::Compatibility::ICompatibilityHost *a2,
        const wchar_t *a3)
{
  __int64 v3; // rax
  char v5; // r13
  int v8; // edi
  char v9; // dl
  const char *v10; // rcx
  int v11; // edi
  int v12; // r12d
  int v13; // ebx
  volatile signed __int64 *v14; // rcx
  void **v15; // rdx
  int v16; // ebx
  int v17; // r8d
  int v18; // r9d
  volatile signed __int64 *v19; // rcx
  void **v20; // rdx
  int v21; // ebx
  int v22; // r8d
  int v23; // r9d
  const char *v24; // r9
  char v25; // dl
  volatile signed __int64 *v26; // rcx
  void **v27; // rdx
  int v28; // ebx
  unsigned __int16 *v29; // rcx
  unsigned __int64 v30; // rdx
  int v31; // r8d
  int v32; // r9d
  const char *v33; // r9
  unsigned int v34; // ecx
  const char *v35; // rdi
  int UninstallInfo; // eax
  volatile signed __int64 *v37; // rcx
  void **v38; // rdx
  int v39; // edi
  int v40; // r8d
  int v41; // r9d
  int v42; // eax
  int v43; // esi
  volatile signed __int64 *v44; // rcx
  void **v45; // rdx
  int v46; // edi
  int v47; // r8d
  int v48; // r9d
  int v49; // eax
  int v50; // esi
  volatile signed __int64 *v51; // rcx
  void **v52; // rdx
  int v53; // edi
  int v54; // r8d
  int v55; // r9d
  char *v57; // [rsp+20h] [rbp-E0h]
  char *v58; // [rsp+20h] [rbp-E0h]
  char *v59; // [rsp+30h] [rbp-D0h]
  char *v60; // [rsp+30h] [rbp-D0h]
  char *v61; // [rsp+30h] [rbp-D0h]
  __int64 v62; // [rsp+38h] [rbp-C8h]
  char v63; // [rsp+70h] [rbp-90h]
  struct _SYSTEMTIME *v64; // [rsp+78h] [rbp-88h] BYREF
  struct _SYSTEMTIME *v65; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME *v66; // [rsp+88h] [rbp-78h] BYREF
  const char *v67; // [rsp+90h] [rbp-70h] BYREF
  char v68[8]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v69[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-50h] BYREF
  char *v71; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v72; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v73; // [rsp+D0h] [rbp-30h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+D8h] [rbp-28h] BYREF
  struct _SYSTEMTIME v75; // [rsp+E0h] [rbp-20h] BYREF
  struct _SYSTEMTIME v76; // [rsp+F0h] [rbp-10h] BYREF
  char v77[144]; // [rsp+100h] [rbp+0h] BYREF
  char v78[144]; // [rsp+190h] [rbp+90h] BYREF

  v3 = *(_QWORD *)a2;
  v5 = 0;
  v69[0] = 0;
  v8 = (*(__int64 (__fastcall **)(struct ConX::Compatibility::ICompatibilityHost *))(v3 + 152))(a2);
  Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(
    (Windows::Compat::Shared::Telemetry::TelemetryProvider *)&APPRAISER_UTC_PROVIDER,
    v8 != 0);
  v9 = 108;
  Windows::Compat::Appraiser::AppraiserSettings::ForcedOptIn = v8 != 0;
  v10 = "Opted in to telemetry";
  if ( !v8 )
  {
    v10 = "Not opted in to telemetry.";
    v9 = 112;
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    v9,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
    0,
    (int)v10,
    v59);
  v63 = 0;
  v11 = wcscmp_0(a3, L"UninstallAllHBApp");
  v12 = wcscmp_0(a3, L"RemoveAllDismissibleHB");
  lpCriticalSection = (LPCRITICAL_SECTION)(this + 1);
  if ( !TryEnterCriticalSection((LPCRITICAL_SECTION)(this + 1)) )
  {
    v13 = -2147024726;
    goto LABEL_62;
  }
  v5 = 1;
  ResetEvent(this[6]);
  Windows::Compat::Appraiser::SetupAppraiser::UpdateCorrelationVector(a2);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v77);
  v14 = (volatile signed __int64 *)v77;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v14 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v14,
    _InterlockedExchangeAdd64(v14 + 17, 0),
    v78);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v15);
  v16 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v72 = 0x1000000;
    v71 = v78;
    LOWORD(v64) = (**(__int64 (__fastcall ***)(struct ConX::Compatibility::ICompatibilityHost *))a2)(a2);
    v73 = (__int64)&szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v65 = &v75;
    v75 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v16,
      (unsigned int)&unk_18029DCBA,
      v17,
      v18,
      (__int64)&v65,
      (__int64)&v73,
      (__int64)&v64,
      (__int64)&v72,
      (__int64)&v71);
  }
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v77);
  v19 = (volatile signed __int64 *)v77;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v19 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v19,
    _InterlockedExchangeAdd64(v19 + 17, 0),
    v78);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v20);
  v21 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000002LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000002LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v73 = 0x1000000;
    v65 = (struct _SYSTEMTIME *)v78;
    v72 = (__int64)a3;
    v71 = (char *)&szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v64 = &v75;
    v75 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v21,
      (unsigned int)&unk_18029DC0B,
      v22,
      v23,
      (__int64)&v64,
      (__int64)&v71,
      (__int64)&v72,
      (__int64)&v73,
      (__int64)&v65);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    133,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
    0,
    (int)"Resolve called for %ls",
    (const char *)a3);
  v13 = Windows::Compat::Appraiser::PersistedData::Read((Windows::Compat::Appraiser::PersistedData *)(this + 19), a2);
  if ( v13 < 0 )
  {
    v24 = "Error reading stored data: [0x%x].";
    v25 = -115;
LABEL_23:
    LODWORD(v60) = v13;
    LODWORD(v57) = v13;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v25,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
      v57,
      (int)v24,
      v60);
    goto LABEL_62;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xE8Du,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
      "Error reading stored data: [0x%x].",
      v13);
  v63 = 1;
  Windows::Compat::Appraiser::SetupAppraiser::UpdateSyncId((Windows::Compat::Appraiser::SetupAppraiser *)this);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v77);
  v26 = (volatile signed __int64 *)v77;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v26 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v26,
    _InterlockedExchangeAdd64(v26 + 17, 0),
    v78);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v27);
  v28 = qword_1802C9560;
  if ( *(_DWORD *)qword_1802C9560 > 5u )
  {
    v29 = *(unsigned __int16 **)(qword_1802C9560 + 24);
    v30 = 0x800000000000LL;
    if ( (*(_QWORD *)(qword_1802C9560 + 16) & 0x800000000000LL) != 0
      && (unsigned __int16 *)((unsigned __int64)v29 & 0x800000000000LL) == v29 )
    {
      v73 = 0x1000000;
      v65 = (struct _SYSTEMTIME *)v78;
      v72 = (__int64)L"Resolve";
      v71 = (char *)L"Setup";
      if ( !Windows::Compat::Appraiser::WicaFactory::AppraiserProcessExeBuffer )
        Windows::Compat::Appraiser::Utilities::GetAppraiserProcessExe(v29, 0x800000000000uLL);
      v64 = (struct _SYSTEMTIME *)&Windows::Compat::Appraiser::WicaFactory::AppraiserProcessExeBuffer;
      if ( !Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer )
        Windows::Compat::Appraiser::Utilities::GetAppraiserBranch(v29, v30);
      v66 = (struct _SYSTEMTIME *)&Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer;
      v67 = (const char *)Windows::Compat::Appraiser::WicaFactory::AppraiserVersion();
      *(_QWORD *)v68 = &szValueBuf;
      v75 = 0;
      GetSystemTime(&v75);
      *(_QWORD *)&SystemTime.wYear = &v76;
      v76 = v75;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v28,
        (unsigned int)&unk_18029DB7F,
        v31,
        v32,
        (__int64)&SystemTime,
        (__int64)v68,
        (__int64)&v67,
        (__int64)&v66,
        (__int64)&v64,
        (__int64)&v71,
        (__int64)&v72,
        (__int64)&v73,
        (__int64)&v65);
    }
  }
  if ( !v11 )
  {
    v13 = Windows::Compat::Appraiser::SetupAppraiser::ResolveAllUninstalls((Windows::Compat::Appraiser::SetupAppraiser *)this);
    if ( v13 < 0 )
    {
      v24 = "Error (or cancel) resolving all uninstalls: [0x%x].";
      v25 = -102;
      goto LABEL_23;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
      goto LABEL_61;
    v33 = "Error (or cancel) resolving all uninstalls: [0x%x].";
    v34 = 3738;
    goto LABEL_60;
  }
  if ( !v12 )
  {
    v13 = Windows::Compat::Appraiser::SetupAppraiser::ResolveAllDismiss((Windows::Compat::Appraiser::SetupAppraiser *)this);
    if ( v13 < 0 )
    {
      v24 = "Error (or cancel) resolving all dismiss items: [0x%x].";
      v25 = -97;
      goto LABEL_23;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
      goto LABEL_61;
    v33 = "Error (or cancel) resolving all dismiss items: [0x%x].";
    v34 = 3743;
    goto LABEL_60;
  }
  v35 = (const char *)(a3 + 1);
  UninstallInfo = Windows::Compat::Appraiser::SetupAppraiser::FindUninstallInfo(
                    (Windows::Compat::Appraiser::SetupAppraiser *)this,
                    (const unsigned __int16 **)v69,
                    a3 + 1);
  v13 = UninstallInfo;
  if ( UninstallInfo < 0 )
  {
    LODWORD(v62) = UninstallInfo;
    LODWORD(v57) = UninstallInfo;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      165,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
      v57,
      (int)"Error finding uninstall path for %ls: [0x%x].",
      v35,
      v62);
    goto LABEL_62;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xEA5u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
      "Error finding uninstall path for %ls: [0x%x].",
      (const wchar_t *)v35,
      UninstallInfo);
  if ( v13 == 1 )
  {
    v13 = -2147024637;
    goto LABEL_62;
  }
  if ( v13 )
  {
    v13 = -2147467259;
    goto LABEL_62;
  }
  v13 = Windows::Compat::Appraiser::SetupAppraiser::ResolveOne(
          (Windows::Compat::Appraiser::SetupAppraiser *)this,
          v69[0],
          (const unsigned __int16 *)v35);
  if ( v13 < 0 )
  {
    v24 = "Error (or cancel) with ResolveOne: [0x%x].";
    v25 = -77;
    goto LABEL_23;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    v33 = "Error (or cancel) with ResolveOne: [0x%x].";
    v34 = 3763;
LABEL_60:
    LODWORD(v57) = v13;
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      v34,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
      v33,
      v57);
  }
LABEL_61:
  v13 = 0;
LABEL_62:
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v77);
  v37 = (volatile signed __int64 *)v77;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v37 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v37,
    _InterlockedExchangeAdd64(v37 + 17, 0),
    v78);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v38);
  v39 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000002LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000002LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)v68 = 0x1000000;
    *(_QWORD *)&SystemTime.wYear = v78;
    v67 = (const char *)&szValueBuf;
    v75 = 0;
    GetSystemTime(&v75);
    v66 = &v76;
    v76 = v75;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v39,
      (unsigned int)&unk_18029DADA,
      v40,
      v41,
      (__int64)&v66,
      (__int64)&v67,
      (__int64)v68,
      (__int64)&SystemTime);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    186,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
    0,
    (int)"Resolve Done",
    v60);
  if ( v63 )
  {
    v42 = Windows::Compat::Appraiser::PersistedData::Save((Windows::Compat::Appraiser::PersistedData *)(this + 19), a2);
    v43 = v42;
    if ( v42 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xEC3u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
          "Error storing data: [0x%x].",
          v13);
    }
    else
    {
      LODWORD(v61) = v13;
      LODWORD(v58) = v42;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        195,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
        v58,
        (int)"Error storing data: [0x%x].",
        v61);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v77);
      v44 = (volatile signed __int64 *)v77;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v44 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v44,
        _InterlockedExchangeAdd64(v44 + 17, 0),
        v78);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v45);
      v46 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        LODWORD(v64) = v43;
        *(_QWORD *)&SystemTime.wYear = v78;
        *(_QWORD *)v68 = "Windows::Compat::Appraiser::SetupAppraiser::Resolve";
        v66 = (struct _SYSTEMTIME *)&szValueBuf;
        v67 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
        LODWORD(v69[0]) = 3779;
        v75 = 0;
        GetSystemTime(&v75);
        v65 = &v76;
        v76 = v75;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v46,
          (unsigned int)&unk_18029DB1C,
          v47,
          v48,
          (__int64)&v65,
          (__int64)&v66,
          (__int64)v69,
          (__int64)&v67,
          (__int64)v68,
          (__int64)&v64,
          (__int64)&SystemTime);
      }
    }
  }
  if ( v5 )
    LeaveCriticalSection(lpCriticalSection);
  if ( v13 >= 0 )
  {
    v49 = (*(__int64 (__fastcall **)(struct ConX::Compatibility::ICompatibilityHost *))(*(_QWORD *)a2 + 120LL))(a2);
    v50 = v49;
    if ( v49 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xED3u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
          "Error setting resolve complete: [0x%x].",
          v49);
    }
    else
    {
      LODWORD(v61) = v49;
      LODWORD(v58) = v49;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        211,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::Resolve",
        v58,
        (int)"Error setting resolve complete: [0x%x].",
        v61);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v77);
      v51 = (volatile signed __int64 *)v77;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v51 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v51,
        _InterlockedExchangeAdd64(v51 + 17, 0),
        v78);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v52);
      v53 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        LODWORD(v69[0]) = v50;
        lpCriticalSection = (LPCRITICAL_SECTION)v78;
        *(_QWORD *)&SystemTime.wYear = "Windows::Compat::Appraiser::SetupAppraiser::Resolve";
        v67 = (const char *)&szValueBuf;
        *(_QWORD *)v68 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
        LODWORD(v64) = 3795;
        v75 = 0;
        GetSystemTime(&v75);
        v66 = &v76;
        v76 = v75;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v53,
          (unsigned int)&unk_18029DA77,
          v54,
          v55,
          (__int64)&v66,
          (__int64)&v67,
          (__int64)&v64,
          (__int64)v68,
          (__int64)&SystemTime,
          (__int64)v69,
          (__int64)&lpCriticalSection);
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180042c10  mov     [rsp-8+arg_18], rbx
0x180042c15  push    rbp
0x180042c16  push    rsi
0x180042c17  push    rdi
0x180042c18  push    r12
0x180042c1a  push    r13
0x180042c1c  push    r14
0x180042c1e  push    r15
0x180042c20  lea     rbp, [rsp-130h]
0x180042c28  sub     rsp, 230h
0x180042c2f  mov     rax, cs:__security_cookie
0x180042c36  xor     rax, rsp
0x180042c39  mov     [rbp+160h+var_40], rax
0x180042c40  mov     rax, [rdx]
0x180042c43  mov     rsi, rcx
0x180042c46  xor     r13d, r13d
0x180042c49  mov     rcx, rdx
0x180042c4c  mov     r15, r8
0x180042c4f  mov     [rbp+160h+var_1C0], r13
0x180042c53  mov     r14, rdx
0x180042c56  mov     rax, [rax+98h]
0x180042c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c62  test    eax, eax
0x180042c64  lea     rcx, ?APPRAISER_UTC_PROVIDER@@3VTelemetryProvider@Telemetry@Shared@Compat@Windows@@A; this
0x180042c6b  mov     edi, eax
0x180042c6d  setnz   bl
0x180042c70  mov     dl, bl; bool
0x180042c72  call    ?InitializeCoreProvider@TelemetryProvider@Telemetry@Shared@Compat@Windows@@IEAAX_N@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(bool)
0x180042c77  mov     edx, 0E6Ch
0x180042c7c  mov     cs:?ForcedOptIn@AppraiserSettings@Appraiser@Compat@Windows@@0_NA, bl; bool Windows::Compat::Appraiser::AppraiserSettings::ForcedOptIn
0x180042c82  lea     rax, aNotOptedInToTe; "Not opted in to telemetry."
0x180042c89  test    edi, edi
0x180042c8b  lea     rcx, aOptedInToTelem; "Opted in to telemetry"
0x180042c92  cmovz   rcx, rax
0x180042c96  lea     r9, aWindowsCompatA_738; "Windows::Compat::Appraiser::SetupApprai"...
0x180042c9d  mov     qword ptr [rsp+260h+var_238], rcx; int
0x180042ca2  lea     eax, [rdx+4]
0x180042ca5  cmovz   edx, eax; bool
0x180042ca8  mov     [rsp+260h+var_240], r13; char *
0x180042cad  xor     ecx, ecx; this
0x180042caf  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180042cb6  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180042cbb  lea     rdx, aUninstallallhb; "UninstallAllHBApp"
0x180042cc2  mov     [rsp+260h+var_1F0], r13b
0x180042cc7  mov     rcx, r15; String1
0x180042cca  call    wcscmp_0
0x180042ccf  lea     rdx, aRemovealldismi; "RemoveAllDismissibleHB"
0x180042cd6  mov     rcx, r15; String1
0x180042cd9  mov     edi, eax
0x180042cdb  call    wcscmp_0
0x180042ce0  mov     r12d, eax
0x180042ce3  lea     rax, [rsi+8]
0x180042ce7  mov     rcx, rax; lpCriticalSection
0x180042cea  mov     [rbp+160h+lpCriticalSection], rax
0x180042cee  call    cs:__imp_TryEnterCriticalSection
0x180042cf4  test    eax, eax
0x180042cf6  jnz     short loc_180042D10
0x180042cf8  mov     ebx, 800700AAh
0x180042cfd  lea     r15, aWindowsCompatA_738; "Windows::Compat::Appraiser::SetupApprai"...
0x180042d04  lea     r12, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180042d0b  jmp     loc_1800432FE
0x180042d10  mov     rcx, [rsi+30h]; hEvent
0x180042d14  mov     r13b, 1
0x180042d17  call    cs:__imp_ResetEvent
0x180042d1d  mov     rcx, r14; struct ConX::Compatibility::ICompatibilityHost *
0x180042d20  call    ?UpdateCorrelationVector@SetupAppraiser@Appraiser@Compat@Windows@@CAXPEAVICompatibilityHost@Compatibility@ConX@@@Z; Windows::Compat::Appraiser::SetupAppraiser::UpdateCorrelationVector(ConX::Compatibility::ICompatibilityHost *)
0x180042d25  lea     rcx, [rbp+160h+var_160]; this
0x180042d29  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180042d2e  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180042d35  lea     rcx, [rbp+160h+var_160]
0x180042d39  test    rax, rax
0x180042d3c  cmovnz  rcx, rax; this
0x180042d40  xor     edx, edx
0x180042d42  lock xadd [rcx+88h], rdx; unsigned __int64
0x180042d4b  lea     r8, [rbp+160h+var_D0]; char *
0x180042d52  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180042d57  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180042d5e  jz      short loc_180042D6C
0x180042d60  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180042d67  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180042d6c  mov     rbx, cs:qword_1802C9628
0x180042d73  mov     eax, [rbx]
0x180042d75  cmp     eax, 5
0x180042d78  jbe     loc_180042E38
0x180042d7e  mov     rcx, [rbx+18h]
0x180042d82  mov     rdx, 200000000000h
0x180042d8c  mov     rax, [rbx+10h]
0x180042d90  test    rdx, rax
0x180042d93  jz      loc_180042E38
0x180042d99  mov     rax, rcx
0x180042d9c  and     rax, rdx
0x180042d9f  cmp     rax, rcx
0x180042da2  jnz     loc_180042E38
0x180042da8  lea     rax, [rbp+160h+var_D0]
0x180042daf  mov     [rbp+160h+var_198], 1000000h
0x180042db7  mov     [rbp+160h+var_1A0], rax
0x180042dbb  mov     rcx, r14
0x180042dbe  mov     rax, [r14]
0x180042dc1  mov     rax, [rax]
0x180042dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042dc9  mov     word ptr [rsp+260h+var_1E8], ax
0x180042dce  lea     rcx, [rbp+160h+SystemTime]; lpSystemTime
0x180042dd2  lea     rax, szValueBuf
0x180042dd9  xorps   xmm0, xmm0
0x180042ddc  mov     [rbp+160h+var_190], rax
0x180042de0  movups  xmmword ptr [rbp+160h+SystemTime.wYear], xmm0
0x180042de4  call    cs:__imp_GetSystemTime
0x180042dea  movaps  xmm0, xmmword ptr [rbp+160h+SystemTime.wYear]
0x180042dee  lea     rax, [rbp+160h+var_180]
0x180042df2  mov     [rbp+160h+var_1E0], rax
0x180042df6  lea     rdx, unk_18029DCBA
0x180042dfd  lea     rax, [rbp+160h+var_1A0]
0x180042e01  movdqa  xmmword ptr [rbp+160h+var_180.wYear], xmm0
0x180042e06  mov     [rsp+260h+var_220], rax
0x180042e0b  mov     rcx, rbx
0x180042e0e  lea     rax, [rbp+160h+var_198]
0x180042e12  mov     [rsp+260h+var_228], rax
0x180042e17  lea     rax, [rsp+260h+var_1E8]
0x180042e1c  mov     [rsp+260h+var_230], rax
0x180042e21  lea     rax, [rbp+160h+var_190]
0x180042e25  mov     qword ptr [rsp+260h+var_238], rax
0x180042e2a  lea     rax, [rbp+160h+var_1E0]
0x180042e2e  mov     [rsp+260h+var_240], rax
0x180042e33  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x180042e38  lea     rcx, [rbp+160h+var_160]; this
0x180042e3c  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180042e41  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180042e48  lea     rcx, [rbp+160h+var_160]
0x180042e4c  test    rax, rax
0x180042e4f  cmovnz  rcx, rax; this
0x180042e53  xor     edx, edx
0x180042e55  lock xadd [rcx+88h], rdx; unsigned __int64
0x180042e5e  lea     r8, [rbp+160h+var_D0]; char *
0x180042e65  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180042e6a  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180042e71  jz      short loc_180042E7F
0x180042e73  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180042e7a  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180042e7f  mov     rbx, cs:qword_1802C9628
0x180042e86  mov     eax, [rbx]
0x180042e88  cmp     eax, 5
0x180042e8b  jbe     loc_180042F3D
0x180042e91  mov     rcx, [rbx+18h]
0x180042e95  mov     rdx, 200000000002h
0x180042e9f  mov     rax, [rbx+10h]
0x180042ea3  test    rdx, rax
0x180042ea6  jz      loc_180042F3D
0x180042eac  mov     rax, rcx
0x180042eaf  and     rax, rdx
0x180042eb2  cmp     rax, rcx
0x180042eb5  jnz     loc_180042F3D
0x180042ebb  lea     rax, [rbp+160h+var_D0]
0x180042ec2  mov     [rbp+160h+var_190], 1000000h
0x180042eca  mov     [rbp+160h+var_1E0], rax
0x180042ece  lea     rcx, [rbp+160h+SystemTime]; lpSystemTime
0x180042ed2  lea     rax, szValueBuf
0x180042ed9  mov     [rbp+160h+var_198], r15
0x180042edd  xorps   xmm0, xmm0
0x180042ee0  mov     [rbp+160h+var_1A0], rax
0x180042ee4  movups  xmmword ptr [rbp+160h+SystemTime.wYear], xmm0
0x180042ee8  call    cs:__imp_GetSystemTime
0x180042eee  movaps  xmm0, xmmword ptr [rbp+160h+SystemTime.wYear]
0x180042ef2  lea     rax, [rbp+160h+var_180]
0x180042ef6  mov     [rsp+260h+var_1E8], rax
0x180042efb  lea     rdx, unk_18029DC0B
0x180042f02  lea     rax, [rbp+160h+var_1E0]
0x180042f06  movdqa  xmmword ptr [rbp+160h+var_180.wYear], xmm0
0x180042f0b  mov     [rsp+260h+var_220], rax
0x180042f10  mov     rcx, rbx
0x180042f13  lea     rax, [rbp+160h+var_190]
0x180042f17  mov     [rsp+260h+var_228], rax
0x180042f1c  lea     rax, [rbp+160h+var_198]
0x180042f20  mov     [rsp+260h+var_230], rax
0x180042f25  lea     rax, [rbp+160h+var_1A0]
0x180042f29  mov     qword ptr [rsp+260h+var_238], rax
0x180042f2e  lea     rax, [rsp+260h+var_1E8]
0x180042f33  mov     [rsp+260h+var_240], rax
0x180042f38  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x180042f3d  lea     rax, aResolveCalledF; "Resolve called for %ls"
0x180042f44  mov     [rsp+260h+var_230], r15; char *
0x180042f49  mov     qword ptr [rsp+260h+var_238], rax; int
0x180042f4e  lea     r9, aWindowsCompatA_738; "Windows::Compat::Appraiser::SetupApprai"...
0x180042f55  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180042f5c  mov     [rsp+260h+var_240], 0; char *
0x180042f65  mov     edx, 0E85h; bool
0x180042f6a  xor     ecx, ecx; this
0x180042f6c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180042f71  lea     rcx, [rsi+98h]; this
0x180042f78  mov     rdx, r14; struct ConX::Compatibility::ICompatibilityHost *
0x180042f7b  call    ?Read@PersistedData@Appraiser@Compat@Windows@@QEAAJPEAVICompatibilityHost@Compatibility@ConX@@@Z; Windows::Compat::Appraiser::PersistedData::Read(ConX::Compatibility::ICompatibilityHost *)
0x180042f80  mov     ebx, eax
0x180042f82  test    eax, eax
0x180042f84  jns     short loc_180042FC2
0x180042f86  lea     r9, aErrorReadingSt; "Error reading stored data: [0x%x]."
0x180042f8d  mov     edx, 0E8Dh; bool
0x180042f92  lea     r15, aWindowsCompatA_738; "Windows::Compat::Appraiser::SetupApprai"...
0x180042f99  lea     r12, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180042fa0  mov     dword ptr [rsp+260h+var_230], ebx; char *
0x180042fa4  mov     r8, r12; unsigned int
0x180042fa7  mov     qword ptr [rsp+260h+var_238], r9; int
0x180042fac  mov     ecx, 1; this
0x180042fb1  mov     r9, r15; char *
0x180042fb4  mov     dword ptr [rsp+260h+var_240], ebx; char *
0x180042fb8  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180042fbd  jmp     loc_1800432FE
0x180042fc2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180042fc8  test    r13b, al
0x180042fcb  jz      short loc_180042FF0
0x180042fcd  lea     r9, aErrorReadingSt; "Error reading stored data: [0x%x]."
0x180042fd4  mov     dword ptr [rsp+260h+var_240], ebx
0x180042fd8  lea     r8, aWindowsCompatA_738; "Windows::Compat::Appraiser::SetupApprai"...
0x180042fdf  mov     ecx, 0E8Dh; unsigned int
0x180042fe4  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180042feb  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180042ff0  mov     rcx, rsi; this
0x180042ff3  mov     [rsp+260h+var_1F0], r13b
0x180042ff8  call    ?UpdateSyncId@SetupAppraiser@Appraiser@Compat@Windows@@AEAAXXZ; Windows::Compat::Appraiser::SetupAppraiser::UpdateSyncId(void)
0x180042ffd  lea     rcx, [rbp+160h+var_160]; this
0x180043001  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180043006  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18004300d  lea     rcx, [rbp+160h+var_160]
0x180043011  test    rax, rax
0x180043014  cmovnz  rcx, rax; this
0x180043018  xor     edx, edx
0x18004301a  lock xadd [rcx+88h], rdx; unsigned __int64
0x180043023  lea     r8, [rbp+160h+var_D0]; char *
0x18004302a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18004302f  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180043036  jz      short loc_180043044
0x180043038  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18004303f  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180043044  mov     rbx, cs:qword_1802C9560
0x18004304b  mov     eax, [rbx]
0x18004304d  cmp     eax, 5
0x180043050  jbe     loc_180043177
0x180043056  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18004305a  mov     rdx, 800000000000h; unsigned __int64
0x180043064  mov     rax, [rbx+10h]
0x180043068  test    rdx, rax
0x18004306b  jz      loc_180043177
0x180043071  mov     rax, rcx
0x180043074  and     rax, rdx
0x180043077  cmp     rax, rcx
0x18004307a  jnz     loc_180043177
0x180043080  lea     rax, [rbp+160h+var_D0]
0x180043087  mov     [rbp+160h+var_190], 1000000h
0x18004308f  mov     [rbp+160h+var_1E0], rax
0x180043093  lea     rax, aResolve; "Resolve"
0x18004309a  mov     [rbp+160h+var_198], rax
0x18004309e  lea     rax, aSetup_1; "Setup"
0x1800430a5  mov     [rbp+160h+var_1A0], rax
0x1800430a9  xor     eax, eax
0x1800430ab  cmp     ax, word ptr cs:?AppraiserProcessExeBuffer@WicaFactory@Appraiser@Compat@Windows@@0PAGA; ushort near * Windows::Compat::Appraiser::WicaFactory::AppraiserProcessExeBuffer
0x1800430b2  jnz     short loc_1800430B9
0x1800430b4  call    ?GetAppraiserProcessExe@Utilities@Appraiser@Compat@Windows@@SAXPEAG_K@Z; Windows::Compat::Appraiser::Utilities::GetAppraiserProcessExe(ushort *,unsigned __int64)
0x1800430b9  lea     rax, ?AppraiserProcessExeBuffer@WicaFactory@Appraiser@Compat@Windows@@0PAGA; ushort near * Windows::Compat::Appraiser::WicaFactory::AppraiserProcessExeBuffer
0x1800430c0  mov     [rsp+260h+var_1E8], rax
0x1800430c5  xor     eax, eax
0x1800430c7  cmp     ax, word ptr cs:?AppraiserBranchBuffer@WicaFactory@Appraiser@Compat@Windows@@0PAGA; ushort near * Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer
0x1800430ce  jnz     short loc_1800430D5
0x1800430d0  call    ?GetAppraiserBranch@Utilities@Appraiser@Compat@Windows@@SAXPEAG_K@Z; Windows::Compat::Appraiser::Utilities::GetAppraiserBranch(ushort *,unsigned __int64)
0x1800430d5  lea     rax, ?AppraiserBranchBuffer@WicaFactory@Appraiser@Compat@Windows@@0PAGA; ushort near * Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer
0x1800430dc  mov     [rbp+160h+var_1D8], rax
0x1800430e0  call    ?AppraiserVersion@WicaFactory@Appraiser@Compat@Windows@@SAPEBGXZ; Windows::Compat::Appraiser::WicaFactory::AppraiserVersion(void)
0x1800430e5  mov     [rbp+160h+var_1D0], rax
0x1800430e9  lea     rcx, [rbp+160h+var_180]; lpSystemTime
0x1800430ed  lea     rax, szValueBuf
0x1800430f4  xorps   xmm0, xmm0
0x1800430f7  mov     qword ptr [rbp+160h+var_1C8], rax
0x1800430fb  movups  xmmword ptr [rbp+160h+var_180.wYear], xmm0
0x1800430ff  call    cs:__imp_GetSystemTime
0x180043105  movaps  xmm0, xmmword ptr [rbp+160h+var_180.wYear]
0x180043109  lea     rax, [rbp+160h+var_170]
0x18004310d  mov     qword ptr [rbp+160h+SystemTime.wYear], rax
0x180043111  lea     rdx, unk_18029DB7F
0x180043118  lea     rax, [rbp+160h+var_1E0]
0x18004311c  movdqa  [rbp+160h+var_170], xmm0
0x180043121  mov     [rsp+260h+var_200], rax
0x180043126  mov     rcx, rbx
0x180043129  lea     rax, [rbp+160h+var_190]
0x18004312d  mov     [rsp+260h+var_208], rax
0x180043132  lea     rax, [rbp+160h+var_198]
0x180043136  mov     [rsp+260h+var_210], rax
0x18004313b  lea     rax, [rbp+160h+var_1A0]
0x18004313f  mov     [rsp+260h+var_218], rax
0x180043144  lea     rax, [rsp+260h+var_1E8]
0x180043149  mov     [rsp+260h+var_220], rax
0x18004314e  lea     rax, [rbp+160h+var_1D8]
0x180043152  mov     [rsp+260h+var_228], rax
0x180043157  lea     rax, [rbp+160h+var_1D0]
0x18004315b  mov     [rsp+260h+var_230], rax
0x180043160  lea     rax, [rbp+160h+var_1C8]
0x180043164  mov     qword ptr [rsp+260h+var_238], rax
0x180043169  lea     rax, [rbp+160h+SystemTime]
0x18004316d  mov     [rsp+260h+var_240], rax
0x180043172  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@44444AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x180043177  mov     rcx, rsi; this
0x18004317a  test    edi, edi
0x18004317c  jnz     short loc_1800431C8
0x18004317e  call    ?ResolveAllUninstalls@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJXZ; Windows::Compat::Appraiser::SetupAppraiser::ResolveAllUninstalls(void)
  ... truncated ...
```
