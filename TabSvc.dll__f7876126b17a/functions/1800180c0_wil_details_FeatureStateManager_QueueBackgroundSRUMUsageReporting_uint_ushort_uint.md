# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800180c0`
- end: `0x1800181a3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180014ff0`

## callees

- `0x1800138cc`
- `0x180013d6c`
- `0x180014070`
- `0x1800180c0`
- `0x180018434`
- `0x1800186a0`
- `0x1800186c0`
- `0x1800186e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800180fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800180fc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018158`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018158`

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
  int Source; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = (RTL_SRWLOCK *)(pv + 40);
    v12 = 0;
    Source = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &Source, 0xCu);
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
0x1800180c0  mov     [rsp+arg_8], rbx
0x1800180c5  mov     [rsp+arg_10], rbp
0x1800180ca  push    rsi
0x1800180cb  push    rdi
0x1800180cc  push    r14
0x1800180ce  sub     rsp, 40h
0x1800180d2  mov     esi, r9d
0x1800180d5  movzx   ebp, r8w
0x1800180d9  mov     r14d, edx
0x1800180dc  mov     rdi, rcx
0x1800180df  cmp     byte ptr [rcx], 0
0x1800180e2  jz      loc_180018190
0x1800180e8  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800180ed  test    al, al
0x1800180ef  jnz     loc_180018190
0x1800180f5  lea     rbx, [rdi+28h]
0x1800180f9  mov     rcx, rbx; SRWLock
0x1800180fc  call    cs:__imp_AcquireSRWLockExclusive
0x180018102  mov     [rsp+58h+var_38], rbx
0x180018107  xor     eax, eax
0x180018109  mov     [rsp+58h+var_2A], ax
0x18001810e  mov     [rsp+58h+Source], r14d
0x180018113  mov     [rsp+58h+var_2C], bp
0x180018118  mov     [rsp+58h+var_28], esi
0x18001811c  lea     rcx, [rdi+0E8h]; this
0x180018123  lea     r8d, [rax+0Ch]; SourceSize
0x180018127  lea     rdx, [rsp+58h+Source]; Source
0x18001812c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018131  cmp     byte ptr [rdi+40h], 0
0x180018135  jnz     short loc_180018185
0x180018137  lea     rbx, [rdi+38h]
0x18001813b  cmp     qword ptr [rbx], 0
0x18001813f  jnz     short loc_180018173
0x180018141  lea     rcx, [rsp+58h+arg_0]; this
0x180018146  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001814b  xor     r8d, r8d; pcbe
0x18001814e  mov     rdx, rdi; pv
0x180018151  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180018158  call    cs:__imp_CreateThreadpoolTimer
0x18001815e  mov     rdx, rax
0x180018161  mov     rcx, rbx
0x180018164  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180018169  lea     rcx, [rsp+58h+arg_0]; this
0x18001816e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018173  mov     r8d, 1388h
0x180018179  lea     rdx, [rdi+40h]
0x18001817d  mov     rcx, rbx
0x180018180  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180018185  lea     rcx, [rsp+58h+var_38]
0x18001818a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001818f  nop
0x180018190  mov     rbx, [rsp+58h+arg_8]
0x180018195  mov     rbp, [rsp+58h+arg_10]
0x18001819a  add     rsp, 40h
0x18001819e  pop     r14
0x1800181a0  pop     rdi
0x1800181a1  pop     rsi
0x1800181a2  retn
```
