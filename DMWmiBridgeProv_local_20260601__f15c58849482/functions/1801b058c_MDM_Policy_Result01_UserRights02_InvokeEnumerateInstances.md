# MDM_Policy_Result01_UserRights02_InvokeEnumerateInstances

- ea: `0x1801b058c`
- end: `0x1801b0fea`
- name: `MDM_Policy_Result01_UserRights02_InvokeEnumerateInstances`
- size: `2654`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `44`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801af7e0`

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
- `0x1801b058c`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801b087a`: `AccessCredentialManagerAsTrustedCaller`
- `0x1801b08b3`: `AccessFromNetwork`
- `0x1801b09d0`: `CreateGlobalObjects`
- `0x1801b0a09`: `CreatePageFile`
- `0x1801b0a42`: `CreatePermanentSharedObjects`
- `0x1801b0a7b`: `CreateSymbolicLinks`
- `0x1801b0ab4`: `CreateToken`
- `0x1801b0b26`: `DenyAccessFromNetwork`
- `0x1801b0b98`: `DenyRemoteDesktopServicesLogOn`
- `0x1801b0c0a`: `GenerateSecurityAudits`
- `0x1801b0c43`: `ImpersonateClient`
- `0x1801b0d27`: `ManageAuditingAndSecurityLog`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_UserRights02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r15d
  _QWORD *v7; // rsi
  unsigned int i; // r14d
  __int64 v10; // [rsp+40h] [rbp-2D8h] BYREF
  char v11; // [rsp+48h] [rbp-2D0h]
  _QWORD *v12; // [rsp+50h] [rbp-2C8h] BYREF
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
  v6 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Result01_UserRights02_NodeList, 31, 2, &v12);
  if ( v6 == MI_RESULT_OK )
  {
    v13[4] = &v12;
    v14 = 1;
    v7 = v12;
    if ( v12 )
    {
      v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
      if ( v6 )
      {
        if ( v12 )
          (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
      }
      else
      {
        v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v12 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(v7[33] - v7[32]) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_UserRights02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_125;
            }
            v11 = 1;
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, __int64 *))(*v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &v10)
              && v10 )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, v10);
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, __int64 *))(*v7 + 24LL))(
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
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccessCredentialManagerAsTrustedCaller",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_User_01_Set_EdpModeId(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AccessFromNetwork",
                      &v10)
                && v10 )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ActAsPartOfTheOperatingSystem",
                      &v10)
                && v10 )
              {
                MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowLocalLogOn",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"BackupFilesAndDirectories",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ChangeSystemTime",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"CreateGlobalObjects",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"CreatePageFile",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"CreatePermanentSharedObjects",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"CreateSymbolicLinks",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"CreateToken",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DebugPrograms",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_User_01_Set_ProfileXML(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DenyAccessFromNetwork",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DenyLocalLogOn",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DenyRemoteDesktopServicesLogOn",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"EnableDelegation",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"GenerateSecurityAudits",
                      &v10)
                && v10 )
              {
                MDM_VPNv2_User_01_Set_DataEncryption(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ImpersonateClient",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownLocalMachineZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"IncreaseSchedulingPriority",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownRestrictedSitesZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"LoadUnloadDeviceDrivers",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"LockMemory",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ManageAuditingAndSecurityLog",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ManageVolume",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsLockedDownTrustedSitesZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ModifyFirmwareEnvironment",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSoftwareWhenSignatureIsInvalid(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ModifyObjectLabel",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ProfileSingleProcess",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RemoteShutdown",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowTrustedSitesZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RestoreFilesAndDirectories",
                      &v10)
                && v10 )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v7 + 24LL))(
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
            (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
            v12 = 0;
          }
        }
      }
    }
    else
    {
      v6 = MI_RESULT_FAILED;
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
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801b058c  mov     [rsp+arg_8], rbx
0x1801b0591  mov     [rsp+arg_10], rsi
0x1801b0596  push    rdi
0x1801b0597  push    r12
0x1801b0599  push    r13
0x1801b059b  push    r14
0x1801b059d  push    r15
0x1801b059f  sub     rsp, 2F0h
0x1801b05a6  mov     rax, cs:__security_cookie
0x1801b05ad  xor     rax, rsp
0x1801b05b0  mov     [rsp+318h+var_38], rax
0x1801b05b8  mov     r13b, dl
0x1801b05bb  mov     r12, rcx
0x1801b05be  xor     edx, edx; Val
0x1801b05c0  mov     r8d, 230h; Size
0x1801b05c6  lea     rcx, [rsp+318h+instance]; void *
0x1801b05ce  call    memset_0
0x1801b05d3  xor     edi, edi
0x1801b05d5  mov     [rsp+318h+var_2D0], dil
0x1801b05da  mov     [rsp+318h+var_2D8], rdi
0x1801b05df  mov     [rsp+318h+var_290], edi
0x1801b05e6  mov     [rsp+318h+var_28C], dil
0x1801b05ee  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801b05f5  mov     [rsp+318h+var_2C0], rax
0x1801b05fa  lea     rax, [rsp+318h+var_290]
0x1801b0602  mov     [rsp+318h+var_2B8], rax
0x1801b0607  lea     rax, aMdmPolicyResul_164; "MDM_Policy_Result01_UserRights02"
0x1801b060e  mov     [rsp+318h+var_2B0], rax
0x1801b0613  lea     rcx, [rsp+318h+var_290]
0x1801b061b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801b0620  mov     eax, cs:dword_180380B68
0x1801b0626  cmp     eax, 5
0x1801b0629  jbe     short loc_1801B069B
0x1801b062b  mov     rdx, 200000000000h
0x1801b0635  lea     rcx, dword_180380B68
0x1801b063c  call    _tlgKeywordOn
0x1801b0641  test    al, al
0x1801b0643  jz      short loc_1801B069B
0x1801b0645  cmp     [rsp+318h+var_28C], dil
0x1801b064d  jz      short loc_1801B067D
0x1801b064f  cmp     [rsp+318h+var_278], edi
0x1801b0656  jnz     short loc_1801B0673
0x1801b0658  cmp     [rsp+318h+var_274], edi
0x1801b065f  jnz     short loc_1801B0673
0x1801b0661  cmp     [rsp+318h+var_270], edi
0x1801b0668  jnz     short loc_1801B0673
0x1801b066a  cmp     [rsp+318h+var_26C], edi
0x1801b0671  jz      short loc_1801B067D
0x1801b0673  lea     r9, [rsp+318h+var_278]
0x1801b067b  jmp     short loc_1801B0680
0x1801b067d  mov     r9, rdi
0x1801b0680  lea     r8, [rsp+318h+var_288]
0x1801b0688  lea     rdx, byte_180344FE9
0x1801b068f  lea     rcx, dword_180380B68
0x1801b0696  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801b069b  lea     rcx, [rsp+318h+var_2C0]; this
0x1801b06a0  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1801b06a5  nop
0x1801b06a6  mov     [rsp+318h+var_2C8], rdi
0x1801b06ab  lea     rax, [rsp+318h+var_2C8]
0x1801b06b0  mov     [rsp+318h+var_2E8], rax
0x1801b06b5  mov     [rsp+318h+var_2F0], 2
0x1801b06bd  mov     [rsp+318h+var_2F8], 1Fh
0x1801b06c5  lea     r9, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_UserRights02_NodeList
0x1801b06cc  xor     r8d, r8d
0x1801b06cf  xor     edx, edx
0x1801b06d1  mov     rcx, r12
0x1801b06d4  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801b06d9  mov     r15d, eax
0x1801b06dc  test    eax, eax
0x1801b06de  jz      short loc_1801B06E5
0x1801b06e0  jmp     loc_1801B0F49
0x1801b06e5  lea     rbx, [rsp+318h+var_2C8]
0x1801b06ea  mov     [rsp+318h+var_2A0], rbx
0x1801b06ef  mov     r14d, 1
0x1801b06f5  mov     [rsp+318h+var_298], r14b
0x1801b06fd  mov     rsi, [rsp+318h+var_2C8]
0x1801b0702  test    rsi, rsi
0x1801b0705  jnz     short loc_1801B070F
0x1801b0707  mov     r15d, r14d
0x1801b070a  jmp     loc_1801B0F49
0x1801b070f  mov     rax, [rsi]
0x1801b0712  mov     rcx, rsi
0x1801b0715  mov     rax, [rax+10h]
0x1801b0719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b071e  mov     r15d, eax
0x1801b0721  test    eax, eax
0x1801b0723  jz      short loc_1801B0743
0x1801b0725  mov     rcx, [rsp+318h+var_2C8]
0x1801b072a  test    rcx, rcx
0x1801b072d  jz      short loc_1801B073E
0x1801b072f  mov     rax, [rcx]
0x1801b0732  mov     edx, r14d
0x1801b0735  mov     rax, [rax]
0x1801b0738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b073d  nop
0x1801b073e  jmp     loc_1801B0F49
0x1801b0743  mov     rax, [rsi]
0x1801b0746  mov     rcx, rsi
0x1801b0749  mov     rax, [rax+8]
0x1801b074d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0752  mov     r15d, eax
0x1801b0755  test    eax, eax
0x1801b0757  jz      short loc_1801B0777
0x1801b0759  mov     rcx, [rsp+318h+var_2C8]
0x1801b075e  test    rcx, rcx
0x1801b0761  jz      short loc_1801B0772
0x1801b0763  mov     rax, [rcx]
0x1801b0766  mov     edx, r14d
0x1801b0769  mov     rax, [rax]
0x1801b076c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0771  nop
0x1801b0772  jmp     loc_1801B0F49
0x1801b0777  mov     r14d, edi
0x1801b077a  mov     rax, [rsi+108h]
0x1801b0781  sub     rax, [rsi+100h]
0x1801b0788  sar     rax, 4
0x1801b078c  cmp     r14d, eax
0x1801b078f  jnb     loc_1801B0F11
0x1801b0795  lea     r8, [rsp+318h+instance]; instance
0x1801b079d  lea     rdx, MDM_Policy_Result01_UserRights02_rtti; classDecl
0x1801b07a4  mov     rcx, r12; context
0x1801b07a7  call    MI_Context_ConstructInstance
0x1801b07ac  mov     r15d, eax
0x1801b07af  test    eax, eax
0x1801b07b1  jz      short loc_1801B07D3
0x1801b07b3  mov     rcx, [rbx]
0x1801b07b6  test    rcx, rcx
0x1801b07b9  jz      short loc_1801B07CE
0x1801b07bb  mov     rax, [rcx]
0x1801b07be  mov     edx, 1
0x1801b07c3  mov     rax, [rax]
0x1801b07c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b07cb  mov     [rbx], rdi
0x1801b07ce  jmp     loc_1801B0F49
0x1801b07d3  mov     [rsp+318h+var_2D0], 1
0x1801b07d8  mov     rax, [rsi]
0x1801b07db  lea     r9, [rsp+318h+var_2D8]
0x1801b07e0  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x1801b07e7  mov     edx, r14d
0x1801b07ea  mov     rcx, rsi
0x1801b07ed  mov     rax, [rax+18h]
0x1801b07f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b07f6  test    eax, eax
0x1801b07f8  jnz     short loc_1801B0811
0x1801b07fa  mov     rdx, [rsp+318h+var_2D8]
0x1801b07ff  test    rdx, rdx
0x1801b0802  jz      short loc_1801B0811
0x1801b0804  lea     rcx, [rsp+318h+instance]
0x1801b080c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801b0811  mov     rax, [rsi]
0x1801b0814  lea     r9, [rsp+318h+var_2D8]
0x1801b0819  lea     r8, aUserrights; "UserRights"
0x1801b0820  mov     edx, r14d
0x1801b0823  mov     rcx, rsi
0x1801b0826  mov     rax, [rax+18h]
0x1801b082a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b082f  test    eax, eax
0x1801b0831  jnz     short loc_1801B084A
0x1801b0833  mov     rdx, [rsp+318h+var_2D8]
0x1801b0838  test    rdx, rdx
0x1801b083b  jz      short loc_1801B084A
0x1801b083d  lea     rcx, [rsp+318h+instance]
0x1801b0845  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801b084a  cmp     r13b, 1
0x1801b084e  jnz     short loc_1801B0872
0x1801b0850  lea     rdx, [rsp+318h+instance]
0x1801b0858  mov     rcx, r12; self
0x1801b085b  call    MI_Instance_Destruct
0x1801b0860  lea     rcx, [rsp+318h+instance]; self
0x1801b0868  call    MI_Instance_Destruct
0x1801b086d  jmp     loc_1801B0F04
0x1801b0872  mov     rax, [rsi]
0x1801b0875  lea     r9, [rsp+318h+var_2D8]
0x1801b087a  lea     r8, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1801b0881  mov     edx, r14d
0x1801b0884  mov     rcx, rsi
0x1801b0887  mov     rax, [rax+18h]
0x1801b088b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0890  test    eax, eax
0x1801b0892  jnz     short loc_1801B08AB
0x1801b0894  mov     rdx, [rsp+318h+var_2D8]
0x1801b0899  test    rdx, rdx
0x1801b089c  jz      short loc_1801B08AB
0x1801b089e  lea     rcx, [rsp+318h+instance]
0x1801b08a6  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1801b08ab  mov     rax, [rsi]
0x1801b08ae  lea     r9, [rsp+318h+var_2D8]
0x1801b08b3  lea     r8, aAccessfromnetw; "AccessFromNetwork"
0x1801b08ba  mov     edx, r14d
0x1801b08bd  mov     rcx, rsi
0x1801b08c0  mov     rax, [rax+18h]
0x1801b08c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b08c9  test    eax, eax
0x1801b08cb  jnz     short loc_1801B08E4
0x1801b08cd  mov     rdx, [rsp+318h+var_2D8]
0x1801b08d2  test    rdx, rdx
0x1801b08d5  jz      short loc_1801B08E4
0x1801b08d7  lea     rcx, [rsp+318h+instance]
0x1801b08df  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1801b08e4  mov     rax, [rsi]
0x1801b08e7  lea     r9, [rsp+318h+var_2D8]
0x1801b08ec  lea     r8, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1801b08f3  mov     edx, r14d
0x1801b08f6  mov     rcx, rsi
0x1801b08f9  mov     rax, [rax+18h]
0x1801b08fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0902  test    eax, eax
0x1801b0904  jnz     short loc_1801B091D
0x1801b0906  mov     rdx, [rsp+318h+var_2D8]
0x1801b090b  test    rdx, rdx
0x1801b090e  jz      short loc_1801B091D
0x1801b0910  lea     rcx, [rsp+318h+instance]
0x1801b0918  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1801b091d  mov     rax, [rsi]
0x1801b0920  lea     r9, [rsp+318h+var_2D8]
0x1801b0925  lea     r8, aAllowlocallogo; "AllowLocalLogOn"
0x1801b092c  mov     edx, r14d
0x1801b092f  mov     rcx, rsi
0x1801b0932  mov     rax, [rax+18h]
0x1801b0936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b093b  test    eax, eax
0x1801b093d  jnz     short loc_1801B0956
0x1801b093f  mov     rdx, [rsp+318h+var_2D8]
0x1801b0944  test    rdx, rdx
0x1801b0947  jz      short loc_1801B0956
0x1801b0949  lea     rcx, [rsp+318h+instance]
0x1801b0951  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1801b0956  mov     rax, [rsi]
0x1801b0959  lea     r9, [rsp+318h+var_2D8]
0x1801b095e  lea     r8, aBackupfilesand; "BackupFilesAndDirectories"
0x1801b0965  mov     edx, r14d
0x1801b0968  mov     rcx, rsi
0x1801b096b  mov     rax, [rax+18h]
0x1801b096f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0974  test    eax, eax
0x1801b0976  jnz     short loc_1801B098F
0x1801b0978  mov     rdx, [rsp+318h+var_2D8]
0x1801b097d  test    rdx, rdx
0x1801b0980  jz      short loc_1801B098F
0x1801b0982  lea     rcx, [rsp+318h+instance]
0x1801b098a  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1801b098f  mov     rax, [rsi]
0x1801b0992  lea     r9, [rsp+318h+var_2D8]
0x1801b0997  lea     r8, aChangesystemti; "ChangeSystemTime"
0x1801b099e  mov     edx, r14d
0x1801b09a1  mov     rcx, rsi
0x1801b09a4  mov     rax, [rax+18h]
0x1801b09a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b09ad  test    eax, eax
0x1801b09af  jnz     short loc_1801B09C8
0x1801b09b1  mov     rdx, [rsp+318h+var_2D8]
0x1801b09b6  test    rdx, rdx
0x1801b09b9  jz      short loc_1801B09C8
0x1801b09bb  lea     rcx, [rsp+318h+instance]
0x1801b09c3  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1801b09c8  mov     rax, [rsi]
0x1801b09cb  lea     r9, [rsp+318h+var_2D8]
0x1801b09d0  lea     r8, aCreateglobalob; "CreateGlobalObjects"
0x1801b09d7  mov     edx, r14d
0x1801b09da  mov     rcx, rsi
0x1801b09dd  mov     rax, [rax+18h]
0x1801b09e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b09e6  test    eax, eax
0x1801b09e8  jnz     short loc_1801B0A01
0x1801b09ea  mov     rdx, [rsp+318h+var_2D8]
0x1801b09ef  test    rdx, rdx
0x1801b09f2  jz      short loc_1801B0A01
0x1801b09f4  lea     rcx, [rsp+318h+instance]
0x1801b09fc  call    MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType
0x1801b0a01  mov     rax, [rsi]
0x1801b0a04  lea     r9, [rsp+318h+var_2D8]
0x1801b0a09  lea     r8, aCreatepagefile; "CreatePageFile"
0x1801b0a10  mov     edx, r14d
0x1801b0a13  mov     rcx, rsi
0x1801b0a16  mov     rax, [rax+18h]
0x1801b0a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0a1f  test    eax, eax
0x1801b0a21  jnz     short loc_1801B0A3A
0x1801b0a23  mov     rdx, [rsp+318h+var_2D8]
0x1801b0a28  test    rdx, rdx
0x1801b0a2b  jz      short loc_1801B0A3A
0x1801b0a2d  lea     rcx, [rsp+318h+instance]
0x1801b0a35  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1801b0a3a  mov     rax, [rsi]
0x1801b0a3d  lea     r9, [rsp+318h+var_2D8]
0x1801b0a42  lea     r8, aCreatepermanen; "CreatePermanentSharedObjects"
0x1801b0a49  mov     edx, r14d
0x1801b0a4c  mov     rcx, rsi
0x1801b0a4f  mov     rax, [rax+18h]
0x1801b0a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0a58  test    eax, eax
0x1801b0a5a  jnz     short loc_1801B0A73
0x1801b0a5c  mov     rdx, [rsp+318h+var_2D8]
0x1801b0a61  test    rdx, rdx
0x1801b0a64  jz      short loc_1801B0A73
0x1801b0a66  lea     rcx, [rsp+318h+instance]
0x1801b0a6e  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x1801b0a73  mov     rax, [rsi]
0x1801b0a76  lea     r9, [rsp+318h+var_2D8]
  ... truncated ...
```
