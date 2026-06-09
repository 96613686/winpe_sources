# OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::HelpDeleteService(SC_HANDLE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &,bool)

- ea: `0x1800f3d68`
- end: `0x1800f44da`
- name: `?HelpDeleteService@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@AEAAXPEAUSC_HANDLE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@_N@Z`
- size: `1906`
- prototype: `bool __fastcall(OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *this, SC_HANDLE hService, SC_HANDLE *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800f44e0`
- `0x1800f4cf4`

## callees

- `0x180012fc8`
- `0x180072114`
- `0x180088d80`
- `0x180088d90`
- `0x1800aed10`
- `0x1800af918`
- `0x1800de144`
- `0x1800e50d0`
- `0x1800ef2ec`
- `0x1800f00b0`
- `0x1800f287c`
- `0x1800f28dc`
- `0x1800f31b0`
- `0x1800f3d68`
- `0x1800f50e8`
- `0x1800f518c`
- `0x1800f5320`
- `0x1800f53d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f41b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f41b4`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x1800f3e34`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x1800f41a4`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x1800f3e34`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x1800f41a4`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800f3e07`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800f3f68`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800f3e07`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800f3f68`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800f3dde`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800f3f3f`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800f418d`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800f3dde`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800f3f3f`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800f418d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800f3ef6`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800f40ae`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800f3ef6`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800f40ae`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800f3eb4`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800f3eb4`

## string_xrefs

- `0x1800f3fcd`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f40da`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4217`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f42e3`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f430e`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f43da`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f43f6`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f440f`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4425`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f443b`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4451`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4467`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4480`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4499`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f44af`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f44c8`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`

## pseudocode

```c
bool __fastcall OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::HelpDeleteService(
        OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *this,
        SC_HANDLE hService,
        SC_HANDLE *a3)
{
  DWORD v6; // eax
  SC_HANDLE v7; // rcx
  const char *v8; // r9
  const char *v9; // r9
  bool result; // al
  const char *v11; // r9
  SC_HANDLE v12; // rcx
  const char *v13; // r9
  int v14; // r12d
  SC_HANDLE v15; // rcx
  DWORD v16; // eax
  SC_HANDLE v17; // rcx
  DWORD LastError; // eax
  struct SC_HANDLE__ *v19; // rdx
  __int64 v20; // rdx
  int v21; // ecx
  __int64 v22; // r8
  unsigned int v23; // r13d
  OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *v24; // rcx
  SC_HANDLE v25; // rcx
  const char *v26; // r9
  __int64 v27; // rdx
  int v28; // ecx
  __int64 v29; // r8
  DWORD v30; // eax
  const char *v31; // r9
  int v32; // eax
  const struct APPX_XML_LINE_INFORMATION *LineInfo; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // r10d
  int v37; // eax
  const struct APPX_XML_LINE_INFORMATION *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  int v41; // r10d
  unsigned int lpBinaryPathName; // [rsp+20h] [rbp-E0h]
  unsigned int lpBinaryPathNamea; // [rsp+20h] [rbp-E0h]
  unsigned int lpBinaryPathNameb; // [rsp+20h] [rbp-E0h]
  unsigned int lpBinaryPathNamec; // [rsp+20h] [rbp-E0h]
  unsigned int lpBinaryPathNamed; // [rsp+20h] [rbp-E0h]
  DWORD v47; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v48; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD pcbBytesNeeded; // [rsp+68h] [rbp-98h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+70h] [rbp-90h] BYREF
  BYTE v51[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v52; // [rsp+D0h] [rbp-30h]
  int v53; // [rsp+E0h] [rbp-20h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+E8h] [rbp-18h] BYREF
  BYTE Buffer[16]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v56; // [rsp+118h] [rbp+18h]
  int v57; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedServicesDEHRemoveHardening>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedServicesDEHRemoveHardening>::GetImpl'::`2'::impl) )
  {
    if ( !ChangeServiceConfigW(*a3, 0xFFFFFFFF, 4u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x420,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        v11);
    v12 = *a3;
    pcbBytesNeeded = 0;
    v57 = 0;
    *(_OWORD *)Buffer = 0;
    v56 = 0;
    if ( !QueryServiceStatusEx(v12, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x42B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        v13);
    v14 = HIDWORD(v56);
    memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
    v15 = *a3;
    pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)OSIntegration::DEH::ContextMenuShellExHandler::Uninitialize;
    pNotifyBuffer.dwVersion = 2;
    v16 = NotifyServiceStatusChangeW(v15, 1u, &pNotifyBuffer);
    if ( v16 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x433,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)v16,
        lpBinaryPathNamea);
    v17 = *a3;
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !ControlService(v17, 1u, &ServiceStatus) )
    {
      LastError = GetLastError();
      if ( LastError - 1061 > 1 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x442,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
          (const char *)LastError,
          lpBinaryPathNamea);
    }
    v19 = *a3;
    v48 = 0;
    v47 = 0;
    if ( !OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::WaitForServiceStop(
            this,
            v19,
            &pNotifyBuffer,
            &v48,
            &v47) )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x454,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)0x8007041DLL,
        lpBinaryPathNameb);
      v23 = v48;
      if ( byte_18024560A < 0 )
        McTemplateU0zqqdzzqq_EventWriteTransfer(
          v21,
          v20,
          *((_QWORD *)this + 30),
          *((_DWORD *)this + 74),
          *((_DWORD *)this + 75),
          29,
          *((_QWORD *)this + 23),
          *((_QWORD *)this + 1),
          v14,
          v48);
      details::appxLog<unsigned short *,unsigned int,unsigned int,long,unsigned short *,unsigned short *,unsigned long,unsigned long>(
        2147943453LL,
        v20,
        v22,
        *((_QWORD *)this + 30),
        *((_DWORD *)this + 74),
        *((_DWORD *)this + 75),
        -2147023843,
        *((_QWORD *)this + 23),
        *((_QWORD *)this + 1),
        v14,
        v23);
      OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::ForceTerminateServiceProcess(v24, *a3, v23);
      v25 = *a3;
      v53 = 0;
      v47 = 0;
      *(_OWORD *)v51 = 0;
      v52 = 0;
      if ( !QueryServiceStatusEx(v25, SC_STATUS_PROCESS_INFO, v51, 0x24u, &v47) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x461,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
          v26);
      if ( *(_DWORD *)&v51[4] != 1 && HIDWORD(v52) )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x46F,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
          (const char *)0x8007041DLL,
          lpBinaryPathNameb);
        if ( byte_18024560A < 0 )
          McTemplateU0zqqdzzqq_EventWriteTransfer(
            v28,
            v27,
            *((_QWORD *)this + 30),
            *((_DWORD *)this + 74),
            *((_DWORD *)this + 75),
            29,
            *((_QWORD *)this + 23),
            *((_QWORD *)this + 1),
            v14,
            SBYTE12(v52));
        details::appxLog<unsigned short *,unsigned int,unsigned int,long,unsigned short *,unsigned short *,unsigned long,unsigned long>(
          2147943453LL,
          v27,
          v29,
          *((_QWORD *)this + 30),
          *((_DWORD *)this + 74),
          *((_DWORD *)this + 75),
          -2147023843,
          *((_QWORD *)this + 23),
          *((_QWORD *)this + 1),
          v14,
          HIDWORD(v52));
      }
    }
    v30 = NotifyServiceStatusChangeW(hService, 0x100u, &pNotifyBuffer);
    if ( v30 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x474,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)v30,
        lpBinaryPathNameb);
    if ( !DeleteService(*a3) && GetLastError() != 1072 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x47A,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        v31);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
      a3,
      0);
    result = OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::WaitForRemove(this, &pNotifyBuffer, hService);
    if ( !result )
    {
      v32 = wil::verify_hresult<long>(2147943453LL);
      if ( v32 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x48A,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
          (const char *)(unsigned int)v32,
          lpBinaryPathNameb);
      if ( byte_18024560A < 0 )
      {
        PackageRepository::PackageTable::GetRepositorySessionInfo(this);
        PackageRepository::PackageTable::GetRepositorySessionInfo((OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 176));
        PackageRepository::PackageTable::GetRepositorySessionInfo((OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 232));
        LineInfo = OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::GetLineInfo(this);
        McTemplateU0zqqdzz_EventWriteTransfer(
          *((_DWORD *)LineInfo + 1),
          (unsigned int)&PackagedServiceDEHDeleteServiceTimeout,
          v36,
          *(_DWORD *)LineInfo,
          *((_DWORD *)LineInfo + 1),
          29,
          v34,
          v35);
      }
      PackageRepository::PackageTable::GetRepositorySessionInfo(this);
      PackageRepository::PackageTable::GetRepositorySessionInfo((OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 176));
      PackageRepository::PackageTable::GetRepositorySessionInfo((OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 232));
      lpBinaryPathNamec = *(_DWORD *)OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::GetLineInfo(this);
      details::appxLog<unsigned short *,unsigned int,unsigned int,long,unsigned short *,unsigned short *>(2147943453LL);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x48C,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)0x41D,
        lpBinaryPathNamec);
    }
  }
  else
  {
    memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
    pNotifyBuffer.dwVersion = 2;
    pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)OSIntegration::DEH::ContextMenuShellExHandler::Uninitialize;
    v6 = NotifyServiceStatusChangeW(hService, 0x100u, &pNotifyBuffer);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x496,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)v6,
        lpBinaryPathName);
    v7 = *a3;
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !ControlService(v7, 1u, &ServiceStatus) && GetLastError() - 1061 > 1 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4A6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        v8);
    if ( !DeleteService(*a3) && GetLastError() != 1072 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4AD,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        v9);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
      a3,
      0);
    result = OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::WaitForRemove(this, &pNotifyBuffer, hService);
    if ( !result )
    {
      v37 = wil::verify_hresult<long>(2147943453LL);
      if ( v37 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4BE,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
          (const char *)(unsigned int)v37,
          lpBinaryPathName);
      if ( byte_18024560A < 0 )
      {
        PackageRepository::PackageTable::GetRepositorySessionInfo(this);
        PackageRepository::PackageTable::GetRepositorySessionInfo((OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 176));
        PackageRepository::PackageTable::GetRepositorySessionInfo((OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 232));
        v38 = OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::GetLineInfo(this);
        McTemplateU0zqqdzz_EventWriteTransfer(
          *((_DWORD *)v38 + 1),
          (unsigned int)&PackagedServiceDEHDeleteServiceTimeout,
          v41,
          *(_DWORD *)v38,
          *((_DWORD *)v38 + 1),
          29,
          v39,
          v40);
      }
      PackageRepository::PackageTable::GetRepositorySessionInfo(this);
      PackageRepository::PackageTable::GetRepositorySessionInfo((OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 176));
      PackageRepository::PackageTable::GetRepositorySessionInfo((OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 232));
      lpBinaryPathNamed = *(_DWORD *)OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::GetLineInfo(this);
      details::appxLog<unsigned short *,unsigned int,unsigned int,long,unsigned short *,unsigned short *>(2147943453LL);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4C0,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)0x41D,
        lpBinaryPathNamed);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800f3d68  push    rbp
