# MDM_Policy_Config01_Audit02_InvokeEnumerateInstances

- ea: `0x18005f0f4`
- end: `0x1800603d7`
- name: `MDM_Policy_Config01_Audit02_InvokeEnumerateInstances`
- size: `4835`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005dbb0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18005f0f4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18005f406`
- `msvcrt!_wtoi` at `0x18005f447`
- `msvcrt!_wtoi` at `0x18005f488`
- `msvcrt!_wtoi` at `0x18005f4c9`
- `msvcrt!_wtoi` at `0x18005f50a`
- `msvcrt!_wtoi` at `0x18005f54b`
- `msvcrt!_wtoi` at `0x18005f58c`
- `msvcrt!_wtoi` at `0x18005f5cd`
- `msvcrt!_wtoi` at `0x18005f60e`
- `msvcrt!_wtoi` at `0x18005f64f`
- `msvcrt!_wtoi` at `0x18005f690`
- `msvcrt!_wtoi` at `0x18005f6d1`
- `msvcrt!_wtoi` at `0x18005f712`
- `msvcrt!_wtoi` at `0x18005f753`
- `msvcrt!_wtoi` at `0x18005f794`
- `msvcrt!_wtoi` at `0x18005f7d5`
- `msvcrt!_wtoi` at `0x18005f816`
- `msvcrt!_wtoi` at `0x18005f857`
- `msvcrt!_wtoi` at `0x18005f898`
- `msvcrt!_wtoi` at `0x18005f8d9`
- `msvcrt!_wtoi` at `0x18005f91a`
- `msvcrt!_wtoi` at `0x18005f95b`
- `msvcrt!_wtoi` at `0x18005f99c`
- `msvcrt!_wtoi` at `0x18005f9dd`
- `msvcrt!_wtoi` at `0x18005fa1e`
- `msvcrt!_wtoi` at `0x18005fa5f`
- `msvcrt!_wtoi` at `0x18005faa0`
- `msvcrt!_wtoi` at `0x18005fae1`
- `msvcrt!_wtoi` at `0x18005fb22`
- `msvcrt!_wtoi` at `0x18005fb63`
- `msvcrt!_wtoi` at `0x18005fba4`
- `msvcrt!_wtoi` at `0x18005fbe5`
- `msvcrt!_wtoi` at `0x18005fc26`
- `msvcrt!_wtoi` at `0x18005fc67`
- `msvcrt!_wtoi` at `0x18005fca8`
- `msvcrt!_wtoi` at `0x18005fce9`
- `msvcrt!_wtoi` at `0x18005fd2a`
- `msvcrt!_wtoi` at `0x18005fd6b`
- `msvcrt!_wtoi` at `0x18005fdac`
- `msvcrt!_wtoi` at `0x18005fded`
- `msvcrt!_wtoi` at `0x18005fe2e`
- `msvcrt!_wtoi` at `0x18005fe6f`
- `msvcrt!_wtoi` at `0x18005feb0`
- `msvcrt!_wtoi` at `0x18005fef1`
- `msvcrt!_wtoi` at `0x18005ff32`
- `msvcrt!_wtoi` at `0x18005ff73`
- `msvcrt!_wtoi` at `0x18005ffb4`
- `msvcrt!_wtoi` at `0x18005fff5`
- `msvcrt!_wtoi` at `0x180060036`
- `msvcrt!_wtoi` at `0x180060077`
- `msvcrt!_wtoi` at `0x1800600b8`
- `msvcrt!_wtoi` at `0x1800600f9`
- `msvcrt!_wtoi` at `0x18006013a`
- `msvcrt!_wtoi` at `0x18006017b`
- `msvcrt!_wtoi` at `0x1800601bc`
- `msvcrt!_wtoi` at `0x1800601fd`
- `msvcrt!_wtoi` at `0x18006023e`
- `msvcrt!_wtoi` at `0x18006027f`
- `msvcrt!_wtoi` at `0x1800602c0`
- `msvcrt!_wtoi` at `0x18005f406`
- `msvcrt!_wtoi` at `0x18005f447`
- `msvcrt!_wtoi` at `0x18005f488`
- `msvcrt!_wtoi` at `0x18005f4c9`
- `msvcrt!_wtoi` at `0x18005f50a`
- `msvcrt!_wtoi` at `0x18005f54b`
- `msvcrt!_wtoi` at `0x18005f58c`
- `msvcrt!_wtoi` at `0x18005f5cd`
- `msvcrt!_wtoi` at `0x18005f60e`
- `msvcrt!_wtoi` at `0x18005f64f`
- `msvcrt!_wtoi` at `0x18005f690`
- `msvcrt!_wtoi` at `0x18005f6d1`
- `msvcrt!_wtoi` at `0x18005f712`
- `msvcrt!_wtoi` at `0x18005f753`
- `msvcrt!_wtoi` at `0x18005f794`
- `msvcrt!_wtoi` at `0x18005f7d5`
- `msvcrt!_wtoi` at `0x18005f816`
- `msvcrt!_wtoi` at `0x18005f857`
- `msvcrt!_wtoi` at `0x18005f898`
- `msvcrt!_wtoi` at `0x18005f8d9`
- `msvcrt!_wtoi` at `0x18005f91a`
- `msvcrt!_wtoi` at `0x18005f95b`
- `msvcrt!_wtoi` at `0x18005f99c`
- `msvcrt!_wtoi` at `0x18005f9dd`
- `msvcrt!_wtoi` at `0x18005fa1e`
- `msvcrt!_wtoi` at `0x18005fa5f`
- `msvcrt!_wtoi` at `0x18005faa0`
- `msvcrt!_wtoi` at `0x18005fae1`
- `msvcrt!_wtoi` at `0x18005fb22`
- `msvcrt!_wtoi` at `0x18005fb63`
- `msvcrt!_wtoi` at `0x18005fba4`
- `msvcrt!_wtoi` at `0x18005fbe5`
- `msvcrt!_wtoi` at `0x18005fc26`
- `msvcrt!_wtoi` at `0x18005fc67`
- `msvcrt!_wtoi` at `0x18005fca8`
- `msvcrt!_wtoi` at `0x18005fce9`
- `msvcrt!_wtoi` at `0x18005fd2a`
- `msvcrt!_wtoi` at `0x18005fd6b`
- `msvcrt!_wtoi` at `0x18005fdac`
- `msvcrt!_wtoi` at `0x18005fded`
- `msvcrt!_wtoi` at `0x18005fe2e`
- `msvcrt!_wtoi` at `0x18005fe6f`
- `msvcrt!_wtoi` at `0x18005feb0`
- `msvcrt!_wtoi` at `0x18005fef1`
- `msvcrt!_wtoi` at `0x18005ff32`
- `msvcrt!_wtoi` at `0x18005ff73`
- `msvcrt!_wtoi` at `0x18005ffb4`
- `msvcrt!_wtoi` at `0x18005fff5`
- `msvcrt!_wtoi` at `0x180060036`
- `msvcrt!_wtoi` at `0x180060077`
- `msvcrt!_wtoi` at `0x1800600b8`
- `msvcrt!_wtoi` at `0x1800600f9`
- `msvcrt!_wtoi` at `0x18006013a`
- `msvcrt!_wtoi` at `0x18006017b`
- `msvcrt!_wtoi` at `0x1800601bc`
- `msvcrt!_wtoi` at `0x1800601fd`
- `msvcrt!_wtoi` at `0x18006023e`
- `msvcrt!_wtoi` at `0x18006027f`
- `msvcrt!_wtoi` at `0x1800602c0`

## string_xrefs

- `0x18005f423`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x18005f464`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x18005f7f2`: `AccountManagement_AuditComputerAccountManagement`
- `0x18005f8b5`: `AccountManagement_AuditSecurityGroupManagement`
- `0x18005fa7c`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x18005fabd`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x18005fafe`: `DSAccess_AuditDirectoryServiceAccess`
- `0x18005fb3f`: `DSAccess_AuditDirectoryServiceChanges`
- `0x18005fb80`: `DSAccess_AuditDirectoryServiceReplication`
- `0x18005fbc1`: `ObjectAccess_AuditApplicationGenerated`
- `0x18005fc02`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x18005fc43`: `ObjectAccess_AuditCertificationServices`
- `0x18005fc84`: `ObjectAccess_AuditDetailedFileShare`
- `0x18005fcc5`: `ObjectAccess_AuditFileShare`
- `0x18005fd06`: `ObjectAccess_AuditFileSystem`
- `0x18005fd47`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x18005fd88`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x18005fdc9`: `ObjectAccess_AuditHandleManipulation`
- `0x18005fe0a`: `ObjectAccess_AuditKernelObject`
- `0x18005fe4b`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x18005fe8c`: `ObjectAccess_AuditRegistry`
- `0x18005fecd`: `ObjectAccess_AuditRemovableStorage`
- `0x18005ff0e`: `ObjectAccess_AuditSAM`
- `0x1800600d5`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x180060116`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x180060157`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x18006021a`: `System_AuditSecurityStateChange`
- `0x18006025b`: `System_AuditSecuritySystemExtension`
- `0x18005f348`: `./Vendor/MSFT/Policy/Config`
- `0x18005f16f`: `MDM_Policy_Config01_Audit02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Audit02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-2E8h] BYREF
  char v14; // [rsp+48h] [rbp-2E0h]
  WmiRequestHandlerAdd *v15; // [rsp+50h] [rbp-2D8h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_Audit02_NodeList,
           0x3Du,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Audit02_rtti, &instance);
              if ( v7 )
              {
                v6 = v15;
                if ( v15 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_226;
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
                      L"Audit",
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
                        L"AccountLogon_AuditCredentialValidation",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogon_AuditKerberosAuthenticationService",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogon_AuditKerberosServiceTicketOperations",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogon_AuditOtherAccountLogonEvents",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditAccountLockout",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditGroupMembership",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditIPsecExtendedMode",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditIPsecMainMode",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditIPsecQuickMode",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditLogoff",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditLogon",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditNetworkPolicyServer",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditSpecialLogon",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountLogonLogoff_AuditUserDeviceClaims",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditApplicationGroupManagement",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditComputerAccountManagement",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditDistributionGroupManagement",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditOtherAccountManagementEvents",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditSecurityGroupManagement",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccountManagement_AuditUserAccountManagement",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditDPAPIActivity",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditPNPActivity",
                        &String)
                  && String )
                {
                  v68 = _wtoi(String);
                  v69 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditProcessCreation",
                        &String)
                  && String )
                {
                  v70 = _wtoi(String);
                  v71 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditProcessTermination",
                        &String)
                  && String )
                {
                  v72 = _wtoi(String);
                  v73 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditRPCEvents",
                        &String)
                  && String )
                {
                  v74 = _wtoi(String);
                  v75 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DetailedTracking_AuditTokenRightAdjusted",
                        &String)
                  && String )
                {
                  v76 = _wtoi(String);
                  v77 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DSAccess_AuditDetailedDirectoryServiceReplication",
                        &String)
                  && String )
                {
                  v78 = _wtoi(String);
                  v79 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DSAccess_AuditDirectoryServiceAccess",
                        &String)
                  && String )
                {
                  v80 = _wtoi(String);
                  v81 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DSAccess_AuditDirectoryServiceChanges",
                        &String)
                  && String )
                {
                  v82 = _wtoi(String);
                  v83 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DSAccess_AuditDirectoryServiceReplication",
                        &String)
                  && String )
                {
                  v84 = _wtoi(String);
                  v85 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditApplicationGenerated",
                        &String)
                  && String )
                {
                  v86 = _wtoi(String);
                  v87 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditCentralAccessPolicyStaging",
                        &String)
                  && String )
                {
                  v88 = _wtoi(String);
                  v89 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditCertificationServices",
                        &String)
                  && String )
                {
                  v90 = _wtoi(String);
                  v91 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditDetailedFileShare",
                        &String)
                  && String )
                {
                  v92 = _wtoi(String);
                  v93 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditFileShare",
                        &String)
                  && String )
                {
                  v94 = _wtoi(String);
                  v95 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditFileSystem",
                        &String)
                  && String )
                {
                  v96 = _wtoi(String);
                  v97 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditFilteringPlatformConnection",
                        &String)
                  && String )
                {
                  v98 = _wtoi(String);
                  v99 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                        &String)
                  && String )
                {
                  v100 = _wtoi(String);
                  v101 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditHandleManipulation",
                        &String)
                  && String )
                {
                  v102 = _wtoi(String);
                  v103 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditKernelObject",
                        &String)
                  && String )
                {
                  v104 = _wtoi(String);
                  v105 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditOtherObjectAccessEvents",
                        &String)
                  && String )
                {
                  v106 = _wtoi(String);
                  v107 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditRegistry",
                        &String)
                  && String )
                {
                  v108 = _wtoi(String);
                  v109 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditRemovableStorage",
                        &String)
                  && String )
                {
                  v110 = _wtoi(String);
                  v111 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ObjectAccess_AuditSAM",
                        &String)
                  && String )
                {
                  v112 = _wtoi(String);
                  v113 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditAuthenticationPolicyChange",
                        &String)
                  && String )
                {
                  v114 = _wtoi(String);
                  v115 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditAuthorizationPolicyChange",
                        &String)
                  && String )
                {
                  v116 = _wtoi(String);
                  v117 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditFilteringPlatformPolicyChange",
                        &String)
                  && String )
                {
                  v118 = _wtoi(String);
                  v119 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                        &String)
                  && String )
                {
                  v120 = _wtoi(String);
                  v121 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditOtherPolicyChangeEvents",
                        &String)
                  && String )
                {
                  v122 = _wtoi(String);
                  v123 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PolicyChange_AuditPolicyChange",
                        &String)
                  && String )
                {
                  v124 = _wtoi(String);
                  v125 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                        &String)
                  && String )
                {
                  v126 = _wtoi(String);
                  v127 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                        &String)
                  && String )
                {
                  v128 = _wtoi(String);
                  v129 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PrivilegeUse_AuditSensitivePrivilegeUse",
                        &String)
                  && String )
                {
                  v130 = _wtoi(String);
                  v131 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"System_AuditIPsecDriver",
                        &String)
                  && String )
                {
                  v132 = _wtoi(String);
                  v133 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"System_AuditOtherSystemEvents",
                        &String)
                  && String )
                {
                  v134 = _wtoi(String);
                  v135 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"System_AuditSecurityStateChange",
                        &String)
                  && String )
                {
                  v136 = _wtoi(String);
                  v137 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"System_AuditSecuritySystemExtension",
                        &String)
                  && String )
                {
                  v138 = _wtoi(String);
                  v139 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
    v7 = (unsigned int)v15;
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
  return v7;
}

```

