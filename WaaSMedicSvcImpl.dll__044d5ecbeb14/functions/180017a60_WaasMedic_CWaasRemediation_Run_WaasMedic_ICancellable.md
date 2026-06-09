# WaasMedic::CWaasRemediation::Run(WaasMedic::ICancellable *)

- ea: `0x180017a60`
- end: `0x18001849e`
- name: `?Run@CWaasRemediation@WaasMedic@@UEAAJPEAUICancellable@2@@Z`
- size: `2622`
- prototype: `__int64 __fastcall(WaasMedic::CWaasRemediation *__hidden this, struct WaasMedic::ICancellable *)`
- caller_count: `0`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800050a0`
- `0x1800050c4`
- `0x180005bbc`
- `0x180008c2c`
- `0x180008d99`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x18000de58`
- `0x18000e7cc`
- `0x18000ea1c`
- `0x18000f860`
- `0x18000f9cc`
- `0x180010db4`
- `0x180011c5c`
- `0x180013998`
- `0x1800141e8`
- `0x180014938`
- `0x180014dac`
- `0x18001558c`
- `0x180017778`
- `0x180017a60`
- `0x180018d3c`
- `0x18001c554`
- `0x18001d650`
- `0x18001d898`
- `0x18001d994`
- `0x18001facc`
- `0x18001fccc`
- `0x180020718`
- `0x180020cf0`
- `0x180020dc8`
- `0x180025424`
- `0x180025f0c`
- `0x180027110`
- `0x18002a644`
- `0x18002c844`
- `0x18002d108`
- `0x18002e81c`
- `0x1800639bc`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800183fd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800183fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018407`
- `OLEAUT32!__imp_VariantInit` at `0x180017aa5`
- `OLEAUT32!__imp_VariantInit` at `0x180017aa5`
- `OLEAUT32!__imp_VariantClear` at `0x18001826c`
- `OLEAUT32!__imp_VariantClear` at `0x180018458`
- `OLEAUT32!__imp_VariantClear` at `0x18001826c`
- `OLEAUT32!__imp_VariantClear` at `0x180018458`

## string_xrefs

- `0x180017ae3`: `SummaryEvent is required for WaaSMedic service run.`
- `0x180018011`: `%windir%\System32\`
- `0x18001807d`: `Full path to capsule: %s`
- `0x1800180da`: `LoadLibrary failed for capsule = %s. hr = 0x%08x`
- `0x180018290`: `RunPluginsInCapsule failed.  Capsule = %s. hr = 0x%08x`
- `0x18001817a`: `FreePluginLibrary failed. hr = 0x%08x`
- `0x1800183d7`: `FreePluginLibrary failed. hr = 0x%08x`
- `0x1800181b9`: `Failed to get AllowInPlaceUpgrade registry key value. Considering default value in CalculateCadenceValue.`
- `0x1800181ff`: `Failed to retrieve WaasMedic registry path ! hr = 0x%08x`
- `0x180018325`: `AllPluginsIneffective`
- `0x18001833e`: `AllPluginsIneffective`
- `0x18001835f`: `All plugins failed to remediate the faults. Sending WER report now.`
- `0x1800183e8`: `Signaling completion, will set m_xhCompleted event.`
- `0x18001841c`: `Failed to Set completed/cancelled event! hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WaasMedic::CWaasRemediation::Run(
        WaasMedic::CWaasRemediation *this,
        struct WaasMedic::ICancellable *a2)
{
  void (__fastcall ***v4)(void *, __int64); // r14
  volatile signed __int64 *v5; // rax
  TraceLoggingCorrelationVector *v6; // rax
  int UnifiedImpactLevel; // eax
  struct CMedicEtwConsumer *Instance; // rax
  char v9; // r12
  unsigned int v10; // r15d
  union _ULARGE_INTEGER *v11; // rdx
  int FreeSpaceInKB; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdi
  void (__fastcall *v15)(__int64, void **, __int128 *, __int64 *); // rbx
  __int64 v16; // rdi
  void (__fastcall *v17)(__int64, void **, __int128 *, _DWORD *); // rbx
  ULONGLONG v18; // rdi
  unsigned int v19; // ebx
  unsigned int v20; // r12d
  int v21; // ebx
  struct CMedicEtwConsumer *v22; // rax
  int v23; // eax
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rbx
  const wchar_t *v27; // rax
  __int64 v28; // r8
  char *v29; // rdi
  char *v30; // r15
  unsigned __int128 v31; // kr00_16
  char v32; // bl
  unsigned int v33; // r8d
  __int128 *v34; // r8
  const struct std::filesystem::path *v35; // rdx
  __int64 v36; // r8
  void **v37; // r9
  unsigned __int64 v38; // rdx
  LPCWSTR *v39; // rdi
  __int64 v40; // rbx
  __int64 v41; // rax
  LPCWSTR *v42; // r8
  const WCHAR *v43; // rdx
  int PluginLibrary; // eax
  __int64 v45; // r8
  LPCWSTR *v46; // r8
  unsigned __int16 *v47; // rax
  int v48; // eax
  int v49; // eax
  unsigned int v50; // ebx
  unsigned __int16 *v51; // rdx
  int PersistedRootPath; // eax
  unsigned int v53; // ebx
  HRESULT v54; // eax
  LPCWSTR *v55; // r8
  int v56; // eax
  int v57; // eax
  const unsigned __int16 *v58; // rdx
  const unsigned __int16 *v59; // rcx
  __int64 v60; // r8
  int v61; // eax
  unsigned int v62; // ebx
  int v63; // eax
  int v64; // eax
  signed int LastError; // eax
  HRESULT v66; // eax
  _ULARGE_INTEGER *p_FreeBytesAvailableToCaller; // [rsp+20h] [rbp-E0h]
  int v69; // [rsp+20h] [rbp-E0h]
  unsigned int *v70; // [rsp+20h] [rbp-E0h]
  __int64 v71; // [rsp+28h] [rbp-D8h]
  __int64 v72; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v73; // [rsp+70h] [rbp-90h] BYREF
  char v74; // [rsp+71h] [rbp-8Fh]
  unsigned int v75; // [rsp+74h] [rbp-8Ch] BYREF
  _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+78h] [rbp-88h] BYREF
  __int64 v77; // [rsp+80h] [rbp-80h] BYREF
  char v78; // [rsp+88h] [rbp-78h]
  unsigned int v79; // [rsp+90h] [rbp-70h] BYREF
  __int64 v80; // [rsp+94h] [rbp-6Ch] BYREF
  _DWORD v81[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v82; // [rsp+A8h] [rbp-58h]
  void (__fastcall ***v83)(void *, __int64); // [rsp+B0h] [rbp-50h]
  __int64 v84; // [rsp+B8h] [rbp-48h]
  VARIANTARG pvarg; // [rsp+C0h] [rbp-40h] BYREF
  void *Src[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v87; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v88; // [rsp+F0h] [rbp-10h]
  LPCWSTR lpSrc[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v90; // [rsp+108h] [rbp+8h]
  unsigned __int64 v91; // [rsp+110h] [rbp+10h]
  __int128 v92; // [rsp+118h] [rbp+18h] BYREF
  __int64 v93; // [rsp+128h] [rbp+28h]
  unsigned __int64 v94; // [rsp+130h] [rbp+30h]
  _OWORD v95[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v96[12]; // [rsp+160h] [rbp+60h] BYREF
  char v97[144]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v98[132]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  v75 = 0;
  v73 = 1;
  VariantInit(&pvarg);
  v80 = 0;
  memset_0(v97, 0, 0x81u);
  WaasMedic::CDeferManager::CDeferManager((WaasMedic::CDeferManager *)v96);
  v4 = 0;
  v83 = 0;
  v79 = 0;
  if ( !*((_QWORD *)this + 3) )
  {
    LogLevelW(2u, L"SummaryEvent is required for WaaSMedic service run.", 0);
LABEL_87:
    v63 = WaasMedic::CDeferManager::FinalizeSchedule((WaasMedic::CDeferManager *)v96);
    if ( v63 < 0 )
      LogLevelW(2u, L"Failed in FinalizeSchedule with error hr = 0x%08X.", (unsigned int)v63);
    v64 = WaasMedic::CWaasRemediation::FreePluginLibrary(this);
    v53 = v64;
    if ( v64 < 0 )
      LogLevelW(2u, L"FreePluginLibrary failed. hr = 0x%08x", (unsigned int)v64);
    LogLevelW(5u, L"Signaling completion, will set m_xhCompleted event.");
    if ( !SetEvent(*((HANDLE *)this + 5)) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(2u, L"Failed to Set completed/cancelled event! hr = 0x%08x", (unsigned int)LastError);
    }
    *((_BYTE *)this + 33) = 0;
    if ( v4 )
      (**v4)(v4, 1);
    WaasMedic::CDeferManager::~CDeferManager((WaasMedic::CDeferManager *)v96);
    v66 = VariantClear(&pvarg);
    if ( v66 < 0 )
      _com_issue_error(v66);
    return v53;
  }
  if ( a2 && (**(unsigned __int8 (__fastcall ***)(struct WaasMedic::ICancellable *))a2)(a2) )
  {
    LogLevelW(4u, L"Waas Remediation engine received a cancellation request.");
    goto LABEL_87;
  }
  if ( !*((_BYTE *)this + 32) )
  {
    LogLevelW(2u, L"Waas Remediation engine was not initialized before calling Run. hr = 0x%08x", 2147549183LL);
    goto LABEL_87;
  }
  v5 = (volatile signed __int64 *)*((_QWORD *)this + 7);
  if ( v5
    || ((v6 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow),
         (v77 = (__int64)v6) == 0)
      ? (v5 = 0)
      : (v5 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v6)),
        (*((_QWORD *)this + 7) = v5) != 0) )
  {
    if ( !TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v5,
            _InterlockedExchangeAdd64(v5 + 17, 0),
            v97) )
    {
      LogLevelW(2u, L"Failed to get cV in WaasMedic engine. hr = 0x%08x", 2147549183LL);
      goto LABEL_87;
    }
  }
  else
  {
    v97[0] = 0;
  }
  *(_WORD *)((char *)this + 33) = 1;
  UnifiedImpactLevel = WaasMedic::CWaasRemediation::GetUnifiedImpactLevel(
                         this,
                         (enum winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel *)&v75);
  if ( UnifiedImpactLevel < 0 )
  {
    LogLevelW(2u, L"Failed to get unified impact level. hr = 0x%08x", (unsigned int)UnifiedImpactLevel);
    goto LABEL_87;
  }
  Instance = CMedicEtwConsumer::getInstance();
  v9 = *((_BYTE *)Instance + 42);
  v10 = *((_DWORD *)Instance + 4);
  FreeBytesAvailableToCaller.QuadPart = 0;
  FreeSpaceInKB = WaasMedic::GetFreeSpaceInKB(&FreeBytesAvailableToCaller, v11);
  v13 = FreeSpaceInKB;
  if ( FreeSpaceInKB < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x307,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)FreeSpaceInKB,
      (int)p_FreeBytesAvailableToCaller);
    LogLevelW(2u, L"Failed to determine free space. hr = 0x%08x", v13);
    goto LABEL_87;
  }
  v78 = 0;
  v77 = 0x20000000ALL;
  v14 = *((_QWORD *)this + 2);
  v15 = *(void (__fastcall **)(__int64, void **, __int128 *, __int64 *))(*(_QWORD *)v14 + 8LL);
  v92 = 0;
  v93 = 0;
  v94 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v92, L"LogFolderSizeMultiplier");
  *(_OWORD *)Src = 0;
  v87 = 0;
  v88 = 0;
  std::wstring::_Construct<1,unsigned short const *>(Src, &word_180073298);
  v15(v14, Src, &v92, &v77);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(&v92);
  v82 = 0;
  v81[0] = 10000;
  v81[1] = 2;
  v16 = *((_QWORD *)this + 2);
  v17 = *(void (__fastcall **)(__int64, void **, __int128 *, _DWORD *))(*(_QWORD *)v16 + 8LL);
  v92 = 0;
  v93 = 0;
  v94 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v92, L"MinLowSpaceForLogScaleMB");
  *(_OWORD *)Src = 0;
  v87 = 0;
  v88 = 0;
  std::wstring::_Construct<1,unsigned short const *>(Src, &word_180073298);
  v17(v16, Src, &v92, v81);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(&v92);
  if ( v75 && !v9 )
  {
    v18 = FreeBytesAvailableToCaller.QuadPart >> 20;
    v19 = v81[0];
    v20 = v77;
    LogLevelW(5u, L"The device is out of date, persist additional logs for investigation");
    if ( (unsigned int)v18 <= v19 )
    {
      LogLevelW(5u, L"Disk space was under the limit: %d MB. Limit unchanged: %u KB", (unsigned int)v18, v10);
    }
    else
    {
      v21 = v20 * v10;
      LODWORD(p_FreeBytesAvailableToCaller) = v20 * v10;
      LogLevelW(5u, L"Original max log folder size: %u KB Factor: %u Applying limit: %d KB", v10, v20);
      v22 = CMedicEtwConsumer::getInstance();
      if ( !*((_BYTE *)v22 + 42) && v21 != *((_DWORD *)v22 + 4) )
        *((_DWORD *)v22 + 4) = v21;
    }
  }
  v23 = WaasMedic::CDeferManager::Initialize((WaasMedic::CDeferManager *)v96);
  if ( v23 < 0 )
  {
    LogLevelW(2u, L"Failed in CDeferManager.Initialize() with error hr = 0x%08X.", (unsigned int)v23);
    goto LABEL_87;
  }
  *(_OWORD *)Src = 0;
  v87 = 0;
  v88 = 0;
  v24 = -1;
  do
    ++v24;
  while ( v97[v24] );
  std::string::_Construct<1,char const *>(Src, v97);
  WaasMedic::CDeferManager::SetCV(v96, Src);
  v4 = (void (__fastcall ***)(void *, __int64))operator new(0x10u);
  v77 = (__int64)v4;
  *v4 = (void (__fastcall **)(void *, __int64))&uus::Session::`vftable';
  v25 = uus::Utility::GetFirstBrainSession<uus::Brain3>((__int64)L"waasmedic.engine.run", 0);
  v4[1] = (void (__fastcall **)(void *, __int64))v25;
  v83 = v4;
  v26 = *((_QWORD *)this + 3);
  if ( v25 )
    v27 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
  else
    v27 = L"0.0.0.0";
  *(_OWORD *)Src = 0;
  v87 = 0;
  v88 = 0;
  v28 = -1;
  do
    ++v28;
  while ( v27[v28] );
  std::wstring::_Construct<1,unsigned short const *>(Src, v27);
  WaasMedic::SummaryEvent::SetUUSVersion(v26, Src);
  v29 = (char *)*((_QWORD *)&WaasMedic::pluginCapsuleCollection + 1);
  v31 = WaasMedic::pluginCapsuleCollection;
  v77 = v31 >> 64;
  v30 = (char *)v31;
  if ( (_QWORD)WaasMedic::pluginCapsuleCollection == *((_QWORD *)&WaasMedic::pluginCapsuleCollection + 1) )
  {
LABEL_70:
    if ( (int)WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(&v79) < 0 )
      LogLevelW(
        3u,
        L"Failed to get AllowInPlaceUpgrade registry key value. Considering default value in CalculateCadenceValue.");
    v50 = WaasMedic::CWaasRemediation::CalculateCadenceValue(this, v75, (unsigned int)v80, v79);
    PersistedRootPath = WaasMedic::RegGetPersistedRootPath(
                          (WaasMedic *)L"WaaSMedic",
                          v51,
                          (unsigned int)v98,
                          0,
                          (unsigned int *)p_FreeBytesAvailableToCaller);
    if ( PersistedRootPath >= 0 )
    {
      LOBYTE(v69) = 1;
      v56 = WaasMedic::RegSetDwordValue(-2147483646, v98, L"RunCadenceInHours", v50, v69);
      if ( v56 < 0 )
      {
        LODWORD(v70) = v56;
        LogLevelW(3u, L"Failed to set %s successfully to %d. hr=0x%08x", L"RunCadenceInHours", v50, v70);
      }
      pvarg.vt = 11;
      pvarg.iVal = v73;
      *(_BYTE *)(*((_QWORD *)this + 3) + 20LL) = v73;
      v57 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1) + 24LL))(
              *((_QWORD *)this + 1),
              0,
              L"AllPluginsIneffective",
              &pvarg);
      if ( v57 >= 0 )
      {
        if ( v73 )
        {
          LogLevelW(4u, L"All plugins failed to remediate the faults. Sending WER report now.");
          v61 = WaasMedic::CWERReporter::ReportError(v59, v58, v60, *((struct WaasMedic::IStateProvider **)this + 1));
          v62 = v61;
          if ( v61 < 0 )
          {
            LogLevelW(2u, L"Failed to call CWERReporter::ReportError with error hr=0x%08X", (unsigned int)v61);
            LogLevelW(2u, L"Failed to send WER report with error hr = 0x%08X.", v62);
          }
        }
      }
      else
      {
        LogLevelW(2u, L"Failed to save state for %s with error hr=0x%08X", L"AllPluginsIneffective", (unsigned int)v57);
      }
    }
    else
    {
      LogLevelW(2u, L"Failed to retrieve WaasMedic registry path ! hr = 0x%08x", (unsigned int)PersistedRootPath);
    }
    goto LABEL_87;
  }
  while ( 1 )
  {
    *(_OWORD *)lpSrc = 0;
    v90 = 0;
    v91 = 7;
    LOWORD(lpSrc[0]) = 0;
    std::wstring::wstring(&v92, v30 + 8);
    v32 = *v30;
    v74 = *v30;
    if ( !v30[1] )
    {
      *(_OWORD *)Src = 0;
      v87 = 0;
      v88 = 0;
      std::wstring::_Construct<1,unsigned short const *>(Src, L"%windir%\\System32\\", 18);
      v41 = std::wstring::append(Src);
      v95[0] = *(_OWORD *)v41;
      v95[1] = *(_OWORD *)(v41 + 16);
      *(_QWORD *)(v41 + 16) = 0;
      *(_QWORD *)(v41 + 24) = 7;
      *(_WORD *)v41 = 0;
      std::wstring::operator=(lpSrc, v95);
      std::wstring::~wstring(v95);
      goto LABEL_53;
    }
    v33 = *(_DWORD *)Feature_UUS_WaasMedic_Capsule__descriptor;
    if ( (*(_DWORD *)Feature_UUS_WaasMedic_Capsule__descriptor & 4) == 0 )
    {
      v84 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UUS_WaasMedic_Capsule>::GetCachedFeatureEnabledState(
                         0,
                         v81);
      v33 = v84;
    }
    FreeBytesAvailableToCaller.LowPart = 0;
    WORD2(FreeBytesAvailableToCaller.QuadPart) = 3;
    LODWORD(v72) = 3;
    LODWORD(v71) = 1;
    p_FreeBytesAvailableToCaller = &FreeBytesAvailableToCaller;
    wil::details::ReportUsageToService(&qword_1800A5A98, 36612934, (v33 >> 10) & 1, (v33 >> 11) & 1);
    v34 = &v92;
    if ( v94 > 7 )
      v34 = (__int128 *)v92;
    uus::Session::GetFullPath((__int64)v4, Src, (__int64)v34);
    if ( !std::filesystem::exists((std::filesystem *)Src, v35) )
      break;
    v37 = Src;
    if ( v88 > 7 )
      v37 = (void **)Src[0];
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v37 + v38) );
    if ( v38 > v91 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        lpSrc,
        v38,
        v36,
        v37);
    }
    else
    {
      v39 = lpSrc;
      if ( v91 > 7 )
        v39 = (LPCWSTR *)lpSrc[0];
      v90 = v38;
      v40 = 2 * v38;
      memmove_0(v39, v37, 2 * v38);
      *(_WORD *)((char *)v39 + v40) = 0;
      v32 = v74;
      v29 = (char *)v77;
    }
LABEL_53:
    std::wstring::~wstring(Src);
    v42 = lpSrc;
    if ( v91 > 7 )
      v42 = (LPCWSTR *)lpSrc[0];
    LogLevelW(4u, L"Full path to capsule: %s", v42);
    v43 = (const WCHAR *)lpSrc;
    if ( v91 > 7 )
      v43 = lpSrc[0];
    PluginLibrary = WaasMedic::CWaasRemediation::LoadPluginLibrary(this, v43);
    if ( PluginLibrary >= 0 )
    {
      v47 = (unsigned __int16 *)lpSrc;
      if ( v91 > 7 )
        v47 = (unsigned __int16 *)lpSrc[0];
      v48 = WaasMedic::CWaasRemediation::RunPluginsInCapsule(
              this,
              0,
              v75,
              (unsigned __int8 (__fastcall ***)(_QWORD))a2,
              0,
              0,
              v47,
              (__int64)v97,
              &v80,
              (_DWORD *)&v80 + 1,
              &v73,
              0,
              (WaasMedic::CDeferManager *)v96);
      if ( v48 < 0 )
      {
        v55 = lpSrc;
        if ( v91 > 7 )
          v55 = (LPCWSTR *)lpSrc[0];
        LogLevelW(2u, L"RunPluginsInCapsule failed.  Capsule = %s. hr = 0x%08x", v55, (unsigned int)v48);
        std::wstring::~wstring(&v92);
        std::wstring::~wstring(lpSrc);
        goto LABEL_87;
      }
      v49 = WaasMedic::CWaasRemediation::FreePluginLibrary(this);
      if ( v49 < 0 )
        LogLevelW(2u, L"FreePluginLibrary failed. hr = 0x%08x", (unsigned int)v49);
    }
    else if ( PluginLibrary == -2147024894 && v32 )
    {
      LogLevelW(4u, L"Optional capsule doesn't exist.", v45, (unsigned int)PluginLibrary);
    }
    else
    {
      ++*(_DWORD *)(*((_QWORD *)this + 3) + 124LL);
      v46 = lpSrc;
      if ( v91 > 7 )
        v46 = (LPCWSTR *)lpSrc[0];
      LogLevelW(
        2u,
        L"LoadLibrary failed for capsule = %s. hr = 0x%08x",
        v46,
        (unsigned int)PluginLibrary,
        p_FreeBytesAvailableToCaller,
        v71,
        v72);
    }
    std::wstring::~wstring(&v92);
    std::wstring::~wstring(lpSrc);
    v30 += 40;
    if ( v30 == v29 )
      goto LABEL_70;
  }
  v53 = -2147024894;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x188,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\waasremediation.cpp",
    (const char *)0x80070002LL,
    (int)&FreeBytesAvailableToCaller);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(&v92);
  std::wstring::~wstring(lpSrc);
  (**v4)(v4, 1);
  WaasMedic::CDeferManager::~CDeferManager((WaasMedic::CDeferManager *)v96);
  v54 = VariantClear(&pvarg);
  if ( v54 < 0 )
    _com_issue_error(v54);
  return v53;
}

```

