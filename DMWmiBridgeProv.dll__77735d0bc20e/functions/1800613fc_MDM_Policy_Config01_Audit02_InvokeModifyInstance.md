# MDM_Policy_Config01_Audit02_InvokeModifyInstance

- ea: `0x1800613fc`
- end: `0x18006254f`
- name: `MDM_Policy_Config01_Audit02_InvokeModifyInstance`
- size: `4435`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180062560`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x1800613fc`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800615d0`: `AccountLogon_AuditKerberosAuthenticationService`
- `0x18006160d`: `AccountLogon_AuditKerberosServiceTicketOperations`
- `0x18006198a`: `AccountManagement_AuditComputerAccountManagement`
- `0x180061a4a`: `AccountManagement_AuditSecurityGroupManagement`
- `0x180061c0a`: `DetailedTracking_AuditTokenRightAdjusted`
- `0x180061c4a`: `DSAccess_AuditDetailedDirectoryServiceReplication`
- `0x180061c8a`: `DSAccess_AuditDirectoryServiceAccess`
- `0x180061cca`: `DSAccess_AuditDirectoryServiceChanges`
- `0x180061d0a`: `DSAccess_AuditDirectoryServiceReplication`
- `0x180061d4a`: `ObjectAccess_AuditApplicationGenerated`
- `0x180061d8a`: `ObjectAccess_AuditCentralAccessPolicyStaging`
- `0x180061dca`: `ObjectAccess_AuditCertificationServices`
- `0x180061e0a`: `ObjectAccess_AuditDetailedFileShare`
- `0x180061e4a`: `ObjectAccess_AuditFileShare`
- `0x180061e8a`: `ObjectAccess_AuditFileSystem`
- `0x180061eca`: `ObjectAccess_AuditFilteringPlatformConnection`
- `0x180061f0a`: `ObjectAccess_AuditFilteringPlatformPacketDrop`
- `0x180061f4a`: `ObjectAccess_AuditHandleManipulation`
- `0x180061f8a`: `ObjectAccess_AuditKernelObject`
- `0x180061fca`: `ObjectAccess_AuditOtherObjectAccessEvents`
- `0x18006200a`: `ObjectAccess_AuditRegistry`
- `0x18006204a`: `ObjectAccess_AuditRemovableStorage`
- `0x18006208a`: `ObjectAccess_AuditSAM`
- `0x18006224a`: `PrivilegeUse_AuditNonSensitivePrivilegeUse`
- `0x18006228a`: `PrivilegeUse_AuditOtherPrivilegeUseEvents`
- `0x1800622ca`: `PrivilegeUse_AuditSensitivePrivilegeUse`
- `0x18006238a`: `System_AuditSecurityStateChange`
- `0x1800623ca`: `System_AuditSecuritySystemExtension`
- `0x180061447`: `MDM_Policy_Config01_Audit02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Audit02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  wil *v5; // rcx
  unsigned int inserted; // edi
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
      inserted = CreateRequestHandlerInstance(
                   a1,
                   *(wchar_t **)(a2 + 80),
                   *(const unsigned __int16 **)(a2 + 64),
                   (struct WmiNodeInfo *)&MDM_Policy_Config01_Audit02_NodeList,
                   0x3Du,
                   3,
                   &v11);
      if ( !inserted )
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
                             (LONG *)(a2 + 96))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogon_AuditKerberosAuthenticationService",
                                  (LONG *)(a2 + 104))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogon_AuditKerberosServiceTicketOperations",
                                  (LONG *)(a2 + 112))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogon_AuditOtherAccountLogonEvents",
                                  (LONG *)(a2 + 120))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 132) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditAccountLockout",
                                  (LONG *)(a2 + 128))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 140) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditGroupMembership",
                                  (LONG *)(a2 + 136))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 148) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditIPsecExtendedMode",
                                  (LONG *)(a2 + 144))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 156) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditIPsecMainMode",
                                  (LONG *)(a2 + 152))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 164) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditIPsecQuickMode",
                                  (LONG *)(a2 + 160))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 172) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditLogoff",
                                  (LONG *)(a2 + 168))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditLogon",
                                  (LONG *)(a2 + 176))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditNetworkPolicyServer",
                                  (LONG *)(a2 + 184))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 196) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditOtherLogonLogoffEvents",
                                  (LONG *)(a2 + 192))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 204) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditSpecialLogon",
                                  (LONG *)(a2 + 200))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 212) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountLogonLogoff_AuditUserDeviceClaims",
                                  (LONG *)(a2 + 208))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 220) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditApplicationGroupManagement",
                                  (LONG *)(a2 + 216))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 228) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditComputerAccountManagement",
                                  (LONG *)(a2 + 224))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditDistributionGroupManagement",
                                  (LONG *)(a2 + 232))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditOtherAccountManagementEvents",
                                  (LONG *)(a2 + 240))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 252) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditSecurityGroupManagement",
                                  (LONG *)(a2 + 248))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 260) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AccountManagement_AuditUserAccountManagement",
                                  (LONG *)(a2 + 256))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 268) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditDPAPIActivity",
                                  (LONG *)(a2 + 264))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 276) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditPNPActivity",
                                  (LONG *)(a2 + 272))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 284) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditProcessCreation",
                                  (LONG *)(a2 + 280))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 292) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditProcessTermination",
                                  (LONG *)(a2 + 288))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 300) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditRPCEvents",
                                  (LONG *)(a2 + 296))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 308) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DetailedTracking_AuditTokenRightAdjusted",
                                  (LONG *)(a2 + 304))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 316) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DSAccess_AuditDetailedDirectoryServiceReplication",
                                  (LONG *)(a2 + 312))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 324) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DSAccess_AuditDirectoryServiceAccess",
                                  (LONG *)(a2 + 320))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 332) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DSAccess_AuditDirectoryServiceChanges",
                                  (LONG *)(a2 + 328))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 340) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DSAccess_AuditDirectoryServiceReplication",
                                  (LONG *)(a2 + 336))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 348) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditApplicationGenerated",
                                  (LONG *)(a2 + 344))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 356) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditCentralAccessPolicyStaging",
                                  (LONG *)(a2 + 352))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 364) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditCertificationServices",
                                  (LONG *)(a2 + 360))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 372) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditDetailedFileShare",
                                  (LONG *)(a2 + 368))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 380) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditFileShare",
                                  (LONG *)(a2 + 376))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 388) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditFileSystem",
                                  (LONG *)(a2 + 384))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 396) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditFilteringPlatformConnection",
                                  (LONG *)(a2 + 392))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 404) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditFilteringPlatformPacketDrop",
                                  (LONG *)(a2 + 400))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 412) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditHandleManipulation",
                                  (LONG *)(a2 + 408))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 420) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditKernelObject",
                                  (LONG *)(a2 + 416))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 428) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditOtherObjectAccessEvents",
                                  (LONG *)(a2 + 424))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 436) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditRegistry",
                                  (LONG *)(a2 + 432))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 444) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditRemovableStorage",
                                  (LONG *)(a2 + 440))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 452) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ObjectAccess_AuditSAM",
                                  (LONG *)(a2 + 448))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 460) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditAuthenticationPolicyChange",
                                  (LONG *)(a2 + 456))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 468) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditAuthorizationPolicyChange",
                                  (LONG *)(a2 + 464))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 476) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditFilteringPlatformPolicyChange",
                                  (LONG *)(a2 + 472))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 484) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditMPSSVCRuleLevelPolicyChange",
                                  (LONG *)(a2 + 480))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 492) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditOtherPolicyChangeEvents",
                                  (LONG *)(a2 + 488))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 500) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PolicyChange_AuditPolicyChange",
                                  (LONG *)(a2 + 496))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 508) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PrivilegeUse_AuditNonSensitivePrivilegeUse",
                                  (LONG *)(a2 + 504))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 516) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PrivilegeUse_AuditOtherPrivilegeUseEvents",
                                  (LONG *)(a2 + 512))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 524) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PrivilegeUse_AuditSensitivePrivilegeUse",
                                  (LONG *)(a2 + 520))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 532) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"System_AuditIPsecDriver",
                                  (LONG *)(a2 + 528))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 540) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"System_AuditOtherSystemEvents",
                                  (LONG *)(a2 + 536))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 548) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"System_AuditSecurityStateChange",
                                  (LONG *)(a2 + 544))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 556) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"System_AuditSecuritySystemExtension",
                                  (LONG *)(a2 + 552))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 564) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"System_AuditSystemIntegrity",
                                  (LONG *)(a2 + 560))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else
          {
            inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( inserted )
            {
              v5 = v11;
              if ( v11 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
            }
            else
            {
              inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 8LL))(v7);
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
          inserted = 1;
        }
      }
    }
    catch ( const exception *v13 )
    {
      v9 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v13[0] + 8LL))(v13[0]);
      TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v12, v9);
      LODWORD(v11) = 1;
      inserted = 1;
    }
    catch ( ... )
    {
      v10 = wil::ResultFromCaughtException(v5);
      TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v12, v10);
      LODWORD(v11) = 1;
      inserted = 1;
    }
  }
  else
  {
    inserted = 4;
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
  return inserted;
}

