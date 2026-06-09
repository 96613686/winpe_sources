# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180028630`
- end: `0x18002871e`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002a160`

## callees

- `0x1800050f0`
- `0x18001009c`
- `0x1800107f0`
- `0x18001430c`
- `0x180026f90`
- `0x180027640`
- `0x180028630`
- `0x18002a55c`
- `0x18002a6b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028673`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028673`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800286cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800286cf`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  RTL_SRWLOCK *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = (RTL_SRWLOCK *)(pv + 40);
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v11, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x180028630  push    rbx
0x180028632  push    rbp
0x180028633  push    rsi
0x180028634  push    rdi
0x180028635  push    r14
0x180028637  sub     rsp, 50h
0x18002863b  mov     rax, cs:__security_cookie
0x180028642  xor     rax, rsp
0x180028645  mov     [rsp+78h+var_38], rax
0x18002864a  cmp     byte ptr [rcx], 0
0x18002864d  mov     r14d, r9d
0x180028650  movzx   ebp, r8w
0x180028654  mov     esi, edx
0x180028656  mov     rdi, rcx
0x180028659  jz      loc_180028706
0x18002865f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180028664  test    al, al
0x180028666  jnz     loc_180028706
0x18002866c  lea     rbx, [rdi+28h]
0x180028670  mov     rcx, rbx; SRWLock
0x180028673  call    cs:__imp_AcquireSRWLockExclusive
0x180028679  xor     eax, eax
0x18002867b  mov     [rsp+78h+var_50], rbx
0x180028680  lea     rcx, [rdi+0E8h]; this
0x180028687  mov     [rsp+78h+var_42], ax
0x18002868c  lea     rdx, [rsp+78h+var_48]; void *
0x180028691  mov     [rsp+78h+var_48], esi
0x180028695  mov     [rsp+78h+var_44], bp
0x18002869a  lea     r8d, [rax+0Ch]; unsigned __int64
0x18002869e  mov     [rsp+78h+var_40], r14d
0x1800286a3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800286a8  cmp     byte ptr [rdi+40h], 0
0x1800286ac  jnz     short loc_1800286FC
0x1800286ae  lea     rbx, [rdi+38h]
0x1800286b2  cmp     qword ptr [rbx], 0
0x1800286b6  jnz     short loc_1800286EA
0x1800286b8  lea     rcx, [rsp+78h+var_58]; this
0x1800286bd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800286c2  xor     r8d, r8d; pcbe
0x1800286c5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800286cc  mov     rdx, rdi; pv
0x1800286cf  call    cs:__imp_CreateThreadpoolTimer
0x1800286d5  mov     rdx, rax
0x1800286d8  mov     rcx, rbx
0x1800286db  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800286e0  lea     rcx, [rsp+78h+var_58]; this
0x1800286e5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800286ea  mov     r8d, 1388h
0x1800286f0  lea     rdx, [rdi+40h]
0x1800286f4  mov     rcx, rbx
0x1800286f7  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800286fc  lea     rcx, [rsp+78h+var_50]
0x180028701  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180028706  mov     rcx, [rsp+78h+var_38]
0x18002870b  xor     rcx, rsp; StackCookie
0x18002870e  call    __security_check_cookie
0x180028713  add     rsp, 50h
0x180028717  pop     r14
0x180028719  pop     rdi
0x18002871a  pop     rsi
0x18002871b  pop     rbp
0x18002871c  pop     rbx
0x18002871d  retn
```
