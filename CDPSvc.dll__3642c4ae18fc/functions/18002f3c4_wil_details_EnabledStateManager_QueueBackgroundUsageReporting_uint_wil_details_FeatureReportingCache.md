# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18002f3c4`
- end: `0x18002f491`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `205`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002f654`

## callees

- `0x18000a3f0`
- `0x18000a52c`
- `0x180019938`
- `0x180019958`
- `0x18001999c`
- `0x18002b2e0`
- `0x18002f3c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f3f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f3f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f481`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f481`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002f44c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002f44c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  int v8; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  char v10; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8 = a2;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], &v8, 0x10u);
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
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x18002f3c4  push    rbx
0x18002f3c6  push    rbp
0x18002f3c7  push    rsi
0x18002f3c8  push    rdi
0x18002f3c9  sub     rsp, 38h
0x18002f3cd  mov     rsi, r8
0x18002f3d0  mov     ebp, edx
0x18002f3d2  mov     rbx, rcx
0x18002f3d5  mov     eax, [rcx]
0x18002f3d7  test    eax, eax
0x18002f3d9  jz      loc_18002F488
0x18002f3df  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002f3e4  test    al, al
0x18002f3e6  jnz     loc_18002F488
0x18002f3ec  lea     rdi, [rbx+8]
0x18002f3f0  mov     rcx, rdi; SRWLock
0x18002f3f3  call    cs:__imp_AcquireSRWLockExclusive
0x18002f3f9  mov     eax, [rbx]
0x18002f3fb  test    eax, eax
0x18002f3fd  jz      short loc_18002F479
0x18002f3ff  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002f404  test    al, al
0x18002f406  jnz     short loc_18002F479
0x18002f408  mov     [rsp+58h+var_38], ebp
0x18002f40c  mov     [rsp+58h+var_30], rsi
0x18002f411  lea     rcx, [rbx+20h]; this
0x18002f415  mov     r8d, 10h; unsigned __int64
0x18002f41b  lea     rdx, [rsp+58h+var_38]; void *
0x18002f420  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002f425  cmp     byte ptr [rbx+18h], 0
0x18002f429  jnz     short loc_18002F479
0x18002f42b  lea     rsi, [rbx+10h]
0x18002f42f  cmp     qword ptr [rsi], 0
0x18002f433  jnz     short loc_18002F467
0x18002f435  lea     rcx, [rsp+58h+arg_0]; this
0x18002f43a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002f43f  xor     r8d, r8d; pcbe
0x18002f442  mov     rdx, rbx; pv
0x18002f445  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002f44c  call    cs:__imp_CreateThreadpoolTimer
0x18002f452  mov     rdx, rax
0x18002f455  mov     rcx, rsi
0x18002f458  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002f45d  lea     rcx, [rsp+58h+arg_0]; this
0x18002f462  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002f467  mov     r8d, 493E0h
0x18002f46d  lea     rdx, [rbx+18h]
0x18002f471  mov     rcx, rsi
0x18002f474  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002f479  test    rdi, rdi
0x18002f47c  jz      short loc_18002F488
0x18002f47e  mov     rcx, rdi; SRWLock
0x18002f481  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f487  nop
0x18002f488  add     rsp, 38h
0x18002f48c  pop     rdi
0x18002f48d  pop     rsi
0x18002f48e  pop     rbp
0x18002f48f  pop     rbx
0x18002f490  retn
```
