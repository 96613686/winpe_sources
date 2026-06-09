# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180007718`
- end: `0x1800077fb`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009850`

## callees

- `0x180004af8`
- `0x180004e64`
- `0x180005240`
- `0x180005974`
- `0x1800076e4`
- `0x180007718`
- `0x180009f20`
- `0x18000a028`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007754`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007754`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800077b0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800077b0`

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
    wil::details_abi::heap_buffer::push_back((void **)pv + 29, &v10, 0xCu);
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
0x180007718  mov     [rsp+arg_8], rbx
0x18000771d  mov     [rsp+arg_10], rbp
0x180007722  push    rsi
0x180007723  push    rdi
0x180007724  push    r14
0x180007726  sub     rsp, 40h
0x18000772a  mov     esi, r9d
0x18000772d  movzx   ebp, r8w
0x180007731  mov     r14d, edx
0x180007734  mov     rdi, rcx
0x180007737  cmp     byte ptr [rcx], 0
0x18000773a  jz      loc_1800077E8
0x180007740  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180007745  test    al, al
0x180007747  jnz     loc_1800077E8
0x18000774d  lea     rbx, [rdi+28h]
0x180007751  mov     rcx, rbx; SRWLock
0x180007754  call    cs:__imp_AcquireSRWLockExclusive
0x18000775a  mov     [rsp+58h+var_38], rbx
0x18000775f  xor     eax, eax
0x180007761  mov     [rsp+58h+var_2A], ax
0x180007766  mov     [rsp+58h+var_30], r14d
0x18000776b  mov     [rsp+58h+var_2C], bp
0x180007770  mov     [rsp+58h+var_28], esi
0x180007774  lea     rcx, [rdi+0E8h]; this
0x18000777b  lea     r8d, [rax+0Ch]; unsigned __int64
0x18000777f  lea     rdx, [rsp+58h+var_30]; void *
0x180007784  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180007789  cmp     byte ptr [rdi+40h], 0
0x18000778d  jnz     short loc_1800077DD
0x18000778f  lea     rbx, [rdi+38h]
0x180007793  cmp     qword ptr [rbx], 0
0x180007797  jnz     short loc_1800077CB
0x180007799  lea     rcx, [rsp+58h+arg_0]; this
0x18000779e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800077a3  xor     r8d, r8d; pcbe
0x1800077a6  mov     rdx, rdi; pv
0x1800077a9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800077b0  call    cs:__imp_CreateThreadpoolTimer
0x1800077b6  mov     rdx, rax
0x1800077b9  mov     rcx, rbx
0x1800077bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800077c1  lea     rcx, [rsp+58h+arg_0]; this
0x1800077c6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800077cb  mov     r8d, 1388h
0x1800077d1  lea     rdx, [rdi+40h]
0x1800077d5  mov     rcx, rbx
0x1800077d8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800077dd  lea     rcx, [rsp+58h+var_38]
0x1800077e2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800077e7  nop
0x1800077e8  mov     rbx, [rsp+58h+arg_8]
0x1800077ed  mov     rbp, [rsp+58h+arg_10]
0x1800077f2  add     rsp, 40h
0x1800077f6  pop     r14
0x1800077f8  pop     rdi
0x1800077f9  pop     rsi
0x1800077fa  retn
```
