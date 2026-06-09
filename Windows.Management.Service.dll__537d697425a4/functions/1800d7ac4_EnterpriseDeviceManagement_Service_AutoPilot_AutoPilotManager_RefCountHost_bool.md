# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)

- ea: `0x1800d7ac4`
- end: `0x1800d7bc8`
- name: `?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z`
- size: `260`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *__hidden this, bool)`
- caller_count: `13`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d098c`
- `0x1800d0a9c`
- `0x1800d0ba0`
- `0x1800d0c9c`
- `0x1800d1f0c`
- `0x1800d2210`
- `0x1800d22ac`
- `0x1800d252c`
- `0x1800d3230`
- `0x1800d3378`
- `0x1800d3e98`
- `0x1800d840c`
- `0x1800da3ac`

## callees

- `0x18006630c`
- `0x180068c74`
- `0x180081e80`
- `0x180081f7c`
- `0x1800827f4`
- `0x1800d7ac4`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d7b19`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d7b19`
- `combase!__imp_CoAddRefSharedService` at `0x1800d7b5e`
- `combase!__imp_CoAddRefSharedService` at `0x1800d7b5e`
- `combase!__imp_CoReleaseSharedService` at `0x1800d7b9c`
- `combase!__imp_CoReleaseSharedService` at `0x1800d7b9c`

## string_xrefs

- `0x1800d7b2e`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

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
0x1800d7ac4  push    rbx
0x1800d7ac6  sub     rsp, 20h
0x1800d7aca  cmp     dword ptr [rcx+74h], 0
0x1800d7ace  mov     rbx, rcx
0x1800d7ad1  jz      loc_1800D7BBF
0x1800d7ad7  test    dl, dl
0x1800d7ad9  jz      loc_1800D7B7B
0x1800d7adf  mov     eax, 1
0x1800d7ae4  lock xadd [rcx+0F0h], eax
0x1800d7aec  inc     eax
0x1800d7aee  cmp     eax, 1
0x1800d7af1  jnz     short loc_1800D7B5B
0x1800d7af3  xor     edx, edx
0x1800d7af5  mov     [rsp+28h+phModule], 0
0x1800d7afe  lea     rcx, [rsp+28h+phModule]
0x1800d7b03  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800d7b08  lea     r8, [rsp+28h+phModule]; phModule
0x1800d7b0d  mov     ecx, 4; dwFlags
0x1800d7b12  lea     rdx, ?DownloadProfileFromNetwork@RipAndReusePolicyManager@Autopilot@Windows@Microsoft@@UEAAJW4AutopilotProfileDownloadOption@Core@2ModernDeployment@@@Z; lpModuleName
0x1800d7b19  call    cs:__imp_GetModuleHandleExW
0x1800d7b20  nop     dword ptr [rax+rax+00h]
0x1800d7b25  test    eax, eax
0x1800d7b27  jnz     short loc_1800D7B40
0x1800d7b29  mov     rcx, [rsp+28h]; this
0x1800d7b2e  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d7b35  mov     edx, 1C3h; void *
0x1800d7b3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800d7b40  lea     rcx, [rbx+0F8h]
0x1800d7b47  lea     rdx, [rsp+28h+phModule]
0x1800d7b4c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800d7b51  lea     rcx, [rsp+28h+phModule]
0x1800d7b56  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800d7b5b  mov     ecx, [rbx+74h]
0x1800d7b5e  call    cs:__imp_CoAddRefSharedService
0x1800d7b65  nop     dword ptr [rax+rax+00h]
0x1800d7b6a  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800d7b6f  mov     rdx, rax
0x1800d7b72  mov     rcx, [rax]
0x1800d7b75  mov     rax, [rcx+8]
0x1800d7b79  jmp     short loc_1800D7BB7
0x1800d7b7b  or      eax, 0FFFFFFFFh
0x1800d7b7e  lock xadd [rcx+0F0h], eax
0x1800d7b86  cmp     eax, 1
0x1800d7b89  jnz     short loc_1800D7B99
0x1800d7b8b  add     rcx, 0F8h
0x1800d7b92  xor     edx, edx
0x1800d7b94  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800d7b99  mov     ecx, [rbx+74h]
0x1800d7b9c  call    cs:__imp_CoReleaseSharedService
0x1800d7ba3  nop     dword ptr [rax+rax+00h]
0x1800d7ba8  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800d7bad  mov     rdx, rax
0x1800d7bb0  mov     rcx, [rax]
0x1800d7bb3  mov     rax, [rcx+10h]
0x1800d7bb7  mov     rcx, rdx
0x1800d7bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7bbf  xor     eax, eax
0x1800d7bc1  add     rsp, 20h
0x1800d7bc5  pop     rbx
0x1800d7bc6  retn
```
