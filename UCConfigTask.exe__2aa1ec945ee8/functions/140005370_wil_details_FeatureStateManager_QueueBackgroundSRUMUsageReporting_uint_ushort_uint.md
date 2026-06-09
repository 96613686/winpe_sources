# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140005370`
- end: `0x140005453`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140006e30`

## callees

- `0x140002d14`
- `0x140002fd4`
- `0x1400032a8`
- `0x140003954`
- `0x14000533c`
- `0x140005370`
- `0x1400073ac`
- `0x1400074b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400053ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400053ac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140005408`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140005408`

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
0x140005370  mov     [rsp+arg_8], rbx
0x140005375  mov     [rsp+arg_10], rbp
0x14000537a  push    rsi
0x14000537b  push    rdi
0x14000537c  push    r14
0x14000537e  sub     rsp, 40h
0x140005382  mov     esi, r9d
0x140005385  movzx   ebp, r8w
0x140005389  mov     r14d, edx
0x14000538c  mov     rdi, rcx
0x14000538f  cmp     byte ptr [rcx], 0
0x140005392  jz      loc_140005440
0x140005398  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000539d  test    al, al
0x14000539f  jnz     loc_140005440
0x1400053a5  lea     rbx, [rdi+28h]
0x1400053a9  mov     rcx, rbx; SRWLock
0x1400053ac  call    cs:__imp_AcquireSRWLockExclusive
0x1400053b2  mov     [rsp+58h+var_38], rbx
0x1400053b7  xor     eax, eax
0x1400053b9  mov     [rsp+58h+var_2A], ax
0x1400053be  mov     [rsp+58h+var_30], r14d
0x1400053c3  mov     [rsp+58h+var_2C], bp
0x1400053c8  mov     [rsp+58h+var_28], esi
0x1400053cc  lea     rcx, [rdi+0E8h]; this
0x1400053d3  lea     r8d, [rax+0Ch]; unsigned __int64
0x1400053d7  lea     rdx, [rsp+58h+var_30]; void *
0x1400053dc  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400053e1  cmp     byte ptr [rdi+40h], 0
0x1400053e5  jnz     short loc_140005435
0x1400053e7  lea     rbx, [rdi+38h]
0x1400053eb  cmp     qword ptr [rbx], 0
0x1400053ef  jnz     short loc_140005423
0x1400053f1  lea     rcx, [rsp+58h+arg_0]; this
0x1400053f6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400053fb  xor     r8d, r8d; pcbe
0x1400053fe  mov     rdx, rdi; pv
0x140005401  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140005408  call    cs:__imp_CreateThreadpoolTimer
0x14000540e  mov     rdx, rax
0x140005411  mov     rcx, rbx
0x140005414  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140005419  lea     rcx, [rsp+58h+arg_0]; this
0x14000541e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140005423  mov     r8d, 1388h
0x140005429  lea     rdx, [rdi+40h]
0x14000542d  mov     rcx, rbx
0x140005430  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140005435  lea     rcx, [rsp+58h+var_38]
0x14000543a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000543f  nop
0x140005440  mov     rbx, [rsp+58h+arg_8]
0x140005445  mov     rbp, [rsp+58h+arg_10]
0x14000544a  add     rsp, 40h
0x14000544e  pop     r14
0x140005450  pop     rdi
0x140005451  pop     rsi
0x140005452  retn
```
