# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_90c90e21c1f6974373c346806996f986__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x18003ae40`
- end: `0x18003af70`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_90c90e21c1f6974373c346806996f986__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180039300`
- `0x180039764`
- `0x18003a3b8`
- `0x18003ae40`
- `0x180071010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003aef7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003aef7`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003af0f`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003af0f`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003aee7`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003aee7`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003af59`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003af59`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_90c90e21c1f6974373c346806996f986__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
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
    v10[0] = off_180072D68;
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
0x18003ae40  mov     [rsp+arg_0], rcx
0x18003ae45  push    rbx
0x18003ae46  push    rsi
0x18003ae47  push    rdi
0x18003ae48  push    r14
0x18003ae4a  push    r15
0x18003ae4c  sub     rsp, 0C0h
0x18003ae53  mov     rdi, rcx
0x18003ae56  lea     rbx, [rcx+8]
0x18003ae5a  mov     [rsp+0E8h+arg_8], rbx
0x18003ae62  mov     rcx, [rbx]
0x18003ae65  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18003ae6a  test    al, al
0x18003ae6c  jnz     short loc_18003AE93
0x18003ae6e  mov     rcx, [rbx]
0x18003ae71  mov     rax, [rcx]
0x18003ae74  lea     rdx, [rcx+10h]
0x18003ae78  mov     [rsp+0E8h+var_C8], rdx
0x18003ae7d  xor     r9d, r9d
0x18003ae80  xor     r8d, r8d
0x18003ae83  mov     dl, 1
0x18003ae85  mov     rax, [rax+8]
0x18003ae89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae8e  jmp     loc_18003AF5F
0x18003ae93  mov     r15, [rbx]
0x18003ae96  lea     rax, off_180072D68
0x18003ae9d  mov     [rsp+0E8h+var_A8], rax
0x18003aea2  mov     rax, [rdi+18h]
0x18003aea6  mov     [rsp+0E8h+var_A0], rax
0x18003aeab  lea     rax, [rsp+0E8h+var_A8]
0x18003aeb0  mov     [rsp+0E8h+var_70], rax
0x18003aeb5  lea     rdx, [rsp+0E8h+var_A8]
0x18003aeba  lea     rcx, [rsp+0E8h+var_68]
0x18003aec2  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x18003aec7  mov     rdi, rax
0x18003aeca  mov     [rsp+0E8h+arg_10], rax
0x18003aed2  mov     rsi, [rbx]
0x18003aed5  add     rsi, 160h
0x18003aedc  mov     [rsp+0E8h+arg_18], rsi
0x18003aee4  mov     rcx, rsi
0x18003aee7  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18003aeed  nop
0x18003aeee  mov     rcx, [rdi+38h]
0x18003aef2  test    rcx, rcx
0x18003aef5  jnz     short loc_18003AEFD
0x18003aef7  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003aefd  mov     rax, [rcx]
0x18003af00  mov     rax, [rax+10h]
0x18003af04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af09  mov     r14b, al
0x18003af0c  mov     rcx, rsi
0x18003af0f  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18003af15  nop
0x18003af16  mov     rcx, [rdi+38h]
0x18003af1a  test    rcx, rcx
0x18003af1d  jz      short loc_18003AF39
0x18003af1f  mov     rax, [rcx]
0x18003af22  cmp     rcx, rdi
0x18003af25  setnz   dl
0x18003af28  mov     rax, [rax+20h]
0x18003af2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af31  mov     qword ptr [rdi+38h], 0
0x18003af39  mov     dl, r14b
0x18003af3c  mov     rcx, r15; this
0x18003af3f  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18003af44  nop
0x18003af45  jmp     short loc_18003AF4F
0x18003af47  mov     rbx, [rsp+0E8h+arg_8]
0x18003af4f  mov     rcx, [rbx]
0x18003af52  add     rcx, 160h
0x18003af59  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18003af5f  add     rsp, 0C0h
0x18003af66  pop     r15
0x18003af68  pop     r14
0x18003af6a  pop     rdi
0x18003af6b  pop     rsi
0x18003af6c  pop     rbx
0x18003af6d  retn
0x18003af6e  jmp     short loc_18003AF47
```
