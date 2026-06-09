# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_0bcac2e3b18903b10fee974fc96716ce__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x180033c20`
- end: `0x180033c82`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_0bcac2e3b18903b10fee974fc96716ce__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002e890`
- `0x180030768`
- `0x180032f24`
- `0x180033c20`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180033c71`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180033c71`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_0bcac2e3b18903b10fee974fc96716ce__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v3 = a1 + 8;
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_0bcac2e3b18903b10fee974fc96716ce__Concurrency::details::_TypeSelectorNoAsync_::_Init(a1);
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
0x180033c20  mov     [rsp+arg_10], rbx
0x180033c25  mov     [rsp+arg_0], rcx
0x180033c2a  push    rdi
0x180033c2b  sub     rsp, 30h
0x180033c2f  mov     rbx, rcx
0x180033c32  lea     rdi, [rcx+8]
0x180033c36  mov     [rsp+38h+arg_8], rdi
0x180033c3b  mov     rcx, [rdi]
0x180033c3e  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x180033c43  test    al, al
0x180033c45  jnz     short loc_180033C53
0x180033c47  mov     dl, 1; bool
0x180033c49  mov     rcx, [rdi]; this
0x180033c4c  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x180033c51  jmp     short loc_180033C77
0x180033c53  mov     rcx, rbx
0x180033c56  call    Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_0bcac2e3b18903b10fee974fc96716ce__Concurrency__details___TypeSelectorNoAsync____Init
0x180033c5b  nop
0x180033c5c  jmp     short loc_180033C62
0x180033c5e  jmp     short loc_180033C62
0x180033c60  jmp     short $+2
0x180033c62  mov     rax, [rsp+38h+arg_8]
0x180033c67  mov     rcx, [rax]
0x180033c6a  add     rcx, 160h
0x180033c71  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180033c77  mov     rbx, [rsp+38h+arg_10]
0x180033c7c  add     rsp, 30h
0x180033c80  pop     rdi
0x180033c81  retn
```
