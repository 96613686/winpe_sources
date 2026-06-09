# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_0bcac2e3b18903b10fee974fc96716ce__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x180032f24`
- end: `0x180032fe6`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_0bcac2e3b18903b10fee974fc96716ce__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033c20`

## callees

- `0x18002be78`
- `0x18002f428`
- `0x18002fc10`
- `0x180032f24`
- `0x18005a010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180032f89`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180032f89`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180032f9e`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180032f9e`

## pseudocode

```c
__int64 __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_0bcac2e3b18903b10fee974fc96716ce__Concurrency::details::_TypeSelectorNoAsync_::_Init(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rsi
  __int64 v3; // rdi
  __int64 *v4; // rcx
  __int64 v5; // rdx
  _QWORD v7[8]; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v8[88]; // [rsp+60h] [rbp-58h] BYREF
  Concurrency::details::_TaskEventLogger *v9; // [rsp+D0h] [rbp+18h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
  v7[0] = off_18005F5E0;
  v7[1] = *(_QWORD *)(a1 + 24);
  v7[7] = v7;
  v3 = Concurrency::_Init_func_transformer<void>::_Perform(v8, v7);
  v9 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v9);
  std::_Func_class<void,>::operator()(v3);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v9);
  v4 = *(__int64 **)(v3 + 56);
  if ( v4 )
  {
    v5 = *v4;
    LOBYTE(v5) = v4 != (__int64 *)v3;
    (*(void (__fastcall **)(__int64 *, __int64))(*v4 + 32))(v4, v5);
    *(_QWORD *)(v3 + 56) = 0;
  }
  return Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
}

```

## disassembly

```asm
0x180032f24  mov     [rsp+arg_8], rbx
0x180032f29  push    rbp
0x180032f2a  push    rsi
0x180032f2b  push    rdi
0x180032f2c  sub     rsp, 0A0h
0x180032f33  mov     rbx, rcx
0x180032f36  mov     rsi, [rcx+8]
0x180032f3a  lea     rax, off_18005F5E0
0x180032f41  mov     [rsp+0B8h+var_98], rax
0x180032f46  mov     rax, [rcx+18h]
0x180032f4a  mov     [rsp+0B8h+var_90], rax
0x180032f4f  lea     rax, [rsp+0B8h+var_98]
0x180032f54  mov     [rsp+0B8h+var_60], rax
0x180032f59  lea     rdx, [rsp+0B8h+var_98]
0x180032f5e  lea     rcx, [rsp+0B8h+var_58]
0x180032f63  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x180032f68  mov     rdi, rax
0x180032f6b  mov     [rsp+0B8h+arg_0], rax
0x180032f73  mov     rbx, [rbx+8]
0x180032f77  add     rbx, 160h
0x180032f7e  mov     [rsp+0B8h+arg_10], rbx
0x180032f86  mov     rcx, rbx
0x180032f89  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180032f8f  nop
0x180032f90  mov     rcx, rdi
0x180032f93  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180032f98  mov     bpl, al
0x180032f9b  mov     rcx, rbx
0x180032f9e  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180032fa4  nop
0x180032fa5  mov     rcx, [rdi+38h]
0x180032fa9  test    rcx, rcx
0x180032fac  jz      short loc_180032FC8
0x180032fae  mov     rdx, [rcx]
0x180032fb1  mov     rax, [rdx+20h]
0x180032fb5  cmp     rcx, rdi
0x180032fb8  setnz   dl
0x180032fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fc0  mov     qword ptr [rdi+38h], 0
0x180032fc8  mov     dl, bpl
0x180032fcb  mov     rcx, rsi; this
0x180032fce  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x180032fd3  mov     rbx, [rsp+0B8h+arg_8]
0x180032fdb  add     rsp, 0A0h
0x180032fe2  pop     rdi
0x180032fe3  pop     rsi
0x180032fe4  pop     rbp
0x180032fe5  retn
```
