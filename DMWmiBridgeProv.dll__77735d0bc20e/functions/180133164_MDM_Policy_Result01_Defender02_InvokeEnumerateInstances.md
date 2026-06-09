# MDM_Policy_Result01_Defender02_InvokeEnumerateInstances

- ea: `0x180133164`
- end: `0x180133f9e`
- name: `MDM_Policy_Result01_Defender02_InvokeEnumerateInstances`
- size: `3642`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180132060`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000522c`
- `0x18000529c`
- `0x18000530c`
- `0x180005344`
- `0x1800054cc`
- `0x1800055e4`
- `0x18000561c`
- `0x18000568c`
- `0x180005814`
- `0x18000584c`
- `0x180005884`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180133164`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180133476`
- `msvcrt!_wtoi` at `0x1801334b7`
- `msvcrt!_wtoi` at `0x1801334f8`
- `msvcrt!_wtoi` at `0x180133539`
- `msvcrt!_wtoi` at `0x18013357a`
- `msvcrt!_wtoi` at `0x1801335bb`
- `msvcrt!_wtoi` at `0x1801335fc`
- `msvcrt!_wtoi` at `0x18013363d`
- `msvcrt!_wtoi` at `0x18013367e`
- `msvcrt!_wtoi` at `0x1801336bf`
- `msvcrt!_wtoi` at `0x180133700`
- `msvcrt!_wtoi` at `0x180133741`
- `msvcrt!_wtoi` at `0x180133782`
- `msvcrt!_wtoi` at `0x180133835`
- `msvcrt!_wtoi` at `0x180133876`
- `msvcrt!_wtoi` at `0x1801338b7`
- `msvcrt!_wtoi` at `0x1801338f8`
- `msvcrt!_wtoi` at `0x1801339ab`
- `msvcrt!_wtoi` at `0x1801339ec`
- `msvcrt!_wtoi` at `0x180133a2d`
- `msvcrt!_wtoi` at `0x180133a6e`
- `msvcrt!_wtoi` at `0x180133aaf`
- `msvcrt!_wtoi` at `0x180133af0`
- `msvcrt!_wtoi` at `0x180133bdc`
- `msvcrt!_wtoi` at `0x180133c1d`
- `msvcrt!_wtoi` at `0x180133c5e`
- `msvcrt!_wtoi` at `0x180133c9f`
- `msvcrt!_wtoi` at `0x180133ce0`
- `msvcrt!_wtoi` at `0x180133d21`
- `msvcrt!_wtoi` at `0x180133e0d`
- `msvcrt!_wtoi` at `0x180133e4e`
- `msvcrt!_wtoi` at `0x180133476`
- `msvcrt!_wtoi` at `0x1801334b7`
- `msvcrt!_wtoi` at `0x1801334f8`
- `msvcrt!_wtoi` at `0x180133539`
- `msvcrt!_wtoi` at `0x18013357a`
- `msvcrt!_wtoi` at `0x1801335bb`
- `msvcrt!_wtoi` at `0x1801335fc`
- `msvcrt!_wtoi` at `0x18013363d`
- `msvcrt!_wtoi` at `0x18013367e`
- `msvcrt!_wtoi` at `0x1801336bf`
- `msvcrt!_wtoi` at `0x180133700`
- `msvcrt!_wtoi` at `0x180133741`
- `msvcrt!_wtoi` at `0x180133782`
- `msvcrt!_wtoi` at `0x180133835`
- `msvcrt!_wtoi` at `0x180133876`
- `msvcrt!_wtoi` at `0x1801338b7`
- `msvcrt!_wtoi` at `0x1801338f8`
- `msvcrt!_wtoi` at `0x1801339ab`
- `msvcrt!_wtoi` at `0x1801339ec`
- `msvcrt!_wtoi` at `0x180133a2d`
- `msvcrt!_wtoi` at `0x180133a6e`
- `msvcrt!_wtoi` at `0x180133aaf`
- `msvcrt!_wtoi` at `0x180133af0`
- `msvcrt!_wtoi` at `0x180133bdc`
- `msvcrt!_wtoi` at `0x180133c1d`
- `msvcrt!_wtoi` at `0x180133c5e`
- `msvcrt!_wtoi` at `0x180133c9f`
- `msvcrt!_wtoi` at `0x180133ce0`
- `msvcrt!_wtoi` at `0x180133d21`
- `msvcrt!_wtoi` at `0x180133e0d`
- `msvcrt!_wtoi` at `0x180133e4e`

## string_xrefs

