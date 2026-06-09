# MDM_Policy_Config01_UserRights02_InvokeEnumerateInstances

- ea: `0x1800f9ffc`
- end: `0x1800faa5a`
- name: `MDM_Policy_Config01_UserRights02_InvokeEnumerateInstances`
- size: `2654`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `44`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f9250`

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
- `0x1800f9ffc`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800fa2ea`: `AccessCredentialManagerAsTrustedCaller`
- `0x1800fa323`: `AccessFromNetwork`
- `0x1800fa440`: `CreateGlobalObjects`
- `0x1800fa479`: `CreatePageFile`
- `0x1800fa4b2`: `CreatePermanentSharedObjects`
- `0x1800fa4eb`: `CreateSymbolicLinks`
- `0x1800fa524`: `CreateToken`
- `0x1800fa596`: `DenyAccessFromNetwork`
- `0x1800fa608`: `DenyRemoteDesktopServicesLogOn`
- `0x1800fa67a`: `GenerateSecurityAudits`
- `0x1800fa6b3`: `ImpersonateClient`
- `0x1800fa797`: `ManageAuditingAndSecurityLog`
- `0x1800fa250`: `./Vendor/MSFT/Policy/Config`
- `0x1800fa077`: `MDM_Policy_Config01_UserRights02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_UserRights02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  __int64 v13; // [rsp+40h] [rbp-2D8h] BYREF
  char v14; // [rsp+48h] [rbp-2D0h]
  _QWORD *v15; // [rsp+50h] [rbp-2C8h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-2C0h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-2A8h] BYREF
  char v18; // [rsp+80h] [rbp-298h]
  int v19; // [rsp+88h] [rbp-290h] BYREF
  char v20; // [rsp+8Ch] [rbp-28Ch]
  _BYTE v21[16]; // [rsp+90h] [rbp-288h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-278h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-268h] BYREF

  memset_0(&instance, 0, 0x230u);
  v14 = 0;
  v13 = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_Policy_Config01_UserRights02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180353A51,
      v21,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v16, v4);
  try
  {
    v15 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_UserRights02_NodeList, 31, 2, &v15);
    if ( v7 == MI_RESULT_OK )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = (wil *)v15;
          if ( v15 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
        }
        else
        {
          v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = (wil *)v15;
            if ( v15 )
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(v8[33] - v8[32]) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_UserRights02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v15;
                if ( v15 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_136;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, __int64 *))(*v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &v13)
                && v13 )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, v13);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, __int64 *))(*v8 + 24LL))(
                      v8,
                      i,
                      L"UserRights",
                      &v13)
                && v13 )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, v13);
              }
              if ( a2 != 1 )
              {
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccessCredentialManagerAsTrustedCaller",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_User_01_Set_EdpModeId(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AccessFromNetwork",
                        &v13)
                  && v13 )
                {
                  MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ActAsPartOfTheOperatingSystem",
                        &v13)
                  && v13 )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowLocalLogOn",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"BackupFilesAndDirectories",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ChangeSystemTime",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CreateGlobalObjects",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CreatePageFile",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CreatePermanentSharedObjects",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CreateSymbolicLinks",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CreateToken",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DebugPrograms",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_User_01_Set_ProfileXML(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DenyAccessFromNetwork",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DenyLocalLogOn",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DenyRemoteDesktopServicesLogOn",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableDelegation",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"GenerateSecurityAudits",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_User_01_Set_DataEncryption(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ImpersonateClient",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownLocalMachineZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"IncreaseSchedulingPriority",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownRestrictedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"LoadUnloadDeviceDrivers",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"LockMemory",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ManageAuditingAndSecurityLog",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ManageVolume",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsLockedDownTrustedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ModifyFirmwareEnvironment",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSoftwareWhenSignatureIsInvalid(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ModifyObjectLabel",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ProfileSingleProcess",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RemoteShutdown",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowTrustedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RestoreFilesAndDirectories",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, __int64 *))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TakeOwnership",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
                }
              }
              MI_Instance_Destruct((MI_Instance *)self);
              MI_Instance_Destruct(&instance);
              v14 = 0;
            }
            v6 = (wil *)v15;
            if ( v15 )
            {
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = MI_RESULT_FAILED;
      }
    }
  }
  catch ( const exception *v17 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v17[0] + 8LL))(v17[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v16, v11);
    LODWORD(v15) = 1;
    goto LABEL_127;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_127:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (int)v15;
  }
LABEL_136:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18036668F,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800f9ffc  mov     [rsp+arg_8], rbx
0x1800fa001  mov     [rsp+arg_10], rsi
0x1800fa006  push    rdi
0x1800fa007  push    r12
0x1800fa009  push    r13
0x1800fa00b  push    r14
0x1800fa00d  push    r15
0x1800fa00f  sub     rsp, 2F0h
0x1800fa016  mov     rax, cs:__security_cookie
0x1800fa01d  xor     rax, rsp
0x1800fa020  mov     [rsp+318h+var_38], rax
0x1800fa028  mov     r13b, dl
0x1800fa02b  mov     r12, rcx
0x1800fa02e  xor     edx, edx; Val
0x1800fa030  mov     r8d, 230h; Size
0x1800fa036  lea     rcx, [rsp+318h+instance]; void *
0x1800fa03e  call    memset_0
0x1800fa043  xor     edi, edi
0x1800fa045  mov     [rsp+318h+var_2D0], dil
0x1800fa04a  mov     [rsp+318h+var_2D8], rdi
0x1800fa04f  mov     [rsp+318h+var_290], edi
0x1800fa056  mov     [rsp+318h+var_28C], dil
0x1800fa05e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800fa065  mov     [rsp+318h+var_2C0], rax
0x1800fa06a  lea     rax, [rsp+318h+var_290]
0x1800fa072  mov     [rsp+318h+var_2B8], rax
0x1800fa077  lea     rax, aMdmPolicyConfi_97; "MDM_Policy_Config01_UserRights02"
0x1800fa07e  mov     [rsp+318h+var_2B0], rax
0x1800fa083  lea     rcx, [rsp+318h+var_290]
0x1800fa08b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800fa090  mov     eax, cs:dword_180380B68
0x1800fa096  cmp     eax, 5
0x1800fa099  jbe     short loc_1800FA10B
0x1800fa09b  mov     rdx, 200000000000h
0x1800fa0a5  lea     rcx, dword_180380B68
0x1800fa0ac  call    _tlgKeywordOn
0x1800fa0b1  test    al, al
0x1800fa0b3  jz      short loc_1800FA10B
0x1800fa0b5  cmp     [rsp+318h+var_28C], dil
0x1800fa0bd  jz      short loc_1800FA0ED
0x1800fa0bf  cmp     [rsp+318h+var_278], edi
0x1800fa0c6  jnz     short loc_1800FA0E3
0x1800fa0c8  cmp     [rsp+318h+var_274], edi
0x1800fa0cf  jnz     short loc_1800FA0E3
0x1800fa0d1  cmp     [rsp+318h+var_270], edi
0x1800fa0d8  jnz     short loc_1800FA0E3
0x1800fa0da  cmp     [rsp+318h+var_26C], edi
0x1800fa0e1  jz      short loc_1800FA0ED
0x1800fa0e3  lea     r9, [rsp+318h+var_278]
0x1800fa0eb  jmp     short loc_1800FA0F0
0x1800fa0ed  mov     r9, rdi
0x1800fa0f0  lea     r8, [rsp+318h+var_288]
0x1800fa0f8  lea     rdx, byte_180353A51
0x1800fa0ff  lea     rcx, dword_180380B68
0x1800fa106  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800fa10b  lea     rcx, [rsp+318h+var_2C0]; this
0x1800fa110  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800fa115  nop
0x1800fa116  mov     [rsp+318h+var_2C8], rdi
0x1800fa11b  lea     rax, [rsp+318h+var_2C8]
0x1800fa120  mov     [rsp+318h+var_2E8], rax
0x1800fa125  mov     [rsp+318h+var_2F0], 2
0x1800fa12d  mov     [rsp+318h+var_2F8], 1Fh
0x1800fa135  lea     r9, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_UserRights02_NodeList
0x1800fa13c  xor     r8d, r8d
0x1800fa13f  xor     edx, edx
0x1800fa141  mov     rcx, r12
0x1800fa144  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800fa149  mov     r15d, eax
0x1800fa14c  test    eax, eax
0x1800fa14e  jz      short loc_1800FA155
0x1800fa150  jmp     loc_1800FA9B9
0x1800fa155  lea     rbx, [rsp+318h+var_2C8]
0x1800fa15a  mov     [rsp+318h+var_2A0], rbx
0x1800fa15f  mov     r14d, 1
0x1800fa165  mov     [rsp+318h+var_298], r14b
0x1800fa16d  mov     rsi, [rsp+318h+var_2C8]
0x1800fa172  test    rsi, rsi
0x1800fa175  jnz     short loc_1800FA17F
0x1800fa177  mov     r15d, r14d
0x1800fa17a  jmp     loc_1800FA9B9
0x1800fa17f  mov     rax, [rsi]
0x1800fa182  mov     rcx, rsi
0x1800fa185  mov     rax, [rax+10h]
0x1800fa189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa18e  mov     r15d, eax
0x1800fa191  test    eax, eax
0x1800fa193  jz      short loc_1800FA1B3
0x1800fa195  mov     rcx, [rsp+318h+var_2C8]
0x1800fa19a  test    rcx, rcx
0x1800fa19d  jz      short loc_1800FA1AE
0x1800fa19f  mov     rax, [rcx]
0x1800fa1a2  mov     edx, r14d
0x1800fa1a5  mov     rax, [rax]
0x1800fa1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa1ad  nop
0x1800fa1ae  jmp     loc_1800FA9B9
0x1800fa1b3  mov     rax, [rsi]
0x1800fa1b6  mov     rcx, rsi
0x1800fa1b9  mov     rax, [rax+8]
0x1800fa1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa1c2  mov     r15d, eax
0x1800fa1c5  test    eax, eax
0x1800fa1c7  jz      short loc_1800FA1E7
0x1800fa1c9  mov     rcx, [rsp+318h+var_2C8]
0x1800fa1ce  test    rcx, rcx
0x1800fa1d1  jz      short loc_1800FA1E2
0x1800fa1d3  mov     rax, [rcx]
0x1800fa1d6  mov     edx, r14d
0x1800fa1d9  mov     rax, [rax]
0x1800fa1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa1e1  nop
0x1800fa1e2  jmp     loc_1800FA9B9
0x1800fa1e7  mov     r14d, edi
0x1800fa1ea  mov     rax, [rsi+108h]
0x1800fa1f1  sub     rax, [rsi+100h]
0x1800fa1f8  sar     rax, 4
0x1800fa1fc  cmp     r14d, eax
0x1800fa1ff  jnb     loc_1800FA981
0x1800fa205  lea     r8, [rsp+318h+instance]; instance
0x1800fa20d  lea     rdx, MDM_Policy_Config01_UserRights02_rtti; classDecl
0x1800fa214  mov     rcx, r12; context
0x1800fa217  call    MI_Context_ConstructInstance
0x1800fa21c  mov     r15d, eax
0x1800fa21f  test    eax, eax
0x1800fa221  jz      short loc_1800FA243
0x1800fa223  mov     rcx, [rbx]
0x1800fa226  test    rcx, rcx
0x1800fa229  jz      short loc_1800FA23E
0x1800fa22b  mov     rax, [rcx]
0x1800fa22e  mov     edx, 1
0x1800fa233  mov     rax, [rax]
0x1800fa236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa23b  mov     [rbx], rdi
0x1800fa23e  jmp     loc_1800FA9B9
0x1800fa243  mov     [rsp+318h+var_2D0], 1
0x1800fa248  mov     rax, [rsi]
0x1800fa24b  lea     r9, [rsp+318h+var_2D8]
0x1800fa250  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800fa257  mov     edx, r14d
0x1800fa25a  mov     rcx, rsi
0x1800fa25d  mov     rax, [rax+18h]
0x1800fa261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa266  test    eax, eax
0x1800fa268  jnz     short loc_1800FA281
0x1800fa26a  mov     rdx, [rsp+318h+var_2D8]
0x1800fa26f  test    rdx, rdx
0x1800fa272  jz      short loc_1800FA281
0x1800fa274  lea     rcx, [rsp+318h+instance]
0x1800fa27c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800fa281  mov     rax, [rsi]
0x1800fa284  lea     r9, [rsp+318h+var_2D8]
0x1800fa289  lea     r8, aUserrights; "UserRights"
0x1800fa290  mov     edx, r14d
0x1800fa293  mov     rcx, rsi
0x1800fa296  mov     rax, [rax+18h]
0x1800fa29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa29f  test    eax, eax
0x1800fa2a1  jnz     short loc_1800FA2BA
0x1800fa2a3  mov     rdx, [rsp+318h+var_2D8]
0x1800fa2a8  test    rdx, rdx
0x1800fa2ab  jz      short loc_1800FA2BA
0x1800fa2ad  lea     rcx, [rsp+318h+instance]
0x1800fa2b5  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800fa2ba  cmp     r13b, 1
0x1800fa2be  jnz     short loc_1800FA2E2
0x1800fa2c0  lea     rdx, [rsp+318h+instance]
0x1800fa2c8  mov     rcx, r12; self
0x1800fa2cb  call    MI_Instance_Destruct
0x1800fa2d0  lea     rcx, [rsp+318h+instance]; self
0x1800fa2d8  call    MI_Instance_Destruct
0x1800fa2dd  jmp     loc_1800FA974
0x1800fa2e2  mov     rax, [rsi]
0x1800fa2e5  lea     r9, [rsp+318h+var_2D8]
0x1800fa2ea  lea     r8, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1800fa2f1  mov     edx, r14d
0x1800fa2f4  mov     rcx, rsi
0x1800fa2f7  mov     rax, [rax+18h]
0x1800fa2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa300  test    eax, eax
0x1800fa302  jnz     short loc_1800FA31B
0x1800fa304  mov     rdx, [rsp+318h+var_2D8]
0x1800fa309  test    rdx, rdx
0x1800fa30c  jz      short loc_1800FA31B
0x1800fa30e  lea     rcx, [rsp+318h+instance]
0x1800fa316  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1800fa31b  mov     rax, [rsi]
0x1800fa31e  lea     r9, [rsp+318h+var_2D8]
0x1800fa323  lea     r8, aAccessfromnetw; "AccessFromNetwork"
0x1800fa32a  mov     edx, r14d
0x1800fa32d  mov     rcx, rsi
0x1800fa330  mov     rax, [rax+18h]
0x1800fa334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa339  test    eax, eax
0x1800fa33b  jnz     short loc_1800FA354
0x1800fa33d  mov     rdx, [rsp+318h+var_2D8]
0x1800fa342  test    rdx, rdx
0x1800fa345  jz      short loc_1800FA354
0x1800fa347  lea     rcx, [rsp+318h+instance]
0x1800fa34f  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800fa354  mov     rax, [rsi]
0x1800fa357  lea     r9, [rsp+318h+var_2D8]
0x1800fa35c  lea     r8, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1800fa363  mov     edx, r14d
0x1800fa366  mov     rcx, rsi
0x1800fa369  mov     rax, [rax+18h]
0x1800fa36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa372  test    eax, eax
0x1800fa374  jnz     short loc_1800FA38D
0x1800fa376  mov     rdx, [rsp+318h+var_2D8]
0x1800fa37b  test    rdx, rdx
0x1800fa37e  jz      short loc_1800FA38D
0x1800fa380  lea     rcx, [rsp+318h+instance]
0x1800fa388  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1800fa38d  mov     rax, [rsi]
0x1800fa390  lea     r9, [rsp+318h+var_2D8]
0x1800fa395  lea     r8, aAllowlocallogo; "AllowLocalLogOn"
0x1800fa39c  mov     edx, r14d
0x1800fa39f  mov     rcx, rsi
0x1800fa3a2  mov     rax, [rax+18h]
0x1800fa3a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa3ab  test    eax, eax
0x1800fa3ad  jnz     short loc_1800FA3C6
0x1800fa3af  mov     rdx, [rsp+318h+var_2D8]
0x1800fa3b4  test    rdx, rdx
0x1800fa3b7  jz      short loc_1800FA3C6
0x1800fa3b9  lea     rcx, [rsp+318h+instance]
0x1800fa3c1  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1800fa3c6  mov     rax, [rsi]
0x1800fa3c9  lea     r9, [rsp+318h+var_2D8]
0x1800fa3ce  lea     r8, aBackupfilesand; "BackupFilesAndDirectories"
0x1800fa3d5  mov     edx, r14d
0x1800fa3d8  mov     rcx, rsi
0x1800fa3db  mov     rax, [rax+18h]
0x1800fa3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa3e4  test    eax, eax
0x1800fa3e6  jnz     short loc_1800FA3FF
0x1800fa3e8  mov     rdx, [rsp+318h+var_2D8]
0x1800fa3ed  test    rdx, rdx
0x1800fa3f0  jz      short loc_1800FA3FF
0x1800fa3f2  lea     rcx, [rsp+318h+instance]
0x1800fa3fa  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1800fa3ff  mov     rax, [rsi]
0x1800fa402  lea     r9, [rsp+318h+var_2D8]
0x1800fa407  lea     r8, aChangesystemti; "ChangeSystemTime"
0x1800fa40e  mov     edx, r14d
0x1800fa411  mov     rcx, rsi
0x1800fa414  mov     rax, [rax+18h]
0x1800fa418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa41d  test    eax, eax
0x1800fa41f  jnz     short loc_1800FA438
0x1800fa421  mov     rdx, [rsp+318h+var_2D8]
0x1800fa426  test    rdx, rdx
0x1800fa429  jz      short loc_1800FA438
0x1800fa42b  lea     rcx, [rsp+318h+instance]
0x1800fa433  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1800fa438  mov     rax, [rsi]
0x1800fa43b  lea     r9, [rsp+318h+var_2D8]
0x1800fa440  lea     r8, aCreateglobalob; "CreateGlobalObjects"
0x1800fa447  mov     edx, r14d
0x1800fa44a  mov     rcx, rsi
0x1800fa44d  mov     rax, [rax+18h]
0x1800fa451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa456  test    eax, eax
0x1800fa458  jnz     short loc_1800FA471
0x1800fa45a  mov     rdx, [rsp+318h+var_2D8]
0x1800fa45f  test    rdx, rdx
0x1800fa462  jz      short loc_1800FA471
0x1800fa464  lea     rcx, [rsp+318h+instance]
0x1800fa46c  call    MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType
0x1800fa471  mov     rax, [rsi]
0x1800fa474  lea     r9, [rsp+318h+var_2D8]
0x1800fa479  lea     r8, aCreatepagefile; "CreatePageFile"
0x1800fa480  mov     edx, r14d
0x1800fa483  mov     rcx, rsi
0x1800fa486  mov     rax, [rax+18h]
0x1800fa48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa48f  test    eax, eax
0x1800fa491  jnz     short loc_1800FA4AA
0x1800fa493  mov     rdx, [rsp+318h+var_2D8]
0x1800fa498  test    rdx, rdx
0x1800fa49b  jz      short loc_1800FA4AA
0x1800fa49d  lea     rcx, [rsp+318h+instance]
0x1800fa4a5  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1800fa4aa  mov     rax, [rsi]
0x1800fa4ad  lea     r9, [rsp+318h+var_2D8]
0x1800fa4b2  lea     r8, aCreatepermanen; "CreatePermanentSharedObjects"
0x1800fa4b9  mov     edx, r14d
0x1800fa4bc  mov     rcx, rsi
0x1800fa4bf  mov     rax, [rax+18h]
0x1800fa4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa4c8  test    eax, eax
0x1800fa4ca  jnz     short loc_1800FA4E3
0x1800fa4cc  mov     rdx, [rsp+318h+var_2D8]
0x1800fa4d1  test    rdx, rdx
0x1800fa4d4  jz      short loc_1800FA4E3
0x1800fa4d6  lea     rcx, [rsp+318h+instance]
0x1800fa4de  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x1800fa4e3  mov     rax, [rsi]
0x1800fa4e6  lea     r9, [rsp+318h+var_2D8]
  ... truncated ...
```
