# MDM_Policy_Config01_Audit02_InvokeCreateInstance

- ea: `0x18005d22c`
- end: `0x18005e44c`
- name: `MDM_Policy_Config01_Audit02_InvokeCreateInstance`
- size: `4640`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005d170`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18005d22c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x18005d432`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x18005d46f`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x18005d7ec`: `AccountManagement_AuditComputerAccountManagement`
- `0x18005d8ac`: `AccountManagement_AuditSecurityGroupManagement`
- `0x18005da6c`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x18005daac`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x18005daec`: `DSAccess_AuditDirectoryServiceAccess`
- `0x18005db2c`: `DSAccess_AuditDirectoryServiceChanges`
- `0x18005db6c`: `DSAccess_AuditDirectoryServiceReplication`
- `0x18005dbac`: `ObjectAccess_AuditApplicationGenerated`
- `0x18005dbec`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x18005dc2c`: `ObjectAccess_AuditCertificationServices`
- `0x18005dc6c`: `ObjectAccess_AuditDetailedFileShare`
- `0x18005dcac`: `ObjectAccess_AuditFileShare`
- `0x18005dcec`: `ObjectAccess_AuditFileSystem`
- `0x18005dd2c`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x18005dd6c`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x18005ddac`: `ObjectAccess_AuditHandleManipulation`
- `0x18005ddec`: `ObjectAccess_AuditKernelObject`
- `0x18005de2c`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x18005de6c`: `ObjectAccess_AuditRegistry`
- `0x18005deac`: `ObjectAccess_AuditRemovableStorage`
- `0x18005deec`: `ObjectAccess_AuditSAM`
- `0x18005e0ac`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x18005e0ec`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x18005e12c`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x18005e1ec`: `System_AuditSecurityStateChange`
- `0x18005e22c`: `System_AuditSecuritySystemExtension`
- `0x18005d355`: `CreateInstanceStart`
- `0x18005e3b2`: `CreateInstanceEnd`
- `0x18005d29c`: `MDM_Policy_Config01_Audit02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Audit02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-2D8h] BYREF
  char v9; // [rsp+48h] [rbp-2D0h]
  _QWORD v10[5]; // [rsp+50h] [rbp-2C8h] BYREF
  char v11; // [rsp+78h] [rbp-2A0h]
  int v12; // [rsp+80h] [rbp-298h] BYREF
  char v13; // [rsp+84h] [rbp-294h]
  _BYTE v14[16]; // [rsp+88h] [rbp-290h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-280h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-268h] BYREF

  memset_0(&instance, 0, 0x238u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Config01_Audit02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180361242,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_265;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = (unsigned int)CreateRequestHandlerInstance(
                             self,
                             a2[1].serverName,
                             a2[1].ft,
                             &MDM_Policy_Config01_Audit02_NodeList,
                             61,
                             4,
                             &v8);
  if ( inserted == MI_RESULT_OK )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = MI_RESULT_FAILED;
      goto LABEL_265;
    }
    WmiRequestHandler::SetRequestMIInstance(v8, a2, (struct WmiNodeInfo *)&MDM_Policy_Config01_Audit02_NodeList, 0x3Du);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccountLogon_AuditCredentialValidation", a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
