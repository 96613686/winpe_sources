# MDM_Policy_Config01_Audit02_InvokeGetInstance

- ea: `0x1800603e0`
- end: `0x1800613f3`
- name: `MDM_Policy_Config01_Audit02_InvokeGetInstance`
- size: `4115`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005dbf0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800603e0`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18006067f`
- `msvcrt!_wtoi` at `0x1800606b6`
- `msvcrt!_wtoi` at `0x1800606ed`
- `msvcrt!_wtoi` at `0x180060724`
- `msvcrt!_wtoi` at `0x18006075b`
- `msvcrt!_wtoi` at `0x180060792`
- `msvcrt!_wtoi` at `0x1800607c9`
- `msvcrt!_wtoi` at `0x180060800`
- `msvcrt!_wtoi` at `0x180060837`
- `msvcrt!_wtoi` at `0x18006086e`
- `msvcrt!_wtoi` at `0x1800608a5`
- `msvcrt!_wtoi` at `0x1800608dc`
- `msvcrt!_wtoi` at `0x180060913`
- `msvcrt!_wtoi` at `0x18006094a`
- `msvcrt!_wtoi` at `0x180060981`
- `msvcrt!_wtoi` at `0x1800609b8`
- `msvcrt!_wtoi` at `0x1800609ef`
- `msvcrt!_wtoi` at `0x180060a26`
- `msvcrt!_wtoi` at `0x180060a5d`
- `msvcrt!_wtoi` at `0x180060a94`
- `msvcrt!_wtoi` at `0x180060acb`
- `msvcrt!_wtoi` at `0x180060b02`
- `msvcrt!_wtoi` at `0x180060b39`
- `msvcrt!_wtoi` at `0x180060b70`
- `msvcrt!_wtoi` at `0x180060ba7`
- `msvcrt!_wtoi` at `0x180060bde`
- `msvcrt!_wtoi` at `0x180060c15`
- `msvcrt!_wtoi` at `0x180060c4c`
- `msvcrt!_wtoi` at `0x180060c83`
- `msvcrt!_wtoi` at `0x180060cba`
- `msvcrt!_wtoi` at `0x180060cf1`
- `msvcrt!_wtoi` at `0x180060d28`
- `msvcrt!_wtoi` at `0x180060d5f`
- `msvcrt!_wtoi` at `0x180060d96`
- `msvcrt!_wtoi` at `0x180060dcd`
- `msvcrt!_wtoi` at `0x180060e04`
- `msvcrt!_wtoi` at `0x180060e3b`
- `msvcrt!_wtoi` at `0x180060e72`
- `msvcrt!_wtoi` at `0x180060ea9`
- `msvcrt!_wtoi` at `0x180060ee0`
- `msvcrt!_wtoi` at `0x180060f17`
- `msvcrt!_wtoi` at `0x180060f4e`
- `msvcrt!_wtoi` at `0x180060f85`
- `msvcrt!_wtoi` at `0x180060fbc`
- `msvcrt!_wtoi` at `0x180060ff3`
- `msvcrt!_wtoi` at `0x18006102a`
- `msvcrt!_wtoi` at `0x180061061`
- `msvcrt!_wtoi` at `0x180061098`
- `msvcrt!_wtoi` at `0x1800610cf`
- `msvcrt!_wtoi` at `0x180061106`
- `msvcrt!_wtoi` at `0x18006113d`
- `msvcrt!_wtoi` at `0x180061174`
- `msvcrt!_wtoi` at `0x1800611ab`
- `msvcrt!_wtoi` at `0x1800611e2`
- `msvcrt!_wtoi` at `0x180061219`
- `msvcrt!_wtoi` at `0x180061250`
- `msvcrt!_wtoi` at `0x180061287`
- `msvcrt!_wtoi` at `0x1800612be`
- `msvcrt!_wtoi` at `0x1800612f5`
- `msvcrt!_wtoi` at `0x18006067f`
- `msvcrt!_wtoi` at `0x1800606b6`
- `msvcrt!_wtoi` at `0x1800606ed`
- `msvcrt!_wtoi` at `0x180060724`
- `msvcrt!_wtoi` at `0x18006075b`
- `msvcrt!_wtoi` at `0x180060792`
- `msvcrt!_wtoi` at `0x1800607c9`
- `msvcrt!_wtoi` at `0x180060800`
- `msvcrt!_wtoi` at `0x180060837`
- `msvcrt!_wtoi` at `0x18006086e`
- `msvcrt!_wtoi` at `0x1800608a5`
- `msvcrt!_wtoi` at `0x1800608dc`
- `msvcrt!_wtoi` at `0x180060913`
- `msvcrt!_wtoi` at `0x18006094a`
- `msvcrt!_wtoi` at `0x180060981`
- `msvcrt!_wtoi` at `0x1800609b8`
- `msvcrt!_wtoi` at `0x1800609ef`
- `msvcrt!_wtoi` at `0x180060a26`
- `msvcrt!_wtoi` at `0x180060a5d`
- `msvcrt!_wtoi` at `0x180060a94`
- `msvcrt!_wtoi` at `0x180060acb`
- `msvcrt!_wtoi` at `0x180060b02`
- `msvcrt!_wtoi` at `0x180060b39`
- `msvcrt!_wtoi` at `0x180060b70`
- `msvcrt!_wtoi` at `0x180060ba7`
- `msvcrt!_wtoi` at `0x180060bde`
- `msvcrt!_wtoi` at `0x180060c15`
- `msvcrt!_wtoi` at `0x180060c4c`
- `msvcrt!_wtoi` at `0x180060c83`
- `msvcrt!_wtoi` at `0x180060cba`
- `msvcrt!_wtoi` at `0x180060cf1`
- `msvcrt!_wtoi` at `0x180060d28`
- `msvcrt!_wtoi` at `0x180060d5f`
- `msvcrt!_wtoi` at `0x180060d96`
- `msvcrt!_wtoi` at `0x180060dcd`
- `msvcrt!_wtoi` at `0x180060e04`
- `msvcrt!_wtoi` at `0x180060e3b`
- `msvcrt!_wtoi` at `0x180060e72`
- `msvcrt!_wtoi` at `0x180060ea9`
- `msvcrt!_wtoi` at `0x180060ee0`
- `msvcrt!_wtoi` at `0x180060f17`
- `msvcrt!_wtoi` at `0x180060f4e`
- `msvcrt!_wtoi` at `0x180060f85`
- `msvcrt!_wtoi` at `0x180060fbc`
- `msvcrt!_wtoi` at `0x180060ff3`
- `msvcrt!_wtoi` at `0x18006102a`
- `msvcrt!_wtoi` at `0x180061061`
- `msvcrt!_wtoi` at `0x180061098`
- `msvcrt!_wtoi` at `0x1800610cf`
- `msvcrt!_wtoi` at `0x180061106`
- `msvcrt!_wtoi` at `0x18006113d`
- `msvcrt!_wtoi` at `0x180061174`
- `msvcrt!_wtoi` at `0x1800611ab`
- `msvcrt!_wtoi` at `0x1800611e2`
- `msvcrt!_wtoi` at `0x180061219`
- `msvcrt!_wtoi` at `0x180061250`
- `msvcrt!_wtoi` at `0x180061287`
- `msvcrt!_wtoi` at `0x1800612be`
- `msvcrt!_wtoi` at `0x1800612f5`

