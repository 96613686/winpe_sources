# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x18001a770`
- end: `0x18001a83b`
- name: `?invoke@?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEBAXXZ`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18001956c`
- `0x18001a770`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a7a2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a7be`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a7a2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a7be`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001a823`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001a823`
- `msvcp_win!_Mtx_unlock` at `0x18001a7d0`
- `msvcp_win!_Mtx_unlock` at `0x18001a804`
- `msvcp_win!_Mtx_unlock` at `0x18001a7d0`
- `msvcp_win!_Mtx_unlock` at `0x18001a804`
- `msvcp_win!_Mtx_lock` at `0x18001a793`
- `msvcp_win!_Mtx_lock` at `0x18001a793`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _invoke____PPLTaskHandle_EU___InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__U_TaskProcHandle_details_3__details_Concurrency__UEBAXXZ(
        __int64 a1)
{
  _QWORD *v2; // r14
  __int64 v3; // rsi
  struct _Mtx_internal_imp_t *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  Concurrency::details::_Task_impl_base *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rdx
  _OWORD v11[2]; // [rsp+30h] [rbp-28h] BYREF

  v2 = (_QWORD *)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 8);
  if ( _Mtx_lock((_Mtx_t)(v3 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v3 + 108) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v3 + 108) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v4 = (struct _Mtx_internal_imp_t *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 8) == 2 )
  {
    _Mtx_unlock(v4);
    v5 = *v2 + 16LL;
    LOBYTE(v5) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)*v2 + 8LL))(*v2, v5, 0, 0, *v2 + 16LL);
  }
  else
  {
    *(_DWORD *)(v3 + 8) = 1;
    _Mtx_unlock(v4);
    try
    {
      __Init____InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__QEBAXU_TypeSelectorNoAsync_details_3__Z(a1);
    }
    catch ( Concurrency::task_canceled )
    {
      v6 = *(_QWORD *)(a1 + 8);
      v7 = v6 + 16;
      LOBYTE(v7) = 1;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v6 + 8LL))(v6, v7, 0, 0, v6 + 16);
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v9 = *(_QWORD *)(a1 + 8);
      v10 = v9 + 16;
      LOBYTE(v10) = 1;
      guard_dispatch_icall_thunk_10345483385596137414(v9, v10, 0, 0, v9 + 16);
    }
    catch ( ... )
    {
      v8 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v11[0] = 0;
      __ExceptionPtrCreate(v11);
      __ExceptionPtrCurrentException(v11);
      Concurrency::details::_Task_impl_base::_CancelWithException(v8, (const struct std::exception_ptr *)v11);
      __ExceptionPtrDestroy(v11);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*v2 + 352LL));
  }
}

```

## disassembly

```asm
0x18001a770  mov     [rsp+arg_10], rbx
0x18001a775  mov     [rsp+arg_0], rcx
0x18001a77a  push    rsi
0x18001a77b  push    rdi
0x18001a77c  push    r14
0x18001a77e  sub     rsp, 40h
0x18001a782  mov     rdi, rcx
0x18001a785  lea     r14, [rcx+8]
0x18001a789  mov     rsi, [r14]
0x18001a78c  lea     rbx, [rsi+20h]
0x18001a790  mov     rcx, rbx; _Mtx_t
0x18001a793  call    cs:__imp__Mtx_lock
0x18001a799  test    eax, eax
0x18001a79b  jz      short loc_18001A7A9
0x18001a79d  mov     ecx, 5
0x18001a7a2  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001a7a8  int     3; Trap to Debugger
0x18001a7a9  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18001a7b0  jnz     short loc_18001A7C5
0x18001a7b2  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18001a7b9  mov     ecx, 6
0x18001a7be  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001a7c4  int     3; Trap to Debugger
0x18001a7c5  mov     eax, [rsi+8]
0x18001a7c8  mov     rcx, rbx; _Mtx_t
0x18001a7cb  cmp     eax, 2
0x18001a7ce  jnz     short loc_18001A7F8
0x18001a7d0  call    cs:__imp__Mtx_unlock
0x18001a7d6  mov     rcx, [r14]
0x18001a7d9  mov     rax, [rcx]
0x18001a7dc  lea     rdx, [rcx+10h]
0x18001a7e0  mov     [rsp+58h+var_38], rdx
0x18001a7e5  xor     r9d, r9d
0x18001a7e8  xor     r8d, r8d
0x18001a7eb  mov     dl, 1
0x18001a7ed  mov     rax, [rax+8]
0x18001a7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7f6  jmp     short loc_18001A829
0x18001a7f8  mov     [rsp+58h+arg_8], r14
0x18001a7fd  mov     dword ptr [rsi+8], 1
0x18001a804  call    cs:__imp__Mtx_unlock
0x18001a80a  nop
0x18001a80b  mov     rcx, rdi
0x18001a80e  call    ?_Init@?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x18001a813  nop
0x18001a814  mov     rax, [rsp+58h+arg_8]
0x18001a819  mov     rcx, [rax]
0x18001a81c  add     rcx, 160h
0x18001a823  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18001a829  mov     rbx, [rsp+58h+arg_10]
0x18001a82e  add     rsp, 40h
0x18001a832  pop     r14
0x18001a834  pop     rdi
0x18001a835  pop     rsi
0x18001a836  retn
0x18001a837  jmp     short loc_18001A814
0x18001a839  jmp     short loc_18001A814
```
