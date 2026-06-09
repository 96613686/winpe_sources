# std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)

- ea: `0x18001510c`
- end: `0x18001527b`
- name: `??$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@1@@Z`
- size: `367`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800175c0`

## callees

- `0x18001501c`
- `0x18001510c`
- `0x180015488`
- `0x18001a6a8`
- `0x18002d010`

## import_xrefs

- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x180015185`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x180015185`

## pseudocode

```c
__int64 __fastcall ____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__1__Z(
        __int64 a1,
        _OWORD *a2)
{
  __int64 *v3; // rsi
  __int64 *ambient_scheduler; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 *DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__4__Z_Vtask_options_0__Z; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  volatile signed __int32 *v11; // rbx
  volatile signed __int32 *v12; // rbx
  _BYTE v14[8]; // [rsp+20h] [rbp-39h] BYREF
  volatile signed __int32 *v15; // [rsp+28h] [rbp-31h]
  _QWORD v16[4]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v17[24]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v18; // [rsp+68h] [rbp+Fh]
  __int128 v19; // [rsp+70h] [rbp+17h]
  __int64 v20; // [rsp+80h] [rbp+27h]
  __int16 v21; // [rsp+88h] [rbp+2Fh]

  ____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std___0A_____Packaged_state___A6AXXZ_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__1__Z(
    a1,
    a2);
  *(_QWORD *)a1 = &std::_Task_async_state<void>::`vftable';
  v3 = (__int64 *)(a1 + 272);
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  ambient_scheduler = (__int64 *)Concurrency::get_ambient_scheduler();
  v5 = ambient_scheduler[1];
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  v6 = *ambient_scheduler;
  v7 = ambient_scheduler[1];
  v16[0] = v6;
  v16[1] = v7;
  v16[2] = v6;
  v16[3] = 0;
  Concurrency::task_continuation_context::task_continuation_context((Concurrency::task_continuation_context *)v17);
  v19 = 0;
  v20 = 0;
  v18 = 0;
  v17[16] = 0;
  v21 = 0;
  DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__4__Z_Vtask_options_0__Z = (__int64 *)___create_task_V_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z__Concurrency__YA_AV__task_X_0_V_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__4__Z_Vtask_options_0__Z(v14, a1, v16);
  if ( v3 != DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__4__Z_Vtask_options_0__Z )
  {
    v9 = *DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__4__Z_Vtask_options_0__Z;
    v10 = DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__4__Z_Vtask_options_0__Z[1];
    *DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__4__Z_Vtask_options_0__Z = 0;
    DialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__4__Z_Vtask_options_0__Z[1] = 0;
    *v3 = v9;
    v11 = *(volatile signed __int32 **)(a1 + 280);
    *(_QWORD *)(a1 + 280) = v10;
    if ( v11 )
    {
      if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
  v12 = v15;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  *(_BYTE *)(a1 + 194) = 1;
  return a1;
}

```

## disassembly

```asm
0x18001510c  mov     [rsp-8+arg_0], rcx
0x180015111  push    rbp
0x180015112  push    rbx
0x180015113  push    rsi
0x180015114  push    rdi
0x180015115  push    r14
0x180015117  lea     rbp, [rsp-37h]
0x18001511c  sub     rsp, 90h
0x180015123  mov     rdi, rcx
0x180015126  call    ??$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@$0A@@?$_Packaged_state@$$A6AXXZ@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@1@@Z; std::_Packaged_state<void (void)>::_Packaged_state<void (void)>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)
0x18001512b  nop
0x18001512c  lea     rax, ??_7?$_Task_async_state@X@std@@6B@; const std::_Task_async_state<void>::`vftable'
0x180015133  mov     [rdi], rax
0x180015136  lea     rsi, [rdi+110h]
0x18001513d  mov     qword ptr [rsi], 0
0x180015144  mov     qword ptr [rsi+8], 0
0x18001514c  lea     rax, [rbp+57h+var_80]
0x180015150  mov     [rbp+57h+arg_10], rax
0x180015154  call    ?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ; Concurrency::get_ambient_scheduler(void)
0x180015159  mov     rcx, [rax+8]
0x18001515d  test    rcx, rcx
0x180015160  jz      short loc_180015166
0x180015162  lock inc dword ptr [rcx+8]
0x180015166  mov     rcx, [rax]
0x180015169  mov     rax, [rax+8]
0x18001516d  mov     [rbp+57h+var_80], rcx
0x180015171  mov     [rbp+57h+var_78], rax
0x180015175  mov     [rbp+57h+var_70], rcx
0x180015179  mov     [rbp+57h+var_68], 0
0x180015181  lea     rcx, [rbp+57h+var_60]
0x180015185  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x18001518b  xorps   xmm0, xmm0
0x18001518e  movdqu  [rbp+57h+var_40], xmm0
0x180015193  mov     [rbp+57h+var_30], 0
0x18001519b  mov     [rbp+57h+var_48], 0
0x1800151a3  mov     [rbp+57h+var_50], 0
0x1800151a7  mov     [rbp+57h+var_28], 0
0x1800151ad  lea     r8, [rbp+57h+var_80]
0x1800151b1  mov     rdx, rdi
0x1800151b4  lea     rcx, [rbp+57h+var_90]
0x1800151b8  call    ??$create_task@V_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@3@@Z@@Concurrency@@YA?AV?$task@X@0@V_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@4@@Z@Vtask_options@0@@Z; Concurrency::create_task<`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_>(`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,Concurrency::task_options)
0x1800151bd  or      r14d, 0FFFFFFFFh
0x1800151c1  cmp     rsi, rax
0x1800151c4  jz      short loc_180015223
0x1800151c6  mov     rcx, [rax]
0x1800151c9  mov     rdx, [rax+8]
0x1800151cd  mov     qword ptr [rax], 0
0x1800151d4  mov     qword ptr [rax+8], 0
0x1800151dc  mov     [rsi], rcx
0x1800151df  mov     rbx, [rsi+8]
0x1800151e3  mov     [rsi+8], rdx
0x1800151e7  test    rbx, rbx
0x1800151ea  jz      short loc_180015223
0x1800151ec  mov     eax, r14d
0x1800151ef  lock xadd [rbx+8], eax
0x1800151f4  add     eax, r14d
0x1800151f7  jnz     short loc_180015223
0x1800151f9  mov     rax, [rbx]
0x1800151fc  mov     rcx, rbx
0x1800151ff  mov     rax, [rax]
0x180015202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015207  mov     eax, r14d
0x18001520a  lock xadd [rbx+0Ch], eax
0x18001520f  add     eax, r14d
0x180015212  jnz     short loc_180015223
0x180015214  mov     rax, [rbx]
0x180015217  mov     rcx, rbx
0x18001521a  mov     rax, [rax+8]
0x18001521e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015223  mov     rbx, [rbp+57h+var_88]
0x180015227  test    rbx, rbx
0x18001522a  jz      short loc_180015263
0x18001522c  mov     eax, r14d
0x18001522f  lock xadd [rbx+8], eax
0x180015234  add     eax, r14d
0x180015237  jnz     short loc_180015263
0x180015239  mov     rax, [rbx]
0x18001523c  mov     rcx, rbx
0x18001523f  mov     rax, [rax]
0x180015242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015247  mov     eax, r14d
0x18001524a  lock xadd [rbx+0Ch], eax
0x18001524f  add     eax, r14d
0x180015252  jnz     short loc_180015263
0x180015254  mov     rax, [rbx]
0x180015257  mov     rcx, rbx
0x18001525a  mov     rax, [rax+8]
0x18001525e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015263  mov     byte ptr [rdi+0C2h], 1
0x18001526a  mov     rax, rdi
0x18001526d  add     rsp, 90h
0x180015274  pop     r14
0x180015276  pop     rdi
0x180015277  pop     rsi
0x180015278  pop     rbx
0x180015279  pop     rbp
0x18001527a  retn
```
