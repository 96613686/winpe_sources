# MDM_Policy_Result01_UserRights02_InvokeEnumerateInstances

- ea: `0x1801b0778`
- end: `0x1801b11d5`
- name: `MDM_Policy_Result01_UserRights02_InvokeEnumerateInstances`
- size: `2653`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `44`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801af9b0`

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
- `0x1801b0778`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801b0a66`: `AccessCredentialManagerAsTrustedCaller`
- `0x1801b0a9f`: `AccessFromNetwork`
- `0x1801b0bbc`: `CreateGlobalObjects`
- `0x1801b0bf5`: `CreatePageFile`
- `0x1801b0c2e`: `CreatePermanentSharedObjects`
- `0x1801b0c67`: `CreateSymbolicLinks`
- `0x1801b0ca0`: `CreateToken`
- `0x1801b0d12`: `DenyAccessFromNetwork`
- `0x1801b0d84`: `DenyRemoteDesktopServicesLogOn`
- `0x1801b0df6`: `GenerateSecurityAudits`
- `0x1801b0e2f`: `ImpersonateClient`
- `0x1801b0f13`: `ManageAuditingAndSecurityLog`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_UserRights02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r15d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r14d
  __int64 v10; // [rsp+40h] [rbp-2D8h] BYREF
  char v11; // [rsp+48h] [rbp-2D0h]
  WmiRequestHandlerAdd *v12; // [rsp+50h] [rbp-2C8h] BYREF
  _QWORD v13[5]; // [rsp+58h] [rbp-2C0h] BYREF
  char v14; // [rsp+80h] [rbp-298h]
  int v15; // [rsp+88h] [rbp-290h] BYREF
  char v16; // [rsp+8Ch] [rbp-28Ch]
  _BYTE v17[16]; // [rsp+90h] [rbp-288h] BYREF
  _DWORD v18[4]; // [rsp+A0h] [rbp-278h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-268h] BYREF

  memset_0(&instance, 0, 0x230u);
  v11 = 0;
  v10 = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = &TelemetryEventWriter::`vftable';
  v13[1] = &v15;
  v13[2] = "MDM_Policy_Result01_UserRights02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v5 = v18;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180344FE9,
      v17,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v13, v4);
  v12 = 0;
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_UserRights02_NodeList,
         0x1Fu,
         2,
         &v12);
  if ( !v6 )
  {
    v13[4] = &v12;
    v14 = 1;
    v7 = v12;
    if ( v12 )
    {
      v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v6 )
      {
        if ( v12 )
          (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v12 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v7 + 33) - *((_QWORD *)v7 + 32)) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_UserRights02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_125;
            }
            v11 = 1;
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &v10)
              && v10 )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, v10);
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"UserRights",
                    &v10)
              && v10 )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, v10);
            }
            if ( a2 != 1 )
            {
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccessCredentialManagerAsTrustedCaller",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_User_01_Set_EdpModeId(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AccessFromNetwork",
                      &v10)
                && v10 )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ActAsPartOfTheOperatingSystem",
                      &v10)
                && v10 )
              {
                MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowLocalLogOn",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"BackupFilesAndDirectories",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ChangeSystemTime",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"CreateGlobalObjects",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"CreatePageFile",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"CreatePermanentSharedObjects",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"CreateSymbolicLinks",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"CreateToken",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DebugPrograms",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_User_01_Set_ProfileXML(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DenyAccessFromNetwork",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DenyLocalLogOn",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DenyRemoteDesktopServicesLogOn",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"EnableDelegation",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"GenerateSecurityAudits",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_User_01_Set_DataEncryption(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ImpersonateClient",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownLocalMachineZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"IncreaseSchedulingPriority",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownRestrictedSitesZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"LoadUnloadDeviceDrivers",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"LockMemory",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ManageAuditingAndSecurityLog",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ManageVolume",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsLockedDownTrustedSitesZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ModifyFirmwareEnvironment",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSoftwareWhenSignatureIsInvalid(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ModifyObjectLabel",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ProfileSingleProcess",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RemoteShutdown",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowTrustedSitesZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RestoreFilesAndDirectories",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"TakeOwnership",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
              }
            }
            MI_Instance_Destruct((MI_Instance *)self);
            MI_Instance_Destruct(&instance);
            v11 = 0;
          }
          if ( v12 )
          {
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
            v12 = 0;
          }
        }
      }
    }
    else
    {
      v6 = 1;
    }
  }
LABEL_125:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v13, "EnumerateInstancesEnd", v6);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_180351CA4,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return v6;
}

```

