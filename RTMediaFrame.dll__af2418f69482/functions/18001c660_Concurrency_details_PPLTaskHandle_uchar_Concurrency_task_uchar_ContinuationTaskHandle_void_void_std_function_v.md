# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::invoke(void)

- ea: `0x18001c660`
- end: `0x18001c6d7`
- name: `?invoke@?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEBAXXZ`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001c660`
- `0x18001db5c`
- `0x18001dbb0`
- `0x1800218b8`
- `0x1800218e4`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001c6c6`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001c6c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  Concurrency::details::_Task_impl_base *v3; // rcx
  Concurrency::details::_Task_impl_base *v4; // rbx
  const struct std::exception_ptr *v5; // rax
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 40);
  v8 = a1 + 40;
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 40)) )
  {
    try
    {
      Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(a1);
    }
    catch ( Concurrency::task_canceled )
    {
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 40), 1);
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 40), 1);
    }
    catch ( ... )
    {
      v4 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
      v5 = (const struct std::exception_ptr *)std::current_exception(v6);
      Concurrency::details::_Task_impl_base::_CancelWithException(v4, v5);
      __ExceptionPtrDestroy(v6);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*(_QWORD *)v8 + 352LL));
  }
  else
  {
    v3 = *v2;
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 56) + 16LL) )
      Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder(v3);
    else
      Concurrency::details::_Task_impl_base::_Cancel(v3, 1);
  }
}

```

## disassembly

```asm
0x18001c660  mov     [rsp+arg_10], rbx
0x18001c665  mov     [rsp+arg_0], rcx
0x18001c66a  push    rdi
0x18001c66b  sub     rsp, 30h
0x18001c66f  mov     rbx, rcx
0x18001c672  lea     rdi, [rcx+28h]
0x18001c676  mov     [rsp+38h+arg_8], rdi
0x18001c67b  mov     rcx, [rdi]
0x18001c67e  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18001c683  test    al, al
0x18001c685  jnz     short loc_18001C6A8
0x18001c687  mov     rdx, [rbx+38h]
0x18001c68b  add     rdx, 10h
0x18001c68f  mov     rcx, [rdi]; this
0x18001c692  cmp     qword ptr [rdx], 0
0x18001c696  jz      short loc_18001C69F
0x18001c698  call    ?_CancelWithExceptionHolder@_Task_impl_base@details@Concurrency@@QEAA_NAEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@_N@Z; Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &,bool)
0x18001c69d  jmp     short loc_18001C6CC
0x18001c69f  mov     dl, 1; bool
0x18001c6a1  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18001c6a6  jmp     short loc_18001C6CC
0x18001c6a8  mov     rcx, rbx
0x18001c6ab  call    ?_Continue@?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU?$integral_constant@_N$00@std@@U_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync)
0x18001c6b0  nop
0x18001c6b1  jmp     short loc_18001C6B7
0x18001c6b3  jmp     short loc_18001C6B7
0x18001c6b5  jmp     short $+2
0x18001c6b7  mov     rax, [rsp+38h+arg_8]
0x18001c6bc  mov     rcx, [rax]
0x18001c6bf  add     rcx, 160h
0x18001c6c6  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18001c6cc  mov     rbx, [rsp+38h+arg_10]
0x18001c6d1  add     rsp, 30h
0x18001c6d5  pop     rdi
0x18001c6d6  retn
```
