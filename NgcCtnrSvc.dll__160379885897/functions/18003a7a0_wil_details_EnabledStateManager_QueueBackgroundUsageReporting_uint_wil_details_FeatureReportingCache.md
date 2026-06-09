# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18003a7a0`
- end: `0x18003a88a`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180015340`

## callees

- `0x180012e40`
- `0x18001ad2c`
- `0x18001b940`
- `0x180025d04`
- `0x180025d28`
- `0x180025d70`
- `0x180025d9c`
- `0x18003a7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a7d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a7d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003a83e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003a83e`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
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
        Source[0] = a2;
        Source[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], Source, 0x10u);
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
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v11);
  }
}

```

## disassembly

```asm
0x18003a7a0  mov     [rsp+arg_8], rbx
0x18003a7a5  push    rbp
0x18003a7a6  push    rsi
0x18003a7a7  push    rdi
0x18003a7a8  sub     rsp, 30h
0x18003a7ac  mov     rsi, r8
0x18003a7af  mov     ebp, edx
0x18003a7b1  mov     rdi, rcx
0x18003a7b4  mov     eax, [rcx]
0x18003a7b6  test    eax, eax
0x18003a7b8  jz      loc_18003A87C
0x18003a7be  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003a7c3  test    al, al
0x18003a7c5  jnz     loc_18003A87C
0x18003a7cb  lea     rbx, [rdi+8]
0x18003a7cf  mov     rcx, rbx; SRWLock
0x18003a7d2  call    cs:__imp_AcquireSRWLockExclusive
0x18003a7d9  nop     dword ptr [rax+rax+00h]
0x18003a7de  mov     [rsp+48h+arg_18], rbx
0x18003a7e3  mov     eax, [rdi]
0x18003a7e5  test    eax, eax
0x18003a7e7  jz      loc_18003A871
0x18003a7ed  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003a7f2  test    al, al
0x18003a7f4  jnz     short loc_18003A871
0x18003a7f6  mov     [rsp+48h+Source], ebp
0x18003a7fa  xor     eax, eax
0x18003a7fc  mov     [rsp+48h+var_24], eax
0x18003a800  mov     [rsp+48h+var_20], rsi
0x18003a805  lea     rcx, [rdi+20h]; this
0x18003a809  lea     r8d, [rax+10h]; SourceSize
0x18003a80d  lea     rdx, [rsp+48h+Source]; Source
0x18003a812  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003a817  cmp     byte ptr [rdi+18h], 0
0x18003a81b  jnz     short loc_18003A871
0x18003a81d  lea     rbx, [rdi+10h]
0x18003a821  cmp     qword ptr [rbx], 0
0x18003a825  jnz     short loc_18003A85F
0x18003a827  lea     rcx, [rsp+48h+arg_0]; this
0x18003a82c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003a831  xor     r8d, r8d; pcbe
0x18003a834  mov     rdx, rdi; pv
0x18003a837  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003a83e  call    cs:__imp_CreateThreadpoolTimer
0x18003a845  nop     dword ptr [rax+rax+00h]
0x18003a84a  mov     rdx, rax
0x18003a84d  mov     rcx, rbx
0x18003a850  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003a855  lea     rcx, [rsp+48h+arg_0]; this
0x18003a85a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003a85f  mov     r8d, 493E0h
0x18003a865  lea     rdx, [rdi+18h]
0x18003a869  mov     rcx, rbx
0x18003a86c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003a871  lea     rcx, [rsp+48h+arg_18]
0x18003a876  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18003a87b  nop
0x18003a87c  mov     rbx, [rsp+48h+arg_8]
0x18003a881  add     rsp, 30h
0x18003a885  pop     rdi
0x18003a886  pop     rsi
0x18003a887  pop     rbp
0x18003a888  retn
```
