# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000931c`
- end: `0x1800093ff`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000a7f0`

## callees

- `0x180004d14`
- `0x180005010`
- `0x18000665c`
- `0x180007d14`
- `0x1800083c0`
- `0x18000931c`
- `0x18000acb0`
- `0x18000adb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009358`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009358`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800093b4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800093b4`

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
0x18000931c  mov     [rsp+arg_8], rbx
0x180009321  mov     [rsp+arg_10], rbp
0x180009326  push    rsi
0x180009327  push    rdi
0x180009328  push    r14
0x18000932a  sub     rsp, 40h
0x18000932e  mov     esi, r9d
0x180009331  movzx   ebp, r8w
0x180009335  mov     r14d, edx
0x180009338  mov     rdi, rcx
0x18000933b  cmp     byte ptr [rcx], 0
0x18000933e  jz      loc_1800093EC
0x180009344  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180009349  test    al, al
0x18000934b  jnz     loc_1800093EC
0x180009351  lea     rbx, [rdi+28h]
0x180009355  mov     rcx, rbx; SRWLock
0x180009358  call    cs:__imp_AcquireSRWLockExclusive
0x18000935e  mov     [rsp+58h+var_38], rbx
0x180009363  xor     eax, eax
0x180009365  mov     [rsp+58h+var_2A], ax
0x18000936a  mov     [rsp+58h+var_30], r14d
0x18000936f  mov     [rsp+58h+var_2C], bp
0x180009374  mov     [rsp+58h+var_28], esi
0x180009378  lea     rcx, [rdi+0E8h]; this
0x18000937f  lea     r8d, [rax+0Ch]; unsigned __int64
0x180009383  lea     rdx, [rsp+58h+var_30]; void *
0x180009388  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000938d  cmp     byte ptr [rdi+40h], 0
0x180009391  jnz     short loc_1800093E1
0x180009393  lea     rbx, [rdi+38h]
0x180009397  cmp     qword ptr [rbx], 0
0x18000939b  jnz     short loc_1800093CF
0x18000939d  lea     rcx, [rsp+58h+arg_0]; this
0x1800093a2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800093a7  xor     r8d, r8d; pcbe
0x1800093aa  mov     rdx, rdi; pv
0x1800093ad  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800093b4  call    cs:__imp_CreateThreadpoolTimer
0x1800093ba  mov     rdx, rax
0x1800093bd  mov     rcx, rbx
0x1800093c0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800093c5  lea     rcx, [rsp+58h+arg_0]; this
0x1800093ca  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800093cf  mov     r8d, 1388h
0x1800093d5  lea     rdx, [rdi+40h]
0x1800093d9  mov     rcx, rbx
0x1800093dc  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800093e1  lea     rcx, [rsp+58h+var_38]
0x1800093e6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800093eb  nop
0x1800093ec  mov     rbx, [rsp+58h+arg_8]
0x1800093f1  mov     rbp, [rsp+58h+arg_10]
0x1800093f6  add     rsp, 40h
0x1800093fa  pop     r14
0x1800093fc  pop     rdi
0x1800093fd  pop     rsi
0x1800093fe  retn
```
