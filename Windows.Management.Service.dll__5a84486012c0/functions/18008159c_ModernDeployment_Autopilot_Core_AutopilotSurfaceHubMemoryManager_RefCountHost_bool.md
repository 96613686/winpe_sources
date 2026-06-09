# ModernDeployment::Autopilot::Core::AutopilotSurfaceHubMemoryManager::RefCountHost(bool)

- ea: `0x18008159c`
- end: `0x18008167f`
- name: `?RefCountHost@AutopilotSurfaceHubMemoryManager@Core@Autopilot@ModernDeployment@@AEAAJ_N@Z`
- size: `227`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::AutopilotSurfaceHubMemoryManager *__hidden this, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006b614`
- `0x180081428`

## callees

- `0x180066044`
- `0x1800687f4`
- `0x1800813fc`
- `0x1800814e8`
- `0x18008159c`
- `0x180081d38`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800815ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800815ee`
- `combase!__imp_CoAddRefSharedService` at `0x180081628`
- `combase!__imp_CoAddRefSharedService` at `0x180081628`
- `combase!__imp_CoReleaseSharedService` at `0x18008165a`
- `combase!__imp_CoReleaseSharedService` at `0x18008165a`

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
0x18008159c  push    rbx
0x18008159e  sub     rsp, 20h
0x1800815a2  cmp     dword ptr [rcx+18h], 0
0x1800815a6  mov     rbx, rcx
0x1800815a9  jz      loc_180081677
0x1800815af  test    dl, dl
0x1800815b1  jz      loc_18008163F
0x1800815b7  mov     eax, 1
0x1800815bc  lock xadd [rcx+1Ch], eax
0x1800815c1  inc     eax
0x1800815c3  cmp     eax, 1
0x1800815c6  jnz     short loc_180081625
0x1800815c8  xor     edx, edx
0x1800815ca  mov     [rsp+28h+phModule], 0
0x1800815d3  lea     rcx, [rsp+28h+phModule]
0x1800815d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800815dd  lea     r8, [rsp+28h+phModule]; phModule
0x1800815e2  mov     ecx, 4; dwFlags
0x1800815e7  lea     rdx, ?DownloadProfileFromNetwork@RipAndReusePolicyManager@Autopilot@Windows@Microsoft@@UEAAJW4AutopilotProfileDownloadOption@Core@2ModernDeployment@@@Z; lpModuleName
0x1800815ee  call    cs:__imp_GetModuleHandleExW
0x1800815f4  test    eax, eax
0x1800815f6  jnz     short loc_18008160D
0x1800815f8  mov     rcx, [rsp+28h]; this
0x1800815fd  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\moderndeployment\\au"...
0x180081604  lea     edx, [rax+62h]; void *
0x180081607  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008160d  lea     rcx, [rbx+20h]
0x180081611  lea     rdx, [rsp+28h+phModule]
0x180081616  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x18008161b  lea     rcx, [rsp+28h+phModule]
0x180081620  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180081625  mov     ecx, [rbx+18h]
0x180081628  call    cs:__imp_CoAddRefSharedService
0x18008162e  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180081633  mov     rdx, rax
0x180081636  mov     rcx, [rax]
0x180081639  mov     rax, [rcx+8]
0x18008163d  jmp     short loc_18008166F
0x18008163f  or      eax, 0FFFFFFFFh
0x180081642  lock xadd [rcx+1Ch], eax
0x180081647  cmp     eax, 1
0x18008164a  jnz     short loc_180081657
0x18008164c  add     rcx, 20h ; ' '
0x180081650  xor     edx, edx
0x180081652  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180081657  mov     ecx, [rbx+18h]
0x18008165a  call    cs:__imp_CoReleaseSharedService
0x180081660  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180081665  mov     rdx, rax
0x180081668  mov     rcx, [rax]
0x18008166b  mov     rax, [rcx+10h]
0x18008166f  mov     rcx, rdx
0x180081672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081677  xor     eax, eax
0x180081679  add     rsp, 20h
0x18008167d  pop     rbx
0x18008167e  retn
```
