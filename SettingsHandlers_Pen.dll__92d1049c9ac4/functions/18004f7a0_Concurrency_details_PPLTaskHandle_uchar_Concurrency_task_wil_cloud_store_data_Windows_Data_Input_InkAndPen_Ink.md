# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::invoke(void)

- ea: `0x18004f7a0`
- end: `0x18004f817`
- name: `?invoke@?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@XV?$function@$$A6AXV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@U?$integral_constant@_N$0A@@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEBAXXZ`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18004ca10`
- `0x18004d250`
- `0x18004d2f8`
- `0x18004f2e0`
- `0x18004f7a0`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004f806`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004f806`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::invoke(
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
      Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(a1);
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
0x18004f7a0  mov     [rsp+arg_10], rbx
0x18004f7a5  mov     [rsp+arg_0], rcx
0x18004f7aa  push    rdi
0x18004f7ab  sub     rsp, 30h
0x18004f7af  mov     rbx, rcx
0x18004f7b2  lea     rdi, [rcx+28h]
0x18004f7b6  mov     [rsp+38h+arg_8], rdi
0x18004f7bb  mov     rcx, [rdi]
0x18004f7be  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18004f7c3  test    al, al
0x18004f7c5  jnz     short loc_18004F7E8
0x18004f7c7  mov     rdx, [rbx+38h]
0x18004f7cb  add     rdx, 10h
0x18004f7cf  mov     rcx, [rdi]; this
0x18004f7d2  cmp     qword ptr [rdx], 0
0x18004f7d6  jz      short loc_18004F7DF
0x18004f7d8  call    ?_CancelWithExceptionHolder@_Task_impl_base@details@Concurrency@@QEAA_NAEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@_N@Z; Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &,bool)
0x18004f7dd  jmp     short loc_18004F80C
0x18004f7df  mov     dl, 1; bool
0x18004f7e1  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18004f7e6  jmp     short loc_18004F80C
0x18004f7e8  mov     rcx, rbx
0x18004f7eb  call    ?_Continue@?$_ContinuationTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@XV?$function@$$A6AXV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@U?$integral_constant@_N$0A@@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)
0x18004f7f0  nop
0x18004f7f1  jmp     short loc_18004F7F7
0x18004f7f3  jmp     short loc_18004F7F7
0x18004f7f5  jmp     short $+2
0x18004f7f7  mov     rax, [rsp+38h+arg_8]
0x18004f7fc  mov     rcx, [rax]
0x18004f7ff  add     rcx, 160h
0x18004f806  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18004f80c  mov     rbx, [rsp+38h+arg_10]
0x18004f811  add     rsp, 30h
0x18004f815  pop     rdi
0x18004f816  retn
```
