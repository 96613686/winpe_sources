# MDM_Policy_Result01_Defender02_InvokeGetInstance

- ea: `0x180133fa4`
- end: `0x180134bb8`
- name: `MDM_Policy_Result01_Defender02_InvokeGetInstance`
- size: `3092`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801320a0`

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
- `0x180133fa4`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180134243`
- `msvcrt!_wtoi` at `0x18013427a`
- `msvcrt!_wtoi` at `0x1801342b1`
- `msvcrt!_wtoi` at `0x1801342e8`
- `msvcrt!_wtoi` at `0x18013431f`
- `msvcrt!_wtoi` at `0x180134356`
- `msvcrt!_wtoi` at `0x18013438d`
- `msvcrt!_wtoi` at `0x1801343c4`
- `msvcrt!_wtoi` at `0x1801343fb`
- `msvcrt!_wtoi` at `0x180134432`
- `msvcrt!_wtoi` at `0x180134469`
- `msvcrt!_wtoi` at `0x1801344a0`
- `msvcrt!_wtoi` at `0x1801344d7`
- `msvcrt!_wtoi` at `0x18013456c`
- `msvcrt!_wtoi` at `0x1801345a3`
- `msvcrt!_wtoi` at `0x1801345da`
- `msvcrt!_wtoi` at `0x180134611`
- `msvcrt!_wtoi` at `0x1801346a6`
- `msvcrt!_wtoi` at `0x1801346dd`
- `msvcrt!_wtoi` at `0x180134714`
- `msvcrt!_wtoi` at `0x18013474b`
- `msvcrt!_wtoi` at `0x180134782`
- `msvcrt!_wtoi` at `0x1801347b9`
- `msvcrt!_wtoi` at `0x18013487d`
- `msvcrt!_wtoi` at `0x1801348b4`
- `msvcrt!_wtoi` at `0x1801348eb`
- `msvcrt!_wtoi` at `0x180134922`
- `msvcrt!_wtoi` at `0x180134959`
- `msvcrt!_wtoi` at `0x180134990`
- `msvcrt!_wtoi` at `0x180134a54`
- `msvcrt!_wtoi` at `0x180134a8b`
- `msvcrt!_wtoi` at `0x180134243`
- `msvcrt!_wtoi` at `0x18013427a`
- `msvcrt!_wtoi` at `0x1801342b1`
- `msvcrt!_wtoi` at `0x1801342e8`
- `msvcrt!_wtoi` at `0x18013431f`
- `msvcrt!_wtoi` at `0x180134356`
- `msvcrt!_wtoi` at `0x18013438d`
- `msvcrt!_wtoi` at `0x1801343c4`
- `msvcrt!_wtoi` at `0x1801343fb`
- `msvcrt!_wtoi` at `0x180134432`
- `msvcrt!_wtoi` at `0x180134469`
- `msvcrt!_wtoi` at `0x1801344a0`
- `msvcrt!_wtoi` at `0x1801344d7`
- `msvcrt!_wtoi` at `0x18013456c`
- `msvcrt!_wtoi` at `0x1801345a3`
- `msvcrt!_wtoi` at `0x1801345da`
- `msvcrt!_wtoi` at `0x180134611`
- `msvcrt!_wtoi` at `0x1801346a6`
- `msvcrt!_wtoi` at `0x1801346dd`
- `msvcrt!_wtoi` at `0x180134714`
- `msvcrt!_wtoi` at `0x18013474b`
- `msvcrt!_wtoi` at `0x180134782`
- `msvcrt!_wtoi` at `0x1801347b9`
- `msvcrt!_wtoi` at `0x18013487d`
- `msvcrt!_wtoi` at `0x1801348b4`
- `msvcrt!_wtoi` at `0x1801348eb`
- `msvcrt!_wtoi` at `0x180134922`
- `msvcrt!_wtoi` at `0x180134959`
- `msvcrt!_wtoi` at `0x180134990`
- `msvcrt!_wtoi` at `0x180134a54`
- `msvcrt!_wtoi` at `0x180134a8b`

## string_xrefs

