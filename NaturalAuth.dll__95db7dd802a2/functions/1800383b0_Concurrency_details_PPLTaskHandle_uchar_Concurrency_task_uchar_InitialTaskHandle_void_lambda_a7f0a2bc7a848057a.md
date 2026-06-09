# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x1800383b0`
- end: `0x180038412`
- name: `?invoke@?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_a7f0a2bc7a848057a70d113d8425a777_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEBAXXZ`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180016b00`
- `0x18001abc0`
- `0x180037ed0`
- `0x1800383b0`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180038401`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180038401`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v3 = a1 + 8;
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*(_QWORD *)v3 + 352LL));
  }
  else
  {
    Concurrency::details::_Task_impl_base::_Cancel(*v2, 1);
  }
}

```

## disassembly

```asm
0x1800383b0  mov     [rsp+arg_10], rbx
0x1800383b5  mov     [rsp+arg_0], rcx
0x1800383ba  push    rdi
0x1800383bb  sub     rsp, 30h
0x1800383bf  mov     rbx, rcx
0x1800383c2  lea     rdi, [rcx+8]
0x1800383c6  mov     [rsp+38h+arg_8], rdi
0x1800383cb  mov     rcx, [rdi]
0x1800383ce  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x1800383d3  test    al, al
0x1800383d5  jnz     short loc_1800383E3
0x1800383d7  mov     dl, 1; bool
0x1800383d9  mov     rcx, [rdi]; this
0x1800383dc  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x1800383e1  jmp     short loc_180038407
0x1800383e3  mov     rcx, rbx
0x1800383e6  call    ?_Init@?$_InitialTaskHandle@XV_lambda_a7f0a2bc7a848057a70d113d8425a777_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x1800383eb  nop
0x1800383ec  jmp     short loc_1800383F2
0x1800383ee  jmp     short loc_1800383F2
0x1800383f0  jmp     short $+2
0x1800383f2  mov     rax, [rsp+38h+arg_8]
0x1800383f7  mov     rcx, [rax]
0x1800383fa  add     rcx, 160h
0x180038401  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180038407  mov     rbx, [rsp+38h+arg_10]
0x18003840c  add     rsp, 30h
0x180038410  pop     rdi
0x180038411  retn
```
