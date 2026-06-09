# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18005c054`
- end: `0x18005c137`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180050f50`

## callees

- `0x18004826c`
- `0x18004828c`
- `0x18004869c`
- `0x1800487ac`
- `0x1800487d0`
- `0x1800488f8`
- `0x18005c054`
- `0x18005c914`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18005c0f2`
- `KERNEL32!CreateThreadpoolTimer` at `0x18005c0f2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18005c090`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18005c090`

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
0x18005c054  push    rbp
0x18005c056  push    rsi
0x18005c057  push    rdi
0x18005c058  sub     rsp, 40h
0x18005c05c  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18005c065  mov     [rsp+58h+arg_8], rbx
0x18005c06a  mov     rsi, r8
0x18005c06d  mov     ebp, edx
0x18005c06f  mov     rdi, rcx
0x18005c072  mov     eax, [rcx]
0x18005c074  test    eax, eax
0x18005c076  jz      loc_18005C12A
0x18005c07c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18005c081  test    al, al
0x18005c083  jnz     loc_18005C12A
0x18005c089  lea     rbx, [rdi+8]
0x18005c08d  mov     rcx, rbx; SRWLock
0x18005c090  call    cs:__imp_AcquireSRWLockExclusive
0x18005c096  mov     [rsp+58h+arg_18], rbx
0x18005c09b  mov     eax, [rdi]
0x18005c09d  test    eax, eax
0x18005c09f  jz      short loc_18005C11F
0x18005c0a1  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18005c0a6  test    al, al
0x18005c0a8  jnz     short loc_18005C11F
0x18005c0aa  mov     [rsp+58h+var_30], ebp
0x18005c0ae  xor     eax, eax
0x18005c0b0  mov     [rsp+58h+var_2C], eax
0x18005c0b4  mov     [rsp+58h+var_28], rsi
0x18005c0b9  lea     rcx, [rdi+20h]; this
0x18005c0bd  lea     r8d, [rax+10h]; unsigned __int64
0x18005c0c1  lea     rdx, [rsp+58h+var_30]; void *
0x18005c0c6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18005c0cb  cmp     byte ptr [rdi+18h], 0
0x18005c0cf  jnz     short loc_18005C11F
0x18005c0d1  lea     rbx, [rdi+10h]
0x18005c0d5  cmp     qword ptr [rbx], 0
0x18005c0d9  jnz     short loc_18005C10D
0x18005c0db  lea     rcx, [rsp+58h+arg_0]; this
0x18005c0e0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005c0e5  xor     r8d, r8d; pcbe
0x18005c0e8  mov     rdx, rdi; pv
0x18005c0eb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005c0f2  call    cs:__imp_CreateThreadpoolTimer
0x18005c0f8  mov     rdx, rax
0x18005c0fb  mov     rcx, rbx
0x18005c0fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005c103  lea     rcx, [rsp+58h+arg_0]; this
0x18005c108  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005c10d  mov     r8d, 493E0h
0x18005c113  lea     rdx, [rdi+18h]
0x18005c117  mov     rcx, rbx
0x18005c11a  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18005c11f  lea     rcx, [rsp+58h+arg_18]
0x18005c124  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005c129  nop
0x18005c12a  mov     rbx, [rsp+58h+arg_8]
0x18005c12f  add     rsp, 40h
0x18005c133  pop     rdi
0x18005c134  pop     rsi
0x18005c135  pop     rbp
0x18005c136  retn
```