0x1800f3d6a  push    rbx
0x1800f3d6b  push    rsi
0x1800f3d6c  push    rdi
0x1800f3d6d  push    r12
0x1800f3d6f  push    r13
0x1800f3d71  push    r15
0x1800f3d73  lea     rbp, [rsp-40h]
0x1800f3d78  sub     rsp, 140h
0x1800f3d7f  mov     rax, cs:__security_cookie
0x1800f3d86  xor     rax, rsp
0x1800f3d89  mov     [rbp+70h+var_40], rax
0x1800f3d8d  mov     rsi, r8
0x1800f3d90  mov     r15, rdx
0x1800f3d93  mov     rbx, rcx
0x1800f3d96  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedServicesDEHRemoveHardening@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedServicesDEHRemoveHardening@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedServicesDEHRemoveHardening> `wil::Feature<__WilFeatureTraits_Feature_PackagedServicesDEHRemoveHardening>::GetImpl(void)'::`2'::impl
0x1800f3d9d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedServicesDEHRemoveHardening@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedServicesDEHRemoveHardening>::__private_IsEnabled(void)
0x1800f3da2  xor     r13d, r13d
0x1800f3da5  test    al, al
0x1800f3da7  jnz     loc_1800F3E82
0x1800f3dad  xor     edx, edx; Val
0x1800f3daf  lea     r8d, [r13+50h]; Size
0x1800f3db3  lea     rcx, [rsp+170h+pNotifyBuffer]; void *
0x1800f3db8  call    memset_0
0x1800f3dbd  lea     rax, ?Uninitialize@ContextMenuShellExHandler@DEH@OSIntegration@@UEAAXXZ; OSIntegration::DEH::ContextMenuShellExHandler::Uninitialize(void)
0x1800f3dc4  mov     [rsp+170h+pNotifyBuffer.dwVersion], 2
0x1800f3dcc  lea     r8, [rsp+170h+pNotifyBuffer]; pNotifyBuffer
0x1800f3dd1  mov     [rsp+170h+pNotifyBuffer.pfnNotifyCallback], rax
0x1800f3dd6  mov     edx, 100h; dwNotifyMask
0x1800f3ddb  mov     rcx, r15; hService
0x1800f3dde  call    cs:__imp_NotifyServiceStatusChangeW
0x1800f3de5  nop     dword ptr [rax+rax+00h]
0x1800f3dea  test    eax, eax
0x1800f3dec  jnz     loc_1800F43F2
0x1800f3df2  mov     rcx, [rsi]; hService
0x1800f3df5  lea     r8, [rbp+70h+ServiceStatus]; lpServiceStatus
0x1800f3df9  xorps   xmm0, xmm0
0x1800f3dfc  lea     edx, [rax+1]; dwControl
0x1800f3dff  movups  xmmword ptr [rbp+70h+ServiceStatus.dwServiceType], xmm0
0x1800f3e03  movups  xmmword ptr [rbp+70h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800f3e07  call    cs:__imp_ControlService
0x1800f3e0e  nop     dword ptr [rax+rax+00h]
0x1800f3e13  test    eax, eax
0x1800f3e15  jnz     short loc_1800F3E31
0x1800f3e17  call    cs:__imp_GetLastError
0x1800f3e1e  nop     dword ptr [rax+rax+00h]
0x1800f3e23  add     eax, 0FFFFFBDBh
0x1800f3e28  cmp     eax, 1
0x1800f3e2b  ja      loc_1800F440B
0x1800f3e31  mov     rcx, [rsi]; hService
0x1800f3e34  call    cs:__imp_DeleteService
0x1800f3e3b  nop     dword ptr [rax+rax+00h]
0x1800f3e40  test    eax, eax
0x1800f3e42  jnz     short loc_1800F3E5B
0x1800f3e44  call    cs:__imp_GetLastError
0x1800f3e4b  nop     dword ptr [rax+rax+00h]
0x1800f3e50  cmp     eax, 430h
0x1800f3e55  jnz     loc_1800F4421
0x1800f3e5b  xor     edx, edx
0x1800f3e5d  mov     rcx, rsi
0x1800f3e60  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x1800f3e65  mov     r8, r15; struct SC_HANDLE__ *
0x1800f3e68  lea     rdx, [rsp+170h+pNotifyBuffer]; struct _SERVICE_NOTIFY_2W *
0x1800f3e6d  mov     rcx, rbx; this
0x1800f3e70  call    ?WaitForRemove@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@AEAA_NAEAU_SERVICE_NOTIFY_2W@@PEAUSC_HANDLE__@@@Z; OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::WaitForRemove(_SERVICE_NOTIFY_2W &,SC_HANDLE__ *)
0x1800f3e75  test    al, al
0x1800f3e77  jz      loc_1800F42FA
0x1800f3e7d  jmp     loc_1800F41E9
0x1800f3e82  mov     rcx, [rsi]; hService
0x1800f3e85  or      edx, 0FFFFFFFFh; dwServiceType
0x1800f3e88  mov     [rsp+170h+lpDisplayName], r13; lpDisplayName
0x1800f3e8d  mov     r9d, edx; dwErrorControl
0x1800f3e90  mov     [rsp+170h+lpPassword], r13; lpPassword
0x1800f3e95  mov     r8d, 4; dwStartType
0x1800f3e9b  mov     [rsp+170h+lpServiceStartName], r13; lpServiceStartName
0x1800f3ea0  mov     [rsp+170h+lpDependencies], r13; lpDependencies
0x1800f3ea5  mov     [rsp+170h+lpdwTagId], r13; lpdwTagId
0x1800f3eaa  mov     [rsp+170h+lpLoadOrderGroup], r13; lpLoadOrderGroup
0x1800f3eaf  mov     [rsp+170h+lpBinaryPathName], r13; lpBinaryPathName
0x1800f3eb4  call    cs:__imp_ChangeServiceConfigW
0x1800f3ebb  nop     dword ptr [rax+rax+00h]
0x1800f3ec0  test    eax, eax
0x1800f3ec2  jz      loc_1800F4437
0x1800f3ec8  mov     rcx, [rsi]; hService
0x1800f3ecb  lea     r8, [rbp+70h+Buffer]; lpBuffer
0x1800f3ecf  xor     eax, eax
0x1800f3ed1  mov     [rsp+170h+pcbBytesNeeded], r13d
0x1800f3ed6  xorps   xmm0, xmm0
0x1800f3ed9  mov     [rbp+70h+var_48], eax
0x1800f3edc  lea     rax, [rsp+170h+pcbBytesNeeded]
0x1800f3ee1  mov     r9d, 24h ; '$'; cbBufSize
0x1800f3ee7  xor     edx, edx; InfoLevel
0x1800f3ee9  mov     [rsp+170h+lpBinaryPathName], rax; unsigned int
0x1800f3eee  movups  xmmword ptr [rbp+70h+Buffer], xmm0
0x1800f3ef2  movups  [rbp+70h+var_58], xmm0
0x1800f3ef6  call    cs:__imp_QueryServiceStatusEx
0x1800f3efd  nop     dword ptr [rax+rax+00h]
0x1800f3f02  test    eax, eax
0x1800f3f04  jz      loc_1800F444D
0x1800f3f0a  mov     r12d, dword ptr [rbp+70h+var_58+0Ch]
0x1800f3f0e  lea     rcx, [rsp+170h+pNotifyBuffer]; void *
0x1800f3f13  xor     edx, edx; Val
0x1800f3f15  lea     r8d, [rdx+50h]; Size
0x1800f3f19  call    memset_0
0x1800f3f1e  mov     rcx, [rsi]; hService
0x1800f3f21  lea     rax, ?Uninitialize@ContextMenuShellExHandler@DEH@OSIntegration@@UEAAXXZ; OSIntegration::DEH::ContextMenuShellExHandler::Uninitialize(void)
0x1800f3f28  lea     r8, [rsp+170h+pNotifyBuffer]; pNotifyBuffer
0x1800f3f2d  mov     [rsp+170h+pNotifyBuffer.pfnNotifyCallback], rax
0x1800f3f32  mov     edx, 1; dwNotifyMask
0x1800f3f37  mov     [rsp+170h+pNotifyBuffer.dwVersion], 2
0x1800f3f3f  call    cs:__imp_NotifyServiceStatusChangeW
0x1800f3f46  nop     dword ptr [rax+rax+00h]
0x1800f3f4b  test    eax, eax
0x1800f3f4d  jnz     loc_1800F4463
0x1800f3f53  mov     rcx, [rsi]; hService
0x1800f3f56  lea     r8, [rbp+70h+ServiceStatus]; lpServiceStatus
0x1800f3f5a  xorps   xmm0, xmm0
0x1800f3f5d  lea     edx, [rax+1]; dwControl
0x1800f3f60  movups  xmmword ptr [rbp+70h+ServiceStatus.dwServiceType], xmm0
0x1800f3f64  movups  xmmword ptr [rbp+70h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800f3f68  call    cs:__imp_ControlService
0x1800f3f6f  nop     dword ptr [rax+rax+00h]
0x1800f3f74  test    eax, eax
0x1800f3f76  jnz     short loc_1800F3F93
0x1800f3f78  call    cs:__imp_GetLastError
0x1800f3f7f  nop     dword ptr [rax+rax+00h]
0x1800f3f84  lea     ecx, [rax-425h]
0x1800f3f8a  cmp     ecx, 1
0x1800f3f8d  ja      loc_1800F447C
0x1800f3f93  mov     rdx, [rsi]; struct SC_HANDLE__ *
0x1800f3f96  lea     rax, [rsp+170h+var_110]
0x1800f3f9b  lea     r9, [rsp+170h+var_10C]; unsigned int *
0x1800f3fa0  mov     [rsp+170h+lpBinaryPathName], rax; int
0x1800f3fa5  lea     r8, [rsp+170h+pNotifyBuffer]; struct _SERVICE_NOTIFY_2W *
0x1800f3faa  mov     [rsp+170h+var_10C], r13d
0x1800f3faf  mov     rcx, rbx; this
0x1800f3fb2  mov     [rsp+170h+var_110], r13d
0x1800f3fb7  call    ?WaitForServiceStop@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@AEAA_NPEAUSC_HANDLE__@@AEAU_SERVICE_NOTIFY_2W@@AEAK2@Z; OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::WaitForServiceStop(SC_HANDLE__ *,_SERVICE_NOTIFY_2W &,ulong &,ulong &)
0x1800f3fbc  mov     edi, 8007041Dh
0x1800f3fc1  test    al, al
0x1800f3fc3  jnz     loc_1800F4180
0x1800f3fc9  mov     rcx, [rbp+78h]; this
0x1800f3fcd  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800f3fd4  mov     r9d, edi; char *
0x1800f3fd7  mov     edx, 454h; void *
0x1800f3fdc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f3fe1  cmp     cs:byte_18024560A, 0
0x1800f3fe8  mov     r13d, [rsp+170h+var_10C]
0x1800f3fed  jge     short loc_1800F402F
0x1800f3fef  mov     rax, [rbx+8]
0x1800f3ff3  mov     r9d, [rbx+128h]
0x1800f3ffa  mov     r8, [rbx+0F0h]
0x1800f4001  mov     dword ptr [rsp+170h+lpPassword], r13d
0x1800f4006  mov     dword ptr [rsp+170h+lpServiceStartName], r12d
0x1800f400b  mov     [rsp+170h+lpDependencies], rax
0x1800f4010  mov     rax, [rbx+0B8h]
0x1800f4017  mov     [rsp+170h+lpdwTagId], rax
0x1800f401c  mov     eax, [rbx+12Ch]
0x1800f4022  mov     dword ptr [rsp+170h+lpLoadOrderGroup], edi
0x1800f4026  mov     dword ptr [rsp+170h+lpBinaryPathName], eax
0x1800f402a  call    McTemplateU0zqqdzzqq_EventWriteTransfer
0x1800f402f  mov     rax, [rbx+8]
0x1800f4033  mov     ecx, edi
0x1800f4035  mov     r9, [rbx+0F0h]
0x1800f403c  mov     dword ptr [rsp+170h+lpDisplayName], r13d
0x1800f4041  mov     dword ptr [rsp+170h+lpPassword], r12d
0x1800f4046  mov     [rsp+170h+lpServiceStartName], rax
0x1800f404b  mov     rax, [rbx+0B8h]
0x1800f4052  mov     [rsp+170h+lpDependencies], rax
0x1800f4057  mov     eax, [rbx+12Ch]
0x1800f405d  mov     dword ptr [rsp+170h+lpdwTagId], edi
0x1800f4061  mov     dword ptr [rsp+170h+lpLoadOrderGroup], eax
0x1800f4065  mov     eax, [rbx+128h]
0x1800f406b  mov     dword ptr [rsp+170h+lpBinaryPathName], eax
0x1800f406f  call    ??$appxLog@PEAGIIJPEAGPEAGKK@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAGIIJ22KK@Z; details::appxLog<ushort *,uint,uint,long,ushort *,ushort *,ulong,ulong>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,uint,uint,long,ushort *,ushort *,ulong,ulong)
0x1800f4074  mov     rdx, [rsi]; struct SC_HANDLE__ *
0x1800f4077  mov     r8d, r13d; unsigned int
0x1800f407a  call    ?ForceTerminateServiceProcess@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@AEAAXPEAUSC_HANDLE__@@K@Z; OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::ForceTerminateServiceProcess(SC_HANDLE__ *,ulong)
0x1800f407f  mov     rcx, [rsi]; hService
0x1800f4082  lea     r8, [rbp+70h+var_B0]; lpBuffer
0x1800f4086  xor     eax, eax
0x1800f4088  xorps   xmm0, xmm0
0x1800f408b  xor     r13d, r13d
0x1800f408e  mov     [rbp+70h+var_90], eax
0x1800f4091  lea     rax, [rsp+170h+var_110]
0x1800f4096  mov     [rsp+170h+var_110], r13d
0x1800f409b  xor     edx, edx; InfoLevel
0x1800f409d  mov     [rsp+170h+lpBinaryPathName], rax; int
0x1800f40a2  movups  xmmword ptr [rbp+70h+var_B0], xmm0
0x1800f40a6  lea     r9d, [r13+24h]; cbBufSize
0x1800f40aa  movups  [rbp+70h+var_A0], xmm0
0x1800f40ae  call    cs:__imp_QueryServiceStatusEx
0x1800f40b5  nop     dword ptr [rax+rax+00h]
0x1800f40ba  test    eax, eax
0x1800f40bc  jz      loc_1800F4495
0x1800f40c2  cmp     dword ptr [rbp+70h+var_B0+4], 1
0x1800f40c6  jz      loc_1800F4180
0x1800f40cc  cmp     dword ptr [rbp+70h+var_A0+0Ch], r13d
0x1800f40d0  jz      loc_1800F4180
0x1800f40d6  mov     rcx, [rbp+78h]; this
0x1800f40da  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800f40e1  mov     r9d, edi; char *
0x1800f40e4  mov     edx, 46Fh; void *
0x1800f40e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f40ee  cmp     cs:byte_18024560A, r13b
0x1800f40f5  jge     short loc_1800F4139
0x1800f40f7  mov     eax, dword ptr [rbp+70h+var_A0+0Ch]
0x1800f40fa  mov     r9d, [rbx+128h]
0x1800f4101  mov     r8, [rbx+0F0h]
0x1800f4108  mov     dword ptr [rsp+170h+lpPassword], eax
0x1800f410c  mov     rax, [rbx+8]
0x1800f4110  mov     dword ptr [rsp+170h+lpServiceStartName], r12d
0x1800f4115  mov     [rsp+170h+lpDependencies], rax
0x1800f411a  mov     rax, [rbx+0B8h]
0x1800f4121  mov     [rsp+170h+lpdwTagId], rax
0x1800f4126  mov     eax, [rbx+12Ch]
0x1800f412c  mov     dword ptr [rsp+170h+lpLoadOrderGroup], edi
0x1800f4130  mov     dword ptr [rsp+170h+lpBinaryPathName], eax
0x1800f4134  call    McTemplateU0zqqdzzqq_EventWriteTransfer
0x1800f4139  mov     eax, dword ptr [rbp+70h+var_A0+0Ch]
0x1800f413c  mov     ecx, edi
0x1800f413e  mov     r9, [rbx+0F0h]
0x1800f4145  mov     dword ptr [rsp+170h+lpDisplayName], eax
0x1800f4149  mov     rax, [rbx+8]
0x1800f414d  mov     dword ptr [rsp+170h+lpPassword], r12d
0x1800f4152  mov     [rsp+170h+lpServiceStartName], rax
0x1800f4157  mov     rax, [rbx+0B8h]
0x1800f415e  mov     [rsp+170h+lpDependencies], rax
0x1800f4163  mov     eax, [rbx+12Ch]
0x1800f4169  mov     dword ptr [rsp+170h+lpdwTagId], edi
0x1800f416d  mov     dword ptr [rsp+170h+lpLoadOrderGroup], eax
0x1800f4171  mov     eax, [rbx+128h]
0x1800f4177  mov     dword ptr [rsp+170h+lpBinaryPathName], eax; unsigned int
0x1800f417b  call    ??$appxLog@PEAGIIJPEAGPEAGKK@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAGIIJ22KK@Z; details::appxLog<ushort *,uint,uint,long,ushort *,ushort *,ulong,ulong>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,uint,uint,long,ushort *,ushort *,ulong,ulong)
0x1800f4180  lea     r8, [rsp+170h+pNotifyBuffer]; pNotifyBuffer
0x1800f4185  mov     edx, 100h; dwNotifyMask
0x1800f418a  mov     rcx, r15; hService
0x1800f418d  call    cs:__imp_NotifyServiceStatusChangeW
0x1800f4194  nop     dword ptr [rax+rax+00h]
0x1800f4199  test    eax, eax
0x1800f419b  jnz     loc_1800F44AB
0x1800f41a1  mov     rcx, [rsi]; hService
0x1800f41a4  call    cs:__imp_DeleteService
0x1800f41ab  nop     dword ptr [rax+rax+00h]
0x1800f41b0  test    eax, eax
0x1800f41b2  jnz     short loc_1800F41CB
0x1800f41b4  call    cs:__imp_GetLastError
0x1800f41bb  nop     dword ptr [rax+rax+00h]
0x1800f41c0  cmp     eax, 430h
0x1800f41c5  jnz     loc_1800F44C4
0x1800f41cb  xor     edx, edx
0x1800f41cd  mov     rcx, rsi
0x1800f41d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x1800f41d5  mov     r8, r15; struct SC_HANDLE__ *
0x1800f41d8  lea     rdx, [rsp+170h+pNotifyBuffer]; struct _SERVICE_NOTIFY_2W *
0x1800f41dd  mov     rcx, rbx; this
0x1800f41e0  call    ?WaitForRemove@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@AEAA_NAEAU_SERVICE_NOTIFY_2W@@PEAUSC_HANDLE__@@@Z; OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::WaitForRemove(_SERVICE_NOTIFY_2W &,SC_HANDLE__ *)
0x1800f41e5  test    al, al
0x1800f41e7  jz      short loc_1800F4208
0x1800f41e9  mov     rcx, [rbp+70h+var_40]
0x1800f41ed  xor     rcx, rsp; StackCookie
0x1800f41f0  call    __security_check_cookie
0x1800f41f5  add     rsp, 140h
0x1800f41fc  pop     r15
0x1800f41fe  pop     r13
0x1800f4200  pop     r12
0x1800f4202  pop     rdi
0x1800f4203  pop     rsi
0x1800f4204  pop     rbx
0x1800f4205  pop     rbp
0x1800f4206  retn
0x1800f4208  mov     ecx, edi
0x1800f420a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800f420f  test    eax, eax
0x1800f4211  jns     short loc_1800F422B
0x1800f4213  mov     rcx, [rbp+78h]; this
0x1800f4217  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800f421e  mov     r9d, eax; char *
0x1800f4221  mov     edx, 48Ah; void *
0x1800f4226  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f422b  cmp     cs:byte_18024560A, r13b
0x1800f4232  jge     short loc_1800F428C
0x1800f4234  mov     rcx, rbx; this
0x1800f4237  call    ?GetRepositorySessionInfo@PackageTable@PackageRepository@@UEAAPEAVIRepositorySessionInfo@2@XZ; PackageRepository::PackageTable::GetRepositorySessionInfo(void)
0x1800f423c  lea     rcx, [rbx+0B0h]; this
0x1800f4243  mov     r8, rax
0x1800f4246  call    ?GetRepositorySessionInfo@PackageTable@PackageRepository@@UEAAPEAVIRepositorySessionInfo@2@XZ; PackageRepository::PackageTable::GetRepositorySessionInfo(void)
0x1800f424b  lea     rcx, [rbx+0E8h]; this
0x1800f4252  mov     rdx, rax
0x1800f4255  call    ?GetRepositorySessionInfo@PackageTable@PackageRepository@@UEAAPEAVIRepositorySessionInfo@2@XZ; PackageRepository::PackageTable::GetRepositorySessionInfo(void)
0x1800f425a  mov     rcx, rbx; this
0x1800f425d  mov     r10, rax
0x1800f4260  call    ?GetLineInfo@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@QEAAAEBUAPPX_XML_LINE_INFORMATION@@XZ; OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::GetLineInfo(void)
0x1800f4265  mov     [rsp+170h+lpDependencies], r8
0x1800f426a  mov     r8, r10
0x1800f426d  mov     [rsp+170h+lpdwTagId], rdx
0x1800f4272  lea     rdx, PackagedServiceDEHDeleteServiceTimeout
0x1800f4279  mov     dword ptr [rsp+170h+lpLoadOrderGroup], edi
0x1800f427d  mov     ecx, [rax+4]
0x1800f4280  mov     r9d, [rax]
  ... truncated ...
```
