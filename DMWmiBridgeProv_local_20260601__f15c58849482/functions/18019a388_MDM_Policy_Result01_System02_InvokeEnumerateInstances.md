# MDM_Policy_Result01_System02_InvokeEnumerateInstances

- ea: `0x18019a388`
- end: `0x18019b019`
- name: `MDM_Policy_Result01_System02_InvokeEnumerateInstances`
- size: `3217`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180199520`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x1800052e8`
- `0x180005470`
- `0x1800055f8`
- `0x180005aac`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18019a388`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18019a69a`
- `msvcrt!_wtoi` at `0x18019a6e1`
- `msvcrt!_wtoi` at `0x18019a728`
- `msvcrt!_wtoi` at `0x18019a76f`
- `msvcrt!_wtoi` at `0x18019a7b6`
- `msvcrt!_wtoi` at `0x18019a7fd`
- `msvcrt!_wtoi` at `0x18019a844`
- `msvcrt!_wtoi` at `0x18019a88b`
- `msvcrt!_wtoi` at `0x18019a8d2`
- `msvcrt!_wtoi` at `0x18019a919`
- `msvcrt!_wtoi` at `0x18019a960`
- `msvcrt!_wtoi` at `0x18019a9a7`
- `msvcrt!_wtoi` at `0x18019a9ee`
- `msvcrt!_wtoi` at `0x18019aa35`
- `msvcrt!_wtoi` at `0x18019aaee`
- `msvcrt!_wtoi` at `0x18019ab35`
- `msvcrt!_wtoi` at `0x18019ab7c`
- `msvcrt!_wtoi` at `0x18019abc3`
- `msvcrt!_wtoi` at `0x18019ac0a`
- `msvcrt!_wtoi` at `0x18019ac51`
- `msvcrt!_wtoi` at `0x18019ac98`
- `msvcrt!_wtoi` at `0x18019acdf`
- `msvcrt!_wtoi` at `0x18019ad5f`
- `msvcrt!_wtoi` at `0x18019ada6`
- `msvcrt!_wtoi` at `0x18019aded`
- `msvcrt!_wtoi` at `0x18019ae34`
- `msvcrt!_wtoi` at `0x18019ae7b`
- `msvcrt!_wtoi` at `0x18019aefb`
- `msvcrt!_wtoi` at `0x18019a69a`
- `msvcrt!_wtoi` at `0x18019a6e1`
- `msvcrt!_wtoi` at `0x18019a728`
- `msvcrt!_wtoi` at `0x18019a76f`
- `msvcrt!_wtoi` at `0x18019a7b6`
- `msvcrt!_wtoi` at `0x18019a7fd`
- `msvcrt!_wtoi` at `0x18019a844`
- `msvcrt!_wtoi` at `0x18019a88b`
- `msvcrt!_wtoi` at `0x18019a8d2`
- `msvcrt!_wtoi` at `0x18019a919`
- `msvcrt!_wtoi` at `0x18019a960`
- `msvcrt!_wtoi` at `0x18019a9a7`
- `msvcrt!_wtoi` at `0x18019a9ee`
- `msvcrt!_wtoi` at `0x18019aa35`
- `msvcrt!_wtoi` at `0x18019aaee`
- `msvcrt!_wtoi` at `0x18019ab35`
- `msvcrt!_wtoi` at `0x18019ab7c`
- `msvcrt!_wtoi` at `0x18019abc3`
- `msvcrt!_wtoi` at `0x18019ac0a`
- `msvcrt!_wtoi` at `0x18019ac51`
- `msvcrt!_wtoi` at `0x18019ac98`
- `msvcrt!_wtoi` at `0x18019acdf`
- `msvcrt!_wtoi` at `0x18019ad5f`
- `msvcrt!_wtoi` at `0x18019ada6`
- `msvcrt!_wtoi` at `0x18019aded`
- `msvcrt!_wtoi` at `0x18019ae34`
- `msvcrt!_wtoi` at `0x18019ae7b`
- `msvcrt!_wtoi` at `0x18019aefb`

## string_xrefs