LABEL_260:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_265;
      }
    }
    if ( BYTE4(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogon_AuditKerberosAuthenticationService",
                   &a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogon_AuditKerberosServiceTicketOperations",
                   &a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogon_AuditOtherAccountLogonEvents",
                   &a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccountLogonLogoff_AuditAccountLockout", &a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogonLogoff_AuditGroupMembership",
                   &a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogonLogoff_AuditIPsecExtendedMode",
                   &a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccountLogonLogoff_AuditIPsecMainMode", &a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccountLogonLogoff_AuditIPsecQuickMode", a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccountLogonLogoff_AuditLogoff", &a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccountLogonLogoff_AuditLogon", &a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogonLogoff_AuditNetworkPolicyServer",
                   &a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccountLogonLogoff_AuditOtherLogonLogoffEvents", &a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccountLogonLogoff_AuditSpecialLogon", &a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogonLogoff_AuditUserDeviceClaims",
                   &a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountManagement_AuditApplicationGroupManagement",
                   &a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountManagement_AuditComputerAccountManagement",
                   a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountManagement_AuditDistributionGroupManagement",
                   &a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountManagement_AuditOtherAccountManagementEvents",
                   &a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountManagement_AuditSecurityGroupManagement",
                   &a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccountManagement_AuditUserAccountManagement", &a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DetailedTracking_AuditDPAPIActivity", &a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DetailedTracking_AuditPNPActivity", &a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DetailedTracking_AuditProcessCreation", &a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DetailedTracking_AuditProcessTermination",
                   a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DetailedTracking_AuditRPCEvents", &a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DetailedTracking_AuditTokenRightAdjusted",
                   &a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DSAccess_AuditDetailedDirectoryServiceReplication",
                   &a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DSAccess_AuditDirectoryServiceAccess", &a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DSAccess_AuditDirectoryServiceChanges", &a2[5].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DSAccess_AuditDirectoryServiceReplication",
                   &a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ObjectAccess_AuditApplicationGenerated",
                   &a2[5].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ObjectAccess_AuditCentralAccessPolicyStaging",
                   a2[5].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ObjectAccess_AuditCertificationServices",
                   &a2[5].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditDetailedFileShare", &a2[5].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditFileShare", &a2[5].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditFileSystem", &a2[6]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ObjectAccess_AuditFilteringPlatformConnection",
                   &a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                   &a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditHandleManipulation", &a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditKernelObject", a2[6].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ObjectAccess_AuditOtherObjectAccessEvents",
                   &a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditRegistry", &a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditRemovableStorage", &a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[7].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditSAM", &a2[7]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PolicyChange_AuditAuthenticationPolicyChange",
                   &a2[7].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PolicyChange_AuditAuthorizationPolicyChange",
                   &a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[7].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PolicyChange_AuditFilteringPlatformPolicyChange",
                   &a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[7].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                   a2[7].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PolicyChange_AuditOtherPolicyChangeEvents",
                   &a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PolicyChange_AuditPolicyChange", &a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[7].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                   &a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PrivilegeUse_AuditOtherPrivilegeUseEvents", &a2[8]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PrivilegeUse_AuditSensitivePrivilegeUse",
                   &a2[8].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"System_AuditIPsecDriver", &a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"System_AuditOtherSystemEvents", &a2[8].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"System_AuditSecurityStateChange", a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"System_AuditSecuritySystemExtension", &a2[8].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"System_AuditSystemIntegrity", &a2[8].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_265;
      goto LABEL_260;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_265;
      goto LABEL_260;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Audit02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_265;
      goto LABEL_260;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_265:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033A025,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18005d22c  mov     [rsp+arg_10], rsi
0x18005d231  mov     [rsp+arg_18], rdi
0x18005d236  push    r12
0x18005d238  push    r14
0x18005d23a  push    r15
0x18005d23c  sub     rsp, 300h
0x18005d243  mov     rax, cs:__security_cookie
0x18005d24a  xor     rax, rsp
0x18005d24d  mov     [rsp+318h+var_28], rax
0x18005d255  mov     rsi, rdx
0x18005d258  mov     r15, rcx
0x18005d25b  xor     edx, edx; Val
0x18005d25d  mov     r8d, 238h; Size
0x18005d263  lea     rcx, [rsp+318h+instance]; void *
0x18005d26b  call    memset_0
0x18005d270  mov     [rsp+318h+var_298], 0
0x18005d27b  mov     [rsp+318h+var_294], 0
0x18005d283  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18005d28a  mov     [rsp+318h+var_2C8], rax
0x18005d28f  lea     rax, [rsp+318h+var_298]
0x18005d297  mov     [rsp+318h+var_2C0], rax
0x18005d29c  lea     rax, aMdmPolicyConfi_129; "MDM_Policy_Config01_Audit02"
0x18005d2a3  mov     [rsp+318h+var_2B8], rax
0x18005d2a8  lea     rcx, [rsp+318h+var_298]
0x18005d2b0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18005d2b5  mov     eax, cs:dword_180380B68
0x18005d2bb  cmp     eax, 5
0x18005d2be  jbe     short loc_18005D334
0x18005d2c0  mov     rdx, 200000000000h
0x18005d2ca  lea     rcx, dword_180380B68
0x18005d2d1  call    _tlgKeywordOn
0x18005d2d6  test    al, al
0x18005d2d8  jz      short loc_18005D334
0x18005d2da  cmp     [rsp+318h+var_294], 0
0x18005d2e2  jz      short loc_18005D316
0x18005d2e4  cmp     [rsp+318h+var_280], 0
0x18005d2ec  jnz     short loc_18005D30C
0x18005d2ee  cmp     [rsp+318h+var_27C], 0
0x18005d2f6  jnz     short loc_18005D30C
0x18005d2f8  cmp     [rsp+318h+var_278], 0
0x18005d300  jnz     short loc_18005D30C
0x18005d302  cmp     [rsp+318h+var_274], 0
0x18005d30a  jz      short loc_18005D316
0x18005d30c  lea     r9, [rsp+318h+var_280]
0x18005d314  jmp     short loc_18005D319
0x18005d316  xor     r9d, r9d
0x18005d319  lea     r8, [rsp+318h+var_290]
0x18005d321  lea     rdx, word_180361242
0x18005d328  lea     rcx, dword_180380B68
0x18005d32f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18005d334  cmp     byte ptr [rsi+48h], 0
0x18005d338  jz      loc_18005E3AA
0x18005d33e  mov     [rsp+318h+var_2D0], 0
0x18005d343  cmp     byte ptr [rsi+58h], 0
0x18005d347  jz      loc_18005E3AA
0x18005d34d  mov     r9, [rsi+40h]; unsigned __int16 *
0x18005d351  mov     r8, [rsi+50h]; unsigned __int16 *
0x18005d355  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18005d35c  lea     rcx, [rsp+318h+var_2C8]; this
0x18005d361  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18005d366  nop
0x18005d367  mov     [rsp+318h+var_2D8], 0
0x18005d370  lea     rax, [rsp+318h+var_2D8]
0x18005d375  mov     [rsp+318h+var_2E8], rax
0x18005d37a  mov     [rsp+318h+var_2F0], 4
0x18005d382  mov     [rsp+318h+var_2F8], 3Dh ; '='
0x18005d38a  lea     r9, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Audit02_NodeList
0x18005d391  mov     r8, [rsi+40h]
0x18005d395  mov     rdx, [rsi+50h]
0x18005d399  mov     rcx, r15
0x18005d39c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18005d3a1  mov     edi, eax
0x18005d3a3  test    eax, eax
0x18005d3a5  jz      short loc_18005D3AC
0x18005d3a7  jmp     loc_18005E3AF
0x18005d3ac  lea     rax, [rsp+318h+var_2D8]
0x18005d3b1  mov     [rsp+318h+var_2A8], rax
0x18005d3b6  mov     r12d, 1
0x18005d3bc  mov     [rsp+318h+var_2A0], r12b
0x18005d3c1  mov     r14, [rsp+318h+var_2D8]
0x18005d3c6  test    r14, r14
0x18005d3c9  jnz     short loc_18005D3D3
0x18005d3cb  mov     edi, r12d
0x18005d3ce  jmp     loc_18005E3AF
0x18005d3d3  mov     r9d, 3Dh ; '='; unsigned int
0x18005d3d9  lea     r8, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18005d3e0  mov     rdx, rsi; struct _MI_Instance *
0x18005d3e3  mov     rcx, r14; this
0x18005d3e6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18005d3eb  lea     r8, [rsi+60h]; void *
0x18005d3ef  cmp     [r8+4], r12b
0x18005d3f3  jnz     short loc_18005D428
0x18005d3f5  lea     rdx, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x18005d3fc  mov     rcx, r14; this
0x18005d3ff  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d404  mov     edi, eax
0x18005d406  test    eax, eax
0x18005d408  jz      short loc_18005D428
0x18005d40a  mov     rcx, [rsp+318h+var_2D8]
0x18005d40f  test    rcx, rcx
0x18005d412  jz      short loc_18005D423
0x18005d414  mov     rax, [rcx]
0x18005d417  mov     edx, r12d
0x18005d41a  mov     rax, [rax]
0x18005d41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d422  nop
0x18005d423  jmp     loc_18005E3AF
0x18005d428  lea     r8, [rsi+68h]; void *
0x18005d42c  cmp     [r8+4], r12b
0x18005d430  jnz     short loc_18005D465
0x18005d432  lea     rdx, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x18005d439  mov     rcx, r14; this
0x18005d43c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d441  mov     edi, eax
0x18005d443  test    eax, eax
0x18005d445  jz      short loc_18005D465
0x18005d447  mov     rcx, [rsp+318h+var_2D8]
0x18005d44c  test    rcx, rcx
0x18005d44f  jz      short loc_18005D460
0x18005d451  mov     rax, [rcx]
0x18005d454  mov     edx, r12d
0x18005d457  mov     rax, [rax]
0x18005d45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d45f  nop
0x18005d460  jmp     loc_18005E3AF
0x18005d465  lea     r8, [rsi+70h]; void *
0x18005d469  cmp     [r8+4], r12b
0x18005d46d  jnz     short loc_18005D4A2
0x18005d46f  lea     rdx, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x18005d476  mov     rcx, r14; this
0x18005d479  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d47e  mov     edi, eax
0x18005d480  test    eax, eax
0x18005d482  jz      short loc_18005D4A2
0x18005d484  mov     rcx, [rsp+318h+var_2D8]
0x18005d489  test    rcx, rcx
0x18005d48c  jz      short loc_18005D49D
0x18005d48e  mov     rax, [rcx]
0x18005d491  mov     edx, r12d
0x18005d494  mov     rax, [rax]
0x18005d497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d49c  nop
0x18005d49d  jmp     loc_18005E3AF
0x18005d4a2  lea     r8, [rsi+78h]; void *
0x18005d4a6  cmp     [r8+4], r12b
0x18005d4aa  jnz     short loc_18005D4DF
0x18005d4ac  lea     rdx, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x18005d4b3  mov     rcx, r14; this
0x18005d4b6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d4bb  mov     edi, eax
0x18005d4bd  test    eax, eax
0x18005d4bf  jz      short loc_18005D4DF
0x18005d4c1  mov     rcx, [rsp+318h+var_2D8]
0x18005d4c6  test    rcx, rcx
0x18005d4c9  jz      short loc_18005D4DA
0x18005d4cb  mov     rax, [rcx]
0x18005d4ce  mov     edx, r12d
0x18005d4d1  mov     rax, [rax]
0x18005d4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d4d9  nop
0x18005d4da  jmp     loc_18005E3AF
0x18005d4df  lea     r8, [rsi+80h]; void *
0x18005d4e6  cmp     [r8+4], r12b
0x18005d4ea  jnz     short loc_18005D51F
0x18005d4ec  lea     rdx, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x18005d4f3  mov     rcx, r14; this
0x18005d4f6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d4fb  mov     edi, eax
0x18005d4fd  test    eax, eax
0x18005d4ff  jz      short loc_18005D51F
0x18005d501  mov     rcx, [rsp+318h+var_2D8]
0x18005d506  test    rcx, rcx
0x18005d509  jz      short loc_18005D51A
0x18005d50b  mov     rax, [rcx]
0x18005d50e  mov     edx, r12d
0x18005d511  mov     rax, [rax]
0x18005d514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d519  nop
0x18005d51a  jmp     loc_18005E3AF
0x18005d51f  lea     r8, [rsi+88h]; void *
0x18005d526  cmp     [r8+4], r12b
0x18005d52a  jnz     short loc_18005D55F
0x18005d52c  lea     rdx, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x18005d533  mov     rcx, r14; this
0x18005d536  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d53b  mov     edi, eax
0x18005d53d  test    eax, eax
0x18005d53f  jz      short loc_18005D55F
0x18005d541  mov     rcx, [rsp+318h+var_2D8]
0x18005d546  test    rcx, rcx
0x18005d549  jz      short loc_18005D55A
0x18005d54b  mov     rax, [rcx]
0x18005d54e  mov     edx, r12d
0x18005d551  mov     rax, [rax]
0x18005d554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d559  nop
0x18005d55a  jmp     loc_18005E3AF
0x18005d55f  lea     r8, [rsi+90h]; void *
0x18005d566  cmp     [r8+4], r12b
0x18005d56a  jnz     short loc_18005D59F
0x18005d56c  lea     rdx, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x18005d573  mov     rcx, r14; this
0x18005d576  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d57b  mov     edi, eax
0x18005d57d  test    eax, eax
0x18005d57f  jz      short loc_18005D59F
0x18005d581  mov     rcx, [rsp+318h+var_2D8]
0x18005d586  test    rcx, rcx
0x18005d589  jz      short loc_18005D59A
0x18005d58b  mov     rax, [rcx]
0x18005d58e  mov     edx, r12d
0x18005d591  mov     rax, [rax]
0x18005d594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d599  nop
0x18005d59a  jmp     loc_18005E3AF
0x18005d59f  lea     r8, [rsi+98h]; void *
0x18005d5a6  cmp     [r8+4], r12b
0x18005d5aa  jnz     short loc_18005D5DF
0x18005d5ac  lea     rdx, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x18005d5b3  mov     rcx, r14; this
0x18005d5b6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d5bb  mov     edi, eax
0x18005d5bd  test    eax, eax
0x18005d5bf  jz      short loc_18005D5DF
0x18005d5c1  mov     rcx, [rsp+318h+var_2D8]
0x18005d5c6  test    rcx, rcx
0x18005d5c9  jz      short loc_18005D5DA
0x18005d5cb  mov     rax, [rcx]
0x18005d5ce  mov     edx, r12d
0x18005d5d1  mov     rax, [rax]
0x18005d5d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d5d9  nop
0x18005d5da  jmp     loc_18005E3AF
0x18005d5df  lea     r8, [rsi+0A0h]; void *
0x18005d5e6  cmp     [r8+4], r12b
0x18005d5ea  jnz     short loc_18005D61F
0x18005d5ec  lea     rdx, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x18005d5f3  mov     rcx, r14; this
0x18005d5f6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d5fb  mov     edi, eax
0x18005d5fd  test    eax, eax
0x18005d5ff  jz      short loc_18005D61F
0x18005d601  mov     rcx, [rsp+318h+var_2D8]
0x18005d606  test    rcx, rcx
0x18005d609  jz      short loc_18005D61A
0x18005d60b  mov     rax, [rcx]
0x18005d60e  mov     edx, r12d
0x18005d611  mov     rax, [rax]
0x18005d614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d619  nop
0x18005d61a  jmp     loc_18005E3AF
0x18005d61f  lea     r8, [rsi+0A8h]; void *
0x18005d626  cmp     [r8+4], r12b
0x18005d62a  jnz     short loc_18005D65F
0x18005d62c  lea     rdx, aAccountlogonlo_4; "AccountLogonLogoff_AuditLogoff"
0x18005d633  mov     rcx, r14; this
0x18005d636  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d63b  mov     edi, eax
0x18005d63d  test    eax, eax
0x18005d63f  jz      short loc_18005D65F
0x18005d641  mov     rcx, [rsp+318h+var_2D8]
0x18005d646  test    rcx, rcx
0x18005d649  jz      short loc_18005D65A
0x18005d64b  mov     rax, [rcx]
0x18005d64e  mov     edx, r12d
0x18005d651  mov     rax, [rax]
0x18005d654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d659  nop
0x18005d65a  jmp     loc_18005E3AF
0x18005d65f  lea     r8, [rsi+0B0h]; void *
0x18005d666  cmp     [r8+4], r12b
0x18005d66a  jnz     short loc_18005D69F
0x18005d66c  lea     rdx, aAccountlogonlo_8; "AccountLogonLogoff_AuditLogon"
0x18005d673  mov     rcx, r14; this
0x18005d676  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d67b  mov     edi, eax
0x18005d67d  test    eax, eax
0x18005d67f  jz      short loc_18005D69F
0x18005d681  mov     rcx, [rsp+318h+var_2D8]
0x18005d686  test    rcx, rcx
0x18005d689  jz      short loc_18005D69A
0x18005d68b  mov     rax, [rcx]
0x18005d68e  mov     edx, r12d
0x18005d691  mov     rax, [rax]
0x18005d694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d699  nop
0x18005d69a  jmp     loc_18005E3AF
0x18005d69f  lea     r8, [rsi+0B8h]; void *
0x18005d6a6  cmp     [r8+4], r12b
0x18005d6aa  jnz     short loc_18005D6DF
0x18005d6ac  lea     rdx, aAccountlogonlo; "AccountLogonLogoff_AuditNetworkPolicySe"...
0x18005d6b3  mov     rcx, r14; this
0x18005d6b6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005d6bb  mov     edi, eax
0x18005d6bd  test    eax, eax
0x18005d6bf  jz      short loc_18005D6DF
0x18005d6c1  mov     rcx, [rsp+318h+var_2D8]
0x18005d6c6  test    rcx, rcx
0x18005d6c9  jz      short loc_18005D6DA
0x18005d6cb  mov     rax, [rcx]
  ... truncated ...
```
