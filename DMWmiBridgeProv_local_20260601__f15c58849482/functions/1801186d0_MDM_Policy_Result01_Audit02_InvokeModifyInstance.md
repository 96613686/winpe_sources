# MDM_Policy_Result01_Audit02_InvokeModifyInstance

- ea: `0x1801186d0`
- end: `0x180119824`
- name: `MDM_Policy_Result01_Audit02_InvokeModifyInstance`
- size: `4436`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180119830`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1801186d0`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801188a4`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x1801188e1`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x180118c5e`: `AccountManagement_AuditComputerAccountManagement`
- `0x180118d1e`: `AccountManagement_AuditSecurityGroupManagement`
- `0x180118ede`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x180118f1e`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x180118f5e`: `DSAccess_AuditDirectoryServiceAccess`
- `0x180118f9e`: `DSAccess_AuditDirectoryServiceChanges`
- `0x180118fde`: `DSAccess_AuditDirectoryServiceReplication`
- `0x18011901e`: `ObjectAccess_AuditApplicationGenerated`
- `0x18011905e`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x18011909e`: `ObjectAccess_AuditCertificationServices`
- `0x1801190de`: `ObjectAccess_AuditDetailedFileShare`
- `0x18011911e`: `ObjectAccess_AuditFileShare`
- `0x18011915e`: `ObjectAccess_AuditFileSystem`
- `0x18011919e`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x1801191de`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x18011921e`: `ObjectAccess_AuditHandleManipulation`
- `0x18011925e`: `ObjectAccess_AuditKernelObject`
- `0x18011929e`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x1801192de`: `ObjectAccess_AuditRegistry`
- `0x18011931e`: `ObjectAccess_AuditRemovableStorage`
- `0x18011935e`: `ObjectAccess_AuditSAM`
- `0x18011951e`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x18011955e`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x18011959e`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x18011965e`: `System_AuditSecurityStateChange`
- `0x18011969e`: `System_AuditSecuritySystemExtension`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Audit02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v9[5]; // [rsp+48h] [rbp-80h] BYREF
  char v10; // [rsp+70h] [rbp-58h]
  int v11; // [rsp+78h] [rbp-50h] BYREF
  char v12; // [rsp+7Ch] [rbp-4Ch]
  _BYTE v13[16]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD v14[4]; // [rsp+90h] [rbp-38h] BYREF

  v11 = 0;
  v12 = 0;
  v9[0] = &TelemetryEventWriter::`vftable';
  v9[1] = &v11;
  v9[2] = "MDM_Policy_Result01_Audit02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v11);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v12 && (v14[0] || v14[1] || v14[2] || v14[3]) )
      v4 = v14;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_18036AC6E,
      v13,
      v4);
  }
  if ( *(_BYTE *)(a2 + 72) && *(_BYTE *)(a2 + 88) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v9,
      "ModifyInstanceStart",
      *(const unsigned __int16 **)(a2 + 80),
      *(const unsigned __int16 **)(a2 + 64));
    v8 = 0;
    inserted = (unsigned int)CreateRequestHandlerInstance(
                               a1,
                               *(_QWORD *)(a2 + 80),
                               *(_QWORD *)(a2 + 64),
                               &MDM_Policy_Result01_Audit02_NodeList,
                               61,
                               3,
                               &v8);
    if ( inserted == MI_RESULT_OK )
    {
      v9[4] = &v8;
      v10 = 1;
      v6 = v8;
      if ( v8 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v8,
          (const struct _MI_Instance *)a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Audit02_NodeList,
          0x3Du);
        if ( *(_BYTE *)(a2 + 100) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                           v6,
                           L"AccountLogon_AuditCredentialValidation",
                           (void *)(a2 + 96))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 108) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditKerberosAuthenticationService",
                                (void *)(a2 + 104))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 116) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditKerberosServiceTicketOperations",
                                (void *)(a2 + 112))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 124) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditOtherAccountLogonEvents",
                                (void *)(a2 + 120))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 132) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditAccountLockout",
                                (void *)(a2 + 128))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 140) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditGroupMembership",
                                (void *)(a2 + 136))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 148) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecExtendedMode",
                                (void *)(a2 + 144))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 156) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecMainMode",
                                (void *)(a2 + 152))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 164) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecQuickMode",
                                (void *)(a2 + 160))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 172) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditLogoff",
                                (void *)(a2 + 168))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 180) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditLogon",
                                (void *)(a2 + 176))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 188) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditNetworkPolicyServer",
                                (void *)(a2 + 184))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 196) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                                (void *)(a2 + 192))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 204) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditSpecialLogon",
                                (void *)(a2 + 200))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 212) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditUserDeviceClaims",
                                (void *)(a2 + 208))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 220) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditApplicationGroupManagement",
                                (void *)(a2 + 216))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 228) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditComputerAccountManagement",
                                (void *)(a2 + 224))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 236) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditDistributionGroupManagement",
                                (void *)(a2 + 232))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 244) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditOtherAccountManagementEvents",
                                (void *)(a2 + 240))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 252) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditSecurityGroupManagement",
                                (void *)(a2 + 248))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 260) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditUserAccountManagement",
                                (void *)(a2 + 256))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 268) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditDPAPIActivity",
                                (void *)(a2 + 264))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 276) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditPNPActivity",
                                (void *)(a2 + 272))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 284) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditProcessCreation",
                                (void *)(a2 + 280))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 292) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditProcessTermination",
                                (void *)(a2 + 288))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 300) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditRPCEvents",
                                (void *)(a2 + 296))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 308) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditTokenRightAdjusted",
                                (void *)(a2 + 304))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 316) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDetailedDirectoryServiceReplication",
                                (void *)(a2 + 312))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 324) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceAccess",
                                (void *)(a2 + 320))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 332) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceChanges",
                                (void *)(a2 + 328))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 340) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceReplication",
                                (void *)(a2 + 336))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 348) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditApplicationGenerated",
                                (void *)(a2 + 344))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 356) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditCentralAccessPolicyStaging",
                                (void *)(a2 + 352))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 364) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditCertificationServices",
                                (void *)(a2 + 360))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 372) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditDetailedFileShare",
                                (void *)(a2 + 368))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 380) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFileShare",
                                (void *)(a2 + 376))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 388) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFileSystem",
                                (void *)(a2 + 384))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 396) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFilteringPlatformConnection",
                                (void *)(a2 + 392))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 404) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                                (void *)(a2 + 400))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 412) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditHandleManipulation",
                                (void *)(a2 + 408))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 420) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditKernelObject",
                                (void *)(a2 + 416))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 428) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditOtherObjectAccessEvents",
                                (void *)(a2 + 424))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 436) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditRegistry",
                                (void *)(a2 + 432))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 444) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditRemovableStorage",
                                (void *)(a2 + 440))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 452) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditSAM", (void *)(a2 + 448))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 460) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditAuthenticationPolicyChange",
                                (void *)(a2 + 456))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 468) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditAuthorizationPolicyChange",
                                (void *)(a2 + 464))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 476) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditFilteringPlatformPolicyChange",
                                (void *)(a2 + 472))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 484) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                                (void *)(a2 + 480))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 492) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditOtherPolicyChangeEvents",
                                (void *)(a2 + 488))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 500) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditPolicyChange",
                                (void *)(a2 + 496))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 508) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                                (void *)(a2 + 504))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 516) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                                (void *)(a2 + 512))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 524) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditSensitivePrivilegeUse",
                                (void *)(a2 + 520))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 532) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditIPsecDriver",
                                (void *)(a2 + 528))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 540) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditOtherSystemEvents",
                                (void *)(a2 + 536))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 548) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSecurityStateChange",
                                (void *)(a2 + 544))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 556) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSecuritySystemExtension",
                                (void *)(a2 + 552))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 564) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSystemIntegrity",
                                (void *)(a2 + 560))) != MI_RESULT_OK )
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
            else if ( v8 )
            {
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
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
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v9, "ModifyInstanceEnd", inserted);
  v11 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180342602,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801186d0  mov     r11, rsp
0x1801186d3  mov     [r11+18h], rsi
0x1801186d7  push    rdi
0x1801186d8  push    r14
0x1801186da  push    r15
0x1801186dc  sub     rsp, 0B0h
0x1801186e3  mov     rax, cs:__security_cookie
0x1801186ea  xor     rax, rsp
0x1801186ed  mov     [rsp+0C8h+var_28], rax
0x1801186f5  mov     rsi, rdx
0x1801186f8  mov     rdi, rcx
0x1801186fb  mov     [rsp+0C8h+var_50], 0
0x180118703  mov     [rsp+0C8h+var_4C], 0
0x180118708  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18011870f  mov     [r11-80h], rax
0x180118713  lea     rax, [r11-50h]
0x180118717  mov     [r11-78h], rax
0x18011871b  lea     rax, aMdmPolicyResul_95; "MDM_Policy_Result01_Audit02"
0x180118722  mov     [r11-70h], rax
0x180118726  lea     rcx, [r11-50h]
0x18011872a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18011872f  mov     eax, cs:dword_180380B68
0x180118735  cmp     eax, 5
0x180118738  jbe     short loc_1801187AB
0x18011873a  mov     rdx, 200000000000h
0x180118744  lea     rcx, dword_180380B68
0x18011874b  call    _tlgKeywordOn
0x180118750  test    al, al
0x180118752  jz      short loc_1801187AB
0x180118754  cmp     [rsp+0C8h+var_4C], 0
0x180118759  jz      short loc_18011878D
0x18011875b  cmp     [rsp+0C8h+var_38], 0
0x180118763  jnz     short loc_180118783
0x180118765  cmp     [rsp+0C8h+var_34], 0
0x18011876d  jnz     short loc_180118783
0x18011876f  cmp     [rsp+0C8h+var_30], 0
0x180118777  jnz     short loc_180118783
0x180118779  cmp     [rsp+0C8h+var_2C], 0
0x180118781  jz      short loc_18011878D
0x180118783  lea     r9, [rsp+0C8h+var_38]
0x18011878b  jmp     short loc_180118790
0x18011878d  xor     r9d, r9d
0x180118790  lea     r8, [rsp+0C8h+var_48]
0x180118798  lea     rdx, word_18036AC6E
0x18011879f  lea     rcx, dword_180380B68
0x1801187a6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801187ab  cmp     byte ptr [rsi+48h], 0
0x1801187af  jz      loc_18011978D
0x1801187b5  cmp     byte ptr [rsi+58h], 0
0x1801187b9  jz      loc_18011978D
0x1801187bf  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801187c3  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801187c7  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801187ce  lea     rcx, [rsp+0C8h+var_80]; this
0x1801187d3  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801187d8  nop
0x1801187d9  mov     [rsp+0C8h+var_88], 0
0x1801187e2  lea     rax, [rsp+0C8h+var_88]
0x1801187e7  mov     [rsp+0C8h+var_98], rax
0x1801187ec  mov     [rsp+0C8h+var_A0], 3
0x1801187f4  mov     [rsp+0C8h+var_A8], 3Dh ; '='
0x1801187fc  lea     r9, ?MDM_Policy_Result01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Audit02_NodeList
0x180118803  mov     r8, [rsi+40h]
0x180118807  mov     rdx, [rsi+50h]
0x18011880b  mov     rcx, rdi
0x18011880e  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180118813  mov     edi, eax
0x180118815  test    eax, eax
0x180118817  jz      short loc_18011881E
0x180118819  jmp     loc_180119792
0x18011881e  lea     rax, [rsp+0C8h+var_88]
0x180118823  mov     [rsp+0C8h+var_60], rax
0x180118828  mov     r15d, 1
0x18011882e  mov     [rsp+0C8h+var_58], r15b
0x180118833  mov     r14, [rsp+0C8h+var_88]
0x180118838  test    r14, r14
0x18011883b  jnz     short loc_180118845
0x18011883d  mov     edi, r15d
0x180118840  jmp     loc_180119792
0x180118845  mov     r9d, 3Dh ; '='; unsigned int
0x18011884b  lea     r8, ?MDM_Policy_Result01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180118852  mov     rdx, rsi; struct _MI_Instance *
0x180118855  mov     rcx, r14; this
0x180118858  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18011885d  lea     r8, [rsi+60h]; void *
0x180118861  cmp     [r8+4], r15b
0x180118865  jnz     short loc_18011889A
0x180118867  lea     rdx, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x18011886e  mov     rcx, r14; this
0x180118871  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118876  mov     edi, eax
0x180118878  test    eax, eax
0x18011887a  jz      short loc_18011889A
0x18011887c  mov     rcx, [rsp+0C8h+var_88]
0x180118881  test    rcx, rcx
0x180118884  jz      short loc_180118895
0x180118886  mov     rax, [rcx]
0x180118889  mov     edx, r15d
0x18011888c  mov     rax, [rax]
0x18011888f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118894  nop
0x180118895  jmp     loc_180119792
0x18011889a  lea     r8, [rsi+68h]; void *
0x18011889e  cmp     [r8+4], r15b
0x1801188a2  jnz     short loc_1801188D7
0x1801188a4  lea     rdx, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x1801188ab  mov     rcx, r14; this
0x1801188ae  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801188b3  mov     edi, eax
0x1801188b5  test    eax, eax
0x1801188b7  jz      short loc_1801188D7
0x1801188b9  mov     rcx, [rsp+0C8h+var_88]
0x1801188be  test    rcx, rcx
0x1801188c1  jz      short loc_1801188D2
0x1801188c3  mov     rax, [rcx]
0x1801188c6  mov     edx, r15d
0x1801188c9  mov     rax, [rax]
0x1801188cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801188d1  nop
0x1801188d2  jmp     loc_180119792
0x1801188d7  lea     r8, [rsi+70h]; void *
0x1801188db  cmp     [r8+4], r15b
0x1801188df  jnz     short loc_180118914
0x1801188e1  lea     rdx, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x1801188e8  mov     rcx, r14; this
0x1801188eb  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801188f0  mov     edi, eax
0x1801188f2  test    eax, eax
0x1801188f4  jz      short loc_180118914
0x1801188f6  mov     rcx, [rsp+0C8h+var_88]
0x1801188fb  test    rcx, rcx
0x1801188fe  jz      short loc_18011890F
0x180118900  mov     rax, [rcx]
0x180118903  mov     edx, r15d
0x180118906  mov     rax, [rax]
0x180118909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011890e  nop
0x18011890f  jmp     loc_180119792
0x180118914  lea     r8, [rsi+78h]; void *
0x180118918  cmp     [r8+4], r15b
0x18011891c  jnz     short loc_180118951
0x18011891e  lea     rdx, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x180118925  mov     rcx, r14; this
0x180118928  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011892d  mov     edi, eax
0x18011892f  test    eax, eax
0x180118931  jz      short loc_180118951
0x180118933  mov     rcx, [rsp+0C8h+var_88]
0x180118938  test    rcx, rcx
0x18011893b  jz      short loc_18011894C
0x18011893d  mov     rax, [rcx]
0x180118940  mov     edx, r15d
0x180118943  mov     rax, [rax]
0x180118946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011894b  nop
0x18011894c  jmp     loc_180119792
0x180118951  lea     r8, [rsi+80h]; void *
0x180118958  cmp     [r8+4], r15b
0x18011895c  jnz     short loc_180118991
0x18011895e  lea     rdx, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x180118965  mov     rcx, r14; this
0x180118968  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18011896d  mov     edi, eax
0x18011896f  test    eax, eax
0x180118971  jz      short loc_180118991
0x180118973  mov     rcx, [rsp+0C8h+var_88]
0x180118978  test    rcx, rcx
0x18011897b  jz      short loc_18011898C
0x18011897d  mov     rax, [rcx]
0x180118980  mov     edx, r15d
0x180118983  mov     rax, [rax]
0x180118986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011898b  nop
0x18011898c  jmp     loc_180119792
0x180118991  lea     r8, [rsi+88h]; void *
0x180118998  cmp     [r8+4], r15b
0x18011899c  jnz     short loc_1801189D1
0x18011899e  lea     rdx, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x1801189a5  mov     rcx, r14; this
0x1801189a8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801189ad  mov     edi, eax
0x1801189af  test    eax, eax
0x1801189b1  jz      short loc_1801189D1
0x1801189b3  mov     rcx, [rsp+0C8h+var_88]
0x1801189b8  test    rcx, rcx
0x1801189bb  jz      short loc_1801189CC
0x1801189bd  mov     rax, [rcx]
0x1801189c0  mov     edx, r15d
0x1801189c3  mov     rax, [rax]
0x1801189c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801189cb  nop
0x1801189cc  jmp     loc_180119792
0x1801189d1  lea     r8, [rsi+90h]; void *
0x1801189d8  cmp     [r8+4], r15b
0x1801189dc  jnz     short loc_180118A11
0x1801189de  lea     rdx, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x1801189e5  mov     rcx, r14; this
0x1801189e8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801189ed  mov     edi, eax
0x1801189ef  test    eax, eax
0x1801189f1  jz      short loc_180118A11
0x1801189f3  mov     rcx, [rsp+0C8h+var_88]
0x1801189f8  test    rcx, rcx
0x1801189fb  jz      short loc_180118A0C
0x1801189fd  mov     rax, [rcx]
0x180118a00  mov     edx, r15d
0x180118a03  mov     rax, [rax]
0x180118a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118a0b  nop
0x180118a0c  jmp     loc_180119792
0x180118a11  lea     r8, [rsi+98h]; void *
0x180118a18  cmp     [r8+4], r15b
0x180118a1c  jnz     short loc_180118A51
0x180118a1e  lea     rdx, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x180118a25  mov     rcx, r14; this
0x180118a28  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118a2d  mov     edi, eax
0x180118a2f  test    eax, eax
0x180118a31  jz      short loc_180118A51
0x180118a33  mov     rcx, [rsp+0C8h+var_88]
0x180118a38  test    rcx, rcx
0x180118a3b  jz      short loc_180118A4C
0x180118a3d  mov     rax, [rcx]
0x180118a40  mov     edx, r15d
0x180118a43  mov     rax, [rax]
0x180118a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118a4b  nop
0x180118a4c  jmp     loc_180119792
0x180118a51  lea     r8, [rsi+0A0h]; void *
0x180118a58  cmp     [r8+4], r15b
0x180118a5c  jnz     short loc_180118A91
0x180118a5e  lea     rdx, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x180118a65  mov     rcx, r14; this
0x180118a68  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118a6d  mov     edi, eax
0x180118a6f  test    eax, eax
0x180118a71  jz      short loc_180118A91
0x180118a73  mov     rcx, [rsp+0C8h+var_88]
0x180118a78  test    rcx, rcx
0x180118a7b  jz      short loc_180118A8C
0x180118a7d  mov     rax, [rcx]
0x180118a80  mov     edx, r15d
0x180118a83  mov     rax, [rax]
0x180118a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118a8b  nop
0x180118a8c  jmp     loc_180119792
0x180118a91  lea     r8, [rsi+0A8h]; void *
0x180118a98  cmp     [r8+4], r15b
0x180118a9c  jnz     short loc_180118AD1
0x180118a9e  lea     rdx, aAccountlogonlo_4; "AccountLogonLogoff_AuditLogoff"
0x180118aa5  mov     rcx, r14; this
0x180118aa8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118aad  mov     edi, eax
0x180118aaf  test    eax, eax
0x180118ab1  jz      short loc_180118AD1
0x180118ab3  mov     rcx, [rsp+0C8h+var_88]
0x180118ab8  test    rcx, rcx
0x180118abb  jz      short loc_180118ACC
0x180118abd  mov     rax, [rcx]
0x180118ac0  mov     edx, r15d
0x180118ac3  mov     rax, [rax]
0x180118ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118acb  nop
0x180118acc  jmp     loc_180119792
0x180118ad1  lea     r8, [rsi+0B0h]; void *
0x180118ad8  cmp     [r8+4], r15b
0x180118adc  jnz     short loc_180118B11
0x180118ade  lea     rdx, aAccountlogonlo_8; "AccountLogonLogoff_AuditLogon"
0x180118ae5  mov     rcx, r14; this
0x180118ae8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118aed  mov     edi, eax
0x180118aef  test    eax, eax
0x180118af1  jz      short loc_180118B11
0x180118af3  mov     rcx, [rsp+0C8h+var_88]
0x180118af8  test    rcx, rcx
0x180118afb  jz      short loc_180118B0C
0x180118afd  mov     rax, [rcx]
0x180118b00  mov     edx, r15d
0x180118b03  mov     rax, [rax]
0x180118b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118b0b  nop
0x180118b0c  jmp     loc_180119792
0x180118b11  lea     r8, [rsi+0B8h]; void *
0x180118b18  cmp     [r8+4], r15b
0x180118b1c  jnz     short loc_180118B51
0x180118b1e  lea     rdx, aAccountlogonlo; "AccountLogonLogoff_AuditNetworkPolicySe"...
0x180118b25  mov     rcx, r14; this
0x180118b28  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118b2d  mov     edi, eax
0x180118b2f  test    eax, eax
0x180118b31  jz      short loc_180118B51
0x180118b33  mov     rcx, [rsp+0C8h+var_88]
0x180118b38  test    rcx, rcx
0x180118b3b  jz      short loc_180118B4C
0x180118b3d  mov     rax, [rcx]
0x180118b40  mov     edx, r15d
0x180118b43  mov     rax, [rax]
0x180118b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118b4b  nop
0x180118b4c  jmp     loc_180119792
  ... truncated ...
```
