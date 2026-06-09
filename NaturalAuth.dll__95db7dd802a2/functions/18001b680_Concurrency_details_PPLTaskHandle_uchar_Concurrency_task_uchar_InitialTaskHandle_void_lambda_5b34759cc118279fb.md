# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x18001b680`
- end: `0x18001b6e2`
- name: `?invoke@?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_5b34759cc118279fbe7c091b1e0eae68_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEBAXXZ`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180016b00`
- `0x180018e34`
- `0x18001abc0`
- `0x18001b680`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001b6d1`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001b6d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
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
      Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
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
0x18001b680  mov     [rsp+arg_10], rbx
0x18001b685  mov     [rsp+arg_0], rcx
0x18001b68a  push    rdi
0x18001b68b  sub     rsp, 30h
0x18001b68f  mov     rbx, rcx
0x18001b692  lea     rdi, [rcx+8]
0x18001b696  mov     [rsp+38h+arg_8], rdi
0x18001b69b  mov     rcx, [rdi]
0x18001b69e  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18001b6a3  test    al, al
0x18001b6a5  jnz     short loc_18001B6B3
0x18001b6a7  mov     dl, 1; bool
0x18001b6a9  mov     rcx, [rdi]; this
0x18001b6ac  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18001b6b1  jmp     short loc_18001B6D7
0x18001b6b3  mov     rcx, rbx
0x18001b6b6  call    ?_Init@?$_InitialTaskHandle@XV_lambda_5b34759cc118279fbe7c091b1e0eae68_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x18001b6bb  nop
0x18001b6bc  jmp     short loc_18001B6C2
0x18001b6be  jmp     short loc_18001B6C2
0x18001b6c0  jmp     short $+2
0x18001b6c2  mov     rax, [rsp+38h+arg_8]
0x18001b6c7  mov     rcx, [rax]
0x18001b6ca  add     rcx, 160h
0x18001b6d1  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18001b6d7  mov     rbx, [rsp+38h+arg_10]
0x18001b6dc  add     rsp, 30h
0x18001b6e0  pop     rdi
0x18001b6e1  retn
```