- `0x1801343de`: `AllowOnAccessProtection`
- `0x1801344ba`: `AllowUserUIAccess`
- `0x18013462b`: `ControlledFolderAccessAllowedApplications`
- `0x18013465a`: `ControlledFolderAccessProtectedFolders`
- `0x18013472e`: `EnableControlledFolderAccess`
- `0x1801347d3`: `ExcludedExtensions`
- `0x180134802`: `ExcludedPaths`
- `0x1801349aa`: `SecurityIntelligenceLocation`
- `0x1801349d9`: `SignatureUpdateFallbackOrder`
- `0x180134a08`: `SignatureUpdateFileSharesSources`
- `0x180134a37`: `SignatureUpdateInterval`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Defender02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-2B8h] BYREF
  char v9; // [rsp+48h] [rbp-2B0h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-2A8h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-2A0h] BYREF
  char v12; // [rsp+80h] [rbp-278h]
  int v13; // [rsp+88h] [rbp-270h] BYREF
  char v14; // [rsp+8Ch] [rbp-26Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-268h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-258h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-248h] BYREF
  int v18; // [rsp+110h] [rbp-1E8h]
  char v19; // [rsp+114h] [rbp-1E4h]
  int v20; // [rsp+118h] [rbp-1E0h]
  char v21; // [rsp+11Ch] [rbp-1DCh]
  int v22; // [rsp+120h] [rbp-1D8h]
  char v23; // [rsp+124h] [rbp-1D4h]
  int v24; // [rsp+128h] [rbp-1D0h]
  char v25; // [rsp+12Ch] [rbp-1CCh]
  int v26; // [rsp+130h] [rbp-1C8h]
  char v27; // [rsp+134h] [rbp-1C4h]
  int v28; // [rsp+138h] [rbp-1C0h]
  char v29; // [rsp+13Ch] [rbp-1BCh]
  int v30; // [rsp+140h] [rbp-1B8h]
  char v31; // [rsp+144h] [rbp-1B4h]
  int v32; // [rsp+148h] [rbp-1B0h]
  char v33; // [rsp+14Ch] [rbp-1ACh]
  int v34; // [rsp+150h] [rbp-1A8h]
  char v35; // [rsp+154h] [rbp-1A4h]
  int v36; // [rsp+158h] [rbp-1A0h]
  char v37; // [rsp+15Ch] [rbp-19Ch]
  int v38; // [rsp+160h] [rbp-198h]
  char v39; // [rsp+164h] [rbp-194h]
  int v40; // [rsp+168h] [rbp-190h]
  char v41; // [rsp+16Ch] [rbp-18Ch]
  int v42; // [rsp+170h] [rbp-188h]
  char v43; // [rsp+174h] [rbp-184h]
  int v44; // [rsp+198h] [rbp-160h]
  char v45; // [rsp+19Ch] [rbp-15Ch]
  int v46; // [rsp+1A0h] [rbp-158h]
  char v47; // [rsp+1A4h] [rbp-154h]
  int v48; // [rsp+1A8h] [rbp-150h]
  char v49; // [rsp+1ACh] [rbp-14Ch]
  int v50; // [rsp+1B0h] [rbp-148h]
  char v51; // [rsp+1B4h] [rbp-144h]
  int v52; // [rsp+1D8h] [rbp-120h]
  char v53; // [rsp+1DCh] [rbp-11Ch]
  int v54; // [rsp+1E0h] [rbp-118h]
  char v55; // [rsp+1E4h] [rbp-114h]
  int v56; // [rsp+1E8h] [rbp-110h]
  char v57; // [rsp+1ECh] [rbp-10Ch]
  int v58; // [rsp+1F0h] [rbp-108h]
  char v59; // [rsp+1F4h] [rbp-104h]
  int v60; // [rsp+1F8h] [rbp-100h]
  char v61; // [rsp+1FCh] [rbp-FCh]
  int v62; // [rsp+200h] [rbp-F8h]
  char v63; // [rsp+204h] [rbp-F4h]
  int v64; // [rsp+238h] [rbp-C0h]
  char v65; // [rsp+23Ch] [rbp-BCh]
  int v66; // [rsp+240h] [rbp-B8h]
  char v67; // [rsp+244h] [rbp-B4h]
  int v68; // [rsp+248h] [rbp-B0h]
  char v69; // [rsp+24Ch] [rbp-ACh]
  int v70; // [rsp+250h] [rbp-A8h]
  char v71; // [rsp+254h] [rbp-A4h]
  int v72; // [rsp+258h] [rbp-A0h]
  char v73; // [rsp+25Ch] [rbp-9Ch]
  int v74; // [rsp+260h] [rbp-98h]
  char v75; // [rsp+264h] [rbp-94h]
  int v76; // [rsp+298h] [rbp-60h]
  char v77; // [rsp+29Ch] [rbp-5Ch]
  int v78; // [rsp+2A0h] [rbp-58h]
  char v79; // [rsp+2A4h] [rbp-54h]

  String = 0;
  memset_0(&instance, 0, 0x208u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Result01_Defender02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180353BCA,
      v15,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v11,
      "GetInstanceStart",
      a2[1].serverName,
      (const unsigned __int16 *)a2[1].ft);
    v10 = 0;
    v5 = CreateRequestHandlerInstance(
           (__int64)self,
           (wchar_t *)a2[1].serverName,
           (const unsigned __int16 *)a2[1].ft,
           (struct WmiNodeInfo *)&MDM_Policy_Result01_Defender02_NodeList,
           0x2Cu,
           0,
           &v10);
    if ( !v5 )
    {
      v11[4] = &v10;
      v12 = 1;
      v6 = v10;
      if ( v10 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v10,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Defender02_NodeList,
          0x2Cu);
        v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
          if ( v5 )
          {
            if ( v10 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
          }
          else
          {
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Defender02_rtti, &instance);
            if ( v5 )
            {
              if ( v10 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
            }
            else
            {
              v9 = 1;
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowArchiveScanning",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowBehaviorMonitoring",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowCloudProtection",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowEmailScanning",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowFullScanOnMappedNetworkDrives",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowFullScanRemovableDriveScanning",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowIntrusionPreventionSystem",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowIOAVProtection",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowOnAccessProtection",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowRealtimeMonitoring",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowScanningNetworkFiles",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowScriptScanning",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowUserUIAccess",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AttackSurfaceReductionOnlyExclusions",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AttackSurfaceReductionRules",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AvgCPULoadFactor",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"CheckForSignaturesBeforeRunningScan",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"CloudBlockLevel",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"CloudExtendedTimeout",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ControlledFolderAccessAllowedApplications",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ControlledFolderAccessProtectedFolders",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DaysToRetainCleanedMalware",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableCatchupFullScan",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableCatchupQuickScan",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"EnableControlledFolderAccess",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"EnableLowCPUPriority",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"EnableNetworkProtection",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ExcludedExtensions",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ExcludedPaths",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ExcludedProcesses",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_ConfigureEdgeRedirectChannel(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"PUAProtection",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RealTimeScanDirection",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ScanParameter",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ScheduleQuickScanTime",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ScheduleScanDay",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v72 = _wtoi(String);
                v73 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ScheduleScanTime",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v74 = _wtoi(String);
                v75 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"SecurityIntelligenceLocation",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCrashDetection(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"SignatureUpdateFallbackOrder",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCustomerExperienceImprovementProgramParticipation(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"SignatureUpdateFileSharesSources",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_DisableDeletingUserVisitedWebsites(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"SignatureUpdateInterval",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v76 = _wtoi(String);
                v77 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"SubmitSamplesConsent",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v78 = _wtoi(String);
                v79 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ThreatSeverityDefaultAction",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_DisableFeedsBackgroundSync(&instance);
              }
              MI_Instance_Destruct((MI_Instance *)self);
              if ( v10 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
              MI_Instance_Destruct(&instance);
            }
          }
        }
      }
      else
      {
        v5 = 1;
      }
    }
  }
  else
  {
    v5 = 4;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18036FC3F,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x180133fa4  mov     [rsp+arg_10], rbx
0x180133fa9  push    rsi
0x180133faa  push    rdi
0x180133fab  push    r12
0x180133fad  push    r14
0x180133faf  push    r15
0x180133fb1  sub     rsp, 2D0h
0x180133fb8  mov     rax, cs:__security_cookie
0x180133fbf  xor     rax, rsp
0x180133fc2  mov     [rsp+2F8h+var_38], rax
0x180133fca  mov     rsi, rdx
0x180133fcd  mov     r15, rcx
0x180133fd0  xor     ebx, ebx
0x180133fd2  mov     [rsp+2F8h+String], rbx
0x180133fd7  xor     edx, edx; Val
0x180133fd9  mov     r8d, 208h; Size
0x180133fdf  lea     rcx, [rsp+2F8h+instance]; void *
0x180133fe7  call    memset_0
0x180133fec  mov     [rsp+2F8h+var_270], ebx
0x180133ff3  mov     [rsp+2F8h+var_26C], bl
0x180133ffa  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180134001  mov     [rsp+2F8h+var_2A0], rax
0x180134006  lea     rax, [rsp+2F8h+var_270]
0x18013400e  mov     [rsp+2F8h+var_298], rax
0x180134013  lea     rax, aMdmPolicyResul_181; "MDM_Policy_Result01_Defender02"
0x18013401a  mov     [rsp+2F8h+var_290], rax
0x18013401f  lea     rcx, [rsp+2F8h+var_270]
0x180134027  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18013402c  mov     eax, cs:dword_180380B68
0x180134032  cmp     eax, 5
0x180134035  jbe     short loc_1801340A6
0x180134037  mov     rdx, 200000000000h
0x180134041  lea     rcx, dword_180380B68
0x180134048  call    _tlgKeywordOn
0x18013404d  test    al, al
0x18013404f  jz      short loc_1801340A6
0x180134051  cmp     [rsp+2F8h+var_26C], bl
0x180134058  jz      short loc_180134088
0x18013405a  cmp     [rsp+2F8h+var_258], ebx
0x180134061  jnz     short loc_18013407E
0x180134063  cmp     [rsp+2F8h+var_254], ebx
0x18013406a  jnz     short loc_18013407E
0x18013406c  cmp     [rsp+2F8h+var_250], ebx
0x180134073  jnz     short loc_18013407E
0x180134075  cmp     [rsp+2F8h+var_24C], ebx
0x18013407c  jz      short loc_180134088
0x18013407e  lea     r9, [rsp+2F8h+var_258]
0x180134086  jmp     short loc_18013408B
0x180134088  mov     r9, rbx
0x18013408b  lea     r8, [rsp+2F8h+var_268]
0x180134093  lea     rdx, word_180353BCA
0x18013409a  lea     rcx, dword_180380B68
0x1801340a1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801340a6  cmp     [rsi+48h], bl
0x1801340a9  jz      loc_180134B17
0x1801340af  mov     [rsp+2F8h+var_2B0], bl
0x1801340b3  cmp     [rsi+58h], bl
0x1801340b6  jz      loc_180134B17
0x1801340bc  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801340c0  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801340c4  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1801340cb  lea     rcx, [rsp+2F8h+var_2A0]; this
0x1801340d0  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801340d5  nop
0x1801340d6  mov     [rsp+2F8h+var_2A8], rbx
0x1801340db  lea     rax, [rsp+2F8h+var_2A8]
0x1801340e0  mov     [rsp+2F8h+var_2C8], rax
0x1801340e5  mov     [rsp+2F8h+var_2D0], ebx
0x1801340e9  mov     [rsp+2F8h+var_2D8], 2Ch ; ','
0x1801340f1  lea     r9, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Defender02_NodeList
0x1801340f8  mov     r8, [rsi+40h]
0x1801340fc  mov     rdx, [rsi+50h]
0x180134100  mov     rcx, r15
0x180134103  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180134108  mov     r14d, eax
0x18013410b  test    eax, eax
0x18013410d  jz      short loc_180134114
0x18013410f  jmp     loc_180134B1D
0x180134114  lea     rax, [rsp+2F8h+var_2A8]
0x180134119  mov     [rsp+2F8h+var_280], rax
0x18013411e  mov     r12d, 1
0x180134124  mov     [rsp+2F8h+var_278], r12b
0x18013412c  mov     rdi, [rsp+2F8h+var_2A8]
0x180134131  test    rdi, rdi
0x180134134  jnz     short loc_18013413E
0x180134136  mov     r14d, r12d
0x180134139  jmp     loc_180134B1D
0x18013413e  mov     r9d, 2Ch ; ','; unsigned int
0x180134144  lea     r8, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18013414b  mov     rdx, rsi; struct _MI_Instance *
0x18013414e  mov     rcx, rdi; this
0x180134151  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180134156  mov     rax, [rdi]
0x180134159  mov     rcx, rdi
0x18013415c  mov     rax, [rax+10h]
0x180134160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134165  mov     r14d, eax
0x180134168  test    eax, eax
0x18013416a  jz      short loc_18013418A
0x18013416c  mov     rcx, [rsp+2F8h+var_2A8]
0x180134171  test    rcx, rcx
0x180134174  jz      short loc_180134185
0x180134176  mov     rax, [rcx]
0x180134179  mov     edx, r12d
0x18013417c  mov     rax, [rax]
0x18013417f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134184  nop
0x180134185  jmp     loc_180134B1D
0x18013418a  mov     rax, [rdi]
0x18013418d  mov     rcx, rdi
0x180134190  mov     rax, [rax+8]
0x180134194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134199  mov     r14d, eax
0x18013419c  test    eax, eax
0x18013419e  jz      short loc_1801341BE
0x1801341a0  mov     rcx, [rsp+2F8h+var_2A8]
0x1801341a5  test    rcx, rcx
0x1801341a8  jz      short loc_1801341B9
0x1801341aa  mov     rax, [rcx]
0x1801341ad  mov     edx, r12d
0x1801341b0  mov     rax, [rax]
0x1801341b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801341b8  nop
0x1801341b9  jmp     loc_180134B1D
0x1801341be  lea     r8, [rsp+2F8h+instance]; instance
0x1801341c6  lea     rdx, MDM_Policy_Result01_Defender02_rtti; classDecl
0x1801341cd  mov     rcx, r15; context
0x1801341d0  call    MI_Context_ConstructInstance
0x1801341d5  mov     r14d, eax
0x1801341d8  test    eax, eax
0x1801341da  jz      short loc_1801341FA
0x1801341dc  mov     rcx, [rsp+2F8h+var_2A8]
0x1801341e1  test    rcx, rcx
0x1801341e4  jz      short loc_1801341F5
0x1801341e6  mov     rax, [rcx]
0x1801341e9  mov     edx, r12d
0x1801341ec  mov     rax, [rax]
0x1801341ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801341f4  nop
0x1801341f5  jmp     loc_180134B1D
0x1801341fa  mov     [rsp+2F8h+var_2B0], r12b
0x1801341ff  mov     rdx, [rsi+40h]
0x180134203  lea     rcx, [rsp+2F8h+instance]
0x18013420b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180134210  mov     rdx, [rsi+50h]
0x180134214  lea     rcx, [rsp+2F8h+instance]
0x18013421c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180134221  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180134226  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x18013422d  mov     rcx, rdi; this
0x180134230  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180134235  test    eax, eax
0x180134237  jnz     short loc_180134258
0x180134239  mov     rcx, [rsp+2F8h+String]; String
0x18013423e  test    rcx, rcx
0x180134241  jz      short loc_180134258
0x180134243  call    cs:__imp__wtoi
0x180134249  mov     [rsp+2F8h+var_1E8], eax
0x180134250  mov     [rsp+2F8h+var_1E4], r12b
0x180134258  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18013425d  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x180134264  mov     rcx, rdi; this
0x180134267  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013426c  test    eax, eax
0x18013426e  jnz     short loc_18013428F
0x180134270  mov     rcx, [rsp+2F8h+String]; String
0x180134275  test    rcx, rcx
0x180134278  jz      short loc_18013428F
0x18013427a  call    cs:__imp__wtoi
0x180134280  mov     [rsp+2F8h+var_1E0], eax
0x180134287  mov     [rsp+2F8h+var_1DC], r12b
0x18013428f  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180134294  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x18013429b  mov     rcx, rdi; this
0x18013429e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801342a3  test    eax, eax
0x1801342a5  jnz     short loc_1801342C6
0x1801342a7  mov     rcx, [rsp+2F8h+String]; String
0x1801342ac  test    rcx, rcx
0x1801342af  jz      short loc_1801342C6
0x1801342b1  call    cs:__imp__wtoi
0x1801342b7  mov     [rsp+2F8h+var_1D8], eax
0x1801342be  mov     [rsp+2F8h+var_1D4], r12b
0x1801342c6  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x1801342cb  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x1801342d2  mov     rcx, rdi; this
0x1801342d5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801342da  test    eax, eax
0x1801342dc  jnz     short loc_1801342FD
0x1801342de  mov     rcx, [rsp+2F8h+String]; String
0x1801342e3  test    rcx, rcx
0x1801342e6  jz      short loc_1801342FD
0x1801342e8  call    cs:__imp__wtoi
0x1801342ee  mov     [rsp+2F8h+var_1D0], eax
0x1801342f5  mov     [rsp+2F8h+var_1CC], r12b
0x1801342fd  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180134302  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x180134309  mov     rcx, rdi; this
0x18013430c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180134311  test    eax, eax
0x180134313  jnz     short loc_180134334
0x180134315  mov     rcx, [rsp+2F8h+String]; String
0x18013431a  test    rcx, rcx
0x18013431d  jz      short loc_180134334
0x18013431f  call    cs:__imp__wtoi
0x180134325  mov     [rsp+2F8h+var_1C8], eax
0x18013432c  mov     [rsp+2F8h+var_1C4], r12b
0x180134334  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180134339  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x180134340  mov     rcx, rdi; this
0x180134343  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180134348  test    eax, eax
0x18013434a  jnz     short loc_18013436B
0x18013434c  mov     rcx, [rsp+2F8h+String]; String
0x180134351  test    rcx, rcx
0x180134354  jz      short loc_18013436B
0x180134356  call    cs:__imp__wtoi
0x18013435c  mov     [rsp+2F8h+var_1C0], eax
0x180134363  mov     [rsp+2F8h+var_1BC], r12b
0x18013436b  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180134370  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x180134377  mov     rcx, rdi; this
0x18013437a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013437f  test    eax, eax
0x180134381  jnz     short loc_1801343A2
0x180134383  mov     rcx, [rsp+2F8h+String]; String
0x180134388  test    rcx, rcx
0x18013438b  jz      short loc_1801343A2
0x18013438d  call    cs:__imp__wtoi
0x180134393  mov     [rsp+2F8h+var_1B8], eax
0x18013439a  mov     [rsp+2F8h+var_1B4], r12b
0x1801343a2  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x1801343a7  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x1801343ae  mov     rcx, rdi; this
0x1801343b1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801343b6  test    eax, eax
0x1801343b8  jnz     short loc_1801343D9
0x1801343ba  mov     rcx, [rsp+2F8h+String]; String
0x1801343bf  test    rcx, rcx
0x1801343c2  jz      short loc_1801343D9
0x1801343c4  call    cs:__imp__wtoi
0x1801343ca  mov     [rsp+2F8h+var_1B0], eax
0x1801343d1  mov     [rsp+2F8h+var_1AC], r12b
0x1801343d9  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x1801343de  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x1801343e5  mov     rcx, rdi; this
0x1801343e8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801343ed  test    eax, eax
0x1801343ef  jnz     short loc_180134410
0x1801343f1  mov     rcx, [rsp+2F8h+String]; String
0x1801343f6  test    rcx, rcx
0x1801343f9  jz      short loc_180134410
0x1801343fb  call    cs:__imp__wtoi
0x180134401  mov     [rsp+2F8h+var_1A8], eax
0x180134408  mov     [rsp+2F8h+var_1A4], r12b
0x180134410  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180134415  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x18013441c  mov     rcx, rdi; this
0x18013441f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180134424  test    eax, eax
0x180134426  jnz     short loc_180134447
0x180134428  mov     rcx, [rsp+2F8h+String]; String
0x18013442d  test    rcx, rcx
0x180134430  jz      short loc_180134447
0x180134432  call    cs:__imp__wtoi
0x180134438  mov     [rsp+2F8h+var_1A0], eax
0x18013443f  mov     [rsp+2F8h+var_19C], r12b
0x180134447  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18013444c  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x180134453  mov     rcx, rdi; this
0x180134456  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013445b  test    eax, eax
0x18013445d  jnz     short loc_18013447E
0x18013445f  mov     rcx, [rsp+2F8h+String]; String
0x180134464  test    rcx, rcx
0x180134467  jz      short loc_18013447E
0x180134469  call    cs:__imp__wtoi
0x18013446f  mov     [rsp+2F8h+var_198], eax
0x180134476  mov     [rsp+2F8h+var_194], r12b
0x18013447e  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180134483  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x18013448a  mov     rcx, rdi; this
0x18013448d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180134492  test    eax, eax
0x180134494  jnz     short loc_1801344B5
0x180134496  mov     rcx, [rsp+2F8h+String]; String
0x18013449b  test    rcx, rcx
0x18013449e  jz      short loc_1801344B5
0x1801344a0  call    cs:__imp__wtoi
0x1801344a6  mov     [rsp+2F8h+var_190], eax
0x1801344ad  mov     [rsp+2F8h+var_18C], r12b
0x1801344b5  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x1801344ba  lea     rdx, aAllowuseruiacc; "AllowUserUIAccess"
0x1801344c1  mov     rcx, rdi; this
0x1801344c4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801344c9  test    eax, eax
0x1801344cb  jnz     short loc_1801344EC
0x1801344cd  mov     rcx, [rsp+2F8h+String]; String
0x1801344d2  test    rcx, rcx
0x1801344d5  jz      short loc_1801344EC
  ... truncated ...
```
