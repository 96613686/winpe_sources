# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_10afeadc2437d204173cbd84f6b8e4eb__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x18003abc0`
- end: `0x18003acf0`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_10afeadc2437d204173cbd84f6b8e4eb__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180039300`
- `0x180039764`
- `0x18003a3b8`
- `0x18003abc0`
- `0x180071010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003ac77`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003ac77`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003ac8f`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003ac8f`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003ac67`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003ac67`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003acd9`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003acd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_10afeadc2437d204173cbd84f6b8e4eb__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
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
  __int64 v10; // rcx
  __int64 v11; // rdx
  Concurrency::details::_Task_impl_base *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int128 v15; // [rsp+30h] [rbp-B8h] BYREF
  _QWORD v16[8]; // [rsp+40h] [rbp-A8h] BYREF
  char v17[104]; // [rsp+80h] [rbp-68h] BYREF
  Concurrency::details::_Task_impl_base **v19; // [rsp+F8h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v19 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    try
    {
      v4 = *v2;
      v16[0] = off_180072D38;
      v16[1] = *(_QWORD *)(a1 + 24);
      v16[7] = v16;
      v5 = Concurrency::_Init_func_transformer<void>::_Perform(v17, v16);
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
    }
    catch ( Concurrency::task_canceled )
    {
      v10 = *(_QWORD *)(a1 + 8);
      v11 = v10 + 16;
      LOBYTE(v11) = 1;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v10 + 8LL))(
        v10,
        v11,
        0,
        0,
        v10 + 16);
      v2 = v19;
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v13 = *(_QWORD *)(a1 + 8);
      v14 = v13 + 16;
      LOBYTE(v14) = 1;
      guard_dispatch_icall_thunk_10345483385596137414(v13, v14, 0, 0, v13 + 16);
      v2 = v19;
    }
    catch ( ... )
    {
      v12 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v15 = 0;
      __ExceptionPtrCreate(&v15);
      __ExceptionPtrCurrentException(&v15);
      Concurrency::details::_Task_impl_base::_CancelWithException(v12, (const struct std::exception_ptr *)&v15);
      __ExceptionPtrDestroy(&v15);
      v2 = v19;
    }
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
0x18003abc0  mov     [rsp+arg_0], rcx
0x18003abc5  push    rbx
0x18003abc6  push    rsi
0x18003abc7  push    rdi
0x18003abc8  push    r14
0x18003abca  push    r15
0x18003abcc  sub     rsp, 0C0h
0x18003abd3  mov     rdi, rcx
0x18003abd6  lea     rbx, [rcx+8]
0x18003abda  mov     [rsp+0E8h+arg_8], rbx
0x18003abe2  mov     rcx, [rbx]
0x18003abe5  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18003abea  test    al, al
0x18003abec  jnz     short loc_18003AC13
0x18003abee  mov     rcx, [rbx]
0x18003abf1  mov     rax, [rcx]
0x18003abf4  lea     rdx, [rcx+10h]
0x18003abf8  mov     [rsp+0E8h+var_C8], rdx
0x18003abfd  xor     r9d, r9d
0x18003ac00  xor     r8d, r8d
0x18003ac03  mov     dl, 1
0x18003ac05  mov     rax, [rax+8]
0x18003ac09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac0e  jmp     loc_18003ACDF
0x18003ac13  mov     r15, [rbx]
0x18003ac16  lea     rax, off_180072D38
0x18003ac1d  mov     [rsp+0E8h+var_A8], rax
0x18003ac22  mov     rax, [rdi+18h]
0x18003ac26  mov     [rsp+0E8h+var_A0], rax
0x18003ac2b  lea     rax, [rsp+0E8h+var_A8]
0x18003ac30  mov     [rsp+0E8h+var_70], rax
0x18003ac35  lea     rdx, [rsp+0E8h+var_A8]
0x18003ac3a  lea     rcx, [rsp+0E8h+var_68]
0x18003ac42  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x18003ac47  mov     rdi, rax
0x18003ac4a  mov     [rsp+0E8h+arg_10], rax
0x18003ac52  mov     rsi, [rbx]
0x18003ac55  add     rsi, 160h
0x18003ac5c  mov     [rsp+0E8h+arg_18], rsi
0x18003ac64  mov     rcx, rsi
0x18003ac67  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18003ac6d  nop
0x18003ac6e  mov     rcx, [rdi+38h]
0x18003ac72  test    rcx, rcx
0x18003ac75  jnz     short loc_18003AC7D
0x18003ac77  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003ac7d  mov     rax, [rcx]
0x18003ac80  mov     rax, [rax+10h]
0x18003ac84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac89  mov     r14b, al
0x18003ac8c  mov     rcx, rsi
0x18003ac8f  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18003ac95  nop
0x18003ac96  mov     rcx, [rdi+38h]
0x18003ac9a  test    rcx, rcx
0x18003ac9d  jz      short loc_18003ACB9
0x18003ac9f  mov     rax, [rcx]
0x18003aca2  cmp     rcx, rdi
0x18003aca5  setnz   dl
0x18003aca8  mov     rax, [rax+20h]
0x18003acac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acb1  mov     qword ptr [rdi+38h], 0
0x18003acb9  mov     dl, r14b
0x18003acbc  mov     rcx, r15; this
0x18003acbf  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18003acc4  nop
0x18003acc5  jmp     short loc_18003ACCF
0x18003acc7  mov     rbx, [rsp+0E8h+arg_8]
0x18003accf  mov     rcx, [rbx]
0x18003acd2  add     rcx, 160h
0x18003acd9  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18003acdf  add     rsp, 0C0h
0x18003ace6  pop     r15
0x18003ace8  pop     r14
0x18003acea  pop     rdi
0x18003aceb  pop     rsi
0x18003acec  pop     rbx
0x18003aced  retn
0x18003acee  jmp     short loc_18003ACC7
```
