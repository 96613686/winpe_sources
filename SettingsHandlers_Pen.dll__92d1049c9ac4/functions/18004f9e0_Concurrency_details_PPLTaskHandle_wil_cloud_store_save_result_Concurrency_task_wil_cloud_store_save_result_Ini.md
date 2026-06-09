# Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x18004f9e0`
- end: `0x18004fa42`
- name: `?invoke@?$_PPLTaskHandle@Vcloud_store_save_result@wil@@U?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@UEBAXXZ`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004ca10`
- `0x18004e940`
- `0x18004f2e0`
- `0x18004f9e0`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004fa31`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004fa31`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  Concurrency::details::_Task_impl_base *v3; // rbx
  const struct std::exception_ptr *v4; // rax
  _BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v7 = a1 + 8;
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    try
    {
      Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
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
      v3 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v4 = (const struct std::exception_ptr *)std::current_exception(v5);
      Concurrency::details::_Task_impl_base::_CancelWithException(v3, v4);
      __ExceptionPtrDestroy(v5);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*(_QWORD *)v7 + 352LL));
  }
  else
  {
    Concurrency::details::_Task_impl_base::_Cancel(*v2, 1);
  }
}

```

## disassembly

```asm
0x18004f9e0  mov     [rsp+arg_10], rbx
0x18004f9e5  mov     [rsp+arg_0], rcx
0x18004f9ea  push    rdi
0x18004f9eb  sub     rsp, 30h
0x18004f9ef  mov     rbx, rcx
0x18004f9f2  lea     rdi, [rcx+8]
0x18004f9f6  mov     [rsp+38h+arg_8], rdi
0x18004f9fb  mov     rcx, [rdi]
0x18004f9fe  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18004fa03  test    al, al
0x18004fa05  jnz     short loc_18004FA13
0x18004fa07  mov     dl, 1; bool
0x18004fa09  mov     rcx, [rdi]; this
0x18004fa0c  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18004fa11  jmp     short loc_18004FA37
0x18004fa13  mov     rcx, rbx
0x18004fa16  call    ?_Init@?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x18004fa1b  nop
0x18004fa1c  jmp     short loc_18004FA22
0x18004fa1e  jmp     short loc_18004FA22
0x18004fa20  jmp     short $+2
0x18004fa22  mov     rax, [rsp+38h+arg_8]
0x18004fa27  mov     rcx, [rax]
0x18004fa2a  add     rcx, 160h
0x18004fa31  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18004fa37  mov     rbx, [rsp+38h+arg_10]
0x18004fa3c  add     rsp, 30h
0x18004fa40  pop     rdi
0x18004fa41  retn
```
