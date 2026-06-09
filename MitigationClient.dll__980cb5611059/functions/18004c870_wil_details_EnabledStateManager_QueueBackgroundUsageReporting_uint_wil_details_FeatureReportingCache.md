# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18004c870`
- end: `0x18004c949`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004cb88`

## callees

- `0x18000e5c4`
- `0x18000ea88`
- `0x18000ee4c`
- `0x18000f514`
- `0x1800112fc`
- `0x180013ed4`
- `0x180013fdc`
- `0x18004c870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c8a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c8a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004c904`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004c904`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v11 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18004c870  mov     [rsp+arg_8], rbx
0x18004c875  push    rbp
0x18004c876  push    rsi
0x18004c877  push    rdi
0x18004c878  sub     rsp, 30h
0x18004c87c  mov     rsi, r8
0x18004c87f  mov     ebp, edx
0x18004c881  mov     rdi, rcx
0x18004c884  mov     eax, [rcx]
0x18004c886  test    eax, eax
0x18004c888  jz      loc_18004C93C
0x18004c88e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004c893  test    al, al
0x18004c895  jnz     loc_18004C93C
0x18004c89b  lea     rbx, [rdi+8]
0x18004c89f  mov     rcx, rbx; SRWLock
0x18004c8a2  call    cs:__imp_AcquireSRWLockExclusive
0x18004c8a8  mov     [rsp+48h+arg_18], rbx
0x18004c8ad  mov     eax, [rdi]
0x18004c8af  test    eax, eax
0x18004c8b1  jz      short loc_18004C931
0x18004c8b3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004c8b8  test    al, al
0x18004c8ba  jnz     short loc_18004C931
0x18004c8bc  mov     [rsp+48h+var_28], ebp
0x18004c8c0  xor     eax, eax
0x18004c8c2  mov     [rsp+48h+var_24], eax
0x18004c8c6  mov     [rsp+48h+var_20], rsi
0x18004c8cb  lea     rcx, [rdi+20h]; this
0x18004c8cf  lea     r8d, [rax+10h]; unsigned __int64
0x18004c8d3  lea     rdx, [rsp+48h+var_28]; void *
0x18004c8d8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18004c8dd  cmp     byte ptr [rdi+18h], 0
0x18004c8e1  jnz     short loc_18004C931
0x18004c8e3  lea     rbx, [rdi+10h]
0x18004c8e7  cmp     qword ptr [rbx], 0
0x18004c8eb  jnz     short loc_18004C91F
0x18004c8ed  lea     rcx, [rsp+48h+arg_0]; this
0x18004c8f2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004c8f7  xor     r8d, r8d; pcbe
0x18004c8fa  mov     rdx, rdi; pv
0x18004c8fd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004c904  call    cs:__imp_CreateThreadpoolTimer
0x18004c90a  mov     rdx, rax
0x18004c90d  mov     rcx, rbx
0x18004c910  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004c915  lea     rcx, [rsp+48h+arg_0]; this
0x18004c91a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004c91f  mov     r8d, 493E0h
0x18004c925  lea     rdx, [rdi+18h]
0x18004c929  mov     rcx, rbx
0x18004c92c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18004c931  lea     rcx, [rsp+48h+arg_18]
0x18004c936  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004c93b  nop
0x18004c93c  mov     rbx, [rsp+48h+arg_8]
0x18004c941  add     rsp, 30h
0x18004c945  pop     rdi
0x18004c946  pop     rsi
0x18004c947  pop     rbp
0x18004c948  retn
```
