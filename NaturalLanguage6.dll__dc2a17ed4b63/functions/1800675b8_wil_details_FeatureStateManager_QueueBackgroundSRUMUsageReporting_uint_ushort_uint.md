# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800675b8`
- end: `0x1800676ab`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `243`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180068e60`

## callees

- `0x1800413c0`
- `0x1800418a0`
- `0x18004b084`
- `0x180065988`
- `0x180066510`
- `0x1800675b8`
- `0x18006924c`
- `0x1800692a8`
- `0x1800693b8`
- `0x18009e300`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006765b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006765b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        struct _TP_TIMER **pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v10[8]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v11; // [rsp+30h] [rbp-48h]
  int v12; // [rsp+38h] [rbp-40h] BYREF
  __int16 v13; // [rsp+3Ch] [rbp-3Ch]
  __int16 v14; // [rsp+3Eh] [rbp-3Ah]
  int v15; // [rsp+40h] [rbp-38h]

  v11 = -2;
  if ( *(_BYTE *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    wil::srwlock::lock_exclusive(pv + 5, v10);
    v14 = 0;
    v12 = a2;
    v13 = a3;
    v15 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 29), &v12, 0xCu);
    if ( !*((_BYTE *)pv + 64) )
    {
      if ( !pv[7] )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 7,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(pv + 7, (_BYTE *)pv + 64, 5000);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>();
  }
}

```

## disassembly

```asm
0x1800675b8  push    rbx
0x1800675ba  push    rbp
0x1800675bb  push    rsi
0x1800675bc  push    rdi
0x1800675bd  sub     rsp, 58h
0x1800675c1  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800675ca  mov     rax, cs:__security_cookie
0x1800675d1  xor     rax, rsp
0x1800675d4  mov     [rsp+78h+var_30], rax
0x1800675d9  mov     ebp, r9d
0x1800675dc  movzx   esi, r8w
0x1800675e0  mov     ebx, edx
0x1800675e2  mov     rdi, rcx
0x1800675e5  cmp     byte ptr [rcx], 0
0x1800675e8  jz      loc_180067695
0x1800675ee  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800675f3  test    al, al
0x1800675f5  jnz     loc_180067695
0x1800675fb  lea     rcx, [rdi+28h]
0x1800675ff  lea     rdx, [rsp+78h+var_50]
0x180067604  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x180067609  nop
0x18006760a  xor     eax, eax
0x18006760c  mov     [rsp+78h+var_3A], ax
0x180067611  mov     [rsp+78h+var_40], ebx
0x180067615  mov     [rsp+78h+var_3C], si
0x18006761a  mov     [rsp+78h+var_38], ebp
0x18006761e  lea     rcx, [rdi+0E8h]; this
0x180067625  lea     r8d, [rax+0Ch]; unsigned __int64
0x180067629  lea     rdx, [rsp+78h+var_40]; void *
0x18006762e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180067633  cmp     byte ptr [rdi+40h], 0
0x180067637  jnz     short loc_18006768A
0x180067639  lea     rbx, [rdi+38h]
0x18006763d  cmp     qword ptr [rbx], 0
0x180067641  jnz     short loc_180067677
0x180067643  lea     rcx, [rsp+78h+var_58]; this
0x180067648  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006764d  nop
0x18006764e  xor     r8d, r8d; pcbe
0x180067651  mov     rdx, rdi; pv
0x180067654  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006765b  call    cs:__imp_CreateThreadpoolTimer
0x180067661  mov     rdx, rax
0x180067664  mov     rcx, rbx
0x180067667  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18006766c  nop
0x18006766d  lea     rcx, [rsp+78h+var_58]; this
0x180067672  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180067677  mov     r8d, 1388h
0x18006767d  lea     rdx, [rdi+40h]
0x180067681  mov     rcx, rbx
0x180067684  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180067689  nop
0x18006768a  lea     rcx, [rsp+78h+var_50]
0x18006768f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180067694  nop
0x180067695  mov     rcx, [rsp+78h+var_30]
0x18006769a  xor     rcx, rsp; StackCookie
0x18006769d  call    __security_check_cookie
0x1800676a2  add     rsp, 58h
0x1800676a6  pop     rdi
0x1800676a7  pop     rsi
0x1800676a8  pop     rbp
0x1800676a9  pop     rbx
0x1800676aa  retn
```
