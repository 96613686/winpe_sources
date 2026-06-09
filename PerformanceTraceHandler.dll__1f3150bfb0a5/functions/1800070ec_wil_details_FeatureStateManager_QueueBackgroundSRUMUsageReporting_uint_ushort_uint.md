# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800070ec`
- end: `0x1800071cf`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008f30`

## callees

- `0x1800045b8`
- `0x18000490c`
- `0x180004c88`
- `0x180005334`
- `0x1800070b8`
- `0x1800070ec`
- `0x180009944`
- `0x180009a4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007128`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007128`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007184`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007184`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = (RTL_SRWLOCK *)(pv + 40);
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
0x1800070ec  mov     [rsp+arg_8], rbx
0x1800070f1  mov     [rsp+arg_10], rbp
0x1800070f6  push    rsi
0x1800070f7  push    rdi
0x1800070f8  push    r14
0x1800070fa  sub     rsp, 40h
0x1800070fe  mov     esi, r9d
0x180007101  movzx   ebp, r8w
0x180007105  mov     r14d, edx
0x180007108  mov     rdi, rcx
0x18000710b  cmp     byte ptr [rcx], 0
0x18000710e  jz      loc_1800071BC
0x180007114  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180007119  test    al, al
0x18000711b  jnz     loc_1800071BC
0x180007121  lea     rbx, [rdi+28h]
0x180007125  mov     rcx, rbx; SRWLock
0x180007128  call    cs:__imp_AcquireSRWLockExclusive
0x18000712e  mov     [rsp+58h+var_38], rbx
0x180007133  xor     eax, eax
0x180007135  mov     [rsp+58h+var_2A], ax
0x18000713a  mov     [rsp+58h+var_30], r14d
0x18000713f  mov     [rsp+58h+var_2C], bp
0x180007144  mov     [rsp+58h+var_28], esi
0x180007148  lea     rcx, [rdi+0E8h]; this
0x18000714f  lea     r8d, [rax+0Ch]; unsigned __int64
0x180007153  lea     rdx, [rsp+58h+var_30]; void *
0x180007158  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000715d  cmp     byte ptr [rdi+40h], 0
0x180007161  jnz     short loc_1800071B1
0x180007163  lea     rbx, [rdi+38h]
0x180007167  cmp     qword ptr [rbx], 0
0x18000716b  jnz     short loc_18000719F
0x18000716d  lea     rcx, [rsp+58h+arg_0]; this
0x180007172  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007177  xor     r8d, r8d; pcbe
0x18000717a  mov     rdx, rdi; pv
0x18000717d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007184  call    cs:__imp_CreateThreadpoolTimer
0x18000718a  mov     rdx, rax
0x18000718d  mov     rcx, rbx
0x180007190  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180007195  lea     rcx, [rsp+58h+arg_0]; this
0x18000719a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000719f  mov     r8d, 1388h
0x1800071a5  lea     rdx, [rdi+40h]
0x1800071a9  mov     rcx, rbx
0x1800071ac  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800071b1  lea     rcx, [rsp+58h+var_38]
0x1800071b6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800071bb  nop
0x1800071bc  mov     rbx, [rsp+58h+arg_8]
0x1800071c1  mov     rbp, [rsp+58h+arg_10]
0x1800071c6  add     rsp, 40h
0x1800071ca  pop     r14
0x1800071cc  pop     rdi
0x1800071cd  pop     rsi
0x1800071ce  retn
```
