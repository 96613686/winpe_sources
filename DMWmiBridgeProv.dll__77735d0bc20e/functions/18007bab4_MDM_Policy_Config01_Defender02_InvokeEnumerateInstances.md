# MDM_Policy_Config01_Defender02_InvokeEnumerateInstances

- ea: `0x18007bab4`
- end: `0x18007c8ee`
- name: `MDM_Policy_Config01_Defender02_InvokeEnumerateInstances`
- size: `3642`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a9b0`

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
- `0x18007bab4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18007bdc6`
- `msvcrt!_wtoi` at `0x18007be07`
- `msvcrt!_wtoi` at `0x18007be48`
- `msvcrt!_wtoi` at `0x18007be89`
- `msvcrt!_wtoi` at `0x18007beca`
- `msvcrt!_wtoi` at `0x18007bf0b`
- `msvcrt!_wtoi` at `0x18007bf4c`
- `msvcrt!_wtoi` at `0x18007bf8d`
- `msvcrt!_wtoi` at `0x18007bfce`
- `msvcrt!_wtoi` at `0x18007c00f`
- `msvcrt!_wtoi` at `0x18007c050`
- `msvcrt!_wtoi` at `0x18007c091`
- `msvcrt!_wtoi` at `0x18007c0d2`
- `msvcrt!_wtoi` at `0x18007c185`
- `msvcrt!_wtoi` at `0x18007c1c6`
- `msvcrt!_wtoi` at `0x18007c207`
- `msvcrt!_wtoi` at `0x18007c248`
- `msvcrt!_wtoi` at `0x18007c2fb`
- `msvcrt!_wtoi` at `0x18007c33c`
- `msvcrt!_wtoi` at `0x18007c37d`
- `msvcrt!_wtoi` at `0x18007c3be`
- `msvcrt!_wtoi` at `0x18007c3ff`
- `msvcrt!_wtoi` at `0x18007c440`
- `msvcrt!_wtoi` at `0x18007c52c`
- `msvcrt!_wtoi` at `0x18007c56d`
- `msvcrt!_wtoi` at `0x18007c5ae`
- `msvcrt!_wtoi` at `0x18007c5ef`
- `msvcrt!_wtoi` at `0x18007c630`
- `msvcrt!_wtoi` at `0x18007c671`
- `msvcrt!_wtoi` at `0x18007c75d`
- `msvcrt!_wtoi` at `0x18007c79e`
- `msvcrt!_wtoi` at `0x18007bdc6`
- `msvcrt!_wtoi` at `0x18007be07`
- `msvcrt!_wtoi` at `0x18007be48`
- `msvcrt!_wtoi` at `0x18007be89`
- `msvcrt!_wtoi` at `0x18007beca`
- `msvcrt!_wtoi` at `0x18007bf0b`
- `msvcrt!_wtoi` at `0x18007bf4c`
- `msvcrt!_wtoi` at `0x18007bf8d`
- `msvcrt!_wtoi` at `0x18007bfce`
- `msvcrt!_wtoi` at `0x18007c00f`
- `msvcrt!_wtoi` at `0x18007c050`
- `msvcrt!_wtoi` at `0x18007c091`
- `msvcrt!_wtoi` at `0x18007c0d2`
- `msvcrt!_wtoi` at `0x18007c185`
- `msvcrt!_wtoi` at `0x18007c1c6`
- `msvcrt!_wtoi` at `0x18007c207`
- `msvcrt!_wtoi` at `0x18007c248`
- `msvcrt!_wtoi` at `0x18007c2fb`
- `msvcrt!_wtoi` at `0x18007c33c`
- `msvcrt!_wtoi` at `0x18007c37d`
- `msvcrt!_wtoi` at `0x18007c3be`
- `msvcrt!_wtoi` at `0x18007c3ff`
- `msvcrt!_wtoi` at `0x18007c440`
- `msvcrt!_wtoi` at `0x18007c52c`
- `msvcrt!_wtoi` at `0x18007c56d`
- `msvcrt!_wtoi` at `0x18007c5ae`
- `msvcrt!_wtoi` at `0x18007c5ef`
- `msvcrt!_wtoi` at `0x18007c630`
- `msvcrt!_wtoi` at `0x18007c671`
- `msvcrt!_wtoi` at `0x18007c75d`
- `msvcrt!_wtoi` at `0x18007c79e`

## string_xrefs

- `0x18007bfaa`: `AllowOnAccessProtection`
- `0x18007c0ae`: `AllowUserUIAccess`
- `0x18007c265`: `ControlledFolderAccessAllowedApplications`
- `0x18007c29e`: `ControlledFolderAccessProtectedFolders`
- `0x18007c39a`: `EnableControlledFolderAccess`
- `0x18007c45d`: `ExcludedExtensions`
- `0x18007c496`: `ExcludedPaths`
- `0x18007c68e`: `SecurityIntelligenceLocation`
- `0x18007c6c7`: `SignatureUpdateFallbackOrder`
- `0x18007c700`: `SignatureUpdateFileSharesSources`
- `0x18007c739`: `SignatureUpdateInterval`
- `0x18007bd08`: `./Vendor/MSFT/Policy/Config`
- `0x18007bb2f`: `MDM_Policy_Config01_Defender02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Defender02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-2B8h] BYREF
  char v14; // [rsp+48h] [rbp-2B0h]
  WmiRequestHandlerAdd *v15; // [rsp+50h] [rbp-2A8h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_Defender02_NodeList,
           0x2Cu,
           2,
           &v15);
    if ( !v7 )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = v15;
          if ( v15 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = v15;
            if ( v15 )
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v8 + 33) - *((_QWORD *)v8 + 32)) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Defender02_rtti, &instance);
              if ( v7 )
              {
                v6 = v15;
                if ( v15 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_175;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowArchiveScanning",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowBehaviorMonitoring",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowCloudProtection",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowEmailScanning",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowFullScanOnMappedNetworkDrives",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowFullScanRemovableDriveScanning",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowIntrusionPreventionSystem",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowIOAVProtection",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowOnAccessProtection",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowRealtimeMonitoring",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowScanningNetworkFiles",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowScriptScanning",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowUserUIAccess",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AttackSurfaceReductionOnlyExclusions",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AttackSurfaceReductionRules",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AvgCPULoadFactor",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"CheckForSignaturesBeforeRunningScan",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"CloudBlockLevel",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"CloudExtendedTimeout",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ControlledFolderAccessAllowedApplications",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ControlledFolderAccessProtectedFolders",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DaysToRetainCleanedMalware",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableCatchupFullScan",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableCatchupQuickScan",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableControlledFolderAccess",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableLowCPUPriority",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableNetworkProtection",
                        &String)
                  && String )
                {
                  v68 = _wtoi(String);
                  v69 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludedExtensions",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludedPaths",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludedProcesses",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_ConfigureEdgeRedirectChannel(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PUAProtection",
                        &String)
                  && String )
                {
                  v70 = _wtoi(String);
                  v71 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RealTimeScanDirection",
                        &String)
                  && String )
                {
                  v72 = _wtoi(String);
                  v73 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ScanParameter",
                        &String)
                  && String )
                {
                  v74 = _wtoi(String);
                  v75 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ScheduleQuickScanTime",
                        &String)
                  && String )
                {
                  v76 = _wtoi(String);
                  v77 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ScheduleScanDay",
                        &String)
                  && String )
                {
                  v78 = _wtoi(String);
                  v79 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ScheduleScanTime",
                        &String)
                  && String )
                {
                  v80 = _wtoi(String);
                  v81 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SecurityIntelligenceLocation",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCrashDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SignatureUpdateFallbackOrder",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCustomerExperienceImprovementProgramParticipation(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SignatureUpdateFileSharesSources",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_DisableDeletingUserVisitedWebsites(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SignatureUpdateInterval",
                        &String)
                  && String )
                {
                  v82 = _wtoi(String);
                  v83 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SubmitSamplesConsent",
                        &String)
                  && String )
                {
                  v84 = _wtoi(String);
                  v85 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
            v6 = v15;
            if ( v15 )
            {
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = 1;
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
    v7 = (unsigned int)v15;
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
  return v7;
}

```

## disassembly

```asm
0x18007bab4  mov     [rsp+arg_8], rbx
0x18007bab9  mov     [rsp+arg_10], rsi
0x18007babe  push    rdi
0x18007babf  push    r12
0x18007bac1  push    r13
0x18007bac3  push    r14
0x18007bac5  push    r15
0x18007bac7  sub     rsp, 2D0h
0x18007bace  mov     rax, cs:__security_cookie
0x18007bad5  xor     rax, rsp
0x18007bad8  mov     [rsp+2F8h+var_38], rax
0x18007bae0  mov     r13b, dl
0x18007bae3  mov     r12, rcx
0x18007bae6  xor     edx, edx; Val
0x18007bae8  mov     r8d, 208h; Size
0x18007baee  lea     rcx, [rsp+2F8h+instance]; void *
0x18007baf6  call    memset_0
0x18007bafb  xor     edi, edi
0x18007bafd  mov     [rsp+2F8h+var_2B0], dil
0x18007bb02  mov     [rsp+2F8h+String], rdi
0x18007bb07  mov     [rsp+2F8h+var_270], edi
0x18007bb0e  mov     [rsp+2F8h+var_26C], dil
0x18007bb16  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007bb1d  mov     [rsp+2F8h+var_2A0], rax
0x18007bb22  lea     rax, [rsp+2F8h+var_270]
0x18007bb2a  mov     [rsp+2F8h+var_298], rax
0x18007bb2f  lea     rax, aMdmPolicyConfi_40; "MDM_Policy_Config01_Defender02"
0x18007bb36  mov     [rsp+2F8h+var_290], rax
0x18007bb3b  lea     rcx, [rsp+2F8h+var_270]
0x18007bb43  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007bb48  mov     eax, cs:dword_180380B68
0x18007bb4e  cmp     eax, 5
0x18007bb51  jbe     short loc_18007BBC3
0x18007bb53  mov     rdx, 200000000000h
0x18007bb5d  lea     rcx, dword_180380B68
0x18007bb64  call    _tlgKeywordOn
0x18007bb69  test    al, al
0x18007bb6b  jz      short loc_18007BBC3
0x18007bb6d  cmp     [rsp+2F8h+var_26C], dil
0x18007bb75  jz      short loc_18007BBA5
0x18007bb77  cmp     [rsp+2F8h+var_258], edi
0x18007bb7e  jnz     short loc_18007BB9B
0x18007bb80  cmp     [rsp+2F8h+var_254], edi
0x18007bb87  jnz     short loc_18007BB9B
0x18007bb89  cmp     [rsp+2F8h+var_250], edi
0x18007bb90  jnz     short loc_18007BB9B
0x18007bb92  cmp     [rsp+2F8h+var_24C], edi
0x18007bb99  jz      short loc_18007BBA5
0x18007bb9b  lea     r9, [rsp+2F8h+var_258]
0x18007bba3  jmp     short loc_18007BBA8
0x18007bba5  mov     r9, rdi
0x18007bba8  lea     r8, [rsp+2F8h+var_268]
0x18007bbb0  lea     rdx, byte_18036BED1
0x18007bbb7  lea     rcx, dword_180380B68
0x18007bbbe  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007bbc3  lea     rcx, [rsp+2F8h+var_2A0]; this
0x18007bbc8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18007bbcd  nop
0x18007bbce  mov     [rsp+2F8h+var_2A8], rdi
0x18007bbd3  lea     rax, [rsp+2F8h+var_2A8]
0x18007bbd8  mov     [rsp+2F8h+var_2C8], rax
0x18007bbdd  mov     [rsp+2F8h+var_2D0], 2
0x18007bbe5  mov     [rsp+2F8h+var_2D8], 2Ch ; ','
0x18007bbed  lea     r9, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Defender02_NodeList
0x18007bbf4  xor     r8d, r8d
0x18007bbf7  xor     edx, edx
0x18007bbf9  mov     rcx, r12
0x18007bbfc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007bc01  mov     r15d, eax
0x18007bc04  test    eax, eax
0x18007bc06  jz      short loc_18007BC0D
0x18007bc08  jmp     loc_18007C84E
0x18007bc0d  lea     rbx, [rsp+2F8h+var_2A8]
0x18007bc12  mov     [rsp+2F8h+var_280], rbx
0x18007bc17  mov     r14d, 1
0x18007bc1d  mov     [rsp+2F8h+var_278], r14b
0x18007bc25  mov     rsi, [rsp+2F8h+var_2A8]
0x18007bc2a  test    rsi, rsi
0x18007bc2d  jnz     short loc_18007BC37
0x18007bc2f  mov     r15d, r14d
0x18007bc32  jmp     loc_18007C84E
0x18007bc37  mov     rax, [rsi]
0x18007bc3a  mov     rcx, rsi
0x18007bc3d  mov     rax, [rax+10h]
0x18007bc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc46  mov     r15d, eax
0x18007bc49  test    eax, eax
0x18007bc4b  jz      short loc_18007BC6B
0x18007bc4d  mov     rcx, [rsp+2F8h+var_2A8]
0x18007bc52  test    rcx, rcx
0x18007bc55  jz      short loc_18007BC66
0x18007bc57  mov     rax, [rcx]
0x18007bc5a  mov     edx, r14d
0x18007bc5d  mov     rax, [rax]
0x18007bc60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc65  nop
0x18007bc66  jmp     loc_18007C84E
0x18007bc6b  mov     rax, [rsi]
0x18007bc6e  mov     rcx, rsi
0x18007bc71  mov     rax, [rax+8]
0x18007bc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc7a  mov     r15d, eax
0x18007bc7d  test    eax, eax
0x18007bc7f  jz      short loc_18007BC9F
0x18007bc81  mov     rcx, [rsp+2F8h+var_2A8]
0x18007bc86  test    rcx, rcx
0x18007bc89  jz      short loc_18007BC9A
0x18007bc8b  mov     rax, [rcx]
0x18007bc8e  mov     edx, r14d
0x18007bc91  mov     rax, [rax]
0x18007bc94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc99  nop
0x18007bc9a  jmp     loc_18007C84E
0x18007bc9f  mov     r14d, edi
0x18007bca2  mov     rax, [rsi+108h]
0x18007bca9  sub     rax, [rsi+100h]
0x18007bcb0  sar     rax, 4
0x18007bcb4  cmp     r14d, eax
0x18007bcb7  jnb     loc_18007C816
0x18007bcbd  lea     r8, [rsp+2F8h+instance]; instance
0x18007bcc5  lea     rdx, MDM_Policy_Config01_Defender02_rtti; classDecl
0x18007bccc  mov     rcx, r12; context
0x18007bccf  call    MI_Context_ConstructInstance
0x18007bcd4  mov     r15d, eax
0x18007bcd7  test    eax, eax
0x18007bcd9  jz      short loc_18007BCFB
0x18007bcdb  mov     rcx, [rbx]
0x18007bcde  test    rcx, rcx
0x18007bce1  jz      short loc_18007BCF6
0x18007bce3  mov     rax, [rcx]
0x18007bce6  mov     edx, 1
0x18007bceb  mov     rax, [rax]
0x18007bcee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bcf3  mov     [rbx], rdi
0x18007bcf6  jmp     loc_18007C84E
0x18007bcfb  mov     [rsp+2F8h+var_2B0], 1
0x18007bd00  mov     rax, [rsi]
0x18007bd03  lea     r9, [rsp+2F8h+String]
0x18007bd08  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18007bd0f  mov     edx, r14d
0x18007bd12  mov     rcx, rsi
0x18007bd15  mov     rax, [rax+18h]
0x18007bd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bd1e  test    eax, eax
0x18007bd20  jnz     short loc_18007BD39
0x18007bd22  mov     rdx, [rsp+2F8h+String]
0x18007bd27  test    rdx, rdx
0x18007bd2a  jz      short loc_18007BD39
0x18007bd2c  lea     rcx, [rsp+2F8h+instance]
0x18007bd34  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18007bd39  mov     rax, [rsi]
0x18007bd3c  lea     r9, [rsp+2F8h+String]
0x18007bd41  lea     r8, aDefender; "Defender"
0x18007bd48  mov     edx, r14d
0x18007bd4b  mov     rcx, rsi
0x18007bd4e  mov     rax, [rax+18h]
0x18007bd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bd57  test    eax, eax
0x18007bd59  jnz     short loc_18007BD72
0x18007bd5b  mov     rdx, [rsp+2F8h+String]
0x18007bd60  test    rdx, rdx
0x18007bd63  jz      short loc_18007BD72
0x18007bd65  lea     rcx, [rsp+2F8h+instance]
0x18007bd6d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18007bd72  cmp     r13b, 1
0x18007bd76  jnz     short loc_18007BD9A
0x18007bd78  lea     rdx, [rsp+2F8h+instance]
0x18007bd80  mov     rcx, r12; self
0x18007bd83  call    MI_Instance_Destruct
0x18007bd88  lea     rcx, [rsp+2F8h+instance]; self
0x18007bd90  call    MI_Instance_Destruct
0x18007bd95  jmp     loc_18007C809
0x18007bd9a  mov     rax, [rsi]
0x18007bd9d  lea     r9, [rsp+2F8h+String]
0x18007bda2  lea     r8, aAllowarchivesc; "AllowArchiveScanning"
0x18007bda9  mov     edx, r14d
0x18007bdac  mov     rcx, rsi
0x18007bdaf  mov     rax, [rax+18h]
0x18007bdb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bdb8  test    eax, eax
0x18007bdba  jnz     short loc_18007BDDB
0x18007bdbc  mov     rcx, [rsp+2F8h+String]; String
0x18007bdc1  test    rcx, rcx
0x18007bdc4  jz      short loc_18007BDDB
0x18007bdc6  call    cs:__imp__wtoi
0x18007bdcc  mov     [rsp+2F8h+var_1E8], eax
0x18007bdd3  mov     [rsp+2F8h+var_1E4], 1
0x18007bddb  mov     rax, [rsi]
0x18007bdde  lea     r9, [rsp+2F8h+String]
0x18007bde3  lea     r8, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x18007bdea  mov     edx, r14d
0x18007bded  mov     rcx, rsi
0x18007bdf0  mov     rax, [rax+18h]
0x18007bdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bdf9  test    eax, eax
0x18007bdfb  jnz     short loc_18007BE1C
0x18007bdfd  mov     rcx, [rsp+2F8h+String]; String
0x18007be02  test    rcx, rcx
0x18007be05  jz      short loc_18007BE1C
0x18007be07  call    cs:__imp__wtoi
0x18007be0d  mov     [rsp+2F8h+var_1E0], eax
0x18007be14  mov     [rsp+2F8h+var_1DC], 1
0x18007be1c  mov     rax, [rsi]
0x18007be1f  lea     r9, [rsp+2F8h+String]
0x18007be24  lea     r8, aAllowcloudprot; "AllowCloudProtection"
0x18007be2b  mov     edx, r14d
0x18007be2e  mov     rcx, rsi
0x18007be31  mov     rax, [rax+18h]
0x18007be35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007be3a  test    eax, eax
0x18007be3c  jnz     short loc_18007BE5D
0x18007be3e  mov     rcx, [rsp+2F8h+String]; String
0x18007be43  test    rcx, rcx
0x18007be46  jz      short loc_18007BE5D
0x18007be48  call    cs:__imp__wtoi
0x18007be4e  mov     [rsp+2F8h+var_1D8], eax
0x18007be55  mov     [rsp+2F8h+var_1D4], 1
0x18007be5d  mov     rax, [rsi]
0x18007be60  lea     r9, [rsp+2F8h+String]
0x18007be65  lea     r8, aAllowemailscan; "AllowEmailScanning"
0x18007be6c  mov     edx, r14d
0x18007be6f  mov     rcx, rsi
0x18007be72  mov     rax, [rax+18h]
0x18007be76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007be7b  test    eax, eax
0x18007be7d  jnz     short loc_18007BE9E
0x18007be7f  mov     rcx, [rsp+2F8h+String]; String
0x18007be84  test    rcx, rcx
0x18007be87  jz      short loc_18007BE9E
0x18007be89  call    cs:__imp__wtoi
0x18007be8f  mov     [rsp+2F8h+var_1D0], eax
0x18007be96  mov     [rsp+2F8h+var_1CC], 1
0x18007be9e  mov     rax, [rsi]
0x18007bea1  lea     r9, [rsp+2F8h+String]
0x18007bea6  lea     r8, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x18007bead  mov     edx, r14d
0x18007beb0  mov     rcx, rsi
0x18007beb3  mov     rax, [rax+18h]
0x18007beb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bebc  test    eax, eax
0x18007bebe  jnz     short loc_18007BEDF
0x18007bec0  mov     rcx, [rsp+2F8h+String]; String
0x18007bec5  test    rcx, rcx
0x18007bec8  jz      short loc_18007BEDF
0x18007beca  call    cs:__imp__wtoi
0x18007bed0  mov     [rsp+2F8h+var_1C8], eax
0x18007bed7  mov     [rsp+2F8h+var_1C4], 1
0x18007bedf  mov     rax, [rsi]
0x18007bee2  lea     r9, [rsp+2F8h+String]
0x18007bee7  lea     r8, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x18007beee  mov     edx, r14d
0x18007bef1  mov     rcx, rsi
0x18007bef4  mov     rax, [rax+18h]
0x18007bef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007befd  test    eax, eax
0x18007beff  jnz     short loc_18007BF20
0x18007bf01  mov     rcx, [rsp+2F8h+String]; String
0x18007bf06  test    rcx, rcx
0x18007bf09  jz      short loc_18007BF20
0x18007bf0b  call    cs:__imp__wtoi
0x18007bf11  mov     [rsp+2F8h+var_1C0], eax
0x18007bf18  mov     [rsp+2F8h+var_1BC], 1
0x18007bf20  mov     rax, [rsi]
0x18007bf23  lea     r9, [rsp+2F8h+String]
0x18007bf28  lea     r8, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x18007bf2f  mov     edx, r14d
0x18007bf32  mov     rcx, rsi
0x18007bf35  mov     rax, [rax+18h]
0x18007bf39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bf3e  test    eax, eax
0x18007bf40  jnz     short loc_18007BF61
0x18007bf42  mov     rcx, [rsp+2F8h+String]; String
0x18007bf47  test    rcx, rcx
0x18007bf4a  jz      short loc_18007BF61
0x18007bf4c  call    cs:__imp__wtoi
0x18007bf52  mov     [rsp+2F8h+var_1B8], eax
0x18007bf59  mov     [rsp+2F8h+var_1B4], 1
0x18007bf61  mov     rax, [rsi]
0x18007bf64  lea     r9, [rsp+2F8h+String]
0x18007bf69  lea     r8, aAllowioavprote; "AllowIOAVProtection"
0x18007bf70  mov     edx, r14d
0x18007bf73  mov     rcx, rsi
0x18007bf76  mov     rax, [rax+18h]
0x18007bf7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bf7f  test    eax, eax
0x18007bf81  jnz     short loc_18007BFA2
0x18007bf83  mov     rcx, [rsp+2F8h+String]; String
0x18007bf88  test    rcx, rcx
0x18007bf8b  jz      short loc_18007BFA2
0x18007bf8d  call    cs:__imp__wtoi
0x18007bf93  mov     [rsp+2F8h+var_1B0], eax
0x18007bf9a  mov     [rsp+2F8h+var_1AC], 1
0x18007bfa2  mov     rax, [rsi]
0x18007bfa5  lea     r9, [rsp+2F8h+String]
0x18007bfaa  lea     r8, aAllowonaccessp; "AllowOnAccessProtection"
0x18007bfb1  mov     edx, r14d
0x18007bfb4  mov     rcx, rsi
0x18007bfb7  mov     rax, [rax+18h]
0x18007bfbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bfc0  test    eax, eax
  ... truncated ...
```
