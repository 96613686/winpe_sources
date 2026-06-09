# MDM_Policy_Config01_System02_InvokeEnumerateInstances

- ea: `0x1800e2c78`
- end: `0x1800e3909`
- name: `MDM_Policy_Config01_System02_InvokeEnumerateInstances`
- size: `3217`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e1e10`

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
- `0x1800e2c78`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e2f8a`
- `msvcrt!_wtoi` at `0x1800e2fd1`
- `msvcrt!_wtoi` at `0x1800e3018`
- `msvcrt!_wtoi` at `0x1800e305f`
- `msvcrt!_wtoi` at `0x1800e30a6`
- `msvcrt!_wtoi` at `0x1800e30ed`
- `msvcrt!_wtoi` at `0x1800e3134`
- `msvcrt!_wtoi` at `0x1800e317b`
- `msvcrt!_wtoi` at `0x1800e31c2`
- `msvcrt!_wtoi` at `0x1800e3209`
- `msvcrt!_wtoi` at `0x1800e3250`
- `msvcrt!_wtoi` at `0x1800e3297`
- `msvcrt!_wtoi` at `0x1800e32de`
- `msvcrt!_wtoi` at `0x1800e3325`
- `msvcrt!_wtoi` at `0x1800e33de`
- `msvcrt!_wtoi` at `0x1800e3425`
- `msvcrt!_wtoi` at `0x1800e346c`
- `msvcrt!_wtoi` at `0x1800e34b3`
- `msvcrt!_wtoi` at `0x1800e34fa`
- `msvcrt!_wtoi` at `0x1800e3541`
- `msvcrt!_wtoi` at `0x1800e3588`
- `msvcrt!_wtoi` at `0x1800e35cf`
- `msvcrt!_wtoi` at `0x1800e364f`
- `msvcrt!_wtoi` at `0x1800e3696`
- `msvcrt!_wtoi` at `0x1800e36dd`
- `msvcrt!_wtoi` at `0x1800e3724`
- `msvcrt!_wtoi` at `0x1800e376b`
- `msvcrt!_wtoi` at `0x1800e37eb`
- `msvcrt!_wtoi` at `0x1800e2f8a`
- `msvcrt!_wtoi` at `0x1800e2fd1`
- `msvcrt!_wtoi` at `0x1800e3018`
- `msvcrt!_wtoi` at `0x1800e305f`
- `msvcrt!_wtoi` at `0x1800e30a6`
- `msvcrt!_wtoi` at `0x1800e30ed`
- `msvcrt!_wtoi` at `0x1800e3134`
- `msvcrt!_wtoi` at `0x1800e317b`
- `msvcrt!_wtoi` at `0x1800e31c2`
- `msvcrt!_wtoi` at `0x1800e3209`
- `msvcrt!_wtoi` at `0x1800e3250`
- `msvcrt!_wtoi` at `0x1800e3297`
- `msvcrt!_wtoi` at `0x1800e32de`
- `msvcrt!_wtoi` at `0x1800e3325`
- `msvcrt!_wtoi` at `0x1800e33de`
- `msvcrt!_wtoi` at `0x1800e3425`
- `msvcrt!_wtoi` at `0x1800e346c`
- `msvcrt!_wtoi` at `0x1800e34b3`
- `msvcrt!_wtoi` at `0x1800e34fa`
- `msvcrt!_wtoi` at `0x1800e3541`
- `msvcrt!_wtoi` at `0x1800e3588`
- `msvcrt!_wtoi` at `0x1800e35cf`
- `msvcrt!_wtoi` at `0x1800e364f`
- `msvcrt!_wtoi` at `0x1800e3696`
- `msvcrt!_wtoi` at `0x1800e36dd`
- `msvcrt!_wtoi` at `0x1800e3724`
- `msvcrt!_wtoi` at `0x1800e376b`
- `msvcrt!_wtoi` at `0x1800e37eb`

## string_xrefs

