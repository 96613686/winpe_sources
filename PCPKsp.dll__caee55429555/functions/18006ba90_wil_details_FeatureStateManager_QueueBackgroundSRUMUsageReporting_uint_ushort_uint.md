# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18006ba90`
- end: `0x18006bb80`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `240`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18005cd10`

## callees

- `0x18004d528`
- `0x18005305c`
- `0x180053e18`
- `0x180054024`
- `0x18005437c`
- `0x18005acd4`
- `0x18006ba90`
- `0x18007a454`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006bacc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006bacc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006bb2e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006bb2e`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char *v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = pv + 40;
    v12 = 0;
    v10 = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v10, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x18006ba90  mov     [rsp+arg_8], rbx
0x18006ba95  mov     [rsp+arg_10], rbp
0x18006ba9a  push    rsi
0x18006ba9b  push    rdi
0x18006ba9c  push    r14
0x18006ba9e  sub     rsp, 40h
0x18006baa2  mov     esi, r9d
0x18006baa5  movzx   ebp, r8w
0x18006baa9  mov     r14d, edx
0x18006baac  mov     rdi, rcx
0x18006baaf  cmp     byte ptr [rcx], 0
0x18006bab2  jz      loc_18006BB6C
0x18006bab8  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18006babd  test    al, al
0x18006babf  jnz     loc_18006BB6C
0x18006bac5  lea     rbx, [rdi+28h]
0x18006bac9  mov     rcx, rbx; SRWLock
0x18006bacc  call    cs:__imp_AcquireSRWLockExclusive
0x18006bad3  nop     dword ptr [rax+rax+00h]
0x18006bad8  mov     [rsp+58h+var_38], rbx
0x18006badd  xor     eax, eax
0x18006badf  mov     [rsp+58h+var_2A], ax
0x18006bae4  mov     [rsp+58h+var_30], r14d
0x18006bae9  mov     [rsp+58h+var_2C], bp
0x18006baee  mov     [rsp+58h+var_28], esi
0x18006baf2  lea     rcx, [rdi+0E8h]; this
0x18006baf9  lea     r8d, [rax+0Ch]; unsigned __int64
0x18006bafd  lea     rdx, [rsp+58h+var_30]; void *
0x18006bb02  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18006bb07  cmp     byte ptr [rdi+40h], 0
0x18006bb0b  jnz     short loc_18006BB61
0x18006bb0d  lea     rbx, [rdi+38h]
0x18006bb11  cmp     qword ptr [rbx], 0
0x18006bb15  jnz     short loc_18006BB4F
0x18006bb17  lea     rcx, [rsp+58h+arg_0]; this
0x18006bb1c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006bb21  xor     r8d, r8d; pcbe
0x18006bb24  mov     rdx, rdi; pv
0x18006bb27  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006bb2e  call    cs:__imp_CreateThreadpoolTimer
0x18006bb35  nop     dword ptr [rax+rax+00h]
0x18006bb3a  mov     rdx, rax
0x18006bb3d  mov     rcx, rbx
0x18006bb40  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18006bb45  lea     rcx, [rsp+58h+arg_0]; this
0x18006bb4a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006bb4f  mov     r8d, 1388h
0x18006bb55  lea     rdx, [rdi+40h]
0x18006bb59  mov     rcx, rbx
0x18006bb5c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18006bb61  lea     rcx, [rsp+58h+var_38]
0x18006bb66  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006bb6b  nop
0x18006bb6c  mov     rbx, [rsp+58h+arg_8]
0x18006bb71  mov     rbp, [rsp+58h+arg_10]
0x18006bb76  add     rsp, 40h
0x18006bb7a  pop     r14
0x18006bb7c  pop     rdi
0x18006bb7d  pop     rsi
0x18006bb7e  retn
```
