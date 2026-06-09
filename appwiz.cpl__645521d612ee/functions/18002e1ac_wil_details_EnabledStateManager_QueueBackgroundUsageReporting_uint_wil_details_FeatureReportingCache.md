# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18002e1ac`
- end: `0x18002e284`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002e410`

## callees

- `0x180005c48`
- `0x180005eb8`
- `0x180007424`
- `0x180008d54`
- `0x180012af0`
- `0x18001aea0`
- `0x18001afac`
- `0x18002e1ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e1de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e1de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002e240`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002e240`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v12 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v9[0] = a2;
        v9[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v9, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x18002e1ac  mov     [rsp+arg_8], rbx
0x18002e1b1  push    rbp
0x18002e1b2  push    rsi
0x18002e1b3  push    rdi
0x18002e1b4  sub     rsp, 30h
0x18002e1b8  mov     eax, [rcx]
0x18002e1ba  mov     rsi, r8
0x18002e1bd  mov     ebp, edx
0x18002e1bf  mov     rdi, rcx
0x18002e1c2  test    eax, eax
0x18002e1c4  jz      loc_18002E277
0x18002e1ca  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002e1cf  test    al, al
0x18002e1d1  jnz     loc_18002E277
0x18002e1d7  lea     rbx, [rdi+8]
0x18002e1db  mov     rcx, rbx; SRWLock
0x18002e1de  call    cs:__imp_AcquireSRWLockExclusive
0x18002e1e4  mov     eax, [rdi]
0x18002e1e6  mov     [rsp+48h+arg_18], rbx
0x18002e1eb  test    eax, eax
0x18002e1ed  jz      short loc_18002E26D
0x18002e1ef  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002e1f4  test    al, al
0x18002e1f6  jnz     short loc_18002E26D
0x18002e1f8  xor     eax, eax
0x18002e1fa  mov     [rsp+48h+var_28], ebp
0x18002e1fe  lea     rcx, [rdi+20h]; this
0x18002e202  mov     [rsp+48h+var_24], eax
0x18002e206  lea     rdx, [rsp+48h+var_28]; void *
0x18002e20b  mov     [rsp+48h+var_20], rsi
0x18002e210  lea     r8d, [rax+10h]; unsigned __int64
0x18002e214  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002e219  cmp     byte ptr [rdi+18h], 0
0x18002e21d  jnz     short loc_18002E26D
0x18002e21f  lea     rbx, [rdi+10h]
0x18002e223  cmp     qword ptr [rbx], 0
0x18002e227  jnz     short loc_18002E25B
0x18002e229  lea     rcx, [rsp+48h+arg_0]; this
0x18002e22e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002e233  xor     r8d, r8d; pcbe
0x18002e236  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002e23d  mov     rdx, rdi; pv
0x18002e240  call    cs:__imp_CreateThreadpoolTimer
0x18002e246  mov     rdx, rax
0x18002e249  mov     rcx, rbx
0x18002e24c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002e251  lea     rcx, [rsp+48h+arg_0]; this
0x18002e256  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002e25b  mov     r8d, 493E0h
0x18002e261  lea     rdx, [rdi+18h]
0x18002e265  mov     rcx, rbx
0x18002e268  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002e26d  lea     rcx, [rsp+48h+arg_18]
0x18002e272  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002e277  mov     rbx, [rsp+48h+arg_8]
0x18002e27c  add     rsp, 30h
0x18002e280  pop     rdi
0x18002e281  pop     rsi
0x18002e282  pop     rbp
0x18002e283  retn
```
