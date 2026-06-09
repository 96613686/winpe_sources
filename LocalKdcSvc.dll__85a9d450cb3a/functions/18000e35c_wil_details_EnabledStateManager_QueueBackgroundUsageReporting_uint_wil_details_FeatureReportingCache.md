# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000e35c`
- end: `0x18000e437`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `219`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000e754`

## callees

- `0x180004d34`
- `0x1800050ac`
- `0x1800053d4`
- `0x1800058a8`
- `0x180005af4`
- `0x18000773c`
- `0x18000996c`
- `0x180009a74`
- `0x18000e35c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e3ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e3ef`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-18h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-10h]
  char v10; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+58h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    wil::AcquireSRWLockExclusive(&v11, (RTL_SRWLOCK *)pv + 1);
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
0x18000e35c  mov     [rsp+arg_8], rbx
0x18000e361  mov     [rsp+arg_10], rsi
0x18000e366  push    rdi
0x18000e367  sub     rsp, 30h
0x18000e36b  mov     rdi, r8
0x18000e36e  mov     esi, edx
0x18000e370  mov     rbx, rcx
0x18000e373  mov     eax, [rcx]
0x18000e375  test    eax, eax
0x18000e377  jz      loc_18000E427
0x18000e37d  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000e382  test    al, al
0x18000e384  jnz     loc_18000E427
0x18000e38a  lea     rdx, [rbx+8]
0x18000e38e  lea     rcx, [rsp+38h+arg_18]
0x18000e393  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000e398  mov     eax, [rbx]
0x18000e39a  test    eax, eax
0x18000e39c  jz      short loc_18000E41C
0x18000e39e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000e3a3  test    al, al
0x18000e3a5  jnz     short loc_18000E41C
0x18000e3a7  mov     [rsp+38h+var_18], esi
0x18000e3ab  xor     eax, eax
0x18000e3ad  mov     [rsp+38h+var_14], eax
0x18000e3b1  mov     [rsp+38h+var_10], rdi
0x18000e3b6  lea     rcx, [rbx+20h]; this
0x18000e3ba  lea     r8d, [rax+10h]; unsigned __int64
0x18000e3be  lea     rdx, [rsp+38h+var_18]; void *
0x18000e3c3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000e3c8  cmp     byte ptr [rbx+18h], 0
0x18000e3cc  jnz     short loc_18000E41C
0x18000e3ce  lea     rdi, [rbx+10h]
0x18000e3d2  cmp     qword ptr [rdi], 0
0x18000e3d6  jnz     short loc_18000E40A
0x18000e3d8  lea     rcx, [rsp+38h+arg_0]; this
0x18000e3dd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e3e2  xor     r8d, r8d; pcbe
0x18000e3e5  mov     rdx, rbx; pv
0x18000e3e8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000e3ef  call    cs:__imp_CreateThreadpoolTimer
0x18000e3f5  mov     rdx, rax
0x18000e3f8  mov     rcx, rdi
0x18000e3fb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000e400  lea     rcx, [rsp+38h+arg_0]; this
0x18000e405  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e40a  mov     r8d, 493E0h
0x18000e410  lea     rdx, [rbx+18h]
0x18000e414  mov     rcx, rdi
0x18000e417  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000e41c  lea     rcx, [rsp+38h+arg_18]
0x18000e421  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e426  nop
0x18000e427  mov     rbx, [rsp+38h+arg_8]
0x18000e42c  mov     rsi, [rsp+38h+arg_10]
0x18000e431  add     rsp, 30h
0x18000e435  pop     rdi
0x18000e436  retn
```
