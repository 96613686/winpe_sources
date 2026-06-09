# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000eb68`
- end: `0x18000ec41`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000fff0`

## callees

- `0x180009b34`
- `0x180009edc`
- `0x18000a37c`
- `0x18000b030`
- `0x18000e88c`
- `0x18000eb68`
- `0x180012b98`
- `0x180012cb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eb9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eb9a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ebfc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ebfc`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v11 = (RTL_SRWLOCK *)(pv + 8);
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
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18000eb68  mov     [rsp+arg_8], rbx
0x18000eb6d  push    rbp
0x18000eb6e  push    rsi
0x18000eb6f  push    rdi
0x18000eb70  sub     rsp, 30h
0x18000eb74  mov     rsi, r8
0x18000eb77  mov     ebp, edx
0x18000eb79  mov     rdi, rcx
0x18000eb7c  mov     eax, [rcx]
0x18000eb7e  test    eax, eax
0x18000eb80  jz      loc_18000EC34
0x18000eb86  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000eb8b  test    al, al
0x18000eb8d  jnz     loc_18000EC34
0x18000eb93  lea     rbx, [rdi+8]
0x18000eb97  mov     rcx, rbx; SRWLock
0x18000eb9a  call    cs:__imp_AcquireSRWLockExclusive
0x18000eba0  mov     [rsp+48h+arg_18], rbx
0x18000eba5  mov     eax, [rdi]
0x18000eba7  test    eax, eax
0x18000eba9  jz      short loc_18000EC29
0x18000ebab  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000ebb0  test    al, al
0x18000ebb2  jnz     short loc_18000EC29
0x18000ebb4  mov     [rsp+48h+var_28], ebp
0x18000ebb8  xor     eax, eax
0x18000ebba  mov     [rsp+48h+var_24], eax
0x18000ebbe  mov     [rsp+48h+var_20], rsi
0x18000ebc3  lea     rcx, [rdi+20h]; this
0x18000ebc7  lea     r8d, [rax+10h]; unsigned __int64
0x18000ebcb  lea     rdx, [rsp+48h+var_28]; void *
0x18000ebd0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ebd5  cmp     byte ptr [rdi+18h], 0
0x18000ebd9  jnz     short loc_18000EC29
0x18000ebdb  lea     rbx, [rdi+10h]
0x18000ebdf  cmp     qword ptr [rbx], 0
0x18000ebe3  jnz     short loc_18000EC17
0x18000ebe5  lea     rcx, [rsp+48h+arg_0]; this
0x18000ebea  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000ebef  xor     r8d, r8d; pcbe
0x18000ebf2  mov     rdx, rdi; pv
0x18000ebf5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ebfc  call    cs:__imp_CreateThreadpoolTimer
0x18000ec02  mov     rdx, rax
0x18000ec05  mov     rcx, rbx
0x18000ec08  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000ec0d  lea     rcx, [rsp+48h+arg_0]; this
0x18000ec12  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ec17  mov     r8d, 493E0h
0x18000ec1d  lea     rdx, [rdi+18h]
0x18000ec21  mov     rcx, rbx
0x18000ec24  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000ec29  lea     rcx, [rsp+48h+arg_18]
0x18000ec2e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ec33  nop
0x18000ec34  mov     rbx, [rsp+48h+arg_8]
0x18000ec39  add     rsp, 30h
0x18000ec3d  pop     rdi
0x18000ec3e  pop     rsi
0x18000ec3f  pop     rbp
0x18000ec40  retn
```
