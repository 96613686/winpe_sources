# Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators(RtlArray<Windows::Compat::Appraiser::RegistryIndicatorConstraintEntry> &,RtlNameValueArray &,RtlArray<std::pair<ushort const *,ushort const *>> &,RtlStringArray &,Windows::Compat::Appraiser::IndicatorType,ushort const *,ushort const *,bool,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,int,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,int>>> &)

- ea: `0x1800df914`
- end: `0x1800e09d3`
- name: `?WriteIndicators@RegistryMarkerOutputter@Appraiser@Compat@Windows@@CAJAEAV?$RtlArray@VRegistryIndicatorConstraintEntry@Appraiser@Compat@Windows@@@@AEAVRtlNameValueArray@@AEAV?$RtlArray@U?$pair@PEBGPEBG@std@@@@AEAVRtlStringArray@@W4IndicatorType@234@PEBG5_NAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@@Z`
- size: `4287`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, unsigned __int16 *, bool, __int64)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800da600`

## callees

- `0x18000147c`
- `0x180001b94`
- `0x180008570`
- `0x18000a927`
- `0x180013c7c`
- `0x180013e88`
- `0x1800151f4`
- `0x180028928`
- `0x180029258`
- `0x18002d06c`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180071ac8`
- `0x180076ddc`
- `0x18008e08c`
- `0x18008f26c`
- `0x1800b7bfc`
- `0x1800bdaf0`
- `0x1800df914`
- `0x1801dbc18`
- `0x1801dbcd0`
- `0x1801dbd8c`
- `0x1801dbe34`
- `0x1801dbf20`
- `0x1801dc634`
- `0x1801dd038`
- `0x1801dd1a4`
- `0x1801dd21c`
- `0x1801dd608`
- `0x1801deb5c`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800e071b`
- `KERNEL32!Sleep` at `0x1800e071b`
- `KERNEL32!GetSystemTime` at `0x1800dfd16`
- `KERNEL32!GetSystemTime` at `0x1800e061a`
- `KERNEL32!GetSystemTime` at `0x1800e08f2`
- `KERNEL32!GetSystemTime` at `0x1800dfd16`
- `KERNEL32!GetSystemTime` at `0x1800e061a`
- `KERNEL32!GetSystemTime` at `0x1800e08f2`
- `KERNEL32!GetProcessHeap` at `0x1800e0055`
- `KERNEL32!GetProcessHeap` at `0x1800e0112`
- `KERNEL32!GetProcessHeap` at `0x1800e0055`
- `KERNEL32!GetProcessHeap` at `0x1800e0112`
- `KERNEL32!HeapAlloc` at `0x1800e0067`
- `KERNEL32!HeapAlloc` at `0x1800e0067`
- `KERNEL32!GetLastError` at `0x1800df9fe`
- `KERNEL32!GetLastError` at `0x1800df9fe`
- `KERNEL32!HeapFree` at `0x1800dffd5`
- `KERNEL32!HeapFree` at `0x1800e0120`
- `KERNEL32!HeapFree` at `0x1800dffd5`
- `KERNEL32!HeapFree` at `0x1800e0120`
- `ADVAPI32!RegDeleteTreeW` at `0x1800dfaed`
- `ADVAPI32!RegDeleteTreeW` at `0x1800dfb14`
- `ADVAPI32!RegDeleteTreeW` at `0x1800dfaed`
- `ADVAPI32!RegDeleteTreeW` at `0x1800dfb14`
- `ADVAPI32!RegSetValueExW` at `0x1800dfb6f`
- `ADVAPI32!RegSetValueExW` at `0x1800dfb6f`
- `OLE32!CoUninitialize` at `0x1800e0811`
- `OLE32!CoUninitialize` at `0x1800e0811`
- `OLE32!CoInitializeEx` at `0x1800e0725`
- `OLE32!CoInitializeEx` at `0x1800e0725`
- `ktmw32!CreateTransaction` at `0x1800df9eb`
- `ktmw32!CreateTransaction` at `0x1800df9eb`

## string_xrefs

- `0x1800e074c`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800e0783`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800e07ba`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800e07f0`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800e07a3`: `Failed to launch UNP notification manager task: [0x%x].`
- `0x1800e07e2`: `Failed to launch UNP notification manager task: [0x%x].`
- `0x1800e0745`: `Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTask`
- `0x1800e077c`: `Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTask`
- `0x1800e07b3`: `Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTask`
- `0x1800e07e9`: `Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTask`
- `0x1800dfb97`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800e097f`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800dfba9`: `Failed to initialize indicator writer: [0x%x].`
- `0x1800e0968`: `Failed to initialize indicator writer: [0x%x].`
- `0x1800dfff1`: `Failed to add multi-string indicator to indicator writer: [0x%x].`
- `0x1800e0140`: `Failed to add multi-string indicator to indicator writer: [0x%x].`
- `0x1800e01a9`: `Failed to add multi-string indicator to indicator writer: [0x%x].`
- `0x1800e01c5`: `Failed to add multi-string indicator to indicator writer: [0x%x].`
- `0x1800dfe89`: `Failed to add indicator to indicator writer: [0x%x].`
- `0x1800e0194`: `Failed to add indicator to indicator writer: [0x%x].`
- `0x1800dfb90`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators`
- `0x1800e0978`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators`
- `0x1800e06f7`: `Failed to launch UNP notification task, swallowing: [0x%x].`
- `0x1800e0823`: `Failed to launch UNP notification task, swallowing: [0x%x].`
- `0x1800e0545`: `Failed to write indicators, swallowing: [0x%x].`
- `0x1800e0692`: `Failed to write indicators, swallowing: [0x%x].`
- `0x1800e0467`: `Failed to add additional multistring indicator to indicator writer: [0x%x].`
- `0x1800e0510`: `Failed to add additional multistring indicator to indicator writer: [0x%x].`
- `0x1800e0307`: `Failed to add additional indicator to indicator writer: [0x%x].`
- `0x1800e04d3`: `Failed to add additional indicator to indicator writer: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators(
        const char *a1,
        unsigned __int64 *a2,
        __int64 a3,
        RtlStringArray *a4,
        int a5,
        int a6,
        unsigned __int16 *a7,
        bool a8,
        __int64 a9)
{
  unsigned __int64 *v9; // r12
  unsigned __int64 *v10; // r15
  unsigned __int16 *v11; // r13
  __int64 v12; // r14
  signed int v13; // ebx
  TraceLoggingCorrelationVector *v14; // rcx
  signed int LastError; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  bool v18; // al
  LSTATUS v19; // eax
  LSTATUS v20; // eax
  __int64 v21; // rax
  LSTATUS v22; // eax
  __int64 v23; // r9
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rbx
  unsigned __int64 v27; // kr00_8
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rax
  unsigned __int16 *v30; // r15
  unsigned __int64 v31; // r8
  volatile signed __int64 *v32; // rcx
  void **v33; // rdx
  __int64 v34; // rbx
  __int64 v35; // r8
  __int64 v36; // r9
  unsigned __int128 v37; // rax
  const char *v38; // r12
  const char *v39; // r13
  const unsigned __int16 *v40; // r14
  __int64 v41; // r8
  unsigned __int64 v42; // rax
  const unsigned __int16 **v43; // rcx
  unsigned __int64 v44; // kr10_8
  __int64 v45; // rcx
  unsigned __int64 v46; // rax
  bool v47; // zf
  int v48; // eax
  _DWORD *v49; // rax
  const char *v50; // r9
  unsigned int v51; // ecx
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // r15
  unsigned __int64 v54; // rax
  unsigned __int64 v55; // rcx
  _WORD *v56; // r14
  unsigned __int64 v57; // rax
  HANDLE *v58; // r15
  const unsigned __int16 *v59; // rax
  const unsigned __int16 *v60; // rdx
  unsigned __int16 *v61; // r14
  unsigned __int16 *v62; // r12
  _DWORD *v63; // rax
  _WORD *v64; // r14
  __int64 v65; // rcx
  const void **v66; // rdx
  unsigned __int64 v67; // rax
  unsigned __int64 v68; // kr20_8
  unsigned __int64 v69; // rcx
  __int64 v70; // rax
  size_t v71; // r13
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v73; // rax
  unsigned __int16 *v74; // r15
  const unsigned __int16 *v75; // rdx
  unsigned __int16 *v76; // r12
  _DWORD *v77; // rax
  HANDLE v78; // rax
  char v79; // dl
  const char *v80; // rax
  __int64 *v81; // rax
  __int64 v82; // rcx
  __int64 v83; // rax
  const unsigned __int16 *v84; // r12
  unsigned __int64 v85; // r8
  __int64 v86; // rbx
  const unsigned __int16 *v87; // rdx
  _DWORD *v88; // rax
  __int64 v89; // rax
  __int64 v90; // rcx
  unsigned __int64 v91; // rax
  unsigned __int64 v92; // r15
  __int64 v93; // r12
  const unsigned __int16 **v94; // r14
  unsigned __int64 v95; // rax
  unsigned __int64 v96; // rcx
  const unsigned __int16 *v97; // rdx
  unsigned __int64 v98; // r8
  const unsigned __int16 *v99; // rdx
  _DWORD *v100; // rax
  __int64 v101; // rax
  int v102; // eax
  int v103; // ebx
  volatile signed __int64 *v104; // rcx
  void **v105; // rdx
  __int64 v106; // r14
  __int64 v107; // r8
  __int64 v108; // r9
  char v109; // cl
  int v110; // ebx
  HRESULT v111; // eax
  int v112; // eax
  volatile signed __int64 *v113; // rcx
  void **v114; // rdx
  __int64 v115; // r14
  __int64 v116; // r8
  __int64 v117; // r9
  const char *IsolationFlags; // [rsp+20h] [rbp-E0h]
  const char *Description; // [rsp+30h] [rbp-D0h]
  bool v121[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v122; // [rsp+68h] [rbp-98h] BYREF
  int v123[2]; // [rsp+70h] [rbp-90h] BYREF
  const char *v124; // [rsp+78h] [rbp-88h] BYREF
  char *v125; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v126; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v127; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME *v128; // [rsp+98h] [rbp-68h] BYREF
  const char *v129; // [rsp+A0h] [rbp-60h] BYREF
  const size_t *v130; // [rsp+A8h] [rbp-58h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-50h] BYREF
  RtlStringArray *v132; // [rsp+C0h] [rbp-40h]
  __int64 v133; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v134; // [rsp+D0h] [rbp-30h]
  unsigned __int64 *v135; // [rsp+D8h] [rbp-28h]
  __int64 v136; // [rsp+E0h] [rbp-20h]
  __int128 v137; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v138; // [rsp+F8h] [rbp-8h]
  struct _SYSTEMTIME v139; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v140[144]; // [rsp+120h] [rbp+20h] BYREF
  void *Transaction; // [rsp+1B0h] [rbp+B0h] BYREF
  HKEY phkResult; // [rsp+1B8h] [rbp+B8h] BYREF
  HKEY hKey; // [rsp+1C0h] [rbp+C0h] BYREF
  HKEY v144; // [rsp+1C8h] [rbp+C8h] BYREF
  BYTE v145[528]; // [rsp+1D0h] [rbp+D0h] BYREF
  _WORD Data[140]; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int16 v147; // [rsp+4F8h] [rbp+3F8h]
  char v148[144]; // [rsp+500h] [rbp+400h] BYREF
  char v149[144]; // [rsp+590h] [rbp+490h] BYREF
  char v150[144]; // [rsp+620h] [rbp+520h] BYREF

  v136 = -2;
  v132 = a4;
  v128 = (struct _SYSTEMTIME *)a3;
  v9 = a2;
  v135 = a2;
  v10 = (unsigned __int64 *)a1;
  v125 = (char *)a1;
  v11 = a7;
  v126 = a7;
  v12 = a9;
  v122 = a9;
  Windows::Compat::Shared::IndicatorWriter::IndicatorWriter((Windows::Compat::Shared::IndicatorWriter *)&Transaction);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v148);
  if ( !v10[2] )
  {
    v13 = 0;
    goto LABEL_191;
  }
  v14 = (TraceLoggingCorrelationVector *)v148;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v14 = Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::Increment(v14, v150);
  v121[0] = 0;
  if ( !a7 )
  {
    v13 = -2147024809;
LABEL_190:
    LODWORD(Description) = v13;
    LODWORD(IsolationFlags) = v13;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      140,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
      IsolationFlags,
      (int)"Failed to initialize indicator writer: [0x%x].",
      Description);
    goto LABEL_191;
  }
  v147 = 0;
  Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, 0);
  if ( Transaction == (void *)-1LL )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( v13 < 0 )
      goto LABEL_190;
  }
  else
  {
    v13 = Windows::Compat::Shared::IndicatorWriter::OpenRegistryKeys(
            &hKey,
            &v144,
            L"TargetVersionUpgradeExperienceIndicators",
            a7,
            &Transaction,
            0);
    if ( v13 < 0 )
      goto LABEL_190;
    Windows::Compat::Shared::IndicatorWriter::OpenRegistryKeys(
      &phkResult,
      0,
      L"TargetVersionUpgradeExperienceIndicators",
      a7,
      0,
      0);
    v18 = a8;
    if ( !a8 )
    {
      if ( (int)Windows::Compat::Shared::RegistryChecksum::IsIntact(v121, &hKey, &v144, 3) < 0 || (v18 = 0, !v121[0]) )
        v18 = 1;
    }
    v13 = Windows::Compat::Shared::IndicatorWriter::SetUpTelemetry(
            (struct Windows::Compat::Shared::IndicatorTelemetry *)v145,
            (struct Windows::Compat::Shared::RegistryKey *)&v144,
            (wchar_t *)L"TargetVersionUpgradeExperienceIndicators",
            a7,
            v18,
            v150);
    if ( v13 < 0 )
      goto LABEL_190;
    v19 = RegDeleteTreeW(hKey, 0);
    v13 = v19;
    if ( v19 > 0 )
      v13 = (unsigned __int16)v19 | 0x80070000;
    if ( v13 < 0 )
      goto LABEL_190;
    v20 = RegDeleteTreeW(v144, 0);
    v13 = v20;
    if ( v20 > 0 )
      v13 = (unsigned __int16)v20 | 0x80070000;
    if ( v13 < 0 )
      goto LABEL_190;
    v21 = -1;
    do
      ++v21;
    while ( Data[v21] );
    v22 = RegSetValueExW(v144, L"UtcSyncId", 0, 1u, (const BYTE *)Data, 2 * v21 + 2);
    v13 = v22;
    if ( v22 > 0 )
      v13 = (unsigned __int16)v22 | 0x80070000;
    if ( v13 < 0 )
      goto LABEL_190;
    v13 = 0;
  }
  v23 = 0;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x78Cu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
      "Failed to initialize indicator writer: [0x%x].",
      v13);
    v23 = 0;
  }
  v24 = v10[2];
  if ( v24 )
  {
    v25 = 0;
    v134 = 0;
    while ( 1 )
    {
      v121[0] = 0;
      v26 = 0;
      if ( v25 < v24 )
      {
        v124 = 0;
        v27 = v25;
        v28 = v10[1] * v25;
        if ( !is_mul_ok(v10[1], v27) || (v29 = v10[5], v26 = v28 + v29, v28 + v29 < v29) )
          v26 = 0;
      }
      v30 = *(unsigned __int16 **)(v26 + 56);
      v127 = v30;
      v137 = 0;
      v138 = 0;
      v31 = -1;
      do
        ++v31;
      while ( v30[v31] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&v137, v30, v31);
      if ( *(_DWORD *)(v26 + 152) != (a5 & *(_DWORD *)(v26 + 152)) )
        goto LABEL_66;
      if ( *(_QWORD *)(*(_QWORD *)v26 + 144LL) <= *(_QWORD *)(v26 + 64) )
      {
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v140);
        v32 = (volatile signed __int64 *)v140;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v32 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v32,
          _InterlockedExchangeAdd64(v32 + 17, 0),
          v149);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v33);
        v34 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v127 = (unsigned __int16 *)v149;
          *(_QWORD *)v123 = 2048;
          v130 = (const size_t *)v30;
          v129 = (const char *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v139 = SystemTime;
          v124 = (const char *)&v139;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
            v34,
            (__int64)qword_1802A3F50,
            v35,
            v36,
            (__int64 *)&v124,
            (const size_t **)&v129,
            &v130,
            (__int64)v123,
            (const char **)&v127);
        }
        goto LABEL_66;
      }
      v123[0] = RtlStringArray::Find(v132, v30) <= -1;
      *(_QWORD *)&v37 = std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::find(
                          v12,
                          &v133,
                          &v137);
      v38 = *(const char **)(v12 + 8);
      v39 = *(const char **)v37;
      v124 = *(const char **)v37;
      if ( *(_DWORD *)(v26 + 80) )
      {
        v57 = *(_QWORD *)(v26 + 64);
        if ( v57 != *(_QWORD *)(v26 + 72) )
        {
          v64 = *(_WORD **)(v26 + 144);
          if ( !v64 )
          {
            v65 = *(_QWORD *)v26;
            v66 = 0;
            if ( v57 < *(_QWORD *)(*(_QWORD *)v26 + 144LL) )
            {
              v129 = 0;
              v68 = v57;
              v67 = *(_QWORD *)(v65 + 136) * v57;
              if ( !is_mul_ok(*(_QWORD *)(v65 + 136), v68)
                || (v69 = *(_QWORD *)(v65 + 168), v66 = (const void **)(v69 + v67), v69 + v67 < v69) )
              {
                v66 = 0;
              }
            }
            v64 = *v66;
          }
          v70 = -1;
          do
            ++v70;
          while ( v64[v70] );
          v71 = 2 * v70;
          ProcessHeap = GetProcessHeap();
          v73 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v71 + 4);
          v74 = v73;
          if ( !v73 )
          {
LABEL_109:
            v13 = -2147024882;
            goto LABEL_105;
          }
          memcpy_0(v73, v64, v71);
          v11 = v126;
          v47 = v124 == v38;
          v76 = v127;
          if ( v47 )
          {
            v12 = v122;
          }
          else
          {
            v13 = Windows::Compat::Shared::IndicatorWriter::CheckForDeltasMultiString(v121, v75, v126, v127, v74);
            if ( v13 < 0 )
            {
              v79 = -12;
              goto LABEL_103;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x7F4u,
                "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
                "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
                "Failed to check indicator reg value delta: [0x%x].",
                v13);
            v12 = v122;
            v77 = (_DWORD *)std::unordered_map<std::wstring,int>::operator[](v122, &v137);
            *v77 = v121[0];
          }
          v13 = Windows::Compat::Shared::IndicatorWriter::AddMulti(
                  (Windows::Compat::Shared::IndicatorWriter *)&Transaction,
                  v76,
                  v74,
                  v123[0]);
          v78 = GetProcessHeap();
          HeapFree(v78, 0, v74);
          if ( v13 < 0 )
          {
            v80 = "Failed to add multi-string indicator to indicator writer: [0x%x].";
            v79 = -5;
            goto LABEL_104;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x7FBu,
              "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
              "Failed to add multi-string indicator to indicator writer: [0x%x].",
              v13);
          goto LABEL_66;
        }
        v58 = (HANDLE *)(v26 + 88);
        v59 = RtlStringArray::AllocMultiString((RtlStringArray *)(v26 + 88));
        v61 = (unsigned __int16 *)v59;
        if ( !v59 )
          goto LABEL_109;
        v47 = v39 == v38;
        v62 = v127;
        v11 = v126;
        if ( !v47 )
        {
          v13 = Windows::Compat::Shared::IndicatorWriter::CheckForDeltasMultiString(v121, v60, v126, v127, v59);
          if ( v13 < 0 )
          {
            v79 = -43;
            goto LABEL_103;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x7D5u,
              "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
              "Failed to check indicator reg value delta: [0x%x].",
              v13);
          v63 = (_DWORD *)std::unordered_map<std::wstring,int>::operator[](v122, &v137);
          *v63 = v121[0];
        }
        v13 = Windows::Compat::Shared::IndicatorWriter::AddMulti(
                (Windows::Compat::Shared::IndicatorWriter *)&Transaction,
                v62,
                v61,
                v123[0]);
        HeapFree(*v58, 0, v61);
        if ( v13 < 0 )
        {
          v80 = "Failed to add multi-string indicator to indicator writer: [0x%x].";
          v79 = -35;
          goto LABEL_104;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
          goto LABEL_65;
        v50 = "Failed to add multi-string indicator to indicator writer: [0x%x].";
        v51 = 2013;
      }
      else
      {
        v40 = *(const unsigned __int16 **)(v26 + 144);
        if ( !v40 )
        {
          v41 = *(_QWORD *)v26;
          v42 = *(_QWORD *)(v26 + 64);
          v43 = 0;
          if ( v42 < *(_QWORD *)(*(_QWORD *)v26 + 144LL) )
          {
            v124 = 0;
            v44 = v42;
            v37 = *(unsigned __int64 *)(v41 + 136) * (unsigned __int128)v42;
            v45 = v37;
            if ( !is_mul_ok(*(_QWORD *)(v41 + 136), v44)
              || (v46 = *(_QWORD *)(v41 + 168), v43 = (const unsigned __int16 **)(v46 + v45),
                                                (unsigned __int64)v43 < v46) )
            {
              v43 = 0;
            }
          }
          v40 = *v43;
        }
        v47 = v39 == v38;
        v11 = v126;
        if ( !v47 )
        {
          v48 = Windows::Compat::Shared::IndicatorWriter::CheckForDeltasString(
                  v121,
                  *((const unsigned __int16 **)&v37 + 1),
                  v126,
                  v30,
                  v40);
          v13 = v48;
          if ( v48 < 0 )
          {
            v79 = -71;
LABEL_103:
            v80 = "Failed to check indicator reg value delta: [0x%x].";
            goto LABEL_104;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x7B9u,
              "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
              "Failed to check indicator reg value delta: [0x%x].",
              v48);
          v49 = (_DWORD *)std::unordered_map<std::wstring,int>::operator[](v122, &v137);
          *v49 = v121[0];
        }
        v13 = Windows::Compat::Shared::IndicatorWriter::Add(
                (Windows::Compat::Shared::IndicatorWriter *)&Transaction,
                v30,
                v40,
                v123[0]);
        if ( v13 < 0 )
        {
          v80 = "Failed to add indicator to indicator writer: [0x%x].";
          v79 = -65;
          goto LABEL_104;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
          goto LABEL_65;
        v50 = "Failed to add indicator to indicator writer: [0x%x].";
        v51 = 1983;
      }
      LODWORD(IsolationFlags) = v13;
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        v51,
        "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
        v50,
        IsolationFlags);
