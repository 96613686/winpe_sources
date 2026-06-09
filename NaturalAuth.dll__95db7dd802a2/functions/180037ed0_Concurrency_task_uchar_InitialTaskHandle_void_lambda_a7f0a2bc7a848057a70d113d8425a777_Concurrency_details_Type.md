# Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x180037ed0`
- end: `0x180037f92`
- name: `?_Init@?$_InitialTaskHandle@XV_lambda_a7f0a2bc7a848057a70d113d8425a777_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800383b0`

## callees

- `0x180013558`
- `0x1800187ec`
- `0x180019c6c`
- `0x180037ed0`
- `0x180046010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180037f35`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180037f35`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180037f4a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180037f4a`

## pseudocode

```c
__int64 __fastcall Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>::_Init(
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
  v7[0] = &std::_Func_impl_no_alloc<_lambda_a7f0a2bc7a848057a70d113d8425a777_,void,>::`vftable';
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
0x180037ed0  mov     [rsp+arg_8], rbx
0x180037ed5  push    rbp
0x180037ed6  push    rsi
0x180037ed7  push    rdi
0x180037ed8  sub     rsp, 0A0h
0x180037edf  mov     rbx, rcx
0x180037ee2  mov     rsi, [rcx+8]
0x180037ee6  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_a7f0a2bc7a848057a70d113d8425a777_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_a7f0a2bc7a848057a70d113d8425a777_,void,>::`vftable'
0x180037eed  mov     [rsp+0B8h+var_98], rax
0x180037ef2  mov     rax, [rcx+18h]
0x180037ef6  mov     [rsp+0B8h+var_90], rax
0x180037efb  lea     rax, [rsp+0B8h+var_98]
0x180037f00  mov     [rsp+0B8h+var_60], rax
0x180037f05  lea     rdx, [rsp+0B8h+var_98]
0x180037f0a  lea     rcx, [rsp+0B8h+var_58]
0x180037f0f  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x180037f14  mov     rdi, rax
0x180037f17  mov     [rsp+0B8h+arg_0], rax
0x180037f1f  mov     rbx, [rbx+8]
0x180037f23  add     rbx, 160h
0x180037f2a  mov     [rsp+0B8h+arg_10], rbx
0x180037f32  mov     rcx, rbx
0x180037f35  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180037f3b  nop
0x180037f3c  mov     rcx, rdi
0x180037f3f  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180037f44  mov     bpl, al
0x180037f47  mov     rcx, rbx
0x180037f4a  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180037f50  nop
0x180037f51  mov     rcx, [rdi+38h]
0x180037f55  test    rcx, rcx
0x180037f58  jz      short loc_180037F74
0x180037f5a  mov     rdx, [rcx]
0x180037f5d  mov     rax, [rdx+20h]
0x180037f61  cmp     rcx, rdi
0x180037f64  setnz   dl
0x180037f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f6c  mov     qword ptr [rdi+38h], 0
0x180037f74  mov     dl, bpl
0x180037f77  mov     rcx, rsi; this
0x180037f7a  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x180037f7f  mov     rbx, [rsp+0B8h+arg_8]
0x180037f87  add     rsp, 0A0h
0x180037f8e  pop     rdi
0x180037f8f  pop     rsi
0x180037f90  pop     rbp
0x180037f91  retn
```
