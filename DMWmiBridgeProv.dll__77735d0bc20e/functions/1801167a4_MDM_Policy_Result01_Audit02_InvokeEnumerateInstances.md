# MDM_Policy_Result01_Audit02_InvokeEnumerateInstances

- ea: `0x1801167a4`
- end: `0x180117a87`
- name: `MDM_Policy_Result01_Audit02_InvokeEnumerateInstances`
- size: `4835`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180115260`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801167a4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180116ab6`
- `msvcrt!_wtoi` at `0x180116af7`
- `msvcrt!_wtoi` at `0x180116b38`
- `msvcrt!_wtoi` at `0x180116b79`
- `msvcrt!_wtoi` at `0x180116bba`
- `msvcrt!_wtoi` at `0x180116bfb`
- `msvcrt!_wtoi` at `0x180116c3c`
- `msvcrt!_wtoi` at `0x180116c7d`
- `msvcrt!_wtoi` at `0x180116cbe`
- `msvcrt!_wtoi` at `0x180116cff`
- `msvcrt!_wtoi` at `0x180116d40`
- `msvcrt!_wtoi` at `0x180116d81`
- `msvcrt!_wtoi` at `0x180116dc2`
- `msvcrt!_wtoi` at `0x180116e03`
- `msvcrt!_wtoi` at `0x180116e44`
- `msvcrt!_wtoi` at `0x180116e85`
- `msvcrt!_wtoi` at `0x180116ec6`
- `msvcrt!_wtoi` at `0x180116f07`
- `msvcrt!_wtoi` at `0x180116f48`
- `msvcrt!_wtoi` at `0x180116f89`
- `msvcrt!_wtoi` at `0x180116fca`
- `msvcrt!_wtoi` at `0x18011700b`
- `msvcrt!_wtoi` at `0x18011704c`
- `msvcrt!_wtoi` at `0x18011708d`
- `msvcrt!_wtoi` at `0x1801170ce`
- `msvcrt!_wtoi` at `0x18011710f`
- `msvcrt!_wtoi` at `0x180117150`
- `msvcrt!_wtoi` at `0x180117191`
- `msvcrt!_wtoi` at `0x1801171d2`
- `msvcrt!_wtoi` at `0x180117213`
- `msvcrt!_wtoi` at `0x180117254`
- `msvcrt!_wtoi` at `0x180117295`
- `msvcrt!_wtoi` at `0x1801172d6`
- `msvcrt!_wtoi` at `0x180117317`
- `msvcrt!_wtoi` at `0x180117358`
- `msvcrt!_wtoi` at `0x180117399`
- `msvcrt!_wtoi` at `0x1801173da`
- `msvcrt!_wtoi` at `0x18011741b`
- `msvcrt!_wtoi` at `0x18011745c`
- `msvcrt!_wtoi` at `0x18011749d`
- `msvcrt!_wtoi` at `0x1801174de`
- `msvcrt!_wtoi` at `0x18011751f`
- `msvcrt!_wtoi` at `0x180117560`
- `msvcrt!_wtoi` at `0x1801175a1`
- `msvcrt!_wtoi` at `0x1801175e2`
- `msvcrt!_wtoi` at `0x180117623`
- `msvcrt!_wtoi` at `0x180117664`
- `msvcrt!_wtoi` at `0x1801176a5`
- `msvcrt!_wtoi` at `0x1801176e6`
- `msvcrt!_wtoi` at `0x180117727`
- `msvcrt!_wtoi` at `0x180117768`
- `msvcrt!_wtoi` at `0x1801177a9`
- `msvcrt!_wtoi` at `0x1801177ea`
- `msvcrt!_wtoi` at `0x18011782b`
- `msvcrt!_wtoi` at `0x18011786c`
- `msvcrt!_wtoi` at `0x1801178ad`
- `msvcrt!_wtoi` at `0x1801178ee`
- `msvcrt!_wtoi` at `0x18011792f`
- `msvcrt!_wtoi` at `0x180117970`
- `msvcrt!_wtoi` at `0x180116ab6`
- `msvcrt!_wtoi` at `0x180116af7`
- `msvcrt!_wtoi` at `0x180116b38`
- `msvcrt!_wtoi` at `0x180116b79`
- `msvcrt!_wtoi` at `0x180116bba`
- `msvcrt!_wtoi` at `0x180116bfb`
- `msvcrt!_wtoi` at `0x180116c3c`
- `msvcrt!_wtoi` at `0x180116c7d`
- `msvcrt!_wtoi` at `0x180116cbe`
- `msvcrt!_wtoi` at `0x180116cff`
- `msvcrt!_wtoi` at `0x180116d40`
- `msvcrt!_wtoi` at `0x180116d81`
- `msvcrt!_wtoi` at `0x180116dc2`
- `msvcrt!_wtoi` at `0x180116e03`
- `msvcrt!_wtoi` at `0x180116e44`
- `msvcrt!_wtoi` at `0x180116e85`
- `msvcrt!_wtoi` at `0x180116ec6`
- `msvcrt!_wtoi` at `0x180116f07`
- `msvcrt!_wtoi` at `0x180116f48`
- `msvcrt!_wtoi` at `0x180116f89`
- `msvcrt!_wtoi` at `0x180116fca`
- `msvcrt!_wtoi` at `0x18011700b`
- `msvcrt!_wtoi` at `0x18011704c`
- `msvcrt!_wtoi` at `0x18011708d`
- `msvcrt!_wtoi` at `0x1801170ce`
- `msvcrt!_wtoi` at `0x18011710f`
- `msvcrt!_wtoi` at `0x180117150`
- `msvcrt!_wtoi` at `0x180117191`
- `msvcrt!_wtoi` at `0x1801171d2`
- `msvcrt!_wtoi` at `0x180117213`
- `msvcrt!_wtoi` at `0x180117254`
- `msvcrt!_wtoi` at `0x180117295`
- `msvcrt!_wtoi` at `0x1801172d6`
- `msvcrt!_wtoi` at `0x180117317`
- `msvcrt!_wtoi` at `0x180117358`
- `msvcrt!_wtoi` at `0x180117399`
- `msvcrt!_wtoi` at `0x1801173da`
- `msvcrt!_wtoi` at `0x18011741b`
- `msvcrt!_wtoi` at `0x18011745c`
- `msvcrt!_wtoi` at `0x18011749d`
- `msvcrt!_wtoi` at `0x1801174de`
- `msvcrt!_wtoi` at `0x18011751f`
- `msvcrt!_wtoi` at `0x180117560`
- `msvcrt!_wtoi` at `0x1801175a1`
- `msvcrt!_wtoi` at `0x1801175e2`
- `msvcrt!_wtoi` at `0x180117623`
- `msvcrt!_wtoi` at `0x180117664`
- `msvcrt!_wtoi` at `0x1801176a5`
- `msvcrt!_wtoi` at `0x1801176e6`
- `msvcrt!_wtoi` at `0x180117727`
- `msvcrt!_wtoi` at `0x180117768`
- `msvcrt!_wtoi` at `0x1801177a9`
- `msvcrt!_wtoi` at `0x1801177ea`
- `msvcrt!_wtoi` at `0x18011782b`
- `msvcrt!_wtoi` at `0x18011786c`
- `msvcrt!_wtoi` at `0x1801178ad`
- `msvcrt!_wtoi` at `0x1801178ee`
- `msvcrt!_wtoi` at `0x18011792f`
- `msvcrt!_wtoi` at `0x180117970`

