# MDM_Policy_Result01_System02_InvokeEnumerateInstances

- ea: `0x18019a9b4`
- end: `0x18019b59c`
- name: `MDM_Policy_Result01_System02_InvokeEnumerateInstances`
- size: `3048`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180199b30`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x180005114`
- `0x18000529c`
- `0x180005424`
- `0x1800058d8`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18019a9b4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18019acc6`
- `msvcrt!_wtoi` at `0x18019ad07`
- `msvcrt!_wtoi` at `0x18019ad48`
- `msvcrt!_wtoi` at `0x18019ad89`
- `msvcrt!_wtoi` at `0x18019adca`
- `msvcrt!_wtoi` at `0x18019ae0b`
- `msvcrt!_wtoi` at `0x18019ae4c`
- `msvcrt!_wtoi` at `0x18019ae8d`
- `msvcrt!_wtoi` at `0x18019aece`
- `msvcrt!_wtoi` at `0x18019af0f`
- `msvcrt!_wtoi` at `0x18019af50`
- `msvcrt!_wtoi` at `0x18019af91`
- `msvcrt!_wtoi` at `0x18019afd2`
- `msvcrt!_wtoi` at `0x18019b013`
- `msvcrt!_wtoi` at `0x18019b0c6`
- `msvcrt!_wtoi` at `0x18019b107`
- `msvcrt!_wtoi` at `0x18019b148`
- `msvcrt!_wtoi` at `0x18019b189`
- `msvcrt!_wtoi` at `0x18019b1ca`
- `msvcrt!_wtoi` at `0x18019b20b`
- `msvcrt!_wtoi` at `0x18019b24c`
- `msvcrt!_wtoi` at `0x18019b28d`
- `msvcrt!_wtoi` at `0x18019b307`
- `msvcrt!_wtoi` at `0x18019b348`
- `msvcrt!_wtoi` at `0x18019b389`
- `msvcrt!_wtoi` at `0x18019b3ca`
- `msvcrt!_wtoi` at `0x18019b40b`
- `msvcrt!_wtoi` at `0x18019b485`
- `msvcrt!_wtoi` at `0x18019acc6`
- `msvcrt!_wtoi` at `0x18019ad07`
- `msvcrt!_wtoi` at `0x18019ad48`
- `msvcrt!_wtoi` at `0x18019ad89`
- `msvcrt!_wtoi` at `0x18019adca`
- `msvcrt!_wtoi` at `0x18019ae0b`
- `msvcrt!_wtoi` at `0x18019ae4c`
- `msvcrt!_wtoi` at `0x18019ae8d`
- `msvcrt!_wtoi` at `0x18019aece`
- `msvcrt!_wtoi` at `0x18019af0f`
- `msvcrt!_wtoi` at `0x18019af50`
- `msvcrt!_wtoi` at `0x18019af91`
- `msvcrt!_wtoi` at `0x18019afd2`
- `msvcrt!_wtoi` at `0x18019b013`
- `msvcrt!_wtoi` at `0x18019b0c6`
- `msvcrt!_wtoi` at `0x18019b107`
- `msvcrt!_wtoi` at `0x18019b148`
- `msvcrt!_wtoi` at `0x18019b189`
- `msvcrt!_wtoi` at `0x18019b1ca`
- `msvcrt!_wtoi` at `0x18019b20b`
- `msvcrt!_wtoi` at `0x18019b24c`
- `msvcrt!_wtoi` at `0x18019b28d`
- `msvcrt!_wtoi` at `0x18019b307`
- `msvcrt!_wtoi` at `0x18019b348`
- `msvcrt!_wtoi` at `0x18019b389`
- `msvcrt!_wtoi` at `0x18019b3ca`
- `msvcrt!_wtoi` at `0x18019b40b`
- `msvcrt!_wtoi` at `0x18019b485`

## string_xrefs

- `0x18019ace3`: `AllowCommercialDataPipeline`
- `0x18019af6d`: `AllowUpdateComplianceProcessing`
- `0x18019b069`: `ConfigureMicrosoft365UploadEndpoint`
- `0x18019b0a2`: `ConfigureTelemetryOptInChangeNotification`
- `0x18019b0e3`: `ConfigureTelemetryOptInSettingsUx`
- `0x18019b124`: `DisableDeviceDelete`
- `0x18019b1a6`: `DisableDirectXDatabaseUpdate`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_System02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r15d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-228h] BYREF
  char v11; // [rsp+48h] [rbp-220h]
  WmiRequestHandlerAdd *v12; // [rsp+50h] [rbp-218h] BYREF
  _QWORD v13[5]; // [rsp+58h] [rbp-210h] BYREF
  char v14; // [rsp+80h] [rbp-1E8h]
  int v15; // [rsp+88h] [rbp-1E0h] BYREF
  char v16; // [rsp+8Ch] [rbp-1DCh]
  _BYTE v17[16]; // [rsp+90h] [rbp-1D8h] BYREF
  _DWORD v18[4]; // [rsp+A0h] [rbp-1C8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-1B8h] BYREF
  int v20; // [rsp+110h] [rbp-158h]
  char v21; // [rsp+114h] [rbp-154h]
  int v22; // [rsp+118h] [rbp-150h]
  char v23; // [rsp+11Ch] [rbp-14Ch]
  int v24; // [rsp+120h] [rbp-148h]
  char v25; // [rsp+124h] [rbp-144h]
  int v26; // [rsp+128h] [rbp-140h]
  char v27; // [rsp+12Ch] [rbp-13Ch]
  int v28; // [rsp+130h] [rbp-138h]
  char v29; // [rsp+134h] [rbp-134h]
  int v30; // [rsp+138h] [rbp-130h]
  char v31; // [rsp+13Ch] [rbp-12Ch]
  int v32; // [rsp+140h] [rbp-128h]
  char v33; // [rsp+144h] [rbp-124h]
  int v34; // [rsp+148h] [rbp-120h]
  char v35; // [rsp+14Ch] [rbp-11Ch]
  int v36; // [rsp+150h] [rbp-118h]
  char v37; // [rsp+154h] [rbp-114h]
  int v38; // [rsp+158h] [rbp-110h]
  char v39; // [rsp+15Ch] [rbp-10Ch]
  int v40; // [rsp+160h] [rbp-108h]
  char v41; // [rsp+164h] [rbp-104h]
  int v42; // [rsp+168h] [rbp-100h]
  char v43; // [rsp+16Ch] [rbp-FCh]
  int v44; // [rsp+170h] [rbp-F8h]
  char v45; // [rsp+174h] [rbp-F4h]
  int v46; // [rsp+178h] [rbp-F0h]
  char v47; // [rsp+17Ch] [rbp-ECh]
  int v48; // [rsp+1A0h] [rbp-C8h]
  char v49; // [rsp+1A4h] [rbp-C4h]
  int v50; // [rsp+1A8h] [rbp-C0h]
  char v51; // [rsp+1ACh] [rbp-BCh]
  int v52; // [rsp+1B0h] [rbp-B8h]
  char v53; // [rsp+1B4h] [rbp-B4h]
  int v54; // [rsp+1B8h] [rbp-B0h]
  char v55; // [rsp+1BCh] [rbp-ACh]
  int v56; // [rsp+1C0h] [rbp-A8h]
  char v57; // [rsp+1C4h] [rbp-A4h]
  int v58; // [rsp+1C8h] [rbp-A0h]
  char v59; // [rsp+1CCh] [rbp-9Ch]
  int v60; // [rsp+1D0h] [rbp-98h]
  char v61; // [rsp+1D4h] [rbp-94h]
  int v62; // [rsp+1D8h] [rbp-90h]
  char v63; // [rsp+1DCh] [rbp-8Ch]
  int v64; // [rsp+1F0h] [rbp-78h]
  char v65; // [rsp+1F4h] [rbp-74h]
  int v66; // [rsp+1F8h] [rbp-70h]
  char v67; // [rsp+1FCh] [rbp-6Ch]
  int v68; // [rsp+200h] [rbp-68h]
  char v69; // [rsp+204h] [rbp-64h]
  int v70; // [rsp+208h] [rbp-60h]
  char v71; // [rsp+20Ch] [rbp-5Ch]
  int v72; // [rsp+210h] [rbp-58h]
  char v73; // [rsp+214h] [rbp-54h]
  int v74; // [rsp+228h] [rbp-40h]
  char v75; // [rsp+22Ch] [rbp-3Ch]

  memset_0(&instance, 0, 0x180u);
  v11 = 0;
  String = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = &TelemetryEventWriter::`vftable';
  v13[1] = &v15;
  v13[2] = "MDM_Policy_Result01_System02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v5 = v18;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_180367B1E,
      v17,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v13, v4);
  v12 = 0;
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_System02_NodeList,
         0x22u,
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
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_System02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_134;
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
                    L"System",
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
                      L"AllowBuildPreview",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowCommercialDataPipeline",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowDesktopAnalyticsProcessing",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowDeviceNameInDiagnosticData",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowEmbeddedMode",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowExperimentation",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowFontProviders",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowLocation",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowMicrosoftManagedDesktopProcessing",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowStorageCard",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowTelemetry",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowUpdateComplianceProcessing",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowUserToResetPhone",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowWUfBCloudProcessing",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"BootStartDriverInitialization",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureMicrosoft365UploadEndpoint",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureTelemetryOptInChangeNotification",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureTelemetryOptInSettingsUx",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableDeviceDelete",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableDiagnosticDataViewer",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableDirectXDatabaseUpdate",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableEnterpriseAuthProxy",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableOneDriveFileSync",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableOneSettingsDownloads",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableSystemRestore",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"EnableOneSettingsAuditing",
                      &String)
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"FeedbackHubAlwaysSaveDiagnosticsLocally",
                      &String)
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"LimitDiagnosticLogCollection",
                      &String)
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"LimitDumpCollection",
                      &String)
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"LimitEnhancedDiagnosticDataWindowsAnalytics",
                      &String)
                && String )
              {
                v72 = _wtoi(String);
                v73 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"TelemetryProxy",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_ConsistentMimeHandlingInternetExplorerProcesses(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"TurnOffFileHistory",
                      &String)
                && String )
              {
                v74 = _wtoi(String);
                v75 = 1;
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
LABEL_134:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v13, "EnumerateInstancesEnd", v6);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_1803431E9,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return v6;
}