## disassembly

```asm
0x1801b0778  mov     [rsp+arg_8], rbx
0x1801b077d  mov     [rsp+arg_10], rsi
0x1801b0782  push    rdi
0x1801b0783  push    r12
0x1801b0785  push    r13
0x1801b0787  push    r14
0x1801b0789  push    r15
0x1801b078b  sub     rsp, 2F0h
0x1801b0792  mov     rax, cs:__security_cookie
0x1801b0799  xor     rax, rsp
0x1801b079c  mov     [rsp+318h+var_38], rax
0x1801b07a4  mov     r13b, dl
0x1801b07a7  mov     r12, rcx
0x1801b07aa  xor     edx, edx; Val
0x1801b07ac  mov     r8d, 230h; Size
0x1801b07b2  lea     rcx, [rsp+318h+instance]; void *
0x1801b07ba  call    memset_0
0x1801b07bf  xor     edi, edi
0x1801b07c1  mov     [rsp+318h+var_2D0], dil
0x1801b07c6  mov     [rsp+318h+var_2D8], rdi
0x1801b07cb  mov     [rsp+318h+var_290], edi
0x1801b07d2  mov     [rsp+318h+var_28C], dil
0x1801b07da  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801b07e1  mov     [rsp+318h+var_2C0], rax
0x1801b07e6  lea     rax, [rsp+318h+var_290]
0x1801b07ee  mov     [rsp+318h+var_2B8], rax
0x1801b07f3  lea     rax, aMdmPolicyResul_164; "MDM_Policy_Result01_UserRights02"
0x1801b07fa  mov     [rsp+318h+var_2B0], rax
0x1801b07ff  lea     rcx, [rsp+318h+var_290]
0x1801b0807  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801b080c  mov     eax, cs:dword_180380B68
0x1801b0812  cmp     eax, 5
0x1801b0815  jbe     short loc_1801B0887
0x1801b0817  mov     rdx, 200000000000h
0x1801b0821  lea     rcx, dword_180380B68
0x1801b0828  call    _tlgKeywordOn
0x1801b082d  test    al, al
0x1801b082f  jz      short loc_1801B0887
0x1801b0831  cmp     [rsp+318h+var_28C], dil
0x1801b0839  jz      short loc_1801B0869
0x1801b083b  cmp     [rsp+318h+var_278], edi
0x1801b0842  jnz     short loc_1801B085F
0x1801b0844  cmp     [rsp+318h+var_274], edi
0x1801b084b  jnz     short loc_1801B085F
0x1801b084d  cmp     [rsp+318h+var_270], edi
0x1801b0854  jnz     short loc_1801B085F
0x1801b0856  cmp     [rsp+318h+var_26C], edi
0x1801b085d  jz      short loc_1801B0869
0x1801b085f  lea     r9, [rsp+318h+var_278]
0x1801b0867  jmp     short loc_1801B086C
0x1801b0869  mov     r9, rdi
0x1801b086c  lea     r8, [rsp+318h+var_288]
0x1801b0874  lea     rdx, byte_180344FE9
0x1801b087b  lea     rcx, dword_180380B68
0x1801b0882  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801b0887  lea     rcx, [rsp+318h+var_2C0]; this
0x1801b088c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1801b0891  nop
0x1801b0892  mov     [rsp+318h+var_2C8], rdi
0x1801b0897  lea     rax, [rsp+318h+var_2C8]
0x1801b089c  mov     [rsp+318h+var_2E8], rax
0x1801b08a1  mov     [rsp+318h+var_2F0], 2
0x1801b08a9  mov     [rsp+318h+var_2F8], 1Fh
0x1801b08b1  lea     r9, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_UserRights02_NodeList
0x1801b08b8  xor     r8d, r8d
0x1801b08bb  xor     edx, edx
0x1801b08bd  mov     rcx, r12
0x1801b08c0  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801b08c5  mov     r15d, eax
0x1801b08c8  test    eax, eax
0x1801b08ca  jz      short loc_1801B08D1
0x1801b08cc  jmp     loc_1801B1135
0x1801b08d1  lea     rbx, [rsp+318h+var_2C8]
0x1801b08d6  mov     [rsp+318h+var_2A0], rbx
0x1801b08db  mov     r14d, 1
0x1801b08e1  mov     [rsp+318h+var_298], r14b
0x1801b08e9  mov     rsi, [rsp+318h+var_2C8]
0x1801b08ee  test    rsi, rsi
0x1801b08f1  jnz     short loc_1801B08FB
0x1801b08f3  mov     r15d, r14d
0x1801b08f6  jmp     loc_1801B1135
0x1801b08fb  mov     rax, [rsi]
0x1801b08fe  mov     rcx, rsi
0x1801b0901  mov     rax, [rax+10h]
0x1801b0905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b090a  mov     r15d, eax
0x1801b090d  test    eax, eax
0x1801b090f  jz      short loc_1801B092F
0x1801b0911  mov     rcx, [rsp+318h+var_2C8]
0x1801b0916  test    rcx, rcx
0x1801b0919  jz      short loc_1801B092A
0x1801b091b  mov     rax, [rcx]
0x1801b091e  mov     edx, r14d
0x1801b0921  mov     rax, [rax]
0x1801b0924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0929  nop
0x1801b092a  jmp     loc_1801B1135
0x1801b092f  mov     rax, [rsi]
0x1801b0932  mov     rcx, rsi
0x1801b0935  mov     rax, [rax+8]
0x1801b0939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b093e  mov     r15d, eax
0x1801b0941  test    eax, eax
0x1801b0943  jz      short loc_1801B0963
0x1801b0945  mov     rcx, [rsp+318h+var_2C8]
0x1801b094a  test    rcx, rcx
0x1801b094d  jz      short loc_1801B095E
0x1801b094f  mov     rax, [rcx]
0x1801b0952  mov     edx, r14d
0x1801b0955  mov     rax, [rax]
0x1801b0958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b095d  nop
0x1801b095e  jmp     loc_1801B1135
0x1801b0963  mov     r14d, edi
0x1801b0966  mov     rax, [rsi+108h]
0x1801b096d  sub     rax, [rsi+100h]
0x1801b0974  sar     rax, 4
0x1801b0978  cmp     r14d, eax
0x1801b097b  jnb     loc_1801B10FD
0x1801b0981  lea     r8, [rsp+318h+instance]; instance
0x1801b0989  lea     rdx, MDM_Policy_Result01_UserRights02_rtti; classDecl
0x1801b0990  mov     rcx, r12; context
0x1801b0993  call    MI_Context_ConstructInstance
0x1801b0998  mov     r15d, eax
0x1801b099b  test    eax, eax
0x1801b099d  jz      short loc_1801B09BF
0x1801b099f  mov     rcx, [rbx]
0x1801b09a2  test    rcx, rcx
0x1801b09a5  jz      short loc_1801B09BA
0x1801b09a7  mov     rax, [rcx]
0x1801b09aa  mov     edx, 1
0x1801b09af  mov     rax, [rax]
0x1801b09b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b09b7  mov     [rbx], rdi
0x1801b09ba  jmp     loc_1801B1135
0x1801b09bf  mov     [rsp+318h+var_2D0], 1
0x1801b09c4  mov     rax, [rsi]
0x1801b09c7  lea     r9, [rsp+318h+var_2D8]
0x1801b09cc  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x1801b09d3  mov     edx, r14d
0x1801b09d6  mov     rcx, rsi
0x1801b09d9  mov     rax, [rax+18h]
0x1801b09dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b09e2  test    eax, eax
0x1801b09e4  jnz     short loc_1801B09FD
0x1801b09e6  mov     rdx, [rsp+318h+var_2D8]
0x1801b09eb  test    rdx, rdx
0x1801b09ee  jz      short loc_1801B09FD
0x1801b09f0  lea     rcx, [rsp+318h+instance]
0x1801b09f8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801b09fd  mov     rax, [rsi]
0x1801b0a00  lea     r9, [rsp+318h+var_2D8]
0x1801b0a05  lea     r8, aUserrights; "UserRights"
0x1801b0a0c  mov     edx, r14d
0x1801b0a0f  mov     rcx, rsi
0x1801b0a12  mov     rax, [rax+18h]
0x1801b0a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0a1b  test    eax, eax
0x1801b0a1d  jnz     short loc_1801B0A36
0x1801b0a1f  mov     rdx, [rsp+318h+var_2D8]
0x1801b0a24  test    rdx, rdx
0x1801b0a27  jz      short loc_1801B0A36
0x1801b0a29  lea     rcx, [rsp+318h+instance]
0x1801b0a31  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801b0a36  cmp     r13b, 1
0x1801b0a3a  jnz     short loc_1801B0A5E
0x1801b0a3c  lea     rdx, [rsp+318h+instance]
0x1801b0a44  mov     rcx, r12; self
0x1801b0a47  call    MI_Instance_Destruct
0x1801b0a4c  lea     rcx, [rsp+318h+instance]; self
0x1801b0a54  call    MI_Instance_Destruct
0x1801b0a59  jmp     loc_1801B10F0
0x1801b0a5e  mov     rax, [rsi]
0x1801b0a61  lea     r9, [rsp+318h+var_2D8]
0x1801b0a66  lea     r8, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1801b0a6d  mov     edx, r14d
0x1801b0a70  mov     rcx, rsi
0x1801b0a73  mov     rax, [rax+18h]
0x1801b0a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0a7c  test    eax, eax
0x1801b0a7e  jnz     short loc_1801B0A97
0x1801b0a80  mov     rdx, [rsp+318h+var_2D8]
0x1801b0a85  test    rdx, rdx
0x1801b0a88  jz      short loc_1801B0A97
0x1801b0a8a  lea     rcx, [rsp+318h+instance]
0x1801b0a92  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1801b0a97  mov     rax, [rsi]
0x1801b0a9a  lea     r9, [rsp+318h+var_2D8]
0x1801b0a9f  lea     r8, aAccessfromnetw; "AccessFromNetwork"
0x1801b0aa6  mov     edx, r14d
0x1801b0aa9  mov     rcx, rsi
0x1801b0aac  mov     rax, [rax+18h]
0x1801b0ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0ab5  test    eax, eax
0x1801b0ab7  jnz     short loc_1801B0AD0
0x1801b0ab9  mov     rdx, [rsp+318h+var_2D8]
0x1801b0abe  test    rdx, rdx
0x1801b0ac1  jz      short loc_1801B0AD0
0x1801b0ac3  lea     rcx, [rsp+318h+instance]
0x1801b0acb  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1801b0ad0  mov     rax, [rsi]
0x1801b0ad3  lea     r9, [rsp+318h+var_2D8]
0x1801b0ad8  lea     r8, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1801b0adf  mov     edx, r14d
0x1801b0ae2  mov     rcx, rsi
0x1801b0ae5  mov     rax, [rax+18h]
0x1801b0ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0aee  test    eax, eax
0x1801b0af0  jnz     short loc_1801B0B09
0x1801b0af2  mov     rdx, [rsp+318h+var_2D8]
0x1801b0af7  test    rdx, rdx
0x1801b0afa  jz      short loc_1801B0B09
0x1801b0afc  lea     rcx, [rsp+318h+instance]
0x1801b0b04  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1801b0b09  mov     rax, [rsi]
0x1801b0b0c  lea     r9, [rsp+318h+var_2D8]
0x1801b0b11  lea     r8, aAllowlocallogo; "AllowLocalLogOn"
0x1801b0b18  mov     edx, r14d
0x1801b0b1b  mov     rcx, rsi
0x1801b0b1e  mov     rax, [rax+18h]
0x1801b0b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0b27  test    eax, eax
0x1801b0b29  jnz     short loc_1801B0B42
0x1801b0b2b  mov     rdx, [rsp+318h+var_2D8]
0x1801b0b30  test    rdx, rdx
0x1801b0b33  jz      short loc_1801B0B42
0x1801b0b35  lea     rcx, [rsp+318h+instance]
0x1801b0b3d  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1801b0b42  mov     rax, [rsi]
0x1801b0b45  lea     r9, [rsp+318h+var_2D8]
0x1801b0b4a  lea     r8, aBackupfilesand; "BackupFilesAndDirectories"
0x1801b0b51  mov     edx, r14d
0x1801b0b54  mov     rcx, rsi
0x1801b0b57  mov     rax, [rax+18h]
0x1801b0b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0b60  test    eax, eax
0x1801b0b62  jnz     short loc_1801B0B7B
0x1801b0b64  mov     rdx, [rsp+318h+var_2D8]
0x1801b0b69  test    rdx, rdx
0x1801b0b6c  jz      short loc_1801B0B7B
0x1801b0b6e  lea     rcx, [rsp+318h+instance]
0x1801b0b76  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1801b0b7b  mov     rax, [rsi]
0x1801b0b7e  lea     r9, [rsp+318h+var_2D8]
0x1801b0b83  lea     r8, aChangesystemti; "ChangeSystemTime"
0x1801b0b8a  mov     edx, r14d
0x1801b0b8d  mov     rcx, rsi
0x1801b0b90  mov     rax, [rax+18h]
0x1801b0b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0b99  test    eax, eax
0x1801b0b9b  jnz     short loc_1801B0BB4
0x1801b0b9d  mov     rdx, [rsp+318h+var_2D8]
0x1801b0ba2  test    rdx, rdx
0x1801b0ba5  jz      short loc_1801B0BB4
0x1801b0ba7  lea     rcx, [rsp+318h+instance]
0x1801b0baf  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1801b0bb4  mov     rax, [rsi]
0x1801b0bb7  lea     r9, [rsp+318h+var_2D8]
0x1801b0bbc  lea     r8, aCreateglobalob; "CreateGlobalObjects"
0x1801b0bc3  mov     edx, r14d
0x1801b0bc6  mov     rcx, rsi
0x1801b0bc9  mov     rax, [rax+18h]
0x1801b0bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0bd2  test    eax, eax
0x1801b0bd4  jnz     short loc_1801B0BED
0x1801b0bd6  mov     rdx, [rsp+318h+var_2D8]
0x1801b0bdb  test    rdx, rdx
0x1801b0bde  jz      short loc_1801B0BED
0x1801b0be0  lea     rcx, [rsp+318h+instance]
0x1801b0be8  call    MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType
0x1801b0bed  mov     rax, [rsi]
0x1801b0bf0  lea     r9, [rsp+318h+var_2D8]
0x1801b0bf5  lea     r8, aCreatepagefile; "CreatePageFile"
0x1801b0bfc  mov     edx, r14d
0x1801b0bff  mov     rcx, rsi
0x1801b0c02  mov     rax, [rax+18h]
0x1801b0c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0c0b  test    eax, eax
0x1801b0c0d  jnz     short loc_1801B0C26
0x1801b0c0f  mov     rdx, [rsp+318h+var_2D8]
0x1801b0c14  test    rdx, rdx
0x1801b0c17  jz      short loc_1801B0C26
0x1801b0c19  lea     rcx, [rsp+318h+instance]
0x1801b0c21  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1801b0c26  mov     rax, [rsi]
0x1801b0c29  lea     r9, [rsp+318h+var_2D8]
0x1801b0c2e  lea     r8, aCreatepermanen; "CreatePermanentSharedObjects"
0x1801b0c35  mov     edx, r14d
0x1801b0c38  mov     rcx, rsi
0x1801b0c3b  mov     rax, [rax+18h]
0x1801b0c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0c44  test    eax, eax
0x1801b0c46  jnz     short loc_1801B0C5F
0x1801b0c48  mov     rdx, [rsp+318h+var_2D8]
0x1801b0c4d  test    rdx, rdx
0x1801b0c50  jz      short loc_1801B0C5F
0x1801b0c52  lea     rcx, [rsp+318h+instance]
0x1801b0c5a  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x1801b0c5f  mov     rax, [rsi]
0x1801b0c62  lea     r9, [rsp+318h+var_2D8]
  ... truncated ...
```
