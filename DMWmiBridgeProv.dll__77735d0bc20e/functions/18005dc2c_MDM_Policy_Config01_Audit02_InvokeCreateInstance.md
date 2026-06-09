# MDM_Policy_Config01_Audit02_InvokeCreateInstance

- ea: `0x18005dc2c`
- end: `0x18005ee4b`
- name: `MDM_Policy_Config01_Audit02_InvokeCreateInstance`
- size: `4639`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005db30`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18005dc2c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x18005de32`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x18005de6f`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x18005e1ec`: `AccountManagement_AuditComputerAccountManagement`
- `0x18005e2ac`: `AccountManagement_AuditSecurityGroupManagement`
- `0x18005e46c`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x18005e4ac`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x18005e4ec`: `DSAccess_AuditDirectoryServiceAccess`
- `0x18005e52c`: `DSAccess_AuditDirectoryServiceChanges`
- `0x18005e56c`: `DSAccess_AuditDirectoryServiceReplication`
- `0x18005e5ac`: `ObjectAccess_AuditApplicationGenerated`
- `0x18005e5ec`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x18005e62c`: `ObjectAccess_AuditCertificationServices`
- `0x18005e66c`: `ObjectAccess_AuditDetailedFileShare`
- `0x18005e6ac`: `ObjectAccess_AuditFileShare`
- `0x18005e6ec`: `ObjectAccess_AuditFileSystem`
- `0x18005e72c`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x18005e76c`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x18005e7ac`: `ObjectAccess_AuditHandleManipulation`
- `0x18005e7ec`: `ObjectAccess_AuditKernelObject`
- `0x18005e82c`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x18005e86c`: `ObjectAccess_AuditRegistry`
- `0x18005e8ac`: `ObjectAccess_AuditRemovableStorage`
- `0x18005e8ec`: `ObjectAccess_AuditSAM`
- `0x18005eaac`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x18005eaec`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x18005eb2c`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x18005ebec`: `System_AuditSecurityStateChange`
- `0x18005ec2c`: `System_AuditSecuritySystemExtension`
- `0x18005dd55`: `CreateInstanceStart`
- `0x18005edb2`: `CreateInstanceEnd`
- `0x18005dc9c`: `MDM_Policy_Config01_Audit02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Audit02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
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
    inserted = 4;
    goto LABEL_265;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = CreateRequestHandlerInstance(
               (__int64)self,
               (wchar_t *)a2[1].serverName,
               (const unsigned __int16 *)a2[1].ft,
               (struct WmiNodeInfo *)&MDM_Policy_Config01_Audit02_NodeList,
               0x3Du,
               4,
               &v8);
  if ( !inserted )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = 1;
      goto LABEL_265;
    }
    WmiRequestHandler::SetRequestMIInstance(v8, a2, (struct WmiNodeInfo *)&MDM_Policy_Config01_Audit02_NodeList, 0x3Du);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogon_AuditCredentialValidation",
                   (LONG *)a2[1].reserved);
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
                   (LONG *)&a2[1].reserved[1]);
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
                   (LONG *)&a2[1].reserved[2]);
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
                   (LONG *)&a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccountLogonLogoff_AuditAccountLockout", (LONG *)&a2[2]);
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
                   (LONG *)&a2[2].classDecl);
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
                   (LONG *)&a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogonLogoff_AuditIPsecMainMode",
                   (LONG *)&a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogonLogoff_AuditIPsecQuickMode",
                   (LONG *)a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogonLogoff_AuditLogoff",
                   (LONG *)&a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogonLogoff_AuditLogon",
                   (LONG *)&a2[2].reserved[2]);
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
                   (LONG *)&a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                   (LONG *)&a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountLogonLogoff_AuditSpecialLogon",
                   (LONG *)&a2[3].classDecl);
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
                   (LONG *)&a2[3].serverName);
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
                   (LONG *)&a2[3].nameSpace);
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
                   (LONG *)a2[3].reserved);
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
                   (LONG *)&a2[3].reserved[1]);
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
                   (LONG *)&a2[3].reserved[2]);
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
                   (LONG *)&a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccountManagement_AuditUserAccountManagement",
                   (LONG *)&a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DetailedTracking_AuditDPAPIActivity",
                   (LONG *)&a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DetailedTracking_AuditPNPActivity",
                   (LONG *)&a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DetailedTracking_AuditProcessCreation",
                   (LONG *)&a2[4].nameSpace);
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
                   (LONG *)a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DetailedTracking_AuditRPCEvents",
                   (LONG *)&a2[4].reserved[1]);
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
                   (LONG *)&a2[4].reserved[2]);
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
                   (LONG *)&a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DSAccess_AuditDirectoryServiceAccess", (LONG *)&a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DSAccess_AuditDirectoryServiceChanges",
                   (LONG *)&a2[5].classDecl);
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
                   (LONG *)&a2[5].serverName);
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
                   (LONG *)&a2[5].nameSpace);
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
                   (LONG *)a2[5].reserved);
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
                   (LONG *)&a2[5].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ObjectAccess_AuditDetailedFileShare",
                   (LONG *)&a2[5].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[5].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditFileShare", (LONG *)&a2[5].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditFileSystem", (LONG *)&a2[6]);
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
                   (LONG *)&a2[6].classDecl);
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
                   (LONG *)&a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ObjectAccess_AuditHandleManipulation",
                   (LONG *)&a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditKernelObject", (LONG *)a2[6].reserved);
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
                   (LONG *)&a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditRegistry", (LONG *)&a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ObjectAccess_AuditRemovableStorage",
                   (LONG *)&a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[7].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditSAM", (LONG *)&a2[7]);
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
                   (LONG *)&a2[7].classDecl);
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
                   (LONG *)&a2[7].serverName);
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
                   (LONG *)&a2[7].nameSpace);
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
                   (LONG *)a2[7].reserved);
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
                   (LONG *)&a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PolicyChange_AuditPolicyChange",
                   (LONG *)&a2[7].reserved[2]);
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
                   (LONG *)&a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                   (LONG *)&a2[8]);
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
                   (LONG *)&a2[8].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"System_AuditIPsecDriver", (LONG *)&a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"System_AuditOtherSystemEvents", (LONG *)&a2[8].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"System_AuditSecurityStateChange", (LONG *)a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"System_AuditSecuritySystemExtension",
                   (LONG *)&a2[8].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    if ( BYTE4(a2[8].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"System_AuditSystemIntegrity", (LONG *)&a2[8].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_265;
        goto LABEL_260;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_265;
      goto LABEL_260;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return inserted;
}

```

## disassembly

```asm
0x18005dc2c  mov     [rsp+arg_10], rsi
0x18005dc31  mov     [rsp+arg_18], rdi
0x18005dc36  push    r12
0x18005dc38  push    r14
0x18005dc3a  push    r15
0x18005dc3c  sub     rsp, 300h
0x18005dc43  mov     rax, cs:__security_cookie
0x18005dc4a  xor     rax, rsp
0x18005dc4d  mov     [rsp+318h+var_28], rax
0x18005dc55  mov     rsi, rdx
0x18005dc58  mov     r15, rcx
0x18005dc5b  xor     edx, edx; Val
0x18005dc5d  mov     r8d, 238h; Size
0x18005dc63  lea     rcx, [rsp+318h+instance]; void *
0x18005dc6b  call    memset_0
0x18005dc70  mov     [rsp+318h+var_298], 0
0x18005dc7b  mov     [rsp+318h+var_294], 0
0x18005dc83  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18005dc8a  mov     [rsp+318h+var_2C8], rax
0x18005dc8f  lea     rax, [rsp+318h+var_298]
0x18005dc97  mov     [rsp+318h+var_2C0], rax
0x18005dc9c  lea     rax, aMdmPolicyConfi_129; "MDM_Policy_Config01_Audit02"
0x18005dca3  mov     [rsp+318h+var_2B8], rax
0x18005dca8  lea     rcx, [rsp+318h+var_298]
0x18005dcb0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18005dcb5  mov     eax, cs:dword_180380B68
0x18005dcbb  cmp     eax, 5
0x18005dcbe  jbe     short loc_18005DD34
0x18005dcc0  mov     rdx, 200000000000h
0x18005dcca  lea     rcx, dword_180380B68
0x18005dcd1  call    _tlgKeywordOn
0x18005dcd6  test    al, al
0x18005dcd8  jz      short loc_18005DD34
0x18005dcda  cmp     [rsp+318h+var_294], 0
0x18005dce2  jz      short loc_18005DD16
0x18005dce4  cmp     [rsp+318h+var_280], 0
0x18005dcec  jnz     short loc_18005DD0C
0x18005dcee  cmp     [rsp+318h+var_27C], 0
0x18005dcf6  jnz     short loc_18005DD0C
0x18005dcf8  cmp     [rsp+318h+var_278], 0
0x18005dd00  jnz     short loc_18005DD0C
0x18005dd02  cmp     [rsp+318h+var_274], 0
0x18005dd0a  jz      short loc_18005DD16
0x18005dd0c  lea     r9, [rsp+318h+var_280]
0x18005dd14  jmp     short loc_18005DD19
0x18005dd16  xor     r9d, r9d
0x18005dd19  lea     r8, [rsp+318h+var_290]
0x18005dd21  lea     rdx, word_180361242
0x18005dd28  lea     rcx, dword_180380B68
0x18005dd2f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18005dd34  cmp     byte ptr [rsi+48h], 0
0x18005dd38  jz      loc_18005EDAA
0x18005dd3e  mov     [rsp+318h+var_2D0], 0
0x18005dd43  cmp     byte ptr [rsi+58h], 0
0x18005dd47  jz      loc_18005EDAA
0x18005dd4d  mov     r9, [rsi+40h]; unsigned __int16 *
0x18005dd51  mov     r8, [rsi+50h]; unsigned __int16 *
0x18005dd55  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18005dd5c  lea     rcx, [rsp+318h+var_2C8]; this
0x18005dd61  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18005dd66  nop
0x18005dd67  mov     [rsp+318h+var_2D8], 0
0x18005dd70  lea     rax, [rsp+318h+var_2D8]
0x18005dd75  mov     [rsp+318h+var_2E8], rax
0x18005dd7a  mov     [rsp+318h+var_2F0], 4
0x18005dd82  mov     [rsp+318h+var_2F8], 3Dh ; '='
0x18005dd8a  lea     r9, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Audit02_NodeList
0x18005dd91  mov     r8, [rsi+40h]
0x18005dd95  mov     rdx, [rsi+50h]
0x18005dd99  mov     rcx, r15
0x18005dd9c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18005dda1  mov     edi, eax
0x18005dda3  test    eax, eax
0x18005dda5  jz      short loc_18005DDAC
0x18005dda7  jmp     loc_18005EDAF
0x18005ddac  lea     rax, [rsp+318h+var_2D8]
0x18005ddb1  mov     [rsp+318h+var_2A8], rax
0x18005ddb6  mov     r12d, 1
0x18005ddbc  mov     [rsp+318h+var_2A0], r12b
0x18005ddc1  mov     r14, [rsp+318h+var_2D8]
0x18005ddc6  test    r14, r14
0x18005ddc9  jnz     short loc_18005DDD3
0x18005ddcb  mov     edi, r12d
0x18005ddce  jmp     loc_18005EDAF
0x18005ddd3  mov     r9d, 3Dh ; '='; unsigned int
0x18005ddd9  lea     r8, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18005dde0  mov     rdx, rsi; struct _MI_Instance *
0x18005dde3  mov     rcx, r14; this
0x18005dde6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18005ddeb  lea     r8, [rsi+60h]; void *
0x18005ddef  cmp     [r8+4], r12b
0x18005ddf3  jnz     short loc_18005DE28
0x18005ddf5  lea     rdx, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x18005ddfc  mov     rcx, r14; this
0x18005ddff  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005de04  mov     edi, eax
0x18005de06  test    eax, eax
0x18005de08  jz      short loc_18005DE28
0x18005de0a  mov     rcx, [rsp+318h+var_2D8]
0x18005de0f  test    rcx, rcx
0x18005de12  jz      short loc_18005DE23
0x18005de14  mov     rax, [rcx]
0x18005de17  mov     edx, r12d
0x18005de1a  mov     rax, [rax]
0x18005de1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de22  nop
0x18005de23  jmp     loc_18005EDAF
0x18005de28  lea     r8, [rsi+68h]; void *
0x18005de2c  cmp     [r8+4], r12b
0x18005de30  jnz     short loc_18005DE65
0x18005de32  lea     rdx, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x18005de39  mov     rcx, r14; this
0x18005de3c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005de41  mov     edi, eax
0x18005de43  test    eax, eax
0x18005de45  jz      short loc_18005DE65
0x18005de47  mov     rcx, [rsp+318h+var_2D8]
0x18005de4c  test    rcx, rcx
0x18005de4f  jz      short loc_18005DE60
0x18005de51  mov     rax, [rcx]
0x18005de54  mov     edx, r12d
0x18005de57  mov     rax, [rax]
0x18005de5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de5f  nop
0x18005de60  jmp     loc_18005EDAF
0x18005de65  lea     r8, [rsi+70h]; void *
0x18005de69  cmp     [r8+4], r12b
0x18005de6d  jnz     short loc_18005DEA2
0x18005de6f  lea     rdx, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x18005de76  mov     rcx, r14; this
0x18005de79  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005de7e  mov     edi, eax
0x18005de80  test    eax, eax
0x18005de82  jz      short loc_18005DEA2
0x18005de84  mov     rcx, [rsp+318h+var_2D8]
0x18005de89  test    rcx, rcx
0x18005de8c  jz      short loc_18005DE9D
0x18005de8e  mov     rax, [rcx]
0x18005de91  mov     edx, r12d
0x18005de94  mov     rax, [rax]
0x18005de97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de9c  nop
0x18005de9d  jmp     loc_18005EDAF
0x18005dea2  lea     r8, [rsi+78h]; void *
0x18005dea6  cmp     [r8+4], r12b
0x18005deaa  jnz     short loc_18005DEDF
0x18005deac  lea     rdx, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x18005deb3  mov     rcx, r14; this
0x18005deb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005debb  mov     edi, eax
0x18005debd  test    eax, eax
0x18005debf  jz      short loc_18005DEDF
0x18005dec1  mov     rcx, [rsp+318h+var_2D8]
0x18005dec6  test    rcx, rcx
0x18005dec9  jz      short loc_18005DEDA
0x18005decb  mov     rax, [rcx]
0x18005dece  mov     edx, r12d
0x18005ded1  mov     rax, [rax]
0x18005ded4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ded9  nop
0x18005deda  jmp     loc_18005EDAF
0x18005dedf  lea     r8, [rsi+80h]; void *
0x18005dee6  cmp     [r8+4], r12b
0x18005deea  jnz     short loc_18005DF1F
0x18005deec  lea     rdx, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x18005def3  mov     rcx, r14; this
0x18005def6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005defb  mov     edi, eax
0x18005defd  test    eax, eax
0x18005deff  jz      short loc_18005DF1F
0x18005df01  mov     rcx, [rsp+318h+var_2D8]
0x18005df06  test    rcx, rcx
0x18005df09  jz      short loc_18005DF1A
0x18005df0b  mov     rax, [rcx]
0x18005df0e  mov     edx, r12d
0x18005df11  mov     rax, [rax]
0x18005df14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df19  nop
0x18005df1a  jmp     loc_18005EDAF
0x18005df1f  lea     r8, [rsi+88h]; void *
0x18005df26  cmp     [r8+4], r12b
0x18005df2a  jnz     short loc_18005DF5F
0x18005df2c  lea     rdx, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x18005df33  mov     rcx, r14; this
0x18005df36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005df3b  mov     edi, eax
0x18005df3d  test    eax, eax
0x18005df3f  jz      short loc_18005DF5F
0x18005df41  mov     rcx, [rsp+318h+var_2D8]
0x18005df46  test    rcx, rcx
0x18005df49  jz      short loc_18005DF5A
0x18005df4b  mov     rax, [rcx]
0x18005df4e  mov     edx, r12d
0x18005df51  mov     rax, [rax]
0x18005df54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df59  nop
0x18005df5a  jmp     loc_18005EDAF
0x18005df5f  lea     r8, [rsi+90h]; void *
0x18005df66  cmp     [r8+4], r12b
0x18005df6a  jnz     short loc_18005DF9F
0x18005df6c  lea     rdx, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x18005df73  mov     rcx, r14; this
0x18005df76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005df7b  mov     edi, eax
0x18005df7d  test    eax, eax
0x18005df7f  jz      short loc_18005DF9F
0x18005df81  mov     rcx, [rsp+318h+var_2D8]
0x18005df86  test    rcx, rcx
0x18005df89  jz      short loc_18005DF9A
0x18005df8b  mov     rax, [rcx]
0x18005df8e  mov     edx, r12d
0x18005df91  mov     rax, [rax]
0x18005df94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df99  nop
0x18005df9a  jmp     loc_18005EDAF
0x18005df9f  lea     r8, [rsi+98h]; void *
0x18005dfa6  cmp     [r8+4], r12b
0x18005dfaa  jnz     short loc_18005DFDF
0x18005dfac  lea     rdx, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x18005dfb3  mov     rcx, r14; this
0x18005dfb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005dfbb  mov     edi, eax
0x18005dfbd  test    eax, eax
0x18005dfbf  jz      short loc_18005DFDF
0x18005dfc1  mov     rcx, [rsp+318h+var_2D8]
0x18005dfc6  test    rcx, rcx
0x18005dfc9  jz      short loc_18005DFDA
0x18005dfcb  mov     rax, [rcx]
0x18005dfce  mov     edx, r12d
0x18005dfd1  mov     rax, [rax]
0x18005dfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dfd9  nop
0x18005dfda  jmp     loc_18005EDAF
0x18005dfdf  lea     r8, [rsi+0A0h]; void *
0x18005dfe6  cmp     [r8+4], r12b
0x18005dfea  jnz     short loc_18005E01F
0x18005dfec  lea     rdx, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x18005dff3  mov     rcx, r14; this
0x18005dff6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005dffb  mov     edi, eax
0x18005dffd  test    eax, eax
0x18005dfff  jz      short loc_18005E01F
0x18005e001  mov     rcx, [rsp+318h+var_2D8]
0x18005e006  test    rcx, rcx
0x18005e009  jz      short loc_18005E01A
0x18005e00b  mov     rax, [rcx]
0x18005e00e  mov     edx, r12d
0x18005e011  mov     rax, [rax]
0x18005e014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e019  nop
0x18005e01a  jmp     loc_18005EDAF
0x18005e01f  lea     r8, [rsi+0A8h]; void *
0x18005e026  cmp     [r8+4], r12b
0x18005e02a  jnz     short loc_18005E05F
0x18005e02c  lea     rdx, aAccountlogonlo_4; "AccountLogonLogoff_AuditLogoff"
0x18005e033  mov     rcx, r14; this
0x18005e036  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005e03b  mov     edi, eax
0x18005e03d  test    eax, eax
0x18005e03f  jz      short loc_18005E05F
0x18005e041  mov     rcx, [rsp+318h+var_2D8]
0x18005e046  test    rcx, rcx
0x18005e049  jz      short loc_18005E05A
0x18005e04b  mov     rax, [rcx]
0x18005e04e  mov     edx, r12d
0x18005e051  mov     rax, [rax]
0x18005e054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e059  nop
0x18005e05a  jmp     loc_18005EDAF
0x18005e05f  lea     r8, [rsi+0B0h]; void *
0x18005e066  cmp     [r8+4], r12b
0x18005e06a  jnz     short loc_18005E09F
0x18005e06c  lea     rdx, aAccountlogonlo_8; "AccountLogonLogoff_AuditLogon"
0x18005e073  mov     rcx, r14; this
0x18005e076  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005e07b  mov     edi, eax
0x18005e07d  test    eax, eax
0x18005e07f  jz      short loc_18005E09F
0x18005e081  mov     rcx, [rsp+318h+var_2D8]
0x18005e086  test    rcx, rcx
0x18005e089  jz      short loc_18005E09A
0x18005e08b  mov     rax, [rcx]
0x18005e08e  mov     edx, r12d
0x18005e091  mov     rax, [rax]
0x18005e094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e099  nop
0x18005e09a  jmp     loc_18005EDAF
0x18005e09f  lea     r8, [rsi+0B8h]; void *
0x18005e0a6  cmp     [r8+4], r12b
0x18005e0aa  jnz     short loc_18005E0DF
0x18005e0ac  lea     rdx, aAccountlogonlo; "AccountLogonLogoff_AuditNetworkPolicySe"...
0x18005e0b3  mov     rcx, r14; this
0x18005e0b6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18005e0bb  mov     edi, eax
0x18005e0bd  test    eax, eax
0x18005e0bf  jz      short loc_18005E0DF
0x18005e0c1  mov     rcx, [rsp+318h+var_2D8]
0x18005e0c6  test    rcx, rcx
0x18005e0c9  jz      short loc_18005E0DA
0x18005e0cb  mov     rax, [rcx]
  ... truncated ...
```
