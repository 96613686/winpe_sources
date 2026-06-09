# MDM_Policy_Result01_UserRights02_InvokeGetInstance

- ea: `0x1801b0ff0`
- end: `0x1801b18aa`
- name: `MDM_Policy_Result01_UserRights02_InvokeGetInstance`
- size: `2234`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `46`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801af810`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005048`
- `0x180005080`
- `0x1800050b8`
- `0x1800050f0`
- `0x180005128`
- `0x180005160`
- `0x180005198`
- `0x1800051d0`
- `0x180005208`
- `0x180005240`
- `0x180005278`
- `0x1800052b0`
- `0x1800052e8`
- `0x180005320`
- `0x180005358`
- `0x180005390`
- `0x1800053c8`
- `0x180005400`
- `0x180005438`
- `0x180005470`
- `0x1800054a8`
- `0x1800054e0`
- `0x180005518`
- `0x180005550`
- `0x180005588`
- `0x1800055c0`
- `0x1800055f8`
- `0x180005630`
- `0x180005668`
- `0x1800056a0`
- `0x1800059e8`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1801b0ff0`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801b1272`: `AccessCredentialManagerAsTrustedCaller`
- `0x1801b12a1`: `AccessFromNetwork`
- `0x1801b138c`: `CreateGlobalObjects`
- `0x1801b13bb`: `CreatePageFile`
- `0x1801b13ea`: `CreatePermanentSharedObjects`
- `0x1801b1419`: `CreateSymbolicLinks`
- `0x1801b1448`: `CreateToken`
- `0x1801b14a6`: `DenyAccessFromNetwork`
- `0x1801b1504`: `DenyRemoteDesktopServicesLogOn`
- `0x1801b1562`: `GenerateSecurityAudits`
- `0x1801b1591`: `ImpersonateClient`
- `0x1801b164d`: `ManageAuditingAndSecurityLog`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_UserRights02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
  WmiRequestHandler *v6; // rdi
  unsigned __int16 *v8; // [rsp+40h] [rbp-2D8h] BYREF
  char v9; // [rsp+48h] [rbp-2D0h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-2C8h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-2C0h] BYREF
  char v12; // [rsp+80h] [rbp-298h]
  int v13; // [rsp+88h] [rbp-290h] BYREF
  char v14; // [rsp+8Ch] [rbp-28Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-288h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-278h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-268h] BYREF

  v8 = 0;
  memset_0(&instance, 0, 0x230u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Result01_UserRights02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &unk_18033ADC8,
      v15,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
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
                         &MDM_Policy_Result01_UserRights02_NodeList,
                         31,
                         0,
                         &v10);
    if ( v5 == MI_RESULT_OK )
    {
      v11[4] = &v10;
      v12 = 1;
      v6 = v10;
      if ( v10 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v10,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_UserRights02_NodeList,
          0x1Fu);
        v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
          if ( v5 )
          {
            if ( v10 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
          }
          else
          {
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_UserRights02_rtti, &instance);
            if ( v5 )
            {
              if ( v10 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
            }
            else
            {
              v9 = 1;
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AccessCredentialManagerAsTrustedCaller",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_VPNv2_User_01_Set_EdpModeId(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"AccessFromNetwork", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ActAsPartOfTheOperatingSystem",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowLocalLogOn", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"BackupFilesAndDirectories",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"ChangeSystemTime", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"CreateGlobalObjects", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"CreatePageFile", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"CreatePermanentSharedObjects",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"CreateSymbolicLinks", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"CreateToken", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DebugPrograms", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_VPNv2_User_01_Set_ProfileXML(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DenyAccessFromNetwork",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DenyLocalLogOn", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DenyRemoteDesktopServicesLogOn",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"EnableDelegation", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"GenerateSecurityAudits",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_VPNv2_User_01_Set_DataEncryption(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"ImpersonateClient", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownLocalMachineZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"IncreaseSchedulingPriority",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownRestrictedSitesZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"LoadUnloadDeviceDrivers",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"LockMemory", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ManageAuditingAndSecurityLog",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"ManageVolume", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsLockedDownTrustedSitesZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ModifyFirmwareEnvironment",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSoftwareWhenSignatureIsInvalid(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"ModifyObjectLabel", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"ProfileSingleProcess", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"RemoteShutdown", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowTrustedSitesZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"RestoreFilesAndDirectories",
                     (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"TakeOwnership", (const unsigned __int16 **)&v8) == MI_RESULT_OK
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
              }
              MI_Instance_Destruct((MI_Instance *)self);
              if ( v10 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
              MI_Instance_Destruct(&instance);
            }
          }
        }
      }
      else
      {
        v5 = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180357F17,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801b0ff0  mov     [rsp+arg_10], rbx
0x1801b0ff5  push    rsi
0x1801b0ff6  push    rdi
0x1801b0ff7  push    r13
0x1801b0ff9  push    r14
0x1801b0ffb  push    r15
0x1801b0ffd  sub     rsp, 2F0h
0x1801b1004  mov     rax, cs:__security_cookie
0x1801b100b  xor     rax, rsp
0x1801b100e  mov     [rsp+318h+var_38], rax
0x1801b1016  mov     rsi, rdx
0x1801b1019  mov     r15, rcx
0x1801b101c  xor     ebx, ebx
0x1801b101e  mov     [rsp+318h+var_2D8], rbx
0x1801b1023  xor     edx, edx; Val
0x1801b1025  mov     r8d, 230h; Size
0x1801b102b  lea     rcx, [rsp+318h+instance]; void *
0x1801b1033  call    memset_0
0x1801b1038  mov     [rsp+318h+var_290], ebx
0x1801b103f  mov     [rsp+318h+var_28C], bl
0x1801b1046  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801b104d  mov     [rsp+318h+var_2C0], rax
0x1801b1052  lea     rax, [rsp+318h+var_290]
0x1801b105a  mov     [rsp+318h+var_2B8], rax
0x1801b105f  lea     rax, aMdmPolicyResul_164; "MDM_Policy_Result01_UserRights02"
0x1801b1066  mov     [rsp+318h+var_2B0], rax
0x1801b106b  lea     rcx, [rsp+318h+var_290]
0x1801b1073  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801b1078  mov     eax, cs:dword_180380B68
0x1801b107e  cmp     eax, 5
0x1801b1081  jbe     short loc_1801B10F2
0x1801b1083  mov     rdx, 200000000000h
0x1801b108d  lea     rcx, dword_180380B68
0x1801b1094  call    _tlgKeywordOn
0x1801b1099  test    al, al
0x1801b109b  jz      short loc_1801B10F2
0x1801b109d  cmp     [rsp+318h+var_28C], bl
0x1801b10a4  jz      short loc_1801B10D4
0x1801b10a6  cmp     [rsp+318h+var_278], ebx
0x1801b10ad  jnz     short loc_1801B10CA
0x1801b10af  cmp     [rsp+318h+var_274], ebx
0x1801b10b6  jnz     short loc_1801B10CA
0x1801b10b8  cmp     [rsp+318h+var_270], ebx
0x1801b10bf  jnz     short loc_1801B10CA
0x1801b10c1  cmp     [rsp+318h+var_26C], ebx
0x1801b10c8  jz      short loc_1801B10D4
0x1801b10ca  lea     r9, [rsp+318h+var_278]
0x1801b10d2  jmp     short loc_1801B10D7
0x1801b10d4  mov     r9, rbx
0x1801b10d7  lea     r8, [rsp+318h+var_288]
0x1801b10df  lea     rdx, unk_18033ADC8
0x1801b10e6  lea     rcx, dword_180380B68
0x1801b10ed  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801b10f2  cmp     [rsi+48h], bl
0x1801b10f5  jz      loc_1801B1808
0x1801b10fb  mov     [rsp+318h+var_2D0], bl
0x1801b10ff  cmp     [rsi+58h], bl
0x1801b1102  jz      loc_1801B1808
0x1801b1108  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801b110c  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801b1110  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1801b1117  lea     rcx, [rsp+318h+var_2C0]; this
0x1801b111c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801b1121  nop
0x1801b1122  mov     [rsp+318h+var_2C8], rbx
0x1801b1127  lea     rax, [rsp+318h+var_2C8]
0x1801b112c  mov     [rsp+318h+var_2E8], rax
0x1801b1131  mov     [rsp+318h+var_2F0], ebx
0x1801b1135  mov     [rsp+318h+var_2F8], 1Fh
0x1801b113d  lea     r9, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_UserRights02_NodeList
0x1801b1144  mov     r8, [rsi+40h]
0x1801b1148  mov     rdx, [rsi+50h]
0x1801b114c  mov     rcx, r15
0x1801b114f  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801b1154  mov     r14d, eax
0x1801b1157  test    eax, eax
0x1801b1159  jz      short loc_1801B1160
0x1801b115b  jmp     loc_1801B180E
0x1801b1160  lea     rax, [rsp+318h+var_2C8]
0x1801b1165  mov     [rsp+318h+var_2A0], rax
0x1801b116a  mov     r13d, 1
0x1801b1170  mov     [rsp+318h+var_298], r13b
0x1801b1178  mov     rdi, [rsp+318h+var_2C8]
0x1801b117d  test    rdi, rdi
0x1801b1180  jnz     short loc_1801B118A
0x1801b1182  mov     r14d, r13d
0x1801b1185  jmp     loc_1801B180E
0x1801b118a  mov     r9d, 1Fh; unsigned int
0x1801b1190  lea     r8, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801b1197  mov     rdx, rsi; struct _MI_Instance *
0x1801b119a  mov     rcx, rdi; this
0x1801b119d  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801b11a2  mov     rax, [rdi]
0x1801b11a5  mov     rcx, rdi
0x1801b11a8  mov     rax, [rax+10h]
0x1801b11ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b11b1  mov     r14d, eax
0x1801b11b4  test    eax, eax
0x1801b11b6  jz      short loc_1801B11D6
0x1801b11b8  mov     rcx, [rsp+318h+var_2C8]
0x1801b11bd  test    rcx, rcx
0x1801b11c0  jz      short loc_1801B11D1
0x1801b11c2  mov     rax, [rcx]
0x1801b11c5  mov     edx, r13d
0x1801b11c8  mov     rax, [rax]
0x1801b11cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b11d0  nop
0x1801b11d1  jmp     loc_1801B180E
0x1801b11d6  mov     rax, [rdi]
0x1801b11d9  mov     rcx, rdi
0x1801b11dc  mov     rax, [rax+8]
0x1801b11e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b11e5  mov     r14d, eax
0x1801b11e8  test    eax, eax
0x1801b11ea  jz      short loc_1801B120A
0x1801b11ec  mov     rcx, [rsp+318h+var_2C8]
0x1801b11f1  test    rcx, rcx
0x1801b11f4  jz      short loc_1801B1205
0x1801b11f6  mov     rax, [rcx]
0x1801b11f9  mov     edx, r13d
0x1801b11fc  mov     rax, [rax]
0x1801b11ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1204  nop
0x1801b1205  jmp     loc_1801B180E
0x1801b120a  lea     r8, [rsp+318h+instance]; instance
0x1801b1212  lea     rdx, MDM_Policy_Result01_UserRights02_rtti; classDecl
0x1801b1219  mov     rcx, r15; context
0x1801b121c  call    MI_Context_ConstructInstance
0x1801b1221  mov     r14d, eax
0x1801b1224  test    eax, eax
0x1801b1226  jz      short loc_1801B1246
0x1801b1228  mov     rcx, [rsp+318h+var_2C8]
0x1801b122d  test    rcx, rcx
0x1801b1230  jz      short loc_1801B1241
0x1801b1232  mov     rax, [rcx]
0x1801b1235  mov     edx, r13d
0x1801b1238  mov     rax, [rax]
0x1801b123b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1240  nop
0x1801b1241  jmp     loc_1801B180E
0x1801b1246  mov     [rsp+318h+var_2D0], r13b
0x1801b124b  mov     rdx, [rsi+40h]
0x1801b124f  lea     rcx, [rsp+318h+instance]
0x1801b1257  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801b125c  mov     rdx, [rsi+50h]
0x1801b1260  lea     rcx, [rsp+318h+instance]
0x1801b1268  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801b126d  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b1272  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1801b1279  mov     rcx, rdi; this
0x1801b127c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b1281  test    eax, eax
0x1801b1283  jnz     short loc_1801B129C
0x1801b1285  mov     rdx, [rsp+318h+var_2D8]
0x1801b128a  test    rdx, rdx
0x1801b128d  jz      short loc_1801B129C
0x1801b128f  lea     rcx, [rsp+318h+instance]
0x1801b1297  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1801b129c  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b12a1  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1801b12a8  mov     rcx, rdi; this
0x1801b12ab  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b12b0  test    eax, eax
0x1801b12b2  jnz     short loc_1801B12CB
0x1801b12b4  mov     rdx, [rsp+318h+var_2D8]
0x1801b12b9  test    rdx, rdx
0x1801b12bc  jz      short loc_1801B12CB
0x1801b12be  lea     rcx, [rsp+318h+instance]
0x1801b12c6  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1801b12cb  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b12d0  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1801b12d7  mov     rcx, rdi; this
0x1801b12da  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b12df  test    eax, eax
0x1801b12e1  jnz     short loc_1801B12FA
0x1801b12e3  mov     rdx, [rsp+318h+var_2D8]
0x1801b12e8  test    rdx, rdx
0x1801b12eb  jz      short loc_1801B12FA
0x1801b12ed  lea     rcx, [rsp+318h+instance]
0x1801b12f5  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1801b12fa  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b12ff  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1801b1306  mov     rcx, rdi; this
0x1801b1309  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b130e  test    eax, eax
0x1801b1310  jnz     short loc_1801B1329
0x1801b1312  mov     rdx, [rsp+318h+var_2D8]
0x1801b1317  test    rdx, rdx
0x1801b131a  jz      short loc_1801B1329
0x1801b131c  lea     rcx, [rsp+318h+instance]
0x1801b1324  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1801b1329  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b132e  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1801b1335  mov     rcx, rdi; this
0x1801b1338  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b133d  test    eax, eax
0x1801b133f  jnz     short loc_1801B1358
0x1801b1341  mov     rdx, [rsp+318h+var_2D8]
0x1801b1346  test    rdx, rdx
0x1801b1349  jz      short loc_1801B1358
0x1801b134b  lea     rcx, [rsp+318h+instance]
0x1801b1353  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1801b1358  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b135d  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1801b1364  mov     rcx, rdi; this
0x1801b1367  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b136c  test    eax, eax
0x1801b136e  jnz     short loc_1801B1387
0x1801b1370  mov     rdx, [rsp+318h+var_2D8]
0x1801b1375  test    rdx, rdx
0x1801b1378  jz      short loc_1801B1387
0x1801b137a  lea     rcx, [rsp+318h+instance]
0x1801b1382  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1801b1387  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b138c  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1801b1393  mov     rcx, rdi; this
0x1801b1396  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b139b  test    eax, eax
0x1801b139d  jnz     short loc_1801B13B6
0x1801b139f  mov     rdx, [rsp+318h+var_2D8]
0x1801b13a4  test    rdx, rdx
0x1801b13a7  jz      short loc_1801B13B6
0x1801b13a9  lea     rcx, [rsp+318h+instance]
0x1801b13b1  call    MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType
0x1801b13b6  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b13bb  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1801b13c2  mov     rcx, rdi; this
0x1801b13c5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b13ca  test    eax, eax
0x1801b13cc  jnz     short loc_1801B13E5
0x1801b13ce  mov     rdx, [rsp+318h+var_2D8]
0x1801b13d3  test    rdx, rdx
0x1801b13d6  jz      short loc_1801B13E5
0x1801b13d8  lea     rcx, [rsp+318h+instance]
0x1801b13e0  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1801b13e5  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b13ea  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1801b13f1  mov     rcx, rdi; this
0x1801b13f4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b13f9  test    eax, eax
0x1801b13fb  jnz     short loc_1801B1414
0x1801b13fd  mov     rdx, [rsp+318h+var_2D8]
0x1801b1402  test    rdx, rdx
0x1801b1405  jz      short loc_1801B1414
0x1801b1407  lea     rcx, [rsp+318h+instance]
0x1801b140f  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x1801b1414  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b1419  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1801b1420  mov     rcx, rdi; this
0x1801b1423  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b1428  test    eax, eax
0x1801b142a  jnz     short loc_1801B1443
0x1801b142c  mov     rdx, [rsp+318h+var_2D8]
0x1801b1431  test    rdx, rdx
0x1801b1434  jz      short loc_1801B1443
0x1801b1436  lea     rcx, [rsp+318h+instance]
0x1801b143e  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x1801b1443  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b1448  lea     rdx, aCreatetoken; "CreateToken"
0x1801b144f  mov     rcx, rdi; this
0x1801b1452  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b1457  test    eax, eax
0x1801b1459  jnz     short loc_1801B1472
0x1801b145b  mov     rdx, [rsp+318h+var_2D8]
0x1801b1460  test    rdx, rdx
0x1801b1463  jz      short loc_1801B1472
0x1801b1465  lea     rcx, [rsp+318h+instance]
0x1801b146d  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList
0x1801b1472  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b1477  lea     rdx, aDebugprograms; "DebugPrograms"
0x1801b147e  mov     rcx, rdi; this
0x1801b1481  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b1486  test    eax, eax
0x1801b1488  jnz     short loc_1801B14A1
0x1801b148a  mov     rdx, [rsp+318h+var_2D8]
0x1801b148f  test    rdx, rdx
0x1801b1492  jz      short loc_1801B14A1
0x1801b1494  lea     rcx, [rsp+318h+instance]
0x1801b149c  call    MDM_VPNv2_User_01_Set_ProfileXML
0x1801b14a1  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b14a6  lea     rdx, aDenyaccessfrom; "DenyAccessFromNetwork"
0x1801b14ad  mov     rcx, rdi; this
0x1801b14b0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b14b5  test    eax, eax
0x1801b14b7  jnz     short loc_1801B14D0
0x1801b14b9  mov     rdx, [rsp+318h+var_2D8]
0x1801b14be  test    rdx, rdx
0x1801b14c1  jz      short loc_1801B14D0
0x1801b14c3  lea     rcx, [rsp+318h+instance]
0x1801b14cb  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate
0x1801b14d0  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b14d5  lea     rdx, aDenylocallogon; "DenyLocalLogOn"
0x1801b14dc  mov     rcx, rdi; this
0x1801b14df  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b14e4  test    eax, eax
0x1801b14e6  jnz     short loc_1801B14FF
0x1801b14e8  mov     rdx, [rsp+318h+var_2D8]
0x1801b14ed  test    rdx, rdx
0x1801b14f0  jz      short loc_1801B14FF
0x1801b14f2  lea     rcx, [rsp+318h+instance]
  ... truncated ...
```
