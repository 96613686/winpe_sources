# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180012cec`
- end: `0x180012dc4`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800101e0`

## callees

- `0x18000fa7c`
- `0x180011aa0`
- `0x180012294`
- `0x1800123d8`
- `0x180012cec`
- `0x18001ed4c`
- `0x18001ef60`
- `0x18001ff94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012d1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012d1e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012d80`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012d80`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v12 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v9[0] = a2;
        v9[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v9, 0x10u);
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
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x180012cec  mov     [rsp+arg_8], rbx
0x180012cf1  push    rbp
0x180012cf2  push    rsi
0x180012cf3  push    rdi
0x180012cf4  sub     rsp, 30h
0x180012cf8  mov     eax, [rcx]
0x180012cfa  mov     rsi, r8
0x180012cfd  mov     ebp, edx
0x180012cff  mov     rdi, rcx
0x180012d02  test    eax, eax
0x180012d04  jz      loc_180012DB7
0x180012d0a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180012d0f  test    al, al
0x180012d11  jnz     loc_180012DB7
0x180012d17  lea     rbx, [rdi+8]
0x180012d1b  mov     rcx, rbx; SRWLock
0x180012d1e  call    cs:__imp_AcquireSRWLockExclusive
0x180012d24  mov     eax, [rdi]
0x180012d26  mov     [rsp+48h+arg_18], rbx
0x180012d2b  test    eax, eax
0x180012d2d  jz      short loc_180012DAD
0x180012d2f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180012d34  test    al, al
0x180012d36  jnz     short loc_180012DAD
0x180012d38  xor     eax, eax
0x180012d3a  mov     [rsp+48h+var_28], ebp
0x180012d3e  lea     rcx, [rdi+20h]; this
0x180012d42  mov     [rsp+48h+var_24], eax
0x180012d46  lea     rdx, [rsp+48h+var_28]; void *
0x180012d4b  mov     [rsp+48h+var_20], rsi
0x180012d50  lea     r8d, [rax+10h]; unsigned __int64
0x180012d54  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180012d59  cmp     byte ptr [rdi+18h], 0
0x180012d5d  jnz     short loc_180012DAD
0x180012d5f  lea     rbx, [rdi+10h]
0x180012d63  cmp     qword ptr [rbx], 0
0x180012d67  jnz     short loc_180012D9B
0x180012d69  lea     rcx, [rsp+48h+arg_0]; this
0x180012d6e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180012d73  xor     r8d, r8d; pcbe
0x180012d76  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180012d7d  mov     rdx, rdi; pv
0x180012d80  call    cs:__imp_CreateThreadpoolTimer
0x180012d86  mov     rdx, rax
0x180012d89  mov     rcx, rbx
0x180012d8c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180012d91  lea     rcx, [rsp+48h+arg_0]; this
0x180012d96  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180012d9b  mov     r8d, 493E0h
0x180012da1  lea     rdx, [rdi+18h]
0x180012da5  mov     rcx, rbx
0x180012da8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180012dad  lea     rcx, [rsp+48h+arg_18]
0x180012db2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012db7  mov     rbx, [rsp+48h+arg_8]
0x180012dbc  add     rsp, 30h
0x180012dc0  pop     rdi
0x180012dc1  pop     rsi
0x180012dc2  pop     rbp
0x180012dc3  retn
```
