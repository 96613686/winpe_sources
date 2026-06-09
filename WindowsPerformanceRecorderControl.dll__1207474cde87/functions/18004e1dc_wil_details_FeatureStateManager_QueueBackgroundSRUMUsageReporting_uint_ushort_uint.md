# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18004e1dc`
- end: `0x18004e2c9`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `237`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180055da0`

## callees

- `0x180035e98`
- `0x1800421d0`
- `0x18004e1dc`
- `0x18004e3a4`
- `0x18004e3c4`
- `0x18004e408`
- `0x18004e428`
- `0x180056354`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004e222`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004e222`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004e27e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004e27e`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+30h] [rbp-28h] BYREF
  __int16 v11; // [rsp+34h] [rbp-24h]
  __int16 v12; // [rsp+36h] [rbp-22h]
  int v13; // [rsp+38h] [rbp-20h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  v9[1] = -2;
  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9[0] = pv + 40;
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
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v9);
  }
}

```

## disassembly

```asm
0x18004e1dc  push    rsi
0x18004e1de  push    rdi
0x18004e1df  push    r14
0x18004e1e1  sub     rsp, 40h
0x18004e1e5  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFEh
0x18004e1ee  mov     [rsp+58h+arg_8], rbx
0x18004e1f3  mov     [rsp+58h+arg_10], rbp
0x18004e1f8  mov     esi, r9d
0x18004e1fb  movzx   ebp, r8w
0x18004e1ff  mov     r14d, edx
0x18004e202  mov     rdi, rcx
0x18004e205  cmp     byte ptr [rcx], 0
0x18004e208  jz      loc_18004E2B6
0x18004e20e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004e213  test    al, al
0x18004e215  jnz     loc_18004E2B6
0x18004e21b  lea     rbx, [rdi+28h]
0x18004e21f  mov     rcx, rbx; SRWLock
0x18004e222  call    cs:__imp_AcquireSRWLockExclusive
0x18004e228  mov     [rsp+58h+var_38], rbx
0x18004e22d  xor     eax, eax
0x18004e22f  mov     [rsp+58h+var_22], ax
0x18004e234  mov     [rsp+58h+var_28], r14d
0x18004e239  mov     [rsp+58h+var_24], bp
0x18004e23e  mov     [rsp+58h+var_20], esi
0x18004e242  lea     rcx, [rdi+0E8h]; this
0x18004e249  lea     r8d, [rax+0Ch]; unsigned __int64
0x18004e24d  lea     rdx, [rsp+58h+var_28]; void *
0x18004e252  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18004e257  cmp     byte ptr [rdi+40h], 0
0x18004e25b  jnz     short loc_18004E2AB
0x18004e25d  lea     rbx, [rdi+38h]
0x18004e261  cmp     qword ptr [rbx], 0
0x18004e265  jnz     short loc_18004E299
0x18004e267  lea     rcx, [rsp+58h+arg_0]; this
0x18004e26c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004e271  xor     r8d, r8d; pcbe
0x18004e274  mov     rdx, rdi; pv
0x18004e277  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004e27e  call    cs:__imp_CreateThreadpoolTimer
0x18004e284  mov     rdx, rax
0x18004e287  mov     rcx, rbx
0x18004e28a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004e28f  lea     rcx, [rsp+58h+arg_0]; this
0x18004e294  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004e299  mov     r8d, 1388h
0x18004e29f  lea     rdx, [rdi+40h]
0x18004e2a3  mov     rcx, rbx
0x18004e2a6  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18004e2ab  lea     rcx, [rsp+58h+var_38]
0x18004e2b0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004e2b5  nop
0x18004e2b6  mov     rbx, [rsp+58h+arg_8]
0x18004e2bb  mov     rbp, [rsp+58h+arg_10]
0x18004e2c0  add     rsp, 40h
0x18004e2c4  pop     r14
0x18004e2c6  pop     rdi
0x18004e2c7  pop     rsi
0x18004e2c8  retn
```
