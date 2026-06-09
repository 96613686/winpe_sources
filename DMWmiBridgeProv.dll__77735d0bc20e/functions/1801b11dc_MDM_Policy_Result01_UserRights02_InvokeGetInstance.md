# MDM_Policy_Result01_UserRights02_InvokeGetInstance

- ea: `0x1801b11dc`
- end: `0x1801b1a95`
- name: `MDM_Policy_Result01_UserRights02_InvokeGetInstance`
- size: `2233`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `46`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801af9f0`

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
- `0x1801b11dc`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801b145e`: `AccessCredentialManagerAsTrustedCaller`
- `0x1801b148d`: `AccessFromNetwork`
- `0x1801b1578`: `CreateGlobalObjects`
- `0x1801b15a7`: `CreatePageFile`
- `0x1801b15d6`: `CreatePermanentSharedObjects`
- `0x1801b1605`: `CreateSymbolicLinks`
- `0x1801b1634`: `CreateToken`
- `0x1801b1692`: `DenyAccessFromNetwork`
- `0x1801b16f0`: `DenyRemoteDesktopServicesLogOn`
- `0x1801b174e`: `GenerateSecurityAudits`
- `0x1801b177d`: `ImpersonateClient`
- `0x1801b1839`: `ManageAuditingAndSecurityLog`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_UserRights02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
    v5 = CreateRequestHandlerInstance(
           (__int64)self,
           (wchar_t *)a2[1].serverName,
           (const unsigned __int16 *)a2[1].ft,
           (struct WmiNodeInfo *)&MDM_Policy_Result01_UserRights02_NodeList,
           0x1Fu,
           0,
           &v10);
    if ( !v5 )
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
        v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowLocalLogOn",
                                    (const unsigned __int16 **)&v8)
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"CreatePageFile",
                                    (const unsigned __int16 **)&v8)
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"CreateToken",
                                    (const unsigned __int16 **)&v8)
                && v8 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DebugPrograms",
                                    (const unsigned __int16 **)&v8)
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DenyLocalLogOn",
                                    (const unsigned __int16 **)&v8)
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"LockMemory",
                                    (const unsigned __int16 **)&v8)
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ManageVolume",
                                    (const unsigned __int16 **)&v8)
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RemoteShutdown",
                                    (const unsigned __int16 **)&v8)
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"TakeOwnership",
                                    (const unsigned __int16 **)&v8)
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
        v5 = 1;
      }
    }
  }
  else
  {
    v5 = 4;
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
  return v5;
}

