# MDM_Policy_Result01_Audit02_InvokeEnumerateInstances

- ea: `0x180116108`
- end: `0x18011754e`
- name: `MDM_Policy_Result01_Audit02_InvokeEnumerateInstances`
- size: `5190`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180114be0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180116108`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18011641a`
- `msvcrt!_wtoi` at `0x180116461`
- `msvcrt!_wtoi` at `0x1801164a8`
- `msvcrt!_wtoi` at `0x1801164ef`
- `msvcrt!_wtoi` at `0x180116536`
- `msvcrt!_wtoi` at `0x18011657d`
- `msvcrt!_wtoi` at `0x1801165c4`
- `msvcrt!_wtoi` at `0x18011660b`
- `msvcrt!_wtoi` at `0x180116652`
- `msvcrt!_wtoi` at `0x180116699`
- `msvcrt!_wtoi` at `0x1801166e0`
- `msvcrt!_wtoi` at `0x180116727`
- `msvcrt!_wtoi` at `0x18011676e`
- `msvcrt!_wtoi` at `0x1801167b5`
- `msvcrt!_wtoi` at `0x1801167fc`
- `msvcrt!_wtoi` at `0x180116843`
- `msvcrt!_wtoi` at `0x18011688a`
- `msvcrt!_wtoi` at `0x1801168d1`
- `msvcrt!_wtoi` at `0x180116918`
- `msvcrt!_wtoi` at `0x18011695f`
- `msvcrt!_wtoi` at `0x1801169a6`
- `msvcrt!_wtoi` at `0x1801169ed`
- `msvcrt!_wtoi` at `0x180116a34`
- `msvcrt!_wtoi` at `0x180116a7b`
- `msvcrt!_wtoi` at `0x180116ac2`
- `msvcrt!_wtoi` at `0x180116b09`
- `msvcrt!_wtoi` at `0x180116b50`
- `msvcrt!_wtoi` at `0x180116b97`
- `msvcrt!_wtoi` at `0x180116bde`
- `msvcrt!_wtoi` at `0x180116c25`
- `msvcrt!_wtoi` at `0x180116c6c`
- `msvcrt!_wtoi` at `0x180116cb3`
- `msvcrt!_wtoi` at `0x180116cfa`
- `msvcrt!_wtoi` at `0x180116d41`
- `msvcrt!_wtoi` at `0x180116d88`
- `msvcrt!_wtoi` at `0x180116dcf`
- `msvcrt!_wtoi` at `0x180116e16`
- `msvcrt!_wtoi` at `0x180116e5d`
- `msvcrt!_wtoi` at `0x180116ea4`
- `msvcrt!_wtoi` at `0x180116eeb`
- `msvcrt!_wtoi` at `0x180116f32`
- `msvcrt!_wtoi` at `0x180116f79`
- `msvcrt!_wtoi` at `0x180116fc0`
- `msvcrt!_wtoi` at `0x180117007`
- `msvcrt!_wtoi` at `0x18011704e`
- `msvcrt!_wtoi` at `0x180117095`
- `msvcrt!_wtoi` at `0x1801170dc`
- `msvcrt!_wtoi` at `0x180117123`
- `msvcrt!_wtoi` at `0x18011716a`
- `msvcrt!_wtoi` at `0x1801171b1`
- `msvcrt!_wtoi` at `0x1801171f8`
- `msvcrt!_wtoi` at `0x18011723f`
- `msvcrt!_wtoi` at `0x180117286`
- `msvcrt!_wtoi` at `0x1801172cd`
- `msvcrt!_wtoi` at `0x180117314`
- `msvcrt!_wtoi` at `0x18011735b`
- `msvcrt!_wtoi` at `0x1801173a2`
- `msvcrt!_wtoi` at `0x1801173e9`
- `msvcrt!_wtoi` at `0x180117430`
- `msvcrt!_wtoi` at `0x18011641a`
- `msvcrt!_wtoi` at `0x180116461`
- `msvcrt!_wtoi` at `0x1801164a8`
- `msvcrt!_wtoi` at `0x1801164ef`
- `msvcrt!_wtoi` at `0x180116536`
- `msvcrt!_wtoi` at `0x18011657d`
- `msvcrt!_wtoi` at `0x1801165c4`
- `msvcrt!_wtoi` at `0x18011660b`
- `msvcrt!_wtoi` at `0x180116652`
- `msvcrt!_wtoi` at `0x180116699`
- `msvcrt!_wtoi` at `0x1801166e0`
- `msvcrt!_wtoi` at `0x180116727`
- `msvcrt!_wtoi` at `0x18011676e`
- `msvcrt!_wtoi` at `0x1801167b5`
- `msvcrt!_wtoi` at `0x1801167fc`
- `msvcrt!_wtoi` at `0x180116843`
- `msvcrt!_wtoi` at `0x18011688a`
- `msvcrt!_wtoi` at `0x1801168d1`
- `msvcrt!_wtoi` at `0x180116918`
- `msvcrt!_wtoi` at `0x18011695f`
- `msvcrt!_wtoi` at `0x1801169a6`
- `msvcrt!_wtoi` at `0x1801169ed`
- `msvcrt!_wtoi` at `0x180116a34`
- `msvcrt!_wtoi` at `0x180116a7b`
- `msvcrt!_wtoi` at `0x180116ac2`
- `msvcrt!_wtoi` at `0x180116b09`
- `msvcrt!_wtoi` at `0x180116b50`
- `msvcrt!_wtoi` at `0x180116b97`
- `msvcrt!_wtoi` at `0x180116bde`
- `msvcrt!_wtoi` at `0x180116c25`
- `msvcrt!_wtoi` at `0x180116c6c`
- `msvcrt!_wtoi` at `0x180116cb3`
- `msvcrt!_wtoi` at `0x180116cfa`
- `msvcrt!_wtoi` at `0x180116d41`
- `msvcrt!_wtoi` at `0x180116d88`
- `msvcrt!_wtoi` at `0x180116dcf`
- `msvcrt!_wtoi` at `0x180116e16`
- `msvcrt!_wtoi` at `0x180116e5d`
- `msvcrt!_wtoi` at `0x180116ea4`
- `msvcrt!_wtoi` at `0x180116eeb`
- `msvcrt!_wtoi` at `0x180116f32`
- `msvcrt!_wtoi` at `0x180116f79`
- `msvcrt!_wtoi` at `0x180116fc0`
- `msvcrt!_wtoi` at `0x180117007`
- `msvcrt!_wtoi` at `0x18011704e`
- `msvcrt!_wtoi` at `0x180117095`
- `msvcrt!_wtoi` at `0x1801170dc`
- `msvcrt!_wtoi` at `0x180117123`
- `msvcrt!_wtoi` at `0x18011716a`
- `msvcrt!_wtoi` at `0x1801171b1`
- `msvcrt!_wtoi` at `0x1801171f8`
- `msvcrt!_wtoi` at `0x18011723f`
- `msvcrt!_wtoi` at `0x180117286`
- `msvcrt!_wtoi` at `0x1801172cd`
- `msvcrt!_wtoi` at `0x180117314`
- `msvcrt!_wtoi` at `0x18011735b`
- `msvcrt!_wtoi` at `0x1801173a2`
- `msvcrt!_wtoi` at `0x1801173e9`
- `msvcrt!_wtoi` at `0x180117430`