LABEL_65:
      v12 = v122;
LABEL_66:
      std::wstring::~wstring((char **)&v137);
      v25 = v134 + 1;
      v134 = v25;
      v10 = (unsigned __int64 *)v125;
      v24 = *((_QWORD *)v125 + 2);
      v23 = 0;
      if ( v25 >= v24 )
      {
        v9 = v135;
        break;
      }
    }
  }
  v52 = v9[2];
  if ( v52 )
  {
    v53 = 0;
    while ( v53 < v52 )
    {
      v133 = 0;
      v54 = v9[1] * v53;
      if ( is_mul_ok(v9[1], v53) && (v55 = v9[5], v54 + v55 >= v55) )
        v56 = *(_WORD **)(v54 + v55);
      else
        v56 = (_WORD *)MEMORY[0];
      v133 = 0;
      if ( !is_mul_ok(v9[1], v53) )
        goto LABEL_117;
      v81 = (__int64 *)(v9[5] + v9[1] * v53);
      if ( (unsigned __int64)v81 < v9[5] )
        goto LABEL_117;
LABEL_118:
      v82 = *v81;
      v83 = -1;
      do
        ++v83;
      while ( *(_WORD *)(v82 + 2 * v83) );
      v84 = (const unsigned __int16 *)(v82 + 2 * (v83 + 1));
      v121[0] = 0;
      v137 = 0;
      v138 = 0;
      v85 = -1;
      do
        ++v85;
      while ( v56[v85] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&v137, v56, v85);
      v86 = v122;
      if ( *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::find(
                        v122,
                        &v125,
                        &v137) != *(_QWORD *)(v86 + 8) )
      {
        v13 = Windows::Compat::Shared::IndicatorWriter::CheckForDeltasString(v121, v87, v11, v56, v84);
        if ( v13 < 0 )
        {
          v80 = "Failed to check indicator reg value delta: [0x%x].";
          v79 = 12;
          goto LABEL_104;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x80Cu,
            "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
            "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
            "Failed to check indicator reg value delta: [0x%x].",
            v13);
        v88 = (_DWORD *)std::unordered_map<std::wstring,int>::operator[](v122, &v137);
        *v88 = v121[0];
      }
      v89 = RtlStringArray::Find(v132, v56);
      v13 = Windows::Compat::Shared::IndicatorWriter::Add(
              (Windows::Compat::Shared::IndicatorWriter *)&Transaction,
              v56,
              v84,
              v89 <= -1);
      if ( v13 < 0 )
      {
        v80 = "Failed to add additional indicator to indicator writer: [0x%x].";
        v79 = 18;
        goto LABEL_104;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x812u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
          "Failed to add additional indicator to indicator writer: [0x%x].",
          v13);
      std::wstring::~wstring((char **)&v137);
      ++v53;
      v9 = v135;
      v52 = v135[2];
      v23 = 0;
      if ( v53 >= v52 )
        goto LABEL_131;
    }
    v56 = (_WORD *)MEMORY[0];
LABEL_117:
    v81 = 0;
    goto LABEL_118;
  }
