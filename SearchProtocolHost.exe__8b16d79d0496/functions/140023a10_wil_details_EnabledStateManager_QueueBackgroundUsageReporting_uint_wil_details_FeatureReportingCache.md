# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140023a10`
- end: `0x140023af3`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140027b70`

## callees

- `0x14000e2b4`
- `0x14000f30c`
- `0x1400101e4`
- `0x1400155e8`
- `0x140021ddc`
- `0x140023a10`
- `0x1400375c4`
- `0x140037d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140023a4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140023a4c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140023aae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140023aae`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+28h] [rbp-30h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+30h] [rbp-28h]
  char v10; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+78h] [rbp+20h] BYREF

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
0x140023a10  push    rbp
0x140023a12  push    rsi
0x140023a13  push    rdi
0x140023a14  sub     rsp, 40h
0x140023a18  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x140023a21  mov     [rsp+58h+arg_8], rbx
0x140023a26  mov     rsi, r8
0x140023a29  mov     ebp, edx
0x140023a2b  mov     rdi, rcx
0x140023a2e  mov     eax, [rcx]
0x140023a30  test    eax, eax
0x140023a32  jz      loc_140023AE6
0x140023a38  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140023a3d  test    al, al
0x140023a3f  jnz     loc_140023AE6
0x140023a45  lea     rbx, [rdi+8]
0x140023a49  mov     rcx, rbx; SRWLock
0x140023a4c  call    cs:__imp_AcquireSRWLockExclusive
0x140023a52  mov     [rsp+58h+arg_18], rbx
0x140023a57  mov     eax, [rdi]
0x140023a59  test    eax, eax
0x140023a5b  jz      short loc_140023ADB
0x140023a5d  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140023a62  test    al, al
0x140023a64  jnz     short loc_140023ADB
0x140023a66  mov     [rsp+58h+var_30], ebp
0x140023a6a  xor     eax, eax
0x140023a6c  mov     [rsp+58h+var_2C], eax
0x140023a70  mov     [rsp+58h+var_28], rsi
0x140023a75  lea     rcx, [rdi+20h]; this
0x140023a79  lea     r8d, [rax+10h]; unsigned __int64
0x140023a7d  lea     rdx, [rsp+58h+var_30]; void *
0x140023a82  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140023a87  cmp     byte ptr [rdi+18h], 0
0x140023a8b  jnz     short loc_140023ADB
0x140023a8d  lea     rbx, [rdi+10h]
0x140023a91  cmp     qword ptr [rbx], 0
0x140023a95  jnz     short loc_140023AC9
0x140023a97  lea     rcx, [rsp+58h+arg_0]; this
0x140023a9c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140023aa1  xor     r8d, r8d; pcbe
0x140023aa4  mov     rdx, rdi; pv
0x140023aa7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140023aae  call    cs:__imp_CreateThreadpoolTimer
0x140023ab4  mov     rdx, rax
0x140023ab7  mov     rcx, rbx
0x140023aba  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140023abf  lea     rcx, [rsp+58h+arg_0]; this
0x140023ac4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140023ac9  mov     r8d, 493E0h
0x140023acf  lea     rdx, [rdi+18h]
0x140023ad3  mov     rcx, rbx
0x140023ad6  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140023adb  lea     rcx, [rsp+58h+arg_18]
0x140023ae0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140023ae5  nop
0x140023ae6  mov     rbx, [rsp+58h+arg_8]
0x140023aeb  add     rsp, 40h
0x140023aef  pop     rdi
0x140023af0  pop     rsi
0x140023af1  pop     rbp
0x140023af2  retn
```