## string_xrefs

- `0x180116ad3`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x180116b14`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x180116ea2`: `AccountManagement_AuditComputerAccountManagement`
- `0x180116f65`: `AccountManagement_AuditSecurityGroupManagement`
- `0x18011712c`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x18011716d`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x1801171ae`: `DSAccess_AuditDirectoryServiceAccess`
- `0x1801171ef`: `DSAccess_AuditDirectoryServiceChanges`
- `0x180117230`: `DSAccess_AuditDirectoryServiceReplication`
- `0x180117271`: `ObjectAccess_AuditApplicationGenerated`
- `0x1801172b2`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x1801172f3`: `ObjectAccess_AuditCertificationServices`
- `0x180117334`: `ObjectAccess_AuditDetailedFileShare`
- `0x180117375`: `ObjectAccess_AuditFileShare`
- `0x1801173b6`: `ObjectAccess_AuditFileSystem`
- `0x1801173f7`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x180117438`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x180117479`: `ObjectAccess_AuditHandleManipulation`
- `0x1801174ba`: `ObjectAccess_AuditKernelObject`
- `0x1801174fb`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x18011753c`: `ObjectAccess_AuditRegistry`
- `0x18011757d`: `ObjectAccess_AuditRemovableStorage`
- `0x1801175be`: `ObjectAccess_AuditSAM`
- `0x180117785`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x1801177c6`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x180117807`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x1801178ca`: `System_AuditSecurityStateChange`
- `0x18011790b`: `System_AuditSecuritySystemExtension`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Audit02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r15d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-2E8h] BYREF
  char v11; // [rsp+48h] [rbp-2E0h]
  WmiRequestHandlerAdd *v12; // [rsp+50h] [rbp-2D8h] BYREF
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
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_Audit02_NodeList,
         0x3Du,
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
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Audit02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_215;
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
                    L"Audit",
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
                      L"AccountLogon_AuditCredentialValidation",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogon_AuditKerberosAuthenticationService",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogon_AuditKerberosServiceTicketOperations",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogon_AuditOtherAccountLogonEvents",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditAccountLockout",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditGroupMembership",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditIPsecExtendedMode",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditIPsecMainMode",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditIPsecQuickMode",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditLogoff",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditLogon",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditNetworkPolicyServer",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditSpecialLogon",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountLogonLogoff_AuditUserDeviceClaims",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditApplicationGroupManagement",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditComputerAccountManagement",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditDistributionGroupManagement",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditOtherAccountManagementEvents",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditSecurityGroupManagement",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccountManagement_AuditUserAccountManagement",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditDPAPIActivity",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditPNPActivity",
                      &String)
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditProcessCreation",
                      &String)
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditProcessTermination",
                      &String)
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditRPCEvents",
                      &String)
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DetailedTracking_AuditTokenRightAdjusted",
                      &String)
                && String )
              {
                v72 = _wtoi(String);
                v73 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DSAccess_AuditDetailedDirectoryServiceReplication",
                      &String)
                && String )
              {
                v74 = _wtoi(String);
                v75 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DSAccess_AuditDirectoryServiceAccess",
                      &String)
                && String )
              {
                v76 = _wtoi(String);
                v77 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DSAccess_AuditDirectoryServiceChanges",
                      &String)
                && String )
              {
                v78 = _wtoi(String);
                v79 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DSAccess_AuditDirectoryServiceReplication",
                      &String)
                && String )
              {
                v80 = _wtoi(String);
                v81 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditApplicationGenerated",
                      &String)
                && String )
              {
                v82 = _wtoi(String);
                v83 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditCentralAccessPolicyStaging",
                      &String)
                && String )
              {
                v84 = _wtoi(String);
                v85 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditCertificationServices",
                      &String)
                && String )
              {
                v86 = _wtoi(String);
                v87 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditDetailedFileShare",
                      &String)
                && String )
              {
                v88 = _wtoi(String);
                v89 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditFileShare",
                      &String)
                && String )
              {
                v90 = _wtoi(String);
                v91 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditFileSystem",
                      &String)
                && String )
              {
                v92 = _wtoi(String);
                v93 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditFilteringPlatformConnection",
                      &String)
                && String )
              {
                v94 = _wtoi(String);
                v95 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                      &String)
                && String )
              {
                v96 = _wtoi(String);
                v97 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditHandleManipulation",
                      &String)
                && String )
              {
                v98 = _wtoi(String);
                v99 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditKernelObject",
                      &String)
                && String )
              {
                v100 = _wtoi(String);
                v101 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditOtherObjectAccessEvents",
                      &String)
                && String )
              {
                v102 = _wtoi(String);
                v103 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditRegistry",
                      &String)
                && String )
              {
                v104 = _wtoi(String);
                v105 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditRemovableStorage",
                      &String)
                && String )
              {
                v106 = _wtoi(String);
                v107 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ObjectAccess_AuditSAM",
                      &String)
                && String )
              {
                v108 = _wtoi(String);
                v109 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditAuthenticationPolicyChange",
                      &String)
                && String )
              {
                v110 = _wtoi(String);
                v111 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditAuthorizationPolicyChange",
                      &String)
                && String )
              {
                v112 = _wtoi(String);
                v113 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditFilteringPlatformPolicyChange",
                      &String)
                && String )
              {
                v114 = _wtoi(String);
                v115 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                      &String)
                && String )
              {
                v116 = _wtoi(String);
                v117 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditOtherPolicyChangeEvents",
                      &String)
                && String )
              {
                v118 = _wtoi(String);
                v119 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PolicyChange_AuditPolicyChange",
                      &String)
                && String )
              {
                v120 = _wtoi(String);
                v121 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                      &String)
                && String )
              {
                v122 = _wtoi(String);
                v123 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                      &String)
                && String )
              {
                v124 = _wtoi(String);
                v125 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PrivilegeUse_AuditSensitivePrivilegeUse",
                      &String)
                && String )
              {
                v126 = _wtoi(String);
                v127 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"System_AuditIPsecDriver",
                      &String)
                && String )
              {
                v128 = _wtoi(String);
                v129 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"System_AuditOtherSystemEvents",
                      &String)
                && String )
              {
                v130 = _wtoi(String);
                v131 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"System_AuditSecurityStateChange",
                      &String)
                && String )
              {
                v132 = _wtoi(String);
                v133 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"System_AuditSecuritySystemExtension",
                      &String)
                && String )
              {
                v134 = _wtoi(String);
                v135 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
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
  return v6;
}

```

