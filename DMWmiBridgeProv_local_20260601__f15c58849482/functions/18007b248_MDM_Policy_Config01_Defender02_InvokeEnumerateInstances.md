# MDM_Policy_Config01_Defender02_InvokeEnumerateInstances

- ea: `0x18007b248`
- end: `0x18007c13d`
- name: `MDM_Policy_Config01_Defender02_InvokeEnumerateInstances`
- size: `3829`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a160`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180005400`
- `0x180005470`
- `0x1800054e0`
- `0x180005518`
- `0x1800056a0`
- `0x1800057b8`
- `0x1800057f0`
- `0x180005860`
- `0x1800059e8`
- `0x180005a20`
- `0x180005a58`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18007b248`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18007b55a`
- `msvcrt!_wtoi` at `0x18007b5a1`
- `msvcrt!_wtoi` at `0x18007b5e8`
- `msvcrt!_wtoi` at `0x18007b62f`
- `msvcrt!_wtoi` at `0x18007b676`
- `msvcrt!_wtoi` at `0x18007b6bd`
- `msvcrt!_wtoi` at `0x18007b704`
- `msvcrt!_wtoi` at `0x18007b74b`
- `msvcrt!_wtoi` at `0x18007b792`
- `msvcrt!_wtoi` at `0x18007b7d9`
- `msvcrt!_wtoi` at `0x18007b820`
- `msvcrt!_wtoi` at `0x18007b867`
- `msvcrt!_wtoi` at `0x18007b8ae`
- `msvcrt!_wtoi` at `0x18007b967`
- `msvcrt!_wtoi` at `0x18007b9ae`
- `msvcrt!_wtoi` at `0x18007b9f5`
- `msvcrt!_wtoi` at `0x18007ba3c`
- `msvcrt!_wtoi` at `0x18007baf5`
- `msvcrt!_wtoi` at `0x18007bb3c`
- `msvcrt!_wtoi` at `0x18007bb83`
- `msvcrt!_wtoi` at `0x18007bbca`
- `msvcrt!_wtoi` at `0x18007bc11`
- `msvcrt!_wtoi` at `0x18007bc58`
- `msvcrt!_wtoi` at `0x18007bd4a`
- `msvcrt!_wtoi` at `0x18007bd91`
- `msvcrt!_wtoi` at `0x18007bdd8`
- `msvcrt!_wtoi` at `0x18007be1f`
- `msvcrt!_wtoi` at `0x18007be66`
- `msvcrt!_wtoi` at `0x18007bead`
- `msvcrt!_wtoi` at `0x18007bf9f`
- `msvcrt!_wtoi` at `0x18007bfe6`
- `msvcrt!_wtoi` at `0x18007b55a`
- `msvcrt!_wtoi` at `0x18007b5a1`
- `msvcrt!_wtoi` at `0x18007b5e8`
- `msvcrt!_wtoi` at `0x18007b62f`
- `msvcrt!_wtoi` at `0x18007b676`
- `msvcrt!_wtoi` at `0x18007b6bd`
- `msvcrt!_wtoi` at `0x18007b704`
- `msvcrt!_wtoi` at `0x18007b74b`
- `msvcrt!_wtoi` at `0x18007b792`
- `msvcrt!_wtoi` at `0x18007b7d9`
- `msvcrt!_wtoi` at `0x18007b820`
- `msvcrt!_wtoi` at `0x18007b867`
- `msvcrt!_wtoi` at `0x18007b8ae`
- `msvcrt!_wtoi` at `0x18007b967`
- `msvcrt!_wtoi` at `0x18007b9ae`
- `msvcrt!_wtoi` at `0x18007b9f5`
- `msvcrt!_wtoi` at `0x18007ba3c`
- `msvcrt!_wtoi` at `0x18007baf5`
- `msvcrt!_wtoi` at `0x18007bb3c`
- `msvcrt!_wtoi` at `0x18007bb83`
- `msvcrt!_wtoi` at `0x18007bbca`
- `msvcrt!_wtoi` at `0x18007bc11`
- `msvcrt!_wtoi` at `0x18007bc58`
- `msvcrt!_wtoi` at `0x18007bd4a`
- `msvcrt!_wtoi` at `0x18007bd91`
- `msvcrt!_wtoi` at `0x18007bdd8`
- `msvcrt!_wtoi` at `0x18007be1f`
- `msvcrt!_wtoi` at `0x18007be66`
- `msvcrt!_wtoi` at `0x18007bead`
- `msvcrt!_wtoi` at `0x18007bf9f`
- `msvcrt!_wtoi` at `0x18007bfe6`

