# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14001c0fc`
- end: `0x14001c1d5`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14001f198`

## callees

- `0x14000e428`
- `0x14000ed94`
- `0x14000f384`
- `0x140011d14`
- `0x14001bd3c`
- `0x14001c0fc`
- `0x14002bf20`
- `0x14002c328`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x14001c190`
- `KERNEL32!CreateThreadpoolTimer` at `0x14001c190`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001c12e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001c12e`

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
0x14001c0fc  mov     [rsp+arg_8], rbx
0x14001c101  push    rbp
0x14001c102  push    rsi
0x14001c103  push    rdi
0x14001c104  sub     rsp, 30h
0x14001c108  mov     rsi, r8
0x14001c10b  mov     ebp, edx
0x14001c10d  mov     rdi, rcx
0x14001c110  mov     eax, [rcx]
0x14001c112  test    eax, eax
0x14001c114  jz      loc_14001C1C8
0x14001c11a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14001c11f  test    al, al
0x14001c121  jnz     loc_14001C1C8
0x14001c127  lea     rbx, [rdi+8]
0x14001c12b  mov     rcx, rbx; SRWLock
0x14001c12e  call    cs:__imp_AcquireSRWLockExclusive
0x14001c134  mov     [rsp+48h+arg_18], rbx
0x14001c139  mov     eax, [rdi]
0x14001c13b  test    eax, eax
0x14001c13d  jz      short loc_14001C1BD
0x14001c13f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14001c144  test    al, al
0x14001c146  jnz     short loc_14001C1BD
0x14001c148  mov     [rsp+48h+var_28], ebp
0x14001c14c  xor     eax, eax
0x14001c14e  mov     [rsp+48h+var_24], eax
0x14001c152  mov     [rsp+48h+var_20], rsi
0x14001c157  lea     rcx, [rdi+20h]; this
0x14001c15b  lea     r8d, [rax+10h]; unsigned __int64
0x14001c15f  lea     rdx, [rsp+48h+var_28]; void *
0x14001c164  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14001c169  cmp     byte ptr [rdi+18h], 0
0x14001c16d  jnz     short loc_14001C1BD
0x14001c16f  lea     rbx, [rdi+10h]
0x14001c173  cmp     qword ptr [rbx], 0
0x14001c177  jnz     short loc_14001C1AB
0x14001c179  lea     rcx, [rsp+48h+arg_0]; this
0x14001c17e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001c183  xor     r8d, r8d; pcbe
0x14001c186  mov     rdx, rdi; pv
0x14001c189  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14001c190  call    cs:__imp_CreateThreadpoolTimer
0x14001c196  mov     rdx, rax
0x14001c199  mov     rcx, rbx
0x14001c19c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14001c1a1  lea     rcx, [rsp+48h+arg_0]; this
0x14001c1a6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001c1ab  mov     r8d, 493E0h
0x14001c1b1  lea     rdx, [rdi+18h]
0x14001c1b5  mov     rcx, rbx
0x14001c1b8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14001c1bd  lea     rcx, [rsp+48h+arg_18]
0x14001c1c2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14001c1c7  nop
0x14001c1c8  mov     rbx, [rsp+48h+arg_8]
0x14001c1cd  add     rsp, 30h
0x14001c1d1  pop     rdi
0x14001c1d2  pop     rsi
0x14001c1d3  pop     rbp
0x14001c1d4  retn
```
