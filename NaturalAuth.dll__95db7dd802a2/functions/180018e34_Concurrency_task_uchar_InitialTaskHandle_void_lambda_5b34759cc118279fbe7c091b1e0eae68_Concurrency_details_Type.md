# Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x180018e34`
- end: `0x180018ef6`
- name: `?_Init@?$_InitialTaskHandle@XV_lambda_5b34759cc118279fbe7c091b1e0eae68_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b680`

## callees

- `0x180013558`
- `0x1800187ec`
- `0x180018e34`
- `0x180019c6c`
- `0x180046010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180018e99`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180018e99`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180018eae`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180018eae`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>::_Init(
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
  v7[0] = &std::_Func_impl_no_alloc<_lambda_5b34759cc118279fbe7c091b1e0eae68_,void,>::`vftable';
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
0x180018e34  mov     [rsp+arg_8], rbx
0x180018e39  push    rbp
0x180018e3a  push    rsi
0x180018e3b  push    rdi
0x180018e3c  sub     rsp, 0A0h
0x180018e43  mov     rbx, rcx
0x180018e46  mov     rsi, [rcx+8]
0x180018e4a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_5b34759cc118279fbe7c091b1e0eae68_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_5b34759cc118279fbe7c091b1e0eae68_,void,>::`vftable'
0x180018e51  mov     [rsp+0B8h+var_98], rax
0x180018e56  mov     rax, [rcx+18h]
0x180018e5a  mov     [rsp+0B8h+var_90], rax
0x180018e5f  lea     rax, [rsp+0B8h+var_98]
0x180018e64  mov     [rsp+0B8h+var_60], rax
0x180018e69  lea     rdx, [rsp+0B8h+var_98]
0x180018e6e  lea     rcx, [rsp+0B8h+var_58]
0x180018e73  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x180018e78  mov     rdi, rax
0x180018e7b  mov     [rsp+0B8h+arg_0], rax
0x180018e83  mov     rbx, [rbx+8]
0x180018e87  add     rbx, 160h
0x180018e8e  mov     [rsp+0B8h+arg_10], rbx
0x180018e96  mov     rcx, rbx
0x180018e99  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180018e9f  nop
0x180018ea0  mov     rcx, rdi
0x180018ea3  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180018ea8  mov     bpl, al
0x180018eab  mov     rcx, rbx
0x180018eae  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180018eb4  nop
0x180018eb5  mov     rcx, [rdi+38h]
0x180018eb9  test    rcx, rcx
0x180018ebc  jz      short loc_180018ED8
0x180018ebe  mov     rdx, [rcx]
0x180018ec1  mov     rax, [rdx+20h]
0x180018ec5  cmp     rcx, rdi
0x180018ec8  setnz   dl
0x180018ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ed0  mov     qword ptr [rdi+38h], 0
0x180018ed8  mov     dl, bpl
0x180018edb  mov     rcx, rsi; this
0x180018ede  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x180018ee3  mov     rbx, [rsp+0B8h+arg_8]
0x180018eeb  add     rsp, 0A0h
0x180018ef2  pop     rdi
0x180018ef3  pop     rsi
0x180018ef4  pop     rbp
0x180018ef5  retn
```
