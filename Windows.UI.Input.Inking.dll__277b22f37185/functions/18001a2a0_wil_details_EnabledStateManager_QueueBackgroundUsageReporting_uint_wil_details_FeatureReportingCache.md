# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001a2a0`
- end: `0x18001a379`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001adc0`

## callees

- `0x18000bac0`
- `0x18000bed8`
- `0x18000c2ec`
- `0x18000d8e4`
- `0x180011110`
- `0x180014d24`
- `0x180014e2c`
- `0x18001a2a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a2d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a2d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a334`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a334`

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
0x18001a2a0  mov     [rsp+arg_8], rbx
0x18001a2a5  push    rbp
0x18001a2a6  push    rsi
0x18001a2a7  push    rdi
0x18001a2a8  sub     rsp, 30h
0x18001a2ac  mov     rsi, r8
0x18001a2af  mov     ebp, edx
0x18001a2b1  mov     rdi, rcx
0x18001a2b4  mov     eax, [rcx]
0x18001a2b6  test    eax, eax
0x18001a2b8  jz      loc_18001A36C
0x18001a2be  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001a2c3  test    al, al
0x18001a2c5  jnz     loc_18001A36C
0x18001a2cb  lea     rbx, [rdi+8]
0x18001a2cf  mov     rcx, rbx; SRWLock
0x18001a2d2  call    cs:__imp_AcquireSRWLockExclusive
0x18001a2d8  mov     [rsp+48h+arg_18], rbx
0x18001a2dd  mov     eax, [rdi]
0x18001a2df  test    eax, eax
0x18001a2e1  jz      short loc_18001A361
0x18001a2e3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001a2e8  test    al, al
0x18001a2ea  jnz     short loc_18001A361
0x18001a2ec  mov     [rsp+48h+var_28], ebp
0x18001a2f0  xor     eax, eax
0x18001a2f2  mov     [rsp+48h+var_24], eax
0x18001a2f6  mov     [rsp+48h+var_20], rsi
0x18001a2fb  lea     rcx, [rdi+20h]; this
0x18001a2ff  lea     r8d, [rax+10h]; unsigned __int64
0x18001a303  lea     rdx, [rsp+48h+var_28]; void *
0x18001a308  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001a30d  cmp     byte ptr [rdi+18h], 0
0x18001a311  jnz     short loc_18001A361
0x18001a313  lea     rbx, [rdi+10h]
0x18001a317  cmp     qword ptr [rbx], 0
0x18001a31b  jnz     short loc_18001A34F
0x18001a31d  lea     rcx, [rsp+48h+arg_0]; this
0x18001a322  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a327  xor     r8d, r8d; pcbe
0x18001a32a  mov     rdx, rdi; pv
0x18001a32d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001a334  call    cs:__imp_CreateThreadpoolTimer
0x18001a33a  mov     rdx, rax
0x18001a33d  mov     rcx, rbx
0x18001a340  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001a345  lea     rcx, [rsp+48h+arg_0]; this
0x18001a34a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a34f  mov     r8d, 493E0h
0x18001a355  lea     rdx, [rdi+18h]
0x18001a359  mov     rcx, rbx
0x18001a35c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001a361  lea     rcx, [rsp+48h+arg_18]
0x18001a366  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001a36b  nop
0x18001a36c  mov     rbx, [rsp+48h+arg_8]
0x18001a371  add     rsp, 30h
0x18001a375  pop     rdi
0x18001a376  pop     rsi
0x18001a377  pop     rbp
0x18001a378  retn
```
