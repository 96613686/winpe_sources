# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180015b00`
- end: `0x180015bea`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180016b04`

## callees

- `0x18000526c`
- `0x180005544`
- `0x1800058fc`
- `0x180006188`
- `0x180008530`
- `0x18000af30`
- `0x18000b03c`
- `0x180015b00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015b32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015b32`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015b9e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015b9e`

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
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], v8, 0x10u);
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
0x180015b00  mov     [rsp+arg_8], rbx
0x180015b05  push    rbp
0x180015b06  push    rsi
0x180015b07  push    rdi
0x180015b08  sub     rsp, 30h
0x180015b0c  mov     rsi, r8
0x180015b0f  mov     ebp, edx
0x180015b11  mov     rdi, rcx
0x180015b14  mov     eax, [rcx]
0x180015b16  test    eax, eax
0x180015b18  jz      loc_180015BDC
0x180015b1e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180015b23  test    al, al
0x180015b25  jnz     loc_180015BDC
0x180015b2b  lea     rbx, [rdi+8]
0x180015b2f  mov     rcx, rbx; SRWLock
0x180015b32  call    cs:__imp_AcquireSRWLockExclusive
0x180015b39  nop     dword ptr [rax+rax+00h]
0x180015b3e  mov     [rsp+48h+arg_18], rbx
0x180015b43  mov     eax, [rdi]
0x180015b45  test    eax, eax
0x180015b47  jz      loc_180015BD1
0x180015b4d  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180015b52  test    al, al
0x180015b54  jnz     short loc_180015BD1
0x180015b56  mov     [rsp+48h+var_28], ebp
0x180015b5a  xor     eax, eax
0x180015b5c  mov     [rsp+48h+var_24], eax
0x180015b60  mov     [rsp+48h+var_20], rsi
0x180015b65  lea     rcx, [rdi+30h]; this
0x180015b69  lea     r8d, [rax+10h]; unsigned __int64
0x180015b6d  lea     rdx, [rsp+48h+var_28]; void *
0x180015b72  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015b77  cmp     byte ptr [rdi+18h], 0
0x180015b7b  jnz     short loc_180015BD1
0x180015b7d  lea     rbx, [rdi+10h]
0x180015b81  cmp     qword ptr [rbx], 0
0x180015b85  jnz     short loc_180015BBF
0x180015b87  lea     rcx, [rsp+48h+arg_0]; this
0x180015b8c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015b91  xor     r8d, r8d; pcbe
0x180015b94  mov     rdx, rdi; pv
0x180015b97  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180015b9e  call    cs:__imp_CreateThreadpoolTimer
0x180015ba5  nop     dword ptr [rax+rax+00h]
0x180015baa  mov     rdx, rax
0x180015bad  mov     rcx, rbx
0x180015bb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180015bb5  lea     rcx, [rsp+48h+arg_0]; this
0x180015bba  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180015bbf  mov     r8d, 493E0h
0x180015bc5  lea     rdx, [rdi+18h]
0x180015bc9  mov     rcx, rbx
0x180015bcc  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180015bd1  lea     rcx, [rsp+48h+arg_18]
0x180015bd6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015bdb  nop
0x180015bdc  mov     rbx, [rsp+48h+arg_8]
0x180015be1  add     rsp, 30h
0x180015be5  pop     rdi
0x180015be6  pop     rsi
0x180015be7  pop     rbp
0x180015be8  retn
```
