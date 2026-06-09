# Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint(ushort const *,ulong,ulong,ulong,ulong,bool)

- ea: `0x18009d6e0`
- end: `0x18009e9d8`
- name: `?GetSettingsFromEndpoint@AppraiserSettings@Appraiser@Compat@Windows@@CAJPEBGKKKK_N@Z`
- size: `4856`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, bool)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18009edb8`

## callees

- `0x18000147c`
- `0x180008570`
- `0x1800092dc`
- `0x180011d94`
- `0x180013c7c`
- `0x180014be8`
- `0x1800151f4`
- `0x18001a2f4`
- `0x18001a558`
- `0x180026fd0`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180076ddc`
- `0x180077918`
- `0x18008b878`
- `0x18008ef0c`
- `0x180094a04`
- `0x18009b808`
- `0x18009b8e0`
- `0x18009bb34`
- `0x18009bd30`
- `0x18009cf6c`
- `0x18009d3c8`
- `0x18009d450`
- `0x18009d5fc`
- `0x18009d6e0`
- `0x1800a20bc`
- `0x1800a3e20`
- `0x1802174cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18009e5bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18009e5bc`
- `KERNEL32!InitOnceExecuteOnce` at `0x18009d7cb`
- `KERNEL32!InitOnceExecuteOnce` at `0x18009d7cb`
- `KERNEL32!Sleep` at `0x18009dd5e`
- `KERNEL32!Sleep` at `0x18009e179`
- `KERNEL32!Sleep` at `0x18009dd5e`
- `KERNEL32!Sleep` at `0x18009e179`
- `KERNEL32!GetSystemTime` at `0x18009d91e`
- `KERNEL32!GetSystemTime` at `0x18009db9e`
- `KERNEL32!GetSystemTime` at `0x18009df76`
- `KERNEL32!GetSystemTime` at `0x18009e4f0`
- `KERNEL32!GetSystemTime` at `0x18009e833`
- `KERNEL32!GetSystemTime` at `0x18009d91e`
- `KERNEL32!GetSystemTime` at `0x18009db9e`
- `KERNEL32!GetSystemTime` at `0x18009df76`
- `KERNEL32!GetSystemTime` at `0x18009e4f0`
- `KERNEL32!GetSystemTime` at `0x18009e833`
- `OLE32!CoUninitialize` at `0x18009e989`
- `OLE32!CoUninitialize` at `0x18009e989`
- `OLE32!CoInitializeEx` at `0x18009dc35`
- `OLE32!CoInitializeEx` at `0x18009dc35`

## string_xrefs

