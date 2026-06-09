# TimeUpdate::~TimeUpdate(void)

- ea: `0x18000591c`
- end: `0x180005a05`
- name: `??1TimeUpdate@@UEAA@XZ`
- size: `233`
- prototype: `void __fastcall(TimeUpdate *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180005bc0`

## callees

- `0x180002afc`
- `0x180005820`
- `0x180005860`
- `0x18000587c`
- `0x18000591c`
- `0x180005a58`
- `0x1800096b0`
- `0x18000b60c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000594b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800059ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000594b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800059ed`

## pseudocode

```c
void __fastcall TimeUpdate::~TimeUpdate(TimeUpdate *this)
{
  void *v2; // rdx
  volatile signed __int32 *v3; // rbx

  *(_QWORD *)this = &TimeUpdate::`vftable';
  TimeUpdate::Shutdown(this);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((SC_HANDLE *)this + 80);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 15);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 73,
    v2);
  std::thread::~thread((TimeUpdate *)((char *)this + 480));
  `eh vector destructor iterator'((char *)this + 256, 0x38u, 4u, (void (*)(void *))WnfSubscription::~WnfSubscription);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>((struct _TP_TIMER **)this + 31);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 29);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  WNFNotificationDispatcher::~WNFNotificationDispatcher((TimeUpdate *)((char *)this + 144));
  WNFNotificationDispatcher::~WNFNotificationDispatcher((TimeUpdate *)((char *)this + 64));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18000591c  mov     [rsp+arg_0], rbx
0x180005921  push    rdi
0x180005922  sub     rsp, 20h
0x180005926  mov     rdi, rcx
0x180005929  lea     rax, ??_7TimeUpdate@@6B@; const TimeUpdate::`vftable'
0x180005930  mov     [rcx], rax
0x180005933  call    ?Shutdown@TimeUpdate@@QEAAXXZ; TimeUpdate::Shutdown(void)
0x180005938  lea     rcx, [rdi+280h]
0x18000593f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180005944  lea     rcx, [rdi+258h]; lpCriticalSection
0x18000594b  call    cs:__imp_DeleteCriticalSection
0x180005951  lea     rcx, [rdi+248h]
0x180005958  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000595d  lea     rcx, [rdi+1E0h]; this
0x180005964  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180005969  lea     rcx, [rdi+100h]; void *
0x180005970  lea     r9, ??1WnfSubscription@@QEAA@XZ; void (*)(void *)
0x180005977  mov     edx, 38h ; '8'; unsigned __int64
0x18000597c  lea     r8d, [rdx-34h]; unsigned __int64
0x180005980  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180005985  lea     rcx, [rdi+0F8h]
0x18000598c  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x180005991  mov     rbx, [rdi+0E8h]
0x180005998  test    rbx, rbx
0x18000599b  jz      short loc_1800059D4
0x18000599d  or      eax, 0FFFFFFFFh
0x1800059a0  lock xadd [rbx+8], eax
0x1800059a5  cmp     eax, 1
0x1800059a8  jnz     short loc_1800059D4
0x1800059aa  mov     rax, [rbx]
0x1800059ad  mov     rcx, rbx
0x1800059b0  mov     rax, [rax]
0x1800059b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b8  or      eax, 0FFFFFFFFh
0x1800059bb  lock xadd [rbx+0Ch], eax
0x1800059c0  cmp     eax, 1
0x1800059c3  jnz     short loc_1800059D4
0x1800059c5  mov     rax, [rbx]
0x1800059c8  mov     rcx, rbx
0x1800059cb  mov     rax, [rax+8]
0x1800059cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d4  lea     rcx, [rdi+90h]; this
0x1800059db  call    ??1WNFNotificationDispatcher@@QEAA@XZ; WNFNotificationDispatcher::~WNFNotificationDispatcher(void)
0x1800059e0  lea     rcx, [rdi+40h]; this
0x1800059e4  call    ??1WNFNotificationDispatcher@@QEAA@XZ; WNFNotificationDispatcher::~WNFNotificationDispatcher(void)
0x1800059e9  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800059ed  call    cs:__imp_DeleteCriticalSection
0x1800059f3  mov     dword ptr [rdi+0Ch], 0C0000001h
0x1800059fa  mov     rbx, [rsp+28h+arg_0]
0x1800059ff  add     rsp, 20h
0x180005a03  pop     rdi
0x180005a04  retn
```