## disassembly

```asm
0x18005f0f4  mov     [rsp+arg_8], rbx
0x18005f0f9  mov     [rsp+arg_10], rsi
0x18005f0fe  push    rdi
0x18005f0ff  push    r12
0x18005f101  push    r13
0x18005f103  push    r14
0x18005f105  push    r15
0x18005f107  sub     rsp, 300h
0x18005f10e  mov     rax, cs:__security_cookie
0x18005f115  xor     rax, rsp
0x18005f118  mov     [rsp+328h+var_38], rax
0x18005f120  mov     r13b, dl
0x18005f123  mov     r12, rcx
0x18005f126  xor     edx, edx; Val
0x18005f128  mov     r8d, 238h; Size
0x18005f12e  lea     rcx, [rsp+328h+instance]; void *
0x18005f136  call    memset_0
0x18005f13b  xor     edi, edi
0x18005f13d  mov     [rsp+328h+var_2E0], dil
0x18005f142  mov     [rsp+328h+String], rdi
0x18005f147  mov     [rsp+328h+var_2A0], edi
0x18005f14e  mov     [rsp+328h+var_29C], dil
0x18005f156  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18005f15d  mov     [rsp+328h+var_2D0], rax
0x18005f162  lea     rax, [rsp+328h+var_2A0]
0x18005f16a  mov     [rsp+328h+var_2C8], rax
0x18005f16f  lea     rax, aMdmPolicyConfi_129; "MDM_Policy_Config01_Audit02"
0x18005f176  mov     [rsp+328h+var_2C0], rax
0x18005f17b  lea     rcx, [rsp+328h+var_2A0]
0x18005f183  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18005f188  mov     eax, cs:dword_180380B68
0x18005f18e  cmp     eax, 5
0x18005f191  jbe     short loc_18005F203
0x18005f193  mov     rdx, 200000000000h
0x18005f19d  lea     rcx, dword_180380B68
0x18005f1a4  call    _tlgKeywordOn
0x18005f1a9  test    al, al
0x18005f1ab  jz      short loc_18005F203
0x18005f1ad  cmp     [rsp+328h+var_29C], dil
0x18005f1b5  jz      short loc_18005F1E5
0x18005f1b7  cmp     [rsp+328h+var_288], edi
0x18005f1be  jnz     short loc_18005F1DB
0x18005f1c0  cmp     [rsp+328h+var_284], edi
0x18005f1c7  jnz     short loc_18005F1DB
0x18005f1c9  cmp     [rsp+328h+var_280], edi
0x18005f1d0  jnz     short loc_18005F1DB
0x18005f1d2  cmp     [rsp+328h+var_27C], edi
0x18005f1d9  jz      short loc_18005F1E5
0x18005f1db  lea     r9, [rsp+328h+var_288]
0x18005f1e3  jmp     short loc_18005F1E8
0x18005f1e5  mov     r9, rdi
0x18005f1e8  lea     r8, [rsp+328h+var_298]
0x18005f1f0  lea     rdx, byte_180353FCF
0x18005f1f7  lea     rcx, dword_180380B68
0x18005f1fe  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18005f203  lea     rcx, [rsp+328h+var_2D0]; this
0x18005f208  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18005f20d  nop
0x18005f20e  mov     [rsp+328h+var_2D8], rdi
0x18005f213  lea     rax, [rsp+328h+var_2D8]
0x18005f218  mov     [rsp+328h+var_2F8], rax
0x18005f21d  mov     [rsp+328h+var_300], 2
0x18005f225  mov     [rsp+328h+var_308], 3Dh ; '='
0x18005f22d  lea     r9, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Audit02_NodeList
0x18005f234  xor     r8d, r8d
0x18005f237  xor     edx, edx
0x18005f239  mov     rcx, r12
0x18005f23c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18005f241  mov     r15d, eax
0x18005f244  test    eax, eax
0x18005f246  jz      short loc_18005F24D
0x18005f248  jmp     loc_180060337
0x18005f24d  lea     rbx, [rsp+328h+var_2D8]
0x18005f252  mov     [rsp+328h+var_2B0], rbx
0x18005f257  mov     r14d, 1
0x18005f25d  mov     [rsp+328h+var_2A8], r14b
0x18005f265  mov     rsi, [rsp+328h+var_2D8]
0x18005f26a  test    rsi, rsi
0x18005f26d  jnz     short loc_18005F277
0x18005f26f  mov     r15d, r14d
0x18005f272  jmp     loc_180060337
0x18005f277  mov     rax, [rsi]
0x18005f27a  mov     rcx, rsi
0x18005f27d  mov     rax, [rax+10h]
0x18005f281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f286  mov     r15d, eax
0x18005f289  test    eax, eax
0x18005f28b  jz      short loc_18005F2AB
0x18005f28d  mov     rcx, [rsp+328h+var_2D8]
0x18005f292  test    rcx, rcx
0x18005f295  jz      short loc_18005F2A6
0x18005f297  mov     rax, [rcx]
0x18005f29a  mov     edx, r14d
0x18005f29d  mov     rax, [rax]
0x18005f2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2a5  nop
0x18005f2a6  jmp     loc_180060337
0x18005f2ab  mov     rax, [rsi]
0x18005f2ae  mov     rcx, rsi
0x18005f2b1  mov     rax, [rax+8]
0x18005f2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2ba  mov     r15d, eax
0x18005f2bd  test    eax, eax
0x18005f2bf  jz      short loc_18005F2DF
0x18005f2c1  mov     rcx, [rsp+328h+var_2D8]
0x18005f2c6  test    rcx, rcx
0x18005f2c9  jz      short loc_18005F2DA
0x18005f2cb  mov     rax, [rcx]
0x18005f2ce  mov     edx, r14d
0x18005f2d1  mov     rax, [rax]
0x18005f2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2d9  nop
0x18005f2da  jmp     loc_180060337
0x18005f2df  mov     r14d, edi
0x18005f2e2  mov     rax, [rsi+108h]
0x18005f2e9  sub     rax, [rsi+100h]
0x18005f2f0  sar     rax, 4
0x18005f2f4  cmp     r14d, eax
0x18005f2f7  jnb     loc_1800602FF
0x18005f2fd  lea     r8, [rsp+328h+instance]; instance
0x18005f305  lea     rdx, MDM_Policy_Config01_Audit02_rtti; classDecl
0x18005f30c  mov     rcx, r12; context
0x18005f30f  call    MI_Context_ConstructInstance
0x18005f314  mov     r15d, eax
0x18005f317  test    eax, eax
0x18005f319  jz      short loc_18005F33B
0x18005f31b  mov     rcx, [rbx]
0x18005f31e  test    rcx, rcx
0x18005f321  jz      short loc_18005F336
0x18005f323  mov     rax, [rcx]
0x18005f326  mov     edx, 1
0x18005f32b  mov     rax, [rax]
0x18005f32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f333  mov     [rbx], rdi
0x18005f336  jmp     loc_180060337
0x18005f33b  mov     [rsp+328h+var_2E0], 1
0x18005f340  mov     rax, [rsi]
0x18005f343  lea     r9, [rsp+328h+String]
0x18005f348  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18005f34f  mov     edx, r14d
0x18005f352  mov     rcx, rsi
0x18005f355  mov     rax, [rax+18h]
0x18005f359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f35e  test    eax, eax
0x18005f360  jnz     short loc_18005F379
0x18005f362  mov     rdx, [rsp+328h+String]
0x18005f367  test    rdx, rdx
0x18005f36a  jz      short loc_18005F379
0x18005f36c  lea     rcx, [rsp+328h+instance]
0x18005f374  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18005f379  mov     rax, [rsi]
0x18005f37c  lea     r9, [rsp+328h+String]
0x18005f381  lea     r8, aAudit; "Audit"
0x18005f388  mov     edx, r14d
0x18005f38b  mov     rcx, rsi
0x18005f38e  mov     rax, [rax+18h]
0x18005f392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f397  test    eax, eax
0x18005f399  jnz     short loc_18005F3B2
0x18005f39b  mov     rdx, [rsp+328h+String]
0x18005f3a0  test    rdx, rdx
0x18005f3a3  jz      short loc_18005F3B2
0x18005f3a5  lea     rcx, [rsp+328h+instance]
0x18005f3ad  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18005f3b2  cmp     r13b, 1
0x18005f3b6  jnz     short loc_18005F3DA
0x18005f3b8  lea     rdx, [rsp+328h+instance]
0x18005f3c0  mov     rcx, r12; self
0x18005f3c3  call    MI_Instance_Destruct
0x18005f3c8  lea     rcx, [rsp+328h+instance]; self
0x18005f3d0  call    MI_Instance_Destruct
0x18005f3d5  jmp     loc_1800602F2
0x18005f3da  mov     rax, [rsi]
0x18005f3dd  lea     r9, [rsp+328h+String]
0x18005f3e2  lea     r8, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x18005f3e9  mov     edx, r14d
0x18005f3ec  mov     rcx, rsi
0x18005f3ef  mov     rax, [rax+18h]
0x18005f3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3f8  test    eax, eax
0x18005f3fa  jnz     short loc_18005F41B
0x18005f3fc  mov     rcx, [rsp+328h+String]; String
0x18005f401  test    rcx, rcx
0x18005f404  jz      short loc_18005F41B
0x18005f406  call    cs:__imp__wtoi
0x18005f40c  mov     [rsp+328h+var_218], eax
0x18005f413  mov     [rsp+328h+var_214], 1
0x18005f41b  mov     rax, [rsi]
0x18005f41e  lea     r9, [rsp+328h+String]
0x18005f423  lea     r8, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x18005f42a  mov     edx, r14d
0x18005f42d  mov     rcx, rsi
0x18005f430  mov     rax, [rax+18h]
0x18005f434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f439  test    eax, eax
0x18005f43b  jnz     short loc_18005F45C
0x18005f43d  mov     rcx, [rsp+328h+String]; String
0x18005f442  test    rcx, rcx
0x18005f445  jz      short loc_18005F45C
0x18005f447  call    cs:__imp__wtoi
0x18005f44d  mov     [rsp+328h+var_210], eax
0x18005f454  mov     [rsp+328h+var_20C], 1
0x18005f45c  mov     rax, [rsi]
0x18005f45f  lea     r9, [rsp+328h+String]
0x18005f464  lea     r8, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x18005f46b  mov     edx, r14d
0x18005f46e  mov     rcx, rsi
0x18005f471  mov     rax, [rax+18h]
0x18005f475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f47a  test    eax, eax
0x18005f47c  jnz     short loc_18005F49D
0x18005f47e  mov     rcx, [rsp+328h+String]; String
0x18005f483  test    rcx, rcx
0x18005f486  jz      short loc_18005F49D
0x18005f488  call    cs:__imp__wtoi
0x18005f48e  mov     [rsp+328h+var_208], eax
0x18005f495  mov     [rsp+328h+var_204], 1
0x18005f49d  mov     rax, [rsi]
0x18005f4a0  lea     r9, [rsp+328h+String]
0x18005f4a5  lea     r8, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x18005f4ac  mov     edx, r14d
0x18005f4af  mov     rcx, rsi
0x18005f4b2  mov     rax, [rax+18h]
0x18005f4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f4bb  test    eax, eax
0x18005f4bd  jnz     short loc_18005F4DE
0x18005f4bf  mov     rcx, [rsp+328h+String]; String
0x18005f4c4  test    rcx, rcx
0x18005f4c7  jz      short loc_18005F4DE
0x18005f4c9  call    cs:__imp__wtoi
0x18005f4cf  mov     [rsp+328h+var_200], eax
0x18005f4d6  mov     [rsp+328h+var_1FC], 1
0x18005f4de  mov     rax, [rsi]
0x18005f4e1  lea     r9, [rsp+328h+String]
0x18005f4e6  lea     r8, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x18005f4ed  mov     edx, r14d
0x18005f4f0  mov     rcx, rsi
0x18005f4f3  mov     rax, [rax+18h]
0x18005f4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f4fc  test    eax, eax
0x18005f4fe  jnz     short loc_18005F51F
0x18005f500  mov     rcx, [rsp+328h+String]; String
0x18005f505  test    rcx, rcx
0x18005f508  jz      short loc_18005F51F
0x18005f50a  call    cs:__imp__wtoi
0x18005f510  mov     [rsp+328h+var_1F8], eax
0x18005f517  mov     [rsp+328h+var_1F4], 1
0x18005f51f  mov     rax, [rsi]
0x18005f522  lea     r9, [rsp+328h+String]
0x18005f527  lea     r8, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x18005f52e  mov     edx, r14d
0x18005f531  mov     rcx, rsi
0x18005f534  mov     rax, [rax+18h]
0x18005f538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f53d  test    eax, eax
0x18005f53f  jnz     short loc_18005F560
0x18005f541  mov     rcx, [rsp+328h+String]; String
0x18005f546  test    rcx, rcx
0x18005f549  jz      short loc_18005F560
0x18005f54b  call    cs:__imp__wtoi
0x18005f551  mov     [rsp+328h+var_1F0], eax
0x18005f558  mov     [rsp+328h+var_1EC], 1
0x18005f560  mov     rax, [rsi]
0x18005f563  lea     r9, [rsp+328h+String]
0x18005f568  lea     r8, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x18005f56f  mov     edx, r14d
0x18005f572  mov     rcx, rsi
0x18005f575  mov     rax, [rax+18h]
0x18005f579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f57e  test    eax, eax
0x18005f580  jnz     short loc_18005F5A1
0x18005f582  mov     rcx, [rsp+328h+String]; String
0x18005f587  test    rcx, rcx
0x18005f58a  jz      short loc_18005F5A1
0x18005f58c  call    cs:__imp__wtoi
0x18005f592  mov     [rsp+328h+var_1E8], eax
0x18005f599  mov     [rsp+328h+var_1E4], 1
0x18005f5a1  mov     rax, [rsi]
0x18005f5a4  lea     r9, [rsp+328h+String]
0x18005f5a9  lea     r8, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x18005f5b0  mov     edx, r14d
0x18005f5b3  mov     rcx, rsi
0x18005f5b6  mov     rax, [rax+18h]
0x18005f5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f5bf  test    eax, eax
0x18005f5c1  jnz     short loc_18005F5E2
0x18005f5c3  mov     rcx, [rsp+328h+String]; String
0x18005f5c8  test    rcx, rcx
0x18005f5cb  jz      short loc_18005F5E2
0x18005f5cd  call    cs:__imp__wtoi
0x18005f5d3  mov     [rsp+328h+var_1E0], eax
0x18005f5da  mov     [rsp+328h+var_1DC], 1
0x18005f5e2  mov     rax, [rsi]
0x18005f5e5  lea     r9, [rsp+328h+String]
0x18005f5ea  lea     r8, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x18005f5f1  mov     edx, r14d
0x18005f5f4  mov     rcx, rsi
0x18005f5f7  mov     rax, [rax+18h]
0x18005f5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f600  test    eax, eax
  ... truncated ...
```
