# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001ee24`
- end: `0x18001eefd`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001e990`

## callees

- `0x18001ee24`
- `0x180023e34`
- `0x180027c28`
- `0x180027d38`
- `0x1800286c4`
- `0x18003512c`
- `0x18003514c`
- `0x180035170`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ee56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ee56`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001eeb8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001eeb8`

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
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18001ee24  mov     [rsp+arg_8], rbx
0x18001ee29  push    rbp
0x18001ee2a  push    rsi
0x18001ee2b  push    rdi
0x18001ee2c  sub     rsp, 30h
0x18001ee30  mov     rsi, r8
0x18001ee33  mov     ebp, edx
0x18001ee35  mov     rdi, rcx
0x18001ee38  mov     eax, [rcx]
0x18001ee3a  test    eax, eax
0x18001ee3c  jz      loc_18001EEF0
0x18001ee42  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001ee47  test    al, al
0x18001ee49  jnz     loc_18001EEF0
0x18001ee4f  lea     rbx, [rdi+8]
0x18001ee53  mov     rcx, rbx; SRWLock
0x18001ee56  call    cs:__imp_AcquireSRWLockExclusive
0x18001ee5c  mov     [rsp+48h+arg_18], rbx
0x18001ee61  mov     eax, [rdi]
0x18001ee63  test    eax, eax
0x18001ee65  jz      short loc_18001EEE5
0x18001ee67  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001ee6c  test    al, al
0x18001ee6e  jnz     short loc_18001EEE5
0x18001ee70  mov     [rsp+48h+Source], ebp
0x18001ee74  xor     eax, eax
0x18001ee76  mov     [rsp+48h+var_24], eax
0x18001ee7a  mov     [rsp+48h+var_20], rsi
0x18001ee7f  lea     rcx, [rdi+20h]; this
0x18001ee83  lea     r8d, [rax+10h]; SourceSize
0x18001ee87  lea     rdx, [rsp+48h+Source]; Source
0x18001ee8c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001ee91  cmp     byte ptr [rdi+18h], 0
0x18001ee95  jnz     short loc_18001EEE5
0x18001ee97  lea     rbx, [rdi+10h]
0x18001ee9b  cmp     qword ptr [rbx], 0
0x18001ee9f  jnz     short loc_18001EED3
0x18001eea1  lea     rcx, [rsp+48h+arg_0]; this
0x18001eea6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001eeab  xor     r8d, r8d; pcbe
0x18001eeae  mov     rdx, rdi; pv
0x18001eeb1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001eeb8  call    cs:__imp_CreateThreadpoolTimer
0x18001eebe  mov     rdx, rax
0x18001eec1  mov     rcx, rbx
0x18001eec4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001eec9  lea     rcx, [rsp+48h+arg_0]; this
0x18001eece  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001eed3  mov     r8d, 493E0h
0x18001eed9  lea     rdx, [rdi+18h]
0x18001eedd  mov     rcx, rbx
0x18001eee0  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001eee5  lea     rcx, [rsp+48h+arg_18]
0x18001eeea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001eeef  nop
0x18001eef0  mov     rbx, [rsp+48h+arg_8]
0x18001eef5  add     rsp, 30h
0x18001eef9  pop     rdi
0x18001eefa  pop     rsi
0x18001eefb  pop     rbp
0x18001eefc  retn
```