## string_xrefs

- `0x18007b76e`: `AllowOnAccessProtection`
- `0x18007b88a`: `AllowUserUIAccess`
- `0x18007ba5f`: `ControlledFolderAccessAllowedApplications`
- `0x18007ba98`: `ControlledFolderAccessProtectedFolders`
- `0x18007bba6`: `EnableControlledFolderAccess`
- `0x18007bc7b`: `ExcludedExtensions`
- `0x18007bcb4`: `ExcludedPaths`
- `0x18007bed0`: `SecurityIntelligenceLocation`
- `0x18007bf09`: `SignatureUpdateFallbackOrder`
- `0x18007bf42`: `SignatureUpdateFileSharesSources`
- `0x18007bf7b`: `SignatureUpdateInterval`
- `0x18007b49c`: `./Vendor/MSFT/Policy/Config`
- `0x18007b2c3`: `MDM_Policy_Config01_Defender02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Defender02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-2B8h] BYREF
  char v14; // [rsp+48h] [rbp-2B0h]
  _QWORD *v15; // [rsp+50h] [rbp-2A8h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-2A0h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-288h] BYREF
  char v18; // [rsp+80h] [rbp-278h]
  int v19; // [rsp+88h] [rbp-270h] BYREF
  char v20; // [rsp+8Ch] [rbp-26Ch]
  _BYTE v21[16]; // [rsp+90h] [rbp-268h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-258h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-248h] BYREF
  int v24; // [rsp+110h] [rbp-1E8h]
  char v25; // [rsp+114h] [rbp-1E4h]
  int v26; // [rsp+118h] [rbp-1E0h]
  char v27; // [rsp+11Ch] [rbp-1DCh]
  int v28; // [rsp+120h] [rbp-1D8h]
  char v29; // [rsp+124h] [rbp-1D4h]
  int v30; // [rsp+128h] [rbp-1D0h]
  char v31; // [rsp+12Ch] [rbp-1CCh]
  int v32; // [rsp+130h] [rbp-1C8h]
  char v33; // [rsp+134h] [rbp-1C4h]
  int v34; // [rsp+138h] [rbp-1C0h]
  char v35; // [rsp+13Ch] [rbp-1BCh]
  int v36; // [rsp+140h] [rbp-1B8h]
  char v37; // [rsp+144h] [rbp-1B4h]
  int v38; // [rsp+148h] [rbp-1B0h]
  char v39; // [rsp+14Ch] [rbp-1ACh]
  int v40; // [rsp+150h] [rbp-1A8h]
  char v41; // [rsp+154h] [rbp-1A4h]
  int v42; // [rsp+158h] [rbp-1A0h]
  char v43; // [rsp+15Ch] [rbp-19Ch]
  int v44; // [rsp+160h] [rbp-198h]
  char v45; // [rsp+164h] [rbp-194h]
  int v46; // [rsp+168h] [rbp-190h]
  char v47; // [rsp+16Ch] [rbp-18Ch]
  int v48; // [rsp+170h] [rbp-188h]
  char v49; // [rsp+174h] [rbp-184h]
  int v50; // [rsp+198h] [rbp-160h]
  char v51; // [rsp+19Ch] [rbp-15Ch]
  int v52; // [rsp+1A0h] [rbp-158h]
  char v53; // [rsp+1A4h] [rbp-154h]
  int v54; // [rsp+1A8h] [rbp-150h]
  char v55; // [rsp+1ACh] [rbp-14Ch]
  int v56; // [rsp+1B0h] [rbp-148h]
  char v57; // [rsp+1B4h] [rbp-144h]
  int v58; // [rsp+1D8h] [rbp-120h]
  char v59; // [rsp+1DCh] [rbp-11Ch]
  int v60; // [rsp+1E0h] [rbp-118h]
  char v61; // [rsp+1E4h] [rbp-114h]
  int v62; // [rsp+1E8h] [rbp-110h]
  char v63; // [rsp+1ECh] [rbp-10Ch]
  int v64; // [rsp+1F0h] [rbp-108h]
  char v65; // [rsp+1F4h] [rbp-104h]
  int v66; // [rsp+1F8h] [rbp-100h]
  char v67; // [rsp+1FCh] [rbp-FCh]
  int v68; // [rsp+200h] [rbp-F8h]
  char v69; // [rsp+204h] [rbp-F4h]
  int v70; // [rsp+238h] [rbp-C0h]
  char v71; // [rsp+23Ch] [rbp-BCh]
  int v72; // [rsp+240h] [rbp-B8h]
  char v73; // [rsp+244h] [rbp-B4h]
  int v74; // [rsp+248h] [rbp-B0h]
  char v75; // [rsp+24Ch] [rbp-ACh]
  int v76; // [rsp+250h] [rbp-A8h]
  char v77; // [rsp+254h] [rbp-A4h]
  int v78; // [rsp+258h] [rbp-A0h]
  char v79; // [rsp+25Ch] [rbp-9Ch]
  int v80; // [rsp+260h] [rbp-98h]
  char v81; // [rsp+264h] [rbp-94h]
  int v82; // [rsp+298h] [rbp-60h]
  char v83; // [rsp+29Ch] [rbp-5Ch]
  int v84; // [rsp+2A0h] [rbp-58h]
  char v85; // [rsp+2A4h] [rbp-54h]

  memset_0(&instance, 0, 0x208u);
  v14 = 0;
  String = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_Policy_Config01_Defender02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18036BED1,
      v21,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v16, v4);
  try
  {
    v15 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_Defender02_NodeList, 44, 2, &v15);
    if ( v7 == MI_RESULT_OK )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = (wil *)v15;
          if ( v15 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
        }
        else
        {
          v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = (wil *)v15;
            if ( v15 )
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(v8[33] - v8[32]) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Defender02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v15;
                if ( v15 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_175;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"Defender",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
              }
              if ( a2 != 1 )
              {
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowArchiveScanning",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowBehaviorMonitoring",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowCloudProtection",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowEmailScanning",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowFullScanOnMappedNetworkDrives",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowFullScanRemovableDriveScanning",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowIntrusionPreventionSystem",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowIOAVProtection",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowOnAccessProtection",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowRealtimeMonitoring",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowScanningNetworkFiles",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowScriptScanning",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowUserUIAccess",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AttackSurfaceReductionOnlyExclusions",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AttackSurfaceReductionRules",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AvgCPULoadFactor",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CheckForSignaturesBeforeRunningScan",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CloudBlockLevel",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CloudExtendedTimeout",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ControlledFolderAccessAllowedApplications",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ControlledFolderAccessProtectedFolders",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DaysToRetainCleanedMalware",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableCatchupFullScan",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableCatchupQuickScan",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableControlledFolderAccess",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableLowCPUPriority",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableNetworkProtection",
                        &String)
                  && String )
                {
                  v68 = _wtoi(String);
                  v69 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludedExtensions",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludedPaths",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludedProcesses",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_ConfigureEdgeRedirectChannel(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PUAProtection",
                        &String)
                  && String )
                {
                  v70 = _wtoi(String);
                  v71 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RealTimeScanDirection",
                        &String)
                  && String )
                {
                  v72 = _wtoi(String);
                  v73 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ScanParameter",
                        &String)
                  && String )
                {
                  v74 = _wtoi(String);
                  v75 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ScheduleQuickScanTime",
                        &String)
                  && String )
                {
                  v76 = _wtoi(String);
                  v77 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ScheduleScanDay",
                        &String)
                  && String )
                {
                  v78 = _wtoi(String);
                  v79 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ScheduleScanTime",
                        &String)
                  && String )
                {
                  v80 = _wtoi(String);
                  v81 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SecurityIntelligenceLocation",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCrashDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SignatureUpdateFallbackOrder",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCustomerExperienceImprovementProgramParticipation(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SignatureUpdateFileSharesSources",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_DisableDeletingUserVisitedWebsites(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SignatureUpdateInterval",
                        &String)
                  && String )
                {
                  v82 = _wtoi(String);
                  v83 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SubmitSamplesConsent",
                        &String)
                  && String )
                {
                  v84 = _wtoi(String);
                  v85 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ThreatSeverityDefaultAction",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_DisableFeedsBackgroundSync(&instance);
                }
              }
              MI_Instance_Destruct((MI_Instance *)self);
              MI_Instance_Destruct(&instance);
              v14 = 0;
            }
            v6 = (wil *)v15;
            if ( v15 )
            {
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = MI_RESULT_FAILED;
      }
    }
  }
  catch ( const exception *v17 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v17[0] + 8LL))(v17[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v16, v11);
    LODWORD(v15) = 1;
    goto LABEL_166;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_166:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (int)v15;
  }
LABEL_175:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_18033AEA8,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007b248  mov     [rsp+arg_8], rbx
0x18007b24d  mov     [rsp+arg_10], rsi
0x18007b252  push    rdi
0x18007b253  push    r12
0x18007b255  push    r13
0x18007b257  push    r14
0x18007b259  push    r15
0x18007b25b  sub     rsp, 2D0h
0x18007b262  mov     rax, cs:__security_cookie
0x18007b269  xor     rax, rsp
0x18007b26c  mov     [rsp+2F8h+var_38], rax
0x18007b274  mov     r13b, dl
0x18007b277  mov     r12, rcx
0x18007b27a  xor     edx, edx; Val
0x18007b27c  mov     r8d, 208h; Size
0x18007b282  lea     rcx, [rsp+2F8h+instance]; void *
0x18007b28a  call    memset_0
0x18007b28f  xor     edi, edi
0x18007b291  mov     [rsp+2F8h+var_2B0], dil
0x18007b296  mov     [rsp+2F8h+String], rdi
0x18007b29b  mov     [rsp+2F8h+var_270], edi
0x18007b2a2  mov     [rsp+2F8h+var_26C], dil
0x18007b2aa  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007b2b1  mov     [rsp+2F8h+var_2A0], rax
0x18007b2b6  lea     rax, [rsp+2F8h+var_270]
0x18007b2be  mov     [rsp+2F8h+var_298], rax
0x18007b2c3  lea     rax, aMdmPolicyConfi_40; "MDM_Policy_Config01_Defender02"
0x18007b2ca  mov     [rsp+2F8h+var_290], rax
0x18007b2cf  lea     rcx, [rsp+2F8h+var_270]
0x18007b2d7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007b2dc  mov     eax, cs:dword_180380B68
0x18007b2e2  cmp     eax, 5
0x18007b2e5  jbe     short loc_18007B357
0x18007b2e7  mov     rdx, 200000000000h
0x18007b2f1  lea     rcx, dword_180380B68
0x18007b2f8  call    _tlgKeywordOn
0x18007b2fd  test    al, al
0x18007b2ff  jz      short loc_18007B357
0x18007b301  cmp     [rsp+2F8h+var_26C], dil
0x18007b309  jz      short loc_18007B339
0x18007b30b  cmp     [rsp+2F8h+var_258], edi
0x18007b312  jnz     short loc_18007B32F
0x18007b314  cmp     [rsp+2F8h+var_254], edi
0x18007b31b  jnz     short loc_18007B32F
0x18007b31d  cmp     [rsp+2F8h+var_250], edi
0x18007b324  jnz     short loc_18007B32F
0x18007b326  cmp     [rsp+2F8h+var_24C], edi
0x18007b32d  jz      short loc_18007B339
0x18007b32f  lea     r9, [rsp+2F8h+var_258]
0x18007b337  jmp     short loc_18007B33C
0x18007b339  mov     r9, rdi
0x18007b33c  lea     r8, [rsp+2F8h+var_268]
0x18007b344  lea     rdx, byte_18036BED1
0x18007b34b  lea     rcx, dword_180380B68
0x18007b352  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007b357  lea     rcx, [rsp+2F8h+var_2A0]; this
0x18007b35c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18007b361  nop
0x18007b362  mov     [rsp+2F8h+var_2A8], rdi
0x18007b367  lea     rax, [rsp+2F8h+var_2A8]
0x18007b36c  mov     [rsp+2F8h+var_2C8], rax
0x18007b371  mov     [rsp+2F8h+var_2D0], 2
0x18007b379  mov     [rsp+2F8h+var_2D8], 2Ch ; ','
0x18007b381  lea     r9, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Defender02_NodeList
0x18007b388  xor     r8d, r8d
0x18007b38b  xor     edx, edx
0x18007b38d  mov     rcx, r12
0x18007b390  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007b395  mov     r15d, eax
0x18007b398  test    eax, eax
0x18007b39a  jz      short loc_18007B3A1
0x18007b39c  jmp     loc_18007C09C
0x18007b3a1  lea     rbx, [rsp+2F8h+var_2A8]
0x18007b3a6  mov     [rsp+2F8h+var_280], rbx
0x18007b3ab  mov     r14d, 1
0x18007b3b1  mov     [rsp+2F8h+var_278], r14b
0x18007b3b9  mov     rsi, [rsp+2F8h+var_2A8]
0x18007b3be  test    rsi, rsi
0x18007b3c1  jnz     short loc_18007B3CB
0x18007b3c3  mov     r15d, r14d
0x18007b3c6  jmp     loc_18007C09C
0x18007b3cb  mov     rax, [rsi]
0x18007b3ce  mov     rcx, rsi
0x18007b3d1  mov     rax, [rax+10h]
0x18007b3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b3da  mov     r15d, eax
0x18007b3dd  test    eax, eax
0x18007b3df  jz      short loc_18007B3FF
0x18007b3e1  mov     rcx, [rsp+2F8h+var_2A8]
0x18007b3e6  test    rcx, rcx
0x18007b3e9  jz      short loc_18007B3FA
0x18007b3eb  mov     rax, [rcx]
0x18007b3ee  mov     edx, r14d
0x18007b3f1  mov     rax, [rax]
0x18007b3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b3f9  nop
0x18007b3fa  jmp     loc_18007C09C
0x18007b3ff  mov     rax, [rsi]
0x18007b402  mov     rcx, rsi
0x18007b405  mov     rax, [rax+8]
0x18007b409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b40e  mov     r15d, eax
0x18007b411  test    eax, eax
0x18007b413  jz      short loc_18007B433
0x18007b415  mov     rcx, [rsp+2F8h+var_2A8]
0x18007b41a  test    rcx, rcx
0x18007b41d  jz      short loc_18007B42E
0x18007b41f  mov     rax, [rcx]
0x18007b422  mov     edx, r14d
0x18007b425  mov     rax, [rax]
0x18007b428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b42d  nop
0x18007b42e  jmp     loc_18007C09C
0x18007b433  mov     r14d, edi
0x18007b436  mov     rax, [rsi+108h]
0x18007b43d  sub     rax, [rsi+100h]
0x18007b444  sar     rax, 4
0x18007b448  cmp     r14d, eax
0x18007b44b  jnb     loc_18007C064
0x18007b451  lea     r8, [rsp+2F8h+instance]; instance
0x18007b459  lea     rdx, MDM_Policy_Config01_Defender02_rtti; classDecl
0x18007b460  mov     rcx, r12; context
0x18007b463  call    MI_Context_ConstructInstance
0x18007b468  mov     r15d, eax
0x18007b46b  test    eax, eax
0x18007b46d  jz      short loc_18007B48F
0x18007b46f  mov     rcx, [rbx]
0x18007b472  test    rcx, rcx
0x18007b475  jz      short loc_18007B48A
0x18007b477  mov     rax, [rcx]
0x18007b47a  mov     edx, 1
0x18007b47f  mov     rax, [rax]
0x18007b482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b487  mov     [rbx], rdi
0x18007b48a  jmp     loc_18007C09C
0x18007b48f  mov     [rsp+2F8h+var_2B0], 1
0x18007b494  mov     rax, [rsi]
0x18007b497  lea     r9, [rsp+2F8h+String]
0x18007b49c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18007b4a3  mov     edx, r14d
0x18007b4a6  mov     rcx, rsi
0x18007b4a9  mov     rax, [rax+18h]
0x18007b4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b4b2  test    eax, eax
0x18007b4b4  jnz     short loc_18007B4CD
0x18007b4b6  mov     rdx, [rsp+2F8h+String]
0x18007b4bb  test    rdx, rdx
0x18007b4be  jz      short loc_18007B4CD
0x18007b4c0  lea     rcx, [rsp+2F8h+instance]
0x18007b4c8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18007b4cd  mov     rax, [rsi]
0x18007b4d0  lea     r9, [rsp+2F8h+String]
0x18007b4d5  lea     r8, aDefender; "Defender"
0x18007b4dc  mov     edx, r14d
0x18007b4df  mov     rcx, rsi
0x18007b4e2  mov     rax, [rax+18h]
0x18007b4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b4eb  test    eax, eax
0x18007b4ed  jnz     short loc_18007B506
0x18007b4ef  mov     rdx, [rsp+2F8h+String]
0x18007b4f4  test    rdx, rdx
0x18007b4f7  jz      short loc_18007B506
0x18007b4f9  lea     rcx, [rsp+2F8h+instance]
0x18007b501  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18007b506  cmp     r13b, 1
0x18007b50a  jnz     short loc_18007B52E
0x18007b50c  lea     rdx, [rsp+2F8h+instance]
0x18007b514  mov     rcx, r12; self
0x18007b517  call    MI_Instance_Destruct
0x18007b51c  lea     rcx, [rsp+2F8h+instance]; self
0x18007b524  call    MI_Instance_Destruct
0x18007b529  jmp     loc_18007C057
0x18007b52e  mov     rax, [rsi]
0x18007b531  lea     r9, [rsp+2F8h+String]
0x18007b536  lea     r8, aAllowarchivesc; "AllowArchiveScanning"
0x18007b53d  mov     edx, r14d
0x18007b540  mov     rcx, rsi
0x18007b543  mov     rax, [rax+18h]
0x18007b547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b54c  test    eax, eax
0x18007b54e  jnz     short loc_18007B575
0x18007b550  mov     rcx, [rsp+2F8h+String]; String
0x18007b555  test    rcx, rcx
0x18007b558  jz      short loc_18007B575
0x18007b55a  call    cs:__imp__wtoi
0x18007b561  nop     dword ptr [rax+rax+00h]
0x18007b566  mov     [rsp+2F8h+var_1E8], eax
0x18007b56d  mov     [rsp+2F8h+var_1E4], 1
0x18007b575  mov     rax, [rsi]
0x18007b578  lea     r9, [rsp+2F8h+String]
0x18007b57d  lea     r8, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x18007b584  mov     edx, r14d
0x18007b587  mov     rcx, rsi
0x18007b58a  mov     rax, [rax+18h]
0x18007b58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b593  test    eax, eax
0x18007b595  jnz     short loc_18007B5BC
0x18007b597  mov     rcx, [rsp+2F8h+String]; String
0x18007b59c  test    rcx, rcx
0x18007b59f  jz      short loc_18007B5BC
0x18007b5a1  call    cs:__imp__wtoi
0x18007b5a8  nop     dword ptr [rax+rax+00h]
0x18007b5ad  mov     [rsp+2F8h+var_1E0], eax
0x18007b5b4  mov     [rsp+2F8h+var_1DC], 1
0x18007b5bc  mov     rax, [rsi]
0x18007b5bf  lea     r9, [rsp+2F8h+String]
0x18007b5c4  lea     r8, aAllowcloudprot; "AllowCloudProtection"
0x18007b5cb  mov     edx, r14d
0x18007b5ce  mov     rcx, rsi
0x18007b5d1  mov     rax, [rax+18h]
0x18007b5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b5da  test    eax, eax
0x18007b5dc  jnz     short loc_18007B603
0x18007b5de  mov     rcx, [rsp+2F8h+String]; String
0x18007b5e3  test    rcx, rcx
0x18007b5e6  jz      short loc_18007B603
0x18007b5e8  call    cs:__imp__wtoi
0x18007b5ef  nop     dword ptr [rax+rax+00h]
0x18007b5f4  mov     [rsp+2F8h+var_1D8], eax
0x18007b5fb  mov     [rsp+2F8h+var_1D4], 1
0x18007b603  mov     rax, [rsi]
0x18007b606  lea     r9, [rsp+2F8h+String]
0x18007b60b  lea     r8, aAllowemailscan; "AllowEmailScanning"
0x18007b612  mov     edx, r14d
0x18007b615  mov     rcx, rsi
0x18007b618  mov     rax, [rax+18h]
0x18007b61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b621  test    eax, eax
0x18007b623  jnz     short loc_18007B64A
0x18007b625  mov     rcx, [rsp+2F8h+String]; String
0x18007b62a  test    rcx, rcx
0x18007b62d  jz      short loc_18007B64A
0x18007b62f  call    cs:__imp__wtoi
0x18007b636  nop     dword ptr [rax+rax+00h]
0x18007b63b  mov     [rsp+2F8h+var_1D0], eax
0x18007b642  mov     [rsp+2F8h+var_1CC], 1
0x18007b64a  mov     rax, [rsi]
0x18007b64d  lea     r9, [rsp+2F8h+String]
0x18007b652  lea     r8, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x18007b659  mov     edx, r14d
0x18007b65c  mov     rcx, rsi
0x18007b65f  mov     rax, [rax+18h]
0x18007b663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b668  test    eax, eax
0x18007b66a  jnz     short loc_18007B691
0x18007b66c  mov     rcx, [rsp+2F8h+String]; String
0x18007b671  test    rcx, rcx
0x18007b674  jz      short loc_18007B691
0x18007b676  call    cs:__imp__wtoi
0x18007b67d  nop     dword ptr [rax+rax+00h]
0x18007b682  mov     [rsp+2F8h+var_1C8], eax
0x18007b689  mov     [rsp+2F8h+var_1C4], 1
0x18007b691  mov     rax, [rsi]
0x18007b694  lea     r9, [rsp+2F8h+String]
0x18007b699  lea     r8, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x18007b6a0  mov     edx, r14d
0x18007b6a3  mov     rcx, rsi
0x18007b6a6  mov     rax, [rax+18h]
0x18007b6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6af  test    eax, eax
0x18007b6b1  jnz     short loc_18007B6D8
0x18007b6b3  mov     rcx, [rsp+2F8h+String]; String
0x18007b6b8  test    rcx, rcx
0x18007b6bb  jz      short loc_18007B6D8
0x18007b6bd  call    cs:__imp__wtoi
0x18007b6c4  nop     dword ptr [rax+rax+00h]
0x18007b6c9  mov     [rsp+2F8h+var_1C0], eax
0x18007b6d0  mov     [rsp+2F8h+var_1BC], 1
0x18007b6d8  mov     rax, [rsi]
0x18007b6db  lea     r9, [rsp+2F8h+String]
0x18007b6e0  lea     r8, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x18007b6e7  mov     edx, r14d
0x18007b6ea  mov     rcx, rsi
0x18007b6ed  mov     rax, [rax+18h]
0x18007b6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6f6  test    eax, eax
0x18007b6f8  jnz     short loc_18007B71F
0x18007b6fa  mov     rcx, [rsp+2F8h+String]; String
0x18007b6ff  test    rcx, rcx
0x18007b702  jz      short loc_18007B71F
0x18007b704  call    cs:__imp__wtoi
0x18007b70b  nop     dword ptr [rax+rax+00h]
0x18007b710  mov     [rsp+2F8h+var_1B8], eax
0x18007b717  mov     [rsp+2F8h+var_1B4], 1
0x18007b71f  mov     rax, [rsi]
0x18007b722  lea     r9, [rsp+2F8h+String]
0x18007b727  lea     r8, aAllowioavprote; "AllowIOAVProtection"
0x18007b72e  mov     edx, r14d
0x18007b731  mov     rcx, rsi
0x18007b734  mov     rax, [rax+18h]
0x18007b738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b73d  test    eax, eax
0x18007b73f  jnz     short loc_18007B766
0x18007b741  mov     rcx, [rsp+2F8h+String]; String
0x18007b746  test    rcx, rcx
0x18007b749  jz      short loc_18007B766
0x18007b74b  call    cs:__imp__wtoi
0x18007b752  nop     dword ptr [rax+rax+00h]
0x18007b757  mov     [rsp+2F8h+var_1B0], eax
0x18007b75e  mov     [rsp+2F8h+var_1AC], 1
  ... truncated ...
```
