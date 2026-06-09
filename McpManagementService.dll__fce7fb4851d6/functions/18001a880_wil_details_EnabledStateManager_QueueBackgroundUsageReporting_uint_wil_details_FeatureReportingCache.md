# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001a880`
- end: `0x18001a959`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001adec`

## callees

- `0x180006edc`
- `0x1800074a8`
- `0x18000792c`
- `0x18000898c`
- `0x18000b18c`
- `0x18000e600`
- `0x18000e7e4`
- `0x18001a880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a8b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a8b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a914`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a914`

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
0x18001a880  mov     [rsp+arg_8], rbx
0x18001a885  push    rbp
0x18001a886  push    rsi
0x18001a887  push    rdi
0x18001a888  sub     rsp, 30h
0x18001a88c  mov     rsi, r8
0x18001a88f  mov     ebp, edx
0x18001a891  mov     rdi, rcx
0x18001a894  mov     eax, [rcx]
0x18001a896  test    eax, eax
0x18001a898  jz      loc_18001A94C
0x18001a89e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001a8a3  test    al, al
0x18001a8a5  jnz     loc_18001A94C
0x18001a8ab  lea     rbx, [rdi+8]
0x18001a8af  mov     rcx, rbx; SRWLock
0x18001a8b2  call    cs:__imp_AcquireSRWLockExclusive
0x18001a8b8  mov     [rsp+48h+arg_18], rbx
0x18001a8bd  mov     eax, [rdi]
0x18001a8bf  test    eax, eax
0x18001a8c1  jz      short loc_18001A941
0x18001a8c3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001a8c8  test    al, al
0x18001a8ca  jnz     short loc_18001A941
0x18001a8cc  mov     [rsp+48h+var_28], ebp
0x18001a8d0  xor     eax, eax
0x18001a8d2  mov     [rsp+48h+var_24], eax
0x18001a8d6  mov     [rsp+48h+var_20], rsi
0x18001a8db  lea     rcx, [rdi+20h]; this
0x18001a8df  lea     r8d, [rax+10h]; unsigned __int64
0x18001a8e3  lea     rdx, [rsp+48h+var_28]; void *
0x18001a8e8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001a8ed  cmp     byte ptr [rdi+18h], 0
0x18001a8f1  jnz     short loc_18001A941
0x18001a8f3  lea     rbx, [rdi+10h]
0x18001a8f7  cmp     qword ptr [rbx], 0
0x18001a8fb  jnz     short loc_18001A92F
0x18001a8fd  lea     rcx, [rsp+48h+arg_0]; this
0x18001a902  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a907  xor     r8d, r8d; pcbe
0x18001a90a  mov     rdx, rdi; pv
0x18001a90d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001a914  call    cs:__imp_CreateThreadpoolTimer
0x18001a91a  mov     rdx, rax
0x18001a91d  mov     rcx, rbx
0x18001a920  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001a925  lea     rcx, [rsp+48h+arg_0]; this
0x18001a92a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a92f  mov     r8d, 493E0h
0x18001a935  lea     rdx, [rdi+18h]
0x18001a939  mov     rcx, rbx
0x18001a93c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001a941  lea     rcx, [rsp+48h+arg_18]
0x18001a946  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001a94b  nop
0x18001a94c  mov     rbx, [rsp+48h+arg_8]
0x18001a951  add     rsp, 30h
0x18001a955  pop     rdi
0x18001a956  pop     rsi
0x18001a957  pop     rbp
0x18001a958  retn
```
