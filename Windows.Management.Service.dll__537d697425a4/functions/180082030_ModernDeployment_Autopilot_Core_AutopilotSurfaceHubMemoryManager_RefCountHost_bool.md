# ModernDeployment::Autopilot::Core::AutopilotSurfaceHubMemoryManager::RefCountHost(bool)

- ea: `0x180082030`
- end: `0x180082126`
- name: `?RefCountHost@AutopilotSurfaceHubMemoryManager@Core@Autopilot@ModernDeployment@@AEAAJ_N@Z`
- size: `246`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::AutopilotSurfaceHubMemoryManager *__hidden this, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006bafc`
- `0x180081eb0`

## callees

- `0x18006630c`
- `0x180068c74`
- `0x180081e80`
- `0x180081f7c`
- `0x180082030`
- `0x1800827f4`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180082082`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180082082`
- `combase!__imp_CoAddRefSharedService` at `0x1800820c2`
- `combase!__imp_CoAddRefSharedService` at `0x1800820c2`
- `combase!__imp_CoReleaseSharedService` at `0x1800820fa`
- `combase!__imp_CoReleaseSharedService` at `0x1800820fa`

## pseudocode

```c
__int64 __fastcall ModernDeployment::Autopilot::Core::AutopilotSurfaceHubMemoryManager::RefCountHost(
        ModernDeployment::Autopilot::Core::AutopilotSurfaceHubMemoryManager *this,
        char a2)
{
  const char *v3; // r9
  __int64 v4; // rdx
  __int64 v5; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    if ( a2 )
    {
      if ( _InterlockedIncrement((volatile signed __int32 *)this + 7) == 1 )
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
            (void *)0x62,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotsurfacehubhelper\\autopilotsurfacehub"
                          "memorymanager.cpp",
            v3);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
          (char *)this + 32,
          &phModule);
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&phModule);
      }
      CoAddRefSharedService(*((unsigned int *)this + 6));
      v4 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    }
    else
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 7, 0xFFFFFFFF) == 1 )
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
          (char *)this + 32,
          0);
      CoReleaseSharedService(*((unsigned int *)this + 6));
      v5 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180082030  push    rbx
0x180082032  sub     rsp, 20h
0x180082036  cmp     dword ptr [rcx+18h], 0
0x18008203a  mov     rbx, rcx
0x18008203d  jz      loc_18008211D
0x180082043  test    dl, dl
0x180082045  jz      loc_1800820DF
0x18008204b  mov     eax, 1
0x180082050  lock xadd [rcx+1Ch], eax
0x180082055  inc     eax
0x180082057  cmp     eax, 1
0x18008205a  jnz     short loc_1800820BF
0x18008205c  xor     edx, edx
0x18008205e  mov     [rsp+28h+phModule], 0
0x180082067  lea     rcx, [rsp+28h+phModule]
0x18008206c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180082071  lea     r8, [rsp+28h+phModule]; phModule
0x180082076  mov     ecx, 4; dwFlags
0x18008207b  lea     rdx, ?DownloadProfileFromNetwork@RipAndReusePolicyManager@Autopilot@Windows@Microsoft@@UEAAJW4AutopilotProfileDownloadOption@Core@2ModernDeployment@@@Z; lpModuleName
0x180082082  call    cs:__imp_GetModuleHandleExW
0x180082089  nop     dword ptr [rax+rax+00h]
0x18008208e  test    eax, eax
0x180082090  jnz     short loc_1800820A7
0x180082092  mov     rcx, [rsp+28h]; this
0x180082097  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008209e  lea     edx, [rax+62h]; void *
0x1800820a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800820a7  lea     rcx, [rbx+20h]
0x1800820ab  lea     rdx, [rsp+28h+phModule]
0x1800820b0  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800820b5  lea     rcx, [rsp+28h+phModule]
0x1800820ba  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800820bf  mov     ecx, [rbx+18h]
0x1800820c2  call    cs:__imp_CoAddRefSharedService
0x1800820c9  nop     dword ptr [rax+rax+00h]
0x1800820ce  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800820d3  mov     rdx, rax
0x1800820d6  mov     rcx, [rax]
0x1800820d9  mov     rax, [rcx+8]
0x1800820dd  jmp     short loc_180082115
0x1800820df  or      eax, 0FFFFFFFFh
0x1800820e2  lock xadd [rcx+1Ch], eax
0x1800820e7  cmp     eax, 1
0x1800820ea  jnz     short loc_1800820F7
0x1800820ec  add     rcx, 20h ; ' '
0x1800820f0  xor     edx, edx
0x1800820f2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800820f7  mov     ecx, [rbx+18h]
0x1800820fa  call    cs:__imp_CoReleaseSharedService
0x180082101  nop     dword ptr [rax+rax+00h]
0x180082106  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18008210b  mov     rdx, rax
0x18008210e  mov     rcx, [rax]
0x180082111  mov     rax, [rcx+10h]
0x180082115  mov     rcx, rdx
0x180082118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008211d  xor     eax, eax
0x18008211f  add     rsp, 20h
0x180082123  pop     rbx
0x180082124  retn
```