```

## disassembly

```asm
0x1801b11dc  mov     [rsp+arg_10], rbx
0x1801b11e1  push    rsi
0x1801b11e2  push    rdi
0x1801b11e3  push    r13
0x1801b11e5  push    r14
0x1801b11e7  push    r15
0x1801b11e9  sub     rsp, 2F0h
0x1801b11f0  mov     rax, cs:__security_cookie
0x1801b11f7  xor     rax, rsp
0x1801b11fa  mov     [rsp+318h+var_38], rax
0x1801b1202  mov     rsi, rdx
0x1801b1205  mov     r15, rcx
0x1801b1208  xor     ebx, ebx
0x1801b120a  mov     [rsp+318h+var_2D8], rbx
0x1801b120f  xor     edx, edx; Val
0x1801b1211  mov     r8d, 230h; Size
0x1801b1217  lea     rcx, [rsp+318h+instance]; void *
0x1801b121f  call    memset_0
0x1801b1224  mov     [rsp+318h+var_290], ebx
0x1801b122b  mov     [rsp+318h+var_28C], bl
0x1801b1232  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801b1239  mov     [rsp+318h+var_2C0], rax
0x1801b123e  lea     rax, [rsp+318h+var_290]
0x1801b1246  mov     [rsp+318h+var_2B8], rax
0x1801b124b  lea     rax, aMdmPolicyResul_164; "MDM_Policy_Result01_UserRights02"
0x1801b1252  mov     [rsp+318h+var_2B0], rax
0x1801b1257  lea     rcx, [rsp+318h+var_290]
0x1801b125f  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801b1264  mov     eax, cs:dword_180380B68
0x1801b126a  cmp     eax, 5
0x1801b126d  jbe     short loc_1801B12DE
0x1801b126f  mov     rdx, 200000000000h
0x1801b1279  lea     rcx, dword_180380B68
0x1801b1280  call    _tlgKeywordOn
0x1801b1285  test    al, al
0x1801b1287  jz      short loc_1801B12DE
0x1801b1289  cmp     [rsp+318h+var_28C], bl
0x1801b1290  jz      short loc_1801B12C0
0x1801b1292  cmp     [rsp+318h+var_278], ebx
0x1801b1299  jnz     short loc_1801B12B6
0x1801b129b  cmp     [rsp+318h+var_274], ebx
0x1801b12a2  jnz     short loc_1801B12B6
0x1801b12a4  cmp     [rsp+318h+var_270], ebx
0x1801b12ab  jnz     short loc_1801B12B6
0x1801b12ad  cmp     [rsp+318h+var_26C], ebx
0x1801b12b4  jz      short loc_1801B12C0
0x1801b12b6  lea     r9, [rsp+318h+var_278]
0x1801b12be  jmp     short loc_1801B12C3
0x1801b12c0  mov     r9, rbx
0x1801b12c3  lea     r8, [rsp+318h+var_288]
0x1801b12cb  lea     rdx, unk_18033ADC8
0x1801b12d2  lea     rcx, dword_180380B68
0x1801b12d9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801b12de  cmp     [rsi+48h], bl
0x1801b12e1  jz      loc_1801B19F4
0x1801b12e7  mov     [rsp+318h+var_2D0], bl
0x1801b12eb  cmp     [rsi+58h], bl
0x1801b12ee  jz      loc_1801B19F4
0x1801b12f4  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801b12f8  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801b12fc  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1801b1303  lea     rcx, [rsp+318h+var_2C0]; this
0x1801b1308  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801b130d  nop
0x1801b130e  mov     [rsp+318h+var_2C8], rbx
0x1801b1313  lea     rax, [rsp+318h+var_2C8]
0x1801b1318  mov     [rsp+318h+var_2E8], rax
0x1801b131d  mov     [rsp+318h+var_2F0], ebx
0x1801b1321  mov     [rsp+318h+var_2F8], 1Fh
0x1801b1329  lea     r9, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_UserRights02_NodeList
0x1801b1330  mov     r8, [rsi+40h]
0x1801b1334  mov     rdx, [rsi+50h]
0x1801b1338  mov     rcx, r15
0x1801b133b  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801b1340  mov     r14d, eax
0x1801b1343  test    eax, eax
0x1801b1345  jz      short loc_1801B134C
0x1801b1347  jmp     loc_1801B19FA
0x1801b134c  lea     rax, [rsp+318h+var_2C8]
0x1801b1351  mov     [rsp+318h+var_2A0], rax
0x1801b1356  mov     r13d, 1
0x1801b135c  mov     [rsp+318h+var_298], r13b
0x1801b1364  mov     rdi, [rsp+318h+var_2C8]
0x1801b1369  test    rdi, rdi
0x1801b136c  jnz     short loc_1801B1376
0x1801b136e  mov     r14d, r13d
0x1801b1371  jmp     loc_1801B19FA
0x1801b1376  mov     r9d, 1Fh; unsigned int
0x1801b137c  lea     r8, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801b1383  mov     rdx, rsi; struct _MI_Instance *
0x1801b1386  mov     rcx, rdi; this
0x1801b1389  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801b138e  mov     rax, [rdi]
0x1801b1391  mov     rcx, rdi
0x1801b1394  mov     rax, [rax+10h]
0x1801b1398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b139d  mov     r14d, eax
0x1801b13a0  test    eax, eax
0x1801b13a2  jz      short loc_1801B13C2
0x1801b13a4  mov     rcx, [rsp+318h+var_2C8]
0x1801b13a9  test    rcx, rcx
0x1801b13ac  jz      short loc_1801B13BD
0x1801b13ae  mov     rax, [rcx]
0x1801b13b1  mov     edx, r13d
0x1801b13b4  mov     rax, [rax]
0x1801b13b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b13bc  nop
0x1801b13bd  jmp     loc_1801B19FA
0x1801b13c2  mov     rax, [rdi]
0x1801b13c5  mov     rcx, rdi
0x1801b13c8  mov     rax, [rax+8]
0x1801b13cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b13d1  mov     r14d, eax
0x1801b13d4  test    eax, eax
0x1801b13d6  jz      short loc_1801B13F6
0x1801b13d8  mov     rcx, [rsp+318h+var_2C8]
0x1801b13dd  test    rcx, rcx
0x1801b13e0  jz      short loc_1801B13F1
0x1801b13e2  mov     rax, [rcx]
0x1801b13e5  mov     edx, r13d
0x1801b13e8  mov     rax, [rax]
0x1801b13eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b13f0  nop
0x1801b13f1  jmp     loc_1801B19FA
0x1801b13f6  lea     r8, [rsp+318h+instance]; instance
0x1801b13fe  lea     rdx, MDM_Policy_Result01_UserRights02_rtti; classDecl
0x1801b1405  mov     rcx, r15; context
0x1801b1408  call    MI_Context_ConstructInstance
0x1801b140d  mov     r14d, eax
0x1801b1410  test    eax, eax
0x1801b1412  jz      short loc_1801B1432
0x1801b1414  mov     rcx, [rsp+318h+var_2C8]
0x1801b1419  test    rcx, rcx
0x1801b141c  jz      short loc_1801B142D
0x1801b141e  mov     rax, [rcx]
0x1801b1421  mov     edx, r13d
0x1801b1424  mov     rax, [rax]
0x1801b1427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b142c  nop
0x1801b142d  jmp     loc_1801B19FA
0x1801b1432  mov     [rsp+318h+var_2D0], r13b
0x1801b1437  mov     rdx, [rsi+40h]
0x1801b143b  lea     rcx, [rsp+318h+instance]
0x1801b1443  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801b1448  mov     rdx, [rsi+50h]
0x1801b144c  lea     rcx, [rsp+318h+instance]
0x1801b1454  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801b1459  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b145e  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1801b1465  mov     rcx, rdi; this
0x1801b1468  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b146d  test    eax, eax
0x1801b146f  jnz     short loc_1801B1488
0x1801b1471  mov     rdx, [rsp+318h+var_2D8]
0x1801b1476  test    rdx, rdx
0x1801b1479  jz      short loc_1801B1488
0x1801b147b  lea     rcx, [rsp+318h+instance]
0x1801b1483  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1801b1488  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b148d  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1801b1494  mov     rcx, rdi; this
0x1801b1497  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b149c  test    eax, eax
0x1801b149e  jnz     short loc_1801B14B7
0x1801b14a0  mov     rdx, [rsp+318h+var_2D8]
0x1801b14a5  test    rdx, rdx
0x1801b14a8  jz      short loc_1801B14B7
0x1801b14aa  lea     rcx, [rsp+318h+instance]
0x1801b14b2  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1801b14b7  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b14bc  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1801b14c3  mov     rcx, rdi; this
0x1801b14c6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b14cb  test    eax, eax
0x1801b14cd  jnz     short loc_1801B14E6
0x1801b14cf  mov     rdx, [rsp+318h+var_2D8]
0x1801b14d4  test    rdx, rdx
0x1801b14d7  jz      short loc_1801B14E6
0x1801b14d9  lea     rcx, [rsp+318h+instance]
0x1801b14e1  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1801b14e6  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b14eb  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1801b14f2  mov     rcx, rdi; this
0x1801b14f5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b14fa  test    eax, eax
0x1801b14fc  jnz     short loc_1801B1515
0x1801b14fe  mov     rdx, [rsp+318h+var_2D8]
0x1801b1503  test    rdx, rdx
0x1801b1506  jz      short loc_1801B1515
0x1801b1508  lea     rcx, [rsp+318h+instance]
0x1801b1510  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1801b1515  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b151a  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1801b1521  mov     rcx, rdi; this
0x1801b1524  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b1529  test    eax, eax
0x1801b152b  jnz     short loc_1801B1544
0x1801b152d  mov     rdx, [rsp+318h+var_2D8]
0x1801b1532  test    rdx, rdx
0x1801b1535  jz      short loc_1801B1544
0x1801b1537  lea     rcx, [rsp+318h+instance]
0x1801b153f  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1801b1544  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b1549  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1801b1550  mov     rcx, rdi; this
0x1801b1553  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b1558  test    eax, eax
0x1801b155a  jnz     short loc_1801B1573
0x1801b155c  mov     rdx, [rsp+318h+var_2D8]
0x1801b1561  test    rdx, rdx
0x1801b1564  jz      short loc_1801B1573
0x1801b1566  lea     rcx, [rsp+318h+instance]
0x1801b156e  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1801b1573  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b1578  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1801b157f  mov     rcx, rdi; this
0x1801b1582  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b1587  test    eax, eax
0x1801b1589  jnz     short loc_1801B15A2
0x1801b158b  mov     rdx, [rsp+318h+var_2D8]
0x1801b1590  test    rdx, rdx
0x1801b1593  jz      short loc_1801B15A2
0x1801b1595  lea     rcx, [rsp+318h+instance]
0x1801b159d  call    MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType
0x1801b15a2  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b15a7  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1801b15ae  mov     rcx, rdi; this
0x1801b15b1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b15b6  test    eax, eax
0x1801b15b8  jnz     short loc_1801B15D1
0x1801b15ba  mov     rdx, [rsp+318h+var_2D8]
0x1801b15bf  test    rdx, rdx
0x1801b15c2  jz      short loc_1801B15D1
0x1801b15c4  lea     rcx, [rsp+318h+instance]
0x1801b15cc  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1801b15d1  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b15d6  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1801b15dd  mov     rcx, rdi; this
0x1801b15e0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b15e5  test    eax, eax
0x1801b15e7  jnz     short loc_1801B1600
0x1801b15e9  mov     rdx, [rsp+318h+var_2D8]
0x1801b15ee  test    rdx, rdx
0x1801b15f1  jz      short loc_1801B1600
0x1801b15f3  lea     rcx, [rsp+318h+instance]
0x1801b15fb  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x1801b1600  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b1605  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1801b160c  mov     rcx, rdi; this
0x1801b160f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b1614  test    eax, eax
0x1801b1616  jnz     short loc_1801B162F
0x1801b1618  mov     rdx, [rsp+318h+var_2D8]
0x1801b161d  test    rdx, rdx
0x1801b1620  jz      short loc_1801B162F
0x1801b1622  lea     rcx, [rsp+318h+instance]
0x1801b162a  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x1801b162f  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b1634  lea     rdx, aCreatetoken; "CreateToken"
0x1801b163b  mov     rcx, rdi; this
0x1801b163e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b1643  test    eax, eax
0x1801b1645  jnz     short loc_1801B165E
0x1801b1647  mov     rdx, [rsp+318h+var_2D8]
0x1801b164c  test    rdx, rdx
0x1801b164f  jz      short loc_1801B165E
0x1801b1651  lea     rcx, [rsp+318h+instance]
0x1801b1659  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList
0x1801b165e  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b1663  lea     rdx, aDebugprograms; "DebugPrograms"
0x1801b166a  mov     rcx, rdi; this
0x1801b166d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b1672  test    eax, eax
0x1801b1674  jnz     short loc_1801B168D
0x1801b1676  mov     rdx, [rsp+318h+var_2D8]
0x1801b167b  test    rdx, rdx
0x1801b167e  jz      short loc_1801B168D
0x1801b1680  lea     rcx, [rsp+318h+instance]
0x1801b1688  call    MDM_VPNv2_User_01_Set_ProfileXML
0x1801b168d  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b1692  lea     rdx, aDenyaccessfrom; "DenyAccessFromNetwork"
0x1801b1699  mov     rcx, rdi; this
0x1801b169c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b16a1  test    eax, eax
0x1801b16a3  jnz     short loc_1801B16BC
0x1801b16a5  mov     rdx, [rsp+318h+var_2D8]
0x1801b16aa  test    rdx, rdx
0x1801b16ad  jz      short loc_1801B16BC
0x1801b16af  lea     rcx, [rsp+318h+instance]
0x1801b16b7  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate
0x1801b16bc  lea     r8, [rsp+318h+var_2D8]; unsigned __int16 **
0x1801b16c1  lea     rdx, aDenylocallogon; "DenyLocalLogOn"
0x1801b16c8  mov     rcx, rdi; this
0x1801b16cb  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b16d0  test    eax, eax
0x1801b16d2  jnz     short loc_1801B16EB
0x1801b16d4  mov     rdx, [rsp+318h+var_2D8]
0x1801b16d9  test    rdx, rdx
0x1801b16dc  jz      short loc_1801B16EB
0x1801b16de  lea     rcx, [rsp+318h+instance]
  ... truncated ...
```
