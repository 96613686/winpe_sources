# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180038864`
- end: `0x180038953`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `239`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180038e9c`

## callees

- `0x180015404`
- `0x180015424`
- `0x180015474`
- `0x180015494`
- `0x1800154b8`
- `0x1800155e0`
- `0x180020c18`
- `0x180038864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038896`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038896`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180038900`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180038900`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  char v11; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v10 = pv + 1;
    if ( !LODWORD(pv->Ptr) || wil::ProcessShutdownInProgress(v6) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    }
    else
    {
      v8[0] = a2;
      v8[1] = 0;
      v9 = a3;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            &pv[2],
            ThreadpoolTimer);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
        }
        wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    }
  }
}

```

## disassembly

```asm
0x180038864  mov     [rsp+arg_8], rbx
0x180038869  push    rbp
0x18003886a  push    rsi
0x18003886b  push    rdi
0x18003886c  sub     rsp, 30h
0x180038870  mov     rsi, r8
0x180038873  mov     ebp, edx
0x180038875  mov     rdi, rcx
0x180038878  mov     eax, [rcx]
0x18003887a  test    eax, eax
0x18003887c  jz      loc_180038946
0x180038882  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180038887  test    al, al
0x180038889  jnz     loc_180038946
0x18003888f  lea     rbx, [rdi+8]
0x180038893  mov     rcx, rbx; SRWLock
0x180038896  call    cs:__imp_AcquireSRWLockExclusive
0x18003889c  mov     [rsp+48h+arg_0], rbx
0x1800388a1  mov     eax, [rdi]
0x1800388a3  test    eax, eax
0x1800388a5  jz      loc_18003893B
0x1800388ab  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800388b0  test    al, al
0x1800388b2  jnz     loc_18003893B
0x1800388b8  mov     [rsp+48h+var_28], ebp
0x1800388bc  xor     eax, eax
0x1800388be  mov     [rsp+48h+var_24], eax
0x1800388c2  mov     [rsp+48h+var_20], rsi
0x1800388c7  lea     rcx, [rdi+20h]; this
0x1800388cb  lea     r8d, [rax+10h]; unsigned __int64
0x1800388cf  lea     rdx, [rsp+48h+var_28]; void *
0x1800388d4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800388d9  cmp     byte ptr [rdi+18h], 0
0x1800388dd  jnz     short loc_18003892E
0x1800388df  lea     rbx, [rdi+10h]
0x1800388e3  cmp     qword ptr [rbx], 0
0x1800388e7  jnz     short loc_18003891B
0x1800388e9  lea     rcx, [rsp+48h+arg_18]; this
0x1800388ee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800388f3  xor     r8d, r8d; pcbe
0x1800388f6  mov     rdx, rdi; pv
0x1800388f9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180038900  call    cs:__imp_CreateThreadpoolTimer
0x180038906  mov     rdx, rax
0x180038909  mov     rcx, rbx
0x18003890c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180038911  lea     rcx, [rsp+48h+arg_18]; this
0x180038916  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003891b  mov     r8d, 493E0h
0x180038921  lea     rdx, [rdi+18h]
0x180038925  mov     rcx, rbx
0x180038928  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003892d  nop
0x18003892e  lea     rcx, [rsp+48h+arg_0]
0x180038933  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180038938  nop
0x180038939  jmp     short loc_180038946
0x18003893b  lea     rcx, [rsp+48h+arg_0]
0x180038940  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180038945  nop
0x180038946  mov     rbx, [rsp+48h+arg_8]
0x18003894b  add     rsp, 30h
0x18003894f  pop     rdi
0x180038950  pop     rsi
0x180038951  pop     rbp
0x180038952  retn
```
