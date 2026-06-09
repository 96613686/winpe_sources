# Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18004e940`
- end: `0x18004e9ec`
- name: `?_Init@?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f9e0`

## callees

- `0x180046338`
- `0x180048de4`
- `0x18004ab6c`
- `0x18004e698`
- `0x18004eb2c`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004e99e`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004e99e`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004e9b5`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004e9b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,Concurrency::details::_TypeSelectorNoAsync>::_Init(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rsi
  _OWORD v4[2]; // [rsp+20h] [rbp-59h] BYREF
  _BYTE v5[56]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v6; // [rsp+78h] [rbp-1h]
  _BYTE v7[80]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v8; // [rsp+E0h] [rbp+67h]
  Concurrency::details::_TaskEventLogger *v9; // [rsp+F0h] [rbp+77h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
  v6 = 0;
  v6 = std::_Global_new<std::_Func_impl_no_alloc<_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,wil::cloud_store_save_result,>,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_ const &>((struct _lambda_37b72c2f4ec99a04b6fedfe365ac8865_ *)(a1 + 24));
  v8 = Concurrency::_Init_func_transformer<wil::cloud_store_save_result>::_Perform(v7, v5);
  v9 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v9);
  std::_Func_class<wil::cloud_store_save_result,>::operator()(v8, v4);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v9);
  std::_Func_class<void,>::~_Func_class<void,>(v8);
  v4[1] = v4[0];
  return Concurrency::details::_Task_impl<wil::cloud_store_save_result>::_FinalizeAndRunContinuations(v2);
}

```

## disassembly

```asm
0x18004e940  mov     [rsp-8+arg_8], rbx
0x18004e945  push    rbp
0x18004e946  push    rsi
0x18004e947  push    rdi
0x18004e948  lea     rbp, [rsp-47h]
0x18004e94d  sub     rsp, 0C0h
0x18004e954  mov     rbx, rcx
0x18004e957  mov     rsi, [rcx+8]
0x18004e95b  lea     rax, [rbp+57h+var_90]
0x18004e95f  mov     [rbp+57h+arg_0], rax
0x18004e963  mov     [rbp+57h+var_58], 0
0x18004e96b  add     rcx, 18h; struct _lambda_37b72c2f4ec99a04b6fedfe365ac8865_ *
0x18004e96f  call    ??$_Global_new@V?$_Func_impl_no_alloc@V_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@Vcloud_store_save_result@wil@@$$V@std@@AEBV_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@Vcloud_store_save_result@wil@@$$V@0@AEBV_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@@Z; std::_Global_new<std::_Func_impl_no_alloc<_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,wil::cloud_store_save_result,>,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_ const &>(_lambda_37b72c2f4ec99a04b6fedfe365ac8865_ const &)
0x18004e974  mov     [rbp+57h+var_58], rax
0x18004e978  lea     rdx, [rbp+57h+var_90]
0x18004e97c  lea     rcx, [rbp+57h+var_50]
0x18004e980  call    ?_Perform@?$_Init_func_transformer@Vcloud_store_save_result@wil@@@Concurrency@@SA?AV?$function@$$A6A?AVcloud_store_save_result@wil@@XZ@std@@V34@@Z; Concurrency::_Init_func_transformer<wil::cloud_store_save_result>::_Perform(std::function<wil::cloud_store_save_result (void)>)
0x18004e985  mov     rdi, rax
0x18004e988  mov     [rbp+57h+arg_0], rax
0x18004e98c  mov     rbx, [rbx+8]
0x18004e990  add     rbx, 160h
0x18004e997  mov     [rbp+57h+arg_10], rbx
0x18004e99b  mov     rcx, rbx
0x18004e99e  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18004e9a4  nop
0x18004e9a5  lea     rdx, [rbp+57h+var_B0]
0x18004e9a9  mov     rcx, rdi
0x18004e9ac  call    ??R?$_Func_class@Vcloud_store_save_result@wil@@$$V@std@@QEBA?AVcloud_store_save_result@wil@@XZ; std::_Func_class<wil::cloud_store_save_result,>::operator()(void)
0x18004e9b1  nop
0x18004e9b2  mov     rcx, rbx
0x18004e9b5  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18004e9bb  nop
0x18004e9bc  mov     rcx, rdi
0x18004e9bf  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18004e9c4  movaps  xmm0, [rbp+57h+var_B0]
0x18004e9c8  movdqa  [rbp+57h+var_A0], xmm0
0x18004e9cd  lea     rdx, [rbp+57h+var_A0]
0x18004e9d1  mov     rcx, rsi; this
0x18004e9d4  call    ?_FinalizeAndRunContinuations@?$_Task_impl@Vcloud_store_save_result@wil@@@details@Concurrency@@QEAAXVcloud_store_save_result@wil@@@Z; Concurrency::details::_Task_impl<wil::cloud_store_save_result>::_FinalizeAndRunContinuations(wil::cloud_store_save_result)
0x18004e9d9  mov     rbx, [rsp+0D0h+arg_8]
0x18004e9e1  add     rsp, 0C0h
0x18004e9e8  pop     rdi
0x18004e9e9  pop     rsi
0x18004e9ea  pop     rbp
0x18004e9eb  retn
```
