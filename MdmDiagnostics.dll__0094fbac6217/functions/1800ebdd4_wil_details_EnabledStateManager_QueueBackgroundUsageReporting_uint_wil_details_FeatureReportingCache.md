# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800ebdd4`
- end: `0x1800ebead`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800ecab0`

## callees

- `0x1800e7124`
- `0x1800e7c48`
- `0x1800e82e4`
- `0x1800e9220`
- `0x1800ebd00`
- `0x1800ebdd4`
- `0x1800f1110`
- `0x1800f126c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ebe06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ebe06`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ebe68`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ebe68`

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
0x1800ebdd4  mov     [rsp+arg_8], rbx
0x1800ebdd9  push    rbp
0x1800ebdda  push    rsi
0x1800ebddb  push    rdi
0x1800ebddc  sub     rsp, 30h
0x1800ebde0  mov     rsi, r8
0x1800ebde3  mov     ebp, edx
0x1800ebde5  mov     rdi, rcx
0x1800ebde8  mov     eax, [rcx]
0x1800ebdea  test    eax, eax
0x1800ebdec  jz      loc_1800EBEA0
0x1800ebdf2  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800ebdf7  test    al, al
0x1800ebdf9  jnz     loc_1800EBEA0
0x1800ebdff  lea     rbx, [rdi+8]
0x1800ebe03  mov     rcx, rbx; SRWLock
0x1800ebe06  call    cs:__imp_AcquireSRWLockExclusive
0x1800ebe0c  mov     [rsp+48h+arg_18], rbx
0x1800ebe11  mov     eax, [rdi]
0x1800ebe13  test    eax, eax
0x1800ebe15  jz      short loc_1800EBE95
0x1800ebe17  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800ebe1c  test    al, al
0x1800ebe1e  jnz     short loc_1800EBE95
0x1800ebe20  mov     [rsp+48h+var_28], ebp
0x1800ebe24  xor     eax, eax
0x1800ebe26  mov     [rsp+48h+var_24], eax
0x1800ebe2a  mov     [rsp+48h+var_20], rsi
0x1800ebe2f  lea     rcx, [rdi+20h]; this
0x1800ebe33  lea     r8d, [rax+10h]; unsigned __int64
0x1800ebe37  lea     rdx, [rsp+48h+var_28]; void *
0x1800ebe3c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800ebe41  cmp     byte ptr [rdi+18h], 0
0x1800ebe45  jnz     short loc_1800EBE95
0x1800ebe47  lea     rbx, [rdi+10h]
0x1800ebe4b  cmp     qword ptr [rbx], 0
0x1800ebe4f  jnz     short loc_1800EBE83
0x1800ebe51  lea     rcx, [rsp+48h+arg_0]; this
0x1800ebe56  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800ebe5b  xor     r8d, r8d; pcbe
0x1800ebe5e  mov     rdx, rdi; pv
0x1800ebe61  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800ebe68  call    cs:__imp_CreateThreadpoolTimer
0x1800ebe6e  mov     rdx, rax
0x1800ebe71  mov     rcx, rbx
0x1800ebe74  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800ebe79  lea     rcx, [rsp+48h+arg_0]; this
0x1800ebe7e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800ebe83  mov     r8d, 493E0h
0x1800ebe89  lea     rdx, [rdi+18h]
0x1800ebe8d  mov     rcx, rbx
0x1800ebe90  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800ebe95  lea     rcx, [rsp+48h+arg_18]
0x1800ebe9a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ebe9f  nop
0x1800ebea0  mov     rbx, [rsp+48h+arg_8]
0x1800ebea5  add     rsp, 30h
0x1800ebea9  pop     rdi
0x1800ebeaa  pop     rsi
0x1800ebeab  pop     rbp
0x1800ebeac  retn
```
