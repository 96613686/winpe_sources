# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000a93c`
- end: `0x18000aa15`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b4a4`

## callees

- `0x1800054e0`
- `0x180005790`
- `0x180006d34`
- `0x18000862c`
- `0x1800090f0`
- `0x18000a93c`
- `0x18000c31c`
- `0x18000c424`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a96e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a96e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a9d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a9d0`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v11 = (RTL_SRWLOCK *)(pv + 8);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v8, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18000a93c  mov     [rsp+arg_8], rbx
0x18000a941  push    rbp
0x18000a942  push    rsi
0x18000a943  push    rdi
0x18000a944  sub     rsp, 30h
0x18000a948  mov     rsi, r8
0x18000a94b  mov     ebp, edx
0x18000a94d  mov     rdi, rcx
0x18000a950  mov     eax, [rcx]
0x18000a952  test    eax, eax
0x18000a954  jz      loc_18000AA08
0x18000a95a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000a95f  test    al, al
0x18000a961  jnz     loc_18000AA08
0x18000a967  lea     rbx, [rdi+8]
0x18000a96b  mov     rcx, rbx; SRWLock
0x18000a96e  call    cs:__imp_AcquireSRWLockExclusive
0x18000a974  mov     [rsp+48h+arg_18], rbx
0x18000a979  mov     eax, [rdi]
0x18000a97b  test    eax, eax
0x18000a97d  jz      short loc_18000A9FD
0x18000a97f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000a984  test    al, al
0x18000a986  jnz     short loc_18000A9FD
0x18000a988  mov     [rsp+48h+var_28], ebp
0x18000a98c  xor     eax, eax
0x18000a98e  mov     [rsp+48h+var_24], eax
0x18000a992  mov     [rsp+48h+var_20], rsi
0x18000a997  lea     rcx, [rdi+20h]; this
0x18000a99b  lea     r8d, [rax+10h]; unsigned __int64
0x18000a99f  lea     rdx, [rsp+48h+var_28]; void *
0x18000a9a4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000a9a9  cmp     byte ptr [rdi+18h], 0
0x18000a9ad  jnz     short loc_18000A9FD
0x18000a9af  lea     rbx, [rdi+10h]
0x18000a9b3  cmp     qword ptr [rbx], 0
0x18000a9b7  jnz     short loc_18000A9EB
0x18000a9b9  lea     rcx, [rsp+48h+arg_0]; this
0x18000a9be  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a9c3  xor     r8d, r8d; pcbe
0x18000a9c6  mov     rdx, rdi; pv
0x18000a9c9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a9d0  call    cs:__imp_CreateThreadpoolTimer
0x18000a9d6  mov     rdx, rax
0x18000a9d9  mov     rcx, rbx
0x18000a9dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a9e1  lea     rcx, [rsp+48h+arg_0]; this
0x18000a9e6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a9eb  mov     r8d, 493E0h
0x18000a9f1  lea     rdx, [rdi+18h]
0x18000a9f5  mov     rcx, rbx
0x18000a9f8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000a9fd  lea     rcx, [rsp+48h+arg_18]
0x18000aa02  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000aa07  nop
0x18000aa08  mov     rbx, [rsp+48h+arg_8]
0x18000aa0d  add     rsp, 30h
0x18000aa11  pop     rdi
0x18000aa12  pop     rsi
0x18000aa13  pop     rbp
0x18000aa14  retn
```
