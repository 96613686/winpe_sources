# Concurrency::task<void>::task<void>(`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,Concurrency::task_options const &)

- ea: `0x180014cc0`
- end: `0x180015013`
- name: `??$?0V_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@2@@Z@@?$task@X@Concurrency@@QEAA@V_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@4@@Z@AEBVtask_options@1@@Z`
- size: `851`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180015488`

## callees

- `0x1800021e4`
- `0x180014cc0`
- `0x180015abc`
- `0x180015e28`
- `0x1800165e8`
- `0x180016d00`
- `0x180019878`
- `0x180019e40`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180014f93`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180014f93`

## pseudocode

```c
_QWORD *__fastcall ____0V_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__2__Z____task_X_Concurrency__QEAA_V_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__4__Z_AEBVtask_options_1__Z(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rsi
  __int64 v9; // r13
  _DWORD *v10; // r12
  volatile signed __int32 *v11; // r14
  volatile signed __int32 *v12; // r14
  __int64 v13; // rcx
  __int64 v14; // rax
  volatile signed __int32 *v15; // r14
  _BYTE *v16; // rax
  char v17; // si
  __int64 i; // rcx
  __int64 v19; // rsi
  _QWORD *v20; // rdx
  __int64 v21; // rax
  __int128 v23; // [rsp+20h] [rbp-60h] BYREF
  __int64 v24; // [rsp+30h] [rbp-50h]
  __int128 v25; // [rsp+38h] [rbp-48h] BYREF
  __int64 v26; // [rsp+48h] [rbp-38h]
  _BYTE v27[24]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v28; // [rsp+70h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+38h]

  *a1 = 0;
  a1[1] = 0;
  v25 = 0;
  v6 = *(_QWORD *)(a3 + 8);
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  *(_QWORD *)&v25 = *(_QWORD *)a3;
  v7 = *(_QWORD *)(a3 + 8);
  *((_QWORD *)&v25 + 1) = v7;
  v26 = *(_QWORD *)(a3 + 16);
  v8 = *(volatile signed __int32 **)(a3 + 24);
  if ( v8 )
  {
    _InterlockedIncrement(v8 + 2);
    v7 = *((_QWORD *)&v25 + 1);
  }
  v9 = (__int64)v8;
  if ( !v8 )
    v9 = 2;
  *(_OWORD *)v27 = 0;
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  *(_OWORD *)v27 = v25;
  *(_QWORD *)&v27[16] = v26;
  v10 = operator new(0x1C8u);
  *(_QWORD *)&v23 = v10;
  *(_OWORD *)v10 = 0;
  v10[2] = 1;
  v10[3] = 1;
  *(_QWORD *)v10 = &std::_Ref_count_obj2<Concurrency::details::_Task_impl<unsigned char>>::`vftable';
  if ( *(_QWORD *)&v27[8] )
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v27[8] + 8LL));
  v23 = *(_OWORD *)v27;
  v24 = *(_QWORD *)&v27[16];
  Concurrency::details::_Task_impl<unsigned char>::_Task_impl<unsigned char>(v10 + 4, v9, &v23);
  v11 = *(volatile signed __int32 **)&v27[8];
  if ( *(_QWORD *)&v27[8] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v27[8] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  *a1 = v10 + 4;
  v12 = (volatile signed __int32 *)a1[1];
  a1[1] = v10;
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( v9 != 2 )
  {
    v13 = *a1;
    v23 = 0;
    v14 = a1[1];
    if ( v14 )
    {
      *(_QWORD *)&v23 = v13;
      *((_QWORD *)&v23 + 1) = v14;
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 12));
    }
    Concurrency::details::_Task_impl_base::_RegisterCancellation(v13, &v23);
  }
  v15 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
  if ( *((_QWORD *)&v25 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  if ( v8 && _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
  if ( *(_BYTE *)(a3 + 48) )
  {
    v16 = (_BYTE *)Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
                     (Concurrency::details::_TaskCreationCallstack *)&v25,
                     (const struct Concurrency::details::_TaskCreationCallstack *)(a3 + 56));
    v17 = 13;
  }
  else
  {
    *(_OWORD *)&v27[8] = 0;
    v28 = 0;
    *(_QWORD *)v27 = retaddr;
    v16 = v27;
    v17 = 14;
  }
  Concurrency::details::_TaskCreationCallstack::operator=(*a1 + 320LL, v16);
  if ( (v17 & 2) != 0 )
  {
    v17 &= ~2u;
    std::vector<void *>::~vector<void *>(&v27[8]);
  }
  if ( (v17 & 1) != 0 )
    std::vector<void *>::~vector<void *>((char *)&v25 + 8);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(i + *a1 + 12) = 0;
  Concurrency::details::_TaskEventLogger::_LogScheduleTask((Concurrency::details::_TaskEventLogger *)(*a1 + 352LL), 0);
  v19 = *a1;
  v20 = operator new(0x20u);
  *v20 = &___7___PPLTaskHandle_EU___InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__U_TaskProcHandle_details_3__details_Concurrency__6B_;
  v20[1] = 0;
  v20[2] = 0;
  v21 = a1[1];
  if ( v21 )
    _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
  v20[1] = *a1;
  v20[2] = a1[1];
  *v20 = &___7___InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__6B_;
  v20[3] = a2;
  Concurrency::details::_Task_impl_base::_ScheduleTask(v19, v20, 0);
  return a1;
}

```

## disassembly

```asm
0x180014cc0  mov     [rsp-38h+arg_8], rbx
0x180014cc5  mov     [rsp-38h+arg_0], rcx
0x180014cca  push    rbp
0x180014ccb  push    rsi
0x180014ccc  push    rdi
0x180014ccd  push    r12
0x180014ccf  push    r13
0x180014cd1  push    r14
0x180014cd3  push    r15
0x180014cd5  mov     rbp, rsp
0x180014cd8  sub     rsp, 80h
0x180014cdf  mov     r15, r8
0x180014ce2  mov     rbx, rdx
0x180014ce5  mov     rdi, rcx
0x180014ce8  xor     r14d, r14d
0x180014ceb  mov     dword ptr [rbp+arg_10], r14d
0x180014cef  mov     [rcx], r14
0x180014cf2  mov     [rcx+8], r14
0x180014cf6  xorps   xmm0, xmm0
0x180014cf9  movdqu  [rbp+var_48], xmm0
0x180014cfe  mov     rax, [r8+8]
0x180014d02  test    rax, rax
0x180014d05  jz      short loc_180014D0B
0x180014d07  lock inc dword ptr [rax+8]
0x180014d0b  mov     rax, [r8]
0x180014d0e  mov     qword ptr [rbp+var_48], rax
0x180014d12  mov     rcx, [r8+8]
0x180014d16  mov     qword ptr [rbp+var_48+8], rcx
0x180014d1a  mov     rax, [r8+10h]
0x180014d1e  mov     [rbp+var_38], rax
0x180014d22  lea     rax, [rbp+var_48]
0x180014d26  mov     [rbp+arg_10], rax
0x180014d2a  mov     rsi, [r8+18h]
0x180014d2e  test    rsi, rsi
0x180014d31  jz      short loc_180014D3B
0x180014d33  lock inc dword ptr [rsi+8]
0x180014d37  mov     rcx, qword ptr [rbp+var_48+8]
0x180014d3b  mov     [rbp+arg_18], rsi
0x180014d3f  mov     r13, rsi
0x180014d42  mov     eax, 2
0x180014d47  test    rsi, rsi
0x180014d4a  cmovz   r13, rax
0x180014d4e  movdqu  [rbp+var_28], xmm0
0x180014d53  test    rcx, rcx
0x180014d56  jz      short loc_180014D5C
0x180014d58  lock inc dword ptr [rcx+8]
0x180014d5c  movups  xmm0, [rbp+var_48]
0x180014d60  movups  [rbp+var_28], xmm0
0x180014d64  movsd   xmm1, [rbp+var_38]
0x180014d69  movsd   [rbp+var_18], xmm1
0x180014d6e  lea     rax, [rbp+var_28]
0x180014d72  mov     qword ptr [rbp+var_60], rax
0x180014d76  mov     ecx, 1C8h; Size
0x180014d7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014d80  mov     r12, rax
0x180014d83  mov     qword ptr [rbp+var_60], rax
0x180014d87  xorps   xmm0, xmm0
0x180014d8a  movups  xmmword ptr [rax], xmm0
0x180014d8d  mov     dword ptr [rax+8], 1
0x180014d94  mov     dword ptr [rax+0Ch], 1
0x180014d9b  lea     rax, ??_7?$_Ref_count_obj2@U?$_Task_impl@E@details@Concurrency@@@std@@6B@; const std::_Ref_count_obj2<Concurrency::details::_Task_impl<uchar>>::`vftable'
0x180014da2  mov     [r12], rax
0x180014da6  mov     rcx, qword ptr [rbp+var_28+8]
0x180014daa  test    rcx, rcx
0x180014dad  jz      short loc_180014DB3
0x180014daf  lock inc dword ptr [rcx+8]
0x180014db3  movups  xmm0, [rbp+var_28]
0x180014db7  movups  [rbp+var_60], xmm0
0x180014dbb  movsd   xmm1, [rbp+var_18]
0x180014dc0  movsd   [rbp+var_50], xmm1
0x180014dc5  lea     r8, [rbp+var_60]
0x180014dc9  mov     rdx, r13
0x180014dcc  lea     rcx, [r12+10h]
0x180014dd1  call    ??0?$_Task_impl@E@details@Concurrency@@QEAA@PEAV_CancellationTokenState@12@Uscheduler_ptr@2@@Z; Concurrency::details::_Task_impl<uchar>::_Task_impl<uchar>(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x180014dd6  nop
0x180014dd7  mov     r14, qword ptr [rbp+var_28+8]
0x180014ddb  test    r14, r14
0x180014dde  jz      short loc_180014E19
0x180014de0  or      eax, 0FFFFFFFFh
0x180014de3  lock xadd [r14+8], eax
0x180014de9  cmp     eax, 1
0x180014dec  jnz     short loc_180014E19
0x180014dee  mov     rax, [r14]
0x180014df1  mov     rcx, r14
0x180014df4  mov     rax, [rax]
0x180014df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dfc  or      eax, 0FFFFFFFFh
0x180014dff  lock xadd [r14+0Ch], eax
0x180014e05  cmp     eax, 1
0x180014e08  jnz     short loc_180014E19
0x180014e0a  mov     rax, [r14]
0x180014e0d  mov     rcx, r14
0x180014e10  mov     rax, [rax+8]
0x180014e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e19  lea     rax, [r12+10h]
0x180014e1e  mov     [rdi], rax
0x180014e21  mov     r14, [rdi+8]
0x180014e25  mov     [rdi+8], r12
0x180014e29  xor     r12d, r12d
0x180014e2c  test    r14, r14
0x180014e2f  jz      short loc_180014E6A
0x180014e31  or      eax, 0FFFFFFFFh
0x180014e34  lock xadd [r14+8], eax
0x180014e3a  cmp     eax, 1
0x180014e3d  jnz     short loc_180014E6A
0x180014e3f  mov     rax, [r14]
0x180014e42  mov     rcx, r14
0x180014e45  mov     rax, [rax]
0x180014e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e4d  or      eax, 0FFFFFFFFh
0x180014e50  lock xadd [r14+0Ch], eax
0x180014e56  cmp     eax, 1
0x180014e59  jnz     short loc_180014E6A
0x180014e5b  mov     rax, [r14]
0x180014e5e  mov     rcx, r14
0x180014e61  mov     rax, [rax+8]
0x180014e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e6a  cmp     r13, 2
0x180014e6e  jz      short loc_180014E9A
0x180014e70  mov     rcx, [rdi]
0x180014e73  xorps   xmm0, xmm0
0x180014e76  movdqu  [rbp+var_60], xmm0
0x180014e7b  mov     rax, [rdi+8]
0x180014e7f  test    rax, rax
0x180014e82  jz      short loc_180014E90
0x180014e84  mov     qword ptr [rbp+var_60], rcx
0x180014e88  mov     qword ptr [rbp+var_60+8], rax
0x180014e8c  lock inc dword ptr [rax+0Ch]
0x180014e90  lea     rdx, [rbp+var_60]
0x180014e94  call    ?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z; Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)
0x180014e99  nop
0x180014e9a  mov     r14, qword ptr [rbp+var_48+8]
0x180014e9e  or      r13d, 0FFFFFFFFh
0x180014ea2  test    r14, r14
0x180014ea5  jz      short loc_180014EE1
0x180014ea7  mov     eax, r13d
0x180014eaa  lock xadd [r14+8], eax
0x180014eb0  add     eax, r13d
0x180014eb3  jnz     short loc_180014EE1
0x180014eb5  mov     rax, [r14]
0x180014eb8  mov     rcx, r14
0x180014ebb  mov     rax, [rax]
0x180014ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ec3  mov     eax, r13d
0x180014ec6  lock xadd [r14+0Ch], eax
0x180014ecc  add     eax, r13d
0x180014ecf  jnz     short loc_180014EE1
0x180014ed1  mov     rax, [r14]
0x180014ed4  mov     rcx, r14
0x180014ed7  mov     rax, [rax+8]
0x180014edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ee0  nop
0x180014ee1  test    rsi, rsi
0x180014ee4  jz      short loc_180014F03
0x180014ee6  mov     eax, r13d
0x180014ee9  lock xadd [rsi+8], eax
0x180014eee  add     eax, r13d
0x180014ef1  jnz     short loc_180014F03
0x180014ef3  mov     rax, [rsi]
0x180014ef6  mov     rcx, rsi
0x180014ef9  mov     rax, [rax+8]
0x180014efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f02  nop
0x180014f03  cmp     [r15+30h], r12b
0x180014f07  jz      short loc_180014F1E
0x180014f09  lea     rdx, [r15+38h]; struct Concurrency::details::_TaskCreationCallstack *
0x180014f0d  lea     rcx, [rbp+var_48]; this
0x180014f11  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x180014f16  nop
0x180014f17  mov     esi, 0Dh
0x180014f1c  jmp     short loc_180014F3B
0x180014f1e  mov     rax, [rbp+38h]
0x180014f22  xorps   xmm0, xmm0
0x180014f25  movdqu  [rbp+var_28+8], xmm0
0x180014f2a  mov     [rbp+var_10], r12
0x180014f2e  mov     qword ptr [rbp+var_28], rax
0x180014f32  lea     rax, [rbp+var_28]
0x180014f36  mov     esi, 0Eh
0x180014f3b  mov     dword ptr [rbp+arg_10], esi
0x180014f3e  mov     rcx, [rdi]
0x180014f41  add     rcx, 140h
0x180014f48  mov     rdx, rax
0x180014f4b  call    ??4_TaskCreationCallstack@details@Concurrency@@QEAAAEAV012@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::operator=(Concurrency::details::_TaskCreationCallstack const &)
0x180014f50  nop
0x180014f51  test    sil, 2
0x180014f55  jz      short loc_180014F64
0x180014f57  and     esi, 0FFFFFFFDh
0x180014f5a  lea     rcx, [rbp+var_28+8]
0x180014f5e  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x180014f63  nop
0x180014f64  test    sil, 1
0x180014f68  jz      short loc_180014F73
0x180014f6a  lea     rcx, [rbp+var_48+8]
0x180014f6e  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x180014f73  mov     rcx, r12
0x180014f76  mov     rax, [rdi]
0x180014f79  mov     [rcx+rax+0Ch], r12b
0x180014f7e  inc     rcx
0x180014f81  cmp     rcx, 2
0x180014f85  jnz     short loc_180014F76
0x180014f87  mov     rcx, [rdi]
0x180014f8a  add     rcx, 160h
0x180014f91  xor     edx, edx
0x180014f93  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x180014f99  mov     rsi, [rdi]
0x180014f9c  mov     ecx, 20h ; ' '; Size
0x180014fa1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014fa6  mov     rdx, rax
0x180014fa9  mov     [rbp+arg_10], rax
0x180014fad  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180014fb4  mov     [rdx], rax
0x180014fb7  mov     [rdx+8], r12
0x180014fbb  mov     [rdx+10h], r12
0x180014fbf  mov     rax, [rdi+8]
0x180014fc3  test    rax, rax
0x180014fc6  jz      short loc_180014FCC
0x180014fc8  lock inc dword ptr [rax+8]
0x180014fcc  mov     rax, [rdi]
0x180014fcf  mov     [rdx+8], rax
0x180014fd3  mov     rax, [rdi+8]
0x180014fd7  mov     [rdx+10h], rax
0x180014fdb  lea     rax, ??_7?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@6B@; const Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x180014fe2  mov     [rdx], rax
0x180014fe5  mov     [rdx+18h], rbx
0x180014fe9  xor     r8d, r8d
0x180014fec  mov     rcx, rsi
0x180014fef  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x180014ff4  nop
0x180014ff5  mov     rax, rdi
0x180014ff8  mov     rbx, [rsp+80h+arg_8]
0x180015000  add     rsp, 80h
0x180015007  pop     r15
0x180015009  pop     r14
0x18001500b  pop     r13
0x18001500d  pop     r12
0x18001500f  pop     rdi
0x180015010  pop     rsi
0x180015011  pop     rbp
0x180015012  retn
```
