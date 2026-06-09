# WaasMedic::CStackDataResetPlugin::DetectCondition(ushort const * *,bool *)

- ea: `0x18003a650`
- end: `0x18003afc1`
- name: `?DetectCondition@CStackDataResetPlugin@WaasMedic@@UEAAJPEAPEBGPEA_N@Z`
- size: `2417`
- prototype: `__int64 __fastcall(WaasMedic::CStackDataResetPlugin *__hidden this, const unsigned __int16 **, bool *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callees

- `0x18000256c`
- `0x180003bb0`
- `0x180004708`
- `0x180009a54`
- `0x18000a5d0`
- `0x18000b308`
- `0x180016c9c`
- `0x1800179c4`
- `0x18001ced8`
- `0x1800250e0`
- `0x1800252c4`
- `0x18002543c`
- `0x180025f00`
- `0x1800262a8`
- `0x180026424`
- `0x180030fbc`
- `0x18003a650`
- `0x18003afc8`
- `0x180055fb8`
- `0x1800562c4`
- `0x180056814`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a83c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a8c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a83c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a8c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a82e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a8b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a82e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a8b2`
- `OLEAUT32!__imp_VariantInit` at `0x18003a712`
- `OLEAUT32!__imp_VariantInit` at `0x18003a712`
- `OLEAUT32!__imp_VariantClear` at `0x18003af93`
- `OLEAUT32!__imp_VariantClear` at `0x18003af93`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003a8a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003a8a1`

## string_xrefs

- `0x18003a6f5`: `Plugin bypassing detection due to manual remediation.`
- `0x18003a6ad`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003a858`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003a9a6`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003aa16`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003ab42`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003ad2f`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003ae5b`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003a8cf`: `Datastore is not present on device. Nothing to delete`
- `0x18003ad7f`: `Datastore has been deleted or created recently. 30 days is the default threshold`
- `0x18003ae4c`: `HasAnyHiddenUpdates failed`
- `0x18003aeea`: `Hidden updates are registered on datastore, customer would be offered those updates again`
- `0x18003aeab`: `HiddenUpdates`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::CStackDataResetPlugin::DetectCondition(
        WaasMedic::CStackDataResetPlugin *this,
        const unsigned __int16 **a2,
        bool *a3)
{
  unsigned int v6; // edx
  WaasMedic *v7; // rcx
  unsigned __int16 **v8; // r8
  int v9; // eax
  int IsUpgradeInProgress; // edi
  void *v11; // rbx
  int v12; // eax
  HANDLE v13; // rax
  bool v14; // di
  HANDLE ProcessHeap; // rax
  const struct _tlgProvider_t *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // r9d
  _QWORD *v20; // rsi
  const struct _tlgProvider_t *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // r9d
  _QWORD *v25; // rsi
  unsigned int v26; // ecx
  const struct _tlgProvider_t *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // r9d
  _QWORD *v31; // rsi
  const struct _tlgProvider_t *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // r9d
  _QWORD *v36; // rsi
  const struct _tlgProvider_t *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  int v40; // r9d
  _QWORD *v41; // rsi
  const struct _tlgProvider_t *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  int v45; // r9d
  _QWORD *v46; // rsi
  int v47; // [rsp+20h] [rbp-E0h]
  const char *v48; // [rsp+28h] [rbp-D8h]
  bool v49; // [rsp+40h] [rbp-C0h] BYREF
  bool v50[7]; // [rsp+41h] [rbp-BFh] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v52; // [rsp+50h] [rbp-B0h] BYREF
  const char *v53; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v54; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+70h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszPath[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  if ( a2 )
    *a2 = 0;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      (const char *)0x80004003LL,
      (int)"pfIsDetected is null",
      v48);
    return 2147500035LL;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl) )
  {
    v50[0] = 0;
    if ( (int)WaasMedic::CRemediationPluginBase::IsManualRemediationApplicable(this, v50) >= 0 && v50[0] )
    {
      *a3 = 1;
      LogLevelW(4u, L"Plugin bypassing detection due to manual remediation.");
      return 0;
    }
  }
  VariantInit(&pvarg);
  v50[0] = 0;
  v49 = 0;
  v54 = 0;
  v55 = 0;
  if ( !WaasMedic::MiscUtil::IsTestKeyEnabled(L"IsStackDataResetForcedDetected", v6)
    || !WaasMedic::IsTestSigningEnabled(v7) )
  {
    *a3 = 0;
    memset_0(pszPath, 0, 0x208u);
    lpMem = 0;
    v9 = WaasMedic::SafeExpandEnvironmentString(
           L"%windir%\\SoftwareDistribution\\DataStore",
           (const unsigned __int16 *)&lpMem,
           v8);
    IsUpgradeInProgress = v9;
    if ( v9 >= 0 )
    {
      v11 = lpMem;
      v12 = StringCchPrintfW(pszPath, 0x104u, L"%s\\%s", lpMem);
      IsUpgradeInProgress = v12;
      if ( v12 >= 0 )
      {
        v14 = PathFileExistsW(pszPath);
        if ( v11 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v11);
        }
        if ( v14 )
        {
          IsUpgradeInProgress = WaasMedic::UsoHelper::Initialize((WaasMedic::UsoHelper *)&v54);
          if ( IsUpgradeInProgress < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x9A,
              (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
              (const char *)(unsigned int)IsUpgradeInProgress,
              (int)"USO helper failed to initialize",
              v48);
            if ( *((_QWORD *)&v54 + 1) )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 16LL))(*((_QWORD *)&v54 + 1));
            if ( (_QWORD)v54 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v54 + 16LL))(v54);
            goto LABEL_122;
          }
          IsUpgradeInProgress = WaasMedic::UsoHelper::RebootRequired((WaasMedic::UsoHelper *)&v54, v50);
          if ( IsUpgradeInProgress < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x9C,
              (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
              (const char *)(unsigned int)IsUpgradeInProgress,
              (int)"RebootRequired failed",
              v48);
            if ( *((_QWORD *)&v54 + 1) )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 16LL))(*((_QWORD *)&v54 + 1));
            if ( (_QWORD)v54 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v54 + 16LL))(v54);
            goto LABEL_122;
          }
          if ( v50[0] )
          {
            LogLevelA(4u, "Reboot is required, blocking detection to avoid disruption");
            v21 = WaasMedic::TelemetryProvider::Provider();
            if ( *(_DWORD *)v21 > 5u )
            {
              v23 = *((_QWORD *)v21 + 3);
              v22 = 0x400000000000LL;
              if ( (*((_QWORD *)v21 + 2) & 0x400000000000LL) != 0 && (v23 & 0x400000000000LL) == v23 )
              {
                v53 = "RebootRequired";
                v25 = (_QWORD *)((char *)this + 120);
                if ( v25[3] > 0xFu )
                  v25 = (_QWORD *)*v25;
                v52 = v25;
                lpMem = (LPVOID)0x2000000;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  (_DWORD)v21,
                  (unsigned int)&word_1800899CE,
                  v23,
                  v24,
                  (__int64)&lpMem,
                  (__int64)&v52,
                  (__int64)&v53);
              }
            }
            if ( *((_QWORD *)&v54 + 1) )
              (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)&v54 + 1) + 16LL))(
                *((_QWORD *)&v54 + 1),
                v22,
                v23);
          }
          else
          {
            IsUpgradeInProgress = WaasMedic::UsoHelper::IsUpgradeInProgress((WaasMedic::UsoHelper *)&v54, &v49);
            if ( IsUpgradeInProgress < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0xA6,
                (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
                (const char *)(unsigned int)IsUpgradeInProgress,
                (int)"IsUpgradeInProgress failed",
                v48);
              if ( *((_QWORD *)&v54 + 1) )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 16LL))(*((_QWORD *)&v54 + 1));
              if ( (_QWORD)v54 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v54 + 16LL))(v54);
              goto LABEL_122;
            }
            if ( v49 )
            {
              LogLevelA(4u, "Upgrade in progress, blocking detection to avoid disruption");
              v27 = WaasMedic::TelemetryProvider::Provider();
              if ( *(_DWORD *)v27 > 5u )
              {
                v29 = *((_QWORD *)v27 + 3);
                v28 = 0x400000000000LL;
                if ( (*((_QWORD *)v27 + 2) & 0x400000000000LL) != 0 && (v29 & 0x400000000000LL) == v29 )
                {
                  v53 = "UpgradeInProgress";
                  v31 = (_QWORD *)((char *)this + 120);
                  if ( v31[3] > 0xFu )
                    v31 = (_QWORD *)*v31;
                  v52 = v31;
                  lpMem = (LPVOID)0x2000000;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    (_DWORD)v27,
                    (unsigned int)&dword_18008992C,
                    v29,
                    v30,
                    (__int64)&lpMem,
                    (__int64)&v52,
                    (__int64)&v53);
                }
              }
              if ( *((_QWORD *)&v54 + 1) )
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)&v54 + 1) + 16LL))(
                  *((_QWORD *)&v54 + 1),
                  v28,
                  v29);
            }
            else if ( WaasMedic::MiscUtil::IsOobePastThreshold(v26) )
            {
              v49 = 0;
              IsUpgradeInProgress = WaasMedic::CStackDataResetPlugin::EvaluateThresholdToResetDatastore(this, &v49);
              if ( IsUpgradeInProgress < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0xB7,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
                  (const char *)(unsigned int)IsUpgradeInProgress,
                  (int)"EvaluateThresholdToResetDatastore has failed",
                  v48);
                if ( *((_QWORD *)&v54 + 1) )
                  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 16LL))(*((_QWORD *)&v54 + 1));
                if ( (_QWORD)v54 )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v54 + 16LL))(v54);
                goto LABEL_122;
              }
              if ( v49 )
              {
                v49 = 0;
                IsUpgradeInProgress = WaasMedic::MiscUtil::HasAnyHiddenUpdates(&v49);
                if ( IsUpgradeInProgress < 0 )
                {
                  wil::details::in1diag3::Return_HrMsg(
                    retaddr,
                    (void *)0xC0,
                    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
                    (const char *)(unsigned int)IsUpgradeInProgress,
                    (int)"HasAnyHiddenUpdates failed",
                    v48);
                  if ( *((_QWORD *)&v54 + 1) )
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 16LL))(*((_QWORD *)&v54 + 1));
                  if ( (_QWORD)v54 )
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v54 + 16LL))(v54);
                  goto LABEL_122;
                }
                if ( v49 )
                {
                  LogLevelA(4u, "HiddenUpdates");
                  v42 = WaasMedic::TelemetryProvider::Provider();
                  if ( *(_DWORD *)v42 > 5u )
                  {
                    v44 = *((_QWORD *)v42 + 3);
                    v43 = 0x400000000000LL;
                    if ( (*((_QWORD *)v42 + 2) & 0x400000000000LL) != 0 && (v44 & 0x400000000000LL) == v44 )
                    {
                      v53 = "Hidden updates are registered on datastore, customer would be offered those updates again";
                      v46 = (_QWORD *)((char *)this + 120);
                      if ( v46[3] > 0xFu )
                        v46 = (_QWORD *)*v46;
                      v52 = v46;
                      lpMem = (LPVOID)0x2000000;
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                        (_DWORD)v42,
                        (unsigned int)byte_1800898DB,
                        v44,
                        v45,
                        (__int64)&lpMem,
                        (__int64)&v52,
                        (__int64)&v53);
                    }
                  }
                  if ( *((_QWORD *)&v54 + 1) )
                    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)&v54 + 1) + 16LL))(
                      *((_QWORD *)&v54 + 1),
                      v43,
                      v44);
                }
                else
                {
                  *a3 = 1;
                  if ( *((_QWORD *)&v54 + 1) )
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 16LL))(*((_QWORD *)&v54 + 1));
                }
              }
              else
              {
                LogLevelA(4u, "Datastore has been deleted or created recently. 30 days is the default threshold");
                v37 = WaasMedic::TelemetryProvider::Provider();
                if ( *(_DWORD *)v37 > 5u )
                {
                  v39 = *((_QWORD *)v37 + 3);
                  v38 = 0x400000000000LL;
                  if ( (*((_QWORD *)v37 + 2) & 0x400000000000LL) != 0 && (v39 & 0x400000000000LL) == v39 )
                  {
                    v53 = "ThresholdToResetDatastore";
                    v41 = (_QWORD *)((char *)this + 120);
                    if ( v41[3] > 0xFu )
                      v41 = (_QWORD *)*v41;
                    v52 = v41;
                    lpMem = (LPVOID)0x2000000;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                      (_DWORD)v37,
                      (unsigned int)word_18008988A,
                      v39,
                      v40,
                      (__int64)&lpMem,
                      (__int64)&v52,
                      (__int64)&v53);
                  }
                }
                if ( *((_QWORD *)&v54 + 1) )
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)&v54 + 1) + 16LL))(
                    *((_QWORD *)&v54 + 1),
                    v38,
                    v39);
              }
            }
            else
            {
              LogLevelA(4u, "OOBE threshold has not been passed");
              v32 = WaasMedic::TelemetryProvider::Provider();
              if ( *(_DWORD *)v32 > 5u )
              {
                v34 = *((_QWORD *)v32 + 3);
                v33 = 0x400000000000LL;
                if ( (*((_QWORD *)v32 + 2) & 0x400000000000LL) != 0 && (v34 & 0x400000000000LL) == v34 )
                {
                  v53 = "OOBE";
                  v36 = (_QWORD *)((char *)this + 120);
                  if ( v36[3] > 0xFu )
                    v36 = (_QWORD *)*v36;
                  v52 = v36;
                  lpMem = (LPVOID)0x2000000;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    (_DWORD)v32,
                    (unsigned int)byte_18008997D,
                    v34,
                    v35,
                    (__int64)&lpMem,
                    (__int64)&v52,
                    (__int64)&v53);
                }
              }
              if ( *((_QWORD *)&v54 + 1) )
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)&v54 + 1) + 16LL))(
                  *((_QWORD *)&v54 + 1),
                  v33,
                  v34);
            }
          }
        }
        else
        {
          LogLevelA(4u, "Datastore is not present on device. Nothing to delete");
          v16 = WaasMedic::TelemetryProvider::Provider();
          if ( *(_DWORD *)v16 > 5u )
          {
            v18 = *((_QWORD *)v16 + 3);
            v17 = 0x400000000000LL;
            if ( (*((_QWORD *)v16 + 2) & 0x400000000000LL) != 0 && (v18 & 0x400000000000LL) == v18 )
            {
              lpMem = "NoDatastore";
              v20 = (_QWORD *)((char *)this + 120);
              if ( v20[3] > 0xFu )
                v20 = (_QWORD *)*v20;
              v52 = v20;
              v53 = (const char *)0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                (_DWORD)v16,
                (unsigned int)&byte_180089A1F,
                v18,
                v19,
                (__int64)&v53,
                (__int64)&v52,
                (__int64)&lpMem);
            }
          }
          if ( *((_QWORD *)&v54 + 1) )
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)&v54 + 1) + 16LL))(
              *((_QWORD *)&v54 + 1),
              v17,
              v18);
        }
        goto LABEL_119;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x325,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
        (const char *)(unsigned int)v12,
        (int)L"DataStore.edb");
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x323,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
        (const char *)(unsigned int)v9,
        v47);
      v11 = lpMem;
    }
    if ( v11 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v11);
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      (const char *)(unsigned int)IsUpgradeInProgress,
      (int)"Failed to determine if datastore is present on device",
      v48);
    if ( *((_QWORD *)&v54 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 16LL))(*((_QWORD *)&v54 + 1));
    if ( (_QWORD)v54 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v54 + 16LL))(v54);
    goto LABEL_122;
  }
  LogLevelW(3u, L"TestHook set: %s.", L"IsStackDataResetForcedDetected");
  *a3 = 1;
  if ( *((_QWORD *)&v54 + 1) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 16LL))(*((_QWORD *)&v54 + 1));
