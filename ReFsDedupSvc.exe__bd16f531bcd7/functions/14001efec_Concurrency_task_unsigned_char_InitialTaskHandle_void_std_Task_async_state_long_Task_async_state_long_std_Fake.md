# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__std::_Task_async_state_long_::_Task_async_state_long__std::_Fake_no_copy_callable_adapter__Windows::FileSystem::ReFs::DedupTaskHandler::Start_::_3_::_lambda_1______::_2_::_lambda_1__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x14001efec`
- end: `0x14001f0bb`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__std::_Task_async_state_long_::_Task_async_state_long__std::_Fake_no_copy_callable_adapter__Windows::FileSystem::ReFs::DedupTaskHandler::Start_::_3_::_lambda_1______::_2_::_lambda_1__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140020030`

## callees

- `0x14001c9e4`
- `0x14001ed04`
- `0x14001efec`
- `0x14001f210`
- `0x1401b9010`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001f06c`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001f06c`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001f051`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001f051`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__std::_Task_async_state_long_::_Task_async_state_long__std::_Fake_no_copy_callable_adapter__Windows::FileSystem::ReFs::DedupTaskHandler::Start_::_3_::_lambda_1______::_2_::_lambda_1__Concurrency::details::_TypeSelectorNoAsync_::_Init(
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
  v7[0] = off_1401BA168;
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
0x14001efec  mov     [rsp+arg_8], rbx
0x14001eff1  push    rbp
0x14001eff2  push    rsi
0x14001eff3  push    rdi
0x14001eff4  sub     rsp, 0A0h
0x14001effb  mov     rbx, rcx
0x14001effe  mov     rsi, [rcx+8]
0x14001f002  lea     rax, off_1401BA168
0x14001f009  mov     [rsp+0B8h+var_98], rax
0x14001f00e  mov     rax, [rcx+18h]
0x14001f012  mov     [rsp+0B8h+var_90], rax
0x14001f017  lea     rax, [rsp+0B8h+var_98]
0x14001f01c  mov     [rsp+0B8h+var_60], rax
0x14001f021  lea     rdx, [rsp+0B8h+var_98]
0x14001f026  lea     rcx, [rsp+0B8h+var_58]
0x14001f02b  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x14001f030  mov     rdi, rax
0x14001f033  mov     [rsp+0B8h+arg_0], rax
0x14001f03b  mov     rbx, [rbx+8]
0x14001f03f  add     rbx, 160h
0x14001f046  mov     [rsp+0B8h+arg_10], rbx
0x14001f04e  mov     rcx, rbx
0x14001f051  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x14001f058  nop     dword ptr [rax+rax+00h]
0x14001f05d  nop
0x14001f05e  mov     rcx, rdi
0x14001f061  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x14001f066  mov     bpl, al
0x14001f069  mov     rcx, rbx
0x14001f06c  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x14001f073  nop     dword ptr [rax+rax+00h]
0x14001f078  nop
0x14001f079  mov     rcx, [rdi+38h]
0x14001f07d  test    rcx, rcx
0x14001f080  jz      short loc_14001F09C
0x14001f082  mov     rdx, [rcx]
0x14001f085  mov     rax, [rdx+20h]
0x14001f089  cmp     rcx, rdi
0x14001f08c  setnz   dl
0x14001f08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f094  mov     qword ptr [rdi+38h], 0
0x14001f09c  mov     dl, bpl
0x14001f09f  mov     rcx, rsi; this
0x14001f0a2  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x14001f0a7  mov     rbx, [rsp+0B8h+arg_8]
0x14001f0af  add     rsp, 0A0h
0x14001f0b6  pop     rdi
0x14001f0b7  pop     rsi
0x14001f0b8  pop     rbp
0x14001f0b9  retn
```
