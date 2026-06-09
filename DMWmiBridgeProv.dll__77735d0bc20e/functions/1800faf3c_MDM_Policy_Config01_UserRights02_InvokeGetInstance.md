# MDM_Policy_Config01_UserRights02_InvokeGetInstance

- ea: `0x1800faf3c`
- end: `0x1800fb7f5`
- name: `MDM_Policy_Config01_UserRights02_InvokeGetInstance`
- size: `2233`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `46`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f9750`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004e74`
- `0x180004eac`
- `0x180004ee4`
- `0x180004f1c`
- `0x180004f54`
- `0x180004f8c`
- `0x180004fc4`
- `0x180004ffc`
- `0x180005034`
- `0x18000506c`
- `0x1800050a4`
- `0x1800050dc`
- `0x180005114`
- `0x18000514c`
- `0x180005184`
- `0x1800051bc`
- `0x1800051f4`
- `0x18000522c`
- `0x180005264`
- `0x18000529c`
- `0x1800052d4`
- `0x18000530c`
- `0x180005344`
- `0x18000537c`
- `0x1800053b4`
- `0x1800053ec`
- `0x180005424`
- `0x18000545c`
- `0x180005494`
- `0x1800054cc`
- `0x180005814`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800faf3c`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800fb1be`: `AccessCredentialManagerAsTrustedCaller`
- `0x1800fb1ed`: `AccessFromNetwork`
- `0x1800fb2d8`: `CreateGlobalObjects`
- `0x1800fb307`: `CreatePageFile`
- `0x1800fb336`: `CreatePermanentSharedObjects`
- `0x1800fb365`: `CreateSymbolicLinks`
- `0x1800fb394`: `CreateToken`
- `0x1800fb3f2`: `DenyAccessFromNetwork`
- `0x1800fb450`: `DenyRemoteDesktopServicesLogOn`
- `0x1800fb4ae`: `GenerateSecurityAudits`
- `0x1800fb4dd`: `ImpersonateClient`
- `0x1800fb599`: `ManageAuditingAndSecurityLog`
- `0x1800fafab`: `MDM_Policy_Config01_UserRights02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_UserRights02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
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
    v5 = 4;
    goto LABEL_116;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v11,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v10 = 0;
  v5 = CreateRequestHandlerInstance(
         (__int64)self,
         (wchar_t *)a2[1].serverName,
         (const unsigned __int16 *)a2[1].ft,
         (struct WmiNodeInfo *)&MDM_Policy_Config01_UserRights02_NodeList,
         0x1Fu,
         0,
         &v10);
  if ( !v5 )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = 1;
      goto LABEL_116;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_UserRights02_NodeList,
      0x1Fu);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_116;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_116;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccessCredentialManagerAsTrustedCaller",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_VPNv2_User_01_Set_EdpModeId(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AccessFromNetwork",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ActAsPartOfTheOperatingSystem",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"AllowLocalLogOn", (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"BackupFilesAndDirectories",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ChangeSystemTime",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"CreateGlobalObjects",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"CreatePageFile", (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"CreatePermanentSharedObjects",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"CreateSymbolicLinks",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"CreateToken", (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"DebugPrograms", (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_VPNv2_User_01_Set_ProfileXML(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DenyAccessFromNetwork",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"DenyLocalLogOn", (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DenyRemoteDesktopServicesLogOn",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"EnableDelegation",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"GenerateSecurityAudits",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_VPNv2_User_01_Set_DataEncryption(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ImpersonateClient",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownLocalMachineZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"IncreaseSchedulingPriority",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownRestrictedSitesZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"LoadUnloadDeviceDrivers",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"LockMemory", (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ManageAuditingAndSecurityLog",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"ManageVolume", (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsLockedDownTrustedSitesZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ModifyFirmwareEnvironment",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSoftwareWhenSignatureIsInvalid(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ModifyObjectLabel",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ProfileSingleProcess",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"RemoteShutdown", (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowTrustedSitesZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"RestoreFilesAndDirectories",
                          (const unsigned __int16 **)&v8)
      && v8 )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"TakeOwnership", (const unsigned __int16 **)&v8)
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
  return v5;
}

```

## disassembly

