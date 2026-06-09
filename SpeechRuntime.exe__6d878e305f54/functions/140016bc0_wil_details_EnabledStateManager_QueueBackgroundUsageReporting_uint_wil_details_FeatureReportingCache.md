# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140016bc0`
- end: `0x140016c99`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400178b8`

## callees

- `0x140007b48`
- `0x140007fa8`
- `0x140008248`
- `0x14000d398`
- `0x1400150b4`
- `0x140016bc0`
- `0x140018b60`
- `0x140018c68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016bf2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016bf2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140016c54`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140016c54`

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
0x140016bc0  mov     [rsp+arg_8], rbx
0x140016bc5  push    rbp
0x140016bc6  push    rsi
0x140016bc7  push    rdi
0x140016bc8  sub     rsp, 30h
0x140016bcc  mov     rsi, r8
0x140016bcf  mov     ebp, edx
0x140016bd1  mov     rdi, rcx
0x140016bd4  mov     eax, [rcx]
0x140016bd6  test    eax, eax
0x140016bd8  jz      loc_140016C8C
0x140016bde  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140016be3  test    al, al
0x140016be5  jnz     loc_140016C8C
0x140016beb  lea     rbx, [rdi+8]
0x140016bef  mov     rcx, rbx; SRWLock
0x140016bf2  call    cs:__imp_AcquireSRWLockExclusive
0x140016bf8  mov     [rsp+48h+arg_18], rbx
0x140016bfd  mov     eax, [rdi]
0x140016bff  test    eax, eax
0x140016c01  jz      short loc_140016C81
0x140016c03  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140016c08  test    al, al
0x140016c0a  jnz     short loc_140016C81
0x140016c0c  mov     [rsp+48h+var_28], ebp
0x140016c10  xor     eax, eax
0x140016c12  mov     [rsp+48h+var_24], eax
0x140016c16  mov     [rsp+48h+var_20], rsi
0x140016c1b  lea     rcx, [rdi+20h]; this
0x140016c1f  lea     r8d, [rax+10h]; unsigned __int64
0x140016c23  lea     rdx, [rsp+48h+var_28]; void *
0x140016c28  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140016c2d  cmp     byte ptr [rdi+18h], 0
0x140016c31  jnz     short loc_140016C81
0x140016c33  lea     rbx, [rdi+10h]
0x140016c37  cmp     qword ptr [rbx], 0
0x140016c3b  jnz     short loc_140016C6F
0x140016c3d  lea     rcx, [rsp+48h+arg_0]; this
0x140016c42  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140016c47  xor     r8d, r8d; pcbe
0x140016c4a  mov     rdx, rdi; pv
0x140016c4d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140016c54  call    cs:__imp_CreateThreadpoolTimer
0x140016c5a  mov     rdx, rax
0x140016c5d  mov     rcx, rbx
0x140016c60  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140016c65  lea     rcx, [rsp+48h+arg_0]; this
0x140016c6a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140016c6f  mov     r8d, 493E0h
0x140016c75  lea     rdx, [rdi+18h]
0x140016c79  mov     rcx, rbx
0x140016c7c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140016c81  lea     rcx, [rsp+48h+arg_18]
0x140016c86  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140016c8b  nop
0x140016c8c  mov     rbx, [rsp+48h+arg_8]
0x140016c91  add     rsp, 30h
0x140016c95  pop     rdi
0x140016c96  pop     rsi
0x140016c97  pop     rbp
0x140016c98  retn
```
