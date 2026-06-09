# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18006c684`
- end: `0x18006c761`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `221`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006c840`

## callees

- `0x180050f10`
- `0x180051168`
- `0x1800515a4`
- `0x180051e14`
- `0x180054390`
- `0x180056710`
- `0x180056818`
- `0x18006c684`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18006c71a`
- `KERNEL32!CreateThreadpoolTimer` at `0x18006c71a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18006c6b7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18006c6b7`

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
        v8[0] = 59692005;
        v8[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
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
0x18006c684  mov     [rsp+arg_8], rbx
0x18006c689  mov     [rsp+arg_10], rsi
0x18006c68e  push    rdi
0x18006c68f  sub     rsp, 30h
0x18006c693  mov     eax, [rcx]
0x18006c695  mov     rsi, r8
0x18006c698  mov     rdi, rcx
0x18006c69b  test    eax, eax
0x18006c69d  jz      loc_18006C751
0x18006c6a3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18006c6a8  test    al, al
0x18006c6aa  jnz     loc_18006C751
0x18006c6b0  lea     rbx, [rdi+8]
0x18006c6b4  mov     rcx, rbx; SRWLock
0x18006c6b7  call    cs:__imp_AcquireSRWLockExclusive
0x18006c6bd  mov     eax, [rdi]
0x18006c6bf  mov     [rsp+38h+arg_18], rbx
0x18006c6c4  test    eax, eax
0x18006c6c6  jz      short loc_18006C747
0x18006c6c8  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18006c6cd  test    al, al
0x18006c6cf  jnz     short loc_18006C747
0x18006c6d1  lea     rcx, [rdi+20h]; this
0x18006c6d5  mov     [rsp+38h+var_18], 38ED3E5h
0x18006c6de  mov     r8d, 10h; unsigned __int64
0x18006c6e4  mov     [rsp+38h+var_10], rsi
0x18006c6e9  lea     rdx, [rsp+38h+var_18]; void *
0x18006c6ee  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18006c6f3  cmp     byte ptr [rdi+18h], 0
0x18006c6f7  jnz     short loc_18006C747
0x18006c6f9  lea     rbx, [rdi+10h]
0x18006c6fd  cmp     qword ptr [rbx], 0
0x18006c701  jnz     short loc_18006C735
0x18006c703  lea     rcx, [rsp+38h+arg_0]; this
0x18006c708  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006c70d  xor     r8d, r8d; pcbe
0x18006c710  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006c717  mov     rdx, rdi; pv
0x18006c71a  call    cs:__imp_CreateThreadpoolTimer
0x18006c720  mov     rdx, rax
0x18006c723  mov     rcx, rbx
0x18006c726  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18006c72b  lea     rcx, [rsp+38h+arg_0]; this
0x18006c730  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006c735  mov     r8d, 493E0h
0x18006c73b  lea     rdx, [rdi+18h]
0x18006c73f  mov     rcx, rbx
0x18006c742  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18006c747  lea     rcx, [rsp+38h+arg_18]
0x18006c74c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006c751  mov     rbx, [rsp+38h+arg_8]
0x18006c756  mov     rsi, [rsp+38h+arg_10]
0x18006c75b  add     rsp, 30h
0x18006c75f  pop     rdi
0x18006c760  retn
```