## string_xrefs

- `0x18011643d`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x180116484`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x180116866`: `AccountManagement_AuditComputerAccountManagement`
- `0x18011693b`: `AccountManagement_AuditSecurityGroupManagement`
- `0x180116b2c`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x180116b73`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x180116bba`: `DSAccess_AuditDirectoryServiceAccess`
- `0x180116c01`: `DSAccess_AuditDirectoryServiceChanges`
- `0x180116c48`: `DSAccess_AuditDirectoryServiceReplication`
- `0x180116c8f`: `ObjectAccess_AuditApplicationGenerated`
- `0x180116cd6`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x180116d1d`: `ObjectAccess_AuditCertificationServices`
- `0x180116d64`: `ObjectAccess_AuditDetailedFileShare`
- `0x180116dab`: `ObjectAccess_AuditFileShare`
- `0x180116df2`: `ObjectAccess_AuditFileSystem`
- `0x180116e39`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x180116e80`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x180116ec7`: `ObjectAccess_AuditHandleManipulation`
- `0x180116f0e`: `ObjectAccess_AuditKernelObject`
- `0x180116f55`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x180116f9c`: `ObjectAccess_AuditRegistry`
- `0x180116fe3`: `ObjectAccess_AuditRemovableStorage`
- `0x18011702a`: `ObjectAccess_AuditSAM`
- `0x18011721b`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x180117262`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x1801172a9`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x18011737e`: `System_AuditSecurityStateChange`
- `0x1801173c5`: `System_AuditSecuritySystemExtension`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Audit02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r15d
  _QWORD *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-2E8h] BYREF
  char v11; // [rsp+48h] [rbp-2E0h]
  _QWORD *v12; // [rsp+50h] [rbp-2D8h] BYREF
  _QWORD v13[5]; // [rsp+58h] [rbp-2D0h] BYREF
  char v14; // [rsp+80h] [rbp-2A8h]
  int v15; // [rsp+88h] [rbp-2A0h] BYREF
  char v16; // [rsp+8Ch] [rbp-29Ch]
  _BYTE v17[16]; // [rsp+90h] [rbp-298h] BYREF
  _DWORD v18[4]; // [rsp+A0h] [rbp-288h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-278h] BYREF
  int v20; // [rsp+110h] [rbp-218h]
  char v21; // [rsp+114h] [rbp-214h]
  int v22; // [rsp+118h] [rbp-210h]
  char v23; // [rsp+11Ch] [rbp-20Ch]
  int v24; // [rsp+120h] [rbp-208h]
  char v25; // [rsp+124h] [rbp-204h]
  int v26; // [rsp+128h] [rbp-200h]
  char v27; // [rsp+12Ch] [rbp-1FCh]
  int v28; // [rsp+130h] [rbp-1F8h]
  char v29; // [rsp+134h] [rbp-1F4h]
  int v30; // [rsp+138h] [rbp-1F0h]
  char v31; // [rsp+13Ch] [rbp-1ECh]
  int v32; // [rsp+140h] [rbp-1E8h]
  char v33; // [rsp+144h] [rbp-1E4h]
  int v34; // [rsp+148h] [rbp-1E0h]
  char v35; // [rsp+14Ch] [rbp-1DCh]
  int v36; // [rsp+150h] [rbp-1D8h]
  char v37; // [rsp+154h] [rbp-1D4h]
  int v38; // [rsp+158h] [rbp-1D0h]
  char v39; // [rsp+15Ch] [rbp-1CCh]
  int v40; // [rsp+160h] [rbp-1C8h]
  char v41; // [rsp+164h] [rbp-1C4h]
  int v42; // [rsp+168h] [rbp-1C0h]
  char v43; // [rsp+16Ch] [rbp-1BCh]
  int v44; // [rsp+170h] [rbp-1B8h]
  char v45; // [rsp+174h] [rbp-1B4h]
  int v46; // [rsp+178h] [rbp-1B0h]
  char v47; // [rsp+17Ch] [rbp-1ACh]
  int v48; // [rsp+180h] [rbp-1A8h]
  char v49; // [rsp+184h] [rbp-1A4h]
  int v50; // [rsp+188h] [rbp-1A0h]
  char v51; // [rsp+18Ch] [rbp-19Ch]
  int v52; // [rsp+190h] [rbp-198h]
  char v53; // [rsp+194h] [rbp-194h]
  int v54; // [rsp+198h] [rbp-190h]
  char v55; // [rsp+19Ch] [rbp-18Ch]
  int v56; // [rsp+1A0h] [rbp-188h]
  char v57; // [rsp+1A4h] [rbp-184h]
  int v58; // [rsp+1A8h] [rbp-180h]
  char v59; // [rsp+1ACh] [rbp-17Ch]
  int v60; // [rsp+1B0h] [rbp-178h]
  char v61; // [rsp+1B4h] [rbp-174h]
  int v62; // [rsp+1B8h] [rbp-170h]
  char v63; // [rsp+1BCh] [rbp-16Ch]
  int v64; // [rsp+1C0h] [rbp-168h]
  char v65; // [rsp+1C4h] [rbp-164h]
  int v66; // [rsp+1C8h] [rbp-160h]
  char v67; // [rsp+1CCh] [rbp-15Ch]
  int v68; // [rsp+1D0h] [rbp-158h]
  char v69; // [rsp+1D4h] [rbp-154h]
  int v70; // [rsp+1D8h] [rbp-150h]
  char v71; // [rsp+1DCh] [rbp-14Ch]
  int v72; // [rsp+1E0h] [rbp-148h]
  char v73; // [rsp+1E4h] [rbp-144h]
  int v74; // [rsp+1E8h] [rbp-140h]
  char v75; // [rsp+1ECh] [rbp-13Ch]
  int v76; // [rsp+1F0h] [rbp-138h]
  char v77; // [rsp+1F4h] [rbp-134h]
  int v78; // [rsp+1F8h] [rbp-130h]
  char v79; // [rsp+1FCh] [rbp-12Ch]
  int v80; // [rsp+200h] [rbp-128h]
  char v81; // [rsp+204h] [rbp-124h]
  int v82; // [rsp+208h] [rbp-120h]
  char v83; // [rsp+20Ch] [rbp-11Ch]
  int v84; // [rsp+210h] [rbp-118h]
  char v85; // [rsp+214h] [rbp-114h]
  int v86; // [rsp+218h] [rbp-110h]
  char v87; // [rsp+21Ch] [rbp-10Ch]
  int v88; // [rsp+220h] [rbp-108h]
  char v89; // [rsp+224h] [rbp-104h]
  int v90; // [rsp+228h] [rbp-100h]
  char v91; // [rsp+22Ch] [rbp-FCh]
  int v92; // [rsp+230h] [rbp-F8h]
  char v93; // [rsp+234h] [rbp-F4h]
  int v94; // [rsp+238h] [rbp-F0h]
  char v95; // [rsp+23Ch] [rbp-ECh]
  int v96; // [rsp+240h] [rbp-E8h]
  char v97; // [rsp+244h] [rbp-E4h]
  int v98; // [rsp+248h] [rbp-E0h]
  char v99; // [rsp+24Ch] [rbp-DCh]
  int v100; // [rsp+250h] [rbp-D8h]
  char v101; // [rsp+254h] [rbp-D4h]
  int v102; // [rsp+258h] [rbp-D0h]
  char v103; // [rsp+25Ch] [rbp-CCh]
  int v104; // [rsp+260h] [rbp-C8h]
  char v105; // [rsp+264h] [rbp-C4h]
  int v106; // [rsp+268h] [rbp-C0h]
  char v107; // [rsp+26Ch] [rbp-BCh]
  int v108; // [rsp+270h] [rbp-B8h]
  char v109; // [rsp+274h] [rbp-B4h]
  int v110; // [rsp+278h] [rbp-B0h]
  char v111; // [rsp+27Ch] [rbp-ACh]
  int v112; // [rsp+280h] [rbp-A8h]
  char v113; // [rsp+284h] [rbp-A4h]
  int v114; // [rsp+288h] [rbp-A0h]
  char v115; // [rsp+28Ch] [rbp-9Ch]
  int v116; // [rsp+290h] [rbp-98h]
  char v117; // [rsp+294h] [rbp-94h]
  int v118; // [rsp+298h] [rbp-90h]
  char v119; // [rsp+29Ch] [rbp-8Ch]
  int v120; // [rsp+2A0h] [rbp-88h]
  char v121; // [rsp+2A4h] [rbp-84h]
  int v122; // [rsp+2A8h] [rbp-80h]
  char v123; // [rsp+2ACh] [rbp-7Ch]
  int v124; // [rsp+2B0h] [rbp-78h]
  char v125; // [rsp+2B4h] [rbp-74h]
  int v126; // [rsp+2B8h] [rbp-70h]
  char v127; // [rsp+2BCh] [rbp-6Ch]
  int v128; // [rsp+2C0h] [rbp-68h]
  char v129; // [rsp+2C4h] [rbp-64h]
  int v130; // [rsp+2C8h] [rbp-60h]
  char v131; // [rsp+2CCh] [rbp-5Ch]
  int v132; // [rsp+2D0h] [rbp-58h]
  char v133; // [rsp+2D4h] [rbp-54h]
  int v134; // [rsp+2D8h] [rbp-50h]
  char v135; // [rsp+2DCh] [rbp-4Ch]
  int v136; // [rsp+2E0h] [rbp-48h]
  char v137; // [rsp+2E4h] [rbp-44h]

  memset_0(&instance, 0, 0x238u);
  v11 = 0;
  String = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = &TelemetryEventWriter::`vftable';
  v13[1] = &v15;
  v13[2] = "MDM_Policy_Result01_Audit02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v5 = v18;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180346AD0,
      v17,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v13, v4);
  v12 = 0;
  v6 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Result01_Audit02_NodeList, 61, 2, &v12);
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
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Audit02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_215;
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
                    L"Audit",
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
                      L"AccountLogon_AuditCredentialValidation",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogon_AuditKerberosAuthenticationService",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogon_AuditKerberosServiceTicketOperations",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogon_AuditOtherAccountLogonEvents",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditAccountLockout",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditGroupMembership",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditIPsecExtendedMode",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditIPsecMainMode",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditIPsecQuickMode",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditLogoff",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditLogon",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditNetworkPolicyServer",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditSpecialLogon",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditUserDeviceClaims",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditApplicationGroupManagement",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditComputerAccountManagement",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditDistributionGroupManagement",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditOtherAccountManagementEvents",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditSecurityGroupManagement",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditUserAccountManagement",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditDPAPIActivity",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditPNPActivity",
                      &String)
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditProcessCreation",
                      &String)
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditProcessTermination",
                      &String)
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditRPCEvents",
                      &String)
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditTokenRightAdjusted",
                      &String)
                && String )
              {
                v72 = _wtoi(String);
                v73 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DSAccess_AuditDetailedDirectoryServiceReplication",
                      &String)
                && String )
              {
                v74 = _wtoi(String);
                v75 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DSAccess_AuditDirectoryServiceAccess",
                      &String)
                && String )
              {
                v76 = _wtoi(String);
                v77 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DSAccess_AuditDirectoryServiceChanges",
                      &String)
                && String )
              {
                v78 = _wtoi(String);
                v79 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DSAccess_AuditDirectoryServiceReplication",
                      &String)
                && String )
              {
                v80 = _wtoi(String);
                v81 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditApplicationGenerated",
                      &String)
                && String )
              {
                v82 = _wtoi(String);
                v83 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditCentralAccessPolicyStaging",
                      &String)
                && String )
              {
                v84 = _wtoi(String);
                v85 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditCertificationServices",
                      &String)
                && String )
              {
                v86 = _wtoi(String);
                v87 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditDetailedFileShare",
                      &String)
                && String )
              {
                v88 = _wtoi(String);
                v89 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditFileShare",
                      &String)
                && String )
              {
                v90 = _wtoi(String);
                v91 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditFileSystem",
                      &String)
                && String )
              {
                v92 = _wtoi(String);
                v93 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditFilteringPlatformConnection",
                      &String)
                && String )
              {
                v94 = _wtoi(String);
                v95 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                      &String)
                && String )
              {
                v96 = _wtoi(String);
                v97 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditHandleManipulation",
                      &String)
                && String )
              {
                v98 = _wtoi(String);
                v99 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditKernelObject",
                      &String)
                && String )
              {
                v100 = _wtoi(String);
                v101 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditOtherObjectAccessEvents",
                      &String)
                && String )
              {
                v102 = _wtoi(String);
                v103 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditRegistry",
                      &String)
                && String )
              {
                v104 = _wtoi(String);
                v105 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditRemovableStorage",
                      &String)
                && String )
              {
                v106 = _wtoi(String);
                v107 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditSAM",
                      &String)
                && String )
              {
                v108 = _wtoi(String);
                v109 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditAuthenticationPolicyChange",
                      &String)
                && String )
              {
                v110 = _wtoi(String);
                v111 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditAuthorizationPolicyChange",
                      &String)
                && String )
              {
                v112 = _wtoi(String);
                v113 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditFilteringPlatformPolicyChange",
                      &String)
                && String )
              {
                v114 = _wtoi(String);
                v115 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                      &String)
                && String )
              {
                v116 = _wtoi(String);
                v117 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditOtherPolicyChangeEvents",
                      &String)
                && String )
              {
                v118 = _wtoi(String);
                v119 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditPolicyChange",
                      &String)
                && String )
              {
                v120 = _wtoi(String);
                v121 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                      &String)
                && String )
              {
                v122 = _wtoi(String);
                v123 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                      &String)
                && String )
              {
                v124 = _wtoi(String);
                v125 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PrivilegeUse_AuditSensitivePrivilegeUse",
                      &String)
                && String )
              {
                v126 = _wtoi(String);
                v127 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"System_AuditIPsecDriver",
                      &String)
                && String )
              {
                v128 = _wtoi(String);
                v129 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"System_AuditOtherSystemEvents",
                      &String)
                && String )
              {
                v130 = _wtoi(String);
                v131 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"System_AuditSecurityStateChange",
                      &String)
                && String )
              {
                v132 = _wtoi(String);
                v133 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"System_AuditSecuritySystemExtension",
                      &String)
                && String )
              {
                v134 = _wtoi(String);
                v135 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"System_AuditSystemIntegrity",
                      &String)
                && String )
              {
                v136 = _wtoi(String);
                v137 = 1;
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
LABEL_215:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v13, "EnumerateInstancesEnd", v6);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180364F02,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180116108  mov     [rsp+arg_8], rbx
0x18011610d  mov     [rsp+arg_10], rsi
0x180116112  push    rdi
0x180116113  push    r12
0x180116115  push    r13
0x180116117  push    r14
0x180116119  push    r15
0x18011611b  sub     rsp, 300h
0x180116122  mov     rax, cs:__security_cookie
0x180116129  xor     rax, rsp
0x18011612c  mov     [rsp+328h+var_38], rax
0x180116134  mov     r13b, dl
0x180116137  mov     r12, rcx
0x18011613a  xor     edx, edx; Val
0x18011613c  mov     r8d, 238h; Size
0x180116142  lea     rcx, [rsp+328h+instance]; void *
0x18011614a  call    memset_0
0x18011614f  xor     edi, edi
0x180116151  mov     [rsp+328h+var_2E0], dil
0x180116156  mov     [rsp+328h+String], rdi
0x18011615b  mov     [rsp+328h+var_2A0], edi
0x180116162  mov     [rsp+328h+var_29C], dil
0x18011616a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180116171  mov     [rsp+328h+var_2D0], rax
0x180116176  lea     rax, [rsp+328h+var_2A0]
0x18011617e  mov     [rsp+328h+var_2C8], rax
0x180116183  lea     rax, aMdmPolicyResul_95; "MDM_Policy_Result01_Audit02"
0x18011618a  mov     [rsp+328h+var_2C0], rax
0x18011618f  lea     rcx, [rsp+328h+var_2A0]
0x180116197  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18011619c  mov     eax, cs:dword_180380B68
0x1801161a2  cmp     eax, 5
0x1801161a5  jbe     short loc_180116217
0x1801161a7  mov     rdx, 200000000000h
0x1801161b1  lea     rcx, dword_180380B68
0x1801161b8  call    _tlgKeywordOn
0x1801161bd  test    al, al
0x1801161bf  jz      short loc_180116217
0x1801161c1  cmp     [rsp+328h+var_29C], dil
0x1801161c9  jz      short loc_1801161F9
0x1801161cb  cmp     [rsp+328h+var_288], edi
0x1801161d2  jnz     short loc_1801161EF
0x1801161d4  cmp     [rsp+328h+var_284], edi
0x1801161db  jnz     short loc_1801161EF
0x1801161dd  cmp     [rsp+328h+var_280], edi
0x1801161e4  jnz     short loc_1801161EF
0x1801161e6  cmp     [rsp+328h+var_27C], edi
0x1801161ed  jz      short loc_1801161F9
0x1801161ef  lea     r9, [rsp+328h+var_288]
0x1801161f7  jmp     short loc_1801161FC
0x1801161f9  mov     r9, rdi
0x1801161fc  lea     r8, [rsp+328h+var_298]
0x180116204  lea     rdx, qword_180346AD0
0x18011620b  lea     rcx, dword_180380B68
0x180116212  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180116217  lea     rcx, [rsp+328h+var_2D0]; this
0x18011621c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180116221  nop
0x180116222  mov     [rsp+328h+var_2D8], rdi
0x180116227  lea     rax, [rsp+328h+var_2D8]
0x18011622c  mov     [rsp+328h+var_2F8], rax
0x180116231  mov     [rsp+328h+var_300], 2
0x180116239  mov     [rsp+328h+var_308], 3Dh ; '='
0x180116241  lea     r9, ?MDM_Policy_Result01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Audit02_NodeList
0x180116248  xor     r8d, r8d
0x18011624b  xor     edx, edx
0x18011624d  mov     rcx, r12
0x180116250  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180116255  mov     r15d, eax
0x180116258  test    eax, eax
0x18011625a  jz      short loc_180116261
0x18011625c  jmp     loc_1801174AD
0x180116261  lea     rbx, [rsp+328h+var_2D8]
0x180116266  mov     [rsp+328h+var_2B0], rbx
0x18011626b  mov     r14d, 1
0x180116271  mov     [rsp+328h+var_2A8], r14b
0x180116279  mov     rsi, [rsp+328h+var_2D8]
0x18011627e  test    rsi, rsi
0x180116281  jnz     short loc_18011628B
0x180116283  mov     r15d, r14d
0x180116286  jmp     loc_1801174AD
0x18011628b  mov     rax, [rsi]
0x18011628e  mov     rcx, rsi
0x180116291  mov     rax, [rax+10h]
0x180116295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011629a  mov     r15d, eax
0x18011629d  test    eax, eax
0x18011629f  jz      short loc_1801162BF
0x1801162a1  mov     rcx, [rsp+328h+var_2D8]
0x1801162a6  test    rcx, rcx
0x1801162a9  jz      short loc_1801162BA
0x1801162ab  mov     rax, [rcx]
0x1801162ae  mov     edx, r14d
0x1801162b1  mov     rax, [rax]
0x1801162b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801162b9  nop
0x1801162ba  jmp     loc_1801174AD
0x1801162bf  mov     rax, [rsi]
0x1801162c2  mov     rcx, rsi
0x1801162c5  mov     rax, [rax+8]
0x1801162c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801162ce  mov     r15d, eax
0x1801162d1  test    eax, eax
0x1801162d3  jz      short loc_1801162F3
0x1801162d5  mov     rcx, [rsp+328h+var_2D8]
0x1801162da  test    rcx, rcx
0x1801162dd  jz      short loc_1801162EE
0x1801162df  mov     rax, [rcx]
0x1801162e2  mov     edx, r14d
0x1801162e5  mov     rax, [rax]
0x1801162e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801162ed  nop
0x1801162ee  jmp     loc_1801174AD
0x1801162f3  mov     r14d, edi
0x1801162f6  mov     rax, [rsi+108h]
0x1801162fd  sub     rax, [rsi+100h]
0x180116304  sar     rax, 4
0x180116308  cmp     r14d, eax
0x18011630b  jnb     loc_180117475
0x180116311  lea     r8, [rsp+328h+instance]; instance
0x180116319  lea     rdx, MDM_Policy_Result01_Audit02_rtti; classDecl
0x180116320  mov     rcx, r12; context
0x180116323  call    MI_Context_ConstructInstance
0x180116328  mov     r15d, eax
0x18011632b  test    eax, eax
0x18011632d  jz      short loc_18011634F
0x18011632f  mov     rcx, [rbx]
0x180116332  test    rcx, rcx
0x180116335  jz      short loc_18011634A
0x180116337  mov     rax, [rcx]
0x18011633a  mov     edx, 1
0x18011633f  mov     rax, [rax]
0x180116342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116347  mov     [rbx], rdi
0x18011634a  jmp     loc_1801174AD
0x18011634f  mov     [rsp+328h+var_2E0], 1
0x180116354  mov     rax, [rsi]
0x180116357  lea     r9, [rsp+328h+String]
0x18011635c  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x180116363  mov     edx, r14d
0x180116366  mov     rcx, rsi
0x180116369  mov     rax, [rax+18h]
0x18011636d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116372  test    eax, eax
0x180116374  jnz     short loc_18011638D
0x180116376  mov     rdx, [rsp+328h+String]
0x18011637b  test    rdx, rdx
0x18011637e  jz      short loc_18011638D
0x180116380  lea     rcx, [rsp+328h+instance]
0x180116388  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18011638d  mov     rax, [rsi]
0x180116390  lea     r9, [rsp+328h+String]
0x180116395  lea     r8, aAudit; "Audit"
0x18011639c  mov     edx, r14d
0x18011639f  mov     rcx, rsi
0x1801163a2  mov     rax, [rax+18h]
0x1801163a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801163ab  test    eax, eax
0x1801163ad  jnz     short loc_1801163C6
0x1801163af  mov     rdx, [rsp+328h+String]
0x1801163b4  test    rdx, rdx
0x1801163b7  jz      short loc_1801163C6
0x1801163b9  lea     rcx, [rsp+328h+instance]
0x1801163c1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801163c6  cmp     r13b, 1
0x1801163ca  jnz     short loc_1801163EE
0x1801163cc  lea     rdx, [rsp+328h+instance]
0x1801163d4  mov     rcx, r12; self
0x1801163d7  call    MI_Instance_Destruct
0x1801163dc  lea     rcx, [rsp+328h+instance]; self
0x1801163e4  call    MI_Instance_Destruct
0x1801163e9  jmp     loc_180117468
0x1801163ee  mov     rax, [rsi]
0x1801163f1  lea     r9, [rsp+328h+String]
0x1801163f6  lea     r8, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x1801163fd  mov     edx, r14d
0x180116400  mov     rcx, rsi
0x180116403  mov     rax, [rax+18h]
0x180116407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011640c  test    eax, eax
0x18011640e  jnz     short loc_180116435
0x180116410  mov     rcx, [rsp+328h+String]; String
0x180116415  test    rcx, rcx
0x180116418  jz      short loc_180116435
0x18011641a  call    cs:__imp__wtoi
0x180116421  nop     dword ptr [rax+rax+00h]
0x180116426  mov     [rsp+328h+var_218], eax
0x18011642d  mov     [rsp+328h+var_214], 1
0x180116435  mov     rax, [rsi]
0x180116438  lea     r9, [rsp+328h+String]
0x18011643d  lea     r8, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x180116444  mov     edx, r14d
0x180116447  mov     rcx, rsi
0x18011644a  mov     rax, [rax+18h]
0x18011644e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116453  test    eax, eax
0x180116455  jnz     short loc_18011647C
0x180116457  mov     rcx, [rsp+328h+String]; String
0x18011645c  test    rcx, rcx
0x18011645f  jz      short loc_18011647C
0x180116461  call    cs:__imp__wtoi
0x180116468  nop     dword ptr [rax+rax+00h]
0x18011646d  mov     [rsp+328h+var_210], eax
0x180116474  mov     [rsp+328h+var_20C], 1
0x18011647c  mov     rax, [rsi]
0x18011647f  lea     r9, [rsp+328h+String]
0x180116484  lea     r8, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x18011648b  mov     edx, r14d
0x18011648e  mov     rcx, rsi
0x180116491  mov     rax, [rax+18h]
0x180116495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011649a  test    eax, eax
0x18011649c  jnz     short loc_1801164C3
0x18011649e  mov     rcx, [rsp+328h+String]; String
0x1801164a3  test    rcx, rcx
0x1801164a6  jz      short loc_1801164C3
0x1801164a8  call    cs:__imp__wtoi
0x1801164af  nop     dword ptr [rax+rax+00h]
0x1801164b4  mov     [rsp+328h+var_208], eax
0x1801164bb  mov     [rsp+328h+var_204], 1
0x1801164c3  mov     rax, [rsi]
0x1801164c6  lea     r9, [rsp+328h+String]
0x1801164cb  lea     r8, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x1801164d2  mov     edx, r14d
0x1801164d5  mov     rcx, rsi
0x1801164d8  mov     rax, [rax+18h]
0x1801164dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801164e1  test    eax, eax
0x1801164e3  jnz     short loc_18011650A
0x1801164e5  mov     rcx, [rsp+328h+String]; String
0x1801164ea  test    rcx, rcx
0x1801164ed  jz      short loc_18011650A
0x1801164ef  call    cs:__imp__wtoi
0x1801164f6  nop     dword ptr [rax+rax+00h]
0x1801164fb  mov     [rsp+328h+var_200], eax
0x180116502  mov     [rsp+328h+var_1FC], 1
0x18011650a  mov     rax, [rsi]
0x18011650d  lea     r9, [rsp+328h+String]
0x180116512  lea     r8, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x180116519  mov     edx, r14d
0x18011651c  mov     rcx, rsi
0x18011651f  mov     rax, [rax+18h]
0x180116523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116528  test    eax, eax
0x18011652a  jnz     short loc_180116551
0x18011652c  mov     rcx, [rsp+328h+String]; String
0x180116531  test    rcx, rcx
0x180116534  jz      short loc_180116551
0x180116536  call    cs:__imp__wtoi
0x18011653d  nop     dword ptr [rax+rax+00h]
0x180116542  mov     [rsp+328h+var_1F8], eax
0x180116549  mov     [rsp+328h+var_1F4], 1
0x180116551  mov     rax, [rsi]
0x180116554  lea     r9, [rsp+328h+String]
0x180116559  lea     r8, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x180116560  mov     edx, r14d
0x180116563  mov     rcx, rsi
0x180116566  mov     rax, [rax+18h]
0x18011656a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011656f  test    eax, eax
0x180116571  jnz     short loc_180116598
0x180116573  mov     rcx, [rsp+328h+String]; String
0x180116578  test    rcx, rcx
0x18011657b  jz      short loc_180116598
0x18011657d  call    cs:__imp__wtoi
0x180116584  nop     dword ptr [rax+rax+00h]
0x180116589  mov     [rsp+328h+var_1F0], eax
0x180116590  mov     [rsp+328h+var_1EC], 1
0x180116598  mov     rax, [rsi]
0x18011659b  lea     r9, [rsp+328h+String]
0x1801165a0  lea     r8, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x1801165a7  mov     edx, r14d
0x1801165aa  mov     rcx, rsi
0x1801165ad  mov     rax, [rax+18h]
0x1801165b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801165b6  test    eax, eax
0x1801165b8  jnz     short loc_1801165DF
0x1801165ba  mov     rcx, [rsp+328h+String]; String
0x1801165bf  test    rcx, rcx
0x1801165c2  jz      short loc_1801165DF
0x1801165c4  call    cs:__imp__wtoi
0x1801165cb  nop     dword ptr [rax+rax+00h]
0x1801165d0  mov     [rsp+328h+var_1E8], eax
0x1801165d7  mov     [rsp+328h+var_1E4], 1
0x1801165df  mov     rax, [rsi]
0x1801165e2  lea     r9, [rsp+328h+String]
0x1801165e7  lea     r8, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x1801165ee  mov     edx, r14d
0x1801165f1  mov     rcx, rsi
0x1801165f4  mov     rax, [rax+18h]
0x1801165f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801165fd  test    eax, eax
0x1801165ff  jnz     short loc_180116626
0x180116601  mov     rcx, [rsp+328h+String]; String
0x180116606  test    rcx, rcx
0x180116609  jz      short loc_180116626
0x18011660b  call    cs:__imp__wtoi
0x180116612  nop     dword ptr [rax+rax+00h]
0x180116617  mov     [rsp+328h+var_1E0], eax
0x18011661e  mov     [rsp+328h+var_1DC], 1
  ... truncated ...
```