LABEL_119:
  if ( (_QWORD)v54 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v54 + 16LL))(v54);
  IsUpgradeInProgress = 0;
LABEL_122:
  VariantClear(&pvarg);
  return (unsigned int)IsUpgradeInProgress;
}

```

## disassembly

```asm
0x18003a650  mov     [rsp-8+arg_18], rbx
0x18003a655  push    rbp
0x18003a656  push    rsi
0x18003a657  push    rdi
0x18003a658  push    r14
0x18003a65a  push    r15
0x18003a65c  lea     rbp, [rsp-1B0h]
0x18003a664  sub     rsp, 2B0h
0x18003a66b  mov     rax, cs:__security_cookie
0x18003a672  xor     rax, rsp
0x18003a675  mov     [rbp+1D0h+var_30], rax
0x18003a67c  mov     r14, r8
0x18003a67f  mov     rsi, rcx
0x18003a682  xor     r15d, r15d
0x18003a685  test    rdx, rdx
0x18003a688  jz      short loc_18003A68D
0x18003a68a  mov     [rdx], r15
0x18003a68d  test    r14, r14
0x18003a690  jnz     short loc_18003A6C4
0x18003a692  mov     rcx, [rbp+1D8h]; this
0x18003a699  lea     rax, aPfisdetectedIs; "pfIsDetected is null"
0x18003a6a0  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x18003a6a5  mov     ebx, 80004003h
0x18003a6aa  mov     r9d, ebx; char *
0x18003a6ad  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003a6b4  lea     edx, [r14+73h]; void *
0x18003a6b8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a6bd  mov     eax, ebx
0x18003a6bf  jmp     loc_18003AF9B
0x18003a6c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl(void)'::`2'::impl
0x18003a6cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(void)
0x18003a6d0  test    al, al
0x18003a6d2  jz      short loc_18003A70D
0x18003a6d4  mov     [rsp+2D0h+var_28F], r15b
0x18003a6d9  lea     rdx, [rsp+2D0h+var_28F]; bool *
0x18003a6de  mov     rcx, rsi; this
0x18003a6e1  call    ?IsManualRemediationApplicable@CRemediationPluginBase@WaasMedic@@IEAAJAEA_N@Z; WaasMedic::CRemediationPluginBase::IsManualRemediationApplicable(bool &)
0x18003a6e6  test    eax, eax
0x18003a6e8  js      short loc_18003A70D
0x18003a6ea  cmp     [rsp+2D0h+var_28F], r15b
0x18003a6ef  jz      short loc_18003A70D
0x18003a6f1  mov     byte ptr [r14], 1
0x18003a6f5  lea     rdx, aPluginBypassin; "Plugin bypassing detection due to manua"...
0x18003a6fc  mov     ecx, 4; unsigned __int8
0x18003a701  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a706  xor     eax, eax
0x18003a708  jmp     loc_18003AF9B
0x18003a70d  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x18003a712  call    cs:__imp_VariantInit
0x18003a718  nop
0x18003a719  mov     [rsp+2D0h+var_28F], r15b
0x18003a71e  mov     [rsp+2D0h+var_290], r15b
0x18003a723  xor     eax, eax
0x18003a725  mov     [rsp+2D0h+var_260], rax
0x18003a72a  xorps   xmm1, xmm1
0x18003a72d  movdqu  [rsp+2D0h+var_270], xmm1
0x18003a733  mov     byte ptr [rsp+2D0h+var_260], r15b
0x18003a738  lea     rcx, aIsstackdatares; "IsStackDataResetForcedDetected"
0x18003a73f  call    ?IsTestKeyEnabled@MiscUtil@WaasMedic@@SA_NPEBGK@Z; WaasMedic::MiscUtil::IsTestKeyEnabled(ushort const *,ulong)
0x18003a744  test    al, al
0x18003a746  jz      short loc_18003A789
0x18003a748  call    ?IsTestSigningEnabled@WaasMedic@@YA_NXZ; WaasMedic::IsTestSigningEnabled(void)
0x18003a74d  test    al, al
0x18003a74f  jz      short loc_18003A789
0x18003a751  lea     r8, aIsstackdatares; "IsStackDataResetForcedDetected"
0x18003a758  lea     rdx, aTesthookSetS; "TestHook set: %s."
0x18003a75f  mov     ecx, 3; unsigned __int8
0x18003a764  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a769  mov     byte ptr [r14], 1
0x18003a76d  mov     rcx, qword ptr [rsp+2D0h+var_270+8]
0x18003a772  test    rcx, rcx
0x18003a775  jz      short loc_18003A784
0x18003a777  mov     rax, [rcx]
0x18003a77a  mov     rax, [rax+10h]
0x18003a77e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a783  nop
0x18003a784  jmp     loc_18003AF74
0x18003a789  mov     [r14], r15b
0x18003a78c  xor     edx, edx; Val
0x18003a78e  mov     r8d, 208h; Size
0x18003a794  lea     rcx, [rbp+1D0h+pszPath]; void *
0x18003a798  call    memset_0
0x18003a79d  mov     [rsp+2D0h+lpMem], r15
0x18003a7a2  lea     rdx, [rsp+2D0h+lpMem]; unsigned __int16 *
0x18003a7a7  lea     rcx, aWindirSoftware_0; "%windir%\\SoftwareDistribution\\DataSto"...
0x18003a7ae  call    ?SafeExpandEnvironmentString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeExpandEnvironmentString(ushort const *,ushort * *)
0x18003a7b3  mov     edi, eax
0x18003a7b5  test    eax, eax
0x18003a7b7  jns     short loc_18003A7DB
0x18003a7b9  mov     rcx, [rbp+1D8h]; this
0x18003a7c0  mov     r9d, eax; char *
0x18003a7c3  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003a7ca  mov     edx, 323h; void *
0x18003a7cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a7d4  mov     rbx, [rsp+2D0h+lpMem]
0x18003a7d9  jmp     short loc_18003A829
0x18003a7db  lea     rax, aDatastoreEdb; "DataStore.edb"
0x18003a7e2  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x18003a7e7  mov     rbx, [rsp+2D0h+lpMem]
0x18003a7ec  mov     r9, rbx
0x18003a7ef  lea     r8, aSS; "%s\\%s"
0x18003a7f6  mov     edx, 104h; unsigned __int64
0x18003a7fb  lea     rcx, [rbp+1D0h+pszPath]; unsigned __int16 *
0x18003a7ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a804  mov     edi, eax
0x18003a806  test    eax, eax
0x18003a808  jns     loc_18003A89D
0x18003a80e  mov     rcx, [rbp+1D8h]; this
0x18003a815  mov     r9d, eax; char *
0x18003a818  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003a81f  mov     edx, 325h; void *
0x18003a824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a829  test    rbx, rbx
0x18003a82c  jz      short loc_18003A842
0x18003a82e  call    cs:__imp_GetProcessHeap
0x18003a834  mov     r8, rbx; lpMem
0x18003a837  xor     edx, edx; dwFlags
0x18003a839  mov     rcx, rax; hHeap
0x18003a83c  call    cs:__imp_HeapFree
0x18003a842  mov     rcx, [rbp+1D8h]; this
0x18003a849  lea     rax, aFailedToDeterm_4; "Failed to determine if datastore is pre"...
0x18003a850  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x18003a855  mov     r9d, edi; char *
0x18003a858  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003a85f  mov     edx, 92h; void *
0x18003a864  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a869  nop
0x18003a86a  mov     rcx, qword ptr [rsp+2D0h+var_270+8]
0x18003a86f  test    rcx, rcx
0x18003a872  jz      short loc_18003A881
0x18003a874  mov     rax, [rcx]
0x18003a877  mov     rax, [rax+10h]
0x18003a87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a880  nop
0x18003a881  mov     rcx, qword ptr [rsp+2D0h+var_270]
0x18003a886  test    rcx, rcx
0x18003a889  jz      short loc_18003A898
0x18003a88b  mov     rax, [rcx]
0x18003a88e  mov     rax, [rax+10h]
0x18003a892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a897  nop
0x18003a898  jmp     loc_18003AF8E
0x18003a89d  lea     rcx, [rbp+1D0h+pszPath]; pszPath
0x18003a8a1  call    cs:__imp_PathFileExistsW
0x18003a8a7  test    eax, eax
0x18003a8a9  setnz   dil
0x18003a8ad  test    rbx, rbx
0x18003a8b0  jz      short loc_18003A8C6
0x18003a8b2  call    cs:__imp_GetProcessHeap
0x18003a8b8  mov     rcx, rax; hHeap
0x18003a8bb  mov     r8, rbx; lpMem
0x18003a8be  xor     edx, edx; dwFlags
0x18003a8c0  call    cs:__imp_HeapFree
0x18003a8c6  test    dil, dil
0x18003a8c9  jnz     loc_18003A980
0x18003a8cf  lea     rdx, aDatastoreIsNot; "Datastore is not present on device. Not"...
0x18003a8d6  mov     ecx, 4; unsigned __int8
0x18003a8db  call    ?LogLevelA@@YAXEPEBDZZ; LogLevelA(uchar,char const *,...)
0x18003a8e0  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18003a8e5  mov     ecx, [rax]
0x18003a8e7  cmp     ecx, 5
0x18003a8ea  jbe     short loc_18003A964
0x18003a8ec  mov     r8, [rax+18h]
0x18003a8f0  mov     rcx, [rax+10h]
0x18003a8f4  mov     rdx, 400000000000h
0x18003a8fe  test    rdx, rcx
0x18003a901  jz      short loc_18003A964
0x18003a903  mov     rcx, r8
0x18003a906  and     rcx, rdx
0x18003a909  cmp     rcx, r8
0x18003a90c  jnz     short loc_18003A964
0x18003a90e  lea     rcx, aNodatastore; "NoDatastore"
0x18003a915  mov     [rsp+2D0h+lpMem], rcx
0x18003a91a  add     rsi, 78h ; 'x'
0x18003a91e  cmp     qword ptr [rsi+18h], 0Fh
0x18003a923  jbe     short loc_18003A928
0x18003a925  mov     rsi, [rsi]
0x18003a928  mov     [rsp+2D0h+var_280], rsi
0x18003a92d  mov     [rsp+2D0h+var_278], 2000000h
0x18003a936  lea     rcx, [rsp+2D0h+lpMem]
0x18003a93b  mov     [rsp+2D0h+var_2A0], rcx
0x18003a940  lea     rcx, [rsp+2D0h+var_280]
0x18003a945  mov     [rsp+2D0h+var_2A8], rcx
0x18003a94a  lea     rcx, [rsp+2D0h+var_278]
0x18003a94f  mov     qword ptr [rsp+2D0h+var_2B0], rcx
0x18003a954  lea     rdx, byte_180089A1F
0x18003a95b  mov     rcx, rax
0x18003a95e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003a963  nop
0x18003a964  mov     rcx, qword ptr [rsp+2D0h+var_270+8]
0x18003a969  test    rcx, rcx
0x18003a96c  jz      short loc_18003A97B
0x18003a96e  mov     rax, [rcx]
0x18003a971  mov     rax, [rax+10h]
0x18003a975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a97a  nop
0x18003a97b  jmp     loc_18003AF74
0x18003a980  lea     rcx, [rsp+2D0h+var_270]; this
0x18003a985  call    ?Initialize@UsoHelper@WaasMedic@@QEAAJXZ; WaasMedic::UsoHelper::Initialize(void)
0x18003a98a  mov     edi, eax
0x18003a98c  test    eax, eax
0x18003a98e  jns     short loc_18003A9EB
0x18003a990  mov     rcx, [rbp+1D8h]; this
0x18003a997  lea     rax, aUsoHelperFaile; "USO helper failed to initialize"
0x18003a99e  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x18003a9a3  mov     r9d, edi; char *
0x18003a9a6  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003a9ad  mov     edx, 9Ah; void *
0x18003a9b2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a9b7  nop
0x18003a9b8  mov     rcx, qword ptr [rsp+2D0h+var_270+8]
0x18003a9bd  test    rcx, rcx
0x18003a9c0  jz      short loc_18003A9CF
0x18003a9c2  mov     rax, [rcx]
0x18003a9c5  mov     rax, [rax+10h]
0x18003a9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9ce  nop
0x18003a9cf  mov     rcx, qword ptr [rsp+2D0h+var_270]
0x18003a9d4  test    rcx, rcx
0x18003a9d7  jz      short loc_18003A9E6
0x18003a9d9  mov     rax, [rcx]
0x18003a9dc  mov     rax, [rax+10h]
0x18003a9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9e5  nop
0x18003a9e6  jmp     loc_18003AF8E
0x18003a9eb  lea     rdx, [rsp+2D0h+var_28F]; bool *
0x18003a9f0  lea     rcx, [rsp+2D0h+var_270]; this
0x18003a9f5  call    ?RebootRequired@UsoHelper@WaasMedic@@QEAAJPEA_N@Z; WaasMedic::UsoHelper::RebootRequired(bool *)
0x18003a9fa  mov     edi, eax
0x18003a9fc  test    eax, eax
0x18003a9fe  jns     short loc_18003AA5B
0x18003aa00  mov     rcx, [rbp+1D8h]; this
0x18003aa07  lea     rax, aRebootrequired_0; "RebootRequired failed"
0x18003aa0e  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x18003aa13  mov     r9d, edi; char *
0x18003aa16  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003aa1d  mov     edx, 9Ch; void *
0x18003aa22  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003aa27  nop
0x18003aa28  mov     rcx, qword ptr [rsp+2D0h+var_270+8]
0x18003aa2d  test    rcx, rcx
0x18003aa30  jz      short loc_18003AA3F
0x18003aa32  mov     rax, [rcx]
0x18003aa35  mov     rax, [rax+10h]
0x18003aa39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa3e  nop
0x18003aa3f  mov     rcx, qword ptr [rsp+2D0h+var_270]
0x18003aa44  test    rcx, rcx
0x18003aa47  jz      short loc_18003AA56
0x18003aa49  mov     rax, [rcx]
0x18003aa4c  mov     rax, [rax+10h]
0x18003aa50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa55  nop
0x18003aa56  jmp     loc_18003AF8E
0x18003aa5b  cmp     [rsp+2D0h+var_28F], r15b
0x18003aa60  jz      loc_18003AB17
0x18003aa66  lea     rdx, aRebootIsRequir; "Reboot is required, blocking detection "...
0x18003aa6d  mov     ecx, 4; unsigned __int8
0x18003aa72  call    ?LogLevelA@@YAXEPEBDZZ; LogLevelA(uchar,char const *,...)
0x18003aa77  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18003aa7c  mov     ecx, [rax]
0x18003aa7e  cmp     ecx, 5
0x18003aa81  jbe     short loc_18003AAFB
0x18003aa83  mov     r8, [rax+18h]
0x18003aa87  mov     rcx, [rax+10h]
0x18003aa8b  mov     rdx, 400000000000h
0x18003aa95  test    rdx, rcx
0x18003aa98  jz      short loc_18003AAFB
0x18003aa9a  mov     rcx, r8
0x18003aa9d  and     rcx, rdx
0x18003aaa0  cmp     rcx, r8
0x18003aaa3  jnz     short loc_18003AAFB
0x18003aaa5  lea     rcx, aRebootrequired; "RebootRequired"
0x18003aaac  mov     [rsp+2D0h+var_278], rcx
0x18003aab1  add     rsi, 78h ; 'x'
0x18003aab5  cmp     qword ptr [rsi+18h], 0Fh
0x18003aaba  jbe     short loc_18003AABF
0x18003aabc  mov     rsi, [rsi]
0x18003aabf  mov     [rsp+2D0h+var_280], rsi
0x18003aac4  mov     [rsp+2D0h+lpMem], 2000000h
0x18003aacd  lea     rcx, [rsp+2D0h+var_278]
0x18003aad2  mov     [rsp+2D0h+var_2A0], rcx
0x18003aad7  lea     rcx, [rsp+2D0h+var_280]
0x18003aadc  mov     [rsp+2D0h+var_2A8], rcx
0x18003aae1  lea     rcx, [rsp+2D0h+lpMem]
0x18003aae6  mov     qword ptr [rsp+2D0h+var_2B0], rcx
0x18003aaeb  lea     rdx, word_1800899CE
0x18003aaf2  mov     rcx, rax
0x18003aaf5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003aafa  nop
0x18003aafb  mov     rcx, qword ptr [rsp+2D0h+var_270+8]
0x18003ab00  test    rcx, rcx
0x18003ab03  jz      short loc_18003AB12
0x18003ab05  mov     rax, [rcx]
0x18003ab08  mov     rax, [rax+10h]
0x18003ab0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab11  nop
0x18003ab12  jmp     loc_18003AF74
0x18003ab17  lea     rdx, [rsp+2D0h+var_290]; bool *
0x18003ab1c  lea     rcx, [rsp+2D0h+var_270]; this
  ... truncated ...
```