## string_xrefs

- `0x180060699`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x1800606d0`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x1800609d2`: `AccountManagement_AuditComputerAccountManagement`
- `0x180060a77`: `AccountManagement_AuditSecurityGroupManagement`
- `0x180060bf8`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x180060c2f`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x180060c66`: `DSAccess_AuditDirectoryServiceAccess`
- `0x180060c9d`: `DSAccess_AuditDirectoryServiceChanges`
- `0x180060cd4`: `DSAccess_AuditDirectoryServiceReplication`
- `0x180060d0b`: `ObjectAccess_AuditApplicationGenerated`
- `0x180060d42`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x180060d79`: `ObjectAccess_AuditCertificationServices`
- `0x180060db0`: `ObjectAccess_AuditDetailedFileShare`
- `0x180060de7`: `ObjectAccess_AuditFileShare`
- `0x180060e1e`: `ObjectAccess_AuditFileSystem`
- `0x180060e55`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x180060e8c`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x180060ec3`: `ObjectAccess_AuditHandleManipulation`
- `0x180060efa`: `ObjectAccess_AuditKernelObject`
- `0x180060f31`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x180060f68`: `ObjectAccess_AuditRegistry`
- `0x180060f9f`: `ObjectAccess_AuditRemovableStorage`
- `0x180060fd6`: `ObjectAccess_AuditSAM`
- `0x180061157`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x18006118e`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x1800611c5`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x18006126a`: `System_AuditSecurityStateChange`
- `0x1800612a1`: `System_AuditSecuritySystemExtension`
- `0x18006044f`: `MDM_Policy_Config01_Audit02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Audit02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-2E8h] BYREF
  char v9; // [rsp+48h] [rbp-2E0h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-2D8h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-2D0h] BYREF
  char v12; // [rsp+80h] [rbp-2A8h]
  int v13; // [rsp+88h] [rbp-2A0h] BYREF
  char v14; // [rsp+8Ch] [rbp-29Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-298h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-288h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-278h] BYREF
  int v18; // [rsp+110h] [rbp-218h]
  char v19; // [rsp+114h] [rbp-214h]
  int v20; // [rsp+118h] [rbp-210h]
  char v21; // [rsp+11Ch] [rbp-20Ch]
  int v22; // [rsp+120h] [rbp-208h]
  char v23; // [rsp+124h] [rbp-204h]
  int v24; // [rsp+128h] [rbp-200h]
  char v25; // [rsp+12Ch] [rbp-1FCh]
  int v26; // [rsp+130h] [rbp-1F8h]
  char v27; // [rsp+134h] [rbp-1F4h]
  int v28; // [rsp+138h] [rbp-1F0h]
  char v29; // [rsp+13Ch] [rbp-1ECh]
  int v30; // [rsp+140h] [rbp-1E8h]
  char v31; // [rsp+144h] [rbp-1E4h]
  int v32; // [rsp+148h] [rbp-1E0h]
  char v33; // [rsp+14Ch] [rbp-1DCh]
  int v34; // [rsp+150h] [rbp-1D8h]
  char v35; // [rsp+154h] [rbp-1D4h]
  int v36; // [rsp+158h] [rbp-1D0h]
  char v37; // [rsp+15Ch] [rbp-1CCh]
  int v38; // [rsp+160h] [rbp-1C8h]
  char v39; // [rsp+164h] [rbp-1C4h]
  int v40; // [rsp+168h] [rbp-1C0h]
  char v41; // [rsp+16Ch] [rbp-1BCh]
  int v42; // [rsp+170h] [rbp-1B8h]
  char v43; // [rsp+174h] [rbp-1B4h]
  int v44; // [rsp+178h] [rbp-1B0h]
  char v45; // [rsp+17Ch] [rbp-1ACh]
  int v46; // [rsp+180h] [rbp-1A8h]
  char v47; // [rsp+184h] [rbp-1A4h]
  int v48; // [rsp+188h] [rbp-1A0h]
  char v49; // [rsp+18Ch] [rbp-19Ch]
  int v50; // [rsp+190h] [rbp-198h]
  char v51; // [rsp+194h] [rbp-194h]
  int v52; // [rsp+198h] [rbp-190h]
  char v53; // [rsp+19Ch] [rbp-18Ch]
  int v54; // [rsp+1A0h] [rbp-188h]
  char v55; // [rsp+1A4h] [rbp-184h]
  int v56; // [rsp+1A8h] [rbp-180h]
  char v57; // [rsp+1ACh] [rbp-17Ch]
  int v58; // [rsp+1B0h] [rbp-178h]
  char v59; // [rsp+1B4h] [rbp-174h]
  int v60; // [rsp+1B8h] [rbp-170h]
  char v61; // [rsp+1BCh] [rbp-16Ch]
  int v62; // [rsp+1C0h] [rbp-168h]
  char v63; // [rsp+1C4h] [rbp-164h]
  int v64; // [rsp+1C8h] [rbp-160h]
  char v65; // [rsp+1CCh] [rbp-15Ch]
  int v66; // [rsp+1D0h] [rbp-158h]
  char v67; // [rsp+1D4h] [rbp-154h]
  int v68; // [rsp+1D8h] [rbp-150h]
  char v69; // [rsp+1DCh] [rbp-14Ch]
  int v70; // [rsp+1E0h] [rbp-148h]
  char v71; // [rsp+1E4h] [rbp-144h]
  int v72; // [rsp+1E8h] [rbp-140h]
  char v73; // [rsp+1ECh] [rbp-13Ch]
  int v74; // [rsp+1F0h] [rbp-138h]
  char v75; // [rsp+1F4h] [rbp-134h]
  int v76; // [rsp+1F8h] [rbp-130h]
  char v77; // [rsp+1FCh] [rbp-12Ch]
  int v78; // [rsp+200h] [rbp-128h]
  char v79; // [rsp+204h] [rbp-124h]
  int v80; // [rsp+208h] [rbp-120h]
  char v81; // [rsp+20Ch] [rbp-11Ch]
  int v82; // [rsp+210h] [rbp-118h]
  char v83; // [rsp+214h] [rbp-114h]
  int v84; // [rsp+218h] [rbp-110h]
  char v85; // [rsp+21Ch] [rbp-10Ch]
  int v86; // [rsp+220h] [rbp-108h]
  char v87; // [rsp+224h] [rbp-104h]
  int v88; // [rsp+228h] [rbp-100h]
  char v89; // [rsp+22Ch] [rbp-FCh]
  int v90; // [rsp+230h] [rbp-F8h]
  char v91; // [rsp+234h] [rbp-F4h]
  int v92; // [rsp+238h] [rbp-F0h]
  char v93; // [rsp+23Ch] [rbp-ECh]
  int v94; // [rsp+240h] [rbp-E8h]
  char v95; // [rsp+244h] [rbp-E4h]
  int v96; // [rsp+248h] [rbp-E0h]
  char v97; // [rsp+24Ch] [rbp-DCh]
  int v98; // [rsp+250h] [rbp-D8h]
  char v99; // [rsp+254h] [rbp-D4h]
  int v100; // [rsp+258h] [rbp-D0h]
  char v101; // [rsp+25Ch] [rbp-CCh]
  int v102; // [rsp+260h] [rbp-C8h]
  char v103; // [rsp+264h] [rbp-C4h]
  int v104; // [rsp+268h] [rbp-C0h]
  char v105; // [rsp+26Ch] [rbp-BCh]
  int v106; // [rsp+270h] [rbp-B8h]
  char v107; // [rsp+274h] [rbp-B4h]
  int v108; // [rsp+278h] [rbp-B0h]
  char v109; // [rsp+27Ch] [rbp-ACh]
  int v110; // [rsp+280h] [rbp-A8h]
  char v111; // [rsp+284h] [rbp-A4h]
  int v112; // [rsp+288h] [rbp-A0h]
  char v113; // [rsp+28Ch] [rbp-9Ch]
  int v114; // [rsp+290h] [rbp-98h]
  char v115; // [rsp+294h] [rbp-94h]
  int v116; // [rsp+298h] [rbp-90h]
  char v117; // [rsp+29Ch] [rbp-8Ch]
  int v118; // [rsp+2A0h] [rbp-88h]
  char v119; // [rsp+2A4h] [rbp-84h]
  int v120; // [rsp+2A8h] [rbp-80h]
  char v121; // [rsp+2ACh] [rbp-7Ch]
  int v122; // [rsp+2B0h] [rbp-78h]
  char v123; // [rsp+2B4h] [rbp-74h]
  int v124; // [rsp+2B8h] [rbp-70h]
  char v125; // [rsp+2BCh] [rbp-6Ch]
  int v126; // [rsp+2C0h] [rbp-68h]
  char v127; // [rsp+2C4h] [rbp-64h]
  int v128; // [rsp+2C8h] [rbp-60h]
  char v129; // [rsp+2CCh] [rbp-5Ch]
  int v130; // [rsp+2D0h] [rbp-58h]
  char v131; // [rsp+2D4h] [rbp-54h]
  int v132; // [rsp+2D8h] [rbp-50h]
  char v133; // [rsp+2DCh] [rbp-4Ch]
  int v134; // [rsp+2E0h] [rbp-48h]
  char v135; // [rsp+2E4h] [rbp-44h]

  String = 0;
  memset_0(&instance, 0, 0x238u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Config01_Audit02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180356C47,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = 4;
    goto LABEL_206;
  }
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
         (struct WmiNodeInfo *)&MDM_Policy_Config01_Audit02_NodeList,
         0x3Du,
         0,
         &v10);
  if ( !v5 )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = 1;
      goto LABEL_206;
    }
    WmiRequestHandler::SetRequestMIInstance(v10, a2, (struct WmiNodeInfo *)&MDM_Policy_Config01_Audit02_NodeList, 0x3Du);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_206;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_206;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_206;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Audit02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_206;
      goto LABEL_24;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogon_AuditCredentialValidation",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogon_AuditKerberosAuthenticationService",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogon_AuditKerberosServiceTicketOperations",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogon_AuditOtherAccountLogonEvents",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditAccountLockout",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditGroupMembership",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditIPsecExtendedMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditIPsecMainMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditIPsecQuickMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditLogoff",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditLogon",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditNetworkPolicyServer",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditSpecialLogon",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v44 = _wtoi(String);
      v45 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountLogonLogoff_AuditUserDeviceClaims",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v46 = _wtoi(String);
      v47 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountManagement_AuditApplicationGroupManagement",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v48 = _wtoi(String);
      v49 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountManagement_AuditComputerAccountManagement",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v50 = _wtoi(String);
      v51 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountManagement_AuditDistributionGroupManagement",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v52 = _wtoi(String);
      v53 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountManagement_AuditOtherAccountManagementEvents",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v54 = _wtoi(String);
      v55 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountManagement_AuditSecurityGroupManagement",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v56 = _wtoi(String);
      v57 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccountManagement_AuditUserAccountManagement",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v58 = _wtoi(String);
      v59 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DetailedTracking_AuditDPAPIActivity",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v60 = _wtoi(String);
      v61 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DetailedTracking_AuditPNPActivity",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v62 = _wtoi(String);
      v63 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DetailedTracking_AuditProcessCreation",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v64 = _wtoi(String);
      v65 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DetailedTracking_AuditProcessTermination",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v66 = _wtoi(String);
      v67 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DetailedTracking_AuditRPCEvents",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v68 = _wtoi(String);
      v69 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DetailedTracking_AuditTokenRightAdjusted",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v70 = _wtoi(String);
      v71 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DSAccess_AuditDetailedDirectoryServiceReplication",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v72 = _wtoi(String);
      v73 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DSAccess_AuditDirectoryServiceAccess",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v74 = _wtoi(String);
      v75 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DSAccess_AuditDirectoryServiceChanges",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v76 = _wtoi(String);
      v77 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DSAccess_AuditDirectoryServiceReplication",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v78 = _wtoi(String);
      v79 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditApplicationGenerated",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v80 = _wtoi(String);
      v81 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditCentralAccessPolicyStaging",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v82 = _wtoi(String);
      v83 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditCertificationServices",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v84 = _wtoi(String);
      v85 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditDetailedFileShare",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v86 = _wtoi(String);
      v87 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditFileShare",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v88 = _wtoi(String);
      v89 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditFileSystem",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v90 = _wtoi(String);
      v91 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditFilteringPlatformConnection",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v92 = _wtoi(String);
      v93 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v94 = _wtoi(String);
      v95 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditHandleManipulation",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v96 = _wtoi(String);
      v97 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditKernelObject",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v98 = _wtoi(String);
      v99 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditOtherObjectAccessEvents",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v100 = _wtoi(String);
      v101 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditRegistry",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v102 = _wtoi(String);
      v103 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditRemovableStorage",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v104 = _wtoi(String);
      v105 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ObjectAccess_AuditSAM",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v106 = _wtoi(String);
      v107 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PolicyChange_AuditAuthenticationPolicyChange",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v108 = _wtoi(String);
      v109 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PolicyChange_AuditAuthorizationPolicyChange",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v110 = _wtoi(String);
      v111 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PolicyChange_AuditFilteringPlatformPolicyChange",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v112 = _wtoi(String);
      v113 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v114 = _wtoi(String);
      v115 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PolicyChange_AuditOtherPolicyChangeEvents",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v116 = _wtoi(String);
      v117 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PolicyChange_AuditPolicyChange",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v118 = _wtoi(String);
      v119 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v120 = _wtoi(String);
      v121 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v122 = _wtoi(String);
      v123 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PrivilegeUse_AuditSensitivePrivilegeUse",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v124 = _wtoi(String);
      v125 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"System_AuditIPsecDriver",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v126 = _wtoi(String);
      v127 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"System_AuditOtherSystemEvents",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v128 = _wtoi(String);
      v129 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"System_AuditSecurityStateChange",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v130 = _wtoi(String);
      v131 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"System_AuditSecuritySystemExtension",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v132 = _wtoi(String);
      v133 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"System_AuditSystemIntegrity",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v134 = _wtoi(String);
      v135 = 1;
    }
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v10 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_206:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_180332416,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x1800603e0  mov     [rsp+arg_10], rbx
0x1800603e5  push    rsi
0x1800603e6  push    rdi
0x1800603e7  push    r12
0x1800603e9  push    r14
0x1800603eb  push    r15
0x1800603ed  sub     rsp, 300h
0x1800603f4  mov     rax, cs:__security_cookie
0x1800603fb  xor     rax, rsp
0x1800603fe  mov     [rsp+328h+var_38], rax
0x180060406  mov     rsi, rdx
0x180060409  mov     r15, rcx
0x18006040c  xor     ebx, ebx
0x18006040e  mov     [rsp+328h+String], rbx
0x180060413  xor     edx, edx; Val
0x180060415  mov     r8d, 238h; Size
0x18006041b  lea     rcx, [rsp+328h+instance]; void *
0x180060423  call    memset_0
0x180060428  mov     [rsp+328h+var_2A0], ebx
0x18006042f  mov     [rsp+328h+var_29C], bl
0x180060436  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18006043d  mov     [rsp+328h+var_2D0], rax
0x180060442  lea     rax, [rsp+328h+var_2A0]
0x18006044a  mov     [rsp+328h+var_2C8], rax
0x18006044f  lea     rax, aMdmPolicyConfi_129; "MDM_Policy_Config01_Audit02"
0x180060456  mov     [rsp+328h+var_2C0], rax
0x18006045b  lea     rcx, [rsp+328h+var_2A0]
0x180060463  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180060468  mov     eax, cs:dword_180380B68
0x18006046e  cmp     eax, 5
0x180060471  jbe     short loc_1800604E2
0x180060473  mov     rdx, 200000000000h
0x18006047d  lea     rcx, dword_180380B68
0x180060484  call    _tlgKeywordOn
0x180060489  test    al, al
0x18006048b  jz      short loc_1800604E2
0x18006048d  cmp     [rsp+328h+var_29C], bl
0x180060494  jz      short loc_1800604C4
0x180060496  cmp     [rsp+328h+var_288], ebx
0x18006049d  jnz     short loc_1800604BA
0x18006049f  cmp     [rsp+328h+var_284], ebx
0x1800604a6  jnz     short loc_1800604BA
0x1800604a8  cmp     [rsp+328h+var_280], ebx
0x1800604af  jnz     short loc_1800604BA
0x1800604b1  cmp     [rsp+328h+var_27C], ebx
0x1800604b8  jz      short loc_1800604C4
0x1800604ba  lea     r9, [rsp+328h+var_288]
0x1800604c2  jmp     short loc_1800604C7
0x1800604c4  mov     r9, rbx
0x1800604c7  lea     r8, [rsp+328h+var_298]
0x1800604cf  lea     rdx, byte_180356C47
0x1800604d6  lea     rcx, dword_180380B68
0x1800604dd  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800604e2  cmp     [rsi+48h], bl
0x1800604e5  jz      loc_180061352
0x1800604eb  mov     [rsp+328h+var_2E0], bl
0x1800604ef  cmp     [rsi+58h], bl
0x1800604f2  jz      loc_180061352
0x1800604f8  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800604fc  mov     r8, [rsi+50h]; unsigned __int16 *
0x180060500  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x180060507  lea     rcx, [rsp+328h+var_2D0]; this
0x18006050c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180060511  nop
0x180060512  mov     [rsp+328h+var_2D8], rbx
0x180060517  lea     rax, [rsp+328h+var_2D8]
0x18006051c  mov     [rsp+328h+var_2F8], rax
0x180060521  mov     [rsp+328h+var_300], ebx
0x180060525  mov     [rsp+328h+var_308], 3Dh ; '='
0x18006052d  lea     r9, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Audit02_NodeList
0x180060534  mov     r8, [rsi+40h]
0x180060538  mov     rdx, [rsi+50h]
0x18006053c  mov     rcx, r15
0x18006053f  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180060544  mov     r14d, eax
0x180060547  test    eax, eax
0x180060549  jz      short loc_180060550
0x18006054b  jmp     loc_180061358
0x180060550  lea     rax, [rsp+328h+var_2D8]
0x180060555  mov     [rsp+328h+var_2B0], rax
0x18006055a  mov     r12d, 1
0x180060560  mov     [rsp+328h+var_2A8], r12b
0x180060568  mov     rdi, [rsp+328h+var_2D8]
0x18006056d  test    rdi, rdi
0x180060570  jnz     short loc_18006057A
0x180060572  mov     r14d, r12d
0x180060575  jmp     loc_180061358
0x18006057a  mov     r9d, 3Dh ; '='; unsigned int
0x180060580  lea     r8, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180060587  mov     rdx, rsi; struct _MI_Instance *
0x18006058a  mov     rcx, rdi; this
0x18006058d  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180060592  mov     rax, [rdi]
0x180060595  mov     rcx, rdi
0x180060598  mov     rax, [rax+10h]
0x18006059c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605a1  mov     r14d, eax
0x1800605a4  test    eax, eax
0x1800605a6  jz      short loc_1800605C6
0x1800605a8  mov     rcx, [rsp+328h+var_2D8]
0x1800605ad  test    rcx, rcx
0x1800605b0  jz      short loc_1800605C1
0x1800605b2  mov     rax, [rcx]
0x1800605b5  mov     edx, r12d
0x1800605b8  mov     rax, [rax]
0x1800605bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605c0  nop
0x1800605c1  jmp     loc_180061358
0x1800605c6  mov     rax, [rdi]
0x1800605c9  mov     rcx, rdi
0x1800605cc  mov     rax, [rax+8]
0x1800605d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605d5  mov     r14d, eax
0x1800605d8  test    eax, eax
0x1800605da  jz      short loc_1800605FA
0x1800605dc  mov     rcx, [rsp+328h+var_2D8]
0x1800605e1  test    rcx, rcx
0x1800605e4  jz      short loc_1800605F5
0x1800605e6  mov     rax, [rcx]
0x1800605e9  mov     edx, r12d
0x1800605ec  mov     rax, [rax]
0x1800605ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605f4  nop
0x1800605f5  jmp     loc_180061358
0x1800605fa  lea     r8, [rsp+328h+instance]; instance
0x180060602  lea     rdx, MDM_Policy_Config01_Audit02_rtti; classDecl
0x180060609  mov     rcx, r15; context
0x18006060c  call    MI_Context_ConstructInstance
0x180060611  mov     r14d, eax
0x180060614  test    eax, eax
0x180060616  jz      short loc_180060636
0x180060618  mov     rcx, [rsp+328h+var_2D8]
0x18006061d  test    rcx, rcx
0x180060620  jz      short loc_180060631
0x180060622  mov     rax, [rcx]
0x180060625  mov     edx, r12d
0x180060628  mov     rax, [rax]
0x18006062b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060630  nop
0x180060631  jmp     loc_180061358
0x180060636  mov     [rsp+328h+var_2E0], r12b
0x18006063b  mov     rdx, [rsi+40h]
0x18006063f  lea     rcx, [rsp+328h+instance]
0x180060647  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18006064c  mov     rdx, [rsi+50h]
0x180060650  lea     rcx, [rsp+328h+instance]
0x180060658  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18006065d  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x180060662  lea     rdx, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x180060669  mov     rcx, rdi; this
0x18006066c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180060671  test    eax, eax
0x180060673  jnz     short loc_180060694
0x180060675  mov     rcx, [rsp+328h+String]; String
0x18006067a  test    rcx, rcx
0x18006067d  jz      short loc_180060694
0x18006067f  call    cs:__imp__wtoi
0x180060685  mov     [rsp+328h+var_218], eax
0x18006068c  mov     [rsp+328h+var_214], r12b
0x180060694  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x180060699  lea     rdx, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x1800606a0  mov     rcx, rdi; this
0x1800606a3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800606a8  test    eax, eax
0x1800606aa  jnz     short loc_1800606CB
0x1800606ac  mov     rcx, [rsp+328h+String]; String
0x1800606b1  test    rcx, rcx
0x1800606b4  jz      short loc_1800606CB
0x1800606b6  call    cs:__imp__wtoi
0x1800606bc  mov     [rsp+328h+var_210], eax
0x1800606c3  mov     [rsp+328h+var_20C], r12b
0x1800606cb  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x1800606d0  lea     rdx, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x1800606d7  mov     rcx, rdi; this
0x1800606da  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800606df  test    eax, eax
0x1800606e1  jnz     short loc_180060702
0x1800606e3  mov     rcx, [rsp+328h+String]; String
0x1800606e8  test    rcx, rcx
0x1800606eb  jz      short loc_180060702
0x1800606ed  call    cs:__imp__wtoi
0x1800606f3  mov     [rsp+328h+var_208], eax
0x1800606fa  mov     [rsp+328h+var_204], r12b
0x180060702  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x180060707  lea     rdx, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x18006070e  mov     rcx, rdi; this
0x180060711  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180060716  test    eax, eax
0x180060718  jnz     short loc_180060739
0x18006071a  mov     rcx, [rsp+328h+String]; String
0x18006071f  test    rcx, rcx
0x180060722  jz      short loc_180060739
0x180060724  call    cs:__imp__wtoi
0x18006072a  mov     [rsp+328h+var_200], eax
0x180060731  mov     [rsp+328h+var_1FC], r12b
0x180060739  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18006073e  lea     rdx, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x180060745  mov     rcx, rdi; this
0x180060748  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18006074d  test    eax, eax
0x18006074f  jnz     short loc_180060770
0x180060751  mov     rcx, [rsp+328h+String]; String
0x180060756  test    rcx, rcx
0x180060759  jz      short loc_180060770
0x18006075b  call    cs:__imp__wtoi
0x180060761  mov     [rsp+328h+var_1F8], eax
0x180060768  mov     [rsp+328h+var_1F4], r12b
0x180060770  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x180060775  lea     rdx, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x18006077c  mov     rcx, rdi; this
0x18006077f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180060784  test    eax, eax
0x180060786  jnz     short loc_1800607A7
0x180060788  mov     rcx, [rsp+328h+String]; String
0x18006078d  test    rcx, rcx
0x180060790  jz      short loc_1800607A7
0x180060792  call    cs:__imp__wtoi
0x180060798  mov     [rsp+328h+var_1F0], eax
0x18006079f  mov     [rsp+328h+var_1EC], r12b
0x1800607a7  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x1800607ac  lea     rdx, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x1800607b3  mov     rcx, rdi; this
0x1800607b6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800607bb  test    eax, eax
0x1800607bd  jnz     short loc_1800607DE
0x1800607bf  mov     rcx, [rsp+328h+String]; String
0x1800607c4  test    rcx, rcx
0x1800607c7  jz      short loc_1800607DE
0x1800607c9  call    cs:__imp__wtoi
0x1800607cf  mov     [rsp+328h+var_1E8], eax
0x1800607d6  mov     [rsp+328h+var_1E4], r12b
0x1800607de  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x1800607e3  lea     rdx, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x1800607ea  mov     rcx, rdi; this
0x1800607ed  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800607f2  test    eax, eax
0x1800607f4  jnz     short loc_180060815
0x1800607f6  mov     rcx, [rsp+328h+String]; String
0x1800607fb  test    rcx, rcx
0x1800607fe  jz      short loc_180060815
0x180060800  call    cs:__imp__wtoi
0x180060806  mov     [rsp+328h+var_1E0], eax
0x18006080d  mov     [rsp+328h+var_1DC], r12b
0x180060815  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18006081a  lea     rdx, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x180060821  mov     rcx, rdi; this
0x180060824  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180060829  test    eax, eax
0x18006082b  jnz     short loc_18006084C
0x18006082d  mov     rcx, [rsp+328h+String]; String
0x180060832  test    rcx, rcx
0x180060835  jz      short loc_18006084C
0x180060837  call    cs:__imp__wtoi
0x18006083d  mov     [rsp+328h+var_1D8], eax
0x180060844  mov     [rsp+328h+var_1D4], r12b
0x18006084c  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x180060851  lea     rdx, aAccountlogonlo_4; "AccountLogonLogoff_AuditLogoff"
0x180060858  mov     rcx, rdi; this
0x18006085b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180060860  test    eax, eax
0x180060862  jnz     short loc_180060883
0x180060864  mov     rcx, [rsp+328h+String]; String
0x180060869  test    rcx, rcx
0x18006086c  jz      short loc_180060883
0x18006086e  call    cs:__imp__wtoi
0x180060874  mov     [rsp+328h+var_1D0], eax
0x18006087b  mov     [rsp+328h+var_1CC], r12b
0x180060883  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x180060888  lea     rdx, aAccountlogonlo_8; "AccountLogonLogoff_AuditLogon"
0x18006088f  mov     rcx, rdi; this
0x180060892  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180060897  test    eax, eax
0x180060899  jnz     short loc_1800608BA
0x18006089b  mov     rcx, [rsp+328h+String]; String
0x1800608a0  test    rcx, rcx
0x1800608a3  jz      short loc_1800608BA
0x1800608a5  call    cs:__imp__wtoi
0x1800608ab  mov     [rsp+328h+var_1C8], eax
0x1800608b2  mov     [rsp+328h+var_1C4], r12b
0x1800608ba  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x1800608bf  lea     rdx, aAccountlogonlo; "AccountLogonLogoff_AuditNetworkPolicySe"...
0x1800608c6  mov     rcx, rdi; this
0x1800608c9  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800608ce  test    eax, eax
0x1800608d0  jnz     short loc_1800608F1
0x1800608d2  mov     rcx, [rsp+328h+String]; String
0x1800608d7  test    rcx, rcx
0x1800608da  jz      short loc_1800608F1
0x1800608dc  call    cs:__imp__wtoi
0x1800608e2  mov     [rsp+328h+var_1C0], eax
0x1800608e9  mov     [rsp+328h+var_1BC], r12b
0x1800608f1  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x1800608f6  lea     rdx, aAccountlogonlo_3; "AccountLogonLogoff_AuditOtherLogonLogof"...
0x1800608fd  mov     rcx, rdi; this
0x180060900  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180060905  test    eax, eax
0x180060907  jnz     short loc_180060928
0x180060909  mov     rcx, [rsp+328h+String]; String
0x18006090e  test    rcx, rcx
0x180060911  jz      short loc_180060928
  ... truncated ...
```
