# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800257a0`
- end: `0x180025883`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004d650`

## callees

- `0x18000f3f0`
- `0x1800257a0`
- `0x1800259f0`
- `0x180025a10`
- `0x180025a54`
- `0x180025bf4`
- `0x180025c48`
- `0x18004db20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800257dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800257dc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025838`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025838`

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
0x1800257a0  mov     [rsp+arg_8], rbx
0x1800257a5  mov     [rsp+arg_10], rbp
0x1800257aa  push    rsi
0x1800257ab  push    rdi
0x1800257ac  push    r14
0x1800257ae  sub     rsp, 40h
0x1800257b2  mov     esi, r9d
0x1800257b5  movzx   ebp, r8w
0x1800257b9  mov     r14d, edx
0x1800257bc  mov     rdi, rcx
0x1800257bf  cmp     byte ptr [rcx], 0
0x1800257c2  jz      loc_180025870
0x1800257c8  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800257cd  test    al, al
0x1800257cf  jnz     loc_180025870
0x1800257d5  lea     rbx, [rdi+28h]
0x1800257d9  mov     rcx, rbx; SRWLock
0x1800257dc  call    cs:__imp_AcquireSRWLockExclusive
0x1800257e2  mov     [rsp+58h+var_38], rbx
0x1800257e7  xor     eax, eax
0x1800257e9  mov     [rsp+58h+var_2A], ax
0x1800257ee  mov     [rsp+58h+var_30], r14d
0x1800257f3  mov     [rsp+58h+var_2C], bp
0x1800257f8  mov     [rsp+58h+var_28], esi
0x1800257fc  lea     rcx, [rdi+0E8h]; this
0x180025803  lea     r8d, [rax+0Ch]; unsigned __int64
0x180025807  lea     rdx, [rsp+58h+var_30]; void *
0x18002580c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180025811  cmp     byte ptr [rdi+40h], 0
0x180025815  jnz     short loc_180025865
0x180025817  lea     rbx, [rdi+38h]
0x18002581b  cmp     qword ptr [rbx], 0
0x18002581f  jnz     short loc_180025853
0x180025821  lea     rcx, [rsp+58h+arg_0]; this
0x180025826  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002582b  xor     r8d, r8d; pcbe
0x18002582e  mov     rdx, rdi; pv
0x180025831  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180025838  call    cs:__imp_CreateThreadpoolTimer
0x18002583e  mov     rdx, rax
0x180025841  mov     rcx, rbx
0x180025844  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180025849  lea     rcx, [rsp+58h+arg_0]; this
0x18002584e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180025853  mov     r8d, 1388h
0x180025859  lea     rdx, [rdi+40h]
0x18002585d  mov     rcx, rbx
0x180025860  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180025865  lea     rcx, [rsp+58h+var_38]
0x18002586a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002586f  nop
0x180025870  mov     rbx, [rsp+58h+arg_8]
0x180025875  mov     rbp, [rsp+58h+arg_10]
0x18002587a  add     rsp, 40h
0x18002587e  pop     r14
0x180025880  pop     rdi
0x180025881  pop     rsi
0x180025882  retn
```
