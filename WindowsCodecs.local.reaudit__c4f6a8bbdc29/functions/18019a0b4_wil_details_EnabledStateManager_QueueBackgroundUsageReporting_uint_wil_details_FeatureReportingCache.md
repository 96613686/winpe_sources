# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18019a0b4`
- end: `0x18019a1a2`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `238`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800cb3a0`

## callees

- `0x1800ac45c`
- `0x1800b866c`
- `0x1800e30ac`
- `0x1800e30d0`
- `0x1800e3118`
- `0x1800e313c`
- `0x180198860`
- `0x18019a0b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18019a0e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18019a0e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18019a154`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18019a154`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  char v9; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v10; // [rsp+58h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v10 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v8[0] = 36703308;
        v8[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18019a0b4  mov     [rsp+arg_8], rbx
0x18019a0b9  mov     [rsp+arg_10], rsi
0x18019a0be  push    rdi
0x18019a0bf  sub     rsp, 30h
0x18019a0c3  mov     eax, [rcx]
0x18019a0c5  mov     rsi, r8
0x18019a0c8  mov     rdi, rcx
0x18019a0cb  test    eax, eax
0x18019a0cd  jz      loc_18019A191
0x18019a0d3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18019a0d8  test    al, al
0x18019a0da  jnz     loc_18019A191
0x18019a0e0  lea     rbx, [rdi+8]
0x18019a0e4  mov     rcx, rbx; SRWLock
0x18019a0e7  call    cs:__imp_AcquireSRWLockExclusive
0x18019a0ee  nop     dword ptr [rax+rax+00h]
0x18019a0f3  mov     eax, [rdi]
0x18019a0f5  mov     [rsp+38h+arg_18], rbx
0x18019a0fa  test    eax, eax
0x18019a0fc  jz      loc_18019A187
0x18019a102  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18019a107  test    al, al
0x18019a109  jnz     short loc_18019A187
0x18019a10b  lea     rcx, [rdi+30h]; this
0x18019a10f  mov     [rsp+38h+var_18], 2300C4Ch
0x18019a118  mov     r8d, 10h; unsigned __int64
0x18019a11e  mov     [rsp+38h+var_10], rsi
0x18019a123  lea     rdx, [rsp+38h+var_18]; void *
0x18019a128  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18019a12d  cmp     byte ptr [rdi+18h], 0
0x18019a131  jnz     short loc_18019A187
0x18019a133  lea     rbx, [rdi+10h]
0x18019a137  cmp     qword ptr [rbx], 0
0x18019a13b  jnz     short loc_18019A175
0x18019a13d  lea     rcx, [rsp+38h+arg_0]; this
0x18019a142  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18019a147  xor     r8d, r8d; pcbe
0x18019a14a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18019a151  mov     rdx, rdi; pv
0x18019a154  call    cs:__imp_CreateThreadpoolTimer
0x18019a15b  nop     dword ptr [rax+rax+00h]
0x18019a160  mov     rdx, rax
0x18019a163  mov     rcx, rbx
0x18019a166  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18019a16b  lea     rcx, [rsp+38h+arg_0]; this
0x18019a170  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18019a175  mov     r8d, 493E0h
0x18019a17b  lea     rdx, [rdi+18h]
0x18019a17f  mov     rcx, rbx
0x18019a182  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18019a187  lea     rcx, [rsp+38h+arg_18]
0x18019a18c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18019a191  mov     rbx, [rsp+38h+arg_8]
0x18019a196  mov     rsi, [rsp+38h+arg_10]
0x18019a19b  add     rsp, 30h
0x18019a19f  pop     rdi
0x18019a1a0  retn
```
