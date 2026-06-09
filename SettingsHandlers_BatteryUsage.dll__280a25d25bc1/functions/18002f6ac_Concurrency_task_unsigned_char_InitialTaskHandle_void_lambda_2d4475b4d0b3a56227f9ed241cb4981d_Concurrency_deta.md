# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_2d4475b4d0b3a56227f9ed241cb4981d__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x18002f6ac`
- end: `0x18002f76e`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_2d4475b4d0b3a56227f9ed241cb4981d__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031400`

## callees

- `0x18002be78`
- `0x18002f428`
- `0x18002f6ac`
- `0x18002fc10`
- `0x18005a010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002f711`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002f711`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002f726`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002f726`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_2d4475b4d0b3a56227f9ed241cb4981d__Concurrency::details::_TypeSelectorNoAsync_::_Init(
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
  v7[0] = off_18005F0C8;
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
0x18002f6ac  mov     [rsp+arg_8], rbx
0x18002f6b1  push    rbp
0x18002f6b2  push    rsi
0x18002f6b3  push    rdi
0x18002f6b4  sub     rsp, 0A0h
0x18002f6bb  mov     rbx, rcx
0x18002f6be  mov     rsi, [rcx+8]
0x18002f6c2  lea     rax, off_18005F0C8
0x18002f6c9  mov     [rsp+0B8h+var_98], rax
0x18002f6ce  mov     rax, [rcx+18h]
0x18002f6d2  mov     [rsp+0B8h+var_90], rax
0x18002f6d7  lea     rax, [rsp+0B8h+var_98]
0x18002f6dc  mov     [rsp+0B8h+var_60], rax
0x18002f6e1  lea     rdx, [rsp+0B8h+var_98]
0x18002f6e6  lea     rcx, [rsp+0B8h+var_58]
0x18002f6eb  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x18002f6f0  mov     rdi, rax
0x18002f6f3  mov     [rsp+0B8h+arg_0], rax
0x18002f6fb  mov     rbx, [rbx+8]
0x18002f6ff  add     rbx, 160h
0x18002f706  mov     [rsp+0B8h+arg_10], rbx
0x18002f70e  mov     rcx, rbx
0x18002f711  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18002f717  nop
0x18002f718  mov     rcx, rdi
0x18002f71b  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18002f720  mov     bpl, al
0x18002f723  mov     rcx, rbx
0x18002f726  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18002f72c  nop
0x18002f72d  mov     rcx, [rdi+38h]
0x18002f731  test    rcx, rcx
0x18002f734  jz      short loc_18002F750
0x18002f736  mov     rdx, [rcx]
0x18002f739  mov     rax, [rdx+20h]
0x18002f73d  cmp     rcx, rdi
0x18002f740  setnz   dl
0x18002f743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f748  mov     qword ptr [rdi+38h], 0
0x18002f750  mov     dl, bpl
0x18002f753  mov     rcx, rsi; this
0x18002f756  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18002f75b  mov     rbx, [rsp+0B8h+arg_8]
0x18002f763  add     rsp, 0A0h
0x18002f76a  pop     rdi
0x18002f76b  pop     rsi
0x18002f76c  pop     rbp
0x18002f76d  retn
```
