# MDM_Policy_Result01_Audit02_InvokeCreateInstance

- ea: `0x1801152dc`
- end: `0x1801164fb`
- name: `MDM_Policy_Result01_Audit02_InvokeCreateInstance`
- size: `4639`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801151e0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801152dc`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801154e2`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x18011551f`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x18011589c`: `AccountManagement_AuditComputerAccountManagement`
- `0x18011595c`: `AccountManagement_AuditSecurityGroupManagement`
- `0x180115b1c`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x180115b5c`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x180115b9c`: `DSAccess_AuditDirectoryServiceAccess`
- `0x180115bdc`: `DSAccess_AuditDirectoryServiceChanges`
- `0x180115c1c`: `DSAccess_AuditDirectoryServiceReplication`
- `0x180115c5c`: `ObjectAccess_AuditApplicationGenerated`
- `0x180115c9c`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x180115cdc`: `ObjectAccess_AuditCertificationServices`
- `0x180115d1c`: `ObjectAccess_AuditDetailedFileShare`
- `0x180115d5c`: `ObjectAccess_AuditFileShare`
- `0x180115d9c`: `ObjectAccess_AuditFileSystem`
- `0x180115ddc`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x180115e1c`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x180115e5c`: `ObjectAccess_AuditHandleManipulation`
- `0x180115e9c`: `ObjectAccess_AuditKernelObject`
- `0x180115edc`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x180115f1c`: `ObjectAccess_AuditRegistry`
- `0x180115f5c`: `ObjectAccess_AuditRemovableStorage`
- `0x180115f9c`: `ObjectAccess_AuditSAM`
- `0x18011615c`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x18011619c`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x1801161dc`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x18011629c`: `System_AuditSecurityStateChange`
- `0x1801162dc`: `System_AuditSecuritySystemExtension`
- `0x180115405`: `CreateInstanceStart`
- `0x180116462`: `CreateInstanceEnd`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Audit02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v10[2] = "MDM_Policy_Result01_Audit02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18033514F,
      v14,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
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
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_Audit02_NodeList,
                 0x3Du,
                 4,
                 &v8);
    if ( !inserted )
    {
      v10[4] = &v8;
      v11 = 1;
      v6 = v8;
      if ( v8 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v8,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Audit02_NodeList,
          0x3Du);
        if ( BYTE4(a2[1].reserved[0]) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                           v6,
                           L"AccountLogon_AuditCredentialValidation",
                           (LONG *)a2[1].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditKerberosAuthenticationService",
                                (LONG *)&a2[1].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditKerberosServiceTicketOperations",
                                (LONG *)&a2[1].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditOtherAccountLogonEvents",
                                (LONG *)&a2[1].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditAccountLockout",
                                (LONG *)&a2[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditGroupMembership",
                                (LONG *)&a2[2].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecExtendedMode",
                                (LONG *)&a2[2].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecMainMode",
                                (LONG *)&a2[2].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecQuickMode",
                                (LONG *)a2[2].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditLogoff",
                                (LONG *)&a2[2].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditLogon",
                                (LONG *)&a2[2].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditNetworkPolicyServer",
                                (LONG *)&a2[2].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                                (LONG *)&a2[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditSpecialLogon",
                                (LONG *)&a2[3].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditUserDeviceClaims",
                                (LONG *)&a2[3].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditApplicationGroupManagement",
                                (LONG *)&a2[3].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditComputerAccountManagement",
                                (LONG *)a2[3].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditDistributionGroupManagement",
                                (LONG *)&a2[3].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditOtherAccountManagementEvents",
                                (LONG *)&a2[3].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditSecurityGroupManagement",
                                (LONG *)&a2[3].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditUserAccountManagement",
                                (LONG *)&a2[4])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditDPAPIActivity",
                                (LONG *)&a2[4].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditPNPActivity",
                                (LONG *)&a2[4].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditProcessCreation",
                                (LONG *)&a2[4].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditProcessTermination",
                                (LONG *)a2[4].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditRPCEvents",
                                (LONG *)&a2[4].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditTokenRightAdjusted",
                                (LONG *)&a2[4].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDetailedDirectoryServiceReplication",
                                (LONG *)&a2[4].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceAccess",
                                (LONG *)&a2[5])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceChanges",
                                (LONG *)&a2[5].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceReplication",
                                (LONG *)&a2[5].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditApplicationGenerated",
                                (LONG *)&a2[5].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditCentralAccessPolicyStaging",
                                (LONG *)a2[5].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditCertificationServices",
                                (LONG *)&a2[5].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditDetailedFileShare",
                                (LONG *)&a2[5].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFileShare",
                                (LONG *)&a2[5].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFileSystem",
                                (LONG *)&a2[6])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFilteringPlatformConnection",
                                (LONG *)&a2[6].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                                (LONG *)&a2[6].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditHandleManipulation",
                                (LONG *)&a2[6].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditKernelObject",
                                (LONG *)a2[6].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditOtherObjectAccessEvents",
                                (LONG *)&a2[6].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditRegistry",
                                (LONG *)&a2[6].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditRemovableStorage",
                                (LONG *)&a2[6].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditSAM", (LONG *)&a2[7])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditAuthenticationPolicyChange",
                                (LONG *)&a2[7].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditAuthorizationPolicyChange",
                                (LONG *)&a2[7].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditFilteringPlatformPolicyChange",
                                (LONG *)&a2[7].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                                (LONG *)a2[7].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditOtherPolicyChangeEvents",
                                (LONG *)&a2[7].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditPolicyChange",
                                (LONG *)&a2[7].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                                (LONG *)&a2[7].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                                (LONG *)&a2[8])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditSensitivePrivilegeUse",
                                (LONG *)&a2[8].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditIPsecDriver",
                                (LONG *)&a2[8].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditOtherSystemEvents",
                                (LONG *)&a2[8].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSecurityStateChange",
                                (LONG *)a2[8].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSecuritySystemExtension",
                                (LONG *)&a2[8].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSystemIntegrity",
                                (LONG *)&a2[8].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else
        {
          inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( inserted )
          {
            if ( v8 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
          }
          else
          {
            inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
            if ( inserted )
            {
              if ( v8 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
            }
            else
            {
              inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Audit02_rtti, &instance);
              if ( inserted )
              {
                if ( v8 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
              }
              else
              {
                v9 = 1;
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
                MI_Instance_Destruct((MI_Instance *)self);
                if ( v8 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
                MI_Instance_Destruct(&instance);
              }
            }
          }
        }
      }
      else
      {
        inserted = 1;
      }
    }
  }
  else
  {
    inserted = 4;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_1803554C2,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return inserted;
}

```