- `0x18013365a`: `AllowOnAccessProtection`
- `0x18013375e`: `AllowUserUIAccess`
- `0x180133915`: `ControlledFolderAccessAllowedApplications`
- `0x18013394e`: `ControlledFolderAccessProtectedFolders`
- `0x180133a4a`: `EnableControlledFolderAccess`
- `0x180133b0d`: `ExcludedExtensions`
- `0x180133b46`: `ExcludedPaths`
- `0x180133d3e`: `SecurityIntelligenceLocation`
- `0x180133d77`: `SignatureUpdateFallbackOrder`
- `0x180133db0`: `SignatureUpdateFileSharesSources`
- `0x180133de9`: `SignatureUpdateInterval`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Defender02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r15d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-2B8h] BYREF
  char v11; // [rsp+48h] [rbp-2B0h]
  WmiRequestHandlerAdd *v12; // [rsp+50h] [rbp-2A8h] BYREF
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
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_Defender02_NodeList,
         0x2Cu,
         2,
         &v12);
  if ( !v6 )
  {
    v13[4] = &v12;
    v14 = 1;
    v7 = v12;
    if ( v12 )
    {
      v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v6 )
      {
        if ( v12 )
          (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v12 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v7 + 33) - *((_QWORD *)v7 + 32)) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Defender02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_164;
            }
            v11 = 1;
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
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
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowArchiveScanning",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowBehaviorMonitoring",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowCloudProtection",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowEmailScanning",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowFullScanOnMappedNetworkDrives",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowFullScanRemovableDriveScanning",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowIntrusionPreventionSystem",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowIOAVProtection",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowOnAccessProtection",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowRealtimeMonitoring",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowScanningNetworkFiles",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowScriptScanning",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowUserUIAccess",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AttackSurfaceReductionOnlyExclusions",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AttackSurfaceReductionRules",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AvgCPULoadFactor",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"CheckForSignaturesBeforeRunningScan",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"CloudBlockLevel",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"CloudExtendedTimeout",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ControlledFolderAccessAllowedApplications",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ControlledFolderAccessProtectedFolders",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DaysToRetainCleanedMalware",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableCatchupFullScan",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableCatchupQuickScan",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"EnableControlledFolderAccess",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"EnableLowCPUPriority",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"EnableNetworkProtection",
                      &String)
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludedExtensions",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludedPaths",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludedProcesses",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_ConfigureEdgeRedirectChannel(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PUAProtection",
                      &String)
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RealTimeScanDirection",
                      &String)
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ScanParameter",
                      &String)
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ScheduleQuickScanTime",
                      &String)
                && String )
              {
                v72 = _wtoi(String);
                v73 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ScheduleScanDay",
                      &String)
                && String )
              {
                v74 = _wtoi(String);
                v75 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ScheduleScanTime",
                      &String)
                && String )
              {
                v76 = _wtoi(String);
                v77 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"SecurityIntelligenceLocation",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCrashDetection(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"SignatureUpdateFallbackOrder",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCustomerExperienceImprovementProgramParticipation(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"SignatureUpdateFileSharesSources",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_DisableDeletingUserVisitedWebsites(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"SignatureUpdateInterval",
                      &String)
                && String )
              {
                v78 = _wtoi(String);
                v79 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"SubmitSamplesConsent",
                      &String)
                && String )
              {
                v80 = _wtoi(String);
                v81 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
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
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
            v12 = 0;
          }
        }
      }
    }
    else
    {
      v6 = 1;
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
  return v6;
}

