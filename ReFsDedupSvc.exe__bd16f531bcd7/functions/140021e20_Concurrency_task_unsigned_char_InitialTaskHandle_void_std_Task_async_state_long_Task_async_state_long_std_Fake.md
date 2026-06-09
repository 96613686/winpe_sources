# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__std::_Task_async_state_long_::_Task_async_state_long__std::_Fake_no_copy_callable_adapter__Windows::FileSystem::ReFs::DedupScrubTaskHandler::Start_::_3_::_lambda_1______::_2_::_lambda_1__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x140021e20`
- end: `0x140021eef`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__std::_Task_async_state_long_::_Task_async_state_long__std::_Fake_no_copy_callable_adapter__Windows::FileSystem::ReFs::DedupScrubTaskHandler::Start_::_3_::_lambda_1______::_2_::_lambda_1__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140021f60`

## callees

- `0x14001c9e4`
- `0x14001ed04`
- `0x14001f210`
- `0x140021e20`
- `0x1401b9010`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140021ea0`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140021ea0`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140021e85`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140021e85`

## pseudocode

```c
__int64 __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__std::_Task_async_state_long_::_Task_async_state_long__std::_Fake_no_copy_callable_adapter__Windows::FileSystem::ReFs::DedupScrubTaskHandler::Start_::_3_::_lambda_1______::_2_::_lambda_1__Concurrency::details::_TypeSelectorNoAsync_::_Init(
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
  v7[0] = off_1401BA5B8;
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
0x140021e20  mov     [rsp+arg_8], rbx
0x140021e25  push    rbp
0x140021e26  push    rsi
0x140021e27  push    rdi
0x140021e28  sub     rsp, 0A0h
0x140021e2f  mov     rbx, rcx
0x140021e32  mov     rsi, [rcx+8]
0x140021e36  lea     rax, off_1401BA5B8
0x140021e3d  mov     [rsp+0B8h+var_98], rax
0x140021e42  mov     rax, [rcx+18h]
0x140021e46  mov     [rsp+0B8h+var_90], rax
0x140021e4b  lea     rax, [rsp+0B8h+var_98]
0x140021e50  mov     [rsp+0B8h+var_60], rax
0x140021e55  lea     rdx, [rsp+0B8h+var_98]
0x140021e5a  lea     rcx, [rsp+0B8h+var_58]
0x140021e5f  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x140021e64  mov     rdi, rax
0x140021e67  mov     [rsp+0B8h+arg_0], rax
0x140021e6f  mov     rbx, [rbx+8]
0x140021e73  add     rbx, 160h
0x140021e7a  mov     [rsp+0B8h+arg_10], rbx
0x140021e82  mov     rcx, rbx
0x140021e85  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x140021e8c  nop     dword ptr [rax+rax+00h]
0x140021e91  nop
0x140021e92  mov     rcx, rdi
0x140021e95  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x140021e9a  mov     bpl, al
0x140021e9d  mov     rcx, rbx
0x140021ea0  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x140021ea7  nop     dword ptr [rax+rax+00h]
0x140021eac  nop
0x140021ead  mov     rcx, [rdi+38h]
0x140021eb1  test    rcx, rcx
0x140021eb4  jz      short loc_140021ED0
0x140021eb6  mov     rdx, [rcx]
0x140021eb9  mov     rax, [rdx+20h]
0x140021ebd  cmp     rcx, rdi
0x140021ec0  setnz   dl
0x140021ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021ec8  mov     qword ptr [rdi+38h], 0
0x140021ed0  mov     dl, bpl
0x140021ed3  mov     rcx, rsi; this
0x140021ed6  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x140021edb  mov     rbx, [rsp+0B8h+arg_8]
0x140021ee3  add     rsp, 0A0h
0x140021eea  pop     rdi
0x140021eeb  pop     rsi
0x140021eec  pop     rbp
0x140021eed  retn
```