## disassembly

```asm
0x1801152dc  mov     [rsp+arg_10], rsi
0x1801152e1  mov     [rsp+arg_18], rdi
0x1801152e6  push    r12
0x1801152e8  push    r14
0x1801152ea  push    r15
0x1801152ec  sub     rsp, 300h
0x1801152f3  mov     rax, cs:__security_cookie
0x1801152fa  xor     rax, rsp
0x1801152fd  mov     [rsp+318h+var_28], rax
0x180115305  mov     rsi, rdx
0x180115308  mov     r15, rcx
0x18011530b  xor     edx, edx; Val
0x18011530d  mov     r8d, 238h; Size
0x180115313  lea     rcx, [rsp+318h+instance]; void *
0x18011531b  call    memset_0
0x180115320  mov     [rsp+318h+var_298], 0
0x18011532b  mov     [rsp+318h+var_294], 0
0x180115333  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18011533a  mov     [rsp+318h+var_2C8], rax
0x18011533f  lea     rax, [rsp+318h+var_298]
0x180115347  mov     [rsp+318h+var_2C0], rax
0x18011534c  lea     rax, aMdmPolicyResul_95; "MDM_Policy_Result01_Audit02"
0x180115353  mov     [rsp+318h+var_2B8], rax
0x180115358  lea     rcx, [rsp+318h+var_298]
0x180115360  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180115365  mov     eax, cs:dword_180380B68
0x18011536b  cmp     eax, 5
0x18011536e  jbe     short loc_1801153E4
0x180115370  mov     rdx, 200000000000h
0x18011537a  lea     rcx, dword_180380B68
0x180115381  call    _tlgKeywordOn
0x180115386  test    al, al
0x180115388  jz      short loc_1801153E4
0x18011538a  cmp     [rsp+318h+var_294], 0
0x180115392  jz      short loc_1801153C6
0x180115394  cmp     [rsp+318h+var_280], 0
0x18011539c  jnz     short loc_1801153BC
0x18011539e  cmp     [rsp+318h+var_27C], 0
0x1801153a6  jnz     short loc_1801153BC
0x1801153a8  cmp     [rsp+318h+var_278], 0
0x1801153b0  jnz     short loc_1801153BC
0x1801153b2  cmp     [rsp+318h+var_274], 0
0x1801153ba  jz      short loc_1801153C6
0x1801153bc  lea     r9, [rsp+318h+var_280]
0x1801153c4  jmp     short loc_1801153C9
0x1801153c6  xor     r9d, r9d
0x1801153c9  lea     r8, [rsp+318h+var_290]
0x1801153d1  lea     rdx, byte_18033514F
0x1801153d8  lea     rcx, dword_180380B68
0x1801153df  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801153e4  cmp     byte ptr [rsi+48h], 0
0x1801153e8  jz      loc_18011645A
0x1801153ee  mov     [rsp+318h+var_2D0], 0
0x1801153f3  cmp     byte ptr [rsi+58h], 0
0x1801153f7  jz      loc_18011645A
0x1801153fd  mov     r9, [rsi+40h]; unsigned __int16 *
0x180115401  mov     r8, [rsi+50h]; unsigned __int16 *
0x180115405  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18011540c  lea     rcx, [rsp+318h+var_2C8]; this
0x180115411  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180115416  nop
0x180115417  mov     [rsp+318h+var_2D8], 0
0x180115420  lea     rax, [rsp+318h+var_2D8]
0x180115425  mov     [rsp+318h+var_2E8], rax
0x18011542a  mov     [rsp+318h+var_2F0], 4
0x180115432  mov     [rsp+318h+var_2F8], 3Dh ; '='
0x18011543a  lea     r9, ?MDM_Policy_Result01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Audit02_NodeList
0x180115441  mov     r8, [rsi+40h]
0x180115445  mov     rdx, [rsi+50h]
0x180115449  mov     rcx, r15
0x18011544c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180115451  mov     edi, eax
0x180115453  test    eax, eax
0x180115455  jz      short loc_18011545C
0x180115457  jmp     loc_18011645F
0x18011545c  lea     rax, [rsp+318h+var_2D8]
0x180115461  mov     [rsp+318h+var_2A8], rax
0x180115466  mov     r12d, 1
0x18011546c  mov     [rsp+318h+var_2A0], r12b
0x180115471  mov     r14, [rsp+318h+var_2D8]
0x180115476  test    r14, r14
0x180115479  jnz     short loc_180115483
0x18011547b  mov     edi, r12d
0x18011547e  jmp     loc_18011645F
0x180115483  mov     r9d, 3Dh ; '='; unsigned int
0x180115489  lea     r8, ?MDM_Policy_Result01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180115490  mov     rdx, rsi; struct _MI_Instance *
0x180115493  mov     rcx, r14; this
0x180115496  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18011549b  lea     r8, [rsi+60h]; void *
0x18011549f  cmp     [r8+4], r12b
0x1801154a3  jnz     short loc_1801154D8
0x1801154a5  lea     rdx, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x1801154ac  mov     rcx, r14; this
0x1801154af  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801154b4  mov     edi, eax
0x1801154b6  test    eax, eax
0x1801154b8  jz      short loc_1801154D8
0x1801154ba  mov     rcx, [rsp+318h+var_2D8]
0x1801154bf  test    rcx, rcx
0x1801154c2  jz      short loc_1801154D3
0x1801154c4  mov     rax, [rcx]
0x1801154c7  mov     edx, r12d
0x1801154ca  mov     rax, [rax]
0x1801154cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801154d2  nop
0x1801154d3  jmp     loc_18011645F
0x1801154d8  lea     r8, [rsi+68h]; void *
0x1801154dc  cmp     [r8+4], r12b
0x1801154e0  jnz     short loc_180115515
0x1801154e2  lea     rdx, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x1801154e9  mov     rcx, r14; this
0x1801154ec  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801154f1  mov     edi, eax
0x1801154f3  test    eax, eax
0x1801154f5  jz      short loc_180115515
0x1801154f7  mov     rcx, [rsp+318h+var_2D8]
0x1801154fc  test    rcx, rcx
0x1801154ff  jz      short loc_180115510
0x180115501  mov     rax, [rcx]
0x180115504  mov     edx, r12d
0x180115507  mov     rax, [rax]
0x18011550a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011550f  nop
0x180115510  jmp     loc_18011645F
0x180115515  lea     r8, [rsi+70h]; void *
0x180115519  cmp     [r8+4], r12b
0x18011551d  jnz     short loc_180115552
0x18011551f  lea     rdx, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x180115526  mov     rcx, r14; this
0x180115529  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011552e  mov     edi, eax
0x180115530  test    eax, eax
0x180115532  jz      short loc_180115552
0x180115534  mov     rcx, [rsp+318h+var_2D8]
0x180115539  test    rcx, rcx
0x18011553c  jz      short loc_18011554D
0x18011553e  mov     rax, [rcx]
0x180115541  mov     edx, r12d
0x180115544  mov     rax, [rax]
0x180115547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011554c  nop
0x18011554d  jmp     loc_18011645F
0x180115552  lea     r8, [rsi+78h]; void *
0x180115556  cmp     [r8+4], r12b
0x18011555a  jnz     short loc_18011558F
0x18011555c  lea     rdx, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x180115563  mov     rcx, r14; this
0x180115566  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011556b  mov     edi, eax
0x18011556d  test    eax, eax
0x18011556f  jz      short loc_18011558F
0x180115571  mov     rcx, [rsp+318h+var_2D8]
0x180115576  test    rcx, rcx
0x180115579  jz      short loc_18011558A
0x18011557b  mov     rax, [rcx]
0x18011557e  mov     edx, r12d
0x180115581  mov     rax, [rax]
0x180115584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115589  nop
0x18011558a  jmp     loc_18011645F
0x18011558f  lea     r8, [rsi+80h]; void *
0x180115596  cmp     [r8+4], r12b
0x18011559a  jnz     short loc_1801155CF
0x18011559c  lea     rdx, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x1801155a3  mov     rcx, r14; this
0x1801155a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801155ab  mov     edi, eax
0x1801155ad  test    eax, eax
0x1801155af  jz      short loc_1801155CF
0x1801155b1  mov     rcx, [rsp+318h+var_2D8]
0x1801155b6  test    rcx, rcx
0x1801155b9  jz      short loc_1801155CA
0x1801155bb  mov     rax, [rcx]
0x1801155be  mov     edx, r12d
0x1801155c1  mov     rax, [rax]
0x1801155c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801155c9  nop
0x1801155ca  jmp     loc_18011645F
0x1801155cf  lea     r8, [rsi+88h]; void *
0x1801155d6  cmp     [r8+4], r12b
0x1801155da  jnz     short loc_18011560F
0x1801155dc  lea     rdx, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x1801155e3  mov     rcx, r14; this
0x1801155e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801155eb  mov     edi, eax
0x1801155ed  test    eax, eax
0x1801155ef  jz      short loc_18011560F
0x1801155f1  mov     rcx, [rsp+318h+var_2D8]
0x1801155f6  test    rcx, rcx
0x1801155f9  jz      short loc_18011560A
0x1801155fb  mov     rax, [rcx]
0x1801155fe  mov     edx, r12d
0x180115601  mov     rax, [rax]
0x180115604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115609  nop
0x18011560a  jmp     loc_18011645F
0x18011560f  lea     r8, [rsi+90h]; void *
0x180115616  cmp     [r8+4], r12b
0x18011561a  jnz     short loc_18011564F
0x18011561c  lea     rdx, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x180115623  mov     rcx, r14; this
0x180115626  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011562b  mov     edi, eax
0x18011562d  test    eax, eax
0x18011562f  jz      short loc_18011564F
0x180115631  mov     rcx, [rsp+318h+var_2D8]
0x180115636  test    rcx, rcx
0x180115639  jz      short loc_18011564A
0x18011563b  mov     rax, [rcx]
0x18011563e  mov     edx, r12d
0x180115641  mov     rax, [rax]
0x180115644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115649  nop
0x18011564a  jmp     loc_18011645F
0x18011564f  lea     r8, [rsi+98h]; void *
0x180115656  cmp     [r8+4], r12b
0x18011565a  jnz     short loc_18011568F
0x18011565c  lea     rdx, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x180115663  mov     rcx, r14; this
0x180115666  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011566b  mov     edi, eax
0x18011566d  test    eax, eax
0x18011566f  jz      short loc_18011568F
0x180115671  mov     rcx, [rsp+318h+var_2D8]
0x180115676  test    rcx, rcx
0x180115679  jz      short loc_18011568A
0x18011567b  mov     rax, [rcx]
0x18011567e  mov     edx, r12d
0x180115681  mov     rax, [rax]
0x180115684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115689  nop
0x18011568a  jmp     loc_18011645F
0x18011568f  lea     r8, [rsi+0A0h]; void *
0x180115696  cmp     [r8+4], r12b
0x18011569a  jnz     short loc_1801156CF
0x18011569c  lea     rdx, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x1801156a3  mov     rcx, r14; this
0x1801156a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801156ab  mov     edi, eax
0x1801156ad  test    eax, eax
0x1801156af  jz      short loc_1801156CF
0x1801156b1  mov     rcx, [rsp+318h+var_2D8]
0x1801156b6  test    rcx, rcx
0x1801156b9  jz      short loc_1801156CA
0x1801156bb  mov     rax, [rcx]
0x1801156be  mov     edx, r12d
0x1801156c1  mov     rax, [rax]
0x1801156c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801156c9  nop
0x1801156ca  jmp     loc_18011645F
0x1801156cf  lea     r8, [rsi+0A8h]; void *
0x1801156d6  cmp     [r8+4], r12b
0x1801156da  jnz     short loc_18011570F
0x1801156dc  lea     rdx, aAccountlogonlo_4; "AccountLogonLogoff_AuditLogoff"
0x1801156e3  mov     rcx, r14; this
0x1801156e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801156eb  mov     edi, eax
0x1801156ed  test    eax, eax
0x1801156ef  jz      short loc_18011570F
0x1801156f1  mov     rcx, [rsp+318h+var_2D8]
0x1801156f6  test    rcx, rcx
0x1801156f9  jz      short loc_18011570A
0x1801156fb  mov     rax, [rcx]
0x1801156fe  mov     edx, r12d
0x180115701  mov     rax, [rax]
0x180115704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115709  nop
0x18011570a  jmp     loc_18011645F
0x18011570f  lea     r8, [rsi+0B0h]; void *
0x180115716  cmp     [r8+4], r12b
0x18011571a  jnz     short loc_18011574F
0x18011571c  lea     rdx, aAccountlogonlo_8; "AccountLogonLogoff_AuditLogon"
0x180115723  mov     rcx, r14; this
0x180115726  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011572b  mov     edi, eax
0x18011572d  test    eax, eax
0x18011572f  jz      short loc_18011574F
0x180115731  mov     rcx, [rsp+318h+var_2D8]
0x180115736  test    rcx, rcx
0x180115739  jz      short loc_18011574A
0x18011573b  mov     rax, [rcx]
0x18011573e  mov     edx, r12d
0x180115741  mov     rax, [rax]
0x180115744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115749  nop
0x18011574a  jmp     loc_18011645F
0x18011574f  lea     r8, [rsi+0B8h]; void *
0x180115756  cmp     [r8+4], r12b
0x18011575a  jnz     short loc_18011578F
0x18011575c  lea     rdx, aAccountlogonlo; "AccountLogonLogoff_AuditNetworkPolicySe"...
0x180115763  mov     rcx, r14; this
0x180115766  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011576b  mov     edi, eax
0x18011576d  test    eax, eax
0x18011576f  jz      short loc_18011578F
0x180115771  mov     rcx, [rsp+318h+var_2D8]
0x180115776  test    rcx, rcx
0x180115779  jz      short loc_18011578A
0x18011577b  mov     rax, [rcx]
  ... truncated ...
```
