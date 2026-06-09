# ServiceMain

- ea: `0x18001bb10`
- end: `0x18001bbee`
- name: `ServiceMain`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002e60`
- `0x180005548`
- `0x180017ac0`
- `0x18001ace8`
- `0x18001ad64`
- `0x18001b750`
- `0x18001baa8`
- `0x18001bae0`
- `0x18001bb10`
- `0x18001fcf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bbb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bbb9`

## string_xrefs

- `0x18001bb59`: `onecoreuap\windows\dwm\capture\svc\dll\captureservice.cpp`

## pseudocode

```c
__int64 ServiceMain()
{
  int v0; // eax
  char v1; // dl
  struct _RTL_CRITICAL_SECTION *v3; // [rsp+20h] [rbp-60h] BYREF
  Windows::Graphics::Capture::Server::DCompManager **v4; // [rsp+28h] [rbp-58h] BYREF
  struct Windows::Graphics::Capture::Server::DCompManager *v5; // [rsp+30h] [rbp-50h] BYREF
  char v6; // [rsp+38h] [rbp-48h]
  __int128 v7; // [rsp+40h] [rbp-40h] BYREF
  _DWORD v8[8]; // [rsp+50h] [rbp-30h]
  __int64 v9; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  McGenEventRegister_EventRegister();
  v6 = 1;
  v4 = &Windows::Graphics::Capture::Server::g_DCompManager;
  v5 = 0;
  v0 = Windows::Graphics::Capture::Server::DCompManager::Create(&v5);
  if ( v0 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\captureservice.cpp",
      (const char *)(unsigned int)v0,
      (int)v3);
  wil::details::out_param_t<std::unique_ptr<Windows::Graphics::Capture::Server::DCompManager>>::~out_param_t<std::unique_ptr<Windows::Graphics::Capture::Server::DCompManager>>((__int64 **)&v4);
  v9 = 0;
  v8[0] = 16;
  *(_QWORD *)&v8[1] = 4;
  *(_OWORD *)&v8[3] = 0;
  v8[3] = 0;
  v7 = 0;
  Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(
    (__int64)&v7,
    v1);
  Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::~Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>((__int64)&v7);
  EnterCriticalSection(&CriticalSection);
  v3 = &CriticalSection;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v3);
  return McGenEventUnregister_EventUnregister();
}

```

## disassembly

```asm
0x18001bb10  mov     [rsp-8+arg_0], rbx
0x18001bb15  push    rbp
0x18001bb16  mov     rbp, rsp
0x18001bb19  sub     rsp, 80h
0x18001bb20  mov     rax, cs:__security_cookie
0x18001bb27  xor     rax, rsp
0x18001bb2a  mov     [rbp+var_8], rax
0x18001bb2e  call    McGenEventRegister_EventRegister
0x18001bb33  lea     rax, ?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; std::unique_ptr<Windows::Graphics::Capture::Server::DCompManager> Windows::Graphics::Capture::Server::g_DCompManager
0x18001bb3a  mov     [rbp+var_48], 1
0x18001bb3e  xor     ebx, ebx
0x18001bb40  mov     [rbp+var_58], rax
0x18001bb44  lea     rcx, [rbp+var_50]; struct Windows::Graphics::Capture::Server::DCompManager **
0x18001bb48  mov     [rbp+var_50], rbx
0x18001bb4c  call    ?Create@DCompManager@Server@Capture@Graphics@Windows@@SAJPEAPEAV12345@@Z; Windows::Graphics::Capture::Server::DCompManager::Create(Windows::Graphics::Capture::Server::DCompManager * *)
0x18001bb51  test    eax, eax
0x18001bb53  jns     short loc_18001BB6C
0x18001bb55  mov     rcx, [rbp+8]; this
0x18001bb59  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001bb60  mov     r9d, eax; char *
0x18001bb63  lea     edx, [rbx+22h]; void *
0x18001bb66  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001bb6c  lea     rcx, [rbp+var_58]
0x18001bb70  call    ??1?$out_param_t@V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<Windows::Graphics::Capture::Server::DCompManager>>::~out_param_t<std::unique_ptr<Windows::Graphics::Capture::Server::DCompManager>>(void)
0x18001bb75  xorps   xmm1, xmm1
0x18001bb78  mov     [rbp+var_10], rbx
0x18001bb7c  movups  xmmword ptr [rbp+var_30], xmm1
0x18001bb80  mov     [rbp+var_30], 10h
0x18001bb87  lea     rcx, [rbp+var_40]
0x18001bb8b  xorps   xmm0, xmm0
0x18001bb8e  mov     [rbp+var_30+4], 4
0x18001bb95  movups  xmmword ptr [rbp+var_30+0Ch], xmm1
0x18001bb99  mov     [rbp+var_30+0Ch], ebx
0x18001bb9c  movdqu  [rbp+var_40], xmm0
0x18001bba1  call    ?RunServiceMain@?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@QEAAJE@Z; Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(uchar)
0x18001bba6  lea     rcx, [rbp+var_40]
0x18001bbaa  call    ??1?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@QEAA@XZ; Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::~Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(void)
0x18001bbaf  lea     rbx, CriticalSection
0x18001bbb6  mov     rcx, rbx; lpCriticalSection
0x18001bbb9  call    cs:__imp_EnterCriticalSection
0x18001bbbf  lea     rcx, [rbp+var_60]
0x18001bbc3  mov     [rbp+var_60], rbx
0x18001bbc7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001bbcc  call    McGenEventUnregister_EventUnregister
0x18001bbd1  mov     rcx, [rbp+var_8]
0x18001bbd5  xor     rcx, rsp; StackCookie
0x18001bbd8  call    __security_check_cookie
0x18001bbdd  mov     rbx, [rsp+80h+arg_0]
0x18001bbe5  add     rsp, 80h
0x18001bbec  pop     rbp
0x18001bbed  retn
```