- `0x18009d839`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009d8f5`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009d9a8`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009da6b`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009dac3`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009db75`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009dc83`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009de3e`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009de9c`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009df4d`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e085`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e0fe`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e2de`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e365`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e415`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e4c7`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e5fc`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e75d`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e8b7`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e951`: `onecore\base\appcompat\appraiser\helpers\appraisersettings.cpp`
- `0x18009e385`: `ALTERNATEDATALINK`
- `0x18009e59a`: `WRITEEXPIREDAV`
- `0x18009e6db`: `SETUPALTERNATEDATALINK`
- `0x18009e8df`: `MAXIMUMTHREADCOUNT`
- `0x18009d7f5`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009d832`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009d8ea`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009da46`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009da94`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009de37`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009de71`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009e15e`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009e1c1`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009e281`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009e321`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009e962`: `Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint`
- `0x18009d7d1`: `settings-win.data.microsoft.com`
- `0x18009dde8`: `Authorization: MsaToken `
- `0x18009de64`: `Failed to retrieve Appraiser OneSettings DeviceTicket on attempt %Iu [0x%x]`
- `0x18009e151`: `%ls - Trying to query OneSettings for Appraiser, attempt %Iu.`
- `0x18009e314`: `%ls - Querying OneSettings for Appraiser succeeded on attempt %Iu`
- `0x18009e1f1`: `%ls - Failed to Query OneSettings for Appraiser on attempt %Iu [0x%x].`
- `0x18009e274`: `%ls - Failed to Query OneSettings for Appraiser on attempt %Iu [0x%x].`
- `0x18009e402`: `Failed to copy string setting, swallowing: [0x%x].`
- `0x18009e5f2`: `Failed to copy string setting, swallowing: [0x%x].`
- `0x18009e74a`: `Failed to copy string setting, swallowing: [0x%x].`
- `0x18009e8ad`: `Failed to copy string setting, swallowing: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint(
        wchar_t *a1,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        bool a6)
{
  int v6; // r12d
  unsigned int v8; // r14d
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // r13
  bool v12; // dl
  unsigned __int16 *v13; // rcx
  int v14; // eax
  int v15; // esi
  volatile signed __int64 *v16; // rcx
  void **v17; // rdx
  int v18; // ebx
  int v19; // r8d
  int v20; // r9d
  const unsigned __int16 *v21; // rdx
  signed int DeviceTicket; // ebx
  int v23; // esi
  __int64 v24; // r15
  __int64 v25; // rax
  volatile signed __int64 *v26; // rcx
  void **v27; // rdx
  int v28; // r14d
  int v29; // r8d
  int v30; // r9d
  unsigned __int64 v31; // rdx
  HKEY v32; // r9
  HRESULT v33; // eax
  int IsMeteredConnection; // eax
  __int64 v35; // rsi
  unsigned __int16 *v36; // r12
  __int64 v37; // rdx
  __int64 v38; // r8
  __int128 *v39; // rax
  volatile signed __int64 *v40; // rcx
  int v41; // esi
  int v42; // r8d
  int v43; // r9d
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  __int64 v46; // rsi
  unsigned __int64 v47; // r14
  int v48; // eax
  wchar_t *v49; // rsi
  wchar_t *v50; // rsi
  char v51; // r12
  __int64 v52; // rsi
  __int64 v53; // r15
  __int64 v54; // rax
  unsigned __int16 *v55; // rcx
  __int64 v56; // rdx
  unsigned __int16 *v57; // r8
  unsigned __int16 v58; // r9
  unsigned __int16 *v59; // rcx
  volatile signed __int64 *v60; // rcx
  void **v61; // rdx
  int v62; // r14d
  int v63; // r8d
  int v64; // r9d
  unsigned int v65; // eax
  unsigned __int16 *v66; // rax
  unsigned __int16 *v67; // rdx
  unsigned __int16 v68; // cx
  unsigned __int16 *v69; // rcx
  volatile signed __int64 *v70; // rcx
  void **v71; // rdx
  int v72; // esi
  int v73; // r8d
  int v74; // r9d
  struct _SECURITY_ATTRIBUTES *v76; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v77; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v78; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v79; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v80; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v81; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v82; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v83; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v84; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v85; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v86; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v87; // [rsp+28h] [rbp-D8h]
  char *v88; // [rsp+30h] [rbp-D0h]
  char *v89; // [rsp+30h] [rbp-D0h]
  char *v90; // [rsp+30h] [rbp-D0h]
  char *v91; // [rsp+30h] [rbp-D0h]
  char v92; // [rsp+60h] [rbp-A0h]
  bool v93; // [rsp+61h] [rbp-9Fh] BYREF
  int v94; // [rsp+64h] [rbp-9Ch] BYREF
  char v95[4]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v96; // [rsp+70h] [rbp-90h] BYREF
  int v97; // [rsp+78h] [rbp-88h]
  int v98; // [rsp+7Ch] [rbp-84h]
  char *v99; // [rsp+80h] [rbp-80h] BYREF
  const char *v100; // [rsp+88h] [rbp-78h] BYREF
  const char *v101; // [rsp+90h] [rbp-70h] BYREF
  const char *v102; // [rsp+98h] [rbp-68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v104; // [rsp+B0h] [rbp-50h]
  wchar_t *EndPtr[3]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v106[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v107; // [rsp+F0h] [rbp-10h] BYREF
  __m128i si128; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v109[2]; // [rsp+110h] [rbp+10h] BYREF
  __m128i v110; // [rsp+120h] [rbp+20h]
  _BYTE v111[1600]; // [rsp+130h] [rbp+30h] BYREF
  char *v112; // [rsp+770h] [rbp+670h]
  _BYTE v113[16]; // [rsp+7A8h] [rbp+6A8h] BYREF
  unsigned __int64 v114; // [rsp+7B8h] [rbp+6B8h]
  unsigned __int16 v115[72]; // [rsp+880h] [rbp+780h] BYREF
  wchar_t String[16]; // [rsp+910h] [rbp+810h] BYREF
  unsigned __int16 pvData[40]; // [rsp+930h] [rbp+830h] BYREF
  wchar_t String2[264]; // [rsp+980h] [rbp+880h] BYREF
  struct _SECURITY_ATTRIBUTES v119; // [rsp+B90h] [rbp+A90h] BYREF
  unsigned __int16 v120[264]; // [rsp+DA0h] [rbp+CA0h] BYREF

  EndPtr[1] = (wchar_t *)-2LL;
  v6 = (int)a4;
  v8 = (unsigned int)a2;
  EndPtr[0] = a1;
  v107 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v107) = 0;
  *(_OWORD *)v109 = 0;
  v110 = si128;
  LOWORD(v109[0]) = 0;
  if ( Windows::Compat::Appraiser::AppraiserSettings::FeatureType )
  {
    switch ( Windows::Compat::Appraiser::AppraiserSettings::FeatureType )
    {
      case 1:
        v10 = L"setupappraiser";
        break;
      case 2:
        v10 = L"appraiseroobe";
        break;
      case 3:
        v10 = L"restoreappraiser";
        break;
      default:
        v10 = (const unsigned __int16 *)&szValueBuf;
        break;
    }
  }
  else
  {
    v10 = L"appraiser";
  }
  OneCore::Base::Telemetry::OneSettingsQuery::OneSettingsQuery(
    (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
    a2,
    v10,
    a4,
    (const unsigned __int16 *)v76);
  memset_0(a1, 0, 0x208u);
  v92 = 0;
  v93 = 0;
  v11 = 0;
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
    Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
    0,
    0);
  v13 = L"settings-win.data.microsoft.com";
  if ( Windows::Compat::Appraiser::AppraiserTestHooks::TestHookOverrideOneSettingsServer )
    v13 = Windows::Compat::Appraiser::AppraiserTestHooks::TestHookOverrideOneSettingsServer;
  v104 = v13;
  v14 = OneCore::Base::Telemetry::OneSettingsQuery::AddParameterOsVer(
          (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
          v12);
  v15 = v14;
  if ( v14 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x168u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        "Failed to add OneSetting parameter OsVer [0x%x].",
        v14);
  }
  else
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
      359,
      "Failed to add OneSetting parameter OsVer [0x%x].",
      v14);
    LODWORD(v88) = v15;
    LODWORD(v78) = v15;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      104,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
      "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
      (const char *)v78,
      (int)"Failed to add OneSetting parameter OsVer [0x%x].",
      v88);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)String2);
    v16 = (volatile signed __int64 *)String2;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v16 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v16,
      _InterlockedExchangeAdd64(v16 + 17, 0),
      (char *)v115);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v17);
    v18 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v99 = (char *)v115;
      *(_DWORD *)v95 = v15;
      v100 = "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint";
      v101 = "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp";
      v94 = 360;
      v102 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v106[0] = SystemTime;
      v96 = (unsigned __int64)v106;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v18,
        (unsigned int)&unk_1802A2588,
        v19,
        v20,
        (__int64)&v96,
        (__int64)&v102,
        (__int64)&v94,
        (__int64)&v101,
        (__int64)&v100,
        (__int64)v95,
        (__int64)&v99);
    }
  }
  LODWORD(v88) = a5;
  LODWORD(v87) = v6;
  LODWORD(v77) = a3;
  DeviceTicket = StringCchPrintfW(v115, 0x2Cu, L"%d.%d.%d.%d", v8, v77, v87, v88);
  v23 = -2147024809;
  v24 = -1;
  if ( DeviceTicket >= 0 )
  {
    v25 = -1;
    do
      ++v25;
    while ( v115[v25] );
    if ( v25 )
    {
      DeviceTicket = RtlNameValueArray::Insert((RtlNameValueArray *)v113, v21, L"appver", v115, v114);
      if ( DeviceTicket >= 0 )
      {
        DeviceTicket = 0;
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x16Cu,
            "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
            "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
            "Failed to add OneSetting parameter appVer [0x%x].",
            0);
        goto LABEL_41;
      }
    }
    else
    {
      DeviceTicket = -2147024809;
    }
  }
  AslLogCallPrintf(
    3,
    "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
    363,
    "Failed to add OneSetting parameter appVer [0x%x].",
    DeviceTicket);
  LODWORD(v89) = DeviceTicket;
  LODWORD(v80) = DeviceTicket;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    108,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
    "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
    (const char *)v80,
    (int)"Failed to add OneSetting parameter appVer [0x%x].",
    v89);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)String2);
  v26 = (volatile signed __int64 *)String2;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v26 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v26,
    _InterlockedExchangeAdd64(v26 + 17, 0),
    (char *)v115);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v27);
  v28 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v96 = (unsigned __int64)v115;
    v94 = DeviceTicket;
    v102 = "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint";
    v101 = "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp";
    *(_DWORD *)v95 = 364;
    v100 = (const char *)&szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v106[0] = SystemTime;
    v99 = (char *)v106;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v28,
      (unsigned int)&unk_1802A24C2,
      v29,
      v30,
      (__int64)&v99,
      (__int64)&v100,
      (__int64)v95,
      (__int64)&v101,
      (__int64)&v102,
      (__int64)&v94,
      (__int64)&v96);
  }
LABEL_41:
  if ( !IsWindowsVersionOrGreater(0xAu, 0, 0) )
  {
    pvData[0] = 0;
    v96 = 80;
    v44 = Windows::Compat::Shared::Registry::ReadValue(
            pvData,
            &v96,
            2u,
            v32,
            L"SOFTWARE\\Microsoft\\SQMClient",
            L"MachineId");
    DeviceTicket = 0;
    if ( v44 < 0 )
      DeviceTicket = v44;
    if ( DeviceTicket < 0 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        438,
        "Failed to retrieve Appraiser OneSettings Sqm DeviceId: [0x%x].",
        DeviceTicket);
      LODWORD(v89) = DeviceTicket;
      LODWORD(v83) = DeviceTicket;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        183,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        (const char *)v83,
        (int)"Failed to retrieve Sqm DeviceId: [0x%x].",
        v89);
      goto LABEL_147;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1B7u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        "Failed to retrieve Sqm DeviceId: [0x%x].",
        DeviceTicket);
    do
      ++v24;
    while ( pvData[v24] );
    if ( !v24 || (v23 = RtlNameValueArray::Insert((RtlNameValueArray *)v113, v45, L"deviceid", pvData, v114), v23 < 0) )
    {
      DeviceTicket = v23;
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        442,
        "Failed to add OneSettings parameter Sqm DeviceId: [0x%x].",
        v23);
      LODWORD(v89) = v23;
      LODWORD(v86) = v23;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        187,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        (const char *)v86,
        (int)"Failed to add OneSettings parameter Sqm DeviceId: [0x%x].",
        v89);
      goto LABEL_147;
    }
    DeviceTicket = 0;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1BBu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        "Failed to add OneSettings parameter Sqm DeviceId: [0x%x].",
        0);
      DeviceTicket = 0;
    }
    goto LABEL_84;
  }
  if ( Windows::Compat::Appraiser::AppraiserSettings::FeatureType != 3 )
  {
    v33 = CoInitializeEx(0, 0);
    DeviceTicket = v33;
    if ( v33 < 0 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        383,
        "Coinitialize failed for Appraiser OneSettings call: [0x%x].",
        v33);
      LODWORD(v89) = DeviceTicket;
      LODWORD(v81) = DeviceTicket;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        128,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        (const char *)v81,
        (int)"Coinitialize failed: [0x%x].",
        v89);
LABEL_147:
      v51 = 0;
LABEL_148:
      AslLogCallPrintf(
        1,
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        547,
        "Appraiser ADL Pipeline - Failed to Query OneSettings: [ApprADL:0x%x].",
        DeviceTicket);
      goto LABEL_149;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x180u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        "Coinitialize failed: [0x%x].",
        v33);
    v92 = 1;
    IsMeteredConnection = Windows::Compat::Appraiser::Utilities::IsMeteredConnection(&v93);
    DeviceTicket = IsMeteredConnection;
    if ( v93 )
    {
      if ( IsMeteredConnection >= 0 )
      {
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
          394,
          "Running on a metered connection for Appraiser OneSettings call.");
        Windows::Compat::Appraiser::WriteLog(
          0,
          139,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
          "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
          0,
          (int)"Running on a metered connection.",
          v89);
      }
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        397,
        "DeviceTicket not included for Appraiser OneSettings call.");
      Windows::Compat::Appraiser::WriteLog(
        0,
        142,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        0,
        (int)"DeviceTicket not included.",
        v89);
LABEL_84:
      v36 = v104;
      goto LABEL_85;
    }
  }
  v35 = 0;
  v36 = v104;
  if ( Windows::Compat::Appraiser::AppraiserSettings::OnesettingsQueryTries )
  {
    while ( 1 )
    {
      if ( v35 )
        Sleep(0x1388u);
      v96 = 0x435E9442A3D87918LL;
      v97 = 396067475;
      v98 = -1261805047;
      DeviceTicket = OneCore::Base::Telemetry::DeviceTicket::GetDeviceTicket(&v107, v36, &v96);
      if ( DeviceTicket >= 0 )
        break;
      if ( ++v35 >= Windows::Compat::Appraiser::AppraiserSettings::OnesettingsQueryTries )
        goto LABEL_65;
    }
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - si128.m128i_i64[0]) < 0x18 )
      std::_Xlen_string();
    v39 = &v107;
    if ( si128.m128i_i64[1] > 7uLL )
      v39 = (__int128 *)v107;
    std::wstring::wstring(v106, v37, v38, L"Authorization: MsaToken ", 24, v39, si128.m128i_i64[0]);
    std::wstring::operator=(v109, v106);
    std::wstring::~wstring(v106);
    v11 = (const unsigned __int16 *)v109;
    if ( v110.m128i_i64[1] > 7uLL )
      v11 = v109[0];
  }
  else
  {
    v11 = 0;
    if ( DeviceTicket < 0 )
    {
LABEL_65:
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        431,
        "Failed to retrieve Appraiser OneSettings DeviceTicket on attempt %Iu [0x%x]",
        v35,
        DeviceTicket);
      LODWORD(v89) = DeviceTicket;
      LODWORD(v82) = DeviceTicket;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        176,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        (const char *)v82,
        (int)"Failed to retrieve DeviceTicket: [0x%x]",
        v89);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)String2);
      v40 = (volatile signed __int64 *)String2;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v40 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v40,
        _InterlockedExchangeAdd64(v40 + 17, 0),
        (char *)v115);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, (void **)v31);
      v41 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u )
      {
        v31 = 0x200000000000LL;
        if ( (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v96 = (unsigned __int64)v115;
          v94 = DeviceTicket;
          v102 = "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint";
          v101 = "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp";
          *(_DWORD *)v95 = 432;
          v100 = (const char *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v106[0] = SystemTime;
          v99 = (char *)v106;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v41,
            (unsigned int)&unk_1802A2525,
            v42,
            v43,
            (__int64)&v99,
            (__int64)&v100,
            (__int64)v95,
            (__int64)&v101,
            (__int64)&v102,
            (__int64)&v94,
            (__int64)&v96);
        }
      }
      goto LABEL_85;
    }
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1B0u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
      "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
      "Failed to retrieve DeviceTicket: [0x%x]",
      DeviceTicket);
LABEL_85:
  v46 = 0;
  if ( Windows::Compat::Appraiser::AppraiserSettings::OnesettingsQueryTries )
  {
    while ( 1 )
    {
      Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601((unsigned __int16 *)&v119, v31);
      v47 = v46 + 1;
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        453,
        "%ls - Trying to query OneSettings for Appraiser, attempt %Iu.",
        (const wchar_t *)&v119,
        v46 + 1);
      if ( v46 )
        Sleep(0x1388u);
      v48 = OneCore::Base::Telemetry::OneSettingsQuery::Query(
              (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
              v36,
              a6,
              v11,
              v84);
      DeviceTicket = v48;
      if ( v48 >= 0 )
        break;
      if ( !a6 && (unsigned int)(v48 + 2147024894) <= 1 )
      {
        Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601((unsigned __int16 *)&v119, v31);
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
          476,
          "%ls - Failed to Query OneSettings for Appraiser on attempt %Iu [0x%x].",
          (const wchar_t *)&v119,
          v46 + 1,
          DeviceTicket);
        v50 = EndPtr[0];
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
          477,
          "%ls.",
          EndPtr[0]);
        LODWORD(v91) = DeviceTicket;
        Windows::Compat::Appraiser::WriteLog(
          0,
          225,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
          "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
          0,
          (int)"Failed to Query OneSettings [0x%x] :: (%ls)",
          v91,
          v50);
        goto LABEL_95;
      }
      ++v46;
      if ( v47 >= Windows::Compat::Appraiser::AppraiserSettings::OnesettingsQueryTries )
        goto LABEL_92;
    }
    Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601((unsigned __int16 *)&v119, v31);
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
      469,
      "%ls - Querying OneSettings for Appraiser succeeded on attempt %Iu",
      (const wchar_t *)&v119,
      v46 + 1);
  }
LABEL_92:
  Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601((unsigned __int16 *)&v119, v31);
  if ( DeviceTicket < 0 )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
      489,
      "%ls - Failed to Query OneSettings for Appraiser on attempt %Iu [0x%x].",
      (const wchar_t *)&v119,
      v46,
      DeviceTicket);
    v49 = EndPtr[0];
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
      490,
      "%ls.",
      EndPtr[0]);
    LODWORD(v90) = DeviceTicket;
    LODWORD(v85) = DeviceTicket;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      239,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
      "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
      (const char *)v85,
      (int)"Failed to Query OneSettings [0x%x] :: (%ls)",
      v90,
      v49);
LABEL_95:
    v51 = v92;
    goto LABEL_148;
  }
  v51 = v92;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1EFu,
      "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
      "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
      "Failed to Query OneSettings [0x%x] :: (%ls)",
      DeviceTicket,
      EndPtr[0]);
  v52 = 260;
  v53 = 2147483646;
  if ( !OneCore::Base::Telemetry::OneSettingsQuery::GetSetting(
          (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
          L"ALTERNATEDATALINK",
          v120,
          0x104u) )
  {
    v54 = 2147483646;
    v55 = v120;
    v56 = 260;
    v57 = &Windows::Compat::Appraiser::AppraiserSettings::SettingAlternateDataLink;
    do
    {
      if ( !v54 )
        break;
      v58 = *v55;
      if ( !*v55 )
        break;
      ++v55;
      *v57++ = v58;
      --v54;
      --v56;
    }
    while ( v56 );
    DeviceTicket = v56 == 0 ? 0x8007007A : 0;
    v59 = v57 - 1;
    if ( v56 )
      v59 = v57;
    *v59 = 0;
    if ( v56 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x1FAu,
          "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
          "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
          "Failed to copy string setting, swallowing: [0x%x].",
          v56 == 0 ? 0x8007007A : 0);
    }
    else
    {
      LODWORD(v89) = -2147024774;
      LODWORD(v79) = -2147024774;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        250,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        (const char *)v79,
        (int)"Failed to copy string setting, swallowing: [0x%x].",
        v89);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)String2);
      v60 = (volatile signed __int64 *)String2;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v60 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v60,
        _InterlockedExchangeAdd64(v60 + 17, 0),
        (char *)v115);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v61);
      v62 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v96 = (unsigned __int64)v115;
        v94 = DeviceTicket;
        v102 = "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint";
        v101 = "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp";
        *(_DWORD *)v95 = 506;
        v100 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v106[0] = SystemTime;
        v99 = (char *)v106;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v62,
          (unsigned int)&unk_1802A245F,
          v63,
          v64,
          (__int64)&v99,
          (__int64)&v100,
          (__int64)v95,
          (__int64)&v101,
          (__int64)&v102,
          (__int64)&v94,
          (__int64)&v96);
      }
    }
  }
  OneCore::Base::Telemetry::OneSettingsQuery::GetOptionalSettingDword(
    (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
    &Windows::Compat::Appraiser::AppraiserSettings::SettingDataVersionMinimum,
    L"MINDATAVERSION");
  OneCore::Base::Telemetry::OneSettingsQuery::GetOptionalSettingDword(
    (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
    &Windows::Compat::Appraiser::AppraiserSettings::SettingAppraiserVersionMinimum,
    L"MINVERSION");
  EndPtr[0] = 0;
  if ( !OneCore::Base::Telemetry::OneSettingsQuery::GetSetting(
          (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
          L"WRITEEXPIREDAV",
          String,
          0x10u) )
  {
    v65 = wcstoul(String, EndPtr, 0);
    if ( v65 )
    {
      LOBYTE(Windows::Compat::Appraiser::AppraiserSettings::SettingShouldWriteInferredExpiredAv) = 1;
      if ( v65 == 1 )
        goto LABEL_124;
    }
    else if ( *EndPtr[0] || String == EndPtr[0] )
    {
      goto LABEL_124;
    }
    LOBYTE(Windows::Compat::Appraiser::AppraiserSettings::SettingShouldWriteInferredExpiredAv) = 0;
  }
LABEL_124:
  OneCore::Base::Telemetry::OneSettingsQuery::GetOptionalSettingDword(
    (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
    (unsigned int *)&Windows::Compat::Appraiser::AppraiserSettings::SettingMinimumChecksToInferExpired,
    L"MINEXPIREDCHECKS");
  OneCore::Base::Telemetry::OneSettingsQuery::GetOptionalSettingDword(
    (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
    &Windows::Compat::Appraiser::AppraiserSettings::SettingAlternateDataVersion,
    L"ALTERNATEDATAVERSION");
  if ( !OneCore::Base::Telemetry::OneSettingsQuery::GetSetting(
          (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
          L"FORCESYNC",
          String2,
          0x104u) )
    Windows::Compat::Appraiser::AppraiserSettings::SettingForceSync = wcscmp_0(L"TRUE", String2) == 0;
  OneCore::Base::Telemetry::OneSettingsQuery::GetOptionalSettingMap(
    (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
    (struct RtlNameValueArray *)&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupProperties,
    L"SETUP_");
  OneCore::Base::Telemetry::OneSettingsQuery::GetOptionalSettingMap(
    (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
    (struct RtlNameValueArray *)&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAdditionalInitProperties,
    L"SETUPINIT_");
  OneCore::Base::Telemetry::OneSettingsQuery::GetOptionalSettingMap(
    (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
    (struct RtlNameValueArray *)&Windows::Compat::Appraiser::AppraiserSettings::SettingTelemetryAdditionalInitProperties,
    L"TEL_");
  if ( !OneCore::Base::Telemetry::OneSettingsQuery::GetSetting(
          (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
          L"SETUPALTERNATEDATALINK",
          v120,
          0x104u) )
  {
    v66 = v120;
    v67 = &Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAlternateDataLink;
    do
    {
      if ( !v53 )
        break;
      v68 = *v66;
      if ( !*v66 )
        break;
      ++v66;
      *v67++ = v68;
      --v53;
      --v52;
    }
    while ( v52 );
    DeviceTicket = v52 == 0 ? 0x8007007A : 0;
    v69 = v67 - 1;
    if ( v52 )
      v69 = v67;
    *v69 = 0;
    if ( v52 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x215u,
          "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
          "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
          "Failed to copy string setting, swallowing: [0x%x].",
          v52 == 0 ? 0x8007007A : 0);
    }
    else
    {
      LODWORD(v89) = -2147024774;
      LODWORD(v79) = -2147024774;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        21,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp",
        "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint",
        (const char *)v79,
        (int)"Failed to copy string setting, swallowing: [0x%x].",
        v89);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)String2);
      v70 = (volatile signed __int64 *)String2;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v70 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v70,
        _InterlockedExchangeAdd64(v70 + 17, 0),
        (char *)v115);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v71);
      v72 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v96 = (unsigned __int64)v115;
        v94 = DeviceTicket;
        v102 = "Windows::Compat::Appraiser::AppraiserSettings::GetSettingsFromEndpoint";
        v101 = "onecore\\base\\appcompat\\appraiser\\helpers\\appraisersettings.cpp";
        *(_DWORD *)v95 = 533;
        v100 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v106[0] = SystemTime;
        v99 = (char *)v106;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v72,
          (unsigned int)&unk_1802A23FC,
          v73,
          v74,
          (__int64)&v99,
          (__int64)&v100,
          (__int64)v95,
          (__int64)&v101,
          (__int64)&v102,
          (__int64)&v94,
          (__int64)&v96);
      }
    }
  }
  OneCore::Base::Telemetry::OneSettingsQuery::GetOptionalSettingDword(
    (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
    &Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAlternateDataVersion,
    L"SETUPALTERNATEDATAVERSION");
  OneCore::Base::Telemetry::OneSettingsQuery::GetOptionalSettingDword(
    (OneCore::Base::Telemetry::OneSettingsQuery *)v111,
    &Windows::Compat::Appraiser::AppraiserSettings::SettingMaximumThreadCount,
    L"MAXIMUMTHREADCOUNT");
  Windows::Compat::Appraiser::AppraiserSettings::SettingOneSettingsFresh = OneCore::Base::Telemetry::OneSettingsQuery::SettingsFresh((OneCore::Base::Telemetry::OneSettingsQuery *)v111);
  Windows::Compat::Appraiser::AppraiserSettings::SettingOneSettingsFreshnessTimestamp = v112;
  if ( DeviceTicket < 0 )
    goto LABEL_148;
LABEL_149:
  if ( v51 )
    CoUninitialize();
  OneCore::Base::Telemetry::OneSettingsQuery::~OneSettingsQuery((OneCore::Base::Telemetry::OneSettingsQuery *)v111);
  std::wstring::~wstring(v109);
  std::wstring::~wstring(&v107);
  return (unsigned int)DeviceTicket;
}

```

