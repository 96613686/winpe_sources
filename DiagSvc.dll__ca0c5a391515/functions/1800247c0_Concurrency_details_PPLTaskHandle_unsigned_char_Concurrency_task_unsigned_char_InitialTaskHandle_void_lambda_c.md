# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x1800247c0`
- end: `0x180024822`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180022910`
- `0x18002378c`
- `0x1800243a4`
- `0x1800247c0`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180024811`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180024811`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v4 = a1 + 8;
  if ( Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync_::_Init(a1);
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*(_QWORD *)v4 + 352LL));
  }
  else
  {
    LOBYTE(v3) = 1;
    Concurrency::details::_Task_impl_base::_Cancel(*v2, v3);
  }
}

```

## disassembly

```asm
0x1800247c0  mov     [rsp+arg_10], rbx
0x1800247c5  mov     [rsp+arg_0], rcx
0x1800247ca  push    rdi
0x1800247cb  sub     rsp, 30h
0x1800247cf  mov     rbx, rcx
0x1800247d2  lea     rdi, [rcx+8]
0x1800247d6  mov     [rsp+38h+arg_8], rdi
0x1800247db  mov     rcx, [rdi]
0x1800247de  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x1800247e3  test    al, al
0x1800247e5  jnz     short loc_1800247F3
0x1800247e7  mov     dl, 1; bool
0x1800247e9  mov     rcx, [rdi]; this
0x1800247ec  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x1800247f1  jmp     short loc_180024817
0x1800247f3  mov     rcx, rbx
0x1800247f6  call    Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency__details___TypeSelectorNoAsync____Init
0x1800247fb  nop
0x1800247fc  jmp     short loc_180024802
0x1800247fe  jmp     short loc_180024802
0x180024800  jmp     short $+2
0x180024802  mov     rax, [rsp+38h+arg_8]
0x180024807  mov     rcx, [rax]
0x18002480a  add     rcx, 160h
0x180024811  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180024817  mov     rbx, [rsp+38h+arg_10]
0x18002481c  add     rsp, 30h
0x180024820  pop     rdi
0x180024821  retn
```
