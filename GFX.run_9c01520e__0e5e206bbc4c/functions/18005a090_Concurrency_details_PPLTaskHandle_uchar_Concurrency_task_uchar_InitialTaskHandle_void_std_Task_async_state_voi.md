# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<void (&)(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>> const &,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>> const &),std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>> const &> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x18005a090`
- end: `0x18005a11a`
- name: `?invoke@?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@A6AXAEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$function@$$A6AXXZ@std@@@std@@@std@@@std@@0@ZV12@AEBV12@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@A6AXAEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$function@$$A6AXXZ@std@@@std@@@std@@@std@@0@ZV12@AEBV12@@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEBAXXZ`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005a090`
- `0x18005a20c`
- `0x18005a514`
- `0x180076df0`

## import_xrefs

- `MSVCP140!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a0ed`
- `MSVCP140!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a0ed`
- `MSVCP140!_Mtx_unlock` at `0x18005a0cf`
- `MSVCP140!_Mtx_unlock` at `0x18005a101`
- `MSVCP140!_Mtx_unlock` at `0x18005a0cf`
- `MSVCP140!_Mtx_unlock` at `0x18005a101`

## pseudocode

```c
void __fastcall _invoke____PPLTaskHandle_EU___InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_A6AXAEBV___Vector_iterator_V___Vector_val_U___Simple_types_V__function___A6AXXZ_std___std___std___std__0_ZV12_AEBV12__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_A6AXAEBV___Vector_iterator_V___Vector_val_U___Simple_types_V__function___A6AXXZ_std___std___std___std__0_ZV12_AEBV12__3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__U_TaskProcHandle_details_3__details_Concurrency__UEBAXXZ(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // r14
  __int64 v3; // rsi
  struct _Mtx_internal_imp_t *v4; // rcx
  Concurrency::details::_Task_impl_base *v5; // rbx
  const struct std::exception_ptr *v6; // rax
  _BYTE v7[40]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+58h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v9 = a1 + 8;
  v3 = *(_QWORD *)(a1 + 8);
  std::_Mutex_base::lock((std::_Mutex_base *)(v3 + 32));
  v4 = (struct _Mtx_internal_imp_t *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 8) == 2 )
  {
    _Mtx_unlock(v4);
    Concurrency::details::_Task_impl_base::_Cancel(*v2, 1);
  }
  else
  {
    *(_DWORD *)(v3 + 8) = 1;
    _Mtx_unlock(v4);
    try
    {
      __Init____InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_A6AXAEBV___Vector_iterator_V___Vector_val_U___Simple_types_V__function___A6AXXZ_std___std___std___std__0_ZV12_AEBV12__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_A6AXAEBV___Vector_iterator_V___Vector_val_U___Simple_types_V__function___A6AXXZ_std___std___std___std__0_ZV12_AEBV12__3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__QEBAXU_TypeSelectorNoAsync_details_3__Z(a1);
    }
    catch ( Concurrency::task_canceled )
    {
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 8), 1);
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 8), 1);
    }
    catch ( ... )
    {
      v5 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v6 = (const struct std::exception_ptr *)std::current_exception(v7);
      Concurrency::details::_Task_impl_base::_CancelWithException(v5, v6);
      __ExceptionPtrDestroy(v7);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*(_QWORD *)v9 + 352LL));
  }
}

```

## disassembly

```asm
0x18005a090  mov     [rsp+arg_10], rbx
0x18005a095  mov     [rsp+arg_0], rcx
0x18005a09a  push    rsi
0x18005a09b  push    rdi
0x18005a09c  push    r14
0x18005a09e  sub     rsp, 30h
0x18005a0a2  mov     rdi, rcx
0x18005a0a5  lea     r14, [rcx+8]
0x18005a0a9  mov     [rsp+48h+arg_8], r14
0x18005a0ae  mov     rsi, [r14]
0x18005a0b1  lea     rbx, [rsi+20h]
0x18005a0b5  mov     rcx, rbx; this
0x18005a0b8  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18005a0bd  mov     eax, [rsi+8]
0x18005a0c0  mov     rcx, rbx; _Mtx_t
0x18005a0c3  cmp     eax, 2
0x18005a0c6  jz      short loc_18005A101
0x18005a0c8  mov     dword ptr [rsi+8], 1
0x18005a0cf  call    cs:__imp__Mtx_unlock
0x18005a0d5  mov     rcx, rdi
0x18005a0d8  call    ?_Init@?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@A6AXAEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$function@$$A6AXXZ@std@@@std@@@std@@@std@@0@ZV12@AEBV12@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@A6AXAEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$function@$$A6AXXZ@std@@@std@@@std@@@std@@0@ZV12@AEBV12@@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<void (&)(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>> const &,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>> const &),std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>> const &> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x18005a0dd  nop
0x18005a0de  mov     rax, [rsp+48h+arg_8]
0x18005a0e3  mov     rcx, [rax]
0x18005a0e6  add     rcx, 160h
0x18005a0ed  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18005a0f3  mov     rbx, [rsp+48h+arg_10]
0x18005a0f8  add     rsp, 30h
0x18005a0fc  pop     r14
0x18005a0fe  pop     rdi
0x18005a0ff  pop     rsi
0x18005a100  retn
0x18005a101  call    cs:__imp__Mtx_unlock
0x18005a107  mov     dl, 1; bool
0x18005a109  mov     rcx, [r14]; this
0x18005a10c  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18005a111  jmp     short loc_18005A0F3
0x18005a113  jmp     short loc_18005A0DE
0x18005a115  jmp     short loc_18005A0DE
0x18005a117  jmp     short loc_18005A0DE
```
