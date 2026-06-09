# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x18002378c`
- end: `0x18002384e`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800247c0`

## callees

- `0x18001e760`
- `0x18002335c`
- `0x18002378c`
- `0x180023b78`
- `0x180027010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800237f1`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800237f1`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180023806`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180023806`

## pseudocode

```c
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync_::_Init(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rsi
  __int64 v3; // rdi
  char v4; // bp
  __int64 *v5; // rcx
  __int64 v6; // rdx
  _QWORD v7[8]; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v8[88]; // [rsp+60h] [rbp-58h] BYREF
  Concurrency::details::_TaskEventLogger *v9; // [rsp+D0h] [rbp+18h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
  v7[0] = off_180028FA0;
  v7[1] = *(_QWORD *)(a1 + 24);
  v7[7] = v7;
  v3 = Concurrency::_Init_func_transformer<void>::_Perform(v8, v7);
  v9 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v9);
  v4 = std::_Func_class<void,>::operator()(v3);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v9);
  v5 = *(__int64 **)(v3 + 56);
  if ( v5 )
  {
    v6 = *v5;
    LOBYTE(v6) = v5 != (__int64 *)v3;
    (*(void (__fastcall **)(__int64 *, __int64))(*v5 + 32))(v5, v6);
    *(_QWORD *)(v3 + 56) = 0;
  }
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2, v4);
}

```

## disassembly

```asm
0x18002378c  mov     [rsp+arg_8], rbx
0x180023791  push    rbp
0x180023792  push    rsi
0x180023793  push    rdi
0x180023794  sub     rsp, 0A0h
0x18002379b  mov     rbx, rcx
0x18002379e  mov     rsi, [rcx+8]
0x1800237a2  lea     rax, off_180028FA0
0x1800237a9  mov     [rsp+0B8h+var_98], rax
0x1800237ae  mov     rax, [rcx+18h]
0x1800237b2  mov     [rsp+0B8h+var_90], rax
0x1800237b7  lea     rax, [rsp+0B8h+var_98]
0x1800237bc  mov     [rsp+0B8h+var_60], rax
0x1800237c1  lea     rdx, [rsp+0B8h+var_98]
0x1800237c6  lea     rcx, [rsp+0B8h+var_58]
0x1800237cb  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x1800237d0  mov     rdi, rax
0x1800237d3  mov     [rsp+0B8h+arg_0], rax
0x1800237db  mov     rbx, [rbx+8]
0x1800237df  add     rbx, 160h
0x1800237e6  mov     [rsp+0B8h+arg_10], rbx
0x1800237ee  mov     rcx, rbx
0x1800237f1  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1800237f7  nop
0x1800237f8  mov     rcx, rdi
0x1800237fb  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180023800  mov     bpl, al
0x180023803  mov     rcx, rbx
0x180023806  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18002380c  nop
0x18002380d  mov     rcx, [rdi+38h]
0x180023811  test    rcx, rcx
0x180023814  jz      short loc_180023830
0x180023816  mov     rdx, [rcx]
0x180023819  mov     rax, [rdx+20h]
0x18002381d  cmp     rcx, rdi
0x180023820  setnz   dl
0x180023823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023828  mov     qword ptr [rdi+38h], 0
0x180023830  mov     dl, bpl
0x180023833  mov     rcx, rsi; this
0x180023836  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18002383b  mov     rbx, [rsp+0B8h+arg_8]
0x180023843  add     rsp, 0A0h
0x18002384a  pop     rdi
0x18002384b  pop     rsi
0x18002384c  pop     rbp
0x18002384d  retn
```
