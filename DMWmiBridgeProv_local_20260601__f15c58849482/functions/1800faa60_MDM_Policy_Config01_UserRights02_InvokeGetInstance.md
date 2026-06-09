# MDM_Policy_Config01_UserRights02_InvokeGetInstance

- ea: `0x1800faa60`
- end: `0x1800fb31a`
- name: `MDM_Policy_Config01_UserRights02_InvokeGetInstance`
- size: `2234`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `46`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f9280`

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
- `0x1800faa60`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800face2`: `AccessCredentialManagerAsTrustedCaller`
- `0x1800fad11`: `AccessFromNetwork`
- `0x1800fadfc`: `CreateGlobalObjects`
- `0x1800fae2b`: `CreatePageFile`
- `0x1800fae5a`: `CreatePermanentSharedObjects`
- `0x1800fae89`: `CreateSymbolicLinks`
- `0x1800faeb8`: `CreateToken`
- `0x1800faf16`: `DenyAccessFromNetwork`
- `0x1800faf74`: `DenyRemoteDesktopServicesLogOn`
- `0x1800fafd2`: `GenerateSecurityAudits`
- `0x1800fb001`: `ImpersonateClient`
- `0x1800fb0bd`: `ManageAuditingAndSecurityLog`
- `0x1800faacf`: `MDM_Policy_Config01_UserRights02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_UserRights02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v11[2] = "MDM_Policy_Config01_UserRights02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_180358464,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_116;
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
                       &MDM_Policy_Config01_UserRights02_NodeList,
                       31,
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
      goto LABEL_116;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_UserRights02_NodeList,
      0x1Fu);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_116;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_116;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_116;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_UserRights02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_116;
      goto LABEL_24;
    }
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ActAsPartOfTheOperatingSystem", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowLocalLogOn", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"BackupFilesAndDirectories", (const unsigned __int16 **)&v8) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"CreatePermanentSharedObjects", (const unsigned __int16 **)&v8) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DenyAccessFromNetwork", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DenyLocalLogOn", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DenyRemoteDesktopServicesLogOn", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"EnableDelegation", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"GenerateSecurityAudits", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_VPNv2_User_01_Set_DataEncryption(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ImpersonateClient", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownLocalMachineZoneTemplate(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"IncreaseSchedulingPriority", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownRestrictedSitesZoneTemplate(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"LoadUnloadDeviceDrivers", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"LockMemory", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ManageAuditingAndSecurityLog", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ManageVolume", (const unsigned __int16 **)&v8) == MI_RESULT_OK
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsLockedDownTrustedSitesZoneTemplate(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ModifyFirmwareEnvironment", (const unsigned __int16 **)&v8) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"RestoreFilesAndDirectories", (const unsigned __int16 **)&v8) == MI_RESULT_OK
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
LABEL_116:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180355B57,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800faa60  mov     [rsp+arg_10], rbx
0x1800faa65  push    rsi
0x1800faa66  push    rdi
0x1800faa67  push    r13
0x1800faa69  push    r14
0x1800faa6b  push    r15
0x1800faa6d  sub     rsp, 2F0h
0x1800faa74  mov     rax, cs:__security_cookie
0x1800faa7b  xor     rax, rsp
0x1800faa7e  mov     [rsp+318h+var_38], rax
0x1800faa86  mov     rsi, rdx
0x1800faa89  mov     r15, rcx
0x1800faa8c  xor     ebx, ebx
0x1800faa8e  mov     [rsp+318h+var_2D8], rbx
0x1800faa93  xor     edx, edx; Val
0x1800faa95  mov     r8d, 230h; Size
0x1800faa9b  lea     rcx, [rsp+318h+instance]; void *
0x1800faaa3  call    memset_0
0x1800faaa8  mov     [rsp+318h+var_290], ebx
0x1800faaaf  mov     [rsp+318h+var_28C], bl
0x1800faab6  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800faabd  mov     [rsp+318h+var_2C0], rax
0x1800faac2  lea     rax, [rsp+318h+var_290]
0x1800faaca  mov     [rsp+318h+var_2B8], rax
0x1800faacf  lea     rax, aMdmPolicyConfi_97; "MDM_Policy_Config01_UserRights02"
0x1800faad6  mov     [rsp+318h+var_2B0], rax
0x1800faadb  lea     rcx, [rsp+318h+var_290]
0x1800faae3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800faae8  mov     eax, cs:dword_180380B68
0x1800faaee  cmp     eax, 5
0x1800faaf1  jbe     short loc_1800FAB62
0x1800faaf3  mov     rdx, 200000000000h
0x1800faafd  lea     rcx, dword_180380B68
0x1800fab04  call    _tlgKeywordOn
0x1800fab09  test    al, al
0x1800fab0b  jz      short loc_1800FAB62
0x1800fab0d  cmp     [rsp+318h+var_28C], bl
0x1800fab14  jz      short loc_1800FAB44
0x1800fab16  cmp     [rsp+318h+var_278], ebx
0x1800fab1d  jnz     short loc_1800FAB3A
0x1800fab1f  cmp     [rsp+318h+var_274], ebx
0x1800fab26  jnz     short loc_1800FAB3A
0x1800fab28  cmp     [rsp+318h+var_270], ebx
0x1800fab2f  jnz     short loc_1800FAB3A
0x1800fab31  cmp     [rsp+318h+var_26C], ebx
0x1800fab38  jz      short loc_1800FAB44
0x1800fab3a  lea     r9, [rsp+318h+var_278]
0x1800fab42  jmp     short loc_1800FAB47
0x1800fab44  mov     r9, rbx
0x1800fab47  lea     r8, [rsp+318h+var_288]
0x1800fab4f  lea     rdx, dword_180358464
0x1800fab56  lea     rcx, dword_180380B68
0x1800fab5d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800fab62  cmp     [rsi+48h], bl
0x1800fab65  jz      loc_1800FB278
0x1800fab6b  mov     [rsp+318h+var_2D0], bl
0x1800fab6f  cmp     [rsi+58h], bl
0x1800fab72  jz      loc_1800FB278
0x1800fab78  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800fab7c  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800fab80  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800fab87  lea     rcx, [rsp+318h+var_2C0]; this
0x1800fab8c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800fab91  nop
0x1800fab92  mov     [rsp+318h+var_2C8], rbx
0x1800fab97  lea     rax, [rsp+318h+var_2C8]
0x1800fab9c  mov     [rsp+318h+var_2E8], rax
0x1800faba1  mov     [rsp+318h+var_2F0], ebx
0x1800faba5  mov     [rsp+318h+var_2F8], 1Fh
0x1800fabad  lea     r9, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_UserRights02_NodeList
0x1800fabb4  mov     r8, [rsi+40h]
0x1800fabb8  mov     rdx, [rsi+50h]
0x1800fabbc  mov     rcx, r15
0x1800fabbf  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800fabc4  mov     r14d, eax
0x1800fabc7  test    eax, eax
0x1800fabc9  jz      short loc_1800FABD0
0x1800fabcb  jmp     loc_1800FB27E
0x1800fabd0  lea     rax, [rsp+318h+var_2C8]
0x1800fabd5  mov     [rsp+318h+var_2A0], rax
0x1800fabda  mov     r13d, 1
0x1800fabe0  mov     [rsp+318h+var_298], r13b
0x1800fabe8  mov     rdi, [rsp+318h+var_2C8]
0x1800fabed  test    rdi, rdi
0x1800fabf0  jnz     short loc_1800FABFA
0x1800fabf2  mov     r14d, r13d
0x1800fabf5  jmp     loc_1800FB27E
0x1800fabfa  mov     r9d, 1Fh; unsigned int
0x1800fac00  lea     r8, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800fac07  mov     rdx, rsi; struct _MI_Instance *
0x1800fac0a  mov     rcx, rdi; this
0x1800fac0d  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800fac12  mov     rax, [rdi]
0x1800fac15  mov     rcx, rdi
0x1800fac18  mov     rax, [rax+10h]
0x1800fac1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fac21  mov     r14d, eax
0x1800fac24  test    eax, eax
0x1800fac26  jz      short loc_1800FAC46
0x1800fac28  mov     rcx, [rsp+318h+var_2C8]
0x1800fac2d  test    rcx, rcx
0x1800fac30  jz      short loc_1800FAC41
0x1800fac32  mov     rax, [rcx]
0x1800fac35  mov     edx, r13d
0x1800fac38  mov     rax, [rax]
0x1800fac3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fac40  nop
0x1800fac41  jmp     loc_1800FB27E
0x1800fac46  mov     rax, [rdi]
0x1800fac49  mov     rcx, rdi
0x1800fac4c  mov     rax, [rax+8]
0x1800fac50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fac55  mov     r14d, eax
0x1800fac58  test    eax, eax
0x1800fac5a  jz      short loc_1800FAC7A
0x1800fac5c  mov     rcx, [rsp+318h+var_2C8]
0x1800fac61  test    rcx, rcx
0x1800fac64  jz      short loc_1800FAC75
0x1800fac66  mov     rax, [rcx]
0x1800fac69  mov     edx, r13d
0x1800fac6c  mov     rax, [rax]
0x1800fac6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fac74  nop
0x1800fac75  jmp     loc_1800FB27E
0x1800fac7a  lea     r8, [rsp+318h+instance]; instance
0x1800fac82  lea     rdx, MDM_Policy_Config01_UserRights02_rtti; classDecl
0x1800fac89  mov     rcx, r15; context
0x1800fac8c  call    MI_Context_ConstructInstance
0x1800fac91  mov     r14d, eax
0x1800fac94  test    eax, eax
0x1800fac96  jz      short loc_1800FACB6
0x1800fac98  mov     rcx, [rsp+318h+var_2C8]
0x1800fac9d  test    rcx, rcx
0x1800faca0  jz      short loc_1800FACB1
0x1800faca2  mov     rax, [rcx]
0x1800faca5  mov     edx, r13d
0x1800faca8  mov     rax, [rax]
0x1800facab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800facb0  nop
0x1800facb1  jmp     loc_1800FB27E
0x1800facb6  mov     [rsp+318h+var_2D0], r13b
0x1800facbb  mov     rdx, [rsi+40h]
0x1800facbf  lea     rcx, [rsp+318h+instance]
0x1800facc7  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800faccc  mov     rdx, [rsi+50h]
0x1800facd0  lea     rcx, [rsp+318h+instance]
0x1800facd8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800facdd  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800face2  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1800face9  mov     rcx, rdi; this
0x1800facec  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800facf1  test    eax, eax
0x1800facf3  jnz     short loc_1800FAD0C
0x1800facf5  mov     rdx, [rsp+318h+var_2D8]
0x1800facfa  test    rdx, rdx
0x1800facfd  jz      short loc_1800FAD0C
0x1800facff  lea     rcx, [rsp+318h+instance]
0x1800fad07  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1800fad0c  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fad11  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1800fad18  mov     rcx, rdi; this
0x1800fad1b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fad20  test    eax, eax
0x1800fad22  jnz     short loc_1800FAD3B
0x1800fad24  mov     rdx, [rsp+318h+var_2D8]
0x1800fad29  test    rdx, rdx
0x1800fad2c  jz      short loc_1800FAD3B
0x1800fad2e  lea     rcx, [rsp+318h+instance]
0x1800fad36  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800fad3b  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fad40  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1800fad47  mov     rcx, rdi; this
0x1800fad4a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fad4f  test    eax, eax
0x1800fad51  jnz     short loc_1800FAD6A
0x1800fad53  mov     rdx, [rsp+318h+var_2D8]
0x1800fad58  test    rdx, rdx
0x1800fad5b  jz      short loc_1800FAD6A
0x1800fad5d  lea     rcx, [rsp+318h+instance]
0x1800fad65  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1800fad6a  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fad6f  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1800fad76  mov     rcx, rdi; this
0x1800fad79  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fad7e  test    eax, eax
0x1800fad80  jnz     short loc_1800FAD99
0x1800fad82  mov     rdx, [rsp+318h+var_2D8]
0x1800fad87  test    rdx, rdx
0x1800fad8a  jz      short loc_1800FAD99
0x1800fad8c  lea     rcx, [rsp+318h+instance]
0x1800fad94  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1800fad99  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fad9e  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1800fada5  mov     rcx, rdi; this
0x1800fada8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fadad  test    eax, eax
0x1800fadaf  jnz     short loc_1800FADC8
0x1800fadb1  mov     rdx, [rsp+318h+var_2D8]
0x1800fadb6  test    rdx, rdx
0x1800fadb9  jz      short loc_1800FADC8
0x1800fadbb  lea     rcx, [rsp+318h+instance]
0x1800fadc3  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1800fadc8  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fadcd  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1800fadd4  mov     rcx, rdi; this
0x1800fadd7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800faddc  test    eax, eax
0x1800fadde  jnz     short loc_1800FADF7
0x1800fade0  mov     rdx, [rsp+318h+var_2D8]
0x1800fade5  test    rdx, rdx
0x1800fade8  jz      short loc_1800FADF7
0x1800fadea  lea     rcx, [rsp+318h+instance]
0x1800fadf2  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1800fadf7  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fadfc  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1800fae03  mov     rcx, rdi; this
0x1800fae06  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fae0b  test    eax, eax
0x1800fae0d  jnz     short loc_1800FAE26
0x1800fae0f  mov     rdx, [rsp+318h+var_2D8]
0x1800fae14  test    rdx, rdx
0x1800fae17  jz      short loc_1800FAE26
0x1800fae19  lea     rcx, [rsp+318h+instance]
0x1800fae21  call    MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType
0x1800fae26  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fae2b  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1800fae32  mov     rcx, rdi; this
0x1800fae35  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fae3a  test    eax, eax
0x1800fae3c  jnz     short loc_1800FAE55
0x1800fae3e  mov     rdx, [rsp+318h+var_2D8]
0x1800fae43  test    rdx, rdx
0x1800fae46  jz      short loc_1800FAE55
0x1800fae48  lea     rcx, [rsp+318h+instance]
0x1800fae50  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1800fae55  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fae5a  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1800fae61  mov     rcx, rdi; this
0x1800fae64  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fae69  test    eax, eax
0x1800fae6b  jnz     short loc_1800FAE84
0x1800fae6d  mov     rdx, [rsp+318h+var_2D8]
0x1800fae72  test    rdx, rdx
0x1800fae75  jz      short loc_1800FAE84
0x1800fae77  lea     rcx, [rsp+318h+instance]
0x1800fae7f  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x1800fae84  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fae89  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1800fae90  mov     rcx, rdi; this
0x1800fae93  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fae98  test    eax, eax
0x1800fae9a  jnz     short loc_1800FAEB3
0x1800fae9c  mov     rdx, [rsp+318h+var_2D8]
0x1800faea1  test    rdx, rdx
0x1800faea4  jz      short loc_1800FAEB3
0x1800faea6  lea     rcx, [rsp+318h+instance]
0x1800faeae  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x1800faeb3  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800faeb8  lea     rdx, aCreatetoken; "CreateToken"
0x1800faebf  mov     rcx, rdi; this
0x1800faec2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800faec7  test    eax, eax
0x1800faec9  jnz     short loc_1800FAEE2
0x1800faecb  mov     rdx, [rsp+318h+var_2D8]
0x1800faed0  test    rdx, rdx
0x1800faed3  jz      short loc_1800FAEE2
0x1800faed5  lea     rcx, [rsp+318h+instance]
0x1800faedd  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList
0x1800faee2  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800faee7  lea     rdx, aDebugprograms; "DebugPrograms"
0x1800faeee  mov     rcx, rdi; this
0x1800faef1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800faef6  test    eax, eax
0x1800faef8  jnz     short loc_1800FAF11
0x1800faefa  mov     rdx, [rsp+318h+var_2D8]
0x1800faeff  test    rdx, rdx
0x1800faf02  jz      short loc_1800FAF11
0x1800faf04  lea     rcx, [rsp+318h+instance]
0x1800faf0c  call    MDM_VPNv2_User_01_Set_ProfileXML
0x1800faf11  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800faf16  lea     rdx, aDenyaccessfrom; "DenyAccessFromNetwork"
0x1800faf1d  mov     rcx, rdi; this
0x1800faf20  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800faf25  test    eax, eax
0x1800faf27  jnz     short loc_1800FAF40
0x1800faf29  mov     rdx, [rsp+318h+var_2D8]
0x1800faf2e  test    rdx, rdx
0x1800faf31  jz      short loc_1800FAF40
0x1800faf33  lea     rcx, [rsp+318h+instance]
0x1800faf3b  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate
0x1800faf40  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800faf45  lea     rdx, aDenylocallogon; "DenyLocalLogOn"
0x1800faf4c  mov     rcx, rdi; this
0x1800faf4f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800faf54  test    eax, eax
0x1800faf56  jnz     short loc_1800FAF6F
0x1800faf58  mov     rdx, [rsp+318h+var_2D8]
0x1800faf5d  test    rdx, rdx
0x1800faf60  jz      short loc_1800FAF6F
0x1800faf62  lea     rcx, [rsp+318h+instance]
  ... truncated ...
```
