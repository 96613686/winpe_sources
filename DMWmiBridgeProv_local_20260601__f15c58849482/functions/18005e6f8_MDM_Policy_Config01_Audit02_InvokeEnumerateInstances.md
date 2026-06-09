# MDM_Policy_Config01_Audit02_InvokeEnumerateInstances

- ea: `0x18005e6f8`
- end: `0x18005fb3e`
- name: `MDM_Policy_Config01_Audit02_InvokeEnumerateInstances`
- size: `5190`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005d1d0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18005e6f8`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18005ea0a`
- `msvcrt!_wtoi` at `0x18005ea51`
- `msvcrt!_wtoi` at `0x18005ea98`
- `msvcrt!_wtoi` at `0x18005eadf`
- `msvcrt!_wtoi` at `0x18005eb26`
- `msvcrt!_wtoi` at `0x18005eb6d`
- `msvcrt!_wtoi` at `0x18005ebb4`
- `msvcrt!_wtoi` at `0x18005ebfb`
- `msvcrt!_wtoi` at `0x18005ec42`
- `msvcrt!_wtoi` at `0x18005ec89`
- `msvcrt!_wtoi` at `0x18005ecd0`
- `msvcrt!_wtoi` at `0x18005ed17`
- `msvcrt!_wtoi` at `0x18005ed5e`
- `msvcrt!_wtoi` at `0x18005eda5`
- `msvcrt!_wtoi` at `0x18005edec`
- `msvcrt!_wtoi` at `0x18005ee33`
- `msvcrt!_wtoi` at `0x18005ee7a`
- `msvcrt!_wtoi` at `0x18005eec1`
- `msvcrt!_wtoi` at `0x18005ef08`
- `msvcrt!_wtoi` at `0x18005ef4f`
- `msvcrt!_wtoi` at `0x18005ef96`
- `msvcrt!_wtoi` at `0x18005efdd`
- `msvcrt!_wtoi` at `0x18005f024`
- `msvcrt!_wtoi` at `0x18005f06b`
- `msvcrt!_wtoi` at `0x18005f0b2`
- `msvcrt!_wtoi` at `0x18005f0f9`
- `msvcrt!_wtoi` at `0x18005f140`
- `msvcrt!_wtoi` at `0x18005f187`
- `msvcrt!_wtoi` at `0x18005f1ce`
- `msvcrt!_wtoi` at `0x18005f215`
- `msvcrt!_wtoi` at `0x18005f25c`
- `msvcrt!_wtoi` at `0x18005f2a3`
- `msvcrt!_wtoi` at `0x18005f2ea`
- `msvcrt!_wtoi` at `0x18005f331`
- `msvcrt!_wtoi` at `0x18005f378`
- `msvcrt!_wtoi` at `0x18005f3bf`
- `msvcrt!_wtoi` at `0x18005f406`
- `msvcrt!_wtoi` at `0x18005f44d`
- `msvcrt!_wtoi` at `0x18005f494`
- `msvcrt!_wtoi` at `0x18005f4db`
- `msvcrt!_wtoi` at `0x18005f522`
- `msvcrt!_wtoi` at `0x18005f569`
- `msvcrt!_wtoi` at `0x18005f5b0`
- `msvcrt!_wtoi` at `0x18005f5f7`
- `msvcrt!_wtoi` at `0x18005f63e`
- `msvcrt!_wtoi` at `0x18005f685`
- `msvcrt!_wtoi` at `0x18005f6cc`
- `msvcrt!_wtoi` at `0x18005f713`
- `msvcrt!_wtoi` at `0x18005f75a`
- `msvcrt!_wtoi` at `0x18005f7a1`
- `msvcrt!_wtoi` at `0x18005f7e8`
- `msvcrt!_wtoi` at `0x18005f82f`
- `msvcrt!_wtoi` at `0x18005f876`
- `msvcrt!_wtoi` at `0x18005f8bd`
- `msvcrt!_wtoi` at `0x18005f904`
- `msvcrt!_wtoi` at `0x18005f94b`
- `msvcrt!_wtoi` at `0x18005f992`
- `msvcrt!_wtoi` at `0x18005f9d9`
- `msvcrt!_wtoi` at `0x18005fa20`
- `msvcrt!_wtoi` at `0x18005ea0a`
- `msvcrt!_wtoi` at `0x18005ea51`
- `msvcrt!_wtoi` at `0x18005ea98`
- `msvcrt!_wtoi` at `0x18005eadf`
- `msvcrt!_wtoi` at `0x18005eb26`
- `msvcrt!_wtoi` at `0x18005eb6d`
- `msvcrt!_wtoi` at `0x18005ebb4`
- `msvcrt!_wtoi` at `0x18005ebfb`
- `msvcrt!_wtoi` at `0x18005ec42`
- `msvcrt!_wtoi` at `0x18005ec89`
- `msvcrt!_wtoi` at `0x18005ecd0`
- `msvcrt!_wtoi` at `0x18005ed17`
- `msvcrt!_wtoi` at `0x18005ed5e`
- `msvcrt!_wtoi` at `0x18005eda5`
- `msvcrt!_wtoi` at `0x18005edec`
- `msvcrt!_wtoi` at `0x18005ee33`
- `msvcrt!_wtoi` at `0x18005ee7a`
- `msvcrt!_wtoi` at `0x18005eec1`
- `msvcrt!_wtoi` at `0x18005ef08`
- `msvcrt!_wtoi` at `0x18005ef4f`
- `msvcrt!_wtoi` at `0x18005ef96`
- `msvcrt!_wtoi` at `0x18005efdd`
- `msvcrt!_wtoi` at `0x18005f024`
- `msvcrt!_wtoi` at `0x18005f06b`
- `msvcrt!_wtoi` at `0x18005f0b2`
- `msvcrt!_wtoi` at `0x18005f0f9`
- `msvcrt!_wtoi` at `0x18005f140`
- `msvcrt!_wtoi` at `0x18005f187`
- `msvcrt!_wtoi` at `0x18005f1ce`
- `msvcrt!_wtoi` at `0x18005f215`
- `msvcrt!_wtoi` at `0x18005f25c`
- `msvcrt!_wtoi` at `0x18005f2a3`
- `msvcrt!_wtoi` at `0x18005f2ea`
- `msvcrt!_wtoi` at `0x18005f331`
- `msvcrt!_wtoi` at `0x18005f378`
- `msvcrt!_wtoi` at `0x18005f3bf`
- `msvcrt!_wtoi` at `0x18005f406`
- `msvcrt!_wtoi` at `0x18005f44d`
- `msvcrt!_wtoi` at `0x18005f494`
- `msvcrt!_wtoi` at `0x18005f4db`
- `msvcrt!_wtoi` at `0x18005f522`
- `msvcrt!_wtoi` at `0x18005f569`
- `msvcrt!_wtoi` at `0x18005f5b0`
- `msvcrt!_wtoi` at `0x18005f5f7`
- `msvcrt!_wtoi` at `0x18005f63e`
- `msvcrt!_wtoi` at `0x18005f685`
- `msvcrt!_wtoi` at `0x18005f6cc`
- `msvcrt!_wtoi` at `0x18005f713`
- `msvcrt!_wtoi` at `0x18005f75a`
- `msvcrt!_wtoi` at `0x18005f7a1`
- `msvcrt!_wtoi` at `0x18005f7e8`
- `msvcrt!_wtoi` at `0x18005f82f`
- `msvcrt!_wtoi` at `0x18005f876`
- `msvcrt!_wtoi` at `0x18005f8bd`
- `msvcrt!_wtoi` at `0x18005f904`
- `msvcrt!_wtoi` at `0x18005f94b`
- `msvcrt!_wtoi` at `0x18005f992`
- `msvcrt!_wtoi` at `0x18005f9d9`
- `msvcrt!_wtoi` at `0x18005fa20`