- `0x18019a6bd`: `AllowCommercialDataPipeline`
- `0x18019a983`: `AllowUpdateComplianceProcessing`
- `0x18019aa91`: `ConfigureMicrosoft365UploadEndpoint`
- `0x18019aaca`: `ConfigureTelemetryOptInChangeNotification`
- `0x18019ab11`: `ConfigureTelemetryOptInSettingsUx`
- `0x18019ab58`: `DisableDeviceDelete`
- `0x18019abe6`: `DisableDirectXDatabaseUpdate`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_System02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r15d
  _QWORD *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-228h] BYREF
  char v11; // [rsp+48h] [rbp-220h]
  _QWORD *v12; // [rsp+50h] [rbp-218h] BYREF
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
  v6 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Result01_System02_NodeList, 34, 2, &v12);
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
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_System02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_134;
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
                    L"System",
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
                      L"AllowBuildPreview",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowCommercialDataPipeline",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowDesktopAnalyticsProcessing",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowDeviceNameInDiagnosticData",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowEmbeddedMode",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowExperimentation",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowFontProviders",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowLocation",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowMicrosoftManagedDesktopProcessing",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowStorageCard",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowTelemetry",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowUpdateComplianceProcessing",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowUserToResetPhone",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowWUfBCloudProcessing",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"BootStartDriverInitialization",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureMicrosoft365UploadEndpoint",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureTelemetryOptInChangeNotification",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureTelemetryOptInSettingsUx",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableDeviceDelete",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableDiagnosticDataViewer",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableDirectXDatabaseUpdate",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableEnterpriseAuthProxy",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableOneDriveFileSync",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableOneSettingsDownloads",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableSystemRestore",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"EnableOneSettingsAuditing",
                      &String)
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"FeedbackHubAlwaysSaveDiagnosticsLocally",
                      &String)
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"LimitDiagnosticLogCollection",
                      &String)
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"LimitDumpCollection",
                      &String)
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"LimitEnhancedDiagnosticDataWindowsAnalytics",
                      &String)
                && String )
              {
                v72 = _wtoi(String);
                v73 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"TelemetryProxy",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_ConsistentMimeHandlingInternetExplorerProcesses(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
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
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18019a388  mov     [rsp+arg_8], rbx
0x18019a38d  mov     [rsp+arg_10], rsi
0x18019a392  push    rdi
0x18019a393  push    r12
0x18019a395  push    r13
0x18019a397  push    r14
0x18019a399  push    r15
0x18019a39b  sub     rsp, 240h
0x18019a3a2  mov     rax, cs:__security_cookie
0x18019a3a9  xor     rax, rsp
0x18019a3ac  mov     [rsp+268h+var_38], rax
0x18019a3b4  mov     r13b, dl
0x18019a3b7  mov     r12, rcx
0x18019a3ba  xor     edx, edx; Val
0x18019a3bc  mov     r8d, 180h; Size
0x18019a3c2  lea     rcx, [rsp+268h+instance]; void *
0x18019a3ca  call    memset_0
0x18019a3cf  xor     edi, edi
0x18019a3d1  mov     [rsp+268h+var_220], dil
0x18019a3d6  mov     [rsp+268h+String], rdi
0x18019a3db  mov     [rsp+268h+var_1E0], edi
0x18019a3e2  mov     [rsp+268h+var_1DC], dil
0x18019a3ea  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019a3f1  mov     [rsp+268h+var_210], rax
0x18019a3f6  lea     rax, [rsp+268h+var_1E0]
0x18019a3fe  mov     [rsp+268h+var_208], rax
0x18019a403  lea     rax, aMdmPolicyResul_159; "MDM_Policy_Result01_System02"
0x18019a40a  mov     [rsp+268h+var_200], rax
0x18019a40f  lea     rcx, [rsp+268h+var_1E0]
0x18019a417  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019a41c  mov     eax, cs:dword_180380B68
0x18019a422  cmp     eax, 5
0x18019a425  jbe     short loc_18019A497
0x18019a427  mov     rdx, 200000000000h
0x18019a431  lea     rcx, dword_180380B68
0x18019a438  call    _tlgKeywordOn
0x18019a43d  test    al, al
0x18019a43f  jz      short loc_18019A497
0x18019a441  cmp     [rsp+268h+var_1DC], dil
0x18019a449  jz      short loc_18019A479
0x18019a44b  cmp     [rsp+268h+var_1C8], edi
0x18019a452  jnz     short loc_18019A46F
0x18019a454  cmp     [rsp+268h+var_1C4], edi
0x18019a45b  jnz     short loc_18019A46F
0x18019a45d  cmp     [rsp+268h+var_1C0], edi
0x18019a464  jnz     short loc_18019A46F
0x18019a466  cmp     [rsp+268h+var_1BC], edi
0x18019a46d  jz      short loc_18019A479
0x18019a46f  lea     r9, [rsp+268h+var_1C8]
0x18019a477  jmp     short loc_18019A47C
0x18019a479  mov     r9, rdi
0x18019a47c  lea     r8, [rsp+268h+var_1D8]
0x18019a484  lea     rdx, word_180367B1E
0x18019a48b  lea     rcx, dword_180380B68
0x18019a492  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019a497  lea     rcx, [rsp+268h+var_210]; this
0x18019a49c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18019a4a1  nop
0x18019a4a2  mov     [rsp+268h+var_218], rdi
0x18019a4a7  lea     rax, [rsp+268h+var_218]
0x18019a4ac  mov     [rsp+268h+var_238], rax
0x18019a4b1  mov     [rsp+268h+var_240], 2
0x18019a4b9  mov     [rsp+268h+var_248], 22h ; '"'
0x18019a4c1  lea     r9, ?MDM_Policy_Result01_System02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_System02_NodeList
0x18019a4c8  xor     r8d, r8d
0x18019a4cb  xor     edx, edx
0x18019a4cd  mov     rcx, r12
0x18019a4d0  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019a4d5  mov     r15d, eax
0x18019a4d8  test    eax, eax
0x18019a4da  jz      short loc_18019A4E1
0x18019a4dc  jmp     loc_18019AF78
0x18019a4e1  lea     rbx, [rsp+268h+var_218]
0x18019a4e6  mov     [rsp+268h+var_1F0], rbx
0x18019a4eb  mov     r14d, 1
0x18019a4f1  mov     [rsp+268h+var_1E8], r14b
0x18019a4f9  mov     rsi, [rsp+268h+var_218]
0x18019a4fe  test    rsi, rsi
0x18019a501  jnz     short loc_18019A50B
0x18019a503  mov     r15d, r14d
0x18019a506  jmp     loc_18019AF78
0x18019a50b  mov     rax, [rsi]
0x18019a50e  mov     rcx, rsi
0x18019a511  mov     rax, [rax+10h]
0x18019a515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a51a  mov     r15d, eax
0x18019a51d  test    eax, eax
0x18019a51f  jz      short loc_18019A53F
0x18019a521  mov     rcx, [rsp+268h+var_218]
0x18019a526  test    rcx, rcx
0x18019a529  jz      short loc_18019A53A
0x18019a52b  mov     rax, [rcx]
0x18019a52e  mov     edx, r14d
0x18019a531  mov     rax, [rax]
0x18019a534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a539  nop
0x18019a53a  jmp     loc_18019AF78
0x18019a53f  mov     rax, [rsi]
0x18019a542  mov     rcx, rsi
0x18019a545  mov     rax, [rax+8]
0x18019a549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a54e  mov     r15d, eax
0x18019a551  test    eax, eax
0x18019a553  jz      short loc_18019A573
0x18019a555  mov     rcx, [rsp+268h+var_218]
0x18019a55a  test    rcx, rcx
0x18019a55d  jz      short loc_18019A56E
0x18019a55f  mov     rax, [rcx]
0x18019a562  mov     edx, r14d
0x18019a565  mov     rax, [rax]
0x18019a568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a56d  nop
0x18019a56e  jmp     loc_18019AF78
0x18019a573  mov     r14d, edi
0x18019a576  mov     rax, [rsi+108h]
0x18019a57d  sub     rax, [rsi+100h]
0x18019a584  sar     rax, 4
0x18019a588  cmp     r14d, eax
0x18019a58b  jnb     loc_18019AF40
0x18019a591  lea     r8, [rsp+268h+instance]; instance
0x18019a599  lea     rdx, MDM_Policy_Result01_System02_rtti; classDecl
0x18019a5a0  mov     rcx, r12; context
0x18019a5a3  call    MI_Context_ConstructInstance
0x18019a5a8  mov     r15d, eax
0x18019a5ab  test    eax, eax
0x18019a5ad  jz      short loc_18019A5CF
0x18019a5af  mov     rcx, [rbx]
0x18019a5b2  test    rcx, rcx
0x18019a5b5  jz      short loc_18019A5CA
0x18019a5b7  mov     rax, [rcx]
0x18019a5ba  mov     edx, 1
0x18019a5bf  mov     rax, [rax]
0x18019a5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a5c7  mov     [rbx], rdi
0x18019a5ca  jmp     loc_18019AF78
0x18019a5cf  mov     [rsp+268h+var_220], 1
0x18019a5d4  mov     rax, [rsi]
0x18019a5d7  lea     r9, [rsp+268h+String]
0x18019a5dc  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x18019a5e3  mov     edx, r14d
0x18019a5e6  mov     rcx, rsi
0x18019a5e9  mov     rax, [rax+18h]
0x18019a5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a5f2  test    eax, eax
0x18019a5f4  jnz     short loc_18019A60D
0x18019a5f6  mov     rdx, [rsp+268h+String]
0x18019a5fb  test    rdx, rdx
0x18019a5fe  jz      short loc_18019A60D
0x18019a600  lea     rcx, [rsp+268h+instance]
0x18019a608  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18019a60d  mov     rax, [rsi]
0x18019a610  lea     r9, [rsp+268h+String]
0x18019a615  lea     r8, aSystem; "System"
0x18019a61c  mov     edx, r14d
0x18019a61f  mov     rcx, rsi
0x18019a622  mov     rax, [rax+18h]
0x18019a626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a62b  test    eax, eax
0x18019a62d  jnz     short loc_18019A646
0x18019a62f  mov     rdx, [rsp+268h+String]
0x18019a634  test    rdx, rdx
0x18019a637  jz      short loc_18019A646
0x18019a639  lea     rcx, [rsp+268h+instance]
0x18019a641  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18019a646  cmp     r13b, 1
0x18019a64a  jnz     short loc_18019A66E
0x18019a64c  lea     rdx, [rsp+268h+instance]
0x18019a654  mov     rcx, r12; self
0x18019a657  call    MI_Instance_Destruct
0x18019a65c  lea     rcx, [rsp+268h+instance]; self
0x18019a664  call    MI_Instance_Destruct
0x18019a669  jmp     loc_18019AF33
0x18019a66e  mov     rax, [rsi]
0x18019a671  lea     r9, [rsp+268h+String]
0x18019a676  lea     r8, aAllowbuildprev; "AllowBuildPreview"
0x18019a67d  mov     edx, r14d
0x18019a680  mov     rcx, rsi
0x18019a683  mov     rax, [rax+18h]
0x18019a687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a68c  test    eax, eax
0x18019a68e  jnz     short loc_18019A6B5
0x18019a690  mov     rcx, [rsp+268h+String]; String
0x18019a695  test    rcx, rcx
0x18019a698  jz      short loc_18019A6B5
0x18019a69a  call    cs:__imp__wtoi
0x18019a6a1  nop     dword ptr [rax+rax+00h]
0x18019a6a6  mov     [rsp+268h+var_158], eax
0x18019a6ad  mov     [rsp+268h+var_154], 1
0x18019a6b5  mov     rax, [rsi]
0x18019a6b8  lea     r9, [rsp+268h+String]
0x18019a6bd  lea     r8, aAllowcommercia; "AllowCommercialDataPipeline"
0x18019a6c4  mov     edx, r14d
0x18019a6c7  mov     rcx, rsi
0x18019a6ca  mov     rax, [rax+18h]
0x18019a6ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a6d3  test    eax, eax
0x18019a6d5  jnz     short loc_18019A6FC
0x18019a6d7  mov     rcx, [rsp+268h+String]; String
0x18019a6dc  test    rcx, rcx
0x18019a6df  jz      short loc_18019A6FC
0x18019a6e1  call    cs:__imp__wtoi
0x18019a6e8  nop     dword ptr [rax+rax+00h]
0x18019a6ed  mov     [rsp+268h+var_150], eax
0x18019a6f4  mov     [rsp+268h+var_14C], 1
0x18019a6fc  mov     rax, [rsi]
0x18019a6ff  lea     r9, [rsp+268h+String]
0x18019a704  lea     r8, aAllowdesktopan; "AllowDesktopAnalyticsProcessing"
0x18019a70b  mov     edx, r14d
0x18019a70e  mov     rcx, rsi
0x18019a711  mov     rax, [rax+18h]
0x18019a715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a71a  test    eax, eax
0x18019a71c  jnz     short loc_18019A743
0x18019a71e  mov     rcx, [rsp+268h+String]; String
0x18019a723  test    rcx, rcx
0x18019a726  jz      short loc_18019A743
0x18019a728  call    cs:__imp__wtoi
0x18019a72f  nop     dword ptr [rax+rax+00h]
0x18019a734  mov     [rsp+268h+var_148], eax
0x18019a73b  mov     [rsp+268h+var_144], 1
0x18019a743  mov     rax, [rsi]
0x18019a746  lea     r9, [rsp+268h+String]
0x18019a74b  lea     r8, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x18019a752  mov     edx, r14d
0x18019a755  mov     rcx, rsi
0x18019a758  mov     rax, [rax+18h]
0x18019a75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a761  test    eax, eax
0x18019a763  jnz     short loc_18019A78A
0x18019a765  mov     rcx, [rsp+268h+String]; String
0x18019a76a  test    rcx, rcx
0x18019a76d  jz      short loc_18019A78A
0x18019a76f  call    cs:__imp__wtoi
0x18019a776  nop     dword ptr [rax+rax+00h]
0x18019a77b  mov     [rsp+268h+var_140], eax
0x18019a782  mov     [rsp+268h+var_13C], 1
0x18019a78a  mov     rax, [rsi]
0x18019a78d  lea     r9, [rsp+268h+String]
0x18019a792  lea     r8, aAllowembeddedm; "AllowEmbeddedMode"
0x18019a799  mov     edx, r14d
0x18019a79c  mov     rcx, rsi
0x18019a79f  mov     rax, [rax+18h]
0x18019a7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a7a8  test    eax, eax
0x18019a7aa  jnz     short loc_18019A7D1
0x18019a7ac  mov     rcx, [rsp+268h+String]; String
0x18019a7b1  test    rcx, rcx
0x18019a7b4  jz      short loc_18019A7D1
0x18019a7b6  call    cs:__imp__wtoi
0x18019a7bd  nop     dword ptr [rax+rax+00h]
0x18019a7c2  mov     [rsp+268h+var_138], eax
0x18019a7c9  mov     [rsp+268h+var_134], 1
0x18019a7d1  mov     rax, [rsi]
0x18019a7d4  lea     r9, [rsp+268h+String]
0x18019a7d9  lea     r8, aAllowexperimen; "AllowExperimentation"
0x18019a7e0  mov     edx, r14d
0x18019a7e3  mov     rcx, rsi
0x18019a7e6  mov     rax, [rax+18h]
0x18019a7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a7ef  test    eax, eax
0x18019a7f1  jnz     short loc_18019A818
0x18019a7f3  mov     rcx, [rsp+268h+String]; String
0x18019a7f8  test    rcx, rcx
0x18019a7fb  jz      short loc_18019A818
0x18019a7fd  call    cs:__imp__wtoi
0x18019a804  nop     dword ptr [rax+rax+00h]
0x18019a809  mov     [rsp+268h+var_130], eax
0x18019a810  mov     [rsp+268h+var_12C], 1
0x18019a818  mov     rax, [rsi]
0x18019a81b  lea     r9, [rsp+268h+String]
0x18019a820  lea     r8, aAllowfontprovi; "AllowFontProviders"
0x18019a827  mov     edx, r14d
0x18019a82a  mov     rcx, rsi
0x18019a82d  mov     rax, [rax+18h]
0x18019a831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a836  test    eax, eax
0x18019a838  jnz     short loc_18019A85F
0x18019a83a  mov     rcx, [rsp+268h+String]; String
0x18019a83f  test    rcx, rcx
0x18019a842  jz      short loc_18019A85F
0x18019a844  call    cs:__imp__wtoi
0x18019a84b  nop     dword ptr [rax+rax+00h]
0x18019a850  mov     [rsp+268h+var_128], eax
0x18019a857  mov     [rsp+268h+var_124], 1
0x18019a85f  mov     rax, [rsi]
0x18019a862  lea     r9, [rsp+268h+String]
0x18019a867  lea     r8, aAllowlocation; "AllowLocation"
0x18019a86e  mov     edx, r14d
0x18019a871  mov     rcx, rsi
0x18019a874  mov     rax, [rax+18h]
0x18019a878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a87d  test    eax, eax
0x18019a87f  jnz     short loc_18019A8A6
0x18019a881  mov     rcx, [rsp+268h+String]; String
0x18019a886  test    rcx, rcx
0x18019a889  jz      short loc_18019A8A6
0x18019a88b  call    cs:__imp__wtoi
0x18019a892  nop     dword ptr [rax+rax+00h]
0x18019a897  mov     [rsp+268h+var_120], eax
0x18019a89e  mov     [rsp+268h+var_11C], 1
  ... truncated ...
```
