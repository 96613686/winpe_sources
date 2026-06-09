# MDM_Policy_Result01_Defender02_InvokeEnumerateInstances

- ea: `0x180132c58`
- end: `0x180133b4d`
- name: `MDM_Policy_Result01_Defender02_InvokeEnumerateInstances`
- size: `3829`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180131b70`

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
- `0x180132c58`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180132f6a`
- `msvcrt!_wtoi` at `0x180132fb1`
- `msvcrt!_wtoi` at `0x180132ff8`
- `msvcrt!_wtoi` at `0x18013303f`
- `msvcrt!_wtoi` at `0x180133086`
- `msvcrt!_wtoi` at `0x1801330cd`
- `msvcrt!_wtoi` at `0x180133114`
- `msvcrt!_wtoi` at `0x18013315b`
- `msvcrt!_wtoi` at `0x1801331a2`
- `msvcrt!_wtoi` at `0x1801331e9`
- `msvcrt!_wtoi` at `0x180133230`
- `msvcrt!_wtoi` at `0x180133277`
- `msvcrt!_wtoi` at `0x1801332be`
- `msvcrt!_wtoi` at `0x180133377`
- `msvcrt!_wtoi` at `0x1801333be`
- `msvcrt!_wtoi` at `0x180133405`
- `msvcrt!_wtoi` at `0x18013344c`
- `msvcrt!_wtoi` at `0x180133505`
- `msvcrt!_wtoi` at `0x18013354c`
- `msvcrt!_wtoi` at `0x180133593`
- `msvcrt!_wtoi` at `0x1801335da`
- `msvcrt!_wtoi` at `0x180133621`
- `msvcrt!_wtoi` at `0x180133668`
- `msvcrt!_wtoi` at `0x18013375a`
- `msvcrt!_wtoi` at `0x1801337a1`
- `msvcrt!_wtoi` at `0x1801337e8`
- `msvcrt!_wtoi` at `0x18013382f`
- `msvcrt!_wtoi` at `0x180133876`
- `msvcrt!_wtoi` at `0x1801338bd`
- `msvcrt!_wtoi` at `0x1801339af`
- `msvcrt!_wtoi` at `0x1801339f6`
- `msvcrt!_wtoi` at `0x180132f6a`
- `msvcrt!_wtoi` at `0x180132fb1`
- `msvcrt!_wtoi` at `0x180132ff8`
- `msvcrt!_wtoi` at `0x18013303f`
- `msvcrt!_wtoi` at `0x180133086`
- `msvcrt!_wtoi` at `0x1801330cd`
- `msvcrt!_wtoi` at `0x180133114`
- `msvcrt!_wtoi` at `0x18013315b`
- `msvcrt!_wtoi` at `0x1801331a2`
- `msvcrt!_wtoi` at `0x1801331e9`
- `msvcrt!_wtoi` at `0x180133230`
- `msvcrt!_wtoi` at `0x180133277`
- `msvcrt!_wtoi` at `0x1801332be`
- `msvcrt!_wtoi` at `0x180133377`
- `msvcrt!_wtoi` at `0x1801333be`
- `msvcrt!_wtoi` at `0x180133405`
- `msvcrt!_wtoi` at `0x18013344c`
- `msvcrt!_wtoi` at `0x180133505`
- `msvcrt!_wtoi` at `0x18013354c`
- `msvcrt!_wtoi` at `0x180133593`
- `msvcrt!_wtoi` at `0x1801335da`
- `msvcrt!_wtoi` at `0x180133621`
- `msvcrt!_wtoi` at `0x180133668`
- `msvcrt!_wtoi` at `0x18013375a`
- `msvcrt!_wtoi` at `0x1801337a1`
- `msvcrt!_wtoi` at `0x1801337e8`
- `msvcrt!_wtoi` at `0x18013382f`
- `msvcrt!_wtoi` at `0x180133876`
- `msvcrt!_wtoi` at `0x1801338bd`
- `msvcrt!_wtoi` at `0x1801339af`
- `msvcrt!_wtoi` at `0x1801339f6`

