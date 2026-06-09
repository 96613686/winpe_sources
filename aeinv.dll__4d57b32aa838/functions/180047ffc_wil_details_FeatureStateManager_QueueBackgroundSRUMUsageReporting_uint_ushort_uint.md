# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180047ffc`
- end: `0x1800480e9`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `237`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180113ee0`

## callees

- `0x180047ffc`
- `0x18004826c`
- `0x18004828c`
- `0x18004869c`
- `0x1800487ac`
- `0x1800487d0`
- `0x1800488f8`
- `0x18005c914`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18004809e`
- `KERNEL32!CreateThreadpoolTimer` at `0x18004809e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180048042`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180048042`

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
0x180047ffc  push    rsi
0x180047ffe  push    rdi
0x180047fff  push    r14
0x180048001  sub     rsp, 40h
0x180048005  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFEh
0x18004800e  mov     [rsp+58h+arg_8], rbx
0x180048013  mov     [rsp+58h+arg_10], rbp
0x180048018  mov     esi, r9d
0x18004801b  movzx   ebp, r8w
0x18004801f  mov     r14d, edx
0x180048022  mov     rdi, rcx
0x180048025  cmp     byte ptr [rcx], 0
0x180048028  jz      loc_1800480D6
0x18004802e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180048033  test    al, al
0x180048035  jnz     loc_1800480D6
0x18004803b  lea     rbx, [rdi+28h]
0x18004803f  mov     rcx, rbx; SRWLock
0x180048042  call    cs:__imp_AcquireSRWLockExclusive
0x180048048  mov     [rsp+58h+var_38], rbx
0x18004804d  xor     eax, eax
0x18004804f  mov     [rsp+58h+var_22], ax
0x180048054  mov     [rsp+58h+var_28], r14d
0x180048059  mov     [rsp+58h+var_24], bp
0x18004805e  mov     [rsp+58h+var_20], esi
0x180048062  lea     rcx, [rdi+0E8h]; this
0x180048069  lea     r8d, [rax+0Ch]; unsigned __int64
0x18004806d  lea     rdx, [rsp+58h+var_28]; void *
0x180048072  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180048077  cmp     byte ptr [rdi+40h], 0
0x18004807b  jnz     short loc_1800480CB
0x18004807d  lea     rbx, [rdi+38h]
0x180048081  cmp     qword ptr [rbx], 0
0x180048085  jnz     short loc_1800480B9
0x180048087  lea     rcx, [rsp+58h+arg_0]; this
0x18004808c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180048091  xor     r8d, r8d; pcbe
0x180048094  mov     rdx, rdi; pv
0x180048097  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004809e  call    cs:__imp_CreateThreadpoolTimer
0x1800480a4  mov     rdx, rax
0x1800480a7  mov     rcx, rbx
0x1800480aa  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800480af  lea     rcx, [rsp+58h+arg_0]; this
0x1800480b4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800480b9  mov     r8d, 1388h
0x1800480bf  lea     rdx, [rdi+40h]
0x1800480c3  mov     rcx, rbx
0x1800480c6  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800480cb  lea     rcx, [rsp+58h+var_38]
0x1800480d0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800480d5  nop
0x1800480d6  mov     rbx, [rsp+58h+arg_8]
0x1800480db  mov     rbp, [rsp+58h+arg_10]
0x1800480e0  add     rsp, 40h
0x1800480e4  pop     r14
0x1800480e6  pop     rdi
0x1800480e7  pop     rsi
0x1800480e8  retn
```
