# MDM_Policy_Result01_Audit02_InvokeModifyInstance

- ea: `0x180118aac`
- end: `0x180119bff`
- name: `MDM_Policy_Result01_Audit02_InvokeModifyInstance`
- size: `4435`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180119c10`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x180118aac`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x180118c80`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x180118cbd`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x18011903a`: `AccountManagement_AuditComputerAccountManagement`
- `0x1801190fa`: `AccountManagement_AuditSecurityGroupManagement`
- `0x1801192ba`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x1801192fa`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x18011933a`: `DSAccess_AuditDirectoryServiceAccess`
- `0x18011937a`: `DSAccess_AuditDirectoryServiceChanges`
- `0x1801193ba`: `DSAccess_AuditDirectoryServiceReplication`
- `0x1801193fa`: `ObjectAccess_AuditApplicationGenerated`
- `0x18011943a`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x18011947a`: `ObjectAccess_AuditCertificationServices`
- `0x1801194ba`: `ObjectAccess_AuditDetailedFileShare`
- `0x1801194fa`: `ObjectAccess_AuditFileShare`
- `0x18011953a`: `ObjectAccess_AuditFileSystem`
- `0x18011957a`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x1801195ba`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x1801195fa`: `ObjectAccess_AuditHandleManipulation`
- `0x18011963a`: `ObjectAccess_AuditKernelObject`
- `0x18011967a`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x1801196ba`: `ObjectAccess_AuditRegistry`
- `0x1801196fa`: `ObjectAccess_AuditRemovableStorage`
- `0x18011973a`: `ObjectAccess_AuditSAM`
- `0x1801198fa`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x18011993a`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x18011997a`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x180119a3a`: `System_AuditSecurityStateChange`
- `0x180119a7a`: `System_AuditSecuritySystemExtension`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Audit02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
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
    inserted = CreateRequestHandlerInstance(
                 a1,
                 *(wchar_t **)(a2 + 80),
                 *(const unsigned __int16 **)(a2 + 64),
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_Audit02_NodeList,
                 0x3Du,
                 3,
                 &v8);
    if ( !inserted )
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
                           (LONG *)(a2 + 96))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 108) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditKerberosAuthenticationService",
                                (LONG *)(a2 + 104))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 116) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditKerberosServiceTicketOperations",
                                (LONG *)(a2 + 112))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 124) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogon_AuditOtherAccountLogonEvents",
                                (LONG *)(a2 + 120))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 132) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditAccountLockout",
                                (LONG *)(a2 + 128))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 140) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditGroupMembership",
                                (LONG *)(a2 + 136))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 148) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecExtendedMode",
                                (LONG *)(a2 + 144))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 156) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecMainMode",
                                (LONG *)(a2 + 152))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 164) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditIPsecQuickMode",
                                (LONG *)(a2 + 160))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 172) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditLogoff",
                                (LONG *)(a2 + 168))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 180) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditLogon",
                                (LONG *)(a2 + 176))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 188) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditNetworkPolicyServer",
                                (LONG *)(a2 + 184))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 196) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                                (LONG *)(a2 + 192))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 204) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditSpecialLogon",
                                (LONG *)(a2 + 200))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 212) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountLogonLogoff_AuditUserDeviceClaims",
                                (LONG *)(a2 + 208))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 220) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditApplicationGroupManagement",
                                (LONG *)(a2 + 216))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 228) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditComputerAccountManagement",
                                (LONG *)(a2 + 224))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 236) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditDistributionGroupManagement",
                                (LONG *)(a2 + 232))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 244) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditOtherAccountManagementEvents",
                                (LONG *)(a2 + 240))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 252) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditSecurityGroupManagement",
                                (LONG *)(a2 + 248))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 260) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccountManagement_AuditUserAccountManagement",
                                (LONG *)(a2 + 256))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 268) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditDPAPIActivity",
                                (LONG *)(a2 + 264))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 276) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditPNPActivity",
                                (LONG *)(a2 + 272))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 284) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditProcessCreation",
                                (LONG *)(a2 + 280))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 292) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditProcessTermination",
                                (LONG *)(a2 + 288))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 300) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditRPCEvents",
                                (LONG *)(a2 + 296))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 308) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DetailedTracking_AuditTokenRightAdjusted",
                                (LONG *)(a2 + 304))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 316) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDetailedDirectoryServiceReplication",
                                (LONG *)(a2 + 312))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 324) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceAccess",
                                (LONG *)(a2 + 320))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 332) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceChanges",
                                (LONG *)(a2 + 328))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 340) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DSAccess_AuditDirectoryServiceReplication",
                                (LONG *)(a2 + 336))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 348) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditApplicationGenerated",
                                (LONG *)(a2 + 344))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 356) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditCentralAccessPolicyStaging",
                                (LONG *)(a2 + 352))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 364) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditCertificationServices",
                                (LONG *)(a2 + 360))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 372) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditDetailedFileShare",
                                (LONG *)(a2 + 368))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 380) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFileShare",
                                (LONG *)(a2 + 376))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 388) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFileSystem",
                                (LONG *)(a2 + 384))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 396) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFilteringPlatformConnection",
                                (LONG *)(a2 + 392))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 404) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                                (LONG *)(a2 + 400))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 412) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditHandleManipulation",
                                (LONG *)(a2 + 408))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 420) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditKernelObject",
                                (LONG *)(a2 + 416))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 428) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditOtherObjectAccessEvents",
                                (LONG *)(a2 + 424))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 436) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditRegistry",
                                (LONG *)(a2 + 432))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 444) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ObjectAccess_AuditRemovableStorage",
                                (LONG *)(a2 + 440))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 452) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ObjectAccess_AuditSAM", (LONG *)(a2 + 448))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 460) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditAuthenticationPolicyChange",
                                (LONG *)(a2 + 456))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 468) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditAuthorizationPolicyChange",
                                (LONG *)(a2 + 464))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 476) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditFilteringPlatformPolicyChange",
                                (LONG *)(a2 + 472))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 484) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                                (LONG *)(a2 + 480))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 492) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditOtherPolicyChangeEvents",
                                (LONG *)(a2 + 488))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 500) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PolicyChange_AuditPolicyChange",
                                (LONG *)(a2 + 496))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 508) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                                (LONG *)(a2 + 504))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 516) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                                (LONG *)(a2 + 512))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 524) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PrivilegeUse_AuditSensitivePrivilegeUse",
                                (LONG *)(a2 + 520))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 532) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditIPsecDriver",
                                (LONG *)(a2 + 528))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 540) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditOtherSystemEvents",
                                (LONG *)(a2 + 536))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 548) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSecurityStateChange",
                                (LONG *)(a2 + 544))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 556) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSecuritySystemExtension",
                                (LONG *)(a2 + 552))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 564) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"System_AuditSystemIntegrity",
                                (LONG *)(a2 + 560))) != 0 )
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
            else if ( v8 )
            {
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
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
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v9, "ModifyInstanceEnd", inserted);
  v11 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180342602,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return inserted;
}