LABEL_131:
  v90 = (__int64)v128;
  v91 = *(_QWORD *)&v128[1].wYear;
  if ( !v91 )
  {
LABEL_153:
    v102 = Windows::Compat::Shared::IndicatorWriter::Write(&Transaction, v16, v17, v23);
    v103 = v102;
    if ( v102 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x830u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
          "Failed to write indicators, swallowing: [0x%x].",
          v102);
    }
    else
    {
      LODWORD(Description) = v102;
      LODWORD(IsolationFlags) = v102;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        48,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
        IsolationFlags,
        (int)"Failed to write indicators, swallowing: [0x%x].",
        Description);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v140);
      v104 = (volatile signed __int64 *)v140;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v104 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v104,
        _InterlockedExchangeAdd64(v104 + 17, 0),
        v149);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v105);
      v106 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v125 = v149;
        v123[0] = v103;
        v124 = "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators";
        v129 = "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp";
        LODWORD(v122) = 2096;
        v130 = &szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v139 = SystemTime;
        v128 = &v139;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v106,
          (__int64)byte_1802A3F9D,
          v107,
          v108,
          (__int64 *)&v128,
          &v130,
          (__int64)&v122,
          &v129,
          &v124,
          (__int64)v123,
          (const char **)&v125);
      }
    }
    if ( !HIBYTE(v147) )
      goto LABEL_170;
    v109 = 0;
    if ( !_InterlockedExchange(&dword_1802D4C80, 1) )
    {
      if ( !IsWindowsVersionOrGreaterEx(0xAu, 0, 0, 0x42EEu) )
      {
        v110 = 0;
        goto LABEL_168;
      }
      Sleep(0x1388u);
      v111 = CoInitializeEx(0, 0);
      v110 = v111;
      if ( v111 < 0 )
      {
        LODWORD(Description) = v111;
        LODWORD(IsolationFlags) = v111;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          22,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTask",
          IsolationFlags,
          (int)"CoInitialize failed: [0x%x].",
          Description);
LABEL_181:
        LODWORD(Description) = v110;
        LODWORD(IsolationFlags) = v110;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          53,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
          IsolationFlags,
          (int)"Failed to launch UNP notification task, swallowing: [0x%x].",
          Description);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v140);
        v113 = (volatile signed __int64 *)v140;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v113 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v113,
          _InterlockedExchangeAdd64(v113 + 17, 0),
          v149);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v114);
        v115 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v125 = v149;
          LODWORD(v122) = v110;
          v124 = "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators";
          v129 = "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp";
          v123[0] = 2101;
          v130 = &szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v139 = SystemTime;
          v128 = &v139;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v115,
            (__int64)word_1802A3E8A,
            v116,
            v117,
            (__int64 *)&v128,
            &v130,
            (__int64)v123,
            &v129,
            &v124,
            (__int64)&v122,
            (const char **)&v125);
        }
        goto LABEL_170;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x1916u,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTask",
          "CoInitialize failed: [0x%x].",
          v111);
      v112 = Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized();
      v110 = v112;
      if ( v112 < 0 )
      {
        LODWORD(Description) = v112;
        LODWORD(IsolationFlags) = v112;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          26,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTask",
          IsolationFlags,
          (int)"Failed to launch UNP notification manager task: [0x%x].",
          Description);
        goto LABEL_180;
      }
      v109 = 1;
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      {
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x191Au,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTask",
          "Failed to launch UNP notification manager task: [0x%x].",
          v112);
        v110 = 0;