```asm
0x1800faf3c  mov     [rsp+arg_10], rbx
0x1800faf41  push    rsi
0x1800faf42  push    rdi
0x1800faf43  push    r13
0x1800faf45  push    r14
0x1800faf47  push    r15
0x1800faf49  sub     rsp, 2F0h
0x1800faf50  mov     rax, cs:__security_cookie
0x1800faf57  xor     rax, rsp
0x1800faf5a  mov     [rsp+318h+var_38], rax
0x1800faf62  mov     rsi, rdx
0x1800faf65  mov     r15, rcx
0x1800faf68  xor     ebx, ebx
0x1800faf6a  mov     [rsp+318h+var_2D8], rbx
0x1800faf6f  xor     edx, edx; Val
0x1800faf71  mov     r8d, 230h; Size
0x1800faf77  lea     rcx, [rsp+318h+instance]; void *
0x1800faf7f  call    memset_0
0x1800faf84  mov     [rsp+318h+var_290], ebx
0x1800faf8b  mov     [rsp+318h+var_28C], bl
0x1800faf92  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800faf99  mov     [rsp+318h+var_2C0], rax
0x1800faf9e  lea     rax, [rsp+318h+var_290]
0x1800fafa6  mov     [rsp+318h+var_2B8], rax
0x1800fafab  lea     rax, aMdmPolicyConfi_97; "MDM_Policy_Config01_UserRights02"
0x1800fafb2  mov     [rsp+318h+var_2B0], rax
0x1800fafb7  lea     rcx, [rsp+318h+var_290]
0x1800fafbf  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800fafc4  mov     eax, cs:dword_180380B68
0x1800fafca  cmp     eax, 5
0x1800fafcd  jbe     short loc_1800FB03E
0x1800fafcf  mov     rdx, 200000000000h
0x1800fafd9  lea     rcx, dword_180380B68
0x1800fafe0  call    _tlgKeywordOn
0x1800fafe5  test    al, al
0x1800fafe7  jz      short loc_1800FB03E
0x1800fafe9  cmp     [rsp+318h+var_28C], bl
0x1800faff0  jz      short loc_1800FB020
0x1800faff2  cmp     [rsp+318h+var_278], ebx
0x1800faff9  jnz     short loc_1800FB016
0x1800faffb  cmp     [rsp+318h+var_274], ebx
0x1800fb002  jnz     short loc_1800FB016
0x1800fb004  cmp     [rsp+318h+var_270], ebx
0x1800fb00b  jnz     short loc_1800FB016
0x1800fb00d  cmp     [rsp+318h+var_26C], ebx
0x1800fb014  jz      short loc_1800FB020
0x1800fb016  lea     r9, [rsp+318h+var_278]
0x1800fb01e  jmp     short loc_1800FB023
0x1800fb020  mov     r9, rbx
0x1800fb023  lea     r8, [rsp+318h+var_288]
0x1800fb02b  lea     rdx, dword_180358464
0x1800fb032  lea     rcx, dword_180380B68
0x1800fb039  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800fb03e  cmp     [rsi+48h], bl
0x1800fb041  jz      loc_1800FB754
0x1800fb047  mov     [rsp+318h+var_2D0], bl
0x1800fb04b  cmp     [rsi+58h], bl
0x1800fb04e  jz      loc_1800FB754
0x1800fb054  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800fb058  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800fb05c  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800fb063  lea     rcx, [rsp+318h+var_2C0]; this
0x1800fb068  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800fb06d  nop
0x1800fb06e  mov     [rsp+318h+var_2C8], rbx
0x1800fb073  lea     rax, [rsp+318h+var_2C8]
0x1800fb078  mov     [rsp+318h+var_2E8], rax
0x1800fb07d  mov     [rsp+318h+var_2F0], ebx
0x1800fb081  mov     [rsp+318h+var_2F8], 1Fh
0x1800fb089  lea     r9, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_UserRights02_NodeList
0x1800fb090  mov     r8, [rsi+40h]
0x1800fb094  mov     rdx, [rsi+50h]
0x1800fb098  mov     rcx, r15
0x1800fb09b  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800fb0a0  mov     r14d, eax
0x1800fb0a3  test    eax, eax
0x1800fb0a5  jz      short loc_1800FB0AC
0x1800fb0a7  jmp     loc_1800FB75A
0x1800fb0ac  lea     rax, [rsp+318h+var_2C8]
0x1800fb0b1  mov     [rsp+318h+var_2A0], rax
0x1800fb0b6  mov     r13d, 1
0x1800fb0bc  mov     [rsp+318h+var_298], r13b
0x1800fb0c4  mov     rdi, [rsp+318h+var_2C8]
0x1800fb0c9  test    rdi, rdi
0x1800fb0cc  jnz     short loc_1800FB0D6
0x1800fb0ce  mov     r14d, r13d
0x1800fb0d1  jmp     loc_1800FB75A
0x1800fb0d6  mov     r9d, 1Fh; unsigned int
0x1800fb0dc  lea     r8, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800fb0e3  mov     rdx, rsi; struct _MI_Instance *
0x1800fb0e6  mov     rcx, rdi; this
0x1800fb0e9  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800fb0ee  mov     rax, [rdi]
0x1800fb0f1  mov     rcx, rdi
0x1800fb0f4  mov     rax, [rax+10h]
0x1800fb0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb0fd  mov     r14d, eax
0x1800fb100  test    eax, eax
0x1800fb102  jz      short loc_1800FB122
0x1800fb104  mov     rcx, [rsp+318h+var_2C8]
0x1800fb109  test    rcx, rcx
0x1800fb10c  jz      short loc_1800FB11D
0x1800fb10e  mov     rax, [rcx]
0x1800fb111  mov     edx, r13d
0x1800fb114  mov     rax, [rax]
0x1800fb117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb11c  nop
0x1800fb11d  jmp     loc_1800FB75A
0x1800fb122  mov     rax, [rdi]
0x1800fb125  mov     rcx, rdi
0x1800fb128  mov     rax, [rax+8]
0x1800fb12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb131  mov     r14d, eax
0x1800fb134  test    eax, eax
0x1800fb136  jz      short loc_1800FB156
0x1800fb138  mov     rcx, [rsp+318h+var_2C8]
0x1800fb13d  test    rcx, rcx
0x1800fb140  jz      short loc_1800FB151
0x1800fb142  mov     rax, [rcx]
0x1800fb145  mov     edx, r13d
0x1800fb148  mov     rax, [rax]
0x1800fb14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb150  nop
0x1800fb151  jmp     loc_1800FB75A
0x1800fb156  lea     r8, [rsp+318h+instance]; instance
0x1800fb15e  lea     rdx, MDM_Policy_Config01_UserRights02_rtti; classDecl
0x1800fb165  mov     rcx, r15; context
0x1800fb168  call    MI_Context_ConstructInstance
0x1800fb16d  mov     r14d, eax
0x1800fb170  test    eax, eax
0x1800fb172  jz      short loc_1800FB192
0x1800fb174  mov     rcx, [rsp+318h+var_2C8]
0x1800fb179  test    rcx, rcx
0x1800fb17c  jz      short loc_1800FB18D
0x1800fb17e  mov     rax, [rcx]
0x1800fb181  mov     edx, r13d
0x1800fb184  mov     rax, [rax]
0x1800fb187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb18c  nop
0x1800fb18d  jmp     loc_1800FB75A
0x1800fb192  mov     [rsp+318h+var_2D0], r13b
0x1800fb197  mov     rdx, [rsi+40h]
0x1800fb19b  lea     rcx, [rsp+318h+instance]
0x1800fb1a3  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800fb1a8  mov     rdx, [rsi+50h]
0x1800fb1ac  lea     rcx, [rsp+318h+instance]
0x1800fb1b4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800fb1b9  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb1be  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1800fb1c5  mov     rcx, rdi; this
0x1800fb1c8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb1cd  test    eax, eax
0x1800fb1cf  jnz     short loc_1800FB1E8
0x1800fb1d1  mov     rdx, [rsp+318h+var_2D8]
0x1800fb1d6  test    rdx, rdx
0x1800fb1d9  jz      short loc_1800FB1E8
0x1800fb1db  lea     rcx, [rsp+318h+instance]
0x1800fb1e3  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1800fb1e8  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb1ed  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1800fb1f4  mov     rcx, rdi; this
0x1800fb1f7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb1fc  test    eax, eax
0x1800fb1fe  jnz     short loc_1800FB217
0x1800fb200  mov     rdx, [rsp+318h+var_2D8]
0x1800fb205  test    rdx, rdx
0x1800fb208  jz      short loc_1800FB217
0x1800fb20a  lea     rcx, [rsp+318h+instance]
0x1800fb212  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800fb217  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb21c  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1800fb223  mov     rcx, rdi; this
0x1800fb226  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb22b  test    eax, eax
0x1800fb22d  jnz     short loc_1800FB246
0x1800fb22f  mov     rdx, [rsp+318h+var_2D8]
0x1800fb234  test    rdx, rdx
0x1800fb237  jz      short loc_1800FB246
0x1800fb239  lea     rcx, [rsp+318h+instance]
0x1800fb241  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1800fb246  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb24b  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1800fb252  mov     rcx, rdi; this
0x1800fb255  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb25a  test    eax, eax
0x1800fb25c  jnz     short loc_1800FB275
0x1800fb25e  mov     rdx, [rsp+318h+var_2D8]
0x1800fb263  test    rdx, rdx
0x1800fb266  jz      short loc_1800FB275
0x1800fb268  lea     rcx, [rsp+318h+instance]
0x1800fb270  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1800fb275  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb27a  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1800fb281  mov     rcx, rdi; this
0x1800fb284  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb289  test    eax, eax
0x1800fb28b  jnz     short loc_1800FB2A4
0x1800fb28d  mov     rdx, [rsp+318h+var_2D8]
0x1800fb292  test    rdx, rdx
0x1800fb295  jz      short loc_1800FB2A4
0x1800fb297  lea     rcx, [rsp+318h+instance]
0x1800fb29f  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1800fb2a4  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb2a9  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1800fb2b0  mov     rcx, rdi; this
0x1800fb2b3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb2b8  test    eax, eax
0x1800fb2ba  jnz     short loc_1800FB2D3
0x1800fb2bc  mov     rdx, [rsp+318h+var_2D8]
0x1800fb2c1  test    rdx, rdx
0x1800fb2c4  jz      short loc_1800FB2D3
0x1800fb2c6  lea     rcx, [rsp+318h+instance]
0x1800fb2ce  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1800fb2d3  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb2d8  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1800fb2df  mov     rcx, rdi; this
0x1800fb2e2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb2e7  test    eax, eax
0x1800fb2e9  jnz     short loc_1800FB302
0x1800fb2eb  mov     rdx, [rsp+318h+var_2D8]
0x1800fb2f0  test    rdx, rdx
0x1800fb2f3  jz      short loc_1800FB302
0x1800fb2f5  lea     rcx, [rsp+318h+instance]
0x1800fb2fd  call    MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType
0x1800fb302  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb307  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1800fb30e  mov     rcx, rdi; this
0x1800fb311  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb316  test    eax, eax
0x1800fb318  jnz     short loc_1800FB331
0x1800fb31a  mov     rdx, [rsp+318h+var_2D8]
0x1800fb31f  test    rdx, rdx
0x1800fb322  jz      short loc_1800FB331
0x1800fb324  lea     rcx, [rsp+318h+instance]
0x1800fb32c  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1800fb331  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb336  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1800fb33d  mov     rcx, rdi; this
0x1800fb340  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb345  test    eax, eax
0x1800fb347  jnz     short loc_1800FB360
0x1800fb349  mov     rdx, [rsp+318h+var_2D8]
0x1800fb34e  test    rdx, rdx
0x1800fb351  jz      short loc_1800FB360
0x1800fb353  lea     rcx, [rsp+318h+instance]
0x1800fb35b  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x1800fb360  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb365  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1800fb36c  mov     rcx, rdi; this
0x1800fb36f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb374  test    eax, eax
0x1800fb376  jnz     short loc_1800FB38F
0x1800fb378  mov     rdx, [rsp+318h+var_2D8]
0x1800fb37d  test    rdx, rdx
0x1800fb380  jz      short loc_1800FB38F
0x1800fb382  lea     rcx, [rsp+318h+instance]
0x1800fb38a  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x1800fb38f  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb394  lea     rdx, aCreatetoken; "CreateToken"
0x1800fb39b  mov     rcx, rdi; this
0x1800fb39e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb3a3  test    eax, eax
0x1800fb3a5  jnz     short loc_1800FB3BE
0x1800fb3a7  mov     rdx, [rsp+318h+var_2D8]
0x1800fb3ac  test    rdx, rdx
0x1800fb3af  jz      short loc_1800FB3BE
0x1800fb3b1  lea     rcx, [rsp+318h+instance]
0x1800fb3b9  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList
0x1800fb3be  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb3c3  lea     rdx, aDebugprograms; "DebugPrograms"
0x1800fb3ca  mov     rcx, rdi; this
0x1800fb3cd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb3d2  test    eax, eax
0x1800fb3d4  jnz     short loc_1800FB3ED
0x1800fb3d6  mov     rdx, [rsp+318h+var_2D8]
0x1800fb3db  test    rdx, rdx
0x1800fb3de  jz      short loc_1800FB3ED
0x1800fb3e0  lea     rcx, [rsp+318h+instance]
0x1800fb3e8  call    MDM_VPNv2_User_01_Set_ProfileXML
0x1800fb3ed  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb3f2  lea     rdx, aDenyaccessfrom; "DenyAccessFromNetwork"
0x1800fb3f9  mov     rcx, rdi; this
0x1800fb3fc  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb401  test    eax, eax
0x1800fb403  jnz     short loc_1800FB41C
0x1800fb405  mov     rdx, [rsp+318h+var_2D8]
0x1800fb40a  test    rdx, rdx
0x1800fb40d  jz      short loc_1800FB41C
0x1800fb40f  lea     rcx, [rsp+318h+instance]
0x1800fb417  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate
0x1800fb41c  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1800fb421  lea     rdx, aDenylocallogon; "DenyLocalLogOn"
0x1800fb428  mov     rcx, rdi; this
0x1800fb42b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800fb430  test    eax, eax
0x1800fb432  jnz     short loc_1800FB44B
0x1800fb434  mov     rdx, [rsp+318h+var_2D8]
0x1800fb439  test    rdx, rdx
0x1800fb43c  jz      short loc_1800FB44B
0x1800fb43e  lea     rcx, [rsp+318h+instance]
  ... truncated ...
```
