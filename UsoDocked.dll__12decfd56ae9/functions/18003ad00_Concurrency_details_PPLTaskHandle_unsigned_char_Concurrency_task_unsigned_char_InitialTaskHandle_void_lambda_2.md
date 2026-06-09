# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_2fa1bf9d600565b0edca5351f702bc2a__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x18003ad00`
- end: `0x18003ae30`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_2fa1bf9d600565b0edca5351f702bc2a__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180039300`
- `0x180039764`
- `0x18003a3b8`
- `0x18003ad00`
- `0x180071010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003adb7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003adb7`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003adcf`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003adcf`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003ada7`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003ada7`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003ae19`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003ae19`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_2fa1bf9d600565b0edca5351f702bc2a__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rbx
  __int64 v3; // rdx
  Concurrency::details::_Task_impl_base *v4; // r15
  __int64 v5; // rdi
  Concurrency::details::_TaskEventLogger *v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  _QWORD v10[8]; // [rsp+40h] [rbp-A8h] BYREF
  char v11[104]; // [rsp+80h] [rbp-68h] BYREF

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    v4 = *v2;
    v10[0] = off_180072CD8;
    v10[1] = *(_QWORD *)(a1 + 24);
    v10[7] = v10;
    v5 = Concurrency::_Init_func_transformer<void>::_Perform(v11, v10);
    v6 = (Concurrency::details::_Task_impl_base *)((char *)*v2 + 352);
    Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v6);
    v7 = *(_QWORD *)(v5 + 56);
    if ( !v7 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v6);
    v9 = *(_QWORD *)(v5 + 56);
    if ( v9 )
    {
      LOBYTE(v8) = v9 != v5;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, v8);
      *(_QWORD *)(v5 + 56) = 0;
    }
    Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v4);
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_Task_impl_base *)((char *)*v2 + 352));
  }
  else
  {
    v3 = (__int64)*v2 + 16;
    LOBYTE(v3) = 1;
    (*(void (__fastcall **)(Concurrency::details::_Task_impl_base *, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)*v2 + 8LL))(
      *v2,
      v3,
      0,
      0,
      (__int64)*v2 + 16);
  }
}

```

## disassembly

```asm
0x18003ad00  mov     [rsp+arg_0], rcx
0x18003ad05  push    rbx
0x18003ad06  push    rsi
0x18003ad07  push    rdi
0x18003ad08  push    r14
0x18003ad0a  push    r15
0x18003ad0c  sub     rsp, 0C0h
0x18003ad13  mov     rdi, rcx
0x18003ad16  lea     rbx, [rcx+8]
0x18003ad1a  mov     [rsp+0E8h+arg_8], rbx
0x18003ad22  mov     rcx, [rbx]
0x18003ad25  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18003ad2a  test    al, al
0x18003ad2c  jnz     short loc_18003AD53
0x18003ad2e  mov     rcx, [rbx]
0x18003ad31  mov     rax, [rcx]
0x18003ad34  lea     rdx, [rcx+10h]
0x18003ad38  mov     [rsp+0E8h+var_C8], rdx
0x18003ad3d  xor     r9d, r9d
0x18003ad40  xor     r8d, r8d
0x18003ad43  mov     dl, 1
0x18003ad45  mov     rax, [rax+8]
0x18003ad49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad4e  jmp     loc_18003AE1F
0x18003ad53  mov     r15, [rbx]
0x18003ad56  lea     rax, off_180072CD8
0x18003ad5d  mov     [rsp+0E8h+var_A8], rax
0x18003ad62  mov     rax, [rdi+18h]
0x18003ad66  mov     [rsp+0E8h+var_A0], rax
0x18003ad6b  lea     rax, [rsp+0E8h+var_A8]
0x18003ad70  mov     [rsp+0E8h+var_70], rax
0x18003ad75  lea     rdx, [rsp+0E8h+var_A8]
0x18003ad7a  lea     rcx, [rsp+0E8h+var_68]
0x18003ad82  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x18003ad87  mov     rdi, rax
0x18003ad8a  mov     [rsp+0E8h+arg_10], rax
0x18003ad92  mov     rsi, [rbx]
0x18003ad95  add     rsi, 160h
0x18003ad9c  mov     [rsp+0E8h+arg_18], rsi
0x18003ada4  mov     rcx, rsi
0x18003ada7  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18003adad  nop
0x18003adae  mov     rcx, [rdi+38h]
0x18003adb2  test    rcx, rcx
0x18003adb5  jnz     short loc_18003ADBD
0x18003adb7  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003adbd  mov     rax, [rcx]
0x18003adc0  mov     rax, [rax+10h]
0x18003adc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003adc9  mov     r14b, al
0x18003adcc  mov     rcx, rsi
0x18003adcf  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18003add5  nop
0x18003add6  mov     rcx, [rdi+38h]
0x18003adda  test    rcx, rcx
0x18003addd  jz      short loc_18003ADF9
0x18003addf  mov     rax, [rcx]
0x18003ade2  cmp     rcx, rdi
0x18003ade5  setnz   dl
0x18003ade8  mov     rax, [rax+20h]
0x18003adec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003adf1  mov     qword ptr [rdi+38h], 0
0x18003adf9  mov     dl, r14b
0x18003adfc  mov     rcx, r15; this
0x18003adff  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18003ae04  nop
0x18003ae05  jmp     short loc_18003AE0F
0x18003ae07  mov     rbx, [rsp+0E8h+arg_8]
0x18003ae0f  mov     rcx, [rbx]
0x18003ae12  add     rcx, 160h
0x18003ae19  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18003ae1f  add     rsp, 0C0h
0x18003ae26  pop     r15
0x18003ae28  pop     r14
0x18003ae2a  pop     rdi
0x18003ae2b  pop     rsi
0x18003ae2c  pop     rbx
0x18003ae2d  retn
0x18003ae2e  jmp     short loc_18003AE07
```
