# Windows::FileSystem::ReFs::ReFsDedupService::Install(void)

- ea: `0x140033e34`
- end: `0x1400341a4`
- name: `?Install@ReFsDedupService@ReFs@FileSystem@Windows@@SAJXZ`
- size: `880`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140017998`

## callees

- `0x140004870`
- `0x14001179c`
- `0x140015bc4`
- `0x140016bf8`
- `0x140016e00`
- `0x140017b04`
- `0x140018710`
- `0x140019600`
- `0x14001983c`
- `0x140019d88`
- `0x1400329a4`
- `0x140033248`
- `0x140033308`
- `0x140033e34`
- `0x1400357e4`
- `0x14004f620`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x140033fcf`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x140033fcf`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140033ee3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140033ee3`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x140034083`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x140034083`

## string_xrefs

- `0x140033e51`: `ServiceInstallActivity`
- `0x140034064`: `@%SystemRoot%\System32\ReFsDedupSvc.exe,-101`
- `0x140033fbe`: `@%SystemRoot%\System32\ReFsDedupSvc.exe,-100`
- `0x140033f07`: `onecore\base\fs\refsdedupsvc\exe\refsdedupservice.cpp`
- `0x140033ff0`: `onecore\base\fs\refsdedupsvc\exe\refsdedupservice.cpp`
- `0x14003409b`: `onecore\base\fs\refsdedupsvc\exe\refsdedupservice.cpp`

## pseudocode

```c
__int64 Windows::FileSystem::ReFs::ReFsDedupService::Install(void)
{
  const char *v0; // r9
  unsigned int v1; // ebx
  const char *v2; // r9
  __int64 result; // rax
  const WCHAR *lpBinaryPathName; // rax
  SC_HANDLE v5; // r10
  SC_HANDLE ServiceW; // rax
  const char *v7; // r9
  unsigned int v8; // ebx
  const char *v9; // r9
  unsigned int LastError; // ebx
  unsigned __int16 *dwServiceType; // [rsp+20h] [rbp-208h]
  unsigned __int16 v12[4]; // [rsp+70h] [rbp-1B8h] BYREF
  struct ITaskFolder **v13; // [rsp+78h] [rbp-1B0h] BYREF
  Windows::FileSystem::ReFs *v14; // [rsp+80h] [rbp-1A8h] BYREF
  SC_HANDLE v15; // [rsp+88h] [rbp-1A0h] BYREF
  SC_HANDLE v16; // [rsp+90h] [rbp-198h] BYREF
  const wchar_t *Info; // [rsp+98h] [rbp-190h] BYREF
  _BYTE v18[32]; // [rsp+A0h] [rbp-188h] BYREF
  _QWORD v19[42]; // [rsp+C0h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v19);
  v19[0] = &Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::`vftable';
  Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::StartActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity *)v19);
  try
  {
    wil::GetModuleFileNameW<std::wstring,128>(v18);
    wil::make_bstr(&v14, L"Initialization");
    Microsoft::Win32::ModuleResourceHelpers::LoadResourceFileContents(&v13, 201);
    *(_QWORD *)v12 = 0;
    Windows::FileSystem::ReFs::GetOrCreateTask(v14, v12, 0, v13, dwServiceType);
    v15 = OpenSCManagerW(0, 0, 0xF003Fu);
    if ( v15 )
    {
      lpBinaryPathName = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
      ServiceW = CreateServiceW(
                   v5,
                   L"refsdedupsvc",
                   L"@%SystemRoot%\\System32\\ReFsDedupSvc.exe,-100",
                   0xF01FFu,
                   0x10u,
                   3u,
                   1u,
                   lpBinaryPathName,
                   0,
                   0,
                   L"RpcSs",
                   0,
                   0);
      v16 = ServiceW;
      if ( ServiceW )
      {
        Info = L"@%SystemRoot%\\System32\\ReFsDedupSvc.exe,-101";
        if ( ChangeServiceConfig2W(ServiceW, 1u, &Info) )
        {
          wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
            v19,
            0);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v15);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
          wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(v12);
          std::wstring::_Tidy_deallocate(v18);
          Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::~ServiceInstallActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity *)v19);
          result = 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xC7,
                        (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\refsdedupservice.cpp",
                        v9);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v15);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
          wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(v12);
          std::wstring::_Tidy_deallocate(v18);
          Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::~ServiceInstallActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity *)v19);
          result = LastError;
        }
      }
      else
      {
        v8 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xC3,
               (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\refsdedupservice.cpp",
               v7);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v15);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
        wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(v12);
        std::wstring::_Tidy_deallocate(v18);
        Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::~ServiceInstallActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity *)v19);
        result = v8;
      }
    }
    else
    {
      v1 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xB0,
             (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\refsdedupservice.cpp",
             v0);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
      wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(v12);
      std::wstring::_Tidy_deallocate(v18);
      Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::~ServiceInstallActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity *)v19);
      result = v1;
    }
  }
  catch ( ... )
  {
    *(_DWORD *)v12 = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0xCB,
                       (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\refsdedupservice.cpp",
                       v2);
    Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::~ServiceInstallActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity *)v19);
    return *(unsigned int *)v12;
  }
  return result;
}