```

## disassembly

```asm
0x180118aac  mov     r11, rsp
0x180118aaf  mov     [r11+18h], rsi
0x180118ab3  push    rdi
0x180118ab4  push    r14
0x180118ab6  push    r15
0x180118ab8  sub     rsp, 0B0h
0x180118abf  mov     rax, cs:__security_cookie
0x180118ac6  xor     rax, rsp
0x180118ac9  mov     [rsp+0C8h+var_28], rax
0x180118ad1  mov     rsi, rdx
0x180118ad4  mov     rdi, rcx
0x180118ad7  mov     [rsp+0C8h+var_50], 0
0x180118adf  mov     [rsp+0C8h+var_4C], 0
0x180118ae4  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180118aeb  mov     [r11-80h], rax
0x180118aef  lea     rax, [r11-50h]
0x180118af3  mov     [r11-78h], rax
0x180118af7  lea     rax, aMdmPolicyResul_95; "MDM_Policy_Result01_Audit02"
0x180118afe  mov     [r11-70h], rax
0x180118b02  lea     rcx, [r11-50h]
0x180118b06  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180118b0b  mov     eax, cs:dword_180380B68
0x180118b11  cmp     eax, 5
0x180118b14  jbe     short loc_180118B87
0x180118b16  mov     rdx, 200000000000h
0x180118b20  lea     rcx, dword_180380B68
0x180118b27  call    _tlgKeywordOn
0x180118b2c  test    al, al
0x180118b2e  jz      short loc_180118B87
0x180118b30  cmp     [rsp+0C8h+var_4C], 0
0x180118b35  jz      short loc_180118B69
0x180118b37  cmp     [rsp+0C8h+var_38], 0
0x180118b3f  jnz     short loc_180118B5F
0x180118b41  cmp     [rsp+0C8h+var_34], 0
0x180118b49  jnz     short loc_180118B5F
0x180118b4b  cmp     [rsp+0C8h+var_30], 0
0x180118b53  jnz     short loc_180118B5F
0x180118b55  cmp     [rsp+0C8h+var_2C], 0
0x180118b5d  jz      short loc_180118B69
0x180118b5f  lea     r9, [rsp+0C8h+var_38]
0x180118b67  jmp     short loc_180118B6C
0x180118b69  xor     r9d, r9d
0x180118b6c  lea     r8, [rsp+0C8h+var_48]
0x180118b74  lea     rdx, word_18036AC6E
0x180118b7b  lea     rcx, dword_180380B68
0x180118b82  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180118b87  cmp     byte ptr [rsi+48h], 0
0x180118b8b  jz      loc_180119B69
0x180118b91  cmp     byte ptr [rsi+58h], 0
0x180118b95  jz      loc_180119B69
0x180118b9b  mov     r9, [rsi+40h]; unsigned __int16 *
0x180118b9f  mov     r8, [rsi+50h]; unsigned __int16 *
0x180118ba3  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x180118baa  lea     rcx, [rsp+0C8h+var_80]; this
0x180118baf  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180118bb4  nop
0x180118bb5  mov     [rsp+0C8h+var_88], 0
0x180118bbe  lea     rax, [rsp+0C8h+var_88]
0x180118bc3  mov     [rsp+0C8h+var_98], rax
0x180118bc8  mov     [rsp+0C8h+var_A0], 3
0x180118bd0  mov     [rsp+0C8h+var_A8], 3Dh ; '='
0x180118bd8  lea     r9, ?MDM_Policy_Result01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Audit02_NodeList
0x180118bdf  mov     r8, [rsi+40h]
0x180118be3  mov     rdx, [rsi+50h]
0x180118be7  mov     rcx, rdi
0x180118bea  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180118bef  mov     edi, eax
0x180118bf1  test    eax, eax
0x180118bf3  jz      short loc_180118BFA
0x180118bf5  jmp     loc_180119B6E
0x180118bfa  lea     rax, [rsp+0C8h+var_88]
0x180118bff  mov     [rsp+0C8h+var_60], rax
0x180118c04  mov     r15d, 1
0x180118c0a  mov     [rsp+0C8h+var_58], r15b
0x180118c0f  mov     r14, [rsp+0C8h+var_88]
0x180118c14  test    r14, r14
0x180118c17  jnz     short loc_180118C21
0x180118c19  mov     edi, r15d
0x180118c1c  jmp     loc_180119B6E
0x180118c21  mov     r9d, 3Dh ; '='; unsigned int
0x180118c27  lea     r8, ?MDM_Policy_Result01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180118c2e  mov     rdx, rsi; struct _MI_Instance *
0x180118c31  mov     rcx, r14; this
0x180118c34  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180118c39  lea     r8, [rsi+60h]; void *
0x180118c3d  cmp     [r8+4], r15b
0x180118c41  jnz     short loc_180118C76
0x180118c43  lea     rdx, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x180118c4a  mov     rcx, r14; this
0x180118c4d  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118c52  mov     edi, eax
0x180118c54  test    eax, eax
0x180118c56  jz      short loc_180118C76
0x180118c58  mov     rcx, [rsp+0C8h+var_88]
0x180118c5d  test    rcx, rcx
0x180118c60  jz      short loc_180118C71
0x180118c62  mov     rax, [rcx]
0x180118c65  mov     edx, r15d
0x180118c68  mov     rax, [rax]
0x180118c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118c70  nop
0x180118c71  jmp     loc_180119B6E
0x180118c76  lea     r8, [rsi+68h]; void *
0x180118c7a  cmp     [r8+4], r15b
0x180118c7e  jnz     short loc_180118CB3
0x180118c80  lea     rdx, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x180118c87  mov     rcx, r14; this
0x180118c8a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118c8f  mov     edi, eax
0x180118c91  test    eax, eax
0x180118c93  jz      short loc_180118CB3
0x180118c95  mov     rcx, [rsp+0C8h+var_88]
0x180118c9a  test    rcx, rcx
0x180118c9d  jz      short loc_180118CAE
0x180118c9f  mov     rax, [rcx]
0x180118ca2  mov     edx, r15d
0x180118ca5  mov     rax, [rax]
0x180118ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118cad  nop
0x180118cae  jmp     loc_180119B6E
0x180118cb3  lea     r8, [rsi+70h]; void *
0x180118cb7  cmp     [r8+4], r15b
0x180118cbb  jnz     short loc_180118CF0
0x180118cbd  lea     rdx, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x180118cc4  mov     rcx, r14; this
0x180118cc7  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118ccc  mov     edi, eax
0x180118cce  test    eax, eax
0x180118cd0  jz      short loc_180118CF0
0x180118cd2  mov     rcx, [rsp+0C8h+var_88]
0x180118cd7  test    rcx, rcx
0x180118cda  jz      short loc_180118CEB
0x180118cdc  mov     rax, [rcx]
0x180118cdf  mov     edx, r15d
0x180118ce2  mov     rax, [rax]
0x180118ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118cea  nop
0x180118ceb  jmp     loc_180119B6E
0x180118cf0  lea     r8, [rsi+78h]; void *
0x180118cf4  cmp     [r8+4], r15b
0x180118cf8  jnz     short loc_180118D2D
0x180118cfa  lea     rdx, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x180118d01  mov     rcx, r14; this
0x180118d04  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118d09  mov     edi, eax
0x180118d0b  test    eax, eax
0x180118d0d  jz      short loc_180118D2D
0x180118d0f  mov     rcx, [rsp+0C8h+var_88]
0x180118d14  test    rcx, rcx
0x180118d17  jz      short loc_180118D28
0x180118d19  mov     rax, [rcx]
0x180118d1c  mov     edx, r15d
0x180118d1f  mov     rax, [rax]
0x180118d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118d27  nop
0x180118d28  jmp     loc_180119B6E
0x180118d2d  lea     r8, [rsi+80h]; void *
0x180118d34  cmp     [r8+4], r15b
0x180118d38  jnz     short loc_180118D6D
0x180118d3a  lea     rdx, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x180118d41  mov     rcx, r14; this
0x180118d44  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118d49  mov     edi, eax
0x180118d4b  test    eax, eax
0x180118d4d  jz      short loc_180118D6D
0x180118d4f  mov     rcx, [rsp+0C8h+var_88]
0x180118d54  test    rcx, rcx
0x180118d57  jz      short loc_180118D68
0x180118d59  mov     rax, [rcx]
0x180118d5c  mov     edx, r15d
0x180118d5f  mov     rax, [rax]
0x180118d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118d67  nop
0x180118d68  jmp     loc_180119B6E
0x180118d6d  lea     r8, [rsi+88h]; void *
0x180118d74  cmp     [r8+4], r15b
0x180118d78  jnz     short loc_180118DAD
0x180118d7a  lea     rdx, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x180118d81  mov     rcx, r14; this
0x180118d84  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118d89  mov     edi, eax
0x180118d8b  test    eax, eax
0x180118d8d  jz      short loc_180118DAD
0x180118d8f  mov     rcx, [rsp+0C8h+var_88]
0x180118d94  test    rcx, rcx
0x180118d97  jz      short loc_180118DA8
0x180118d99  mov     rax, [rcx]
0x180118d9c  mov     edx, r15d
0x180118d9f  mov     rax, [rax]
0x180118da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118da7  nop
0x180118da8  jmp     loc_180119B6E
0x180118dad  lea     r8, [rsi+90h]; void *
0x180118db4  cmp     [r8+4], r15b
0x180118db8  jnz     short loc_180118DED
0x180118dba  lea     rdx, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x180118dc1  mov     rcx, r14; this
0x180118dc4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118dc9  mov     edi, eax
0x180118dcb  test    eax, eax
0x180118dcd  jz      short loc_180118DED
0x180118dcf  mov     rcx, [rsp+0C8h+var_88]
0x180118dd4  test    rcx, rcx
0x180118dd7  jz      short loc_180118DE8
0x180118dd9  mov     rax, [rcx]
0x180118ddc  mov     edx, r15d
0x180118ddf  mov     rax, [rax]
0x180118de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118de7  nop
0x180118de8  jmp     loc_180119B6E
0x180118ded  lea     r8, [rsi+98h]; void *
0x180118df4  cmp     [r8+4], r15b
0x180118df8  jnz     short loc_180118E2D
0x180118dfa  lea     rdx, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x180118e01  mov     rcx, r14; this
0x180118e04  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118e09  mov     edi, eax
0x180118e0b  test    eax, eax
0x180118e0d  jz      short loc_180118E2D
0x180118e0f  mov     rcx, [rsp+0C8h+var_88]
0x180118e14  test    rcx, rcx
0x180118e17  jz      short loc_180118E28
0x180118e19  mov     rax, [rcx]
0x180118e1c  mov     edx, r15d
0x180118e1f  mov     rax, [rax]
0x180118e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118e27  nop
0x180118e28  jmp     loc_180119B6E
0x180118e2d  lea     r8, [rsi+0A0h]; void *
0x180118e34  cmp     [r8+4], r15b
0x180118e38  jnz     short loc_180118E6D
0x180118e3a  lea     rdx, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x180118e41  mov     rcx, r14; this
0x180118e44  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118e49  mov     edi, eax
0x180118e4b  test    eax, eax
0x180118e4d  jz      short loc_180118E6D
0x180118e4f  mov     rcx, [rsp+0C8h+var_88]
0x180118e54  test    rcx, rcx
0x180118e57  jz      short loc_180118E68
0x180118e59  mov     rax, [rcx]
0x180118e5c  mov     edx, r15d
0x180118e5f  mov     rax, [rax]
0x180118e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118e67  nop
0x180118e68  jmp     loc_180119B6E
0x180118e6d  lea     r8, [rsi+0A8h]; void *
0x180118e74  cmp     [r8+4], r15b
0x180118e78  jnz     short loc_180118EAD
0x180118e7a  lea     rdx, aAccountlogonlo_4; "AccountLogonLogoff_AuditLogoff"
0x180118e81  mov     rcx, r14; this
0x180118e84  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118e89  mov     edi, eax
0x180118e8b  test    eax, eax
0x180118e8d  jz      short loc_180118EAD
0x180118e8f  mov     rcx, [rsp+0C8h+var_88]
0x180118e94  test    rcx, rcx
0x180118e97  jz      short loc_180118EA8
0x180118e99  mov     rax, [rcx]
0x180118e9c  mov     edx, r15d
0x180118e9f  mov     rax, [rax]
0x180118ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118ea7  nop
0x180118ea8  jmp     loc_180119B6E
0x180118ead  lea     r8, [rsi+0B0h]; void *
0x180118eb4  cmp     [r8+4], r15b
0x180118eb8  jnz     short loc_180118EED
0x180118eba  lea     rdx, aAccountlogonlo_8; "AccountLogonLogoff_AuditLogon"
0x180118ec1  mov     rcx, r14; this
0x180118ec4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118ec9  mov     edi, eax
0x180118ecb  test    eax, eax
0x180118ecd  jz      short loc_180118EED
0x180118ecf  mov     rcx, [rsp+0C8h+var_88]
0x180118ed4  test    rcx, rcx
0x180118ed7  jz      short loc_180118EE8
0x180118ed9  mov     rax, [rcx]
0x180118edc  mov     edx, r15d
0x180118edf  mov     rax, [rax]
0x180118ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118ee7  nop
0x180118ee8  jmp     loc_180119B6E
0x180118eed  lea     r8, [rsi+0B8h]; void *
0x180118ef4  cmp     [r8+4], r15b
0x180118ef8  jnz     short loc_180118F2D
0x180118efa  lea     rdx, aAccountlogonlo; "AccountLogonLogoff_AuditNetworkPolicySe"...
0x180118f01  mov     rcx, r14; this
0x180118f04  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180118f09  mov     edi, eax
0x180118f0b  test    eax, eax
0x180118f0d  jz      short loc_180118F2D
0x180118f0f  mov     rcx, [rsp+0C8h+var_88]
0x180118f14  test    rcx, rcx
0x180118f17  jz      short loc_180118F28
0x180118f19  mov     rax, [rcx]
0x180118f1c  mov     edx, r15d
0x180118f1f  mov     rax, [rax]
0x180118f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118f27  nop
0x180118f28  jmp     loc_180119B6E
  ... truncated ...
```
