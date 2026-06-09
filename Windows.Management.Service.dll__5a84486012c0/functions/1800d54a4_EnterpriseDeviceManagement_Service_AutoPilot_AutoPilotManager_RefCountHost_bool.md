# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)

- ea: `0x1800d54a4`
- end: `0x1800d5595`
- name: `?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z`
- size: `241`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *__hidden this, bool)`
- caller_count: `13`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ce580`
- `0x1800ce690`
- `0x1800ce794`
- `0x1800ce88c`
- `0x1800cfab0`
- `0x1800cfd98`
- `0x1800cfe30`
- `0x1800d009c`
- `0x1800d0d60`
- `0x1800d0e84`
- `0x1800d1988`
- `0x1800d5da4`
- `0x1800d7cac`

## callees

- `0x180066044`
- `0x1800687f4`
- `0x1800813fc`
- `0x1800814e8`
- `0x180081d38`
- `0x1800d54a4`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d54f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d54f9`
- `combase!__imp_CoAddRefSharedService` at `0x1800d5538`
- `combase!__imp_CoAddRefSharedService` at `0x1800d5538`
- `combase!__imp_CoReleaseSharedService` at `0x1800d5570`
- `combase!__imp_CoReleaseSharedService` at `0x1800d5570`

## string_xrefs

- `0x1800d5508`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(
        EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *this,
        char a2)
{
  const char *v3; // r9
  __int64 v4; // rdx
  __int64 v5; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 29) )
  {
    if ( a2 )
    {
      if ( _InterlockedIncrement((volatile signed __int32 *)this + 60) == 1 )
      {
        phModule = 0;
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
          &phModule,
          0);
        if ( !GetModuleHandleExW(
                4u,
                (LPCWSTR)&Microsoft::Windows::Autopilot::RipAndReusePolicyManager::DownloadProfileFromNetwork,
                &phModule) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x1C3,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
            v3);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
          (char *)this + 248,
          &phModule);
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&phModule);
      }
      CoAddRefSharedService(*((unsigned int *)this + 29));
      v4 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    }
    else
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 60, 0xFFFFFFFF) == 1 )
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
          (char *)this + 248,
          0);
      CoReleaseSharedService(*((unsigned int *)this + 29));
      v5 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800d54a4  push    rbx
0x1800d54a6  sub     rsp, 20h
0x1800d54aa  cmp     dword ptr [rcx+74h], 0
0x1800d54ae  mov     rbx, rcx
0x1800d54b1  jz      loc_1800D558D
0x1800d54b7  test    dl, dl
0x1800d54b9  jz      loc_1800D554F
0x1800d54bf  mov     eax, 1
0x1800d54c4  lock xadd [rcx+0F0h], eax
0x1800d54cc  inc     eax
0x1800d54ce  cmp     eax, 1
0x1800d54d1  jnz     short loc_1800D5535
0x1800d54d3  xor     edx, edx
0x1800d54d5  mov     [rsp+28h+phModule], 0
0x1800d54de  lea     rcx, [rsp+28h+phModule]
0x1800d54e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800d54e8  lea     r8, [rsp+28h+phModule]; phModule
0x1800d54ed  mov     ecx, 4; dwFlags
0x1800d54f2  lea     rdx, ?DownloadProfileFromNetwork@RipAndReusePolicyManager@Autopilot@Windows@Microsoft@@UEAAJW4AutopilotProfileDownloadOption@Core@2ModernDeployment@@@Z; lpModuleName
0x1800d54f9  call    cs:__imp_GetModuleHandleExW
0x1800d54ff  test    eax, eax
0x1800d5501  jnz     short loc_1800D551A
0x1800d5503  mov     rcx, [rsp+28h]; this
0x1800d5508  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d550f  mov     edx, 1C3h; void *
0x1800d5514  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800d551a  lea     rcx, [rbx+0F8h]
0x1800d5521  lea     rdx, [rsp+28h+phModule]
0x1800d5526  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800d552b  lea     rcx, [rsp+28h+phModule]
0x1800d5530  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800d5535  mov     ecx, [rbx+74h]
0x1800d5538  call    cs:__imp_CoAddRefSharedService
0x1800d553e  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800d5543  mov     rdx, rax
0x1800d5546  mov     rcx, [rax]
0x1800d5549  mov     rax, [rcx+8]
0x1800d554d  jmp     short loc_1800D5585
0x1800d554f  or      eax, 0FFFFFFFFh
0x1800d5552  lock xadd [rcx+0F0h], eax
0x1800d555a  cmp     eax, 1
0x1800d555d  jnz     short loc_1800D556D
0x1800d555f  add     rcx, 0F8h
0x1800d5566  xor     edx, edx
0x1800d5568  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800d556d  mov     ecx, [rbx+74h]
0x1800d5570  call    cs:__imp_CoReleaseSharedService
0x1800d5576  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800d557b  mov     rdx, rax
0x1800d557e  mov     rcx, [rax]
0x1800d5581  mov     rax, [rcx+10h]
0x1800d5585  mov     rcx, rdx
0x1800d5588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d558d  xor     eax, eax
0x1800d558f  add     rsp, 20h
0x1800d5593  pop     rbx
0x1800d5594  retn
```