## disassembly

```asm
0x18009d6e0  push    rbp
0x18009d6e2  push    rbx
0x18009d6e3  push    rsi
0x18009d6e4  push    rdi
0x18009d6e5  push    r12
0x18009d6e7  push    r13
0x18009d6e9  push    r14
0x18009d6eb  push    r15
0x18009d6ed  lea     rbp, [rsp-0EC8h]
0x18009d6f5  sub     rsp, 0FC8h
0x18009d6fc  mov     [rbp+0F00h+var_F40], 0FFFFFFFFFFFFFFFEh
0x18009d704  mov     rax, cs:__security_cookie
0x18009d70b  xor     rax, rsp
0x18009d70e  mov     [rbp+0F00h+var_50], rax
0x18009d715  mov     r12d, r9d
0x18009d718  mov     r15d, r8d
0x18009d71b  mov     r14d, edx
0x18009d71e  mov     rbx, rcx
0x18009d721  mov     [rbp+0F00h+EndPtr], rcx
0x18009d725  xor     edi, edi
0x18009d727  xorps   xmm0, xmm0
0x18009d72a  movups  [rbp+0F00h+var_F10], xmm0
0x18009d72e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18009d736  movdqu  [rbp+0F00h+var_F00], xmm1
0x18009d73b  mov     word ptr [rbp+0F00h+var_F10], di
0x18009d73f  movups  xmmword ptr [rbp+0F00h+var_EF0], xmm0
0x18009d743  movdqu  [rbp+0F00h+var_EE0], xmm1
0x18009d748  mov     word ptr [rbp+0F00h+var_EF0], di
0x18009d74c  mov     ecx, cs:?FeatureType@AppraiserSettings@Appraiser@Compat@Windows@@0W4OnesettingsFeatureType@1234@A; Windows::Compat::Appraiser::AppraiserSettings::OnesettingsFeatureType Windows::Compat::Appraiser::AppraiserSettings::FeatureType
0x18009d752  test    ecx, ecx
0x18009d754  jz      short loc_18009D789
0x18009d756  sub     ecx, 1
0x18009d759  jz      short loc_18009D780
0x18009d75b  sub     ecx, 1
0x18009d75e  jz      short loc_18009D777
0x18009d760  cmp     ecx, 1
0x18009d763  jz      short loc_18009D76E
0x18009d765  lea     r8, szValueBuf
0x18009d76c  jmp     short loc_18009D790
0x18009d76e  lea     r8, aRestoreapprais_1; "restoreappraiser"
0x18009d775  jmp     short loc_18009D790
0x18009d777  lea     r8, aAppraiseroobe; "appraiseroobe"
0x18009d77e  jmp     short loc_18009D790
0x18009d780  lea     r8, aSetupappraiser; "setupappraiser"
0x18009d787  jmp     short loc_18009D790
0x18009d789  lea     r8, aAppraiser_1; "appraiser"
0x18009d790  lea     rcx, [rbp+0F00h+var_ED0]; this
0x18009d794  call    ??0OneSettingsQuery@Telemetry@Base@OneCore@@QEAA@PEBG000@Z; OneCore::Base::Telemetry::OneSettingsQuery::OneSettingsQuery(ushort const *,ushort const *,ushort const *,ushort const *)
0x18009d799  nop
0x18009d79a  xor     edx, edx; Val
0x18009d79c  mov     r8d, 208h; Size
0x18009d7a2  mov     rcx, rbx; void *
0x18009d7a5  call    memset_0
0x18009d7aa  mov     [rsp+1000h+var_FA0], dil
0x18009d7af  mov     [rsp+1000h+var_F9F], dil
0x18009d7b4  mov     r13, rdi
0x18009d7b7  xor     r9d, r9d; Context
0x18009d7ba  xor     r8d, r8d; Parameter
0x18009d7bd  lea     rdx, ?InitOnceCallback@AppraiserTestHooks@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18009d7c4  lea     rcx, ?InitOnce@AppraiserTestHooks@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x18009d7cb  call    cs:__imp_InitOnceExecuteOnce
0x18009d7d1  lea     rcx, aSettingsWinDat; "settings-win.data.microsoft.com"
0x18009d7d8  mov     rax, cs:?TestHookOverrideOneSettingsServer@AppraiserTestHooks@Appraiser@Compat@Windows@@0PEBGEB; ushort const * const Windows::Compat::Appraiser::AppraiserTestHooks::TestHookOverrideOneSettingsServer
0x18009d7df  test    rax, rax
0x18009d7e2  cmovnz  rcx, rax
0x18009d7e6  mov     [rbp+0F00h+var_F50], rcx
0x18009d7ea  lea     rcx, [rbp+0F00h+var_ED0]; this
0x18009d7ee  call    ?AddParameterOsVer@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJ_N@Z; OneCore::Base::Telemetry::OneSettingsQuery::AddParameterOsVer(bool)
0x18009d7f3  mov     esi, eax
0x18009d7f5  lea     rcx, aWindowsCompatA_517; "Windows::Compat::Appraiser::AppraiserSe"...
0x18009d7fc  test    eax, eax
0x18009d7fe  jns     loc_18009D989
0x18009d804  mov     dword ptr [rsp+1000h+var_FE0], eax
0x18009d808  lea     rbx, aFailedToAddOne_0; "Failed to add OneSetting parameter OsVe"...
0x18009d80f  mov     r9, rbx
0x18009d812  mov     r8d, 167h
0x18009d818  mov     rdx, rcx
0x18009d81b  mov     ecx, 3
0x18009d820  call    AslLogCallPrintf
0x18009d825  mov     dword ptr [rsp+1000h+var_FD0], esi; char *
0x18009d829  mov     [rsp+1000h+var_FD8], rbx; int
0x18009d82e  mov     dword ptr [rsp+1000h+var_FE0], esi; char *
0x18009d832  lea     r9, aWindowsCompatA_517; "Windows::Compat::Appraiser::AppraiserSe"...
0x18009d839  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appcompat\\appraiser\\he"...
0x18009d840  mov     edx, 168h; bool
0x18009d845  mov     edi, 1
0x18009d84a  mov     ecx, edi; this
0x18009d84c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18009d851  lea     rcx, [rbp+0F00h+String2]; this
0x18009d858  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18009d85d  lea     rcx, [rbp+0F00h+String2]
0x18009d864  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18009d86b  xor     ebx, ebx
0x18009d86d  test    rax, rax
0x18009d870  cmovnz  rcx, rax; this
0x18009d874  mov     edx, ebx
0x18009d876  lock xadd [rcx+88h], rdx; unsigned __int64
0x18009d87f  lea     r8, [rbp+0F00h+var_780]; char *
0x18009d886  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18009d88b  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, bl; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18009d891  jz      short loc_18009D89F
0x18009d893  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18009d89a  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18009d89f  mov     rbx, cs:qword_1802C9628
0x18009d8a6  mov     eax, [rbx]
0x18009d8a8  cmp     eax, 5
0x18009d8ab  jbe     loc_18009D9B9
0x18009d8b1  mov     rcx, [rbx+18h]
0x18009d8b5  mov     rax, [rbx+10h]
0x18009d8b9  mov     rdx, 200000000000h
0x18009d8c3  test    rdx, rax
0x18009d8c6  jz      loc_18009D9B9
0x18009d8cc  mov     rax, rcx
0x18009d8cf  and     rax, rdx
0x18009d8d2  cmp     rax, rcx
0x18009d8d5  jnz     loc_18009D9B9
0x18009d8db  lea     rax, [rbp+0F00h+var_780]
0x18009d8e2  mov     [rbp+0F00h+var_F80], rax
0x18009d8e6  mov     dword ptr [rsp+1000h+var_F98], esi
0x18009d8ea  lea     rax, aWindowsCompatA_517; "Windows::Compat::Appraiser::AppraiserSe"...
0x18009d8f1  mov     [rbp+0F00h+var_F78], rax
0x18009d8f5  lea     rax, aOnecoreBaseApp_28; "onecore\\base\\appcompat\\appraiser\\he"...
0x18009d8fc  mov     [rbp+0F00h+var_F70], rax
0x18009d900  mov     [rsp+1000h+var_F9C], 168h
0x18009d908  lea     rax, szValueBuf
0x18009d90f  mov     [rbp+0F00h+var_F68], rax
0x18009d913  xorps   xmm0, xmm0
0x18009d916  movups  xmmword ptr [rbp+0F00h+SystemTime.wYear], xmm0
0x18009d91a  lea     rcx, [rbp+0F00h+SystemTime]; lpSystemTime
0x18009d91e  call    cs:__imp_GetSystemTime
0x18009d924  movaps  xmm0, xmmword ptr [rbp+0F00h+SystemTime.wYear]
0x18009d928  movdqa  [rbp+0F00h+var_F30], xmm0
0x18009d92d  lea     rax, [rbp+0F00h+var_F30]
0x18009d931  mov     [rsp+1000h+var_F90], rax
0x18009d936  lea     rax, [rbp+0F00h+var_F80]
0x18009d93a  mov     [rsp+1000h+var_FB0], rax
0x18009d93f  lea     rax, [rsp+1000h+var_F98]
0x18009d944  mov     [rsp+1000h+var_FB8], rax
0x18009d949  lea     rax, [rbp+0F00h+var_F78]
0x18009d94d  mov     [rsp+1000h+var_FC0], rax
0x18009d952  lea     rax, [rbp+0F00h+var_F70]
0x18009d956  mov     [rsp+1000h+var_FC8], rax
0x18009d95b  lea     rax, [rsp+1000h+var_F9C]
0x18009d960  mov     [rsp+1000h+var_FD0], rax
0x18009d965  lea     rax, [rbp+0F00h+var_F68]
0x18009d969  mov     [rsp+1000h+var_FD8], rax
0x18009d96e  lea     rax, [rsp+1000h+var_F90]
0x18009d973  mov     [rsp+1000h+var_FE0], rax
0x18009d978  lea     rdx, unk_1802A2588
0x18009d97f  mov     rcx, rbx
0x18009d982  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009d987  jmp     short loc_18009D9B9
0x18009d989  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18009d98f  mov     edi, 1
0x18009d994  and     eax, edi
0x18009d996  test    al, al
0x18009d998  jz      short loc_18009D9B9
0x18009d99a  mov     dword ptr [rsp+1000h+var_FE0], esi
0x18009d99e  lea     r9, aFailedToAddOne_0; "Failed to add OneSetting parameter OsVe"...
0x18009d9a5  mov     r8, rcx; char *
0x18009d9a8  lea     rdx, aOnecoreBaseApp_28; "onecore\\base\\appcompat\\appraiser\\he"...
0x18009d9af  mov     ecx, 168h; unsigned int
0x18009d9b4  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18009d9b9  mov     eax, [rbp+0F00h+arg_20]
0x18009d9bf  mov     dword ptr [rsp+1000h+var_FD0], eax
0x18009d9c3  mov     dword ptr [rsp+1000h+var_FD8], r12d
0x18009d9c8  mov     dword ptr [rsp+1000h+var_FE0], r15d
0x18009d9cd  mov     r9d, r14d
0x18009d9d0  lea     r8, aDDDD; "%d.%d.%d.%d"
0x18009d9d7  mov     edx, 2Ch ; ','; unsigned __int64
0x18009d9dc  lea     rcx, [rbp+0F00h+var_780]; unsigned __int16 *
0x18009d9e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009d9e8  mov     ebx, eax
0x18009d9ea  mov     esi, 80070057h
0x18009d9ef  or      r15, 0FFFFFFFFFFFFFFFFh
0x18009d9f3  xor     r14d, r14d
0x18009d9f6  test    eax, eax
0x18009d9f8  js      loc_18009DA83
0x18009d9fe  lea     rcx, [rbp+0F00h+var_780]
0x18009da05  mov     rax, r15
0x18009da08  inc     rax
0x18009da0b  cmp     [rcx+rax*2], r14w
0x18009da10  jnz     short loc_18009DA08
0x18009da12  test    rax, rax
0x18009da15  jz      short loc_18009DA81
0x18009da17  mov     rax, [rbp+0F00h+var_848]
0x18009da1e  mov     [rsp+1000h+var_FE0], rax; unsigned __int64
0x18009da23  lea     r9, [rbp+0F00h+var_780]; unsigned __int16 *
0x18009da2a  lea     r8, aAppver; "appver"
0x18009da31  lea     rcx, [rbp+0F00h+var_858]; this
0x18009da38  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18009da3d  mov     ebx, eax
0x18009da3f  test    eax, eax
0x18009da41  js      short loc_18009DA83
0x18009da43  mov     ebx, r14d
0x18009da46  lea     r12, aWindowsCompatA_517; "Windows::Compat::Appraiser::AppraiserSe"...
0x18009da4d  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18009da53  and     eax, edi
0x18009da55  test    al, al
0x18009da57  jz      loc_18009DC09
0x18009da5d  mov     dword ptr [rsp+1000h+var_FE0], ebx
0x18009da61  lea     r9, aFailedToAddOne; "Failed to add OneSetting parameter appV"...
0x18009da68  mov     r8, r12; char *
0x18009da6b  lea     rdx, aOnecoreBaseApp_28; "onecore\\base\\appcompat\\appraiser\\he"...
0x18009da72  mov     ecx, 16Ch; unsigned int
0x18009da77  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18009da7c  jmp     loc_18009DC09
0x18009da81  mov     ebx, esi
0x18009da83  mov     dword ptr [rsp+1000h+var_FE0], ebx
0x18009da87  lea     r9, aFailedToAddOne; "Failed to add OneSetting parameter appV"...
0x18009da8e  mov     r8d, 16Bh
0x18009da94  lea     r12, aWindowsCompatA_517; "Windows::Compat::Appraiser::AppraiserSe"...
0x18009da9b  mov     rdx, r12
0x18009da9e  mov     ecx, 3
0x18009daa3  call    AslLogCallPrintf
0x18009daa8  test    ebx, ebx
0x18009daaa  jns     short loc_18009DA4D
0x18009daac  mov     dword ptr [rsp+1000h+var_FD0], ebx; char *
0x18009dab0  lea     r9, aFailedToAddOne; "Failed to add OneSetting parameter appV"...
0x18009dab7  mov     [rsp+1000h+var_FD8], r9; int
0x18009dabc  mov     dword ptr [rsp+1000h+var_FE0], ebx; char *
0x18009dac0  mov     r9, r12; char *
0x18009dac3  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appcompat\\appraiser\\he"...
0x18009daca  mov     edx, 16Ch; bool
0x18009dacf  mov     ecx, edi; this
0x18009dad1  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18009dad6  lea     rcx, [rbp+0F00h+String2]; this
0x18009dadd  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18009dae2  lea     rcx, [rbp+0F00h+String2]
0x18009dae9  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18009daf0  test    rax, rax
0x18009daf3  cmovnz  rcx, rax; this
0x18009daf7  mov     rdx, r14
0x18009dafa  lock xadd [rcx+88h], rdx; unsigned __int64
0x18009db03  lea     r8, [rbp+0F00h+var_780]; char *
0x18009db0a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18009db0f  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r14b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18009db16  jz      short loc_18009DB24
0x18009db18  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18009db1f  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18009db24  mov     r14, cs:qword_1802C9628
0x18009db2b  mov     eax, [r14]
0x18009db2e  cmp     eax, 5
0x18009db31  jbe     loc_18009DC06
0x18009db37  mov     rcx, [r14+18h]
0x18009db3b  mov     rax, [r14+10h]
0x18009db3f  mov     rdx, 200000000000h
0x18009db49  test    rdx, rax
0x18009db4c  jz      loc_18009DC06
0x18009db52  mov     rax, rcx
0x18009db55  and     rax, rdx
0x18009db58  cmp     rax, rcx
0x18009db5b  jnz     loc_18009DC06
0x18009db61  lea     rax, [rbp+0F00h+var_780]
0x18009db68  mov     [rsp+1000h+var_F90], rax
0x18009db6d  mov     [rsp+1000h+var_F9C], ebx
0x18009db71  mov     [rbp+0F00h+var_F68], r12
0x18009db75  lea     rax, aOnecoreBaseApp_28; "onecore\\base\\appcompat\\appraiser\\he"...
0x18009db7c  mov     [rbp+0F00h+var_F70], rax
0x18009db80  mov     dword ptr [rsp+1000h+var_F98], 16Ch
0x18009db88  lea     rax, szValueBuf
0x18009db8f  mov     [rbp+0F00h+var_F78], rax
0x18009db93  xorps   xmm0, xmm0
0x18009db96  movups  xmmword ptr [rbp+0F00h+SystemTime.wYear], xmm0
0x18009db9a  lea     rcx, [rbp+0F00h+SystemTime]; lpSystemTime
0x18009db9e  call    cs:__imp_GetSystemTime
0x18009dba4  movaps  xmm0, xmmword ptr [rbp+0F00h+SystemTime.wYear]
0x18009dba8  movdqa  [rbp+0F00h+var_F30], xmm0
0x18009dbad  lea     rax, [rbp+0F00h+var_F30]
0x18009dbb1  mov     [rbp+0F00h+var_F80], rax
0x18009dbb5  lea     rax, [rsp+1000h+var_F90]
0x18009dbba  mov     [rsp+1000h+var_FB0], rax
0x18009dbbf  lea     rax, [rsp+1000h+var_F9C]
0x18009dbc4  mov     [rsp+1000h+var_FB8], rax
0x18009dbc9  lea     rax, [rbp+0F00h+var_F68]
0x18009dbcd  mov     [rsp+1000h+var_FC0], rax
0x18009dbd2  lea     rax, [rbp+0F00h+var_F70]
0x18009dbd6  mov     [rsp+1000h+var_FC8], rax
0x18009dbdb  lea     rax, [rsp+1000h+var_F98]
0x18009dbe0  mov     [rsp+1000h+var_FD0], rax; char *
0x18009dbe5  lea     rax, [rbp+0F00h+var_F78]
0x18009dbe9  mov     [rsp+1000h+var_FD8], rax
0x18009dbee  lea     rax, [rbp+0F00h+var_F80]
0x18009dbf2  mov     [rsp+1000h+var_FE0], rax
0x18009dbf7  lea     rdx, unk_1802A24C2
0x18009dbfe  mov     rcx, r14
0x18009dc01  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009dc06  xor     r14d, r14d
0x18009dc09  xor     r8d, r8d; unsigned __int16
0x18009dc0c  xor     edx, edx; unsigned __int16
0x18009dc0e  lea     ecx, [rdx+0Ah]; unsigned __int16
0x18009dc11  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18009dc16  test    al, al
0x18009dc18  jz      loc_18009DFE3
0x18009dc1e  mov     r15d, 3
0x18009dc24  cmp     cs:?FeatureType@AppraiserSettings@Appraiser@Compat@Windows@@0W4OnesettingsFeatureType@1234@A, r15d; Windows::Compat::Appraiser::AppraiserSettings::OnesettingsFeatureType Windows::Compat::Appraiser::AppraiserSettings::FeatureType
0x18009dc2b  jz      loc_18009DD40
0x18009dc31  xor     edx, edx; dwCoInit
0x18009dc33  xor     ecx, ecx; pvReserved
0x18009dc35  call    cs:__imp_CoInitializeEx
  ... truncated ...
```