```

## disassembly

```asm
0x1800613fc  mov     r11, rsp
0x1800613ff  mov     [r11+18h], rsi
0x180061403  push    rdi
0x180061404  push    r14
0x180061406  push    r15
0x180061408  sub     rsp, 0B0h
0x18006140f  mov     rax, cs:__security_cookie
0x180061416  xor     rax, rsp
0x180061419  mov     [rsp+0C8h+var_28], rax
0x180061421  mov     rsi, rdx
0x180061424  mov     rdi, rcx
0x180061427  mov     [rsp+0C8h+var_50], 0
0x18006142f  mov     [rsp+0C8h+var_4C], 0
0x180061434  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18006143b  mov     [r11-80h], rax
0x18006143f  lea     rax, [r11-50h]
0x180061443  mov     [r11-78h], rax
0x180061447  lea     rax, aMdmPolicyConfi_129; "MDM_Policy_Config01_Audit02"
0x18006144e  mov     [r11-70h], rax
0x180061452  lea     rcx, [r11-50h]
0x180061456  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18006145b  mov     eax, cs:dword_180380B68
0x180061461  cmp     eax, 5
0x180061464  jbe     short loc_1800614D7
0x180061466  mov     rdx, 200000000000h
0x180061470  lea     rcx, dword_180380B68
0x180061477  call    _tlgKeywordOn
0x18006147c  test    al, al
0x18006147e  jz      short loc_1800614D7
0x180061480  cmp     [rsp+0C8h+var_4C], 0
0x180061485  jz      short loc_1800614B9
0x180061487  cmp     [rsp+0C8h+var_38], 0
0x18006148f  jnz     short loc_1800614AF
0x180061491  cmp     [rsp+0C8h+var_34], 0
0x180061499  jnz     short loc_1800614AF
0x18006149b  cmp     [rsp+0C8h+var_30], 0
0x1800614a3  jnz     short loc_1800614AF
0x1800614a5  cmp     [rsp+0C8h+var_2C], 0
0x1800614ad  jz      short loc_1800614B9
0x1800614af  lea     r9, [rsp+0C8h+var_38]
0x1800614b7  jmp     short loc_1800614BC
0x1800614b9  xor     r9d, r9d
0x1800614bc  lea     r8, [rsp+0C8h+var_48]
0x1800614c4  lea     rdx, byte_18033B043
0x1800614cb  lea     rcx, dword_180380B68
0x1800614d2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800614d7  cmp     byte ptr [rsi+48h], 0
0x1800614db  jz      loc_1800624B9
0x1800614e1  cmp     byte ptr [rsi+58h], 0
0x1800614e5  jz      loc_1800624B9
0x1800614eb  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800614ef  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800614f3  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1800614fa  lea     rcx, [rsp+0C8h+var_80]; this
0x1800614ff  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180061504  nop
0x180061505  mov     [rsp+0C8h+var_88], 0
0x18006150e  lea     rax, [rsp+0C8h+var_88]
0x180061513  mov     [rsp+0C8h+var_98], rax
0x180061518  mov     [rsp+0C8h+var_A0], 3
0x180061520  mov     [rsp+0C8h+var_A8], 3Dh ; '='
0x180061528  lea     r9, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Audit02_NodeList
0x18006152f  mov     r8, [rsi+40h]
0x180061533  mov     rdx, [rsi+50h]
0x180061537  mov     rcx, rdi
0x18006153a  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18006153f  mov     edi, eax
0x180061541  test    eax, eax
0x180061543  jz      short loc_18006154A
0x180061545  jmp     loc_1800624BE
0x18006154a  lea     rax, [rsp+0C8h+var_88]
0x18006154f  mov     [rsp+0C8h+var_60], rax
0x180061554  mov     r15d, 1
0x18006155a  mov     [rsp+0C8h+var_58], r15b
0x18006155f  mov     r14, [rsp+0C8h+var_88]
0x180061564  test    r14, r14
0x180061567  jnz     short loc_180061571
0x180061569  mov     edi, r15d
0x18006156c  jmp     loc_1800624BE
0x180061571  mov     r9d, 3Dh ; '='; unsigned int
0x180061577  lea     r8, ?MDM_Policy_Config01_Audit02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18006157e  mov     rdx, rsi; struct _MI_Instance *
0x180061581  mov     rcx, r14; this
0x180061584  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180061589  lea     r8, [rsi+60h]; void *
0x18006158d  cmp     [r8+4], r15b
0x180061591  jnz     short loc_1800615C6
0x180061593  lea     rdx, aAccountlogonAu; "AccountLogon_AuditCredentialValidation"
0x18006159a  mov     rcx, r14; this
0x18006159d  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800615a2  mov     edi, eax
0x1800615a4  test    eax, eax
0x1800615a6  jz      short loc_1800615C6
0x1800615a8  mov     rcx, [rsp+0C8h+var_88]
0x1800615ad  test    rcx, rcx
0x1800615b0  jz      short loc_1800615C1
0x1800615b2  mov     rax, [rcx]
0x1800615b5  mov     edx, r15d
0x1800615b8  mov     rax, [rax]
0x1800615bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615c0  nop
0x1800615c1  jmp     loc_1800624BE
0x1800615c6  lea     r8, [rsi+68h]; void *
0x1800615ca  cmp     [r8+4], r15b
0x1800615ce  jnz     short loc_180061603
0x1800615d0  lea     rdx, aAccountlogonAu_0; "AccountLogon_AuditKerberosAuthenticatio"...
0x1800615d7  mov     rcx, r14; this
0x1800615da  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800615df  mov     edi, eax
0x1800615e1  test    eax, eax
0x1800615e3  jz      short loc_180061603
0x1800615e5  mov     rcx, [rsp+0C8h+var_88]
0x1800615ea  test    rcx, rcx
0x1800615ed  jz      short loc_1800615FE
0x1800615ef  mov     rax, [rcx]
0x1800615f2  mov     edx, r15d
0x1800615f5  mov     rax, [rax]
0x1800615f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615fd  nop
0x1800615fe  jmp     loc_1800624BE
0x180061603  lea     r8, [rsi+70h]; void *
0x180061607  cmp     [r8+4], r15b
0x18006160b  jnz     short loc_180061640
0x18006160d  lea     rdx, aAccountlogonAu_2; "AccountLogon_AuditKerberosServiceTicket"...
0x180061614  mov     rcx, r14; this
0x180061617  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006161c  mov     edi, eax
0x18006161e  test    eax, eax
0x180061620  jz      short loc_180061640
0x180061622  mov     rcx, [rsp+0C8h+var_88]
0x180061627  test    rcx, rcx
0x18006162a  jz      short loc_18006163B
0x18006162c  mov     rax, [rcx]
0x18006162f  mov     edx, r15d
0x180061632  mov     rax, [rax]
0x180061635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006163a  nop
0x18006163b  jmp     loc_1800624BE
0x180061640  lea     r8, [rsi+78h]; void *
0x180061644  cmp     [r8+4], r15b
0x180061648  jnz     short loc_18006167D
0x18006164a  lea     rdx, aAccountlogonAu_1; "AccountLogon_AuditOtherAccountLogonEven"...
0x180061651  mov     rcx, r14; this
0x180061654  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180061659  mov     edi, eax
0x18006165b  test    eax, eax
0x18006165d  jz      short loc_18006167D
0x18006165f  mov     rcx, [rsp+0C8h+var_88]
0x180061664  test    rcx, rcx
0x180061667  jz      short loc_180061678
0x180061669  mov     rax, [rcx]
0x18006166c  mov     edx, r15d
0x18006166f  mov     rax, [rax]
0x180061672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061677  nop
0x180061678  jmp     loc_1800624BE
0x18006167d  lea     r8, [rsi+80h]; void *
0x180061684  cmp     [r8+4], r15b
0x180061688  jnz     short loc_1800616BD
0x18006168a  lea     rdx, aAccountlogonlo_1; "AccountLogonLogoff_AuditAccountLockout"
0x180061691  mov     rcx, r14; this
0x180061694  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180061699  mov     edi, eax
0x18006169b  test    eax, eax
0x18006169d  jz      short loc_1800616BD
0x18006169f  mov     rcx, [rsp+0C8h+var_88]
0x1800616a4  test    rcx, rcx
0x1800616a7  jz      short loc_1800616B8
0x1800616a9  mov     rax, [rcx]
0x1800616ac  mov     edx, r15d
0x1800616af  mov     rax, [rax]
0x1800616b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800616b7  nop
0x1800616b8  jmp     loc_1800624BE
0x1800616bd  lea     r8, [rsi+88h]; void *
0x1800616c4  cmp     [r8+4], r15b
0x1800616c8  jnz     short loc_1800616FD
0x1800616ca  lea     rdx, aAccountlogonlo_2; "AccountLogonLogoff_AuditGroupMembership"
0x1800616d1  mov     rcx, r14; this
0x1800616d4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800616d9  mov     edi, eax
0x1800616db  test    eax, eax
0x1800616dd  jz      short loc_1800616FD
0x1800616df  mov     rcx, [rsp+0C8h+var_88]
0x1800616e4  test    rcx, rcx
0x1800616e7  jz      short loc_1800616F8
0x1800616e9  mov     rax, [rcx]
0x1800616ec  mov     edx, r15d
0x1800616ef  mov     rax, [rax]
0x1800616f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800616f7  nop
0x1800616f8  jmp     loc_1800624BE
0x1800616fd  lea     r8, [rsi+90h]; void *
0x180061704  cmp     [r8+4], r15b
0x180061708  jnz     short loc_18006173D
0x18006170a  lea     rdx, aAccountlogonlo_5; "AccountLogonLogoff_AuditIPsecExtendedMo"...
0x180061711  mov     rcx, r14; this
0x180061714  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180061719  mov     edi, eax
0x18006171b  test    eax, eax
0x18006171d  jz      short loc_18006173D
0x18006171f  mov     rcx, [rsp+0C8h+var_88]
0x180061724  test    rcx, rcx
0x180061727  jz      short loc_180061738
0x180061729  mov     rax, [rcx]
0x18006172c  mov     edx, r15d
0x18006172f  mov     rax, [rax]
0x180061732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061737  nop
0x180061738  jmp     loc_1800624BE
0x18006173d  lea     r8, [rsi+98h]; void *
0x180061744  cmp     [r8+4], r15b
0x180061748  jnz     short loc_18006177D
0x18006174a  lea     rdx, aAccountlogonlo_0; "AccountLogonLogoff_AuditIPsecMainMode"
0x180061751  mov     rcx, r14; this
0x180061754  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180061759  mov     edi, eax
0x18006175b  test    eax, eax
0x18006175d  jz      short loc_18006177D
0x18006175f  mov     rcx, [rsp+0C8h+var_88]
0x180061764  test    rcx, rcx
0x180061767  jz      short loc_180061778
0x180061769  mov     rax, [rcx]
0x18006176c  mov     edx, r15d
0x18006176f  mov     rax, [rax]
0x180061772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061777  nop
0x180061778  jmp     loc_1800624BE
0x18006177d  lea     r8, [rsi+0A0h]; void *
0x180061784  cmp     [r8+4], r15b
0x180061788  jnz     short loc_1800617BD
0x18006178a  lea     rdx, aAccountlogonlo_7; "AccountLogonLogoff_AuditIPsecQuickMode"
0x180061791  mov     rcx, r14; this
0x180061794  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180061799  mov     edi, eax
0x18006179b  test    eax, eax
0x18006179d  jz      short loc_1800617BD
0x18006179f  mov     rcx, [rsp+0C8h+var_88]
0x1800617a4  test    rcx, rcx
0x1800617a7  jz      short loc_1800617B8
0x1800617a9  mov     rax, [rcx]
0x1800617ac  mov     edx, r15d
0x1800617af  mov     rax, [rax]
0x1800617b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617b7  nop
0x1800617b8  jmp     loc_1800624BE
0x1800617bd  lea     r8, [rsi+0A8h]; void *
0x1800617c4  cmp     [r8+4], r15b
0x1800617c8  jnz     short loc_1800617FD
0x1800617ca  lea     rdx, aAccountlogonlo_4; "AccountLogonLogoff_AuditLogoff"
0x1800617d1  mov     rcx, r14; this
0x1800617d4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800617d9  mov     edi, eax
0x1800617db  test    eax, eax
0x1800617dd  jz      short loc_1800617FD
0x1800617df  mov     rcx, [rsp+0C8h+var_88]
0x1800617e4  test    rcx, rcx
0x1800617e7  jz      short loc_1800617F8
0x1800617e9  mov     rax, [rcx]
0x1800617ec  mov     edx, r15d
0x1800617ef  mov     rax, [rax]
0x1800617f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617f7  nop
0x1800617f8  jmp     loc_1800624BE
0x1800617fd  lea     r8, [rsi+0B0h]; void *
0x180061804  cmp     [r8+4], r15b
0x180061808  jnz     short loc_18006183D
0x18006180a  lea     rdx, aAccountlogonlo_8; "AccountLogonLogoff_AuditLogon"
0x180061811  mov     rcx, r14; this
0x180061814  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180061819  mov     edi, eax
0x18006181b  test    eax, eax
0x18006181d  jz      short loc_18006183D
0x18006181f  mov     rcx, [rsp+0C8h+var_88]
0x180061824  test    rcx, rcx
0x180061827  jz      short loc_180061838
0x180061829  mov     rax, [rcx]
0x18006182c  mov     edx, r15d
0x18006182f  mov     rax, [rax]
0x180061832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061837  nop
0x180061838  jmp     loc_1800624BE
0x18006183d  lea     r8, [rsi+0B8h]; void *
0x180061844  cmp     [r8+4], r15b
0x180061848  jnz     short loc_18006187D
0x18006184a  lea     rdx, aAccountlogonlo; "AccountLogonLogoff_AuditNetworkPolicySe"...
0x180061851  mov     rcx, r14; this
0x180061854  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180061859  mov     edi, eax
0x18006185b  test    eax, eax
0x18006185d  jz      short loc_18006187D
0x18006185f  mov     rcx, [rsp+0C8h+var_88]
0x180061864  test    rcx, rcx
0x180061867  jz      short loc_180061878
0x180061869  mov     rax, [rcx]
0x18006186c  mov     edx, r15d
0x18006186f  mov     rax, [rax]
0x180061872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061877  nop
0x180061878  jmp     loc_1800624BE
  ... truncated ...
```
