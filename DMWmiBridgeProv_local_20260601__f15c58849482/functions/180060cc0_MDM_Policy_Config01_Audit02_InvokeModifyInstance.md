# MDM_Policy_Config01_Audit02_InvokeModifyInstance

- ea: `0x180060cc0`
- end: `0x180061e14`
- name: `MDM_Policy_Config01_Audit02_InvokeModifyInstance`
- size: `4436`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180061e20`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x180060cc0`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x180060e94`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x180060ed1`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x18006124e`: `AccountManagement_AuditComputerAccountManagement`
- `0x18006130e`: `AccountManagement_AuditSecurityGroupManagement`
- `0x1800614ce`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x18006150e`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x18006154e`: `DSAccess_AuditDirectoryServiceAccess`
- `0x18006158e`: `DSAccess_AuditDirectoryServiceChanges`
- `0x1800615ce`: `DSAccess_AuditDirectoryServiceReplication`
- `0x18006160e`: `ObjectAccess_AuditApplicationGenerated`
- `0x18006164e`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x18006168e`: `ObjectAccess_AuditCertificationServices`
- `0x1800616ce`: `ObjectAccess_AuditDetailedFileShare`
- `0x18006170e`: `ObjectAccess_AuditFileShare`
- `0x18006174e`: `ObjectAccess_AuditFileSystem`
- `0x18006178e`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x1800617ce`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x18006180e`: `ObjectAccess_AuditHandleManipulation`
- `0x18006184e`: `ObjectAccess_AuditKernelObject`
- `0x18006188e`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x1800618ce`: `ObjectAccess_AuditRegistry`
- `0x18006190e`: `ObjectAccess_AuditRemovableStorage`
- `0x18006194e`: `ObjectAccess_AuditSAM`
- `0x180061b0e`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x180061b4e`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x180061b8e`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x180061c4e`: `System_AuditSecurityStateChange`
- `0x180061c8e`: `System_AuditSecuritySystemExtension`
- `0x180060d0b`: `MDM_Policy_Config01_Audit02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Audit02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  wil *v5; // rcx
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v7; // r14
  const char *v9; // rax
  int v10; // eax
  WmiRequestHandler *v11; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-80h] BYREF
  const exception *v13[2]; // [rsp+60h] [rbp-68h] BYREF
  char v14; // [rsp+70h] [rbp-58h]
  int v15; // [rsp+78h] [rbp-50h] BYREF
  char v16; // [rsp+7Ch] [rbp-4Ch]
  _BYTE v17[16]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD v18[4]; // [rsp+90h] [rbp-38h] BYREF

  v15 = 0;
  v16 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v15;
  v12[2] = "MDM_Policy_Config01_Audit02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v4 = v18;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033B043,
      v17,
      v4);
  }
  if ( *(_BYTE *)(a2 + 72) && *(_BYTE *)(a2 + 88) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v12,
      "ModifyInstanceStart",
      *(const unsigned __int16 **)(a2 + 80),
      *(const unsigned __int16 **)(a2 + 64));
    try
    {
      v11 = 0;
      inserted = (unsigned int)CreateRequestHandlerInstance(
                                 a1,
                                 *(_QWORD *)(a2 + 80),
                                 *(_QWORD *)(a2 + 64),
                                 &MDM_Policy_Config01_Audit02_NodeList,
                                 61,
                                 3,
                                 &v11);
      if ( inserted == MI_RESULT_OK )
      {
        v13[1] = (const exception *)&v11;
        v14 = 1;
        v7 = v11;
        if ( v11 )
        {
          WmiRequestHandler::SetRequestMIInstance(
            v11,
            (const struct _MI_Instance *)a2,
            (struct WmiNodeInfo *)&MDM_Policy_Config01_Audit02_NodeList,
            0x3Du);
          if ( *(_BYTE *)(a2 + 100) == 1
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                             v7,
                             L"AccountLogon_AuditCredentialValidation",
                             (void *)(a2 + 96))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogon_AuditKerberosAuthenticationService",
                                  (void *)(a2 + 104))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogon_AuditKerberosServiceTicketOperations",
                                  (void *)(a2 + 112))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogon_AuditOtherAccountLogonEvents",
                                  (void *)(a2 + 120))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 132) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditAccountLockout",
                                  (void *)(a2 + 128))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 140) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditGroupMembership",
                                  (void *)(a2 + 136))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 148) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditIPsecExtendedMode",
                                  (void *)(a2 + 144))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 156) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditIPsecMainMode",
                                  (void *)(a2 + 152))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 164) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditIPsecQuickMode",
                                  (void *)(a2 + 160))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 172) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditLogoff",
                                  (void *)(a2 + 168))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditLogon",
                                  (void *)(a2 + 176))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditNetworkPolicyServer",
                                  (void *)(a2 + 184))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 196) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                                  (void *)(a2 + 192))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 204) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditSpecialLogon",
                                  (void *)(a2 + 200))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 212) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditUserDeviceClaims",
                                  (void *)(a2 + 208))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 220) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditApplicationGroupManagement",
                                  (void *)(a2 + 216))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 228) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditComputerAccountManagement",
                                  (void *)(a2 + 224))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditDistributionGroupManagement",
                                  (void *)(a2 + 232))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditOtherAccountManagementEvents",
                                  (void *)(a2 + 240))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 252) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditSecurityGroupManagement",
                                  (void *)(a2 + 248))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 260) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditUserAccountManagement",
                                  (void *)(a2 + 256))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 268) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditDPAPIActivity",
                                  (void *)(a2 + 264))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 276) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditPNPActivity",
                                  (void *)(a2 + 272))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 284) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditProcessCreation",
                                  (void *)(a2 + 280))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 292) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditProcessTermination",
                                  (void *)(a2 + 288))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 300) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditRPCEvents",
                                  (void *)(a2 + 296))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 308) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditTokenRightAdjusted",
                                  (void *)(a2 + 304))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 316) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DSAccess_AuditDetailedDirectoryServiceReplication",
                                  (void *)(a2 + 312))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 324) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DSAccess_AuditDirectoryServiceAccess",
                                  (void *)(a2 + 320))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 332) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DSAccess_AuditDirectoryServiceChanges",
                                  (void *)(a2 + 328))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 340) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DSAccess_AuditDirectoryServiceReplication",
                                  (void *)(a2 + 336))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 348) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditApplicationGenerated",
                                  (void *)(a2 + 344))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 356) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditCentralAccessPolicyStaging",
                                  (void *)(a2 + 352))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 364) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditCertificationServices",
                                  (void *)(a2 + 360))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 372) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditDetailedFileShare",
                                  (void *)(a2 + 368))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 380) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditFileShare",
                                  (void *)(a2 + 376))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 388) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditFileSystem",
                                  (void *)(a2 + 384))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 396) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditFilteringPlatformConnection",
                                  (void *)(a2 + 392))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 404) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                                  (void *)(a2 + 400))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 412) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditHandleManipulation",
                                  (void *)(a2 + 408))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 420) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditKernelObject",
                                  (void *)(a2 + 416))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 428) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditOtherObjectAccessEvents",
                                  (void *)(a2 + 424))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 436) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditRegistry",
                                  (void *)(a2 + 432))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 444) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditRemovableStorage",
                                  (void *)(a2 + 440))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 452) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditSAM",
                                  (void *)(a2 + 448))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 460) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditAuthenticationPolicyChange",
                                  (void *)(a2 + 456))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 468) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditAuthorizationPolicyChange",
                                  (void *)(a2 + 464))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 476) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditFilteringPlatformPolicyChange",
                                  (void *)(a2 + 472))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 484) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                                  (void *)(a2 + 480))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 492) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditOtherPolicyChangeEvents",
                                  (void *)(a2 + 488))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 500) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditPolicyChange",
                                  (void *)(a2 + 496))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 508) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                                  (void *)(a2 + 504))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 516) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                                  (void *)(a2 + 512))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 524) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PrivilegeUse_AuditSensitivePrivilegeUse",
                                  (void *)(a2 + 520))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 532) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"System_AuditIPsecDriver",
                                  (void *)(a2 + 528))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 540) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"System_AuditOtherSystemEvents",
                                  (void *)(a2 + 536))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 548) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"System_AuditSecurityStateChange",
                                  (void *)(a2 + 544))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 556) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"System_AuditSecuritySystemExtension",
                                  (void *)(a2 + 552))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 564) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"System_AuditSystemIntegrity",
                                  (void *)(a2 + 560))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else
          {
            inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( inserted )
            {
              v5 = v11;
              if ( v11 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
            }
            else
            {
              inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 8LL))(v7);
              v5 = v11;
              if ( inserted )
              {
                if ( v11 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
              }
              else if ( v11 )
              {
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
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
    catch ( const exception *v13 )
    {
      v9 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v13[0] + 8LL))(v13[0]);
      TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v12, v9);
      LODWORD(v11) = 1;
      inserted = MI_RESULT_FAILED;
    }
    catch ( ... )
    {
      v10 = wil::ResultFromCaughtException(v5);
      TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v12, v10);
      LODWORD(v11) = 1;
      inserted = MI_RESULT_FAILED;
    }
  }
  else
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "ModifyInstanceEnd", inserted);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180345978,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180060cc0  mov     r11, rsp
0x180060cc3  mov     [r11+18h], rsi
0x180060cc7  push    rdi
0x180060cc8  push    r14
0x180060cca  push    r15
0x180060ccc  sub     rsp, 0B0h
0x180060cd3  mov     rax, cs:__security_cookie
0x180060cda  xor     rax, rsp
0x180060cdd  mov     [rsp+0C8h+var_28], rax
0x180060ce5  mov     rsi, rdx
0x180060ce8  mov     rdi, rcx
0x180060ceb  mov     [rsp+0C8h+var_50], 0
0x180060cf3  mov     [rsp+0C8h+var_4C], 0
0x180060cf8  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180060cff  mov     [r11-80h], rax
0x180060d03  lea     rax, [r11-50h]
0x180060d07  mov     [r11-78h], rax
0x180060d0b  lea     rax, aMdmPolicyConfi_129; "MDM_Policy_Config01_Audit02"
0x180060d12  mov     [r11-70h], rax
0x180060d16  lea     rcx, [r11-50h]
0x180060d1a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180060d1f  mov     eax, cs:dword_180380B68
0x180060d25  cmp     eax, 5
0x180060d28  jbe     short loc_180060D9B
0x180060d2a  mov     rdx, 200000000000h
0x180060d34  lea     rcx, dword_180380B68
0x180060d3b  call    _tlgKeywordOn
0x180060d40  test    al, al
0x180060d42  jz      short loc_180060D9B
0x180060d44  cmp     [rsp+0C8h+var_4C], 0
0x180060d49  jz      short loc_180060D7D
0x180060d4b  cmp     [rsp+0C8h+var_38], 0
0x180060d53  jnz     short loc_180060D73
0x180060d55  cmp     [rsp+0C8h+var_34], 0
0x180060d5d  jnz     short loc_180060D73
0x180060d5f  cmp     [rsp+0C8h+var_30], 0
0x180060d67  jnz     short loc_180060D73
0x180060d69  cmp     [rsp+0C8h+var_2C], 0
0x180060d71  jz      short loc_180060D7D
0x180060d73  lea     r9, [rsp+0C8h+var_38]
0x180060d7b  jmp     short loc_180060D80
0x180060d7d  xor     r9d, r9d
0x180060d80  lea     r8, [rsp+0C8h+var_48]
0x180060d88  lea     rdx, byte_18033B043
0x180060d8f  lea     rcx, dword_180380B68
0x180060d96  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180060d9b  cmp     byte ptr [rsi+48h], 0
0x180060d9f  jz      loc_180061D7D
0x180060da5  cmp     byte ptr [rsi+58h], 0
0x180060da9  jz      loc_180061D7D
0x180060daf  mov     r9, [rsi+40h]; unsigned __int16 *
0x180060db3  mov     r8, [rsi+50h]; unsigned __int16 *
0x180060db7  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x180060dbe  lea     rcx, [rsp+0C8h+var_80]; this
0x180060dc3  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180060dc8  nop
0x180060dc9  mov     [rsp+0C8h+var_88], 0
0x180060dd2  lea     rax, [rsp+0C8h+var_88]
0x180060dd7  mov     [rsp+0C8h+var_98], rax
0x180060ddc  mov     [rsp+0C8h+var_A0], 3
0x180060de4  mov     [rsp+0C8h+var_A8], 3Dh ; '='
0x180060dec  lea     r9, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Audit02_NodeList
0x180060df3  mov     r8, [rsi+40h]
0x180060df7  mov     rdx, [rsi+50h]
0x180060dfb  mov     rcx, rdi
0x180060dfe  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180060e03  mov     edi, eax
0x180060e05  test    eax, eax
0x180060e07  jz      short loc_180060E0E
0x180060e09  jmp     loc_180061D82
0x180060e0e  lea     rax, [rsp+0C8h+var_88]
0x180060e13  mov     [rsp+0C8h+var_60], rax
0x180060e18  mov     r15d, 1
0x180060e1e  mov     [rsp+0C8h+var_58], r15b
0x180060e23  mov     r14, [rsp+0C8h+var_88]
0x180060e28  test    r14, r14
0x180060e2b  jnz     short loc_180060E35
0x180060e2d  mov     edi, r15d
0x180060e30  jmp     loc_180061D82
0x180060e35  mov     r9d, 3Dh ; '='; unsigned int
0x180060e3b  lea     r8, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180060e42  mov     rdx, rsi; struct _MI_Instance *
0x180060e45  mov     rcx, r14; this
0x180060e48  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180060e4d  lea     r8, [rsi+60h]; void *
0x180060e51  cmp     [r8+4], r15b
0x180060e55  jnz     short loc_180060E8A
0x180060e57  lea     rdx, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x180060e5e  mov     rcx, r14; this
0x180060e61  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180060e66  mov     edi, eax
0x180060e68  test    eax, eax
0x180060e6a  jz      short loc_180060E8A
0x180060e6c  mov     rcx, [rsp+0C8h+var_88]
0x180060e71  test    rcx, rcx
0x180060e74  jz      short loc_180060E85
0x180060e76  mov     rax, [rcx]
0x180060e79  mov     edx, r15d
0x180060e7c  mov     rax, [rax]
0x180060e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060e84  nop
0x180060e85  jmp     loc_180061D82
0x180060e8a  lea     r8, [rsi+68h]; void *
0x180060e8e  cmp     [r8+4], r15b
0x180060e92  jnz     short loc_180060EC7
0x180060e94  lea     rdx, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x180060e9b  mov     rcx, r14; this
0x180060e9e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180060ea3  mov     edi, eax
0x180060ea5  test    eax, eax
0x180060ea7  jz      short loc_180060EC7
0x180060ea9  mov     rcx, [rsp+0C8h+var_88]
0x180060eae  test    rcx, rcx
0x180060eb1  jz      short loc_180060EC2
0x180060eb3  mov     rax, [rcx]
0x180060eb6  mov     edx, r15d
0x180060eb9  mov     rax, [rax]
0x180060ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ec1  nop
0x180060ec2  jmp     loc_180061D82
0x180060ec7  lea     r8, [rsi+70h]; void *
0x180060ecb  cmp     [r8+4], r15b
0x180060ecf  jnz     short loc_180060F04
0x180060ed1  lea     rdx, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x180060ed8  mov     rcx, r14; this
0x180060edb  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180060ee0  mov     edi, eax
0x180060ee2  test    eax, eax
0x180060ee4  jz      short loc_180060F04
0x180060ee6  mov     rcx, [rsp+0C8h+var_88]
0x180060eeb  test    rcx, rcx
0x180060eee  jz      short loc_180060EFF
0x180060ef0  mov     rax, [rcx]
0x180060ef3  mov     edx, r15d
0x180060ef6  mov     rax, [rax]
0x180060ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060efe  nop
0x180060eff  jmp     loc_180061D82
0x180060f04  lea     r8, [rsi+78h]; void *
0x180060f08  cmp     [r8+4], r15b
0x180060f0c  jnz     short loc_180060F41
0x180060f0e  lea     rdx, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x180060f15  mov     rcx, r14; this
0x180060f18  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180060f1d  mov     edi, eax
0x180060f1f  test    eax, eax
0x180060f21  jz      short loc_180060F41
0x180060f23  mov     rcx, [rsp+0C8h+var_88]
0x180060f28  test    rcx, rcx
0x180060f2b  jz      short loc_180060F3C
0x180060f2d  mov     rax, [rcx]
0x180060f30  mov     edx, r15d
0x180060f33  mov     rax, [rax]
0x180060f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f3b  nop
0x180060f3c  jmp     loc_180061D82
0x180060f41  lea     r8, [rsi+80h]; void *
0x180060f48  cmp     [r8+4], r15b
0x180060f4c  jnz     short loc_180060F81
0x180060f4e  lea     rdx, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x180060f55  mov     rcx, r14; this
0x180060f58  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180060f5d  mov     edi, eax
0x180060f5f  test    eax, eax
0x180060f61  jz      short loc_180060F81
0x180060f63  mov     rcx, [rsp+0C8h+var_88]
0x180060f68  test    rcx, rcx
0x180060f6b  jz      short loc_180060F7C
0x180060f6d  mov     rax, [rcx]
0x180060f70  mov     edx, r15d
0x180060f73  mov     rax, [rax]
0x180060f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f7b  nop
0x180060f7c  jmp     loc_180061D82
0x180060f81  lea     r8, [rsi+88h]; void *
0x180060f88  cmp     [r8+4], r15b
0x180060f8c  jnz     short loc_180060FC1
0x180060f8e  lea     rdx, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x180060f95  mov     rcx, r14; this
0x180060f98  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180060f9d  mov     edi, eax
0x180060f9f  test    eax, eax
0x180060fa1  jz      short loc_180060FC1
0x180060fa3  mov     rcx, [rsp+0C8h+var_88]
0x180060fa8  test    rcx, rcx
0x180060fab  jz      short loc_180060FBC
0x180060fad  mov     rax, [rcx]
0x180060fb0  mov     edx, r15d
0x180060fb3  mov     rax, [rax]
0x180060fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060fbb  nop
0x180060fbc  jmp     loc_180061D82
0x180060fc1  lea     r8, [rsi+90h]; void *
0x180060fc8  cmp     [r8+4], r15b
0x180060fcc  jnz     short loc_180061001
0x180060fce  lea     rdx, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x180060fd5  mov     rcx, r14; this
0x180060fd8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180060fdd  mov     edi, eax
0x180060fdf  test    eax, eax
0x180060fe1  jz      short loc_180061001
0x180060fe3  mov     rcx, [rsp+0C8h+var_88]
0x180060fe8  test    rcx, rcx
0x180060feb  jz      short loc_180060FFC
0x180060fed  mov     rax, [rcx]
0x180060ff0  mov     edx, r15d
0x180060ff3  mov     rax, [rax]
0x180060ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ffb  nop
0x180060ffc  jmp     loc_180061D82
0x180061001  lea     r8, [rsi+98h]; void *
0x180061008  cmp     [r8+4], r15b
0x18006100c  jnz     short loc_180061041
0x18006100e  lea     rdx, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x180061015  mov     rcx, r14; this
0x180061018  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006101d  mov     edi, eax
0x18006101f  test    eax, eax
0x180061021  jz      short loc_180061041
0x180061023  mov     rcx, [rsp+0C8h+var_88]
0x180061028  test    rcx, rcx
0x18006102b  jz      short loc_18006103C
0x18006102d  mov     rax, [rcx]
0x180061030  mov     edx, r15d
0x180061033  mov     rax, [rax]
0x180061036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006103b  nop
0x18006103c  jmp     loc_180061D82
0x180061041  lea     r8, [rsi+0A0h]; void *
0x180061048  cmp     [r8+4], r15b
0x18006104c  jnz     short loc_180061081
0x18006104e  lea     rdx, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x180061055  mov     rcx, r14; this
0x180061058  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006105d  mov     edi, eax
0x18006105f  test    eax, eax
0x180061061  jz      short loc_180061081
0x180061063  mov     rcx, [rsp+0C8h+var_88]
0x180061068  test    rcx, rcx
0x18006106b  jz      short loc_18006107C
0x18006106d  mov     rax, [rcx]
0x180061070  mov     edx, r15d
0x180061073  mov     rax, [rax]
0x180061076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006107b  nop
0x18006107c  jmp     loc_180061D82
0x180061081  lea     r8, [rsi+0A8h]; void *
0x180061088  cmp     [r8+4], r15b
0x18006108c  jnz     short loc_1800610C1
0x18006108e  lea     rdx, aAccountlogonlo_4; "AccountLogonLogoff_AuditLogoff"
0x180061095  mov     rcx, r14; this
0x180061098  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006109d  mov     edi, eax
0x18006109f  test    eax, eax
0x1800610a1  jz      short loc_1800610C1
0x1800610a3  mov     rcx, [rsp+0C8h+var_88]
0x1800610a8  test    rcx, rcx
0x1800610ab  jz      short loc_1800610BC
0x1800610ad  mov     rax, [rcx]
0x1800610b0  mov     edx, r15d
0x1800610b3  mov     rax, [rax]
0x1800610b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800610bb  nop
0x1800610bc  jmp     loc_180061D82
0x1800610c1  lea     r8, [rsi+0B0h]; void *
0x1800610c8  cmp     [r8+4], r15b
0x1800610cc  jnz     short loc_180061101
0x1800610ce  lea     rdx, aAccountlogonlo_8; "AccountLogonLogoff_AuditLogon"
0x1800610d5  mov     rcx, r14; this
0x1800610d8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800610dd  mov     edi, eax
0x1800610df  test    eax, eax
0x1800610e1  jz      short loc_180061101
0x1800610e3  mov     rcx, [rsp+0C8h+var_88]
0x1800610e8  test    rcx, rcx
0x1800610eb  jz      short loc_1800610FC
0x1800610ed  mov     rax, [rcx]
0x1800610f0  mov     edx, r15d
0x1800610f3  mov     rax, [rax]
0x1800610f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800610fb  nop
0x1800610fc  jmp     loc_180061D82
0x180061101  lea     r8, [rsi+0B8h]; void *
0x180061108  cmp     [r8+4], r15b
0x18006110c  jnz     short loc_180061141
0x18006110e  lea     rdx, aAccountlogonlo; "AccountLogonLogoff_AuditNetworkPolicySe"...
0x180061115  mov     rcx, r14; this
0x180061118  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006111d  mov     edi, eax
0x18006111f  test    eax, eax
0x180061121  jz      short loc_180061141
0x180061123  mov     rcx, [rsp+0C8h+var_88]
0x180061128  test    rcx, rcx
0x18006112b  jz      short loc_18006113C
0x18006112d  mov     rax, [rcx]
0x180061130  mov     edx, r15d
0x180061133  mov     rax, [rax]
0x180061136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006113b  nop
0x18006113c  jmp     loc_180061D82
  ... truncated ...
```
