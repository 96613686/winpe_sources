# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x180010d90`
- end: `0x180010df2`
- name: `?invoke@?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV?$function@$$A6AXXZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEBAXXZ`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010d90`
- `0x180010df8`
- `0x18001db5c`
- `0x1800218b8`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180010de1`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180010de1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
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
      Concurrency::task<unsigned char>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
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
0x180010d90  mov     [rsp+arg_10], rbx
0x180010d95  mov     [rsp+arg_0], rcx
0x180010d9a  push    rdi
0x180010d9b  sub     rsp, 30h
0x180010d9f  mov     rbx, rcx
0x180010da2  lea     rdi, [rcx+8]
0x180010da6  mov     [rsp+38h+arg_8], rdi
0x180010dab  mov     rcx, [rdi]
0x180010dae  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x180010db3  test    al, al
0x180010db5  jnz     short loc_180010DC3
0x180010db7  mov     dl, 1; bool
0x180010db9  mov     rcx, [rdi]; this
0x180010dbc  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x180010dc1  jmp     short loc_180010DE7
0x180010dc3  mov     rcx, rbx
0x180010dc6  call    ?_Init@?$_InitialTaskHandle@XV?$function@$$A6AXXZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<uchar>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x180010dcb  nop
0x180010dcc  jmp     short loc_180010DD2
0x180010dce  jmp     short loc_180010DD2
0x180010dd0  jmp     short $+2
0x180010dd2  mov     rax, [rsp+38h+arg_8]
0x180010dd7  mov     rcx, [rax]
0x180010dda  add     rcx, 160h
0x180010de1  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180010de7  mov     rbx, [rsp+38h+arg_10]
0x180010dec  add     rsp, 30h
0x180010df0  pop     rdi
0x180010df1  retn
```
