# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::invoke(void)

- ea: `0x18001cdb0`
- end: `0x18001ce27`
- name: `?invoke@?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XV?$function@$$A6AXV?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEBAXXZ`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001cdb0`
- `0x18001d9b4`
- `0x18001db5c`
- `0x1800218b8`
- `0x1800218e4`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001ce16`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001ce16`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  Concurrency::details::_Task_impl_base *v3; // rcx
  __int64 v4; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 40);
  v4 = a1 + 40;
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 40)) )
  {
    Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(a1);
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*(_QWORD *)v4 + 352LL));
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
0x18001cdb0  mov     [rsp+arg_10], rbx
0x18001cdb5  mov     [rsp+arg_0], rcx
0x18001cdba  push    rdi
0x18001cdbb  sub     rsp, 30h
0x18001cdbf  mov     rbx, rcx
0x18001cdc2  lea     rdi, [rcx+28h]
0x18001cdc6  mov     [rsp+38h+arg_8], rdi
0x18001cdcb  mov     rcx, [rdi]
0x18001cdce  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18001cdd3  test    al, al
0x18001cdd5  jnz     short loc_18001CDF8
0x18001cdd7  mov     rdx, [rbx+38h]
0x18001cddb  add     rdx, 10h
0x18001cddf  mov     rcx, [rdi]; this
0x18001cde2  cmp     qword ptr [rdx], 0
0x18001cde6  jz      short loc_18001CDEF
0x18001cde8  call    ?_CancelWithExceptionHolder@_Task_impl_base@details@Concurrency@@QEAA_NAEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@_N@Z; Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &,bool)
0x18001cded  jmp     short loc_18001CE1C
0x18001cdef  mov     dl, 1; bool
0x18001cdf1  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18001cdf6  jmp     short loc_18001CE1C
0x18001cdf8  mov     rcx, rbx
0x18001cdfb  call    ?_Continue@?$_ContinuationTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XV?$function@$$A6AXV?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@QEBAXU?$integral_constant@_N$00@std@@U_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync)
0x18001ce00  nop
0x18001ce01  jmp     short loc_18001CE07
0x18001ce03  jmp     short loc_18001CE07
0x18001ce05  jmp     short $+2
0x18001ce07  mov     rax, [rsp+38h+arg_8]
0x18001ce0c  mov     rcx, [rax]
0x18001ce0f  add     rcx, 160h
0x18001ce16  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18001ce1c  mov     rbx, [rsp+38h+arg_10]
0x18001ce21  add     rsp, 30h
0x18001ce25  pop     rdi
0x18001ce26  retn
```
