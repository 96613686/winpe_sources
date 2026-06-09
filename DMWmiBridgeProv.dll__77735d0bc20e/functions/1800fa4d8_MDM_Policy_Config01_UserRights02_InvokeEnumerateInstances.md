# MDM_Policy_Config01_UserRights02_InvokeEnumerateInstances

- ea: `0x1800fa4d8`
- end: `0x1800faf35`
- name: `MDM_Policy_Config01_UserRights02_InvokeEnumerateInstances`
- size: `2653`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `44`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f9710`

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
- `0x1800fa4d8`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800fa7c6`: `AccessCredentialManagerAsTrustedCaller`
- `0x1800fa7ff`: `AccessFromNetwork`
- `0x1800fa91c`: `CreateGlobalObjects`
- `0x1800fa955`: `CreatePageFile`
- `0x1800fa98e`: `CreatePermanentSharedObjects`
- `0x1800fa9c7`: `CreateSymbolicLinks`
- `0x1800faa00`: `CreateToken`
- `0x1800faa72`: `DenyAccessFromNetwork`
- `0x1800faae4`: `DenyRemoteDesktopServicesLogOn`
- `0x1800fab56`: `GenerateSecurityAudits`
- `0x1800fab8f`: `ImpersonateClient`
- `0x1800fac73`: `ManageAuditingAndSecurityLog`
- `0x1800fa72c`: `./Vendor/MSFT/Policy/Config`
- `0x1800fa553`: `MDM_Policy_Config01_UserRights02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_UserRights02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  __int64 v13; // [rsp+40h] [rbp-2D8h] BYREF
  char v14; // [rsp+48h] [rbp-2D0h]
  WmiRequestHandlerAdd *v15; // [rsp+50h] [rbp-2C8h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_UserRights02_NodeList,
           0x1Fu,
           2,
           &v15);
    if ( !v7 )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = v15;
          if ( v15 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = v15;
            if ( v15 )
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v8 + 33) - *((_QWORD *)v8 + 32)) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_UserRights02_rtti, &instance);
              if ( v7 )
              {
                v6 = v15;
                if ( v15 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_136;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &v13)
                && v13 )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, v13);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, __int64 *))(*(_QWORD *)v8 + 24LL))(
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
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccessCredentialManagerAsTrustedCaller",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_User_01_Set_EdpModeId(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AccessFromNetwork",
                        &v13)
                  && v13 )
                {
                  MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ActAsPartOfTheOperatingSystem",
                        &v13)
                  && v13 )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowLocalLogOn",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"BackupFilesAndDirectories",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ChangeSystemTime",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"CreateGlobalObjects",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"CreatePageFile",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"CreatePermanentSharedObjects",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"CreateSymbolicLinks",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"CreateToken",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DebugPrograms",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_User_01_Set_ProfileXML(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DenyAccessFromNetwork",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DenyLocalLogOn",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DenyRemoteDesktopServicesLogOn",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableDelegation",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"GenerateSecurityAudits",
                        &v13)
                  && v13 )
                {
                  MDM_VPNv2_User_01_Set_DataEncryption(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ImpersonateClient",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownLocalMachineZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"IncreaseSchedulingPriority",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownRestrictedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"LoadUnloadDeviceDrivers",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"LockMemory",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ManageAuditingAndSecurityLog",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ManageVolume",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsLockedDownTrustedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ModifyFirmwareEnvironment",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSoftwareWhenSignatureIsInvalid(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ModifyObjectLabel",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ProfileSingleProcess",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RemoteShutdown",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowTrustedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RestoreFilesAndDirectories",
                        &v13)
                  && v13 )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(
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
            v6 = v15;
            if ( v15 )
            {
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = 1;
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
    v7 = (unsigned int)v15;
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
  return v7;
}

```

## disassembly