- `0x1800e2fad`: `AllowCommercialDataPipeline`
- `0x1800e3273`: `AllowUpdateComplianceProcessing`
- `0x1800e3381`: `ConfigureMicrosoft365UploadEndpoint`
- `0x1800e33ba`: `ConfigureTelemetryOptInChangeNotification`
- `0x1800e3401`: `ConfigureTelemetryOptInSettingsUx`
- `0x1800e3448`: `DisableDeviceDelete`
- `0x1800e34d6`: `DisableDirectXDatabaseUpdate`
- `0x1800e2ecc`: `./Vendor/MSFT/Policy/Config`
- `0x1800e2cf3`: `MDM_Policy_Config01_System02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_System02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-228h] BYREF
  char v14; // [rsp+48h] [rbp-220h]
  _QWORD *v15; // [rsp+50h] [rbp-218h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-210h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-1F8h] BYREF
  char v18; // [rsp+80h] [rbp-1E8h]
  int v19; // [rsp+88h] [rbp-1E0h] BYREF
  char v20; // [rsp+8Ch] [rbp-1DCh]
  _BYTE v21[16]; // [rsp+90h] [rbp-1D8h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-1C8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-1B8h] BYREF
  int v24; // [rsp+110h] [rbp-158h]
  char v25; // [rsp+114h] [rbp-154h]
  int v26; // [rsp+118h] [rbp-150h]
  char v27; // [rsp+11Ch] [rbp-14Ch]
  int v28; // [rsp+120h] [rbp-148h]
  char v29; // [rsp+124h] [rbp-144h]
  int v30; // [rsp+128h] [rbp-140h]
  char v31; // [rsp+12Ch] [rbp-13Ch]
  int v32; // [rsp+130h] [rbp-138h]
  char v33; // [rsp+134h] [rbp-134h]
  int v34; // [rsp+138h] [rbp-130h]
  char v35; // [rsp+13Ch] [rbp-12Ch]
  int v36; // [rsp+140h] [rbp-128h]
  char v37; // [rsp+144h] [rbp-124h]
  int v38; // [rsp+148h] [rbp-120h]
  char v39; // [rsp+14Ch] [rbp-11Ch]
  int v40; // [rsp+150h] [rbp-118h]
  char v41; // [rsp+154h] [rbp-114h]
  int v42; // [rsp+158h] [rbp-110h]
  char v43; // [rsp+15Ch] [rbp-10Ch]
  int v44; // [rsp+160h] [rbp-108h]
  char v45; // [rsp+164h] [rbp-104h]
  int v46; // [rsp+168h] [rbp-100h]
  char v47; // [rsp+16Ch] [rbp-FCh]
  int v48; // [rsp+170h] [rbp-F8h]
  char v49; // [rsp+174h] [rbp-F4h]
  int v50; // [rsp+178h] [rbp-F0h]
  char v51; // [rsp+17Ch] [rbp-ECh]
  int v52; // [rsp+1A0h] [rbp-C8h]
  char v53; // [rsp+1A4h] [rbp-C4h]
  int v54; // [rsp+1A8h] [rbp-C0h]
  char v55; // [rsp+1ACh] [rbp-BCh]
  int v56; // [rsp+1B0h] [rbp-B8h]
  char v57; // [rsp+1B4h] [rbp-B4h]
  int v58; // [rsp+1B8h] [rbp-B0h]
  char v59; // [rsp+1BCh] [rbp-ACh]
  int v60; // [rsp+1C0h] [rbp-A8h]
  char v61; // [rsp+1C4h] [rbp-A4h]
  int v62; // [rsp+1C8h] [rbp-A0h]
  char v63; // [rsp+1CCh] [rbp-9Ch]
  int v64; // [rsp+1D0h] [rbp-98h]
  char v65; // [rsp+1D4h] [rbp-94h]
  int v66; // [rsp+1D8h] [rbp-90h]
  char v67; // [rsp+1DCh] [rbp-8Ch]
  int v68; // [rsp+1F0h] [rbp-78h]
  char v69; // [rsp+1F4h] [rbp-74h]
  int v70; // [rsp+1F8h] [rbp-70h]
  char v71; // [rsp+1FCh] [rbp-6Ch]
  int v72; // [rsp+200h] [rbp-68h]
  char v73; // [rsp+204h] [rbp-64h]
  int v74; // [rsp+208h] [rbp-60h]
  char v75; // [rsp+20Ch] [rbp-5Ch]
  int v76; // [rsp+210h] [rbp-58h]
  char v77; // [rsp+214h] [rbp-54h]
  int v78; // [rsp+228h] [rbp-40h]
  char v79; // [rsp+22Ch] [rbp-3Ch]

  memset_0(&instance, 0, 0x180u);
  v14 = 0;
  String = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_Policy_Config01_System02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18033F9EF,
      v21,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v16, v4);
  try
  {
    v15 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_System02_NodeList, 34, 2, &v15);
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_System02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v15;
                if ( v15 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_145;
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
                      L"System",
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
                        L"AllowBuildPreview",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowCommercialDataPipeline",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowDesktopAnalyticsProcessing",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowDeviceNameInDiagnosticData",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowEmbeddedMode",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowExperimentation",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowFontProviders",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowLocation",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowMicrosoftManagedDesktopProcessing",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowStorageCard",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowTelemetry",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowUpdateComplianceProcessing",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowUserToResetPhone",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowWUfBCloudProcessing",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"BootStartDriverInitialization",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureMicrosoft365UploadEndpoint",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureTelemetryOptInChangeNotification",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureTelemetryOptInSettingsUx",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableDeviceDelete",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableDiagnosticDataViewer",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableDirectXDatabaseUpdate",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableEnterpriseAuthProxy",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableOneDriveFileSync",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableOneSettingsDownloads",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableSystemRestore",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableOneSettingsAuditing",
                        &String)
                  && String )
                {
                  v68 = _wtoi(String);
                  v69 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"FeedbackHubAlwaysSaveDiagnosticsLocally",
                        &String)
                  && String )
                {
                  v70 = _wtoi(String);
                  v71 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"LimitDiagnosticLogCollection",
                        &String)
                  && String )
                {
                  v72 = _wtoi(String);
                  v73 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"LimitDumpCollection",
                        &String)
                  && String )
                {
                  v74 = _wtoi(String);
                  v75 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"LimitEnhancedDiagnosticDataWindowsAnalytics",
                        &String)
                  && String )
                {
                  v76 = _wtoi(String);
                  v77 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TelemetryProxy",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_ConsistentMimeHandlingInternetExplorerProcesses(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TurnOffFileHistory",
                        &String)
                  && String )
                {
                  v78 = _wtoi(String);
                  v79 = 1;
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
    goto LABEL_136;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_136:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (int)v15;
  }
LABEL_145:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18034BBE7,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800e2c78  mov     [rsp+arg_8], rbx
0x1800e2c7d  mov     [rsp+arg_10], rsi
0x1800e2c82  push    rdi
0x1800e2c83  push    r12
0x1800e2c85  push    r13
0x1800e2c87  push    r14
0x1800e2c89  push    r15
0x1800e2c8b  sub     rsp, 240h
0x1800e2c92  mov     rax, cs:__security_cookie
0x1800e2c99  xor     rax, rsp
0x1800e2c9c  mov     [rsp+268h+var_38], rax
0x1800e2ca4  mov     r13b, dl
0x1800e2ca7  mov     r12, rcx
0x1800e2caa  xor     edx, edx; Val
0x1800e2cac  mov     r8d, 180h; Size
0x1800e2cb2  lea     rcx, [rsp+268h+instance]; void *
0x1800e2cba  call    memset_0
0x1800e2cbf  xor     edi, edi
0x1800e2cc1  mov     [rsp+268h+var_220], dil
0x1800e2cc6  mov     [rsp+268h+String], rdi
0x1800e2ccb  mov     [rsp+268h+var_1E0], edi
0x1800e2cd2  mov     [rsp+268h+var_1DC], dil
0x1800e2cda  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e2ce1  mov     [rsp+268h+var_210], rax
0x1800e2ce6  lea     rax, [rsp+268h+var_1E0]
0x1800e2cee  mov     [rsp+268h+var_208], rax
0x1800e2cf3  lea     rax, aMdmPolicyConfi_18; "MDM_Policy_Config01_System02"
0x1800e2cfa  mov     [rsp+268h+var_200], rax
0x1800e2cff  lea     rcx, [rsp+268h+var_1E0]
0x1800e2d07  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e2d0c  mov     eax, cs:dword_180380B68
0x1800e2d12  cmp     eax, 5
0x1800e2d15  jbe     short loc_1800E2D87
0x1800e2d17  mov     rdx, 200000000000h
0x1800e2d21  lea     rcx, dword_180380B68
0x1800e2d28  call    _tlgKeywordOn
0x1800e2d2d  test    al, al
0x1800e2d2f  jz      short loc_1800E2D87
0x1800e2d31  cmp     [rsp+268h+var_1DC], dil
0x1800e2d39  jz      short loc_1800E2D69
0x1800e2d3b  cmp     [rsp+268h+var_1C8], edi
0x1800e2d42  jnz     short loc_1800E2D5F
0x1800e2d44  cmp     [rsp+268h+var_1C4], edi
0x1800e2d4b  jnz     short loc_1800E2D5F
0x1800e2d4d  cmp     [rsp+268h+var_1C0], edi
0x1800e2d54  jnz     short loc_1800E2D5F
0x1800e2d56  cmp     [rsp+268h+var_1BC], edi
0x1800e2d5d  jz      short loc_1800E2D69
0x1800e2d5f  lea     r9, [rsp+268h+var_1C8]
0x1800e2d67  jmp     short loc_1800E2D6C
0x1800e2d69  mov     r9, rdi
0x1800e2d6c  lea     r8, [rsp+268h+var_1D8]
0x1800e2d74  lea     rdx, byte_18033F9EF
0x1800e2d7b  lea     rcx, dword_180380B68
0x1800e2d82  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e2d87  lea     rcx, [rsp+268h+var_210]; this
0x1800e2d8c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800e2d91  nop
0x1800e2d92  mov     [rsp+268h+var_218], rdi
0x1800e2d97  lea     rax, [rsp+268h+var_218]
0x1800e2d9c  mov     [rsp+268h+var_238], rax
0x1800e2da1  mov     [rsp+268h+var_240], 2
0x1800e2da9  mov     [rsp+268h+var_248], 22h ; '"'
0x1800e2db1  lea     r9, ?MDM_Policy_Config01_System02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_System02_NodeList
0x1800e2db8  xor     r8d, r8d
0x1800e2dbb  xor     edx, edx
0x1800e2dbd  mov     rcx, r12
0x1800e2dc0  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e2dc5  mov     r15d, eax
0x1800e2dc8  test    eax, eax
0x1800e2dca  jz      short loc_1800E2DD1
0x1800e2dcc  jmp     loc_1800E3868
0x1800e2dd1  lea     rbx, [rsp+268h+var_218]
0x1800e2dd6  mov     [rsp+268h+var_1F0], rbx
0x1800e2ddb  mov     r14d, 1
0x1800e2de1  mov     [rsp+268h+var_1E8], r14b
0x1800e2de9  mov     rsi, [rsp+268h+var_218]
0x1800e2dee  test    rsi, rsi
0x1800e2df1  jnz     short loc_1800E2DFB
0x1800e2df3  mov     r15d, r14d
0x1800e2df6  jmp     loc_1800E3868
0x1800e2dfb  mov     rax, [rsi]
0x1800e2dfe  mov     rcx, rsi
0x1800e2e01  mov     rax, [rax+10h]
0x1800e2e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2e0a  mov     r15d, eax
0x1800e2e0d  test    eax, eax
0x1800e2e0f  jz      short loc_1800E2E2F
0x1800e2e11  mov     rcx, [rsp+268h+var_218]
0x1800e2e16  test    rcx, rcx
0x1800e2e19  jz      short loc_1800E2E2A
0x1800e2e1b  mov     rax, [rcx]
0x1800e2e1e  mov     edx, r14d
0x1800e2e21  mov     rax, [rax]
0x1800e2e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2e29  nop
0x1800e2e2a  jmp     loc_1800E3868
0x1800e2e2f  mov     rax, [rsi]
0x1800e2e32  mov     rcx, rsi
0x1800e2e35  mov     rax, [rax+8]
0x1800e2e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2e3e  mov     r15d, eax
0x1800e2e41  test    eax, eax
0x1800e2e43  jz      short loc_1800E2E63
0x1800e2e45  mov     rcx, [rsp+268h+var_218]
0x1800e2e4a  test    rcx, rcx
0x1800e2e4d  jz      short loc_1800E2E5E
0x1800e2e4f  mov     rax, [rcx]
0x1800e2e52  mov     edx, r14d
0x1800e2e55  mov     rax, [rax]
0x1800e2e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2e5d  nop
0x1800e2e5e  jmp     loc_1800E3868
0x1800e2e63  mov     r14d, edi
0x1800e2e66  mov     rax, [rsi+108h]
0x1800e2e6d  sub     rax, [rsi+100h]
0x1800e2e74  sar     rax, 4
0x1800e2e78  cmp     r14d, eax
0x1800e2e7b  jnb     loc_1800E3830
0x1800e2e81  lea     r8, [rsp+268h+instance]; instance
0x1800e2e89  lea     rdx, MDM_Policy_Config01_System02_rtti; classDecl
0x1800e2e90  mov     rcx, r12; context
0x1800e2e93  call    MI_Context_ConstructInstance
0x1800e2e98  mov     r15d, eax
0x1800e2e9b  test    eax, eax
0x1800e2e9d  jz      short loc_1800E2EBF
0x1800e2e9f  mov     rcx, [rbx]
0x1800e2ea2  test    rcx, rcx
0x1800e2ea5  jz      short loc_1800E2EBA
0x1800e2ea7  mov     rax, [rcx]
0x1800e2eaa  mov     edx, 1
0x1800e2eaf  mov     rax, [rax]
0x1800e2eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2eb7  mov     [rbx], rdi
0x1800e2eba  jmp     loc_1800E3868
0x1800e2ebf  mov     [rsp+268h+var_220], 1
0x1800e2ec4  mov     rax, [rsi]
0x1800e2ec7  lea     r9, [rsp+268h+String]
0x1800e2ecc  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800e2ed3  mov     edx, r14d
0x1800e2ed6  mov     rcx, rsi
0x1800e2ed9  mov     rax, [rax+18h]
0x1800e2edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2ee2  test    eax, eax
0x1800e2ee4  jnz     short loc_1800E2EFD
0x1800e2ee6  mov     rdx, [rsp+268h+String]
0x1800e2eeb  test    rdx, rdx
0x1800e2eee  jz      short loc_1800E2EFD
0x1800e2ef0  lea     rcx, [rsp+268h+instance]
0x1800e2ef8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e2efd  mov     rax, [rsi]
0x1800e2f00  lea     r9, [rsp+268h+String]
0x1800e2f05  lea     r8, aSystem; "System"
0x1800e2f0c  mov     edx, r14d
0x1800e2f0f  mov     rcx, rsi
0x1800e2f12  mov     rax, [rax+18h]
0x1800e2f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2f1b  test    eax, eax
0x1800e2f1d  jnz     short loc_1800E2F36
0x1800e2f1f  mov     rdx, [rsp+268h+String]
0x1800e2f24  test    rdx, rdx
0x1800e2f27  jz      short loc_1800E2F36
0x1800e2f29  lea     rcx, [rsp+268h+instance]
0x1800e2f31  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e2f36  cmp     r13b, 1
0x1800e2f3a  jnz     short loc_1800E2F5E
0x1800e2f3c  lea     rdx, [rsp+268h+instance]
0x1800e2f44  mov     rcx, r12; self
0x1800e2f47  call    MI_Instance_Destruct
0x1800e2f4c  lea     rcx, [rsp+268h+instance]; self
0x1800e2f54  call    MI_Instance_Destruct
0x1800e2f59  jmp     loc_1800E3823
0x1800e2f5e  mov     rax, [rsi]
0x1800e2f61  lea     r9, [rsp+268h+String]
0x1800e2f66  lea     r8, aAllowbuildprev; "AllowBuildPreview"
0x1800e2f6d  mov     edx, r14d
0x1800e2f70  mov     rcx, rsi
0x1800e2f73  mov     rax, [rax+18h]
0x1800e2f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2f7c  test    eax, eax
0x1800e2f7e  jnz     short loc_1800E2FA5
0x1800e2f80  mov     rcx, [rsp+268h+String]; String
0x1800e2f85  test    rcx, rcx
0x1800e2f88  jz      short loc_1800E2FA5
0x1800e2f8a  call    cs:__imp__wtoi
0x1800e2f91  nop     dword ptr [rax+rax+00h]
0x1800e2f96  mov     [rsp+268h+var_158], eax
0x1800e2f9d  mov     [rsp+268h+var_154], 1
0x1800e2fa5  mov     rax, [rsi]
0x1800e2fa8  lea     r9, [rsp+268h+String]
0x1800e2fad  lea     r8, aAllowcommercia; "AllowCommercialDataPipeline"
0x1800e2fb4  mov     edx, r14d
0x1800e2fb7  mov     rcx, rsi
0x1800e2fba  mov     rax, [rax+18h]
0x1800e2fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2fc3  test    eax, eax
0x1800e2fc5  jnz     short loc_1800E2FEC
0x1800e2fc7  mov     rcx, [rsp+268h+String]; String
0x1800e2fcc  test    rcx, rcx
0x1800e2fcf  jz      short loc_1800E2FEC
0x1800e2fd1  call    cs:__imp__wtoi
0x1800e2fd8  nop     dword ptr [rax+rax+00h]
0x1800e2fdd  mov     [rsp+268h+var_150], eax
0x1800e2fe4  mov     [rsp+268h+var_14C], 1
0x1800e2fec  mov     rax, [rsi]
0x1800e2fef  lea     r9, [rsp+268h+String]
0x1800e2ff4  lea     r8, aAllowdesktopan; "AllowDesktopAnalyticsProcessing"
0x1800e2ffb  mov     edx, r14d
0x1800e2ffe  mov     rcx, rsi
0x1800e3001  mov     rax, [rax+18h]
0x1800e3005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e300a  test    eax, eax
0x1800e300c  jnz     short loc_1800E3033
0x1800e300e  mov     rcx, [rsp+268h+String]; String
0x1800e3013  test    rcx, rcx
0x1800e3016  jz      short loc_1800E3033
0x1800e3018  call    cs:__imp__wtoi
0x1800e301f  nop     dword ptr [rax+rax+00h]
0x1800e3024  mov     [rsp+268h+var_148], eax
0x1800e302b  mov     [rsp+268h+var_144], 1
0x1800e3033  mov     rax, [rsi]
0x1800e3036  lea     r9, [rsp+268h+String]
0x1800e303b  lea     r8, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x1800e3042  mov     edx, r14d
0x1800e3045  mov     rcx, rsi
0x1800e3048  mov     rax, [rax+18h]
0x1800e304c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3051  test    eax, eax
0x1800e3053  jnz     short loc_1800E307A
0x1800e3055  mov     rcx, [rsp+268h+String]; String
0x1800e305a  test    rcx, rcx
0x1800e305d  jz      short loc_1800E307A
0x1800e305f  call    cs:__imp__wtoi
0x1800e3066  nop     dword ptr [rax+rax+00h]
0x1800e306b  mov     [rsp+268h+var_140], eax
0x1800e3072  mov     [rsp+268h+var_13C], 1
0x1800e307a  mov     rax, [rsi]
0x1800e307d  lea     r9, [rsp+268h+String]
0x1800e3082  lea     r8, aAllowembeddedm; "AllowEmbeddedMode"
0x1800e3089  mov     edx, r14d
0x1800e308c  mov     rcx, rsi
0x1800e308f  mov     rax, [rax+18h]
0x1800e3093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3098  test    eax, eax
0x1800e309a  jnz     short loc_1800E30C1
0x1800e309c  mov     rcx, [rsp+268h+String]; String
0x1800e30a1  test    rcx, rcx
0x1800e30a4  jz      short loc_1800E30C1
0x1800e30a6  call    cs:__imp__wtoi
0x1800e30ad  nop     dword ptr [rax+rax+00h]
0x1800e30b2  mov     [rsp+268h+var_138], eax
0x1800e30b9  mov     [rsp+268h+var_134], 1
0x1800e30c1  mov     rax, [rsi]
0x1800e30c4  lea     r9, [rsp+268h+String]
0x1800e30c9  lea     r8, aAllowexperimen; "AllowExperimentation"
0x1800e30d0  mov     edx, r14d
0x1800e30d3  mov     rcx, rsi
0x1800e30d6  mov     rax, [rax+18h]
0x1800e30da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e30df  test    eax, eax
0x1800e30e1  jnz     short loc_1800E3108
0x1800e30e3  mov     rcx, [rsp+268h+String]; String
0x1800e30e8  test    rcx, rcx
0x1800e30eb  jz      short loc_1800E3108
0x1800e30ed  call    cs:__imp__wtoi
0x1800e30f4  nop     dword ptr [rax+rax+00h]
0x1800e30f9  mov     [rsp+268h+var_130], eax
0x1800e3100  mov     [rsp+268h+var_12C], 1
0x1800e3108  mov     rax, [rsi]
0x1800e310b  lea     r9, [rsp+268h+String]
0x1800e3110  lea     r8, aAllowfontprovi; "AllowFontProviders"
0x1800e3117  mov     edx, r14d
0x1800e311a  mov     rcx, rsi
0x1800e311d  mov     rax, [rax+18h]
0x1800e3121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3126  test    eax, eax
0x1800e3128  jnz     short loc_1800E314F
0x1800e312a  mov     rcx, [rsp+268h+String]; String
0x1800e312f  test    rcx, rcx
0x1800e3132  jz      short loc_1800E314F
0x1800e3134  call    cs:__imp__wtoi
0x1800e313b  nop     dword ptr [rax+rax+00h]
0x1800e3140  mov     [rsp+268h+var_128], eax
0x1800e3147  mov     [rsp+268h+var_124], 1
0x1800e314f  mov     rax, [rsi]
0x1800e3152  lea     r9, [rsp+268h+String]
0x1800e3157  lea     r8, aAllowlocation; "AllowLocation"
0x1800e315e  mov     edx, r14d
0x1800e3161  mov     rcx, rsi
0x1800e3164  mov     rax, [rax+18h]
0x1800e3168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e316d  test    eax, eax
0x1800e316f  jnz     short loc_1800E3196
0x1800e3171  mov     rcx, [rsp+268h+String]; String
0x1800e3176  test    rcx, rcx
0x1800e3179  jz      short loc_1800E3196
0x1800e317b  call    cs:__imp__wtoi
0x1800e3182  nop     dword ptr [rax+rax+00h]
0x1800e3187  mov     [rsp+268h+var_120], eax
0x1800e318e  mov     [rsp+268h+var_11C], 1
  ... truncated ...
```
