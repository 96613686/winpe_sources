# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x180024750`
- end: `0x1800247b2`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180022910`
- `0x1800236c4`
- `0x1800243a4`
- `0x180024750`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800247a1`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800247a1`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v4 = a1 + 8;
  if ( Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync_::_Init(a1);
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
0x180024750  mov     [rsp+arg_10], rbx
0x180024755  mov     [rsp+arg_0], rcx
0x18002475a  push    rdi
0x18002475b  sub     rsp, 30h
0x18002475f  mov     rbx, rcx
0x180024762  lea     rdi, [rcx+8]
0x180024766  mov     [rsp+38h+arg_8], rdi
0x18002476b  mov     rcx, [rdi]
0x18002476e  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x180024773  test    al, al
0x180024775  jnz     short loc_180024783
0x180024777  mov     dl, 1; bool
0x180024779  mov     rcx, [rdi]; this
0x18002477c  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x180024781  jmp     short loc_1800247A7
0x180024783  mov     rcx, rbx
0x180024786  call    Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency__details___TypeSelectorNoAsync____Init
0x18002478b  nop
0x18002478c  jmp     short loc_180024792
0x18002478e  jmp     short loc_180024792
0x180024790  jmp     short $+2
0x180024792  mov     rax, [rsp+38h+arg_8]
0x180024797  mov     rcx, [rax]
0x18002479a  add     rcx, 160h
0x1800247a1  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x1800247a7  mov     rbx, [rsp+38h+arg_10]
0x1800247ac  add     rsp, 30h
0x1800247b0  pop     rdi
0x1800247b1  retn
```
