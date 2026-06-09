# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180018a84`
- end: `0x180018b5c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180005500`

## callees

- `0x18000991c`
- `0x18000b49c`
- `0x18000bb00`
- `0x18000bb20`
- `0x18000bb44`
- `0x180012990`
- `0x180018a84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018ab3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018ab3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018b4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018b4c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018b14`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018b14`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  char v10; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
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
    if ( pv != (char *)-8LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 1);
  }
}

```

## disassembly

```asm
0x180018a84  push    rbx
0x180018a86  push    rbp
0x180018a87  push    rsi
0x180018a88  push    rdi
0x180018a89  sub     rsp, 38h
0x180018a8d  mov     rsi, r8
0x180018a90  mov     ebp, edx
0x180018a92  mov     rdi, rcx
0x180018a95  mov     eax, [rcx]
0x180018a97  test    eax, eax
0x180018a99  jz      loc_180018B53
0x180018a9f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180018aa4  test    al, al
0x180018aa6  jnz     loc_180018B53
0x180018aac  lea     rbx, [rdi+8]
0x180018ab0  mov     rcx, rbx; SRWLock
0x180018ab3  call    cs:__imp_AcquireSRWLockExclusive
0x180018ab9  mov     eax, [rdi]
0x180018abb  test    eax, eax
0x180018abd  jz      loc_180018B44
0x180018ac3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180018ac8  test    al, al
0x180018aca  jnz     short loc_180018B44
0x180018acc  mov     [rsp+58h+var_38], ebp
0x180018ad0  xor     eax, eax
0x180018ad2  mov     [rsp+58h+var_34], eax
0x180018ad6  mov     [rsp+58h+var_30], rsi
0x180018adb  lea     rcx, [rdi+20h]; this
0x180018adf  lea     r8d, [rax+10h]; unsigned __int64
0x180018ae3  lea     rdx, [rsp+58h+var_38]; void *
0x180018ae8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018aed  cmp     byte ptr [rdi+18h], 0
0x180018af1  jnz     short loc_180018B42
0x180018af3  lea     rsi, [rdi+10h]
0x180018af7  cmp     qword ptr [rsi], 0
0x180018afb  jnz     short loc_180018B2F
0x180018afd  lea     rcx, [rsp+58h+arg_0]; this
0x180018b02  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018b07  xor     r8d, r8d; pcbe
0x180018b0a  mov     rdx, rdi; pv
0x180018b0d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180018b14  call    cs:__imp_CreateThreadpoolTimer
0x180018b1a  mov     rdx, rax
0x180018b1d  mov     rcx, rsi
0x180018b20  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180018b25  lea     rcx, [rsp+58h+arg_0]; this
0x180018b2a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018b2f  mov     r8d, 493E0h
0x180018b35  lea     rdx, [rdi+18h]
0x180018b39  mov     rcx, rsi
0x180018b3c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180018b41  nop
0x180018b42  jmp     short $+2
0x180018b44  test    rbx, rbx
0x180018b47  jz      short loc_180018B53
0x180018b49  mov     rcx, rbx; SRWLock
0x180018b4c  call    cs:__imp_ReleaseSRWLockExclusive
0x180018b52  nop
0x180018b53  add     rsp, 38h
0x180018b57  pop     rdi
0x180018b58  pop     rsi
0x180018b59  pop     rbp
0x180018b5a  pop     rbx
0x180018b5b  retn
```