LABEL_180:
        CoUninitialize();
        if ( v110 < 0 )
          goto LABEL_181;
LABEL_168:
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x835u,
            "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
            "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
            "Failed to launch UNP notification task, swallowing: [0x%x].",
            v110);
LABEL_170:
        v13 = 0;
        goto LABEL_191;
      }
    }
    v110 = 0;
    if ( !v109 )
      goto LABEL_168;
    goto LABEL_180;
  }
  v92 = 0;
  v93 = v122;
  while ( 1 )
  {
    v94 = 0;
    if ( v92 < v91 )
    {
      v133 = 0;
      v95 = *(_QWORD *)(v90 + 8) * v92;
      if ( !is_mul_ok(*(_QWORD *)(v90 + 8), v92)
        || (v96 = *(_QWORD *)(v90 + 40), v94 = (const unsigned __int16 **)(v95 + v96), v95 + v96 < v96) )
      {
        v94 = 0;
      }
    }
    v121[0] = 0;
    v97 = *v94;
    v137 = 0;
    v138 = 0;
    v98 = -1;
    do
      ++v98;
    while ( v97[v98] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v137, v97, v98);
    if ( *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::find(
                      v93,
                      &v125,
                      &v137) != *(_QWORD *)(v93 + 8) )
    {
      v13 = Windows::Compat::Shared::IndicatorWriter::CheckForDeltasMultiString(v121, v99, v11, *v94, v94[1]);
      if ( v13 < 0 )
      {
        v80 = "Failed to check indicator reg value delta: [0x%x].";
        v79 = 32;
        goto LABEL_104;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x820u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
          "Failed to check indicator reg value delta: [0x%x].",
          v13);
      v100 = (_DWORD *)std::unordered_map<std::wstring,int>::operator[](v93, &v137);
      *v100 = v121[0];
    }
    v101 = RtlStringArray::Find(v132, *v94);
    v13 = Windows::Compat::Shared::IndicatorWriter::AddMulti(
            (Windows::Compat::Shared::IndicatorWriter *)&Transaction,
            *v94,
            v94[1],
            v101 <= -1);
    if ( v13 < 0 )
      break;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x826u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
        "Failed to add additional multistring indicator to indicator writer: [0x%x].",
        v13);
    std::wstring::~wstring((char **)&v137);
    ++v92;
    v90 = (__int64)v128;
    v91 = *(_QWORD *)&v128[1].wYear;
    if ( v92 >= v91 )
      goto LABEL_153;
  }
  v80 = "Failed to add additional multistring indicator to indicator writer: [0x%x].";
  v79 = 38;