```

## disassembly

```asm
0x140033e34  push    rbx
0x140033e36  sub     rsp, 220h
0x140033e3d  mov     rax, cs:__security_cookie
0x140033e44  xor     rax, rsp
0x140033e47  mov     [rsp+228h+var_18], rax
0x140033e4f  xor     ebx, ebx
0x140033e51  lea     rdx, aServiceinstall; "ServiceInstallActivity"
0x140033e58  lea     rcx, [rsp+228h+var_168]; struct wil::details::IFailureCallback *
0x140033e60  call    ??0?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140033e65  lea     rax, ??_7ServiceInstallActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@6B@; const Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::`vftable'
0x140033e6c  mov     [rsp+228h+var_168], rax
0x140033e74  lea     rcx, [rsp+228h+var_168]; this
0x140033e7c  call    ?StartActivity@ServiceInstallActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::StartActivity(void)
0x140033e81  nop
0x140033e82  lea     rcx, [rsp+228h+var_188]
0x140033e8a  call    ??$GetModuleFileNameW@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0IA@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHINSTANCE__@@@Z; wil::GetModuleFileNameW<std::wstring,128>(HINSTANCE__ *)
0x140033e8f  nop
0x140033e90  mov     qword ptr [rsp+228h+var_1B8], rbx
0x140033e95  lea     rdx, aInitialization; "Initialization"
0x140033e9c  lea     rcx, [rsp+228h+var_1A8]
0x140033ea4  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x140033ea9  nop
0x140033eaa  mov     edx, 0C9h
0x140033eaf  lea     rcx, [rsp+228h+var_1B0]
0x140033eb4  call    ?LoadResourceFileContents@ModuleResourceHelpers@Win32@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@HPEAUHINSTANCE__@@@Z; Microsoft::Win32::ModuleResourceHelpers::LoadResourceFileContents(int,HINSTANCE__ *)
0x140033eb9  nop
0x140033eba  mov     qword ptr [rsp+228h+var_1B8], rbx
0x140033ebf  mov     r9, [rsp+228h+var_1B0]; struct ITaskFolder **
0x140033ec4  xor     r8d, r8d; struct IRegisteredTask **
0x140033ec7  lea     rdx, [rsp+228h+var_1B8]; unsigned __int16 *
0x140033ecc  mov     rcx, [rsp+228h+var_1A8]; this
0x140033ed4  call    ?GetOrCreateTask@ReFs@FileSystem@Windows@@YA_NPEAGPEAPEAUIRegisteredTask@@PEAPEAUITaskFolder@@0@Z; Windows::FileSystem::ReFs::GetOrCreateTask(ushort *,IRegisteredTask * *,ITaskFolder * *,ushort *)
0x140033ed9  xor     edx, edx; lpDatabaseName
0x140033edb  xor     ecx, ecx; lpMachineName
0x140033edd  mov     r8d, 0F003Fh; dwDesiredAccess
0x140033ee3  call    cs:__imp_OpenSCManagerW
0x140033eea  nop     dword ptr [rax+rax+00h]
0x140033eef  mov     r10, rax
0x140033ef2  mov     [rsp+228h+var_1A0], rax
0x140033efa  test    rax, rax
0x140033efd  jnz     short loc_140033F6E
0x140033eff  mov     rcx, [rsp+228h]; this
0x140033f07  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\refsdedupsvc\\exe\\r"...
0x140033f0e  mov     edx, 0B0h; void *
0x140033f13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140033f18  mov     ebx, eax
0x140033f1a  lea     rcx, [rsp+228h+var_1A0]
0x140033f22  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x140033f27  nop
0x140033f28  lea     rcx, [rsp+228h+var_1B0]
0x140033f2d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140033f32  nop
0x140033f33  lea     rcx, [rsp+228h+var_1A8]
0x140033f3b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140033f40  nop
0x140033f41  lea     rcx, [rsp+228h+var_1B8]
0x140033f46  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x140033f4b  nop
0x140033f4c  lea     rcx, [rsp+228h+var_188]
0x140033f54  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140033f59  nop
0x140033f5a  lea     rcx, [rsp+228h+var_168]; this
0x140033f62  call    ??1ServiceInstallActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::~ServiceInstallActivity(void)
0x140033f67  mov     eax, ebx
0x140033f69  jmp     loc_14003418A
0x140033f6e  lea     rcx, [rsp+228h+var_188]
0x140033f76  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140033f7b  mov     [rsp+228h+lpPassword], rbx; lpPassword
0x140033f80  mov     [rsp+228h+lpServiceStartName], rbx; lpServiceStartName
0x140033f85  lea     rcx, Dependencies; "RpcSs"
0x140033f8c  mov     [rsp+228h+lpDependencies], rcx; lpDependencies
0x140033f91  mov     [rsp+228h+lpdwTagId], rbx; lpdwTagId
0x140033f96  mov     [rsp+228h+lpLoadOrderGroup], rbx; lpLoadOrderGroup
0x140033f9b  mov     [rsp+228h+lpBinaryPathName], rax; lpBinaryPathName
0x140033fa0  mov     [rsp+228h+dwErrorControl], 1; dwErrorControl
0x140033fa8  mov     [rsp+228h+dwStartType], 3; dwStartType
0x140033fb0  mov     dword ptr [rsp+228h+dwServiceType], 10h; dwServiceType
0x140033fb8  mov     r9d, 0F01FFh; dwDesiredAccess
0x140033fbe  lea     r8, DisplayName; "@%SystemRoot%\\System32\\ReFsDedupSvc.e"...
0x140033fc5  lea     rdx, ServiceName; "refsdedupsvc"
0x140033fcc  mov     rcx, r10; hSCManager
0x140033fcf  call    cs:__imp_CreateServiceW
0x140033fd6  nop     dword ptr [rax+rax+00h]
0x140033fdb  mov     [rsp+228h+var_198], rax
0x140033fe3  test    rax, rax
0x140033fe6  jnz     short loc_140034064
0x140033fe8  mov     rcx, [rsp+228h]; this
0x140033ff0  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\refsdedupsvc\\exe\\r"...
0x140033ff7  mov     edx, 0C3h; void *
0x140033ffc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140034001  mov     ebx, eax
0x140034003  lea     rcx, [rsp+228h+var_198]
0x14003400b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x140034010  lea     rcx, [rsp+228h+var_1A0]
0x140034018  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x14003401d  nop
0x14003401e  lea     rcx, [rsp+228h+var_1B0]
0x140034023  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140034028  nop
0x140034029  lea     rcx, [rsp+228h+var_1A8]
0x140034031  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140034036  nop
0x140034037  lea     rcx, [rsp+228h+var_1B8]
0x14003403c  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x140034041  nop
0x140034042  lea     rcx, [rsp+228h+var_188]
0x14003404a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003404f  nop
0x140034050  lea     rcx, [rsp+228h+var_168]; this
0x140034058  call    ??1ServiceInstallActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::~ServiceInstallActivity(void)
0x14003405d  mov     eax, ebx
0x14003405f  jmp     loc_14003418A
0x140034064  lea     rcx, aSystemrootSyst; "@%SystemRoot%\\System32\\ReFsDedupSvc.e"...
0x14003406b  mov     [rsp+228h+Info], rcx
0x140034073  lea     r8, [rsp+228h+Info]; lpInfo
0x14003407b  mov     edx, 1; dwInfoLevel
0x140034080  mov     rcx, rax; hService
0x140034083  call    cs:__imp_ChangeServiceConfig2W
0x14003408a  nop     dword ptr [rax+rax+00h]
0x14003408f  test    eax, eax
0x140034091  jnz     short loc_14003410C
0x140034093  mov     rcx, [rsp+228h]; this
0x14003409b  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\refsdedupsvc\\exe\\r"...
0x1400340a2  mov     edx, 0C7h; void *
0x1400340a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400340ac  mov     ebx, eax
0x1400340ae  lea     rcx, [rsp+228h+var_198]
0x1400340b6  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1400340bb  lea     rcx, [rsp+228h+var_1A0]
0x1400340c3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1400340c8  nop
0x1400340c9  lea     rcx, [rsp+228h+var_1B0]
0x1400340ce  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400340d3  nop
0x1400340d4  lea     rcx, [rsp+228h+var_1A8]
0x1400340dc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400340e1  nop
0x1400340e2  lea     rcx, [rsp+228h+var_1B8]
0x1400340e7  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x1400340ec  nop
0x1400340ed  lea     rcx, [rsp+228h+var_188]
0x1400340f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400340fa  nop
0x1400340fb  lea     rcx, [rsp+228h+var_168]; this
0x140034103  call    ??1ServiceInstallActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::~ServiceInstallActivity(void)
0x140034108  mov     eax, ebx
0x14003410a  jmp     short loc_14003418A
0x14003410c  xor     edx, edx
0x14003410e  lea     rcx, [rsp+228h+var_168]
0x140034116  call    ?Stop@?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14003411b  lea     rcx, [rsp+228h+var_198]
0x140034123  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x140034128  lea     rcx, [rsp+228h+var_1A0]
0x140034130  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x140034135  nop
0x140034136  lea     rcx, [rsp+228h+var_1B0]
0x14003413b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140034140  nop
0x140034141  lea     rcx, [rsp+228h+var_1A8]
0x140034149  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14003414e  nop
0x14003414f  lea     rcx, [rsp+228h+var_1B8]
0x140034154  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x140034159  nop
0x14003415a  lea     rcx, [rsp+228h+var_188]
0x140034162  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140034167  nop
0x140034168  lea     rcx, [rsp+228h+var_168]; this
0x140034170  call    ??1ServiceInstallActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::~ServiceInstallActivity(void)
0x140034175  xor     eax, eax
0x140034177  jmp     short loc_14003418A
0x140034179  lea     rcx, [rsp+228h+var_168]; this
0x140034181  call    ??1ServiceInstallActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceInstallActivity::~ServiceInstallActivity(void)
0x140034186  mov     eax, dword ptr [rsp+228h+var_1B8]
0x14003418a  mov     rcx, [rsp+228h+var_18]
0x140034192  xor     rcx, rsp; StackCookie
0x140034195  call    __security_check_cookie
0x14003419a  add     rsp, 220h
0x1400341a1  pop     rbx
0x1400341a2  retn
```
