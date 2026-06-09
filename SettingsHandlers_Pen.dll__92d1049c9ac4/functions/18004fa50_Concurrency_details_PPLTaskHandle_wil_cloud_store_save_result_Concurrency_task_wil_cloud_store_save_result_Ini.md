# Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x18004fa50`
- end: `0x18004fab2`
- name: `?invoke@?$_PPLTaskHandle@Vcloud_store_save_result@wil@@U?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_5841bb6124e075856403c279d110f614_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@UEBAXXZ`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004ca10`
- `0x18004e9f4`
- `0x18004f2e0`
- `0x18004fa50`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004faa1`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004faa1`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v3 = a1 + 8;
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
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
0x18004fa50  mov     [rsp+arg_10], rbx
0x18004fa55  mov     [rsp+arg_0], rcx
0x18004fa5a  push    rdi
0x18004fa5b  sub     rsp, 30h
0x18004fa5f  mov     rbx, rcx
0x18004fa62  lea     rdi, [rcx+8]
0x18004fa66  mov     [rsp+38h+arg_8], rdi
0x18004fa6b  mov     rcx, [rdi]
0x18004fa6e  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18004fa73  test    al, al
0x18004fa75  jnz     short loc_18004FA83
0x18004fa77  mov     dl, 1; bool
0x18004fa79  mov     rcx, [rdi]; this
0x18004fa7c  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18004fa81  jmp     short loc_18004FAA7
0x18004fa83  mov     rcx, rbx
0x18004fa86  call    ?_Init@?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_5841bb6124e075856403c279d110f614_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x18004fa8b  nop
0x18004fa8c  jmp     short loc_18004FA92
0x18004fa8e  jmp     short loc_18004FA92
0x18004fa90  jmp     short $+2
0x18004fa92  mov     rax, [rsp+38h+arg_8]
0x18004fa97  mov     rcx, [rax]
0x18004fa9a  add     rcx, 160h
0x18004faa1  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18004faa7  mov     rbx, [rsp+38h+arg_10]
0x18004faac  add     rsp, 30h
0x18004fab0  pop     rdi
0x18004fab1  retn
```