```

## disassembly

```asm
0x18019a9b4  mov     [rsp+arg_8], rbx
0x18019a9b9  mov     [rsp+arg_10], rsi
0x18019a9be  push    rdi
0x18019a9bf  push    r12
0x18019a9c1  push    r13
0x18019a9c3  push    r14
0x18019a9c5  push    r15
0x18019a9c7  sub     rsp, 240h
0x18019a9ce  mov     rax, cs:__security_cookie
0x18019a9d5  xor     rax, rsp
0x18019a9d8  mov     [rsp+268h+var_38], rax
0x18019a9e0  mov     r13b, dl
0x18019a9e3  mov     r12, rcx
0x18019a9e6  xor     edx, edx; Val
0x18019a9e8  mov     r8d, 180h; Size
0x18019a9ee  lea     rcx, [rsp+268h+instance]; void *
0x18019a9f6  call    memset_0
0x18019a9fb  xor     edi, edi
0x18019a9fd  mov     [rsp+268h+var_220], dil
0x18019aa02  mov     [rsp+268h+String], rdi
0x18019aa07  mov     [rsp+268h+var_1E0], edi
0x18019aa0e  mov     [rsp+268h+var_1DC], dil
0x18019aa16  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019aa1d  mov     [rsp+268h+var_210], rax
0x18019aa22  lea     rax, [rsp+268h+var_1E0]
0x18019aa2a  mov     [rsp+268h+var_208], rax
0x18019aa2f  lea     rax, aMdmPolicyResul_159; "MDM_Policy_Result01_System02"
0x18019aa36  mov     [rsp+268h+var_200], rax
0x18019aa3b  lea     rcx, [rsp+268h+var_1E0]
0x18019aa43  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019aa48  mov     eax, cs:dword_180380B68
0x18019aa4e  cmp     eax, 5
0x18019aa51  jbe     short loc_18019AAC3
0x18019aa53  mov     rdx, 200000000000h
0x18019aa5d  lea     rcx, dword_180380B68
0x18019aa64  call    _tlgKeywordOn
0x18019aa69  test    al, al
0x18019aa6b  jz      short loc_18019AAC3
0x18019aa6d  cmp     [rsp+268h+var_1DC], dil
0x18019aa75  jz      short loc_18019AAA5
0x18019aa77  cmp     [rsp+268h+var_1C8], edi
0x18019aa7e  jnz     short loc_18019AA9B
0x18019aa80  cmp     [rsp+268h+var_1C4], edi
0x18019aa87  jnz     short loc_18019AA9B
0x18019aa89  cmp     [rsp+268h+var_1C0], edi
0x18019aa90  jnz     short loc_18019AA9B
0x18019aa92  cmp     [rsp+268h+var_1BC], edi
0x18019aa99  jz      short loc_18019AAA5
0x18019aa9b  lea     r9, [rsp+268h+var_1C8]
0x18019aaa3  jmp     short loc_18019AAA8
0x18019aaa5  mov     r9, rdi
0x18019aaa8  lea     r8, [rsp+268h+var_1D8]
0x18019aab0  lea     rdx, word_180367B1E
0x18019aab7  lea     rcx, dword_180380B68
0x18019aabe  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019aac3  lea     rcx, [rsp+268h+var_210]; this
0x18019aac8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18019aacd  nop
0x18019aace  mov     [rsp+268h+var_218], rdi
0x18019aad3  lea     rax, [rsp+268h+var_218]
0x18019aad8  mov     [rsp+268h+var_238], rax
0x18019aadd  mov     [rsp+268h+var_240], 2
0x18019aae5  mov     [rsp+268h+var_248], 22h ; '"'
0x18019aaed  lea     r9, ?MDM_Policy_Result01_System02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_System02_NodeList
0x18019aaf4  xor     r8d, r8d
0x18019aaf7  xor     edx, edx
0x18019aaf9  mov     rcx, r12
0x18019aafc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019ab01  mov     r15d, eax
0x18019ab04  test    eax, eax
0x18019ab06  jz      short loc_18019AB0D
0x18019ab08  jmp     loc_18019B4FC
0x18019ab0d  lea     rbx, [rsp+268h+var_218]
0x18019ab12  mov     [rsp+268h+var_1F0], rbx
0x18019ab17  mov     r14d, 1
0x18019ab1d  mov     [rsp+268h+var_1E8], r14b
0x18019ab25  mov     rsi, [rsp+268h+var_218]
0x18019ab2a  test    rsi, rsi
0x18019ab2d  jnz     short loc_18019AB37
0x18019ab2f  mov     r15d, r14d
0x18019ab32  jmp     loc_18019B4FC
0x18019ab37  mov     rax, [rsi]
0x18019ab3a  mov     rcx, rsi
0x18019ab3d  mov     rax, [rax+10h]
0x18019ab41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ab46  mov     r15d, eax
0x18019ab49  test    eax, eax
0x18019ab4b  jz      short loc_18019AB6B
0x18019ab4d  mov     rcx, [rsp+268h+var_218]
0x18019ab52  test    rcx, rcx
0x18019ab55  jz      short loc_18019AB66
0x18019ab57  mov     rax, [rcx]
0x18019ab5a  mov     edx, r14d
0x18019ab5d  mov     rax, [rax]
0x18019ab60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ab65  nop
0x18019ab66  jmp     loc_18019B4FC
0x18019ab6b  mov     rax, [rsi]
0x18019ab6e  mov     rcx, rsi
0x18019ab71  mov     rax, [rax+8]
0x18019ab75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ab7a  mov     r15d, eax
0x18019ab7d  test    eax, eax
0x18019ab7f  jz      short loc_18019AB9F
0x18019ab81  mov     rcx, [rsp+268h+var_218]
0x18019ab86  test    rcx, rcx
0x18019ab89  jz      short loc_18019AB9A
0x18019ab8b  mov     rax, [rcx]
0x18019ab8e  mov     edx, r14d
0x18019ab91  mov     rax, [rax]
0x18019ab94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ab99  nop
0x18019ab9a  jmp     loc_18019B4FC
0x18019ab9f  mov     r14d, edi
0x18019aba2  mov     rax, [rsi+108h]
0x18019aba9  sub     rax, [rsi+100h]
0x18019abb0  sar     rax, 4
0x18019abb4  cmp     r14d, eax
0x18019abb7  jnb     loc_18019B4C4
0x18019abbd  lea     r8, [rsp+268h+instance]; instance
0x18019abc5  lea     rdx, MDM_Policy_Result01_System02_rtti; classDecl
0x18019abcc  mov     rcx, r12; context
0x18019abcf  call    MI_Context_ConstructInstance
0x18019abd4  mov     r15d, eax
0x18019abd7  test    eax, eax
0x18019abd9  jz      short loc_18019ABFB
0x18019abdb  mov     rcx, [rbx]
0x18019abde  test    rcx, rcx
0x18019abe1  jz      short loc_18019ABF6
0x18019abe3  mov     rax, [rcx]
0x18019abe6  mov     edx, 1
0x18019abeb  mov     rax, [rax]
0x18019abee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019abf3  mov     [rbx], rdi
0x18019abf6  jmp     loc_18019B4FC
0x18019abfb  mov     [rsp+268h+var_220], 1
0x18019ac00  mov     rax, [rsi]
0x18019ac03  lea     r9, [rsp+268h+String]
0x18019ac08  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x18019ac0f  mov     edx, r14d
0x18019ac12  mov     rcx, rsi
0x18019ac15  mov     rax, [rax+18h]
0x18019ac19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ac1e  test    eax, eax
0x18019ac20  jnz     short loc_18019AC39
0x18019ac22  mov     rdx, [rsp+268h+String]
0x18019ac27  test    rdx, rdx
0x18019ac2a  jz      short loc_18019AC39
0x18019ac2c  lea     rcx, [rsp+268h+instance]
0x18019ac34  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18019ac39  mov     rax, [rsi]
0x18019ac3c  lea     r9, [rsp+268h+String]
0x18019ac41  lea     r8, aSystem; "System"
0x18019ac48  mov     edx, r14d
0x18019ac4b  mov     rcx, rsi
0x18019ac4e  mov     rax, [rax+18h]
0x18019ac52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ac57  test    eax, eax
0x18019ac59  jnz     short loc_18019AC72
0x18019ac5b  mov     rdx, [rsp+268h+String]
0x18019ac60  test    rdx, rdx
0x18019ac63  jz      short loc_18019AC72
0x18019ac65  lea     rcx, [rsp+268h+instance]
0x18019ac6d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18019ac72  cmp     r13b, 1
0x18019ac76  jnz     short loc_18019AC9A
0x18019ac78  lea     rdx, [rsp+268h+instance]
0x18019ac80  mov     rcx, r12; self
0x18019ac83  call    MI_Instance_Destruct
0x18019ac88  lea     rcx, [rsp+268h+instance]; self
0x18019ac90  call    MI_Instance_Destruct
0x18019ac95  jmp     loc_18019B4B7
0x18019ac9a  mov     rax, [rsi]
0x18019ac9d  lea     r9, [rsp+268h+String]
0x18019aca2  lea     r8, aAllowbuildprev; "AllowBuildPreview"
0x18019aca9  mov     edx, r14d
0x18019acac  mov     rcx, rsi
0x18019acaf  mov     rax, [rax+18h]
0x18019acb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019acb8  test    eax, eax
0x18019acba  jnz     short loc_18019ACDB
0x18019acbc  mov     rcx, [rsp+268h+String]; String
0x18019acc1  test    rcx, rcx
0x18019acc4  jz      short loc_18019ACDB
0x18019acc6  call    cs:__imp__wtoi
0x18019accc  mov     [rsp+268h+var_158], eax
0x18019acd3  mov     [rsp+268h+var_154], 1
0x18019acdb  mov     rax, [rsi]
0x18019acde  lea     r9, [rsp+268h+String]
0x18019ace3  lea     r8, aAllowcommercia; "AllowCommercialDataPipeline"
0x18019acea  mov     edx, r14d
0x18019aced  mov     rcx, rsi
0x18019acf0  mov     rax, [rax+18h]
0x18019acf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019acf9  test    eax, eax
0x18019acfb  jnz     short loc_18019AD1C
0x18019acfd  mov     rcx, [rsp+268h+String]; String
0x18019ad02  test    rcx, rcx
0x18019ad05  jz      short loc_18019AD1C
0x18019ad07  call    cs:__imp__wtoi
0x18019ad0d  mov     [rsp+268h+var_150], eax
0x18019ad14  mov     [rsp+268h+var_14C], 1
0x18019ad1c  mov     rax, [rsi]
0x18019ad1f  lea     r9, [rsp+268h+String]
0x18019ad24  lea     r8, aAllowdesktopan; "AllowDesktopAnalyticsProcessing"
0x18019ad2b  mov     edx, r14d
0x18019ad2e  mov     rcx, rsi
0x18019ad31  mov     rax, [rax+18h]
0x18019ad35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ad3a  test    eax, eax
0x18019ad3c  jnz     short loc_18019AD5D
0x18019ad3e  mov     rcx, [rsp+268h+String]; String
0x18019ad43  test    rcx, rcx
0x18019ad46  jz      short loc_18019AD5D
0x18019ad48  call    cs:__imp__wtoi
0x18019ad4e  mov     [rsp+268h+var_148], eax
0x18019ad55  mov     [rsp+268h+var_144], 1
0x18019ad5d  mov     rax, [rsi]
0x18019ad60  lea     r9, [rsp+268h+String]
0x18019ad65  lea     r8, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x18019ad6c  mov     edx, r14d
0x18019ad6f  mov     rcx, rsi
0x18019ad72  mov     rax, [rax+18h]
0x18019ad76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ad7b  test    eax, eax
0x18019ad7d  jnz     short loc_18019AD9E
0x18019ad7f  mov     rcx, [rsp+268h+String]; String
0x18019ad84  test    rcx, rcx
0x18019ad87  jz      short loc_18019AD9E
0x18019ad89  call    cs:__imp__wtoi
0x18019ad8f  mov     [rsp+268h+var_140], eax
0x18019ad96  mov     [rsp+268h+var_13C], 1
0x18019ad9e  mov     rax, [rsi]
0x18019ada1  lea     r9, [rsp+268h+String]
0x18019ada6  lea     r8, aAllowembeddedm; "AllowEmbeddedMode"
0x18019adad  mov     edx, r14d
0x18019adb0  mov     rcx, rsi
0x18019adb3  mov     rax, [rax+18h]
0x18019adb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019adbc  test    eax, eax
0x18019adbe  jnz     short loc_18019ADDF
0x18019adc0  mov     rcx, [rsp+268h+String]; String
0x18019adc5  test    rcx, rcx
0x18019adc8  jz      short loc_18019ADDF
0x18019adca  call    cs:__imp__wtoi
0x18019add0  mov     [rsp+268h+var_138], eax
0x18019add7  mov     [rsp+268h+var_134], 1
0x18019addf  mov     rax, [rsi]
0x18019ade2  lea     r9, [rsp+268h+String]
0x18019ade7  lea     r8, aAllowexperimen; "AllowExperimentation"
0x18019adee  mov     edx, r14d
0x18019adf1  mov     rcx, rsi
0x18019adf4  mov     rax, [rax+18h]
0x18019adf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019adfd  test    eax, eax
0x18019adff  jnz     short loc_18019AE20
0x18019ae01  mov     rcx, [rsp+268h+String]; String
0x18019ae06  test    rcx, rcx
0x18019ae09  jz      short loc_18019AE20
0x18019ae0b  call    cs:__imp__wtoi
0x18019ae11  mov     [rsp+268h+var_130], eax
0x18019ae18  mov     [rsp+268h+var_12C], 1
0x18019ae20  mov     rax, [rsi]
0x18019ae23  lea     r9, [rsp+268h+String]
0x18019ae28  lea     r8, aAllowfontprovi; "AllowFontProviders"
0x18019ae2f  mov     edx, r14d
0x18019ae32  mov     rcx, rsi
0x18019ae35  mov     rax, [rax+18h]
0x18019ae39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ae3e  test    eax, eax
0x18019ae40  jnz     short loc_18019AE61
0x18019ae42  mov     rcx, [rsp+268h+String]; String
0x18019ae47  test    rcx, rcx
0x18019ae4a  jz      short loc_18019AE61
0x18019ae4c  call    cs:__imp__wtoi
0x18019ae52  mov     [rsp+268h+var_128], eax
0x18019ae59  mov     [rsp+268h+var_124], 1
0x18019ae61  mov     rax, [rsi]
0x18019ae64  lea     r9, [rsp+268h+String]
0x18019ae69  lea     r8, aAllowlocation; "AllowLocation"
0x18019ae70  mov     edx, r14d
0x18019ae73  mov     rcx, rsi
0x18019ae76  mov     rax, [rax+18h]
0x18019ae7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ae7f  test    eax, eax
0x18019ae81  jnz     short loc_18019AEA2
0x18019ae83  mov     rcx, [rsp+268h+String]; String
0x18019ae88  test    rcx, rcx
0x18019ae8b  jz      short loc_18019AEA2
0x18019ae8d  call    cs:__imp__wtoi
0x18019ae93  mov     [rsp+268h+var_120], eax
0x18019ae9a  mov     [rsp+268h+var_11C], 1
0x18019aea2  mov     rax, [rsi]
0x18019aea5  lea     r9, [rsp+268h+String]
0x18019aeaa  lea     r8, aAllowmicrosoft_3; "AllowMicrosoftManagedDesktopProcessing"
0x18019aeb1  mov     edx, r14d
0x18019aeb4  mov     rcx, rsi
0x18019aeb7  mov     rax, [rax+18h]
0x18019aebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019aec0  test    eax, eax
  ... truncated ...
```