```asm
0x1800fa4d8  mov     [rsp+arg_8], rbx
0x1800fa4dd  mov     [rsp+arg_10], rsi
0x1800fa4e2  push    rdi
0x1800fa4e3  push    r12
0x1800fa4e5  push    r13
0x1800fa4e7  push    r14
0x1800fa4e9  push    r15
0x1800fa4eb  sub     rsp, 2F0h
0x1800fa4f2  mov     rax, cs:__security_cookie
0x1800fa4f9  xor     rax, rsp
0x1800fa4fc  mov     [rsp+318h+var_38], rax
0x1800fa504  mov     r13b, dl
0x1800fa507  mov     r12, rcx
0x1800fa50a  xor     edx, edx; Val
0x1800fa50c  mov     r8d, 230h; Size
0x1800fa512  lea     rcx, [rsp+318h+instance]; void *
0x1800fa51a  call    memset_0
0x1800fa51f  xor     edi, edi
0x1800fa521  mov     [rsp+318h+var_2D0], dil
0x1800fa526  mov     [rsp+318h+var_2D8], rdi
0x1800fa52b  mov     [rsp+318h+var_290], edi
0x1800fa532  mov     [rsp+318h+var_28C], dil
0x1800fa53a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800fa541  mov     [rsp+318h+var_2C0], rax
0x1800fa546  lea     rax, [rsp+318h+var_290]
0x1800fa54e  mov     [rsp+318h+var_2B8], rax
0x1800fa553  lea     rax, aMdmPolicyConfi_97; "MDM_Policy_Config01_UserRights02"
0x1800fa55a  mov     [rsp+318h+var_2B0], rax
0x1800fa55f  lea     rcx, [rsp+318h+var_290]
0x1800fa567  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800fa56c  mov     eax, cs:dword_180380B68
0x1800fa572  cmp     eax, 5
0x1800fa575  jbe     short loc_1800FA5E7
0x1800fa577  mov     rdx, 200000000000h
0x1800fa581  lea     rcx, dword_180380B68
0x1800fa588  call    _tlgKeywordOn
0x1800fa58d  test    al, al
0x1800fa58f  jz      short loc_1800FA5E7
0x1800fa591  cmp     [rsp+318h+var_28C], dil
0x1800fa599  jz      short loc_1800FA5C9
0x1800fa59b  cmp     [rsp+318h+var_278], edi
0x1800fa5a2  jnz     short loc_1800FA5BF
0x1800fa5a4  cmp     [rsp+318h+var_274], edi
0x1800fa5ab  jnz     short loc_1800FA5BF
0x1800fa5ad  cmp     [rsp+318h+var_270], edi
0x1800fa5b4  jnz     short loc_1800FA5BF
0x1800fa5b6  cmp     [rsp+318h+var_26C], edi
0x1800fa5bd  jz      short loc_1800FA5C9
0x1800fa5bf  lea     r9, [rsp+318h+var_278]
0x1800fa5c7  jmp     short loc_1800FA5CC
0x1800fa5c9  mov     r9, rdi
0x1800fa5cc  lea     r8, [rsp+318h+var_288]
0x1800fa5d4  lea     rdx, byte_180353A51
0x1800fa5db  lea     rcx, dword_180380B68
0x1800fa5e2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800fa5e7  lea     rcx, [rsp+318h+var_2C0]; this
0x1800fa5ec  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800fa5f1  nop
0x1800fa5f2  mov     [rsp+318h+var_2C8], rdi
0x1800fa5f7  lea     rax, [rsp+318h+var_2C8]
0x1800fa5fc  mov     [rsp+318h+var_2E8], rax
0x1800fa601  mov     [rsp+318h+var_2F0], 2
0x1800fa609  mov     [rsp+318h+var_2F8], 1Fh
0x1800fa611  lea     r9, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_UserRights02_NodeList
0x1800fa618  xor     r8d, r8d
0x1800fa61b  xor     edx, edx
0x1800fa61d  mov     rcx, r12
0x1800fa620  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800fa625  mov     r15d, eax
0x1800fa628  test    eax, eax
0x1800fa62a  jz      short loc_1800FA631
0x1800fa62c  jmp     loc_1800FAE95
0x1800fa631  lea     rbx, [rsp+318h+var_2C8]
0x1800fa636  mov     [rsp+318h+var_2A0], rbx
0x1800fa63b  mov     r14d, 1
0x1800fa641  mov     [rsp+318h+var_298], r14b
0x1800fa649  mov     rsi, [rsp+318h+var_2C8]
0x1800fa64e  test    rsi, rsi
0x1800fa651  jnz     short loc_1800FA65B
0x1800fa653  mov     r15d, r14d
0x1800fa656  jmp     loc_1800FAE95
0x1800fa65b  mov     rax, [rsi]
0x1800fa65e  mov     rcx, rsi
0x1800fa661  mov     rax, [rax+10h]
0x1800fa665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa66a  mov     r15d, eax
0x1800fa66d  test    eax, eax
0x1800fa66f  jz      short loc_1800FA68F
0x1800fa671  mov     rcx, [rsp+318h+var_2C8]
0x1800fa676  test    rcx, rcx
0x1800fa679  jz      short loc_1800FA68A
0x1800fa67b  mov     rax, [rcx]
0x1800fa67e  mov     edx, r14d
0x1800fa681  mov     rax, [rax]
0x1800fa684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa689  nop
0x1800fa68a  jmp     loc_1800FAE95
0x1800fa68f  mov     rax, [rsi]
0x1800fa692  mov     rcx, rsi
0x1800fa695  mov     rax, [rax+8]
0x1800fa699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa69e  mov     r15d, eax
0x1800fa6a1  test    eax, eax
0x1800fa6a3  jz      short loc_1800FA6C3
0x1800fa6a5  mov     rcx, [rsp+318h+var_2C8]
0x1800fa6aa  test    rcx, rcx
0x1800fa6ad  jz      short loc_1800FA6BE
0x1800fa6af  mov     rax, [rcx]
0x1800fa6b2  mov     edx, r14d
0x1800fa6b5  mov     rax, [rax]
0x1800fa6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa6bd  nop
0x1800fa6be  jmp     loc_1800FAE95
0x1800fa6c3  mov     r14d, edi
0x1800fa6c6  mov     rax, [rsi+108h]
0x1800fa6cd  sub     rax, [rsi+100h]
0x1800fa6d4  sar     rax, 4
0x1800fa6d8  cmp     r14d, eax
0x1800fa6db  jnb     loc_1800FAE5D
0x1800fa6e1  lea     r8, [rsp+318h+instance]; instance
0x1800fa6e9  lea     rdx, MDM_Policy_Config01_UserRights02_rtti; classDecl
0x1800fa6f0  mov     rcx, r12; context
0x1800fa6f3  call    MI_Context_ConstructInstance
0x1800fa6f8  mov     r15d, eax
0x1800fa6fb  test    eax, eax
0x1800fa6fd  jz      short loc_1800FA71F
0x1800fa6ff  mov     rcx, [rbx]
0x1800fa702  test    rcx, rcx
0x1800fa705  jz      short loc_1800FA71A
0x1800fa707  mov     rax, [rcx]
0x1800fa70a  mov     edx, 1
0x1800fa70f  mov     rax, [rax]
0x1800fa712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa717  mov     [rbx], rdi
0x1800fa71a  jmp     loc_1800FAE95
0x1800fa71f  mov     [rsp+318h+var_2D0], 1
0x1800fa724  mov     rax, [rsi]
0x1800fa727  lea     r9, [rsp+318h+var_2D8]
0x1800fa72c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800fa733  mov     edx, r14d
0x1800fa736  mov     rcx, rsi
0x1800fa739  mov     rax, [rax+18h]
0x1800fa73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa742  test    eax, eax
0x1800fa744  jnz     short loc_1800FA75D
0x1800fa746  mov     rdx, [rsp+318h+var_2D8]
0x1800fa74b  test    rdx, rdx
0x1800fa74e  jz      short loc_1800FA75D
0x1800fa750  lea     rcx, [rsp+318h+instance]
0x1800fa758  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800fa75d  mov     rax, [rsi]
0x1800fa760  lea     r9, [rsp+318h+var_2D8]
0x1800fa765  lea     r8, aUserrights; "UserRights"
0x1800fa76c  mov     edx, r14d
0x1800fa76f  mov     rcx, rsi
0x1800fa772  mov     rax, [rax+18h]
0x1800fa776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa77b  test    eax, eax
0x1800fa77d  jnz     short loc_1800FA796
0x1800fa77f  mov     rdx, [rsp+318h+var_2D8]
0x1800fa784  test    rdx, rdx
0x1800fa787  jz      short loc_1800FA796
0x1800fa789  lea     rcx, [rsp+318h+instance]
0x1800fa791  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800fa796  cmp     r13b, 1
0x1800fa79a  jnz     short loc_1800FA7BE
0x1800fa79c  lea     rdx, [rsp+318h+instance]
0x1800fa7a4  mov     rcx, r12; self
0x1800fa7a7  call    MI_Instance_Destruct
0x1800fa7ac  lea     rcx, [rsp+318h+instance]; self
0x1800fa7b4  call    MI_Instance_Destruct
0x1800fa7b9  jmp     loc_1800FAE50
0x1800fa7be  mov     rax, [rsi]
0x1800fa7c1  lea     r9, [rsp+318h+var_2D8]
0x1800fa7c6  lea     r8, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1800fa7cd  mov     edx, r14d
0x1800fa7d0  mov     rcx, rsi
0x1800fa7d3  mov     rax, [rax+18h]
0x1800fa7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa7dc  test    eax, eax
0x1800fa7de  jnz     short loc_1800FA7F7
0x1800fa7e0  mov     rdx, [rsp+318h+var_2D8]
0x1800fa7e5  test    rdx, rdx
0x1800fa7e8  jz      short loc_1800FA7F7
0x1800fa7ea  lea     rcx, [rsp+318h+instance]
0x1800fa7f2  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1800fa7f7  mov     rax, [rsi]
0x1800fa7fa  lea     r9, [rsp+318h+var_2D8]
0x1800fa7ff  lea     r8, aAccessfromnetw; "AccessFromNetwork"
0x1800fa806  mov     edx, r14d
0x1800fa809  mov     rcx, rsi
0x1800fa80c  mov     rax, [rax+18h]
0x1800fa810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa815  test    eax, eax
0x1800fa817  jnz     short loc_1800FA830
0x1800fa819  mov     rdx, [rsp+318h+var_2D8]
0x1800fa81e  test    rdx, rdx
0x1800fa821  jz      short loc_1800FA830
0x1800fa823  lea     rcx, [rsp+318h+instance]
0x1800fa82b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800fa830  mov     rax, [rsi]
0x1800fa833  lea     r9, [rsp+318h+var_2D8]
0x1800fa838  lea     r8, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1800fa83f  mov     edx, r14d
0x1800fa842  mov     rcx, rsi
0x1800fa845  mov     rax, [rax+18h]
0x1800fa849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa84e  test    eax, eax
0x1800fa850  jnz     short loc_1800FA869
0x1800fa852  mov     rdx, [rsp+318h+var_2D8]
0x1800fa857  test    rdx, rdx
0x1800fa85a  jz      short loc_1800FA869
0x1800fa85c  lea     rcx, [rsp+318h+instance]
0x1800fa864  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1800fa869  mov     rax, [rsi]
0x1800fa86c  lea     r9, [rsp+318h+var_2D8]
0x1800fa871  lea     r8, aAllowlocallogo; "AllowLocalLogOn"
0x1800fa878  mov     edx, r14d
0x1800fa87b  mov     rcx, rsi
0x1800fa87e  mov     rax, [rax+18h]
0x1800fa882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa887  test    eax, eax
0x1800fa889  jnz     short loc_1800FA8A2
0x1800fa88b  mov     rdx, [rsp+318h+var_2D8]
0x1800fa890  test    rdx, rdx
0x1800fa893  jz      short loc_1800FA8A2
0x1800fa895  lea     rcx, [rsp+318h+instance]
0x1800fa89d  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1800fa8a2  mov     rax, [rsi]
0x1800fa8a5  lea     r9, [rsp+318h+var_2D8]
0x1800fa8aa  lea     r8, aBackupfilesand; "BackupFilesAndDirectories"
0x1800fa8b1  mov     edx, r14d
0x1800fa8b4  mov     rcx, rsi
0x1800fa8b7  mov     rax, [rax+18h]
0x1800fa8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa8c0  test    eax, eax
0x1800fa8c2  jnz     short loc_1800FA8DB
0x1800fa8c4  mov     rdx, [rsp+318h+var_2D8]
0x1800fa8c9  test    rdx, rdx
0x1800fa8cc  jz      short loc_1800FA8DB
0x1800fa8ce  lea     rcx, [rsp+318h+instance]
0x1800fa8d6  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1800fa8db  mov     rax, [rsi]
0x1800fa8de  lea     r9, [rsp+318h+var_2D8]
0x1800fa8e3  lea     r8, aChangesystemti; "ChangeSystemTime"
0x1800fa8ea  mov     edx, r14d
0x1800fa8ed  mov     rcx, rsi
0x1800fa8f0  mov     rax, [rax+18h]
0x1800fa8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa8f9  test    eax, eax
0x1800fa8fb  jnz     short loc_1800FA914
0x1800fa8fd  mov     rdx, [rsp+318h+var_2D8]
0x1800fa902  test    rdx, rdx
0x1800fa905  jz      short loc_1800FA914
0x1800fa907  lea     rcx, [rsp+318h+instance]
0x1800fa90f  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1800fa914  mov     rax, [rsi]
0x1800fa917  lea     r9, [rsp+318h+var_2D8]
0x1800fa91c  lea     r8, aCreateglobalob; "CreateGlobalObjects"
0x1800fa923  mov     edx, r14d
0x1800fa926  mov     rcx, rsi
0x1800fa929  mov     rax, [rax+18h]
0x1800fa92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa932  test    eax, eax
0x1800fa934  jnz     short loc_1800FA94D
0x1800fa936  mov     rdx, [rsp+318h+var_2D8]
0x1800fa93b  test    rdx, rdx
0x1800fa93e  jz      short loc_1800FA94D
0x1800fa940  lea     rcx, [rsp+318h+instance]
0x1800fa948  call    MDM_VPNv2_TrafficFilterList02_01_Set_RoutingPolicyType
0x1800fa94d  mov     rax, [rsi]
0x1800fa950  lea     r9, [rsp+318h+var_2D8]
0x1800fa955  lea     r8, aCreatepagefile; "CreatePageFile"
0x1800fa95c  mov     edx, r14d
0x1800fa95f  mov     rcx, rsi
0x1800fa962  mov     rax, [rax+18h]
0x1800fa966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa96b  test    eax, eax
0x1800fa96d  jnz     short loc_1800FA986
0x1800fa96f  mov     rdx, [rsp+318h+var_2D8]
0x1800fa974  test    rdx, rdx
0x1800fa977  jz      short loc_1800FA986
0x1800fa979  lea     rcx, [rsp+318h+instance]
0x1800fa981  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1800fa986  mov     rax, [rsi]
0x1800fa989  lea     r9, [rsp+318h+var_2D8]
0x1800fa98e  lea     r8, aCreatepermanen; "CreatePermanentSharedObjects"
0x1800fa995  mov     edx, r14d
0x1800fa998  mov     rcx, rsi
0x1800fa99b  mov     rax, [rax+18h]
0x1800fa99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa9a4  test    eax, eax
0x1800fa9a6  jnz     short loc_1800FA9BF
0x1800fa9a8  mov     rdx, [rsp+318h+var_2D8]
0x1800fa9ad  test    rdx, rdx
0x1800fa9b0  jz      short loc_1800FA9BF
0x1800fa9b2  lea     rcx, [rsp+318h+instance]
0x1800fa9ba  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x1800fa9bf  mov     rax, [rsi]
0x1800fa9c2  lea     r9, [rsp+318h+var_2D8]
  ... truncated ...
```
