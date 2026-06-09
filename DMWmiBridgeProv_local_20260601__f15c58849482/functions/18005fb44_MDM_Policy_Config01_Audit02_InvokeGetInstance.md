# MDM_Policy_Config01_Audit02_InvokeGetInstance

- ea: `0x18005fb44`
- end: `0x180060cba`
- name: `MDM_Policy_Config01_Audit02_InvokeGetInstance`
- size: `4470`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005d200`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18005fb44`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18005fde3`
- `msvcrt!_wtoi` at `0x18005fe20`
- `msvcrt!_wtoi` at `0x18005fe5d`
- `msvcrt!_wtoi` at `0x18005fe9a`
- `msvcrt!_wtoi` at `0x18005fed7`
- `msvcrt!_wtoi` at `0x18005ff14`
- `msvcrt!_wtoi` at `0x18005ff51`
- `msvcrt!_wtoi` at `0x18005ff8e`
- `msvcrt!_wtoi` at `0x18005ffcb`
- `msvcrt!_wtoi` at `0x180060008`
- `msvcrt!_wtoi` at `0x180060045`
- `msvcrt!_wtoi` at `0x180060082`
- `msvcrt!_wtoi` at `0x1800600bf`
- `msvcrt!_wtoi` at `0x1800600fc`
- `msvcrt!_wtoi` at `0x180060139`
- `msvcrt!_wtoi` at `0x180060176`
- `msvcrt!_wtoi` at `0x1800601b3`
- `msvcrt!_wtoi` at `0x1800601f0`
- `msvcrt!_wtoi` at `0x18006022d`
- `msvcrt!_wtoi` at `0x18006026a`
- `msvcrt!_wtoi` at `0x1800602a7`
- `msvcrt!_wtoi` at `0x1800602e4`
- `msvcrt!_wtoi` at `0x180060321`
- `msvcrt!_wtoi` at `0x18006035e`
- `msvcrt!_wtoi` at `0x18006039b`
- `msvcrt!_wtoi` at `0x1800603d8`
- `msvcrt!_wtoi` at `0x180060415`
- `msvcrt!_wtoi` at `0x180060452`
- `msvcrt!_wtoi` at `0x18006048f`
- `msvcrt!_wtoi` at `0x1800604cc`
- `msvcrt!_wtoi` at `0x180060509`
- `msvcrt!_wtoi` at `0x180060546`
- `msvcrt!_wtoi` at `0x180060583`
- `msvcrt!_wtoi` at `0x1800605c0`
- `msvcrt!_wtoi` at `0x1800605fd`
- `msvcrt!_wtoi` at `0x18006063a`
- `msvcrt!_wtoi` at `0x180060677`
- `msvcrt!_wtoi` at `0x1800606b4`
- `msvcrt!_wtoi` at `0x1800606f1`
- `msvcrt!_wtoi` at `0x18006072e`
- `msvcrt!_wtoi` at `0x18006076b`
- `msvcrt!_wtoi` at `0x1800607a8`
- `msvcrt!_wtoi` at `0x1800607e5`
- `msvcrt!_wtoi` at `0x180060822`
- `msvcrt!_wtoi` at `0x18006085f`
- `msvcrt!_wtoi` at `0x18006089c`
- `msvcrt!_wtoi` at `0x1800608d9`
- `msvcrt!_wtoi` at `0x180060916`
- `msvcrt!_wtoi` at `0x180060953`
- `msvcrt!_wtoi` at `0x180060990`
- `msvcrt!_wtoi` at `0x1800609cd`
- `msvcrt!_wtoi` at `0x180060a0a`
- `msvcrt!_wtoi` at `0x180060a47`
- `msvcrt!_wtoi` at `0x180060a84`
- `msvcrt!_wtoi` at `0x180060ac1`
- `msvcrt!_wtoi` at `0x180060afe`
- `msvcrt!_wtoi` at `0x180060b3b`
- `msvcrt!_wtoi` at `0x180060b78`
- `msvcrt!_wtoi` at `0x180060bb5`
- `msvcrt!_wtoi` at `0x18005fde3`
- `msvcrt!_wtoi` at `0x18005fe20`
- `msvcrt!_wtoi` at `0x18005fe5d`
- `msvcrt!_wtoi` at `0x18005fe9a`
- `msvcrt!_wtoi` at `0x18005fed7`
- `msvcrt!_wtoi` at `0x18005ff14`
- `msvcrt!_wtoi` at `0x18005ff51`
- `msvcrt!_wtoi` at `0x18005ff8e`
- `msvcrt!_wtoi` at `0x18005ffcb`
- `msvcrt!_wtoi` at `0x180060008`
- `msvcrt!_wtoi` at `0x180060045`
- `msvcrt!_wtoi` at `0x180060082`
- `msvcrt!_wtoi` at `0x1800600bf`
- `msvcrt!_wtoi` at `0x1800600fc`
- `msvcrt!_wtoi` at `0x180060139`
- `msvcrt!_wtoi` at `0x180060176`
- `msvcrt!_wtoi` at `0x1800601b3`
- `msvcrt!_wtoi` at `0x1800601f0`
- `msvcrt!_wtoi` at `0x18006022d`
- `msvcrt!_wtoi` at `0x18006026a`
- `msvcrt!_wtoi` at `0x1800602a7`
- `msvcrt!_wtoi` at `0x1800602e4`
- `msvcrt!_wtoi` at `0x180060321`
- `msvcrt!_wtoi` at `0x18006035e`
- `msvcrt!_wtoi` at `0x18006039b`
- `msvcrt!_wtoi` at `0x1800603d8`
- `msvcrt!_wtoi` at `0x180060415`
- `msvcrt!_wtoi` at `0x180060452`
- `msvcrt!_wtoi` at `0x18006048f`
- `msvcrt!_wtoi` at `0x1800604cc`
- `msvcrt!_wtoi` at `0x180060509`
- `msvcrt!_wtoi` at `0x180060546`
- `msvcrt!_wtoi` at `0x180060583`
- `msvcrt!_wtoi` at `0x1800605c0`
- `msvcrt!_wtoi` at `0x1800605fd`
- `msvcrt!_wtoi` at `0x18006063a`
- `msvcrt!_wtoi` at `0x180060677`
- `msvcrt!_wtoi` at `0x1800606b4`
- `msvcrt!_wtoi` at `0x1800606f1`
- `msvcrt!_wtoi` at `0x18006072e`
- `msvcrt!_wtoi` at `0x18006076b`
- `msvcrt!_wtoi` at `0x1800607a8`
- `msvcrt!_wtoi` at `0x1800607e5`
- `msvcrt!_wtoi` at `0x180060822`
- `msvcrt!_wtoi` at `0x18006085f`
- `msvcrt!_wtoi` at `0x18006089c`
- `msvcrt!_wtoi` at `0x1800608d9`
- `msvcrt!_wtoi` at `0x180060916`
- `msvcrt!_wtoi` at `0x180060953`
- `msvcrt!_wtoi` at `0x180060990`
- `msvcrt!_wtoi` at `0x1800609cd`
- `msvcrt!_wtoi` at `0x180060a0a`
- `msvcrt!_wtoi` at `0x180060a47`
- `msvcrt!_wtoi` at `0x180060a84`
- `msvcrt!_wtoi` at `0x180060ac1`
- `msvcrt!_wtoi` at `0x180060afe`
- `msvcrt!_wtoi` at `0x180060b3b`
- `msvcrt!_wtoi` at `0x180060b78`
- `msvcrt!_wtoi` at `0x180060bb5`

## string_xrefs

- `0x18005fe03`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x18005fe40`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x180060196`: `AccountManagement_AuditComputerAccountManagement`
- `0x18006024d`: `AccountManagement_AuditSecurityGroupManagement`
- `0x1800603f8`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x180060435`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x180060472`: `DSAccess_AuditDirectoryServiceAccess`
- `0x1800604af`: `DSAccess_AuditDirectoryServiceChanges`
- `0x1800604ec`: `DSAccess_AuditDirectoryServiceReplication`
- `0x180060529`: `ObjectAccess_AuditApplicationGenerated`
- `0x180060566`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x1800605a3`: `ObjectAccess_AuditCertificationServices`
- `0x1800605e0`: `ObjectAccess_AuditDetailedFileShare`
- `0x18006061d`: `ObjectAccess_AuditFileShare`
- `0x18006065a`: `ObjectAccess_AuditFileSystem`
- `0x180060697`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x1800606d4`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x180060711`: `ObjectAccess_AuditHandleManipulation`
- `0x18006074e`: `ObjectAccess_AuditKernelObject`
- `0x18006078b`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x1800607c8`: `ObjectAccess_AuditRegistry`
- `0x180060805`: `ObjectAccess_AuditRemovableStorage`
- `0x180060842`: `ObjectAccess_AuditSAM`
- `0x1800609ed`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x180060a2a`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x180060a67`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x180060b1e`: `System_AuditSecurityStateChange`
- `0x180060b5b`: `System_AuditSecuritySystemExtension`
- `0x18005fbb3`: `MDM_Policy_Config01_Audit02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Audit02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
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
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_206;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v11,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v10 = 0;
  v5 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       a2[1].serverName,
                       a2[1].ft,
                       &MDM_Policy_Config01_Audit02_NodeList,
                       61,
                       0,
                       &v10);
  if ( v5 == MI_RESULT_OK )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = MI_RESULT_FAILED;
      goto LABEL_206;
    }
    WmiRequestHandler::SetRequestMIInstance(v10, a2, (struct WmiNodeInfo *)&MDM_Policy_Config01_Audit02_NodeList, 0x3Du);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_206;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_206;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogon_AuditCredentialValidation",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogon_AuditKerberosAuthenticationService",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogon_AuditKerberosServiceTicketOperations",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogon_AuditOtherAccountLogonEvents",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditAccountLockout",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditGroupMembership",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditIPsecExtendedMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditIPsecMainMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditIPsecQuickMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditLogoff",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditLogon",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditNetworkPolicyServer",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditSpecialLogon",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v44 = _wtoi(String);
      v45 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountLogonLogoff_AuditUserDeviceClaims",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v46 = _wtoi(String);
      v47 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountManagement_AuditApplicationGroupManagement",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v48 = _wtoi(String);
      v49 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountManagement_AuditComputerAccountManagement",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v50 = _wtoi(String);
      v51 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountManagement_AuditDistributionGroupManagement",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v52 = _wtoi(String);
      v53 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountManagement_AuditOtherAccountManagementEvents",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v54 = _wtoi(String);
      v55 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountManagement_AuditSecurityGroupManagement",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v56 = _wtoi(String);
      v57 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AccountManagement_AuditUserAccountManagement",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v58 = _wtoi(String);
      v59 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DetailedTracking_AuditDPAPIActivity",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v60 = _wtoi(String);
      v61 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DetailedTracking_AuditPNPActivity",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v62 = _wtoi(String);
      v63 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DetailedTracking_AuditProcessCreation",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v64 = _wtoi(String);
      v65 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DetailedTracking_AuditProcessTermination",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v66 = _wtoi(String);
      v67 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DetailedTracking_AuditRPCEvents",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v68 = _wtoi(String);
      v69 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DetailedTracking_AuditTokenRightAdjusted",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v70 = _wtoi(String);
      v71 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DSAccess_AuditDetailedDirectoryServiceReplication",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v72 = _wtoi(String);
      v73 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DSAccess_AuditDirectoryServiceAccess",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v74 = _wtoi(String);
      v75 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DSAccess_AuditDirectoryServiceChanges",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v76 = _wtoi(String);
      v77 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DSAccess_AuditDirectoryServiceReplication",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v78 = _wtoi(String);
      v79 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditApplicationGenerated",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v80 = _wtoi(String);
      v81 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditCentralAccessPolicyStaging",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v82 = _wtoi(String);
      v83 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditCertificationServices",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v84 = _wtoi(String);
      v85 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditDetailedFileShare",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v86 = _wtoi(String);
      v87 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditFileShare",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v88 = _wtoi(String);
      v89 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditFileSystem",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v90 = _wtoi(String);
      v91 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditFilteringPlatformConnection",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v92 = _wtoi(String);
      v93 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditFilteringPlatformPacketDrop",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v94 = _wtoi(String);
      v95 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditHandleManipulation",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v96 = _wtoi(String);
      v97 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditKernelObject",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v98 = _wtoi(String);
      v99 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditOtherObjectAccessEvents",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v100 = _wtoi(String);
      v101 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ObjectAccess_AuditRegistry", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v102 = _wtoi(String);
      v103 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ObjectAccess_AuditRemovableStorage",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v104 = _wtoi(String);
      v105 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ObjectAccess_AuditSAM", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v106 = _wtoi(String);
      v107 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PolicyChange_AuditAuthenticationPolicyChange",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v108 = _wtoi(String);
      v109 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PolicyChange_AuditAuthorizationPolicyChange",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v110 = _wtoi(String);
      v111 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PolicyChange_AuditFilteringPlatformPolicyChange",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v112 = _wtoi(String);
      v113 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v114 = _wtoi(String);
      v115 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PolicyChange_AuditOtherPolicyChangeEvents",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v116 = _wtoi(String);
      v117 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PolicyChange_AuditPolicyChange",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v118 = _wtoi(String);
      v119 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v120 = _wtoi(String);
      v121 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v122 = _wtoi(String);
      v123 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PrivilegeUse_AuditSensitivePrivilegeUse",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v124 = _wtoi(String);
      v125 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"System_AuditIPsecDriver", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v126 = _wtoi(String);
      v127 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"System_AuditOtherSystemEvents",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v128 = _wtoi(String);
      v129 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"System_AuditSecurityStateChange",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v130 = _wtoi(String);
      v131 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"System_AuditSecuritySystemExtension",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v132 = _wtoi(String);
      v133 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"System_AuditSystemIntegrity",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
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
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005fb44  mov     [rsp+arg_10], rbx
0x18005fb49  push    rsi
0x18005fb4a  push    rdi
0x18005fb4b  push    r12
0x18005fb4d  push    r14
0x18005fb4f  push    r15
0x18005fb51  sub     rsp, 300h
0x18005fb58  mov     rax, cs:__security_cookie
0x18005fb5f  xor     rax, rsp
0x18005fb62  mov     [rsp+328h+var_38], rax
0x18005fb6a  mov     rsi, rdx
0x18005fb6d  mov     r15, rcx
0x18005fb70  xor     ebx, ebx
0x18005fb72  mov     [rsp+328h+String], rbx
0x18005fb77  xor     edx, edx; Val
0x18005fb79  mov     r8d, 238h; Size
0x18005fb7f  lea     rcx, [rsp+328h+instance]; void *
0x18005fb87  call    memset_0
0x18005fb8c  mov     [rsp+328h+var_2A0], ebx
0x18005fb93  mov     [rsp+328h+var_29C], bl
0x18005fb9a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18005fba1  mov     [rsp+328h+var_2D0], rax
0x18005fba6  lea     rax, [rsp+328h+var_2A0]
0x18005fbae  mov     [rsp+328h+var_2C8], rax
0x18005fbb3  lea     rax, aMdmPolicyConfi_129; "MDM_Policy_Config01_Audit02"
0x18005fbba  mov     [rsp+328h+var_2C0], rax
0x18005fbbf  lea     rcx, [rsp+328h+var_2A0]
0x18005fbc7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18005fbcc  mov     eax, cs:dword_180380B68
0x18005fbd2  cmp     eax, 5
0x18005fbd5  jbe     short loc_18005FC46
0x18005fbd7  mov     rdx, 200000000000h
0x18005fbe1  lea     rcx, dword_180380B68
0x18005fbe8  call    _tlgKeywordOn
0x18005fbed  test    al, al
0x18005fbef  jz      short loc_18005FC46
0x18005fbf1  cmp     [rsp+328h+var_29C], bl
0x18005fbf8  jz      short loc_18005FC28
0x18005fbfa  cmp     [rsp+328h+var_288], ebx
0x18005fc01  jnz     short loc_18005FC1E
0x18005fc03  cmp     [rsp+328h+var_284], ebx
0x18005fc0a  jnz     short loc_18005FC1E
0x18005fc0c  cmp     [rsp+328h+var_280], ebx
0x18005fc13  jnz     short loc_18005FC1E
0x18005fc15  cmp     [rsp+328h+var_27C], ebx
0x18005fc1c  jz      short loc_18005FC28
0x18005fc1e  lea     r9, [rsp+328h+var_288]
0x18005fc26  jmp     short loc_18005FC2B
0x18005fc28  mov     r9, rbx
0x18005fc2b  lea     r8, [rsp+328h+var_298]
0x18005fc33  lea     rdx, byte_180356C47
0x18005fc3a  lea     rcx, dword_180380B68
0x18005fc41  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18005fc46  cmp     [rsi+48h], bl
0x18005fc49  jz      loc_180060C18
0x18005fc4f  mov     [rsp+328h+var_2E0], bl
0x18005fc53  cmp     [rsi+58h], bl
0x18005fc56  jz      loc_180060C18
0x18005fc5c  mov     r9, [rsi+40h]; unsigned __int16 *
0x18005fc60  mov     r8, [rsi+50h]; unsigned __int16 *
0x18005fc64  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18005fc6b  lea     rcx, [rsp+328h+var_2D0]; this
0x18005fc70  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18005fc75  nop
0x18005fc76  mov     [rsp+328h+var_2D8], rbx
0x18005fc7b  lea     rax, [rsp+328h+var_2D8]
0x18005fc80  mov     [rsp+328h+var_2F8], rax
0x18005fc85  mov     [rsp+328h+var_300], ebx
0x18005fc89  mov     [rsp+328h+var_308], 3Dh ; '='
0x18005fc91  lea     r9, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Audit02_NodeList
0x18005fc98  mov     r8, [rsi+40h]
0x18005fc9c  mov     rdx, [rsi+50h]
0x18005fca0  mov     rcx, r15
0x18005fca3  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18005fca8  mov     r14d, eax
0x18005fcab  test    eax, eax
0x18005fcad  jz      short loc_18005FCB4
0x18005fcaf  jmp     loc_180060C1E
0x18005fcb4  lea     rax, [rsp+328h+var_2D8]
0x18005fcb9  mov     [rsp+328h+var_2B0], rax
0x18005fcbe  mov     r12d, 1
0x18005fcc4  mov     [rsp+328h+var_2A8], r12b
0x18005fccc  mov     rdi, [rsp+328h+var_2D8]
0x18005fcd1  test    rdi, rdi
0x18005fcd4  jnz     short loc_18005FCDE
0x18005fcd6  mov     r14d, r12d
0x18005fcd9  jmp     loc_180060C1E
0x18005fcde  mov     r9d, 3Dh ; '='; unsigned int
0x18005fce4  lea     r8, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18005fceb  mov     rdx, rsi; struct _MI_Instance *
0x18005fcee  mov     rcx, rdi; this
0x18005fcf1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18005fcf6  mov     rax, [rdi]
0x18005fcf9  mov     rcx, rdi
0x18005fcfc  mov     rax, [rax+10h]
0x18005fd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd05  mov     r14d, eax
0x18005fd08  test    eax, eax
0x18005fd0a  jz      short loc_18005FD2A
0x18005fd0c  mov     rcx, [rsp+328h+var_2D8]
0x18005fd11  test    rcx, rcx
0x18005fd14  jz      short loc_18005FD25
0x18005fd16  mov     rax, [rcx]
0x18005fd19  mov     edx, r12d
0x18005fd1c  mov     rax, [rax]
0x18005fd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd24  nop
0x18005fd25  jmp     loc_180060C1E
0x18005fd2a  mov     rax, [rdi]
0x18005fd2d  mov     rcx, rdi
0x18005fd30  mov     rax, [rax+8]
0x18005fd34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd39  mov     r14d, eax
0x18005fd3c  test    eax, eax
0x18005fd3e  jz      short loc_18005FD5E
0x18005fd40  mov     rcx, [rsp+328h+var_2D8]
0x18005fd45  test    rcx, rcx
0x18005fd48  jz      short loc_18005FD59
0x18005fd4a  mov     rax, [rcx]
0x18005fd4d  mov     edx, r12d
0x18005fd50  mov     rax, [rax]
0x18005fd53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd58  nop
0x18005fd59  jmp     loc_180060C1E
0x18005fd5e  lea     r8, [rsp+328h+instance]; instance
0x18005fd66  lea     rdx, MDM_Policy_Config01_Audit02_rtti; classDecl
0x18005fd6d  mov     rcx, r15; context
0x18005fd70  call    MI_Context_ConstructInstance
0x18005fd75  mov     r14d, eax
0x18005fd78  test    eax, eax
0x18005fd7a  jz      short loc_18005FD9A
0x18005fd7c  mov     rcx, [rsp+328h+var_2D8]
0x18005fd81  test    rcx, rcx
0x18005fd84  jz      short loc_18005FD95
0x18005fd86  mov     rax, [rcx]
0x18005fd89  mov     edx, r12d
0x18005fd8c  mov     rax, [rax]
0x18005fd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd94  nop
0x18005fd95  jmp     loc_180060C1E
0x18005fd9a  mov     [rsp+328h+var_2E0], r12b
0x18005fd9f  mov     rdx, [rsi+40h]
0x18005fda3  lea     rcx, [rsp+328h+instance]
0x18005fdab  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18005fdb0  mov     rdx, [rsi+50h]
0x18005fdb4  lea     rcx, [rsp+328h+instance]
0x18005fdbc  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18005fdc1  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18005fdc6  lea     rdx, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x18005fdcd  mov     rcx, rdi; this
0x18005fdd0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005fdd5  test    eax, eax
0x18005fdd7  jnz     short loc_18005FDFE
0x18005fdd9  mov     rcx, [rsp+328h+String]; String
0x18005fdde  test    rcx, rcx
0x18005fde1  jz      short loc_18005FDFE
0x18005fde3  call    cs:__imp__wtoi
0x18005fdea  nop     dword ptr [rax+rax+00h]
0x18005fdef  mov     [rsp+328h+var_218], eax
0x18005fdf6  mov     [rsp+328h+var_214], r12b
0x18005fdfe  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18005fe03  lea     rdx, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x18005fe0a  mov     rcx, rdi; this
0x18005fe0d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005fe12  test    eax, eax
0x18005fe14  jnz     short loc_18005FE3B
0x18005fe16  mov     rcx, [rsp+328h+String]; String
0x18005fe1b  test    rcx, rcx
0x18005fe1e  jz      short loc_18005FE3B
0x18005fe20  call    cs:__imp__wtoi
0x18005fe27  nop     dword ptr [rax+rax+00h]
0x18005fe2c  mov     [rsp+328h+var_210], eax
0x18005fe33  mov     [rsp+328h+var_20C], r12b
0x18005fe3b  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18005fe40  lea     rdx, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x18005fe47  mov     rcx, rdi; this
0x18005fe4a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005fe4f  test    eax, eax
0x18005fe51  jnz     short loc_18005FE78
0x18005fe53  mov     rcx, [rsp+328h+String]; String
0x18005fe58  test    rcx, rcx
0x18005fe5b  jz      short loc_18005FE78
0x18005fe5d  call    cs:__imp__wtoi
0x18005fe64  nop     dword ptr [rax+rax+00h]
0x18005fe69  mov     [rsp+328h+var_208], eax
0x18005fe70  mov     [rsp+328h+var_204], r12b
0x18005fe78  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18005fe7d  lea     rdx, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x18005fe84  mov     rcx, rdi; this
0x18005fe87  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005fe8c  test    eax, eax
0x18005fe8e  jnz     short loc_18005FEB5
0x18005fe90  mov     rcx, [rsp+328h+String]; String
0x18005fe95  test    rcx, rcx
0x18005fe98  jz      short loc_18005FEB5
0x18005fe9a  call    cs:__imp__wtoi
0x18005fea1  nop     dword ptr [rax+rax+00h]
0x18005fea6  mov     [rsp+328h+var_200], eax
0x18005fead  mov     [rsp+328h+var_1FC], r12b
0x18005feb5  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18005feba  lea     rdx, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x18005fec1  mov     rcx, rdi; this
0x18005fec4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005fec9  test    eax, eax
0x18005fecb  jnz     short loc_18005FEF2
0x18005fecd  mov     rcx, [rsp+328h+String]; String
0x18005fed2  test    rcx, rcx
0x18005fed5  jz      short loc_18005FEF2
0x18005fed7  call    cs:__imp__wtoi
0x18005fede  nop     dword ptr [rax+rax+00h]
0x18005fee3  mov     [rsp+328h+var_1F8], eax
0x18005feea  mov     [rsp+328h+var_1F4], r12b
0x18005fef2  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18005fef7  lea     rdx, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x18005fefe  mov     rcx, rdi; this
0x18005ff01  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005ff06  test    eax, eax
0x18005ff08  jnz     short loc_18005FF2F
0x18005ff0a  mov     rcx, [rsp+328h+String]; String
0x18005ff0f  test    rcx, rcx
0x18005ff12  jz      short loc_18005FF2F
0x18005ff14  call    cs:__imp__wtoi
0x18005ff1b  nop     dword ptr [rax+rax+00h]
0x18005ff20  mov     [rsp+328h+var_1F0], eax
0x18005ff27  mov     [rsp+328h+var_1EC], r12b
0x18005ff2f  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18005ff34  lea     rdx, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x18005ff3b  mov     rcx, rdi; this
0x18005ff3e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005ff43  test    eax, eax
0x18005ff45  jnz     short loc_18005FF6C
0x18005ff47  mov     rcx, [rsp+328h+String]; String
0x18005ff4c  test    rcx, rcx
0x18005ff4f  jz      short loc_18005FF6C
0x18005ff51  call    cs:__imp__wtoi
0x18005ff58  nop     dword ptr [rax+rax+00h]
0x18005ff5d  mov     [rsp+328h+var_1E8], eax
0x18005ff64  mov     [rsp+328h+var_1E4], r12b
0x18005ff6c  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18005ff71  lea     rdx, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x18005ff78  mov     rcx, rdi; this
0x18005ff7b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005ff80  test    eax, eax
0x18005ff82  jnz     short loc_18005FFA9
0x18005ff84  mov     rcx, [rsp+328h+String]; String
0x18005ff89  test    rcx, rcx
0x18005ff8c  jz      short loc_18005FFA9
0x18005ff8e  call    cs:__imp__wtoi
0x18005ff95  nop     dword ptr [rax+rax+00h]
0x18005ff9a  mov     [rsp+328h+var_1E0], eax
0x18005ffa1  mov     [rsp+328h+var_1DC], r12b
0x18005ffa9  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18005ffae  lea     rdx, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x18005ffb5  mov     rcx, rdi; this
0x18005ffb8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005ffbd  test    eax, eax
0x18005ffbf  jnz     short loc_18005FFE6
0x18005ffc1  mov     rcx, [rsp+328h+String]; String
0x18005ffc6  test    rcx, rcx
0x18005ffc9  jz      short loc_18005FFE6
0x18005ffcb  call    cs:__imp__wtoi
0x18005ffd2  nop     dword ptr [rax+rax+00h]
0x18005ffd7  mov     [rsp+328h+var_1D8], eax
0x18005ffde  mov     [rsp+328h+var_1D4], r12b
0x18005ffe6  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x18005ffeb  lea     rdx, aAccountlogonlo_4; "AccountLogonLogoff_AuditLogoff"
0x18005fff2  mov     rcx, rdi; this
0x18005fff5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005fffa  test    eax, eax
0x18005fffc  jnz     short loc_180060023
0x18005fffe  mov     rcx, [rsp+328h+String]; String
0x180060003  test    rcx, rcx
0x180060006  jz      short loc_180060023
0x180060008  call    cs:__imp__wtoi
0x18006000f  nop     dword ptr [rax+rax+00h]
0x180060014  mov     [rsp+328h+var_1D0], eax
0x18006001b  mov     [rsp+328h+var_1CC], r12b
0x180060023  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x180060028  lea     rdx, aAccountlogonlo_8; "AccountLogonLogoff_AuditLogon"
0x18006002f  mov     rcx, rdi; this
0x180060032  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180060037  test    eax, eax
0x180060039  jnz     short loc_180060060
0x18006003b  mov     rcx, [rsp+328h+String]; String
0x180060040  test    rcx, rcx
0x180060043  jz      short loc_180060060
0x180060045  call    cs:__imp__wtoi
0x18006004c  nop     dword ptr [rax+rax+00h]
0x180060051  mov     [rsp+328h+var_1C8], eax
0x180060058  mov     [rsp+328h+var_1C4], r12b
0x180060060  lea     r8, [rsp+328h+String]; unsigned __int16 **
0x180060065  lea     rdx, aAccountlogonlo; "AccountLogonLogoff_AuditNetworkPolicySe"...
0x18006006c  mov     rcx, rdi; this
0x18006006f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180060074  test    eax, eax
0x180060076  jnz     short loc_18006009D
0x180060078  mov     rcx, [rsp+328h+String]; String
0x18006007d  test    rcx, rcx
0x180060080  jz      short loc_18006009D
0x180060082  call    cs:__imp__wtoi
  ... truncated ...
```