LABEL_104:
  LODWORD(Description) = v13;
  LODWORD(IsolationFlags) = v13;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v79,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
    "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators",
    IsolationFlags,
    (int)v80,
    Description);
LABEL_105:
  std::wstring::~wstring((char **)&v137);
LABEL_191:
  Windows::Compat::Shared::IndicatorWriter::UnInitialize((Windows::Compat::Shared::IndicatorWriter *)&Transaction);
  Windows::Compat::Shared::IndicatorTelemetry::~IndicatorTelemetry((Windows::Compat::Shared::IndicatorTelemetry *)v145);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800df914  push    rbp
0x1800df916  push    rbx
0x1800df917  push    rsi
0x1800df918  push    rdi
0x1800df919  push    r12
0x1800df91b  push    r13
0x1800df91d  push    r14
0x1800df91f  push    r15
0x1800df921  lea     rbp, [rsp-5C8h]
0x1800df929  sub     rsp, 6C8h
0x1800df930  mov     [rbp+600h+var_620], 0FFFFFFFFFFFFFFFEh
0x1800df938  mov     rax, cs:__security_cookie
0x1800df93f  xor     rax, rsp
0x1800df942  mov     [rbp+600h+var_50], rax
0x1800df949  mov     [rbp+600h+var_640], r9
0x1800df94d  mov     [rbp+600h+var_668], r8
0x1800df951  mov     r12, rdx
0x1800df954  mov     [rbp+600h+var_628], rdx
0x1800df958  mov     r15, rcx
0x1800df95b  mov     [rbp+600h+var_680], rcx
0x1800df95f  mov     r13, [rbp+600h+arg_30]
0x1800df966  mov     [rbp+600h+var_678], r13
0x1800df96a  mov     r14, [rbp+600h+arg_40]
0x1800df971  mov     [rsp+700h+var_698], r14
0x1800df976  lea     rcx, [rbp+600h+var_550]; this
0x1800df97d  call    ??0IndicatorWriter@Shared@Compat@Windows@@QEAA@XZ; Windows::Compat::Shared::IndicatorWriter::IndicatorWriter(void)
0x1800df982  nop
0x1800df983  lea     rcx, [rbp+600h+var_200]; this
0x1800df98a  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800df98f  xor     esi, esi
0x1800df991  cmp     [r15+10h], rsi
0x1800df995  jnz     short loc_1800DF99E
0x1800df997  mov     ebx, esi
0x1800df999  jmp     loc_1800E0995
0x1800df99e  lea     rcx, [rbp+600h+var_200]
0x1800df9a5  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800df9ac  test    rax, rax
0x1800df9af  cmovnz  rcx, rax; this
0x1800df9b3  lea     rdx, [rbp+600h+var_E0]; char *
0x1800df9ba  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800df9bf  mov     [rsp+700h+var_6A0], sil
0x1800df9c4  test    r13, r13
0x1800df9c7  jz      loc_1800E095F
0x1800df9cd  mov     [rbp+600h+var_208], si
0x1800df9d4  mov     [rsp+700h+Description], rsi; Description
0x1800df9d9  mov     [rsp+700h+Timeout], esi; Timeout
0x1800df9dd  mov     [rsp+700h+IsolationFlags], esi; IsolationFlags
0x1800df9e1  xor     r9d, r9d; IsolationLevel
0x1800df9e4  xor     r8d, r8d; CreateOptions
0x1800df9e7  xor     edx, edx; UOW
0x1800df9e9  xor     ecx, ecx; lpTransactionAttributes
0x1800df9eb  call    cs:__imp_CreateTransaction
0x1800df9f1  mov     [rbp+600h+var_550], rax
0x1800df9f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800df9fc  jnz     short loc_1800DFA20
0x1800df9fe  call    cs:__imp_GetLastError
0x1800dfa04  mov     ebx, eax
0x1800dfa06  test    eax, eax
0x1800dfa08  jle     short loc_1800DFA13
0x1800dfa0a  movzx   ebx, ax
0x1800dfa0d  or      ebx, 80070000h
0x1800dfa13  test    ebx, ebx
0x1800dfa15  jns     loc_1800DFB8A
0x1800dfa1b  jmp     loc_1800E0964
0x1800dfa20  mov     byte ptr [rsp+700h+Timeout], sil; bool
0x1800dfa25  lea     rax, [rbp+600h+var_550]
0x1800dfa2c  mov     qword ptr [rsp+700h+IsolationFlags], rax; void **
0x1800dfa31  mov     r9, r13; unsigned __int16 *
0x1800dfa34  lea     rdi, aTargetversionu; "TargetVersionUpgradeExperienceIndicator"...
0x1800dfa3b  mov     r8, rdi; unsigned __int16 *
0x1800dfa3e  lea     rdx, [rbp+600h+var_538]; PHKEY
0x1800dfa45  lea     rcx, [rbp+600h+hKey]; phkResult
0x1800dfa4c  call    ?OpenRegistryKeys@IndicatorWriter@Shared@Compat@Windows@@CAJPEAVRegistryKey@234@0PEBG1PEAPEAX_N@Z; Windows::Compat::Shared::IndicatorWriter::OpenRegistryKeys(Windows::Compat::Shared::RegistryKey *,Windows::Compat::Shared::RegistryKey *,ushort const *,ushort const *,void * *,bool)
0x1800dfa51  mov     ebx, eax
0x1800dfa53  test    eax, eax
0x1800dfa55  js      loc_1800E0964
0x1800dfa5b  mov     byte ptr [rsp+700h+Timeout], sil; bool
0x1800dfa60  mov     qword ptr [rsp+700h+IsolationFlags], rsi; void **
0x1800dfa65  mov     r9, r13; unsigned __int16 *
0x1800dfa68  mov     r8, rdi; unsigned __int16 *
0x1800dfa6b  xor     edx, edx; PHKEY
0x1800dfa6d  lea     rcx, [rbp+600h+phkResult]; phkResult
0x1800dfa74  call    ?OpenRegistryKeys@IndicatorWriter@Shared@Compat@Windows@@CAJPEAVRegistryKey@234@0PEBG1PEAPEAX_N@Z; Windows::Compat::Shared::IndicatorWriter::OpenRegistryKeys(Windows::Compat::Shared::RegistryKey *,Windows::Compat::Shared::RegistryKey *,ushort const *,ushort const *,void * *,bool)
0x1800dfa79  mov     al, [rbp+600h+arg_38]
0x1800dfa7f  test    al, al
0x1800dfa81  jnz     short loc_1800DFAB1
0x1800dfa83  mov     r9d, 3
0x1800dfa89  lea     r8, [rbp+600h+var_538]
0x1800dfa90  lea     rdx, [rbp+600h+hKey]
0x1800dfa97  lea     rcx, [rsp+700h+var_6A0]
0x1800dfa9c  call    ?IsIntact@RegistryChecksum@Shared@Compat@Windows@@SAJPEA_NPEAVRegistryKey@234@1W4RegistryChecksumType@234@PEBG@Z; Windows::Compat::Shared::RegistryChecksum::IsIntact(bool *,Windows::Compat::Shared::RegistryKey *,Windows::Compat::Shared::RegistryKey *,Windows::Compat::Shared::RegistryChecksumType,ushort const *)
0x1800dfaa1  test    eax, eax
0x1800dfaa3  js      short loc_1800DFAAF
0x1800dfaa5  cmp     [rsp+700h+var_6A0], sil
0x1800dfaaa  mov     al, sil
0x1800dfaad  jnz     short loc_1800DFAB1
0x1800dfaaf  mov     al, 1
0x1800dfab1  lea     rcx, [rbp+600h+var_E0]
0x1800dfab8  mov     qword ptr [rsp+700h+Timeout], rcx; char *
0x1800dfabd  mov     byte ptr [rsp+700h+IsolationFlags], al; bool
0x1800dfac1  mov     r9, r13; unsigned __int16 *
0x1800dfac4  mov     r8, rdi; String1
0x1800dfac7  lea     rdx, [rbp+600h+var_538]; struct Windows::Compat::Shared::RegistryKey *
0x1800dface  lea     rcx, [rbp+600h+var_530]; this
0x1800dfad5  call    ?SetUpTelemetry@IndicatorWriter@Shared@Compat@Windows@@CAJPEAVIndicatorTelemetry@234@PEAVRegistryKey@234@PEBG2_NPEBD@Z; Windows::Compat::Shared::IndicatorWriter::SetUpTelemetry(Windows::Compat::Shared::IndicatorTelemetry *,Windows::Compat::Shared::RegistryKey *,ushort const *,ushort const *,bool,char const *)
0x1800dfada  mov     ebx, eax
0x1800dfadc  test    eax, eax
0x1800dfade  js      loc_1800E0964
0x1800dfae4  xor     edx, edx; lpSubKey
0x1800dfae6  mov     rcx, [rbp+600h+hKey]; hKey
0x1800dfaed  call    cs:__imp_RegDeleteTreeW
0x1800dfaf3  mov     ebx, eax
0x1800dfaf5  mov     edi, 80070000h
0x1800dfafa  test    eax, eax
0x1800dfafc  jle     short loc_1800DFB03
0x1800dfafe  movzx   ebx, ax
0x1800dfb01  or      ebx, edi
0x1800dfb03  test    ebx, ebx
0x1800dfb05  js      loc_1800E0964
0x1800dfb0b  xor     edx, edx; lpSubKey
0x1800dfb0d  mov     rcx, [rbp+600h+var_538]; hKey
0x1800dfb14  call    cs:__imp_RegDeleteTreeW
0x1800dfb1a  mov     ebx, eax
0x1800dfb1c  test    eax, eax
0x1800dfb1e  jle     short loc_1800DFB25
0x1800dfb20  movzx   ebx, ax
0x1800dfb23  or      ebx, edi
0x1800dfb25  test    ebx, ebx
0x1800dfb27  js      loc_1800E0964
0x1800dfb2d  lea     rcx, [rbp+600h+Data]
0x1800dfb34  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800dfb38  inc     rax
0x1800dfb3b  cmp     [rcx+rax*2], si
0x1800dfb3f  jnz     short loc_1800DFB38
0x1800dfb41  lea     eax, ds:2[rax*2]
0x1800dfb48  mov     [rsp+700h+Timeout], eax; cbData
0x1800dfb4c  lea     rax, [rbp+600h+Data]
0x1800dfb53  mov     qword ptr [rsp+700h+IsolationFlags], rax; lpData
0x1800dfb58  mov     r9d, 1; dwType
0x1800dfb5e  xor     r8d, r8d; Reserved
0x1800dfb61  lea     rdx, aUtcsyncid; "UtcSyncId"
0x1800dfb68  mov     rcx, [rbp+600h+var_538]; hKey
0x1800dfb6f  call    cs:__imp_RegSetValueExW
0x1800dfb75  mov     ebx, eax
0x1800dfb77  test    eax, eax
0x1800dfb79  jle     short loc_1800DFB80
0x1800dfb7b  movzx   ebx, ax
0x1800dfb7e  or      ebx, edi
0x1800dfb80  test    ebx, ebx
0x1800dfb82  js      loc_1800E0964
0x1800dfb88  mov     ebx, esi
0x1800dfb8a  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800dfb90  lea     rdi, aWindowsCompatA_804; "Windows::Compat::Appraiser::RegistryMar"...
0x1800dfb97  lea     rsi, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800dfb9e  xor     r9d, r9d
0x1800dfba1  test    al, 1
0x1800dfba3  jz      short loc_1800DFBC3
0x1800dfba5  mov     [rsp+700h+IsolationFlags], ebx
0x1800dfba9  lea     r9, aFailedToInitia_18; "Failed to initialize indicator writer: "...
0x1800dfbb0  mov     r8, rdi; char *
0x1800dfbb3  mov     rdx, rsi; char *
0x1800dfbb6  mov     ecx, 78Ch; unsigned int
0x1800dfbbb  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800dfbc0  xor     r9d, r9d
0x1800dfbc3  mov     rax, [r15+10h]
0x1800dfbc7  test    rax, rax
0x1800dfbca  jz      loc_1800DFEDF
0x1800dfbd0  mov     rcx, r9
0x1800dfbd3  mov     [rbp+600h+var_630], rcx
0x1800dfbd7  mov     r12, 200000000020h
0x1800dfbe1  mov     [rsp+700h+var_6A0], r9b
0x1800dfbe6  mov     rbx, r9
0x1800dfbe9  cmp     rcx, rax
0x1800dfbec  jnb     short loc_1800DFC12
0x1800dfbee  mov     [rsp+700h+var_688], r9
0x1800dfbf3  mov     rax, rcx
0x1800dfbf6  mul     qword ptr [r15+8]
0x1800dfbfa  mov     rcx, rax
0x1800dfbfd  test    rdx, rdx
0x1800dfc00  jnz     short loc_1800DFC0F
0x1800dfc02  mov     rax, [r15+28h]
0x1800dfc06  lea     rbx, [rcx+rax]
0x1800dfc0a  cmp     rbx, rax
0x1800dfc0d  jnb     short loc_1800DFC12
0x1800dfc0f  mov     rbx, r9
0x1800dfc12  mov     r15, [rbx+38h]
0x1800dfc16  mov     [rbp+600h+var_670], r15
0x1800dfc1a  xorps   xmm0, xmm0
0x1800dfc1d  movups  [rbp+600h+var_618], xmm0
0x1800dfc21  xorps   xmm1, xmm1
0x1800dfc24  movdqu  [rbp+600h+var_608], xmm1
0x1800dfc29  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800dfc2d  inc     r8
0x1800dfc30  cmp     [r15+r8*2], r9w
0x1800dfc35  jnz     short loc_1800DFC2D
0x1800dfc37  mov     rdx, r15
0x1800dfc3a  lea     rcx, [rbp+600h+var_618]
0x1800dfc3e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800dfc43  nop
0x1800dfc44  mov     ecx, [rbx+98h]
0x1800dfc4a  mov     eax, ecx
0x1800dfc4c  and     eax, [rbp+600h+arg_20]
0x1800dfc52  cmp     ecx, eax
0x1800dfc54  jnz     loc_1800DFEB3
0x1800dfc5a  mov     rcx, [rbx]
0x1800dfc5d  mov     rax, [rbx+40h]
0x1800dfc61  cmp     [rcx+90h], rax
0x1800dfc68  ja      loc_1800DFD71
0x1800dfc6e  lea     rcx, [rbp+600h+var_5E0]; this
0x1800dfc72  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800dfc77  lea     rcx, [rbp+600h+var_5E0]
0x1800dfc7b  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800dfc82  xor     ebx, ebx
0x1800dfc84  test    rax, rax
0x1800dfc87  cmovnz  rcx, rax; this
0x1800dfc8b  mov     edx, ebx
0x1800dfc8d  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800dfc96  lea     r8, [rbp+600h+var_170]; char *
0x1800dfc9d  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800dfca2  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, bl; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800dfca8  jz      short loc_1800DFCB6
0x1800dfcaa  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800dfcb1  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800dfcb6  mov     rbx, cs:qword_1802C9628
0x1800dfcbd  mov     eax, [rbx]
0x1800dfcbf  cmp     eax, 5
0x1800dfcc2  jbe     loc_1800DFEB3
0x1800dfcc8  mov     rcx, [rbx+18h]
0x1800dfccc  mov     rax, [rbx+10h]
0x1800dfcd0  test    r12, rax
0x1800dfcd3  jz      loc_1800DFEB3
0x1800dfcd9  mov     rax, rcx
0x1800dfcdc  and     rax, r12
0x1800dfcdf  cmp     rax, rcx
0x1800dfce2  jnz     loc_1800DFEB3
0x1800dfce8  lea     rax, [rbp+600h+var_170]
0x1800dfcef  mov     [rbp+600h+var_670], rax
0x1800dfcf3  mov     qword ptr [rsp+700h+var_690], 800h
0x1800dfcfc  mov     [rbp+600h+var_658], r15
0x1800dfd00  lea     rax, szValueBuf
0x1800dfd07  mov     [rbp+600h+var_660], rax
0x1800dfd0b  xorps   xmm0, xmm0
0x1800dfd0e  movups  xmmword ptr [rbp+600h+SystemTime.wYear], xmm0
0x1800dfd12  lea     rcx, [rbp+600h+SystemTime]; lpSystemTime
0x1800dfd16  call    cs:__imp_GetSystemTime
0x1800dfd1c  movaps  xmm0, xmmword ptr [rbp+600h+SystemTime.wYear]
0x1800dfd20  movdqa  [rbp+600h+var_5F0], xmm0
0x1800dfd25  lea     rax, [rbp+600h+var_5F0]
0x1800dfd29  mov     [rsp+700h+var_688], rax
0x1800dfd2e  lea     rax, [rbp+600h+var_670]
0x1800dfd32  mov     [rsp+700h+var_6C0], rax
0x1800dfd37  lea     rax, [rsp+700h+var_690]
0x1800dfd3c  mov     [rsp+700h+var_6C8], rax
0x1800dfd41  lea     rax, [rbp+600h+var_658]
0x1800dfd45  mov     [rsp+700h+Description], rax
0x1800dfd4a  lea     rax, [rbp+600h+var_660]
0x1800dfd4e  mov     qword ptr [rsp+700h+Timeout], rax
0x1800dfd53  lea     rax, [rsp+700h+var_688]
0x1800dfd58  mov     qword ptr [rsp+700h+IsolationFlags], rax
0x1800dfd5d  lea     rdx, qword_1802A3F50
0x1800dfd64  mov     rcx, rbx
0x1800dfd67  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x1800dfd6c  jmp     loc_1800DFEB3
0x1800dfd71  mov     rdx, r15; unsigned __int16 *
0x1800dfd74  mov     rcx, [rbp+600h+var_640]; this
0x1800dfd78  call    ?Find@RtlStringArray@@QEBA_JPEBG@Z; RtlStringArray::Find(ushort const *)
0x1800dfd7d  xor     ecx, ecx
0x1800dfd7f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800dfd83  setle   cl
0x1800dfd86  mov     [rsp+700h+var_690], ecx
0x1800dfd8a  lea     r8, [rbp+600h+var_618]
0x1800dfd8e  lea     rdx, [rbp+600h+var_638]
0x1800dfd92  mov     rcx, r14
0x1800dfd95  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::find(std::wstring const &)
0x1800dfd9a  mov     r12, [r14+8]
0x1800dfd9e  mov     r13, [rax]
0x1800dfda1  mov     [rsp+700h+var_688], r13
0x1800dfda6  xor     r9d, r9d
0x1800dfda9  cmp     [rbx+50h], r9d
0x1800dfdad  jnz     loc_1800DFF28
0x1800dfdb3  mov     r14, [rbx+90h]
0x1800dfdba  test    r14, r14
0x1800dfdbd  jnz     short loc_1800DFDFB
0x1800dfdbf  mov     r8, [rbx]
0x1800dfdc2  mov     rax, [rbx+40h]
0x1800dfdc6  mov     ecx, r9d
0x1800dfdc9  cmp     rax, [r8+90h]
0x1800dfdd0  jnb     short loc_1800DFDF8
0x1800dfdd2  mov     [rsp+700h+var_688], r9
0x1800dfdd7  mul     qword ptr [r8+88h]
0x1800dfdde  mov     rcx, rax
0x1800dfde1  test    rdx, rdx
0x1800dfde4  jnz     short loc_1800DFDF5
0x1800dfde6  mov     rax, [r8+0A8h]
0x1800dfded  add     rcx, rax
0x1800dfdf0  cmp     rcx, rax
0x1800dfdf3  jnb     short loc_1800DFDF8
0x1800dfdf5  mov     rcx, r9
0x1800dfdf8  mov     r14, [rcx]
0x1800dfdfb  cmp     r13, r12
  ... truncated ...
```
