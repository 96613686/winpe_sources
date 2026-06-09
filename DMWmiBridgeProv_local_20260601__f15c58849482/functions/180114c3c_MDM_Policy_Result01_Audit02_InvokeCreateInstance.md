# MDM_Policy_Result01_Audit02_InvokeCreateInstance

- ea: `0x180114c3c`
- end: `0x180115e5c`
- name: `MDM_Policy_Result01_Audit02_InvokeCreateInstance`
- size: `4640`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180114b80`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180114c3c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x180114e42`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x180114e7f`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x1801151fc`: `AccountManagement_AuditComputerAccountManagement`
- `0x1801152bc`: `AccountManagement_AuditSecurityGroupManagement`
- `0x18011547c`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x1801154bc`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x1801154fc`: `DSAccess_AuditDirectoryServiceAccess`
- `0x18011553c`: `DSAccess_AuditDirectoryServiceChanges`
- `0x18011557c`: `DSAccess_AuditDirectoryServiceReplication`
- `0x1801155bc`: `ObjectAccess_AuditApplicationGenerated`
- `0x1801155fc`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x18011563c`: `ObjectAccess_AuditCertificationServices`
- `0x18011567c`: `ObjectAccess_AuditDetailedFileShare`
- `0x1801156bc`: `ObjectAccess_AuditFileShare`
- `0x1801156fc`: `ObjectAccess_AuditFileSystem`
- `0x18011573c`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x18011577c`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x1801157bc`: `ObjectAccess_AuditHandleManipulation`
- `0x1801157fc`: `ObjectAccess_AuditKernelObject`
- `0x18011583c`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x18011587c`: `ObjectAccess_AuditRegistry`
- `0x1801158bc`: `ObjectAccess_AuditRemovableStorage`
- `0x1801158fc`: `ObjectAccess_AuditSAM`
- `0x180115abc`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x180115afc`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x180115b3c`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x180115bfc`: `System_AuditSecurityStateChange`
- `0x180115c3c`: `System_AuditSecuritySystemExtension`
- `0x180114d65`: `CreateInstanceStart`
- `0x180115dc2`: `CreateInstanceEnd`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Audit02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
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
    inserted = (unsigned int)CreateRequestHandlerInstance(
                               self,
                               a2[1].serverName,
                               a2[1].ft,
                               &MDM_Policy_Result01_Audit02_NodeList,
                               61,
                               4,
                               &v8);
    if ( inserted == MI_RESULT_OK )
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
                           a2[1].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditKerberosAuthenticationService",
                                &a2[1].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditKerberosServiceTicketOperations",
                                &a2[1].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditOtherAccountLogonEvents",
                                &a2[1].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditAccountLockout",
                                &a2[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditGroupMembership",
                                &a2[2].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecExtendedMode",
                                &a2[2].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecMainMode",
                                &a2[2].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecQuickMode",
                                a2[2].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditLogoff",
                                &a2[2].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditLogon",
                                &a2[2].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditNetworkPolicyServer",
                                &a2[2].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                                &a2[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditSpecialLogon",
                                &a2[3].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditUserDeviceClaims",
                                &a2[3].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditApplicationGroupManagement",
                                &a2[3].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditComputerAccountManagement",
                                a2[3].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditDistributionGroupManagement",
                                &a2[3].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditOtherAccountManagementEvents",
                                &a2[3].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditSecurityGroupManagement",
                                &a2[3].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditUserAccountManagement",
                                &a2[4])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditDPAPIActivity",
                                &a2[4].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditPNPActivity",
                                &a2[4].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditProcessCreation",
                                &a2[4].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditProcessTermination",
                                a2[4].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditRPCEvents",
                                &a2[4].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditTokenRightAdjusted",
                                &a2[4].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDetailedDirectoryServiceReplication",
                                &a2[4].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceAccess",
                                &a2[5])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceChanges",
                                &a2[5].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceReplication",
                                &a2[5].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditApplicationGenerated",
                                &a2[5].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditCentralAccessPolicyStaging",
                                a2[5].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditCertificationServices",
                                &a2[5].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditDetailedFileShare",
                                &a2[5].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFileShare",
                                &a2[5].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditFileSystem", &a2[6])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFilteringPlatformConnection",
                                &a2[6].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                                &a2[6].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditHandleManipulation",
                                &a2[6].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditKernelObject",
                                a2[6].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditOtherObjectAccessEvents",
                                &a2[6].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditRegistry",
                                &a2[6].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditRemovableStorage",
                                &a2[6].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditSAM", &a2[7])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditAuthenticationPolicyChange",
                                &a2[7].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditAuthorizationPolicyChange",
                                &a2[7].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditFilteringPlatformPolicyChange",
                                &a2[7].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                                a2[7].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditOtherPolicyChangeEvents",
                                &a2[7].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditPolicyChange",
                                &a2[7].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                                &a2[7].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                                &a2[8])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditSensitivePrivilegeUse",
                                &a2[8].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"System_AuditIPsecDriver", &a2[8].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditOtherSystemEvents",
                                &a2[8].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSecurityStateChange",
                                a2[8].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSecuritySystemExtension",
                                &a2[8].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSystemIntegrity",
                                &a2[8].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else
        {
          inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( inserted )
          {
            if ( v8 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
          }
          else
          {
            inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
        inserted = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
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
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180114c3c  mov     [rsp+arg_10], rsi
0x180114c41  mov     [rsp+arg_18], rdi
0x180114c46  push    r12
0x180114c48  push    r14
0x180114c4a  push    r15
0x180114c4c  sub     rsp, 300h
0x180114c53  mov     rax, cs:__security_cookie
0x180114c5a  xor     rax, rsp
0x180114c5d  mov     [rsp+318h+var_28], rax
0x180114c65  mov     rsi, rdx
0x180114c68  mov     r15, rcx
0x180114c6b  xor     edx, edx; Val
0x180114c6d  mov     r8d, 238h; Size
0x180114c73  lea     rcx, [rsp+318h+instance]; void *
0x180114c7b  call    memset_0
0x180114c80  mov     [rsp+318h+var_298], 0
0x180114c8b  mov     [rsp+318h+var_294], 0
0x180114c93  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180114c9a  mov     [rsp+318h+var_2C8], rax
0x180114c9f  lea     rax, [rsp+318h+var_298]
0x180114ca7  mov     [rsp+318h+var_2C0], rax
0x180114cac  lea     rax, aMdmPolicyResul_95; "MDM_Policy_Result01_Audit02"
0x180114cb3  mov     [rsp+318h+var_2B8], rax
0x180114cb8  lea     rcx, [rsp+318h+var_298]
0x180114cc0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180114cc5  mov     eax, cs:dword_180380B68
0x180114ccb  cmp     eax, 5
0x180114cce  jbe     short loc_180114D44
0x180114cd0  mov     rdx, 200000000000h
0x180114cda  lea     rcx, dword_180380B68
0x180114ce1  call    _tlgKeywordOn
0x180114ce6  test    al, al
0x180114ce8  jz      short loc_180114D44
0x180114cea  cmp     [rsp+318h+var_294], 0
0x180114cf2  jz      short loc_180114D26
0x180114cf4  cmp     [rsp+318h+var_280], 0
0x180114cfc  jnz     short loc_180114D1C
0x180114cfe  cmp     [rsp+318h+var_27C], 0
0x180114d06  jnz     short loc_180114D1C
0x180114d08  cmp     [rsp+318h+var_278], 0
0x180114d10  jnz     short loc_180114D1C
0x180114d12  cmp     [rsp+318h+var_274], 0
0x180114d1a  jz      short loc_180114D26
0x180114d1c  lea     r9, [rsp+318h+var_280]
0x180114d24  jmp     short loc_180114D29
0x180114d26  xor     r9d, r9d
0x180114d29  lea     r8, [rsp+318h+var_290]
0x180114d31  lea     rdx, byte_18033514F
0x180114d38  lea     rcx, dword_180380B68
0x180114d3f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180114d44  cmp     byte ptr [rsi+48h], 0
0x180114d48  jz      loc_180115DBA
0x180114d4e  mov     [rsp+318h+var_2D0], 0
0x180114d53  cmp     byte ptr [rsi+58h], 0
0x180114d57  jz      loc_180115DBA
0x180114d5d  mov     r9, [rsi+40h]; unsigned __int16 *
0x180114d61  mov     r8, [rsi+50h]; unsigned __int16 *
0x180114d65  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x180114d6c  lea     rcx, [rsp+318h+var_2C8]; this
0x180114d71  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180114d76  nop
0x180114d77  mov     [rsp+318h+var_2D8], 0
0x180114d80  lea     rax, [rsp+318h+var_2D8]
0x180114d85  mov     [rsp+318h+var_2E8], rax
0x180114d8a  mov     [rsp+318h+var_2F0], 4
0x180114d92  mov     [rsp+318h+var_2F8], 3Dh ; '='
0x180114d9a  lea     r9, ?MDM_Policy_Result01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Audit02_NodeList
0x180114da1  mov     r8, [rsi+40h]
0x180114da5  mov     rdx, [rsi+50h]
0x180114da9  mov     rcx, r15
0x180114dac  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180114db1  mov     edi, eax
0x180114db3  test    eax, eax
0x180114db5  jz      short loc_180114DBC
0x180114db7  jmp     loc_180115DBF
0x180114dbc  lea     rax, [rsp+318h+var_2D8]
0x180114dc1  mov     [rsp+318h+var_2A8], rax
0x180114dc6  mov     r12d, 1
0x180114dcc  mov     [rsp+318h+var_2A0], r12b
0x180114dd1  mov     r14, [rsp+318h+var_2D8]
0x180114dd6  test    r14, r14
0x180114dd9  jnz     short loc_180114DE3
0x180114ddb  mov     edi, r12d
0x180114dde  jmp     loc_180115DBF
0x180114de3  mov     r9d, 3Dh ; '='; unsigned int
0x180114de9  lea     r8, ?MDM_Policy_Result01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180114df0  mov     rdx, rsi; struct _MI_Instance *
0x180114df3  mov     rcx, r14; this
0x180114df6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180114dfb  lea     r8, [rsi+60h]; void *
0x180114dff  cmp     [r8+4], r12b
0x180114e03  jnz     short loc_180114E38
0x180114e05  lea     rdx, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x180114e0c  mov     rcx, r14; this
0x180114e0f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180114e14  mov     edi, eax
0x180114e16  test    eax, eax
0x180114e18  jz      short loc_180114E38
0x180114e1a  mov     rcx, [rsp+318h+var_2D8]
0x180114e1f  test    rcx, rcx
0x180114e22  jz      short loc_180114E33
0x180114e24  mov     rax, [rcx]
0x180114e27  mov     edx, r12d
0x180114e2a  mov     rax, [rax]
0x180114e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114e32  nop
0x180114e33  jmp     loc_180115DBF
0x180114e38  lea     r8, [rsi+68h]; void *
0x180114e3c  cmp     [r8+4], r12b
0x180114e40  jnz     short loc_180114E75
0x180114e42  lea     rdx, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x180114e49  mov     rcx, r14; this
0x180114e4c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180114e51  mov     edi, eax
0x180114e53  test    eax, eax
0x180114e55  jz      short loc_180114E75
0x180114e57  mov     rcx, [rsp+318h+var_2D8]
0x180114e5c  test    rcx, rcx
0x180114e5f  jz      short loc_180114E70
0x180114e61  mov     rax, [rcx]
0x180114e64  mov     edx, r12d
0x180114e67  mov     rax, [rax]
0x180114e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114e6f  nop
0x180114e70  jmp     loc_180115DBF
0x180114e75  lea     r8, [rsi+70h]; void *
0x180114e79  cmp     [r8+4], r12b
0x180114e7d  jnz     short loc_180114EB2
0x180114e7f  lea     rdx, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x180114e86  mov     rcx, r14; this
0x180114e89  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180114e8e  mov     edi, eax
0x180114e90  test    eax, eax
0x180114e92  jz      short loc_180114EB2
0x180114e94  mov     rcx, [rsp+318h+var_2D8]
0x180114e99  test    rcx, rcx
0x180114e9c  jz      short loc_180114EAD
0x180114e9e  mov     rax, [rcx]
0x180114ea1  mov     edx, r12d
0x180114ea4  mov     rax, [rax]
0x180114ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114eac  nop
0x180114ead  jmp     loc_180115DBF
0x180114eb2  lea     r8, [rsi+78h]; void *
0x180114eb6  cmp     [r8+4], r12b
0x180114eba  jnz     short loc_180114EEF
0x180114ebc  lea     rdx, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x180114ec3  mov     rcx, r14; this
0x180114ec6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180114ecb  mov     edi, eax
0x180114ecd  test    eax, eax
0x180114ecf  jz      short loc_180114EEF
0x180114ed1  mov     rcx, [rsp+318h+var_2D8]
0x180114ed6  test    rcx, rcx
0x180114ed9  jz      short loc_180114EEA
0x180114edb  mov     rax, [rcx]
0x180114ede  mov     edx, r12d
0x180114ee1  mov     rax, [rax]
0x180114ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114ee9  nop
0x180114eea  jmp     loc_180115DBF
0x180114eef  lea     r8, [rsi+80h]; void *
0x180114ef6  cmp     [r8+4], r12b
0x180114efa  jnz     short loc_180114F2F
0x180114efc  lea     rdx, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x180114f03  mov     rcx, r14; this
0x180114f06  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180114f0b  mov     edi, eax
0x180114f0d  test    eax, eax
0x180114f0f  jz      short loc_180114F2F
0x180114f11  mov     rcx, [rsp+318h+var_2D8]
0x180114f16  test    rcx, rcx
0x180114f19  jz      short loc_180114F2A
0x180114f1b  mov     rax, [rcx]
0x180114f1e  mov     edx, r12d
0x180114f21  mov     rax, [rax]
0x180114f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114f29  nop
0x180114f2a  jmp     loc_180115DBF
0x180114f2f  lea     r8, [rsi+88h]; void *
0x180114f36  cmp     [r8+4], r12b
0x180114f3a  jnz     short loc_180114F6F
0x180114f3c  lea     rdx, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x180114f43  mov     rcx, r14; this
0x180114f46  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180114f4b  mov     edi, eax
0x180114f4d  test    eax, eax
0x180114f4f  jz      short loc_180114F6F
0x180114f51  mov     rcx, [rsp+318h+var_2D8]
0x180114f56  test    rcx, rcx
0x180114f59  jz      short loc_180114F6A
0x180114f5b  mov     rax, [rcx]
0x180114f5e  mov     edx, r12d
0x180114f61  mov     rax, [rax]
0x180114f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114f69  nop
0x180114f6a  jmp     loc_180115DBF
0x180114f6f  lea     r8, [rsi+90h]; void *
0x180114f76  cmp     [r8+4], r12b
0x180114f7a  jnz     short loc_180114FAF
0x180114f7c  lea     rdx, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x180114f83  mov     rcx, r14; this
0x180114f86  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180114f8b  mov     edi, eax
0x180114f8d  test    eax, eax
0x180114f8f  jz      short loc_180114FAF
0x180114f91  mov     rcx, [rsp+318h+var_2D8]
0x180114f96  test    rcx, rcx
0x180114f99  jz      short loc_180114FAA
0x180114f9b  mov     rax, [rcx]
0x180114f9e  mov     edx, r12d
0x180114fa1  mov     rax, [rax]
0x180114fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114fa9  nop
0x180114faa  jmp     loc_180115DBF
0x180114faf  lea     r8, [rsi+98h]; void *
0x180114fb6  cmp     [r8+4], r12b
0x180114fba  jnz     short loc_180114FEF
0x180114fbc  lea     rdx, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x180114fc3  mov     rcx, r14; this
0x180114fc6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180114fcb  mov     edi, eax
0x180114fcd  test    eax, eax
0x180114fcf  jz      short loc_180114FEF
0x180114fd1  mov     rcx, [rsp+318h+var_2D8]
0x180114fd6  test    rcx, rcx
0x180114fd9  jz      short loc_180114FEA
0x180114fdb  mov     rax, [rcx]
0x180114fde  mov     edx, r12d
0x180114fe1  mov     rax, [rax]
0x180114fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114fe9  nop
0x180114fea  jmp     loc_180115DBF
0x180114fef  lea     r8, [rsi+0A0h]; void *
0x180114ff6  cmp     [r8+4], r12b
0x180114ffa  jnz     short loc_18011502F
0x180114ffc  lea     rdx, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x180115003  mov     rcx, r14; this
0x180115006  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011500b  mov     edi, eax
0x18011500d  test    eax, eax
0x18011500f  jz      short loc_18011502F
0x180115011  mov     rcx, [rsp+318h+var_2D8]
0x180115016  test    rcx, rcx
0x180115019  jz      short loc_18011502A
0x18011501b  mov     rax, [rcx]
0x18011501e  mov     edx, r12d
0x180115021  mov     rax, [rax]
0x180115024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115029  nop
0x18011502a  jmp     loc_180115DBF
0x18011502f  lea     r8, [rsi+0A8h]; void *
0x180115036  cmp     [r8+4], r12b
0x18011503a  jnz     short loc_18011506F
0x18011503c  lea     rdx, aAccountlogonlo_4; "AccountLogonLogoff_AuditLogoff"
0x180115043  mov     rcx, r14; this
0x180115046  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011504b  mov     edi, eax
0x18011504d  test    eax, eax
0x18011504f  jz      short loc_18011506F
0x180115051  mov     rcx, [rsp+318h+var_2D8]
0x180115056  test    rcx, rcx
0x180115059  jz      short loc_18011506A
0x18011505b  mov     rax, [rcx]
0x18011505e  mov     edx, r12d
0x180115061  mov     rax, [rax]
0x180115064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115069  nop
0x18011506a  jmp     loc_180115DBF
0x18011506f  lea     r8, [rsi+0B0h]; void *
0x180115076  cmp     [r8+4], r12b
0x18011507a  jnz     short loc_1801150AF
0x18011507c  lea     rdx, aAccountlogonlo_8; "AccountLogonLogoff_AuditLogon"
0x180115083  mov     rcx, r14; this
0x180115086  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011508b  mov     edi, eax
0x18011508d  test    eax, eax
0x18011508f  jz      short loc_1801150AF
0x180115091  mov     rcx, [rsp+318h+var_2D8]
0x180115096  test    rcx, rcx
0x180115099  jz      short loc_1801150AA
0x18011509b  mov     rax, [rcx]
0x18011509e  mov     edx, r12d
0x1801150a1  mov     rax, [rax]
0x1801150a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801150a9  nop
0x1801150aa  jmp     loc_180115DBF
0x1801150af  lea     r8, [rsi+0B8h]; void *
0x1801150b6  cmp     [r8+4], r12b
0x1801150ba  jnz     short loc_1801150EF
0x1801150bc  lea     rdx, aAccountlogonlo; "AccountLogonLogoff_AuditNetworkPolicySe"...
0x1801150c3  mov     rcx, r14; this
0x1801150c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801150cb  mov     edi, eax
0x1801150cd  test    eax, eax
0x1801150cf  jz      short loc_1801150EF
0x1801150d1  mov     rcx, [rsp+318h+var_2D8]
0x1801150d6  test    rcx, rcx
0x1801150d9  jz      short loc_1801150EA
0x1801150db  mov     rax, [rcx]
  ... truncated ...
```