## string_xrefs

- `0x18005ea2d`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x18005ea74`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x18005ee56`: `AccountManagement_AuditComputerAccountManagement`
- `0x18005ef2b`: `AccountManagement_AuditSecurityGroupManagement`
- `0x18005f11c`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x18005f163`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x18005f1aa`: `DSAccess_AuditDirectoryServiceAccess`
- `0x18005f1f1`: `DSAccess_AuditDirectoryServiceChanges`
- `0x18005f238`: `DSAccess_AuditDirectoryServiceReplication`
- `0x18005f27f`: `ObjectAccess_AuditApplicationGenerated`
- `0x18005f2c6`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x18005f30d`: `ObjectAccess_AuditCertificationServices`
- `0x18005f354`: `ObjectAccess_AuditDetailedFileShare`
- `0x18005f39b`: `ObjectAccess_AuditFileShare`
- `0x18005f3e2`: `ObjectAccess_AuditFileSystem`
- `0x18005f429`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x18005f470`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x18005f4b7`: `ObjectAccess_AuditHandleManipulation`
- `0x18005f4fe`: `ObjectAccess_AuditKernelObject`
- `0x18005f545`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x18005f58c`: `ObjectAccess_AuditRegistry`
- `0x18005f5d3`: `ObjectAccess_AuditRemovableStorage`
- `0x18005f61a`: `ObjectAccess_AuditSAM`
- `0x18005f80b`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x18005f852`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x18005f899`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x18005f96e`: `System_AuditSecurityStateChange`
- `0x18005f9b5`: `System_AuditSecuritySystemExtension`
- `0x18005e94c`: `./Vendor/MSFT/Policy/Config`
- `0x18005e773`: `MDM_Policy_Config01_Audit02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Audit02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-2E8h] BYREF
  char v14; // [rsp+48h] [rbp-2E0h]
  _QWORD *v15; // [rsp+50h] [rbp-2D8h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-2D0h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-2B8h] BYREF
  char v18; // [rsp+80h] [rbp-2A8h]
  int v19; // [rsp+88h] [rbp-2A0h] BYREF
  char v20; // [rsp+8Ch] [rbp-29Ch]
  _BYTE v21[16]; // [rsp+90h] [rbp-298h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-288h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-278h] BYREF
  int v24; // [rsp+110h] [rbp-218h]
  char v25; // [rsp+114h] [rbp-214h]
  int v26; // [rsp+118h] [rbp-210h]
  char v27; // [rsp+11Ch] [rbp-20Ch]
  int v28; // [rsp+120h] [rbp-208h]
  char v29; // [rsp+124h] [rbp-204h]
  int v30; // [rsp+128h] [rbp-200h]
  char v31; // [rsp+12Ch] [rbp-1FCh]
  int v32; // [rsp+130h] [rbp-1F8h]
  char v33; // [rsp+134h] [rbp-1F4h]
  int v34; // [rsp+138h] [rbp-1F0h]
  char v35; // [rsp+13Ch] [rbp-1ECh]
  int v36; // [rsp+140h] [rbp-1E8h]
  char v37; // [rsp+144h] [rbp-1E4h]
  int v38; // [rsp+148h] [rbp-1E0h]
  char v39; // [rsp+14Ch] [rbp-1DCh]
  int v40; // [rsp+150h] [rbp-1D8h]
  char v41; // [rsp+154h] [rbp-1D4h]
  int v42; // [rsp+158h] [rbp-1D0h]
  char v43; // [rsp+15Ch] [rbp-1CCh]
  int v44; // [rsp+160h] [rbp-1C8h]
  char v45; // [rsp+164h] [rbp-1C4h]
  int v46; // [rsp+168h] [rbp-1C0h]
  char v47; // [rsp+16Ch] [rbp-1BCh]
  int v48; // [rsp+170h] [rbp-1B8h]
  char v49; // [rsp+174h] [rbp-1B4h]
  int v50; // [rsp+178h] [rbp-1B0h]
  char v51; // [rsp+17Ch] [rbp-1ACh]
  int v52; // [rsp+180h] [rbp-1A8h]
  char v53; // [rsp+184h] [rbp-1A4h]
  int v54; // [rsp+188h] [rbp-1A0h]
  char v55; // [rsp+18Ch] [rbp-19Ch]
  int v56; // [rsp+190h] [rbp-198h]
  char v57; // [rsp+194h] [rbp-194h]
  int v58; // [rsp+198h] [rbp-190h]
  char v59; // [rsp+19Ch] [rbp-18Ch]
  int v60; // [rsp+1A0h] [rbp-188h]
  char v61; // [rsp+1A4h] [rbp-184h]
  int v62; // [rsp+1A8h] [rbp-180h]
  char v63; // [rsp+1ACh] [rbp-17Ch]
  int v64; // [rsp+1B0h] [rbp-178h]
  char v65; // [rsp+1B4h] [rbp-174h]
  int v66; // [rsp+1B8h] [rbp-170h]
  char v67; // [rsp+1BCh] [rbp-16Ch]
  int v68; // [rsp+1C0h] [rbp-168h]
  char v69; // [rsp+1C4h] [rbp-164h]
  int v70; // [rsp+1C8h] [rbp-160h]
  char v71; // [rsp+1CCh] [rbp-15Ch]
  int v72; // [rsp+1D0h] [rbp-158h]
  char v73; // [rsp+1D4h] [rbp-154h]
  int v74; // [rsp+1D8h] [rbp-150h]
  char v75; // [rsp+1DCh] [rbp-14Ch]
  int v76; // [rsp+1E0h] [rbp-148h]
  char v77; // [rsp+1E4h] [rbp-144h]
  int v78; // [rsp+1E8h] [rbp-140h]
  char v79; // [rsp+1ECh] [rbp-13Ch]
  int v80; // [rsp+1F0h] [rbp-138h]
  char v81; // [rsp+1F4h] [rbp-134h]
  int v82; // [rsp+1F8h] [rbp-130h]
  char v83; // [rsp+1FCh] [rbp-12Ch]
  int v84; // [rsp+200h] [rbp-128h]
  char v85; // [rsp+204h] [rbp-124h]
  int v86; // [rsp+208h] [rbp-120h]
  char v87; // [rsp+20Ch] [rbp-11Ch]
  int v88; // [rsp+210h] [rbp-118h]
  char v89; // [rsp+214h] [rbp-114h]
  int v90; // [rsp+218h] [rbp-110h]
  char v91; // [rsp+21Ch] [rbp-10Ch]
  int v92; // [rsp+220h] [rbp-108h]
  char v93; // [rsp+224h] [rbp-104h]
  int v94; // [rsp+228h] [rbp-100h]
  char v95; // [rsp+22Ch] [rbp-FCh]
  int v96; // [rsp+230h] [rbp-F8h]
  char v97; // [rsp+234h] [rbp-F4h]
  int v98; // [rsp+238h] [rbp-F0h]
  char v99; // [rsp+23Ch] [rbp-ECh]
  int v100; // [rsp+240h] [rbp-E8h]
  char v101; // [rsp+244h] [rbp-E4h]
  int v102; // [rsp+248h] [rbp-E0h]
  char v103; // [rsp+24Ch] [rbp-DCh]
  int v104; // [rsp+250h] [rbp-D8h]
  char v105; // [rsp+254h] [rbp-D4h]
  int v106; // [rsp+258h] [rbp-D0h]
  char v107; // [rsp+25Ch] [rbp-CCh]
  int v108; // [rsp+260h] [rbp-C8h]
  char v109; // [rsp+264h] [rbp-C4h]
  int v110; // [rsp+268h] [rbp-C0h]
  char v111; // [rsp+26Ch] [rbp-BCh]
  int v112; // [rsp+270h] [rbp-B8h]
  char v113; // [rsp+274h] [rbp-B4h]
  int v114; // [rsp+278h] [rbp-B0h]
  char v115; // [rsp+27Ch] [rbp-ACh]
  int v116; // [rsp+280h] [rbp-A8h]
  char v117; // [rsp+284h] [rbp-A4h]
  int v118; // [rsp+288h] [rbp-A0h]
  char v119; // [rsp+28Ch] [rbp-9Ch]
  int v120; // [rsp+290h] [rbp-98h]
  char v121; // [rsp+294h] [rbp-94h]
  int v122; // [rsp+298h] [rbp-90h]
  char v123; // [rsp+29Ch] [rbp-8Ch]
  int v124; // [rsp+2A0h] [rbp-88h]
  char v125; // [rsp+2A4h] [rbp-84h]
  int v126; // [rsp+2A8h] [rbp-80h]
  char v127; // [rsp+2ACh] [rbp-7Ch]
  int v128; // [rsp+2B0h] [rbp-78h]
  char v129; // [rsp+2B4h] [rbp-74h]
  int v130; // [rsp+2B8h] [rbp-70h]
  char v131; // [rsp+2BCh] [rbp-6Ch]
  int v132; // [rsp+2C0h] [rbp-68h]
  char v133; // [rsp+2C4h] [rbp-64h]
  int v134; // [rsp+2C8h] [rbp-60h]
  char v135; // [rsp+2CCh] [rbp-5Ch]
  int v136; // [rsp+2D0h] [rbp-58h]
  char v137; // [rsp+2D4h] [rbp-54h]
  int v138; // [rsp+2D8h] [rbp-50h]
  char v139; // [rsp+2DCh] [rbp-4Ch]
  int v140; // [rsp+2E0h] [rbp-48h]
  char v141; // [rsp+2E4h] [rbp-44h]

  memset_0(&instance, 0, 0x238u);
  v14 = 0;
  String = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_Policy_Config01_Audit02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180353FCF,
      v21,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v16, v4);
  try
  {
    v15 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_Audit02_NodeList, 61, 2, &v15);
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Audit02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v15;
                if ( v15 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_226;
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
                      L"Audit",
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
                        L"AccountLogon_AuditCredentialValidation",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogon_AuditKerberosAuthenticationService",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogon_AuditKerberosServiceTicketOperations",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogon_AuditOtherAccountLogonEvents",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditAccountLockout",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditGroupMembership",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditIPsecExtendedMode",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditIPsecMainMode",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditIPsecQuickMode",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditLogoff",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditLogon",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditNetworkPolicyServer",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditSpecialLogon",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditUserDeviceClaims",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditApplicationGroupManagement",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditComputerAccountManagement",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditDistributionGroupManagement",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditOtherAccountManagementEvents",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditSecurityGroupManagement",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditUserAccountManagement",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditDPAPIActivity",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditPNPActivity",
                        &String)
                  && String )
                {
                  v68 = _wtoi(String);
                  v69 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditProcessCreation",
                        &String)
                  && String )
                {
                  v70 = _wtoi(String);
                  v71 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditProcessTermination",
                        &String)
                  && String )
                {
                  v72 = _wtoi(String);
                  v73 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditRPCEvents",
                        &String)
                  && String )
                {
                  v74 = _wtoi(String);
                  v75 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditTokenRightAdjusted",
                        &String)
                  && String )
                {
                  v76 = _wtoi(String);
                  v77 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DSAccess_AuditDetailedDirectoryServiceReplication",
                        &String)
                  && String )
                {
                  v78 = _wtoi(String);
                  v79 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DSAccess_AuditDirectoryServiceAccess",
                        &String)
                  && String )
                {
                  v80 = _wtoi(String);
                  v81 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DSAccess_AuditDirectoryServiceChanges",
                        &String)
                  && String )
                {
                  v82 = _wtoi(String);
                  v83 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DSAccess_AuditDirectoryServiceReplication",
                        &String)
                  && String )
                {
                  v84 = _wtoi(String);
                  v85 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditApplicationGenerated",
                        &String)
                  && String )
                {
                  v86 = _wtoi(String);
                  v87 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditCentralAccessPolicyStaging",
                        &String)
                  && String )
                {
                  v88 = _wtoi(String);
                  v89 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditCertificationServices",
                        &String)
                  && String )
                {
                  v90 = _wtoi(String);
                  v91 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditDetailedFileShare",
                        &String)
                  && String )
                {
                  v92 = _wtoi(String);
                  v93 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditFileShare",
                        &String)
                  && String )
                {
                  v94 = _wtoi(String);
                  v95 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditFileSystem",
                        &String)
                  && String )
                {
                  v96 = _wtoi(String);
                  v97 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditFilteringPlatformConnection",
                        &String)
                  && String )
                {
                  v98 = _wtoi(String);
                  v99 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                        &String)
                  && String )
                {
                  v100 = _wtoi(String);
                  v101 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditHandleManipulation",
                        &String)
                  && String )
                {
                  v102 = _wtoi(String);
                  v103 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditKernelObject",
                        &String)
                  && String )
                {
                  v104 = _wtoi(String);
                  v105 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditOtherObjectAccessEvents",
                        &String)
                  && String )
                {
                  v106 = _wtoi(String);
                  v107 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditRegistry",
                        &String)
                  && String )
                {
                  v108 = _wtoi(String);
                  v109 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditRemovableStorage",
                        &String)
                  && String )
                {
                  v110 = _wtoi(String);
                  v111 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditSAM",
                        &String)
                  && String )
                {
                  v112 = _wtoi(String);
                  v113 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditAuthenticationPolicyChange",
                        &String)
                  && String )
                {
                  v114 = _wtoi(String);
                  v115 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditAuthorizationPolicyChange",
                        &String)
                  && String )
                {
                  v116 = _wtoi(String);
                  v117 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditFilteringPlatformPolicyChange",
                        &String)
                  && String )
                {
                  v118 = _wtoi(String);
                  v119 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                        &String)
                  && String )
                {
                  v120 = _wtoi(String);
                  v121 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditOtherPolicyChangeEvents",
                        &String)
                  && String )
                {
                  v122 = _wtoi(String);
                  v123 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditPolicyChange",
                        &String)
                  && String )
                {
                  v124 = _wtoi(String);
                  v125 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                        &String)
                  && String )
                {
                  v126 = _wtoi(String);
                  v127 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                        &String)
                  && String )
                {
                  v128 = _wtoi(String);
                  v129 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PrivilegeUse_AuditSensitivePrivilegeUse",
                        &String)
                  && String )
                {
                  v130 = _wtoi(String);
                  v131 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"System_AuditIPsecDriver",
                        &String)
                  && String )
                {
                  v132 = _wtoi(String);
                  v133 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"System_AuditOtherSystemEvents",
                        &String)
                  && String )
                {
                  v134 = _wtoi(String);
                  v135 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"System_AuditSecurityStateChange",
                        &String)
                  && String )
                {
                  v136 = _wtoi(String);
                  v137 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"System_AuditSecuritySystemExtension",
                        &String)
                  && String )
                {
                  v138 = _wtoi(String);
                  v139 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"System_AuditSystemIntegrity",
                        &String)
                  && String )
                {
                  v140 = _wtoi(String);
                  v141 = 1;
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
    goto LABEL_217;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_217:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (int)v15;
  }
