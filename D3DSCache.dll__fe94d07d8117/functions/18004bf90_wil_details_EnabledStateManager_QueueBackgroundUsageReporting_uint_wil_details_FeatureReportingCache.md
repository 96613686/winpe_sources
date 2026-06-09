# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18004bf90`
- end: `0x18004c06e`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `222`
- prototype: `void __fastcall(char *pv, __int64, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004ccb8`

## callees

- `0x180048a24`
- `0x180048cd4`
- `0x180049020`
- `0x180049ae0`
- `0x18004be70`
- `0x18004bf90`
- `0x18004ee18`
- `0x18004ef9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004bfc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004bfc3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004c026`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004c026`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+40h] [rbp+8h] BYREF
  char *v9; // [rsp+58h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v9 = pv + 8;
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v7[0] = 59898901;
        v7[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v7, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x18004bf90  mov     [rsp+arg_8], rbx
0x18004bf95  mov     [rsp+arg_10], rsi
0x18004bf9a  push    rdi
0x18004bf9b  sub     rsp, 30h
0x18004bf9f  mov     rsi, r8
0x18004bfa2  mov     rdi, rcx
0x18004bfa5  mov     eax, [rcx]
0x18004bfa7  test    eax, eax
0x18004bfa9  jz      loc_18004C05E
0x18004bfaf  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004bfb4  test    al, al
0x18004bfb6  jnz     loc_18004C05E
0x18004bfbc  lea     rbx, [rdi+8]
0x18004bfc0  mov     rcx, rbx; SRWLock
0x18004bfc3  call    cs:__imp_AcquireSRWLockExclusive
0x18004bfc9  mov     [rsp+38h+arg_18], rbx
0x18004bfce  mov     eax, [rdi]
0x18004bfd0  test    eax, eax
0x18004bfd2  jz      short loc_18004C053
0x18004bfd4  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004bfd9  test    al, al
0x18004bfdb  jnz     short loc_18004C053
0x18004bfdd  mov     [rsp+38h+var_18], 391FC15h
0x18004bfe6  mov     [rsp+38h+var_10], rsi
0x18004bfeb  lea     rcx, [rdi+20h]; this
0x18004bfef  mov     r8d, 10h; unsigned __int64
0x18004bff5  lea     rdx, [rsp+38h+var_18]; void *
0x18004bffa  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18004bfff  cmp     byte ptr [rdi+18h], 0
0x18004c003  jnz     short loc_18004C053
0x18004c005  lea     rbx, [rdi+10h]
0x18004c009  cmp     qword ptr [rbx], 0
0x18004c00d  jnz     short loc_18004C041
0x18004c00f  lea     rcx, [rsp+38h+arg_0]; this
0x18004c014  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004c019  xor     r8d, r8d; pcbe
0x18004c01c  mov     rdx, rdi; pv
0x18004c01f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004c026  call    cs:__imp_CreateThreadpoolTimer
0x18004c02c  mov     rdx, rax
0x18004c02f  mov     rcx, rbx
0x18004c032  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004c037  lea     rcx, [rsp+38h+arg_0]; this
0x18004c03c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004c041  mov     r8d, 493E0h
0x18004c047  lea     rdx, [rdi+18h]
0x18004c04b  mov     rcx, rbx
0x18004c04e  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18004c053  lea     rcx, [rsp+38h+arg_18]
0x18004c058  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004c05d  nop
0x18004c05e  mov     rbx, [rsp+38h+arg_8]
0x18004c063  mov     rsi, [rsp+38h+arg_10]
0x18004c068  add     rsp, 30h
0x18004c06c  pop     rdi
0x18004c06d  retn
```