## disassembly

```asm
0x1801167a4  mov     [rsp+arg_8], rbx
0x1801167a9  mov     [rsp+arg_10], rsi
0x1801167ae  push    rdi
0x1801167af  push    r12
0x1801167b1  push    r13
0x1801167b3  push    r14
0x1801167b5  push    r15
0x1801167b7  sub     rsp, 300h
0x1801167be  mov     rax, cs:__security_cookie
0x1801167c5  xor     rax, rsp
0x1801167c8  mov     [rsp+328h+var_38], rax
0x1801167d0  mov     r13b, dl
0x1801167d3  mov     r12, rcx
0x1801167d6  xor     edx, edx; Val
0x1801167d8  mov     r8d, 238h; Size
0x1801167de  lea     rcx, [rsp+328h+instance]; void *
0x1801167e6  call    memset_0
0x1801167eb  xor     edi, edi
0x1801167ed  mov     [rsp+328h+var_2E0], dil
0x1801167f2  mov     [rsp+328h+String], rdi
0x1801167f7  mov     [rsp+328h+var_2A0], edi
0x1801167fe  mov     [rsp+328h+var_29C], dil
0x180116806  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18011680d  mov     [rsp+328h+var_2D0], rax
0x180116812  lea     rax, [rsp+328h+var_2A0]
0x18011681a  mov     [rsp+328h+var_2C8], rax
0x18011681f  lea     rax, aMdmPolicyResul_95; "MDM_Policy_Result01_Audit02"
0x180116826  mov     [rsp+328h+var_2C0], rax
0x18011682b  lea     rcx, [rsp+328h+var_2A0]
0x180116833  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180116838  mov     eax, cs:dword_180380B68
0x18011683e  cmp     eax, 5
0x180116841  jbe     short loc_1801168B3
0x180116843  mov     rdx, 200000000000h
0x18011684d  lea     rcx, dword_180380B68
0x180116854  call    _tlgKeywordOn
0x180116859  test    al, al
0x18011685b  jz      short loc_1801168B3
0x18011685d  cmp     [rsp+328h+var_29C], dil
0x180116865  jz      short loc_180116895
0x180116867  cmp     [rsp+328h+var_288], edi
0x18011686e  jnz     short loc_18011688B
0x180116870  cmp     [rsp+328h+var_284], edi
0x180116877  jnz     short loc_18011688B
0x180116879  cmp     [rsp+328h+var_280], edi
0x180116880  jnz     short loc_18011688B
0x180116882  cmp     [rsp+328h+var_27C], edi
0x180116889  jz      short loc_180116895
0x18011688b  lea     r9, [rsp+328h+var_288]
0x180116893  jmp     short loc_180116898
0x180116895  mov     r9, rdi
0x180116898  lea     r8, [rsp+328h+var_298]
0x1801168a0  lea     rdx, qword_180346AD0
0x1801168a7  lea     rcx, dword_180380B68
0x1801168ae  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801168b3  lea     rcx, [rsp+328h+var_2D0]; this
0x1801168b8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1801168bd  nop
0x1801168be  mov     [rsp+328h+var_2D8], rdi
0x1801168c3  lea     rax, [rsp+328h+var_2D8]
0x1801168c8  mov     [rsp+328h+var_2F8], rax
0x1801168cd  mov     [rsp+328h+var_300], 2
0x1801168d5  mov     [rsp+328h+var_308], 3Dh ; '='
0x1801168dd  lea     r9, ?MDM_Policy_Result01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Audit02_NodeList
0x1801168e4  xor     r8d, r8d
0x1801168e7  xor     edx, edx
0x1801168e9  mov     rcx, r12
0x1801168ec  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801168f1  mov     r15d, eax
0x1801168f4  test    eax, eax
0x1801168f6  jz      short loc_1801168FD
0x1801168f8  jmp     loc_1801179E7
0x1801168fd  lea     rbx, [rsp+328h+var_2D8]
0x180116902  mov     [rsp+328h+var_2B0], rbx
0x180116907  mov     r14d, 1
0x18011690d  mov     [rsp+328h+var_2A8], r14b
0x180116915  mov     rsi, [rsp+328h+var_2D8]
0x18011691a  test    rsi, rsi
0x18011691d  jnz     short loc_180116927
0x18011691f  mov     r15d, r14d
0x180116922  jmp     loc_1801179E7
0x180116927  mov     rax, [rsi]
0x18011692a  mov     rcx, rsi
0x18011692d  mov     rax, [rax+10h]
0x180116931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116936  mov     r15d, eax
0x180116939  test    eax, eax
0x18011693b  jz      short loc_18011695B
0x18011693d  mov     rcx, [rsp+328h+var_2D8]
0x180116942  test    rcx, rcx
0x180116945  jz      short loc_180116956
0x180116947  mov     rax, [rcx]
0x18011694a  mov     edx, r14d
0x18011694d  mov     rax, [rax]
0x180116950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116955  nop
0x180116956  jmp     loc_1801179E7
0x18011695b  mov     rax, [rsi]
0x18011695e  mov     rcx, rsi
0x180116961  mov     rax, [rax+8]
0x180116965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011696a  mov     r15d, eax
0x18011696d  test    eax, eax
0x18011696f  jz      short loc_18011698F
0x180116971  mov     rcx, [rsp+328h+var_2D8]
0x180116976  test    rcx, rcx
0x180116979  jz      short loc_18011698A
0x18011697b  mov     rax, [rcx]
0x18011697e  mov     edx, r14d
0x180116981  mov     rax, [rax]
0x180116984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116989  nop
0x18011698a  jmp     loc_1801179E7
0x18011698f  mov     r14d, edi
0x180116992  mov     rax, [rsi+108h]
0x180116999  sub     rax, [rsi+100h]
0x1801169a0  sar     rax, 4
0x1801169a4  cmp     r14d, eax
0x1801169a7  jnb     loc_1801179AF
0x1801169ad  lea     r8, [rsp+328h+instance]; instance
0x1801169b5  lea     rdx, MDM_Policy_Result01_Audit02_rtti; classDecl
0x1801169bc  mov     rcx, r12; context
0x1801169bf  call    MI_Context_ConstructInstance
0x1801169c4  mov     r15d, eax
0x1801169c7  test    eax, eax
0x1801169c9  jz      short loc_1801169EB
0x1801169cb  mov     rcx, [rbx]
0x1801169ce  test    rcx, rcx
0x1801169d1  jz      short loc_1801169E6
0x1801169d3  mov     rax, [rcx]
0x1801169d6  mov     edx, 1
0x1801169db  mov     rax, [rax]
0x1801169de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801169e3  mov     [rbx], rdi
0x1801169e6  jmp     loc_1801179E7
0x1801169eb  mov     [rsp+328h+var_2E0], 1
0x1801169f0  mov     rax, [rsi]
0x1801169f3  lea     r9, [rsp+328h+String]
0x1801169f8  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x1801169ff  mov     edx, r14d
0x180116a02  mov     rcx, rsi
0x180116a05  mov     rax, [rax+18h]
0x180116a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116a0e  test    eax, eax
0x180116a10  jnz     short loc_180116A29
0x180116a12  mov     rdx, [rsp+328h+String]
0x180116a17  test    rdx, rdx
0x180116a1a  jz      short loc_180116A29
0x180116a1c  lea     rcx, [rsp+328h+instance]
0x180116a24  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180116a29  mov     rax, [rsi]
0x180116a2c  lea     r9, [rsp+328h+String]
0x180116a31  lea     r8, aAudit; "Audit"
0x180116a38  mov     edx, r14d
0x180116a3b  mov     rcx, rsi
0x180116a3e  mov     rax, [rax+18h]
0x180116a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116a47  test    eax, eax
0x180116a49  jnz     short loc_180116A62
0x180116a4b  mov     rdx, [rsp+328h+String]
0x180116a50  test    rdx, rdx
0x180116a53  jz      short loc_180116A62
0x180116a55  lea     rcx, [rsp+328h+instance]
0x180116a5d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180116a62  cmp     r13b, 1
0x180116a66  jnz     short loc_180116A8A
0x180116a68  lea     rdx, [rsp+328h+instance]
0x180116a70  mov     rcx, r12; self
0x180116a73  call    MI_Instance_Destruct
0x180116a78  lea     rcx, [rsp+328h+instance]; self
0x180116a80  call    MI_Instance_Destruct
0x180116a85  jmp     loc_1801179A2
0x180116a8a  mov     rax, [rsi]
0x180116a8d  lea     r9, [rsp+328h+String]
0x180116a92  lea     r8, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x180116a99  mov     edx, r14d
0x180116a9c  mov     rcx, rsi
0x180116a9f  mov     rax, [rax+18h]
0x180116aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116aa8  test    eax, eax
0x180116aaa  jnz     short loc_180116ACB
0x180116aac  mov     rcx, [rsp+328h+String]; String
0x180116ab1  test    rcx, rcx
0x180116ab4  jz      short loc_180116ACB
0x180116ab6  call    cs:__imp__wtoi
0x180116abc  mov     [rsp+328h+var_218], eax
0x180116ac3  mov     [rsp+328h+var_214], 1
0x180116acb  mov     rax, [rsi]
0x180116ace  lea     r9, [rsp+328h+String]
0x180116ad3  lea     r8, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x180116ada  mov     edx, r14d
0x180116add  mov     rcx, rsi
0x180116ae0  mov     rax, [rax+18h]
0x180116ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116ae9  test    eax, eax
0x180116aeb  jnz     short loc_180116B0C
0x180116aed  mov     rcx, [rsp+328h+String]; String
0x180116af2  test    rcx, rcx
0x180116af5  jz      short loc_180116B0C
0x180116af7  call    cs:__imp__wtoi
0x180116afd  mov     [rsp+328h+var_210], eax
0x180116b04  mov     [rsp+328h+var_20C], 1
0x180116b0c  mov     rax, [rsi]
0x180116b0f  lea     r9, [rsp+328h+String]
0x180116b14  lea     r8, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x180116b1b  mov     edx, r14d
0x180116b1e  mov     rcx, rsi
0x180116b21  mov     rax, [rax+18h]
0x180116b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116b2a  test    eax, eax
0x180116b2c  jnz     short loc_180116B4D
0x180116b2e  mov     rcx, [rsp+328h+String]; String
0x180116b33  test    rcx, rcx
0x180116b36  jz      short loc_180116B4D
0x180116b38  call    cs:__imp__wtoi
0x180116b3e  mov     [rsp+328h+var_208], eax
0x180116b45  mov     [rsp+328h+var_204], 1
0x180116b4d  mov     rax, [rsi]
0x180116b50  lea     r9, [rsp+328h+String]
0x180116b55  lea     r8, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x180116b5c  mov     edx, r14d
0x180116b5f  mov     rcx, rsi
0x180116b62  mov     rax, [rax+18h]
0x180116b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116b6b  test    eax, eax
0x180116b6d  jnz     short loc_180116B8E
0x180116b6f  mov     rcx, [rsp+328h+String]; String
0x180116b74  test    rcx, rcx
0x180116b77  jz      short loc_180116B8E
0x180116b79  call    cs:__imp__wtoi
0x180116b7f  mov     [rsp+328h+var_200], eax
0x180116b86  mov     [rsp+328h+var_1FC], 1
0x180116b8e  mov     rax, [rsi]
0x180116b91  lea     r9, [rsp+328h+String]
0x180116b96  lea     r8, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x180116b9d  mov     edx, r14d
0x180116ba0  mov     rcx, rsi
0x180116ba3  mov     rax, [rax+18h]
0x180116ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116bac  test    eax, eax
0x180116bae  jnz     short loc_180116BCF
0x180116bb0  mov     rcx, [rsp+328h+String]; String
0x180116bb5  test    rcx, rcx
0x180116bb8  jz      short loc_180116BCF
0x180116bba  call    cs:__imp__wtoi
0x180116bc0  mov     [rsp+328h+var_1F8], eax
0x180116bc7  mov     [rsp+328h+var_1F4], 1
0x180116bcf  mov     rax, [rsi]
0x180116bd2  lea     r9, [rsp+328h+String]
0x180116bd7  lea     r8, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x180116bde  mov     edx, r14d
0x180116be1  mov     rcx, rsi
0x180116be4  mov     rax, [rax+18h]
0x180116be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116bed  test    eax, eax
0x180116bef  jnz     short loc_180116C10
0x180116bf1  mov     rcx, [rsp+328h+String]; String
0x180116bf6  test    rcx, rcx
0x180116bf9  jz      short loc_180116C10
0x180116bfb  call    cs:__imp__wtoi
0x180116c01  mov     [rsp+328h+var_1F0], eax
0x180116c08  mov     [rsp+328h+var_1EC], 1
0x180116c10  mov     rax, [rsi]
0x180116c13  lea     r9, [rsp+328h+String]
0x180116c18  lea     r8, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x180116c1f  mov     edx, r14d
0x180116c22  mov     rcx, rsi
0x180116c25  mov     rax, [rax+18h]
0x180116c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116c2e  test    eax, eax
0x180116c30  jnz     short loc_180116C51
0x180116c32  mov     rcx, [rsp+328h+String]; String
0x180116c37  test    rcx, rcx
0x180116c3a  jz      short loc_180116C51
0x180116c3c  call    cs:__imp__wtoi
0x180116c42  mov     [rsp+328h+var_1E8], eax
0x180116c49  mov     [rsp+328h+var_1E4], 1
0x180116c51  mov     rax, [rsi]
0x180116c54  lea     r9, [rsp+328h+String]
0x180116c59  lea     r8, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x180116c60  mov     edx, r14d
0x180116c63  mov     rcx, rsi
0x180116c66  mov     rax, [rax+18h]
0x180116c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116c6f  test    eax, eax
0x180116c71  jnz     short loc_180116C92
0x180116c73  mov     rcx, [rsp+328h+String]; String
0x180116c78  test    rcx, rcx
0x180116c7b  jz      short loc_180116C92
0x180116c7d  call    cs:__imp__wtoi
0x180116c83  mov     [rsp+328h+var_1E0], eax
0x180116c8a  mov     [rsp+328h+var_1DC], 1
0x180116c92  mov     rax, [rsi]
0x180116c95  lea     r9, [rsp+328h+String]
0x180116c9a  lea     r8, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x180116ca1  mov     edx, r14d
0x180116ca4  mov     rcx, rsi
0x180116ca7  mov     rax, [rax+18h]
0x180116cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116cb0  test    eax, eax
  ... truncated ...
```
