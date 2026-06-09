# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000f22c`
- end: `0x18000f316`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180010574`

## callees

- `0x180008de0`
- `0x180008fc0`
- `0x180009258`
- `0x18000ac28`
- `0x18000c1f4`
- `0x18000c300`
- `0x18000ee04`
- `0x18000f22c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f25e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f25e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f2ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f2ca`

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
                                `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x18000f22c  mov     [rsp+arg_8], rbx
0x18000f231  push    rbp
0x18000f232  push    rsi
0x18000f233  push    rdi
0x18000f234  sub     rsp, 30h
0x18000f238  mov     rsi, r8
0x18000f23b  mov     ebp, edx
0x18000f23d  mov     rdi, rcx
0x18000f240  mov     eax, [rcx]
0x18000f242  test    eax, eax
0x18000f244  jz      loc_18000F308
0x18000f24a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000f24f  test    al, al
0x18000f251  jnz     loc_18000F308
0x18000f257  lea     rbx, [rdi+8]
0x18000f25b  mov     rcx, rbx; SRWLock
0x18000f25e  call    cs:__imp_AcquireSRWLockExclusive
0x18000f265  nop     dword ptr [rax+rax+00h]
0x18000f26a  mov     [rsp+48h+arg_18], rbx
0x18000f26f  mov     eax, [rdi]
0x18000f271  test    eax, eax
0x18000f273  jz      loc_18000F2FD
0x18000f279  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000f27e  test    al, al
0x18000f280  jnz     short loc_18000F2FD
0x18000f282  mov     [rsp+48h+var_28], ebp
0x18000f286  xor     eax, eax
0x18000f288  mov     [rsp+48h+var_24], eax
0x18000f28c  mov     [rsp+48h+var_20], rsi
0x18000f291  lea     rcx, [rdi+30h]; this
0x18000f295  lea     r8d, [rax+10h]; unsigned __int64
0x18000f299  lea     rdx, [rsp+48h+var_28]; void *
0x18000f29e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f2a3  cmp     byte ptr [rdi+18h], 0
0x18000f2a7  jnz     short loc_18000F2FD
0x18000f2a9  lea     rbx, [rdi+10h]
0x18000f2ad  cmp     qword ptr [rbx], 0
0x18000f2b1  jnz     short loc_18000F2EB
0x18000f2b3  lea     rcx, [rsp+48h+arg_0]; this
0x18000f2b8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000f2bd  xor     r8d, r8d; pcbe
0x18000f2c0  mov     rdx, rdi; pv
0x18000f2c3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f2ca  call    cs:__imp_CreateThreadpoolTimer
0x18000f2d1  nop     dword ptr [rax+rax+00h]
0x18000f2d6  mov     rdx, rax
0x18000f2d9  mov     rcx, rbx
0x18000f2dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000f2e1  lea     rcx, [rsp+48h+arg_0]; this
0x18000f2e6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000f2eb  mov     r8d, 493E0h
0x18000f2f1  lea     rdx, [rdi+18h]
0x18000f2f5  mov     rcx, rbx
0x18000f2f8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000f2fd  lea     rcx, [rsp+48h+arg_18]
0x18000f302  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f307  nop
0x18000f308  mov     rbx, [rsp+48h+arg_8]
0x18000f30d  add     rsp, 30h
0x18000f311  pop     rdi
0x18000f312  pop     rsi
0x18000f313  pop     rbp
0x18000f314  retn
```