LABEL_226:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_18034286E,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005e6f8  mov     [rsp+arg_8], rbx
0x18005e6fd  mov     [rsp+arg_10], rsi
0x18005e702  push    rdi
0x18005e703  push    r12
0x18005e705  push    r13
0x18005e707  push    r14
0x18005e709  push    r15
0x18005e70b  sub     rsp, 300h
0x18005e712  mov     rax, cs:__security_cookie
0x18005e719  xor     rax, rsp
0x18005e71c  mov     [rsp+328h+var_38], rax
0x18005e724  mov     r13b, dl
0x18005e727  mov     r12, rcx
0x18005e72a  xor     edx, edx; Val
0x18005e72c  mov     r8d, 238h; Size
0x18005e732  lea     rcx, [rsp+328h+instance]; void *
0x18005e73a  call    memset_0
0x18005e73f  xor     edi, edi
0x18005e741  mov     [rsp+328h+var_2E0], dil
0x18005e746  mov     [rsp+328h+String], rdi
0x18005e74b  mov     [rsp+328h+var_2A0], edi
0x18005e752  mov     [rsp+328h+var_29C], dil
0x18005e75a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18005e761  mov     [rsp+328h+var_2D0], rax
0x18005e766  lea     rax, [rsp+328h+var_2A0]
0x18005e76e  mov     [rsp+328h+var_2C8], rax
0x18005e773  lea     rax, aMdmPolicyConfi_129; "MDM_Policy_Config01_Audit02"
0x18005e77a  mov     [rsp+328h+var_2C0], rax
0x18005e77f  lea     rcx, [rsp+328h+var_2A0]
0x18005e787  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18005e78c  mov     eax, cs:dword_180380B68
0x18005e792  cmp     eax, 5
0x18005e795  jbe     short loc_18005E807
0x18005e797  mov     rdx, 200000000000h
0x18005e7a1  lea     rcx, dword_180380B68
0x18005e7a8  call    _tlgKeywordOn
0x18005e7ad  test    al, al
0x18005e7af  jz      short loc_18005E807
0x18005e7b1  cmp     [rsp+328h+var_29C], dil
0x18005e7b9  jz      short loc_18005E7E9
0x18005e7bb  cmp     [rsp+328h+var_288], edi
0x18005e7c2  jnz     short loc_18005E7DF
0x18005e7c4  cmp     [rsp+328h+var_284], edi
0x18005e7cb  jnz     short loc_18005E7DF
0x18005e7cd  cmp     [rsp+328h+var_280], edi
0x18005e7d4  jnz     short loc_18005E7DF
0x18005e7d6  cmp     [rsp+328h+var_27C], edi
0x18005e7dd  jz      short loc_18005E7E9
0x18005e7df  lea     r9, [rsp+328h+var_288]
0x18005e7e7  jmp     short loc_18005E7EC
0x18005e7e9  mov     r9, rdi
0x18005e7ec  lea     r8, [rsp+328h+var_298]
0x18005e7f4  lea     rdx, byte_180353FCF
0x18005e7fb  lea     rcx, dword_180380B68
0x18005e802  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18005e807  lea     rcx, [rsp+328h+var_2D0]; this
0x18005e80c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18005e811  nop
0x18005e812  mov     [rsp+328h+var_2D8], rdi
0x18005e817  lea     rax, [rsp+328h+var_2D8]
0x18005e81c  mov     [rsp+328h+var_2F8], rax
0x18005e821  mov     [rsp+328h+var_300], 2
0x18005e829  mov     [rsp+328h+var_308], 3Dh ; '='
0x18005e831  lea     r9, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Audit02_NodeList
0x18005e838  xor     r8d, r8d
0x18005e83b  xor     edx, edx
0x18005e83d  mov     rcx, r12
0x18005e840  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18005e845  mov     r15d, eax
0x18005e848  test    eax, eax
0x18005e84a  jz      short loc_18005E851
0x18005e84c  jmp     loc_18005FA9D
0x18005e851  lea     rbx, [rsp+328h+var_2D8]
0x18005e856  mov     [rsp+328h+var_2B0], rbx
0x18005e85b  mov     r14d, 1
0x18005e861  mov     [rsp+328h+var_2A8], r14b
0x18005e869  mov     rsi, [rsp+328h+var_2D8]
0x18005e86e  test    rsi, rsi
0x18005e871  jnz     short loc_18005E87B
0x18005e873  mov     r15d, r14d
0x18005e876  jmp     loc_18005FA9D
0x18005e87b  mov     rax, [rsi]
0x18005e87e  mov     rcx, rsi
0x18005e881  mov     rax, [rax+10h]
0x18005e885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e88a  mov     r15d, eax
0x18005e88d  test    eax, eax
0x18005e88f  jz      short loc_18005E8AF
0x18005e891  mov     rcx, [rsp+328h+var_2D8]
0x18005e896  test    rcx, rcx
0x18005e899  jz      short loc_18005E8AA
0x18005e89b  mov     rax, [rcx]
0x18005e89e  mov     edx, r14d
0x18005e8a1  mov     rax, [rax]
0x18005e8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8a9  nop
0x18005e8aa  jmp     loc_18005FA9D
0x18005e8af  mov     rax, [rsi]
0x18005e8b2  mov     rcx, rsi
0x18005e8b5  mov     rax, [rax+8]
0x18005e8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8be  mov     r15d, eax
0x18005e8c1  test    eax, eax
0x18005e8c3  jz      short loc_18005E8E3
0x18005e8c5  mov     rcx, [rsp+328h+var_2D8]
0x18005e8ca  test    rcx, rcx
0x18005e8cd  jz      short loc_18005E8DE
0x18005e8cf  mov     rax, [rcx]
0x18005e8d2  mov     edx, r14d
0x18005e8d5  mov     rax, [rax]
0x18005e8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8dd  nop
0x18005e8de  jmp     loc_18005FA9D
0x18005e8e3  mov     r14d, edi
0x18005e8e6  mov     rax, [rsi+108h]
0x18005e8ed  sub     rax, [rsi+100h]
0x18005e8f4  sar     rax, 4
0x18005e8f8  cmp     r14d, eax
0x18005e8fb  jnb     loc_18005FA65
0x18005e901  lea     r8, [rsp+328h+instance]; instance
0x18005e909  lea     rdx, MDM_Policy_Config01_Audit02_rtti; classDecl
0x18005e910  mov     rcx, r12; context
0x18005e913  call    MI_Context_ConstructInstance
0x18005e918  mov     r15d, eax
0x18005e91b  test    eax, eax
0x18005e91d  jz      short loc_18005E93F
0x18005e91f  mov     rcx, [rbx]
0x18005e922  test    rcx, rcx
0x18005e925  jz      short loc_18005E93A
0x18005e927  mov     rax, [rcx]
0x18005e92a  mov     edx, 1
0x18005e92f  mov     rax, [rax]
0x18005e932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e937  mov     [rbx], rdi
0x18005e93a  jmp     loc_18005FA9D
0x18005e93f  mov     [rsp+328h+var_2E0], 1
0x18005e944  mov     rax, [rsi]
0x18005e947  lea     r9, [rsp+328h+String]
0x18005e94c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18005e953  mov     edx, r14d
0x18005e956  mov     rcx, rsi
0x18005e959  mov     rax, [rax+18h]
0x18005e95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e962  test    eax, eax
0x18005e964  jnz     short loc_18005E97D
0x18005e966  mov     rdx, [rsp+328h+String]
0x18005e96b  test    rdx, rdx
0x18005e96e  jz      short loc_18005E97D
0x18005e970  lea     rcx, [rsp+328h+instance]
0x18005e978  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18005e97d  mov     rax, [rsi]
0x18005e980  lea     r9, [rsp+328h+String]
0x18005e985  lea     r8, aAudit; "Audit"
0x18005e98c  mov     edx, r14d
0x18005e98f  mov     rcx, rsi
0x18005e992  mov     rax, [rax+18h]
0x18005e996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e99b  test    eax, eax
0x18005e99d  jnz     short loc_18005E9B6
0x18005e99f  mov     rdx, [rsp+328h+String]
0x18005e9a4  test    rdx, rdx
0x18005e9a7  jz      short loc_18005E9B6
0x18005e9a9  lea     rcx, [rsp+328h+instance]
0x18005e9b1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18005e9b6  cmp     r13b, 1
0x18005e9ba  jnz     short loc_18005E9DE
0x18005e9bc  lea     rdx, [rsp+328h+instance]
0x18005e9c4  mov     rcx, r12; self
0x18005e9c7  call    MI_Instance_Destruct
0x18005e9cc  lea     rcx, [rsp+328h+instance]; self
0x18005e9d4  call    MI_Instance_Destruct
0x18005e9d9  jmp     loc_18005FA58
0x18005e9de  mov     rax, [rsi]
0x18005e9e1  lea     r9, [rsp+328h+String]
0x18005e9e6  lea     r8, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x18005e9ed  mov     edx, r14d
0x18005e9f0  mov     rcx, rsi
0x18005e9f3  mov     rax, [rax+18h]
0x18005e9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9fc  test    eax, eax
0x18005e9fe  jnz     short loc_18005EA25
0x18005ea00  mov     rcx, [rsp+328h+String]; String
0x18005ea05  test    rcx, rcx
0x18005ea08  jz      short loc_18005EA25
0x18005ea0a  call    cs:__imp__wtoi
0x18005ea11  nop     dword ptr [rax+rax+00h]
0x18005ea16  mov     [rsp+328h+var_218], eax
0x18005ea1d  mov     [rsp+328h+var_214], 1
0x18005ea25  mov     rax, [rsi]
0x18005ea28  lea     r9, [rsp+328h+String]
0x18005ea2d  lea     r8, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x18005ea34  mov     edx, r14d
0x18005ea37  mov     rcx, rsi
0x18005ea3a  mov     rax, [rax+18h]
0x18005ea3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea43  test    eax, eax
0x18005ea45  jnz     short loc_18005EA6C
0x18005ea47  mov     rcx, [rsp+328h+String]; String
0x18005ea4c  test    rcx, rcx
0x18005ea4f  jz      short loc_18005EA6C
0x18005ea51  call    cs:__imp__wtoi
0x18005ea58  nop     dword ptr [rax+rax+00h]
0x18005ea5d  mov     [rsp+328h+var_210], eax
0x18005ea64  mov     [rsp+328h+var_20C], 1
0x18005ea6c  mov     rax, [rsi]
0x18005ea6f  lea     r9, [rsp+328h+String]
0x18005ea74  lea     r8, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x18005ea7b  mov     edx, r14d
0x18005ea7e  mov     rcx, rsi
0x18005ea81  mov     rax, [rax+18h]
0x18005ea85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea8a  test    eax, eax
0x18005ea8c  jnz     short loc_18005EAB3
0x18005ea8e  mov     rcx, [rsp+328h+String]; String
0x18005ea93  test    rcx, rcx
0x18005ea96  jz      short loc_18005EAB3
0x18005ea98  call    cs:__imp__wtoi
0x18005ea9f  nop     dword ptr [rax+rax+00h]
0x18005eaa4  mov     [rsp+328h+var_208], eax
0x18005eaab  mov     [rsp+328h+var_204], 1
0x18005eab3  mov     rax, [rsi]
0x18005eab6  lea     r9, [rsp+328h+String]
0x18005eabb  lea     r8, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x18005eac2  mov     edx, r14d
0x18005eac5  mov     rcx, rsi
0x18005eac8  mov     rax, [rax+18h]
0x18005eacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ead1  test    eax, eax
0x18005ead3  jnz     short loc_18005EAFA
0x18005ead5  mov     rcx, [rsp+328h+String]; String
0x18005eada  test    rcx, rcx
0x18005eadd  jz      short loc_18005EAFA
0x18005eadf  call    cs:__imp__wtoi
0x18005eae6  nop     dword ptr [rax+rax+00h]
0x18005eaeb  mov     [rsp+328h+var_200], eax
0x18005eaf2  mov     [rsp+328h+var_1FC], 1
0x18005eafa  mov     rax, [rsi]
0x18005eafd  lea     r9, [rsp+328h+String]
0x18005eb02  lea     r8, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x18005eb09  mov     edx, r14d
0x18005eb0c  mov     rcx, rsi
0x18005eb0f  mov     rax, [rax+18h]
0x18005eb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb18  test    eax, eax
0x18005eb1a  jnz     short loc_18005EB41
0x18005eb1c  mov     rcx, [rsp+328h+String]; String
0x18005eb21  test    rcx, rcx
0x18005eb24  jz      short loc_18005EB41
0x18005eb26  call    cs:__imp__wtoi
0x18005eb2d  nop     dword ptr [rax+rax+00h]
0x18005eb32  mov     [rsp+328h+var_1F8], eax
0x18005eb39  mov     [rsp+328h+var_1F4], 1
0x18005eb41  mov     rax, [rsi]
0x18005eb44  lea     r9, [rsp+328h+String]
0x18005eb49  lea     r8, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x18005eb50  mov     edx, r14d
0x18005eb53  mov     rcx, rsi
0x18005eb56  mov     rax, [rax+18h]
0x18005eb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb5f  test    eax, eax
0x18005eb61  jnz     short loc_18005EB88
0x18005eb63  mov     rcx, [rsp+328h+String]; String
0x18005eb68  test    rcx, rcx
0x18005eb6b  jz      short loc_18005EB88
0x18005eb6d  call    cs:__imp__wtoi
0x18005eb74  nop     dword ptr [rax+rax+00h]
0x18005eb79  mov     [rsp+328h+var_1F0], eax
0x18005eb80  mov     [rsp+328h+var_1EC], 1
0x18005eb88  mov     rax, [rsi]
0x18005eb8b  lea     r9, [rsp+328h+String]
0x18005eb90  lea     r8, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x18005eb97  mov     edx, r14d
0x18005eb9a  mov     rcx, rsi
0x18005eb9d  mov     rax, [rax+18h]
0x18005eba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eba6  test    eax, eax
0x18005eba8  jnz     short loc_18005EBCF
0x18005ebaa  mov     rcx, [rsp+328h+String]; String
0x18005ebaf  test    rcx, rcx
0x18005ebb2  jz      short loc_18005EBCF
0x18005ebb4  call    cs:__imp__wtoi
0x18005ebbb  nop     dword ptr [rax+rax+00h]
0x18005ebc0  mov     [rsp+328h+var_1E8], eax
0x18005ebc7  mov     [rsp+328h+var_1E4], 1
0x18005ebcf  mov     rax, [rsi]
0x18005ebd2  lea     r9, [rsp+328h+String]
0x18005ebd7  lea     r8, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x18005ebde  mov     edx, r14d
0x18005ebe1  mov     rcx, rsi
0x18005ebe4  mov     rax, [rax+18h]
0x18005ebe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ebed  test    eax, eax
0x18005ebef  jnz     short loc_18005EC16
0x18005ebf1  mov     rcx, [rsp+328h+String]; String
0x18005ebf6  test    rcx, rcx
0x18005ebf9  jz      short loc_18005EC16
0x18005ebfb  call    cs:__imp__wtoi
0x18005ec02  nop     dword ptr [rax+rax+00h]
0x18005ec07  mov     [rsp+328h+var_1E0], eax
0x18005ec0e  mov     [rsp+328h+var_1DC], 1
  ... truncated ...
```