## string_xrefs

- `0x18013317e`: `AllowOnAccessProtection`
- `0x18013329a`: `AllowUserUIAccess`
- `0x18013346f`: `ControlledFolderAccessAllowedApplications`
- `0x1801334a8`: `ControlledFolderAccessProtectedFolders`
- `0x1801335b6`: `EnableControlledFolderAccess`
- `0x18013368b`: `ExcludedExtensions`
- `0x1801336c4`: `ExcludedPaths`
- `0x1801338e0`: `SecurityIntelligenceLocation`
- `0x180133919`: `SignatureUpdateFallbackOrder`
- `0x180133952`: `SignatureUpdateFileSharesSources`
- `0x18013398b`: `SignatureUpdateInterval`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Defender02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r15d
  _QWORD *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-2B8h] BYREF
  char v11; // [rsp+48h] [rbp-2B0h]
  _QWORD *v12; // [rsp+50h] [rbp-2A8h] BYREF
  _QWORD v13[5]; // [rsp+58h] [rbp-2A0h] BYREF
  char v14; // [rsp+80h] [rbp-278h]
  int v15; // [rsp+88h] [rbp-270h] BYREF
  char v16; // [rsp+8Ch] [rbp-26Ch]
  _BYTE v17[16]; // [rsp+90h] [rbp-268h] BYREF
  _DWORD v18[4]; // [rsp+A0h] [rbp-258h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-248h] BYREF
  int v20; // [rsp+110h] [rbp-1E8h]
  char v21; // [rsp+114h] [rbp-1E4h]
  int v22; // [rsp+118h] [rbp-1E0h]
  char v23; // [rsp+11Ch] [rbp-1DCh]
  int v24; // [rsp+120h] [rbp-1D8h]
  char v25; // [rsp+124h] [rbp-1D4h]
  int v26; // [rsp+128h] [rbp-1D0h]
  char v27; // [rsp+12Ch] [rbp-1CCh]
  int v28; // [rsp+130h] [rbp-1C8h]
  char v29; // [rsp+134h] [rbp-1C4h]
  int v30; // [rsp+138h] [rbp-1C0h]
  char v31; // [rsp+13Ch] [rbp-1BCh]
  int v32; // [rsp+140h] [rbp-1B8h]
  char v33; // [rsp+144h] [rbp-1B4h]
  int v34; // [rsp+148h] [rbp-1B0h]
  char v35; // [rsp+14Ch] [rbp-1ACh]
  int v36; // [rsp+150h] [rbp-1A8h]
  char v37; // [rsp+154h] [rbp-1A4h]
  int v38; // [rsp+158h] [rbp-1A0h]
  char v39; // [rsp+15Ch] [rbp-19Ch]
  int v40; // [rsp+160h] [rbp-198h]
  char v41; // [rsp+164h] [rbp-194h]
  int v42; // [rsp+168h] [rbp-190h]
  char v43; // [rsp+16Ch] [rbp-18Ch]
  int v44; // [rsp+170h] [rbp-188h]
  char v45; // [rsp+174h] [rbp-184h]
  int v46; // [rsp+198h] [rbp-160h]
  char v47; // [rsp+19Ch] [rbp-15Ch]
  int v48; // [rsp+1A0h] [rbp-158h]
  char v49; // [rsp+1A4h] [rbp-154h]
  int v50; // [rsp+1A8h] [rbp-150h]
  char v51; // [rsp+1ACh] [rbp-14Ch]
  int v52; // [rsp+1B0h] [rbp-148h]
  char v53; // [rsp+1B4h] [rbp-144h]
  int v54; // [rsp+1D8h] [rbp-120h]
  char v55; // [rsp+1DCh] [rbp-11Ch]
  int v56; // [rsp+1E0h] [rbp-118h]
  char v57; // [rsp+1E4h] [rbp-114h]
  int v58; // [rsp+1E8h] [rbp-110h]
  char v59; // [rsp+1ECh] [rbp-10Ch]
  int v60; // [rsp+1F0h] [rbp-108h]
  char v61; // [rsp+1F4h] [rbp-104h]
  int v62; // [rsp+1F8h] [rbp-100h]
  char v63; // [rsp+1FCh] [rbp-FCh]
  int v64; // [rsp+200h] [rbp-F8h]
  char v65; // [rsp+204h] [rbp-F4h]
  int v66; // [rsp+238h] [rbp-C0h]
  char v67; // [rsp+23Ch] [rbp-BCh]
  int v68; // [rsp+240h] [rbp-B8h]
  char v69; // [rsp+244h] [rbp-B4h]
  int v70; // [rsp+248h] [rbp-B0h]
  char v71; // [rsp+24Ch] [rbp-ACh]
  int v72; // [rsp+250h] [rbp-A8h]
  char v73; // [rsp+254h] [rbp-A4h]
  int v74; // [rsp+258h] [rbp-A0h]
  char v75; // [rsp+25Ch] [rbp-9Ch]
  int v76; // [rsp+260h] [rbp-98h]
  char v77; // [rsp+264h] [rbp-94h]
  int v78; // [rsp+298h] [rbp-60h]
  char v79; // [rsp+29Ch] [rbp-5Ch]
  int v80; // [rsp+2A0h] [rbp-58h]
  char v81; // [rsp+2A4h] [rbp-54h]

  memset_0(&instance, 0, 0x208u);
  v11 = 0;
  String = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = &TelemetryEventWriter::`vftable';
  v13[1] = &v15;
  v13[2] = "MDM_Policy_Result01_Defender02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v5 = v18;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_1803562CD,
      v17,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v13, v4);
  v12 = 0;
  v6 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Result01_Defender02_NodeList, 44, 2, &v12);
  if ( v6 == MI_RESULT_OK )
  {
    v13[4] = &v12;
    v14 = 1;
    v7 = v12;
    if ( v12 )
    {
      v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
      if ( v6 )
      {
        if ( v12 )
          (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
      }
      else
      {
        v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v12 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(v7[33] - v7[32]) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Defender02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_164;
            }
            v11 = 1;
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"Defender",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
            }
            if ( a2 != 1 )
            {
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowArchiveScanning",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowBehaviorMonitoring",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowCloudProtection",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowEmailScanning",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowFullScanOnMappedNetworkDrives",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowFullScanRemovableDriveScanning",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowIntrusionPreventionSystem",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowIOAVProtection",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowOnAccessProtection",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowRealtimeMonitoring",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowScanningNetworkFiles",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowScriptScanning",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowUserUIAccess",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AttackSurfaceReductionOnlyExclusions",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AttackSurfaceReductionRules",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AvgCPULoadFactor",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"CheckForSignaturesBeforeRunningScan",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"CloudBlockLevel",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"CloudExtendedTimeout",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ControlledFolderAccessAllowedApplications",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ControlledFolderAccessProtectedFolders",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DaysToRetainCleanedMalware",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableCatchupFullScan",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableCatchupQuickScan",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"EnableControlledFolderAccess",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"EnableLowCPUPriority",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"EnableNetworkProtection",
                      &String)
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludedExtensions",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludedPaths",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludedProcesses",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_ConfigureEdgeRedirectChannel(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PUAProtection",
                      &String)
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RealTimeScanDirection",
                      &String)
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ScanParameter",
                      &String)
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ScheduleQuickScanTime",
                      &String)
                && String )
              {
                v72 = _wtoi(String);
                v73 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ScheduleScanDay",
                      &String)
                && String )
              {
                v74 = _wtoi(String);
                v75 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ScheduleScanTime",
                      &String)
                && String )
              {
                v76 = _wtoi(String);
                v77 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"SecurityIntelligenceLocation",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCrashDetection(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"SignatureUpdateFallbackOrder",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCustomerExperienceImprovementProgramParticipation(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"SignatureUpdateFileSharesSources",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_DisableDeletingUserVisitedWebsites(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"SignatureUpdateInterval",
                      &String)
                && String )
              {
                v78 = _wtoi(String);
                v79 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"SubmitSamplesConsent",
                      &String)
                && String )
              {
                v80 = _wtoi(String);
                v81 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
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
            v11 = 0;
          }
          if ( v12 )
          {
            (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
            v12 = 0;
          }
        }
      }
    }
    else
    {
      v6 = MI_RESULT_FAILED;
    }
  }
LABEL_164:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v13, "EnumerateInstancesEnd", v6);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_18036E7F0,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180132c58  mov     [rsp+arg_8], rbx
0x180132c5d  mov     [rsp+arg_10], rsi
0x180132c62  push    rdi
0x180132c63  push    r12
0x180132c65  push    r13
0x180132c67  push    r14
0x180132c69  push    r15
0x180132c6b  sub     rsp, 2D0h
0x180132c72  mov     rax, cs:__security_cookie
0x180132c79  xor     rax, rsp
0x180132c7c  mov     [rsp+2F8h+var_38], rax
0x180132c84  mov     r13b, dl
0x180132c87  mov     r12, rcx
0x180132c8a  xor     edx, edx; Val
0x180132c8c  mov     r8d, 208h; Size
0x180132c92  lea     rcx, [rsp+2F8h+instance]; void *
0x180132c9a  call    memset_0
0x180132c9f  xor     edi, edi
0x180132ca1  mov     [rsp+2F8h+var_2B0], dil
0x180132ca6  mov     [rsp+2F8h+String], rdi
0x180132cab  mov     [rsp+2F8h+var_270], edi
0x180132cb2  mov     [rsp+2F8h+var_26C], dil
0x180132cba  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180132cc1  mov     [rsp+2F8h+var_2A0], rax
0x180132cc6  lea     rax, [rsp+2F8h+var_270]
0x180132cce  mov     [rsp+2F8h+var_298], rax
0x180132cd3  lea     rax, aMdmPolicyResul_181; "MDM_Policy_Result01_Defender02"
0x180132cda  mov     [rsp+2F8h+var_290], rax
0x180132cdf  lea     rcx, [rsp+2F8h+var_270]
0x180132ce7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180132cec  mov     eax, cs:dword_180380B68
0x180132cf2  cmp     eax, 5
0x180132cf5  jbe     short loc_180132D67
0x180132cf7  mov     rdx, 200000000000h
0x180132d01  lea     rcx, dword_180380B68
0x180132d08  call    _tlgKeywordOn
0x180132d0d  test    al, al
0x180132d0f  jz      short loc_180132D67
0x180132d11  cmp     [rsp+2F8h+var_26C], dil
0x180132d19  jz      short loc_180132D49
0x180132d1b  cmp     [rsp+2F8h+var_258], edi
0x180132d22  jnz     short loc_180132D3F
0x180132d24  cmp     [rsp+2F8h+var_254], edi
0x180132d2b  jnz     short loc_180132D3F
0x180132d2d  cmp     [rsp+2F8h+var_250], edi
0x180132d34  jnz     short loc_180132D3F
0x180132d36  cmp     [rsp+2F8h+var_24C], edi
0x180132d3d  jz      short loc_180132D49
0x180132d3f  lea     r9, [rsp+2F8h+var_258]
0x180132d47  jmp     short loc_180132D4C
0x180132d49  mov     r9, rdi
0x180132d4c  lea     r8, [rsp+2F8h+var_268]
0x180132d54  lea     rdx, byte_1803562CD
0x180132d5b  lea     rcx, dword_180380B68
0x180132d62  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180132d67  lea     rcx, [rsp+2F8h+var_2A0]; this
0x180132d6c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180132d71  nop
0x180132d72  mov     [rsp+2F8h+var_2A8], rdi
0x180132d77  lea     rax, [rsp+2F8h+var_2A8]
0x180132d7c  mov     [rsp+2F8h+var_2C8], rax
0x180132d81  mov     [rsp+2F8h+var_2D0], 2
0x180132d89  mov     [rsp+2F8h+var_2D8], 2Ch ; ','
0x180132d91  lea     r9, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Defender02_NodeList
0x180132d98  xor     r8d, r8d
0x180132d9b  xor     edx, edx
0x180132d9d  mov     rcx, r12
0x180132da0  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180132da5  mov     r15d, eax
0x180132da8  test    eax, eax
0x180132daa  jz      short loc_180132DB1
0x180132dac  jmp     loc_180133AAC
0x180132db1  lea     rbx, [rsp+2F8h+var_2A8]
0x180132db6  mov     [rsp+2F8h+var_280], rbx
0x180132dbb  mov     r14d, 1
0x180132dc1  mov     [rsp+2F8h+var_278], r14b
0x180132dc9  mov     rsi, [rsp+2F8h+var_2A8]
0x180132dce  test    rsi, rsi
0x180132dd1  jnz     short loc_180132DDB
0x180132dd3  mov     r15d, r14d
0x180132dd6  jmp     loc_180133AAC
0x180132ddb  mov     rax, [rsi]
0x180132dde  mov     rcx, rsi
0x180132de1  mov     rax, [rax+10h]
0x180132de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132dea  mov     r15d, eax
0x180132ded  test    eax, eax
0x180132def  jz      short loc_180132E0F
0x180132df1  mov     rcx, [rsp+2F8h+var_2A8]
0x180132df6  test    rcx, rcx
0x180132df9  jz      short loc_180132E0A
0x180132dfb  mov     rax, [rcx]
0x180132dfe  mov     edx, r14d
0x180132e01  mov     rax, [rax]
0x180132e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132e09  nop
0x180132e0a  jmp     loc_180133AAC
0x180132e0f  mov     rax, [rsi]
0x180132e12  mov     rcx, rsi
0x180132e15  mov     rax, [rax+8]
0x180132e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132e1e  mov     r15d, eax
0x180132e21  test    eax, eax
0x180132e23  jz      short loc_180132E43
0x180132e25  mov     rcx, [rsp+2F8h+var_2A8]
0x180132e2a  test    rcx, rcx
0x180132e2d  jz      short loc_180132E3E
0x180132e2f  mov     rax, [rcx]
0x180132e32  mov     edx, r14d
0x180132e35  mov     rax, [rax]
0x180132e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132e3d  nop
0x180132e3e  jmp     loc_180133AAC
0x180132e43  mov     r14d, edi
0x180132e46  mov     rax, [rsi+108h]
0x180132e4d  sub     rax, [rsi+100h]
0x180132e54  sar     rax, 4
0x180132e58  cmp     r14d, eax
0x180132e5b  jnb     loc_180133A74
0x180132e61  lea     r8, [rsp+2F8h+instance]; instance
0x180132e69  lea     rdx, MDM_Policy_Result01_Defender02_rtti; classDecl
0x180132e70  mov     rcx, r12; context
0x180132e73  call    MI_Context_ConstructInstance
0x180132e78  mov     r15d, eax
0x180132e7b  test    eax, eax
0x180132e7d  jz      short loc_180132E9F
0x180132e7f  mov     rcx, [rbx]
0x180132e82  test    rcx, rcx
0x180132e85  jz      short loc_180132E9A
0x180132e87  mov     rax, [rcx]
0x180132e8a  mov     edx, 1
0x180132e8f  mov     rax, [rax]
0x180132e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132e97  mov     [rbx], rdi
0x180132e9a  jmp     loc_180133AAC
0x180132e9f  mov     [rsp+2F8h+var_2B0], 1
0x180132ea4  mov     rax, [rsi]
0x180132ea7  lea     r9, [rsp+2F8h+String]
0x180132eac  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x180132eb3  mov     edx, r14d
0x180132eb6  mov     rcx, rsi
0x180132eb9  mov     rax, [rax+18h]
0x180132ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132ec2  test    eax, eax
0x180132ec4  jnz     short loc_180132EDD
0x180132ec6  mov     rdx, [rsp+2F8h+String]
0x180132ecb  test    rdx, rdx
0x180132ece  jz      short loc_180132EDD
0x180132ed0  lea     rcx, [rsp+2F8h+instance]
0x180132ed8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180132edd  mov     rax, [rsi]
0x180132ee0  lea     r9, [rsp+2F8h+String]
0x180132ee5  lea     r8, aDefender; "Defender"
0x180132eec  mov     edx, r14d
0x180132eef  mov     rcx, rsi
0x180132ef2  mov     rax, [rax+18h]
0x180132ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132efb  test    eax, eax
0x180132efd  jnz     short loc_180132F16
0x180132eff  mov     rdx, [rsp+2F8h+String]
0x180132f04  test    rdx, rdx
0x180132f07  jz      short loc_180132F16
0x180132f09  lea     rcx, [rsp+2F8h+instance]
0x180132f11  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180132f16  cmp     r13b, 1
0x180132f1a  jnz     short loc_180132F3E
0x180132f1c  lea     rdx, [rsp+2F8h+instance]
0x180132f24  mov     rcx, r12; self
0x180132f27  call    MI_Instance_Destruct
0x180132f2c  lea     rcx, [rsp+2F8h+instance]; self
0x180132f34  call    MI_Instance_Destruct
0x180132f39  jmp     loc_180133A67
0x180132f3e  mov     rax, [rsi]
0x180132f41  lea     r9, [rsp+2F8h+String]
0x180132f46  lea     r8, aAllowarchivesc; "AllowArchiveScanning"
0x180132f4d  mov     edx, r14d
0x180132f50  mov     rcx, rsi
0x180132f53  mov     rax, [rax+18h]
0x180132f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132f5c  test    eax, eax
0x180132f5e  jnz     short loc_180132F85
0x180132f60  mov     rcx, [rsp+2F8h+String]; String
0x180132f65  test    rcx, rcx
0x180132f68  jz      short loc_180132F85
0x180132f6a  call    cs:__imp__wtoi
0x180132f71  nop     dword ptr [rax+rax+00h]
0x180132f76  mov     [rsp+2F8h+var_1E8], eax
0x180132f7d  mov     [rsp+2F8h+var_1E4], 1
0x180132f85  mov     rax, [rsi]
0x180132f88  lea     r9, [rsp+2F8h+String]
0x180132f8d  lea     r8, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x180132f94  mov     edx, r14d
0x180132f97  mov     rcx, rsi
0x180132f9a  mov     rax, [rax+18h]
0x180132f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132fa3  test    eax, eax
0x180132fa5  jnz     short loc_180132FCC
0x180132fa7  mov     rcx, [rsp+2F8h+String]; String
0x180132fac  test    rcx, rcx
0x180132faf  jz      short loc_180132FCC
0x180132fb1  call    cs:__imp__wtoi
0x180132fb8  nop     dword ptr [rax+rax+00h]
0x180132fbd  mov     [rsp+2F8h+var_1E0], eax
0x180132fc4  mov     [rsp+2F8h+var_1DC], 1
0x180132fcc  mov     rax, [rsi]
0x180132fcf  lea     r9, [rsp+2F8h+String]
0x180132fd4  lea     r8, aAllowcloudprot; "AllowCloudProtection"
0x180132fdb  mov     edx, r14d
0x180132fde  mov     rcx, rsi
0x180132fe1  mov     rax, [rax+18h]
0x180132fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132fea  test    eax, eax
0x180132fec  jnz     short loc_180133013
0x180132fee  mov     rcx, [rsp+2F8h+String]; String
0x180132ff3  test    rcx, rcx
0x180132ff6  jz      short loc_180133013
0x180132ff8  call    cs:__imp__wtoi
0x180132fff  nop     dword ptr [rax+rax+00h]
0x180133004  mov     [rsp+2F8h+var_1D8], eax
0x18013300b  mov     [rsp+2F8h+var_1D4], 1
0x180133013  mov     rax, [rsi]
0x180133016  lea     r9, [rsp+2F8h+String]
0x18013301b  lea     r8, aAllowemailscan; "AllowEmailScanning"
0x180133022  mov     edx, r14d
0x180133025  mov     rcx, rsi
0x180133028  mov     rax, [rax+18h]
0x18013302c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133031  test    eax, eax
0x180133033  jnz     short loc_18013305A
0x180133035  mov     rcx, [rsp+2F8h+String]; String
0x18013303a  test    rcx, rcx
0x18013303d  jz      short loc_18013305A
0x18013303f  call    cs:__imp__wtoi
0x180133046  nop     dword ptr [rax+rax+00h]
0x18013304b  mov     [rsp+2F8h+var_1D0], eax
0x180133052  mov     [rsp+2F8h+var_1CC], 1
0x18013305a  mov     rax, [rsi]
0x18013305d  lea     r9, [rsp+2F8h+String]
0x180133062  lea     r8, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x180133069  mov     edx, r14d
0x18013306c  mov     rcx, rsi
0x18013306f  mov     rax, [rax+18h]
0x180133073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133078  test    eax, eax
0x18013307a  jnz     short loc_1801330A1
0x18013307c  mov     rcx, [rsp+2F8h+String]; String
0x180133081  test    rcx, rcx
0x180133084  jz      short loc_1801330A1
0x180133086  call    cs:__imp__wtoi
0x18013308d  nop     dword ptr [rax+rax+00h]
0x180133092  mov     [rsp+2F8h+var_1C8], eax
0x180133099  mov     [rsp+2F8h+var_1C4], 1
0x1801330a1  mov     rax, [rsi]
0x1801330a4  lea     r9, [rsp+2F8h+String]
0x1801330a9  lea     r8, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x1801330b0  mov     edx, r14d
0x1801330b3  mov     rcx, rsi
0x1801330b6  mov     rax, [rax+18h]
0x1801330ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801330bf  test    eax, eax
0x1801330c1  jnz     short loc_1801330E8
0x1801330c3  mov     rcx, [rsp+2F8h+String]; String
0x1801330c8  test    rcx, rcx
0x1801330cb  jz      short loc_1801330E8
0x1801330cd  call    cs:__imp__wtoi
0x1801330d4  nop     dword ptr [rax+rax+00h]
0x1801330d9  mov     [rsp+2F8h+var_1C0], eax
0x1801330e0  mov     [rsp+2F8h+var_1BC], 1
0x1801330e8  mov     rax, [rsi]
0x1801330eb  lea     r9, [rsp+2F8h+String]
0x1801330f0  lea     r8, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x1801330f7  mov     edx, r14d
0x1801330fa  mov     rcx, rsi
0x1801330fd  mov     rax, [rax+18h]
0x180133101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133106  test    eax, eax
0x180133108  jnz     short loc_18013312F
0x18013310a  mov     rcx, [rsp+2F8h+String]; String
0x18013310f  test    rcx, rcx
0x180133112  jz      short loc_18013312F
0x180133114  call    cs:__imp__wtoi
0x18013311b  nop     dword ptr [rax+rax+00h]
0x180133120  mov     [rsp+2F8h+var_1B8], eax
0x180133127  mov     [rsp+2F8h+var_1B4], 1
0x18013312f  mov     rax, [rsi]
0x180133132  lea     r9, [rsp+2F8h+String]
0x180133137  lea     r8, aAllowioavprote; "AllowIOAVProtection"
0x18013313e  mov     edx, r14d
0x180133141  mov     rcx, rsi
0x180133144  mov     rax, [rax+18h]
0x180133148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013314d  test    eax, eax
0x18013314f  jnz     short loc_180133176
0x180133151  mov     rcx, [rsp+2F8h+String]; String
0x180133156  test    rcx, rcx
0x180133159  jz      short loc_180133176
0x18013315b  call    cs:__imp__wtoi
0x180133162  nop     dword ptr [rax+rax+00h]
0x180133167  mov     [rsp+2F8h+var_1B0], eax
0x18013316e  mov     [rsp+2F8h+var_1AC], 1
  ... truncated ...
```