```

## disassembly

```asm
0x180133164  mov     [rsp+arg_8], rbx
0x180133169  mov     [rsp+arg_10], rsi
0x18013316e  push    rdi
0x18013316f  push    r12
0x180133171  push    r13
0x180133173  push    r14
0x180133175  push    r15
0x180133177  sub     rsp, 2D0h
0x18013317e  mov     rax, cs:__security_cookie
0x180133185  xor     rax, rsp
0x180133188  mov     [rsp+2F8h+var_38], rax
0x180133190  mov     r13b, dl
0x180133193  mov     r12, rcx
0x180133196  xor     edx, edx; Val
0x180133198  mov     r8d, 208h; Size
0x18013319e  lea     rcx, [rsp+2F8h+instance]; void *
0x1801331a6  call    memset_0
0x1801331ab  xor     edi, edi
0x1801331ad  mov     [rsp+2F8h+var_2B0], dil
0x1801331b2  mov     [rsp+2F8h+String], rdi
0x1801331b7  mov     [rsp+2F8h+var_270], edi
0x1801331be  mov     [rsp+2F8h+var_26C], dil
0x1801331c6  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801331cd  mov     [rsp+2F8h+var_2A0], rax
0x1801331d2  lea     rax, [rsp+2F8h+var_270]
0x1801331da  mov     [rsp+2F8h+var_298], rax
0x1801331df  lea     rax, aMdmPolicyResul_181; "MDM_Policy_Result01_Defender02"
0x1801331e6  mov     [rsp+2F8h+var_290], rax
0x1801331eb  lea     rcx, [rsp+2F8h+var_270]
0x1801331f3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801331f8  mov     eax, cs:dword_180380B68
0x1801331fe  cmp     eax, 5
0x180133201  jbe     short loc_180133273
0x180133203  mov     rdx, 200000000000h
0x18013320d  lea     rcx, dword_180380B68
0x180133214  call    _tlgKeywordOn
0x180133219  test    al, al
0x18013321b  jz      short loc_180133273
0x18013321d  cmp     [rsp+2F8h+var_26C], dil
0x180133225  jz      short loc_180133255
0x180133227  cmp     [rsp+2F8h+var_258], edi
0x18013322e  jnz     short loc_18013324B
0x180133230  cmp     [rsp+2F8h+var_254], edi
0x180133237  jnz     short loc_18013324B
0x180133239  cmp     [rsp+2F8h+var_250], edi
0x180133240  jnz     short loc_18013324B
0x180133242  cmp     [rsp+2F8h+var_24C], edi
0x180133249  jz      short loc_180133255
0x18013324b  lea     r9, [rsp+2F8h+var_258]
0x180133253  jmp     short loc_180133258
0x180133255  mov     r9, rdi
0x180133258  lea     r8, [rsp+2F8h+var_268]
0x180133260  lea     rdx, byte_1803562CD
0x180133267  lea     rcx, dword_180380B68
0x18013326e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180133273  lea     rcx, [rsp+2F8h+var_2A0]; this
0x180133278  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18013327d  nop
0x18013327e  mov     [rsp+2F8h+var_2A8], rdi
0x180133283  lea     rax, [rsp+2F8h+var_2A8]
0x180133288  mov     [rsp+2F8h+var_2C8], rax
0x18013328d  mov     [rsp+2F8h+var_2D0], 2
0x180133295  mov     [rsp+2F8h+var_2D8], 2Ch ; ','
0x18013329d  lea     r9, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Defender02_NodeList
0x1801332a4  xor     r8d, r8d
0x1801332a7  xor     edx, edx
0x1801332a9  mov     rcx, r12
0x1801332ac  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801332b1  mov     r15d, eax
0x1801332b4  test    eax, eax
0x1801332b6  jz      short loc_1801332BD
0x1801332b8  jmp     loc_180133EFE
0x1801332bd  lea     rbx, [rsp+2F8h+var_2A8]
0x1801332c2  mov     [rsp+2F8h+var_280], rbx
0x1801332c7  mov     r14d, 1
0x1801332cd  mov     [rsp+2F8h+var_278], r14b
0x1801332d5  mov     rsi, [rsp+2F8h+var_2A8]
0x1801332da  test    rsi, rsi
0x1801332dd  jnz     short loc_1801332E7
0x1801332df  mov     r15d, r14d
0x1801332e2  jmp     loc_180133EFE
0x1801332e7  mov     rax, [rsi]
0x1801332ea  mov     rcx, rsi
0x1801332ed  mov     rax, [rax+10h]
0x1801332f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801332f6  mov     r15d, eax
0x1801332f9  test    eax, eax
0x1801332fb  jz      short loc_18013331B
0x1801332fd  mov     rcx, [rsp+2F8h+var_2A8]
0x180133302  test    rcx, rcx
0x180133305  jz      short loc_180133316
0x180133307  mov     rax, [rcx]
0x18013330a  mov     edx, r14d
0x18013330d  mov     rax, [rax]
0x180133310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133315  nop
0x180133316  jmp     loc_180133EFE
0x18013331b  mov     rax, [rsi]
0x18013331e  mov     rcx, rsi
0x180133321  mov     rax, [rax+8]
0x180133325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013332a  mov     r15d, eax
0x18013332d  test    eax, eax
0x18013332f  jz      short loc_18013334F
0x180133331  mov     rcx, [rsp+2F8h+var_2A8]
0x180133336  test    rcx, rcx
0x180133339  jz      short loc_18013334A
0x18013333b  mov     rax, [rcx]
0x18013333e  mov     edx, r14d
0x180133341  mov     rax, [rax]
0x180133344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133349  nop
0x18013334a  jmp     loc_180133EFE
0x18013334f  mov     r14d, edi
0x180133352  mov     rax, [rsi+108h]
0x180133359  sub     rax, [rsi+100h]
0x180133360  sar     rax, 4
0x180133364  cmp     r14d, eax
0x180133367  jnb     loc_180133EC6
0x18013336d  lea     r8, [rsp+2F8h+instance]; instance
0x180133375  lea     rdx, MDM_Policy_Result01_Defender02_rtti; classDecl
0x18013337c  mov     rcx, r12; context
0x18013337f  call    MI_Context_ConstructInstance
0x180133384  mov     r15d, eax
0x180133387  test    eax, eax
0x180133389  jz      short loc_1801333AB
0x18013338b  mov     rcx, [rbx]
0x18013338e  test    rcx, rcx
0x180133391  jz      short loc_1801333A6
0x180133393  mov     rax, [rcx]
0x180133396  mov     edx, 1
0x18013339b  mov     rax, [rax]
0x18013339e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801333a3  mov     [rbx], rdi
0x1801333a6  jmp     loc_180133EFE
0x1801333ab  mov     [rsp+2F8h+var_2B0], 1
0x1801333b0  mov     rax, [rsi]
0x1801333b3  lea     r9, [rsp+2F8h+String]
0x1801333b8  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x1801333bf  mov     edx, r14d
0x1801333c2  mov     rcx, rsi
0x1801333c5  mov     rax, [rax+18h]
0x1801333c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801333ce  test    eax, eax
0x1801333d0  jnz     short loc_1801333E9
0x1801333d2  mov     rdx, [rsp+2F8h+String]
0x1801333d7  test    rdx, rdx
0x1801333da  jz      short loc_1801333E9
0x1801333dc  lea     rcx, [rsp+2F8h+instance]
0x1801333e4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801333e9  mov     rax, [rsi]
0x1801333ec  lea     r9, [rsp+2F8h+String]
0x1801333f1  lea     r8, aDefender; "Defender"
0x1801333f8  mov     edx, r14d
0x1801333fb  mov     rcx, rsi
0x1801333fe  mov     rax, [rax+18h]
0x180133402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133407  test    eax, eax
0x180133409  jnz     short loc_180133422
0x18013340b  mov     rdx, [rsp+2F8h+String]
0x180133410  test    rdx, rdx
0x180133413  jz      short loc_180133422
0x180133415  lea     rcx, [rsp+2F8h+instance]
0x18013341d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180133422  cmp     r13b, 1
0x180133426  jnz     short loc_18013344A
0x180133428  lea     rdx, [rsp+2F8h+instance]
0x180133430  mov     rcx, r12; self
0x180133433  call    MI_Instance_Destruct
0x180133438  lea     rcx, [rsp+2F8h+instance]; self
0x180133440  call    MI_Instance_Destruct
0x180133445  jmp     loc_180133EB9
0x18013344a  mov     rax, [rsi]
0x18013344d  lea     r9, [rsp+2F8h+String]
0x180133452  lea     r8, aAllowarchivesc; "AllowArchiveScanning"
0x180133459  mov     edx, r14d
0x18013345c  mov     rcx, rsi
0x18013345f  mov     rax, [rax+18h]
0x180133463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133468  test    eax, eax
0x18013346a  jnz     short loc_18013348B
0x18013346c  mov     rcx, [rsp+2F8h+String]; String
0x180133471  test    rcx, rcx
0x180133474  jz      short loc_18013348B
0x180133476  call    cs:__imp__wtoi
0x18013347c  mov     [rsp+2F8h+var_1E8], eax
0x180133483  mov     [rsp+2F8h+var_1E4], 1
0x18013348b  mov     rax, [rsi]
0x18013348e  lea     r9, [rsp+2F8h+String]
0x180133493  lea     r8, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x18013349a  mov     edx, r14d
0x18013349d  mov     rcx, rsi
0x1801334a0  mov     rax, [rax+18h]
0x1801334a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801334a9  test    eax, eax
0x1801334ab  jnz     short loc_1801334CC
0x1801334ad  mov     rcx, [rsp+2F8h+String]; String
0x1801334b2  test    rcx, rcx
0x1801334b5  jz      short loc_1801334CC
0x1801334b7  call    cs:__imp__wtoi
0x1801334bd  mov     [rsp+2F8h+var_1E0], eax
0x1801334c4  mov     [rsp+2F8h+var_1DC], 1
0x1801334cc  mov     rax, [rsi]
0x1801334cf  lea     r9, [rsp+2F8h+String]
0x1801334d4  lea     r8, aAllowcloudprot; "AllowCloudProtection"
0x1801334db  mov     edx, r14d
0x1801334de  mov     rcx, rsi
0x1801334e1  mov     rax, [rax+18h]
0x1801334e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801334ea  test    eax, eax
0x1801334ec  jnz     short loc_18013350D
0x1801334ee  mov     rcx, [rsp+2F8h+String]; String
0x1801334f3  test    rcx, rcx
0x1801334f6  jz      short loc_18013350D
0x1801334f8  call    cs:__imp__wtoi
0x1801334fe  mov     [rsp+2F8h+var_1D8], eax
0x180133505  mov     [rsp+2F8h+var_1D4], 1
0x18013350d  mov     rax, [rsi]
0x180133510  lea     r9, [rsp+2F8h+String]
0x180133515  lea     r8, aAllowemailscan; "AllowEmailScanning"
0x18013351c  mov     edx, r14d
0x18013351f  mov     rcx, rsi
0x180133522  mov     rax, [rax+18h]
0x180133526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013352b  test    eax, eax
0x18013352d  jnz     short loc_18013354E
0x18013352f  mov     rcx, [rsp+2F8h+String]; String
0x180133534  test    rcx, rcx
0x180133537  jz      short loc_18013354E
0x180133539  call    cs:__imp__wtoi
0x18013353f  mov     [rsp+2F8h+var_1D0], eax
0x180133546  mov     [rsp+2F8h+var_1CC], 1
0x18013354e  mov     rax, [rsi]
0x180133551  lea     r9, [rsp+2F8h+String]
0x180133556  lea     r8, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x18013355d  mov     edx, r14d
0x180133560  mov     rcx, rsi
0x180133563  mov     rax, [rax+18h]
0x180133567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013356c  test    eax, eax
0x18013356e  jnz     short loc_18013358F
0x180133570  mov     rcx, [rsp+2F8h+String]; String
0x180133575  test    rcx, rcx
0x180133578  jz      short loc_18013358F
0x18013357a  call    cs:__imp__wtoi
0x180133580  mov     [rsp+2F8h+var_1C8], eax
0x180133587  mov     [rsp+2F8h+var_1C4], 1
0x18013358f  mov     rax, [rsi]
0x180133592  lea     r9, [rsp+2F8h+String]
0x180133597  lea     r8, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x18013359e  mov     edx, r14d
0x1801335a1  mov     rcx, rsi
0x1801335a4  mov     rax, [rax+18h]
0x1801335a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801335ad  test    eax, eax
0x1801335af  jnz     short loc_1801335D0
0x1801335b1  mov     rcx, [rsp+2F8h+String]; String
0x1801335b6  test    rcx, rcx
0x1801335b9  jz      short loc_1801335D0
0x1801335bb  call    cs:__imp__wtoi
0x1801335c1  mov     [rsp+2F8h+var_1C0], eax
0x1801335c8  mov     [rsp+2F8h+var_1BC], 1
0x1801335d0  mov     rax, [rsi]
0x1801335d3  lea     r9, [rsp+2F8h+String]
0x1801335d8  lea     r8, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x1801335df  mov     edx, r14d
0x1801335e2  mov     rcx, rsi
0x1801335e5  mov     rax, [rax+18h]
0x1801335e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801335ee  test    eax, eax
0x1801335f0  jnz     short loc_180133611
0x1801335f2  mov     rcx, [rsp+2F8h+String]; String
0x1801335f7  test    rcx, rcx
0x1801335fa  jz      short loc_180133611
0x1801335fc  call    cs:__imp__wtoi
0x180133602  mov     [rsp+2F8h+var_1B8], eax
0x180133609  mov     [rsp+2F8h+var_1B4], 1
0x180133611  mov     rax, [rsi]
0x180133614  lea     r9, [rsp+2F8h+String]
0x180133619  lea     r8, aAllowioavprote; "AllowIOAVProtection"
0x180133620  mov     edx, r14d
0x180133623  mov     rcx, rsi
0x180133626  mov     rax, [rax+18h]
0x18013362a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013362f  test    eax, eax
0x180133631  jnz     short loc_180133652
0x180133633  mov     rcx, [rsp+2F8h+String]; String
0x180133638  test    rcx, rcx
0x18013363b  jz      short loc_180133652
0x18013363d  call    cs:__imp__wtoi
0x180133643  mov     [rsp+2F8h+var_1B0], eax
0x18013364a  mov     [rsp+2F8h+var_1AC], 1
0x180133652  mov     rax, [rsi]
0x180133655  lea     r9, [rsp+2F8h+String]
0x18013365a  lea     r8, aAllowonaccessp; "AllowOnAccessProtection"
0x180133661  mov     edx, r14d
0x180133664  mov     rcx, rsi
0x180133667  mov     rax, [rax+18h]
0x18013366b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133670  test    eax, eax
  ... truncated ...
```
