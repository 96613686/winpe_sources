# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::invoke(void)

- ea: `0x18001e780`
- end: `0x18001e7f7`
- name: `?invoke@?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEBAXXZ`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001c110`
- `0x18001c400`
- `0x18001c644`
- `0x18001dec4`
- `0x18001e780`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e7e6`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e7e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // r8
  _QWORD *v4; // rdx
  Concurrency::details::_Task_impl_base *v5; // rcx
  Concurrency::details::_Task_impl_base *v6; // rbx
  const struct std::exception_ptr *v7; // rax
  _BYTE *v8; // rdx
  _BYTE *v9; // rdx
  _BYTE v10[32]; // [rsp+0h] [rbp-38h] BYREF
  _BYTE v11[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v13; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 40);
  v13 = a1 + 40;
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 40)) )
  {
    try
    {
      Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(a1);
    }
    catch ( Concurrency::task_canceled )
    {
      v8 = v10;
      LOBYTE(v8) = 1;
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 40), (__int64)v8);
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v9 = v10;
      LOBYTE(v9) = 1;
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 40), (__int64)v9);
    }
    catch ( ... )
    {
      v6 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
      v7 = (const struct std::exception_ptr *)std::current_exception(v11);
      Concurrency::details::_Task_impl_base::_CancelWithException(v6, v7);
      __ExceptionPtrDestroy(v11);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*(_QWORD *)v13 + 352LL));
  }
  else
  {
    v4 = (_QWORD *)(*(_QWORD *)(a1 + 56) + 16LL);
    v5 = *v2;
    if ( *v4 )
    {
      Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder((__int64)v5, (__int64)v4, v3);
    }
    else
    {
      LOBYTE(v4) = 1;
      Concurrency::details::_Task_impl_base::_Cancel(v5, (__int64)v4);
    }
  }
}

```

## disassembly

```asm
0x18001e780  mov     [rsp+arg_10], rbx
0x18001e785  mov     [rsp+arg_0], rcx
0x18001e78a  push    rdi
0x18001e78b  sub     rsp, 30h
0x18001e78f  mov     rbx, rcx
0x18001e792  lea     rdi, [rcx+28h]
0x18001e796  mov     [rsp+38h+arg_8], rdi
0x18001e79b  mov     rcx, [rdi]
0x18001e79e  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18001e7a3  test    al, al
0x18001e7a5  jnz     short loc_18001E7C8
0x18001e7a7  mov     rdx, [rbx+38h]
0x18001e7ab  add     rdx, 10h
0x18001e7af  mov     rcx, [rdi]; this
0x18001e7b2  cmp     qword ptr [rdx], 0
0x18001e7b6  jz      short loc_18001E7BF
0x18001e7b8  call    ?_CancelWithExceptionHolder@_Task_impl_base@details@Concurrency@@QEAA_NAEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@_N@Z; Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &,bool)
0x18001e7bd  jmp     short loc_18001E7EC
0x18001e7bf  mov     dl, 1; bool
0x18001e7c1  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18001e7c6  jmp     short loc_18001E7EC
0x18001e7c8  mov     rcx, rbx
0x18001e7cb  call    ?_Continue@?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU?$integral_constant@_N$00@std@@U_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync)
0x18001e7d0  nop
0x18001e7d1  jmp     short loc_18001E7D7
0x18001e7d3  jmp     short loc_18001E7D7
0x18001e7d5  jmp     short $+2
0x18001e7d7  mov     rax, [rsp+38h+arg_8]
0x18001e7dc  mov     rcx, [rax]
0x18001e7df  add     rcx, 160h
0x18001e7e6  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18001e7ec  mov     rbx, [rsp+38h+arg_10]
0x18001e7f1  add     rsp, 30h
0x18001e7f5  pop     rdi
0x18001e7f6  retn
```