## disassembly

```asm
0x180017a60  mov     [rsp-8+arg_10], rbx
0x180017a65  push    rbp
0x180017a66  push    rsi
0x180017a67  push    rdi
0x180017a68  push    r12
0x180017a6a  push    r13
0x180017a6c  push    r14
0x180017a6e  push    r15
0x180017a70  lea     rbp, [rsp-370h]
0x180017a78  sub     rsp, 470h
0x180017a7f  mov     rax, cs:__security_cookie
0x180017a86  xor     rax, rsp
0x180017a89  mov     [rbp+3A0h+var_40], rax
0x180017a90  mov     r13, rdx
0x180017a93  mov     rsi, rcx
0x180017a96  xor     edi, edi
0x180017a98  mov     dword ptr [rsp+4A0h+var_430+4], edi
0x180017a9c  mov     byte ptr [rsp+4A0h+var_430], 1
0x180017aa1  lea     rcx, [rbp+3A0h+pvarg]; pvarg
0x180017aa5  call    cs:__imp_VariantInit
0x180017aab  nop
0x180017aac  mov     dword ptr [rbp+3A0h+var_40C], edi
0x180017aaf  mov     dword ptr [rbp+3A0h+var_40C+4], edi
0x180017ab2  xor     edx, edx; Val
0x180017ab4  mov     r8d, 81h; Size
0x180017aba  lea     rcx, [rbp+3A0h+var_2E0]; void *
0x180017ac1  call    memset_0
0x180017ac6  lea     rcx, [rbp+3A0h+var_340]; this
0x180017aca  call    ??0CDeferManager@WaasMedic@@QEAA@XZ; WaasMedic::CDeferManager::CDeferManager(void)
0x180017acf  nop
0x180017ad0  mov     r14d, edi
0x180017ad3  mov     [rbp+3A0h+var_3F0], rdi
0x180017ad7  mov     [rbp+3A0h+var_410], edi
0x180017ada  cmp     [rsi+18h], rdi
0x180017ade  jnz     short loc_180017AEF
0x180017ae0  xor     r8d, r8d
0x180017ae3  lea     rdx, aSummaryeventIs; "SummaryEvent is required for WaaSMedic "...
0x180017aea  jmp     loc_18001839B
0x180017aef  test    r13, r13
0x180017af2  jz      short loc_180017B1D
0x180017af4  mov     rax, [r13+0]
0x180017af8  mov     rcx, r13
0x180017afb  mov     rax, [rax]
0x180017afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b03  test    al, al
0x180017b05  jz      short loc_180017B1D
0x180017b07  lea     rdx, aWaasRemediatio_7; "Waas Remediation engine received a canc"...
0x180017b0e  mov     ecx, 4; unsigned __int8
0x180017b13  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180017b18  jmp     loc_1800183A5
0x180017b1d  cmp     [rsi+20h], dil
0x180017b21  jnz     short loc_180017B35
0x180017b23  mov     r8d, 8000FFFFh
0x180017b29  lea     rdx, aWaasRemediatio_2; "Waas Remediation engine was not initial"...
0x180017b30  jmp     loc_18001839B
0x180017b35  mov     rax, [rsi+38h]
0x180017b39  test    rax, rax
0x180017b3c  jnz     short loc_180017B9B
0x180017b3e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017b45  mov     ecx, 90h; unsigned __int64
0x180017b4a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017b4f  mov     [rbp+3A0h+var_420], rax
0x180017b53  test    rax, rax
0x180017b56  jz      short loc_180017B62
0x180017b58  mov     rcx, rax; this
0x180017b5b  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180017b60  jmp     short loc_180017B65
0x180017b62  mov     rax, rdi
0x180017b65  mov     [rsi+38h], rax
0x180017b69  test    rax, rax
0x180017b6c  jnz     short loc_180017B9B
0x180017b6e  mov     [rbp+3A0h+var_2E0], dil
0x180017b75  mov     word ptr [rsi+21h], 1
0x180017b7b  lea     rdx, [rsp+4A0h+var_430+4]; enum winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel *
0x180017b80  mov     rcx, rsi; this
0x180017b83  call    ?GetUnifiedImpactLevel@CWaasRemediation@WaasMedic@@QEAAJAEAW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@@Z; WaasMedic::CWaasRemediation::GetUnifiedImpactLevel(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel &)
0x180017b88  test    eax, eax
0x180017b8a  jns     short loc_180017BCC
0x180017b8c  mov     r8d, eax
0x180017b8f  lea     rdx, aFailedToGetUni; "Failed to get unified impact level. hr "...
0x180017b96  jmp     loc_18001839B
0x180017b9b  mov     rdx, rdi
0x180017b9e  lock xadd [rax+88h], rdx; unsigned __int64
0x180017ba7  lea     r8, [rbp+3A0h+var_2E0]; char *
0x180017bae  mov     rcx, rax; this
0x180017bb1  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180017bb6  test    al, al
0x180017bb8  jnz     short loc_180017B75
0x180017bba  mov     r8d, 8000FFFFh
0x180017bc0  lea     rdx, aFailedToGetCvI; "Failed to get cV in WaasMedic engine. h"...
0x180017bc7  jmp     loc_18001839B
0x180017bcc  call    ?getInstance@CMedicEtwConsumer@@SAAEAV1@XZ; CMedicEtwConsumer::getInstance(void)
0x180017bd1  mov     r12b, [rax+2Ah]
0x180017bd5  mov     r15d, [rax+10h]
0x180017bd9  mov     qword ptr [rsp+4A0h+FreeBytesAvailableToCaller], rdi
0x180017bde  lea     rcx, [rsp+4A0h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x180017be3  call    ?GetFreeSpaceInKB@WaasMedic@@YAJAEAT_ULARGE_INTEGER@@@Z; WaasMedic::GetFreeSpaceInKB(_ULARGE_INTEGER &)
0x180017be8  mov     ebx, eax
0x180017bea  test    eax, eax
0x180017bec  jns     short loc_180017C15
0x180017bee  mov     rcx, [rbp+3A8h]; this
0x180017bf5  mov     r9d, eax; char *
0x180017bf8  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180017bff  mov     edx, 307h; void *
0x180017c04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c09  lea     rdx, aFailedToDeterm_3; "Failed to determine free space. hr = 0x"...
0x180017c10  jmp     loc_180018398
0x180017c15  mov     [rbp+3A0h+var_418], dil
0x180017c19  mov     dword ptr [rbp+3A0h+var_420], 0Ah
0x180017c20  mov     dword ptr [rbp+3A0h+var_420+4], 2
0x180017c27  mov     rdi, [rsi+10h]
0x180017c2b  mov     rax, [rdi]
0x180017c2e  mov     rbx, [rax+8]
0x180017c32  xorps   xmm0, xmm0
0x180017c35  movups  [rbp+3A0h+var_388], xmm0
0x180017c39  xor     eax, eax
0x180017c3b  mov     [rbp+3A0h+var_378], rax
0x180017c3f  mov     [rbp+3A0h+var_370], rax
0x180017c43  lea     r8d, [rax+17h]
0x180017c47  lea     rdx, aLogfoldersizem; "LogFolderSizeMultiplier"
0x180017c4e  lea     rcx, [rbp+3A0h+var_388]
0x180017c52  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017c57  nop
0x180017c58  xorps   xmm0, xmm0
0x180017c5b  movups  xmmword ptr [rbp+3A0h+Src], xmm0
0x180017c5f  xor     eax, eax
0x180017c61  mov     [rbp+3A0h+var_3B8], rax
0x180017c65  mov     [rbp+3A0h+var_3B0], rax
0x180017c69  xor     r8d, r8d
0x180017c6c  lea     rdx, word_180073298
0x180017c73  lea     rcx, [rbp+3A0h+Src]
0x180017c77  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017c7c  nop
0x180017c7d  lea     r9, [rbp+3A0h+var_420]
0x180017c81  lea     r8, [rbp+3A0h+var_388]
0x180017c85  lea     rdx, [rbp+3A0h+Src]
0x180017c89  mov     rcx, rdi
0x180017c8c  mov     rax, rbx
0x180017c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c94  nop
0x180017c95  lea     rcx, [rbp+3A0h+Src]; void *
0x180017c99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017c9e  nop
0x180017c9f  lea     rcx, [rbp+3A0h+var_388]; void *
0x180017ca3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017ca8  xor     ecx, ecx
0x180017caa  mov     [rbp+3A0h+var_3F8], cl
0x180017cad  mov     [rbp+3A0h+var_400], 2710h
0x180017cb4  mov     [rbp+3A0h+var_3FC], 2
0x180017cbb  mov     rdi, [rsi+10h]
0x180017cbf  mov     rax, [rdi]
0x180017cc2  mov     rbx, [rax+8]
0x180017cc6  xorps   xmm0, xmm0
0x180017cc9  movups  [rbp+3A0h+var_388], xmm0
0x180017ccd  mov     [rbp+3A0h+var_378], rcx
0x180017cd1  mov     [rbp+3A0h+var_370], rcx
0x180017cd5  lea     r8d, [rcx+18h]
0x180017cd9  lea     rdx, aMinlowspacefor; "MinLowSpaceForLogScaleMB"
0x180017ce0  lea     rcx, [rbp+3A0h+var_388]
0x180017ce4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017ce9  nop
0x180017cea  xorps   xmm0, xmm0
0x180017ced  movups  xmmword ptr [rbp+3A0h+Src], xmm0
0x180017cf1  xor     eax, eax
0x180017cf3  mov     [rbp+3A0h+var_3B8], rax
0x180017cf7  mov     [rbp+3A0h+var_3B0], rax
0x180017cfb  xor     r8d, r8d
0x180017cfe  lea     rdx, word_180073298
0x180017d05  lea     rcx, [rbp+3A0h+Src]
0x180017d09  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017d0e  nop
0x180017d0f  lea     r9, [rbp+3A0h+var_400]
0x180017d13  lea     r8, [rbp+3A0h+var_388]
0x180017d17  lea     rdx, [rbp+3A0h+Src]
0x180017d1b  mov     rcx, rdi
0x180017d1e  mov     rax, rbx
0x180017d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d26  nop
0x180017d27  lea     rcx, [rbp+3A0h+Src]; void *
0x180017d2b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017d30  nop
0x180017d31  lea     rcx, [rbp+3A0h+var_388]; void *
0x180017d35  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017d3a  xor     edi, edi
0x180017d3c  cmp     dword ptr [rsp+4A0h+var_430+4], edi
0x180017d40  jz      short loc_180017DB9
0x180017d42  test    r12b, r12b
0x180017d45  jnz     short loc_180017DB9
0x180017d47  mov     rdi, qword ptr [rsp+4A0h+FreeBytesAvailableToCaller]
0x180017d4c  shr     rdi, 14h
0x180017d50  mov     ebx, [rbp+3A0h+var_400]
0x180017d53  mov     r12d, dword ptr [rbp+3A0h+var_420]
0x180017d57  lea     rdx, aTheDeviceIsOut; "The device is out of date, persist addi"...
0x180017d5e  mov     ecx, 5; unsigned __int8
0x180017d63  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180017d68  mov     ecx, 5; unsigned __int8
0x180017d6d  cmp     edi, ebx
0x180017d6f  jbe     short loc_180017DA5
0x180017d71  mov     ebx, r15d
0x180017d74  imul    ebx, r12d
0x180017d78  mov     dword ptr [rsp+4A0h+var_480], ebx
0x180017d7c  mov     r9d, r12d
0x180017d7f  mov     r8d, r15d
0x180017d82  lea     rdx, aOriginalMaxLog; "Original max log folder size: %u KB Fac"...
0x180017d89  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180017d8e  call    ?getInstance@CMedicEtwConsumer@@SAAEAV1@XZ; CMedicEtwConsumer::getInstance(void)
0x180017d93  xor     edi, edi
0x180017d95  cmp     [rax+2Ah], dil
0x180017d99  jnz     short loc_180017DB9
0x180017d9b  cmp     ebx, [rax+10h]
0x180017d9e  jz      short loc_180017DB9
0x180017da0  mov     [rax+10h], ebx
0x180017da3  jmp     short loc_180017DB9
0x180017da5  mov     r9d, r15d
0x180017da8  mov     r8d, edi
0x180017dab  lea     rdx, aDiskSpaceWasUn; "Disk space was under the limit: %d MB. "...
0x180017db2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180017db7  xor     edi, edi
0x180017db9  lea     rcx, [rbp+3A0h+var_340]; this
0x180017dbd  call    ?Initialize@CDeferManager@WaasMedic@@QEAAJXZ; WaasMedic::CDeferManager::Initialize(void)
0x180017dc2  test    eax, eax
0x180017dc4  jns     short loc_180017DD5
0x180017dc6  mov     r8d, eax
0x180017dc9  lea     rdx, aFailedInCdefer_0; "Failed in CDeferManager.Initialize() wi"...
0x180017dd0  jmp     loc_18001839B
0x180017dd5  xorps   xmm0, xmm0
0x180017dd8  movups  xmmword ptr [rbp+3A0h+Src], xmm0
0x180017ddc  mov     [rbp+3A0h+var_3B8], rdi
0x180017de0  mov     [rbp+3A0h+var_3B0], rdi
0x180017de4  lea     rax, [rbp+3A0h+var_2E0]
0x180017deb  or      r15, 0FFFFFFFFFFFFFFFFh
0x180017def  mov     r8, r15
0x180017df2  inc     r8
0x180017df5  cmp     [rax+r8], dil
0x180017df9  jnz     short loc_180017DF2
0x180017dfb  lea     rdx, [rbp+3A0h+var_2E0]
0x180017e02  lea     rcx, [rbp+3A0h+Src]
0x180017e06  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180017e0b  lea     rdx, [rbp+3A0h+Src]
0x180017e0f  lea     rcx, [rbp+3A0h+var_340]
0x180017e13  call    ?SetCV@CDeferManager@WaasMedic@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; WaasMedic::CDeferManager::SetCV(std::string)
0x180017e18  mov     ecx, 10h; Size
0x180017e1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017e22  mov     r14, rax
0x180017e25  mov     [rbp+3A0h+var_420], rax
0x180017e29  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x180017e30  mov     [r14], rax
0x180017e33  xor     edx, edx
0x180017e35  lea     rcx, aWaasmedicEngin_2; "waasmedic.engine.run"
0x180017e3c  call    ??$GetFirstBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@PEBGI@Z; uus::Utility::GetFirstBrainSession<uus::Brain3>(ushort const *,uint)
0x180017e41  mov     rdx, rax
0x180017e44  mov     [r14+8], rax
0x180017e48  mov     [rbp+3A0h+var_3F0], r14
0x180017e4c  mov     rbx, [rsi+18h]
0x180017e50  test    rax, rax
0x180017e53  jz      short loc_180017E66
0x180017e55  mov     rcx, [rax]
0x180017e58  mov     rax, [rcx+20h]
0x180017e5c  mov     rcx, rdx
0x180017e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e64  jmp     short loc_180017E6D
0x180017e66  lea     rax, a0000; "0.0.0.0"
0x180017e6d  xorps   xmm0, xmm0
0x180017e70  movups  xmmword ptr [rbp+3A0h+Src], xmm0
0x180017e74  mov     [rbp+3A0h+var_3B8], rdi
0x180017e78  mov     [rbp+3A0h+var_3B0], rdi
0x180017e7c  mov     r8, r15
0x180017e7f  inc     r8
0x180017e82  cmp     [rax+r8*2], di
0x180017e87  jnz     short loc_180017E7F
0x180017e89  mov     rdx, rax
0x180017e8c  lea     rcx, [rbp+3A0h+Src]
0x180017e90  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017e95  nop
0x180017e96  lea     rdx, [rbp+3A0h+Src]
0x180017e9a  mov     rcx, rbx
0x180017e9d  call    ?SetUUSVersion@SummaryEvent@WaasMedic@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::SummaryEvent::SetUUSVersion(std::wstring)
0x180017ea2  mov     r15, qword ptr cs:?pluginCapsuleCollection@WaasMedic@@3V?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N_N@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N_N@std@@@2@@std@@A; std::vector<std::tuple<std::wstring,bool,bool>> WaasMedic::pluginCapsuleCollection
0x180017ea9  mov     rdi, qword ptr cs:?pluginCapsuleCollection@WaasMedic@@3V?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N_N@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N_N@std@@@2@@std@@A+8; std::vector<std::tuple<std::wstring,bool,bool>> WaasMedic::pluginCapsuleCollection
0x180017eb0  mov     [rbp+3A0h+var_420], rdi
0x180017eb4  mov     r12d, 4
0x180017eba  cmp     r15, rdi
0x180017ebd  jz      loc_1800181AA
0x180017ec3  xor     ebx, ebx
0x180017ec5  xorps   xmm0, xmm0
0x180017ec8  movups  xmmword ptr [rbp+3A0h+lpSrc], xmm0
0x180017ecc  mov     [rbp+3A0h+var_398], rbx
0x180017ed0  mov     [rbp+3A0h+var_390], 7
0x180017ed8  mov     word ptr [rbp+3A0h+lpSrc], bx
0x180017edc  lea     rdx, [r15+8]
0x180017ee0  lea     rcx, [rbp+3A0h+var_388]
0x180017ee4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017ee9  nop
0x180017eea  mov     bl, [r15]
0x180017eed  mov     byte ptr [rsp+4A0h+var_430+1], bl
0x180017ef1  xor     ecx, ecx
0x180017ef3  cmp     [r15+1], cl
0x180017ef7  jz      loc_180017FFC
0x180017efd  mov     rax, cs:Feature_UUS_WaasMedic_Capsule__descriptor
0x180017f04  mov     r8d, [rax]
  ... truncated ...
```
