# Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<void (&)(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>> const &,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>> const &),std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::function<void (void)>>>> const &> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<uchar (void)>>(std::function<uchar (void)>)

- ea: `0x18005a3a8`
- end: `0x18005a41b`
- name: `??$_LogWorkItemAndInvokeUserLambda@V?$function@$$A6AEXZ@std@@@?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@A6AXAEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$function@$$A6AXXZ@std@@@std@@@std@@@std@@0@ZV12@AEBV12@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@A6AXAEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$function@$$A6AXXZ@std@@@std@@@std@@@std@@0@ZV12@AEBV12@@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAEV?$function@$$A6AEXZ@std@@@Z`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005a20c`

## callees

- `0x180057e70`
- `0x18005a3a8`
- `0x18005a4a0`

## import_xrefs

- `MSVCP140!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a3d1`
- `MSVCP140!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a3d1`
- `MSVCP140!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a3f3`
- `MSVCP140!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a3f3`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x18005a414`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x18005a414`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ____LogWorkItemAndInvokeUserLambda_V__function___A6AEXZ_std______InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_A6AXAEBV___Vector_iterator_V___Vector_val_U___Simple_types_V__function___A6AXXZ_std___std___std___std__0_ZV12_AEBV12__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_A6AXAEBV___Vector_iterator_V___Vector_val_U___Simple_types_V__function___A6AXXZ_std___std___std___std__0_ZV12_AEBV12__3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__QEBAEV__function___A6AEXZ_std___Z(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_TaskEventLogger *v3; // rbx
  __int64 v4; // rcx
  char v5; // di

  v3 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v3);
  v4 = *(_QWORD *)(a2 + 56);
  if ( !v4 )
  {
    std::_Xbad_function_call();
    JUMPOUT(0x18005A41BLL);
  }
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v3);
  std::_Func_class<bool,float>::~_Func_class<bool,float>(a2);
  return v5;
}

```

## disassembly

```asm
0x18005a3a8  mov     rax, rsp
0x18005a3ab  mov     [rax+18h], rbx
0x18005a3af  mov     [rax+20h], rsi
0x18005a3b3  mov     [rax+10h], rdx
0x18005a3b7  push    rdi
0x18005a3b8  sub     rsp, 20h
0x18005a3bc  mov     rsi, rdx
0x18005a3bf  mov     rbx, [rcx+8]
0x18005a3c3  add     rbx, 160h
0x18005a3ca  mov     [rax+8], rbx
0x18005a3ce  mov     rcx, rbx
0x18005a3d1  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18005a3d7  mov     rcx, [rsi+38h]
0x18005a3db  test    rcx, rcx
0x18005a3de  jz      short loc_18005A414
0x18005a3e0  mov     rax, [rcx]
0x18005a3e3  mov     rax, [rax+10h]
0x18005a3e7  call    cs:__guard_dispatch_icall_fptr
0x18005a3ed  mov     dil, al
0x18005a3f0  mov     rcx, rbx
0x18005a3f3  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18005a3f9  mov     rcx, rsi
0x18005a3fc  call    ??1?$_Func_class@_NM@std@@QEAA@XZ; std::_Func_class<bool,float>::~_Func_class<bool,float>(void)
0x18005a401  mov     al, dil
0x18005a404  mov     rbx, [rsp+28h+arg_10]
0x18005a409  mov     rsi, [rsp+28h+arg_18]
0x18005a40e  add     rsp, 20h
0x18005a412  pop     rdi
0x18005a413  retn
0x18005a414  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18005a41a  nop
```
