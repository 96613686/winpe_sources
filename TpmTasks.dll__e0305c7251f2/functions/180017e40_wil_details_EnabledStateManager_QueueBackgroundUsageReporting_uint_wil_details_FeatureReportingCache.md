# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180017e40`
- end: `0x180017f19`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180019ca4`

## callees

- `0x18000dd54`
- `0x18000e4cc`
- `0x18000ea88`
- `0x180010a4c`
- `0x180017b38`
- `0x180017e40`
- `0x180024720`
- `0x18002495c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017e72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017e72`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017ed4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017ed4`

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
0x180017e40  mov     [rsp+arg_8], rbx
0x180017e45  push    rbp
0x180017e46  push    rsi
0x180017e47  push    rdi
0x180017e48  sub     rsp, 30h
0x180017e4c  mov     rsi, r8
0x180017e4f  mov     ebp, edx
0x180017e51  mov     rdi, rcx
0x180017e54  mov     eax, [rcx]
0x180017e56  test    eax, eax
0x180017e58  jz      loc_180017F0C
0x180017e5e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180017e63  test    al, al
0x180017e65  jnz     loc_180017F0C
0x180017e6b  lea     rbx, [rdi+8]
0x180017e6f  mov     rcx, rbx; SRWLock
0x180017e72  call    cs:__imp_AcquireSRWLockExclusive
0x180017e78  mov     [rsp+48h+arg_18], rbx
0x180017e7d  mov     eax, [rdi]
0x180017e7f  test    eax, eax
0x180017e81  jz      short loc_180017F01
0x180017e83  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180017e88  test    al, al
0x180017e8a  jnz     short loc_180017F01
0x180017e8c  mov     [rsp+48h+var_28], ebp
0x180017e90  xor     eax, eax
0x180017e92  mov     [rsp+48h+var_24], eax
0x180017e96  mov     [rsp+48h+var_20], rsi
0x180017e9b  lea     rcx, [rdi+20h]; this
0x180017e9f  lea     r8d, [rax+10h]; unsigned __int64
0x180017ea3  lea     rdx, [rsp+48h+var_28]; void *
0x180017ea8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017ead  cmp     byte ptr [rdi+18h], 0
0x180017eb1  jnz     short loc_180017F01
0x180017eb3  lea     rbx, [rdi+10h]
0x180017eb7  cmp     qword ptr [rbx], 0
0x180017ebb  jnz     short loc_180017EEF
0x180017ebd  lea     rcx, [rsp+48h+arg_0]; this
0x180017ec2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017ec7  xor     r8d, r8d; pcbe
0x180017eca  mov     rdx, rdi; pv
0x180017ecd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017ed4  call    cs:__imp_CreateThreadpoolTimer
0x180017eda  mov     rdx, rax
0x180017edd  mov     rcx, rbx
0x180017ee0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180017ee5  lea     rcx, [rsp+48h+arg_0]; this
0x180017eea  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180017eef  mov     r8d, 493E0h
0x180017ef5  lea     rdx, [rdi+18h]
0x180017ef9  mov     rcx, rbx
0x180017efc  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180017f01  lea     rcx, [rsp+48h+arg_18]
0x180017f06  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017f0b  nop
0x180017f0c  mov     rbx, [rsp+48h+arg_8]
0x180017f11  add     rsp, 30h
0x180017f15  pop     rdi
0x180017f16  pop     rsi
0x180017f17  pop     rbp
0x180017f18  retn
```
