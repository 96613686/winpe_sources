# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_2d4475b4d0b3a56227f9ed241cb4981d__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x180031400`
- end: `0x180031462`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_2d4475b4d0b3a56227f9ed241cb4981d__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002e890`
- `0x18002f6ac`
- `0x180030768`
- `0x180031400`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180031451`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180031451`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_2d4475b4d0b3a56227f9ed241cb4981d__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
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
      Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_2d4475b4d0b3a56227f9ed241cb4981d__Concurrency::details::_TypeSelectorNoAsync_::_Init(a1);
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
0x180031400  mov     [rsp+arg_10], rbx
0x180031405  mov     [rsp+arg_0], rcx
0x18003140a  push    rdi
0x18003140b  sub     rsp, 30h
0x18003140f  mov     rbx, rcx
0x180031412  lea     rdi, [rcx+8]
0x180031416  mov     [rsp+38h+arg_8], rdi
0x18003141b  mov     rcx, [rdi]
0x18003141e  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x180031423  test    al, al
0x180031425  jnz     short loc_180031433
0x180031427  mov     dl, 1; bool
0x180031429  mov     rcx, [rdi]; this
0x18003142c  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x180031431  jmp     short loc_180031457
0x180031433  mov     rcx, rbx
0x180031436  call    Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_2d4475b4d0b3a56227f9ed241cb4981d__Concurrency__details___TypeSelectorNoAsync____Init
0x18003143b  nop
0x18003143c  jmp     short loc_180031442
0x18003143e  jmp     short loc_180031442
0x180031440  jmp     short $+2
0x180031442  mov     rax, [rsp+38h+arg_8]
0x180031447  mov     rcx, [rax]
0x18003144a  add     rcx, 160h
0x180031451  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180031457  mov     rbx, [rsp+38h+arg_10]
0x18003145c  add     rsp, 30h
0x180031460  pop     rdi
0x180031461  retn
```
