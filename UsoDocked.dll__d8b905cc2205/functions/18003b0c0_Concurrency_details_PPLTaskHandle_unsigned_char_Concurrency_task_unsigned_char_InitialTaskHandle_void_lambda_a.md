# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_afc3e0c581ebf1dec6a4111471076a98__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x18003b0c0`
- end: `0x18003b1f0`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_afc3e0c581ebf1dec6a4111471076a98__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180039300`
- `0x180039764`
- `0x18003a3b8`
- `0x18003b0c0`
- `0x180071010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003b177`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003b177`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b18f`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b18f`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b167`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b167`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b1d9`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b1d9`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_afc3e0c581ebf1dec6a4111471076a98__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
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
    v10[0] = off_180072CA8;
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
0x18003b0c0  mov     [rsp+arg_0], rcx
0x18003b0c5  push    rbx
0x18003b0c6  push    rsi
0x18003b0c7  push    rdi
0x18003b0c8  push    r14
0x18003b0ca  push    r15
0x18003b0cc  sub     rsp, 0C0h
0x18003b0d3  mov     rdi, rcx
0x18003b0d6  lea     rbx, [rcx+8]
0x18003b0da  mov     [rsp+0E8h+arg_8], rbx
0x18003b0e2  mov     rcx, [rbx]
0x18003b0e5  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18003b0ea  test    al, al
0x18003b0ec  jnz     short loc_18003B113
0x18003b0ee  mov     rcx, [rbx]
0x18003b0f1  mov     rax, [rcx]
0x18003b0f4  lea     rdx, [rcx+10h]
0x18003b0f8  mov     [rsp+0E8h+var_C8], rdx
0x18003b0fd  xor     r9d, r9d
0x18003b100  xor     r8d, r8d
0x18003b103  mov     dl, 1
0x18003b105  mov     rax, [rax+8]
0x18003b109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b10e  jmp     loc_18003B1DF
0x18003b113  mov     r15, [rbx]
0x18003b116  lea     rax, off_180072CA8
0x18003b11d  mov     [rsp+0E8h+var_A8], rax
0x18003b122  mov     rax, [rdi+18h]
0x18003b126  mov     [rsp+0E8h+var_A0], rax
0x18003b12b  lea     rax, [rsp+0E8h+var_A8]
0x18003b130  mov     [rsp+0E8h+var_70], rax
0x18003b135  lea     rdx, [rsp+0E8h+var_A8]
0x18003b13a  lea     rcx, [rsp+0E8h+var_68]
0x18003b142  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x18003b147  mov     rdi, rax
0x18003b14a  mov     [rsp+0E8h+arg_10], rax
0x18003b152  mov     rsi, [rbx]
0x18003b155  add     rsi, 160h
0x18003b15c  mov     [rsp+0E8h+arg_18], rsi
0x18003b164  mov     rcx, rsi
0x18003b167  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18003b16d  nop
0x18003b16e  mov     rcx, [rdi+38h]
0x18003b172  test    rcx, rcx
0x18003b175  jnz     short loc_18003B17D
0x18003b177  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003b17d  mov     rax, [rcx]
0x18003b180  mov     rax, [rax+10h]
0x18003b184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b189  mov     r14b, al
0x18003b18c  mov     rcx, rsi
0x18003b18f  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18003b195  nop
0x18003b196  mov     rcx, [rdi+38h]
0x18003b19a  test    rcx, rcx
0x18003b19d  jz      short loc_18003B1B9
0x18003b19f  mov     rax, [rcx]
0x18003b1a2  cmp     rcx, rdi
0x18003b1a5  setnz   dl
0x18003b1a8  mov     rax, [rax+20h]
0x18003b1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1b1  mov     qword ptr [rdi+38h], 0
0x18003b1b9  mov     dl, r14b
0x18003b1bc  mov     rcx, r15; this
0x18003b1bf  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18003b1c4  nop
0x18003b1c5  jmp     short loc_18003B1CF
0x18003b1c7  mov     rbx, [rsp+0E8h+arg_8]
0x18003b1cf  mov     rcx, [rbx]
0x18003b1d2  add     rcx, 160h
0x18003b1d9  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18003b1df  add     rsp, 0C0h
0x18003b1e6  pop     r15
0x18003b1e8  pop     r14
0x18003b1ea  pop     rdi
0x18003b1eb  pop     rsi
0x18003b1ec  pop     rbx
0x18003b1ed  retn
0x18003b1ee  jmp     short loc_18003B1C7
```
