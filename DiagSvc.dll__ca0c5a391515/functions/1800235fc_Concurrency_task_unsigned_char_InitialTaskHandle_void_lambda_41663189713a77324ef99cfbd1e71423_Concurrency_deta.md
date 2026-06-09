# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x1800235fc`
- end: `0x1800236be`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800246e0`

## callees

- `0x18001e760`
- `0x18002335c`
- `0x1800235fc`
- `0x180023b78`
- `0x180027010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180023661`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180023661`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180023676`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180023676`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync_::_Init(
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
  v7[0] = off_180028F70;
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
0x1800235fc  mov     [rsp+arg_8], rbx
0x180023601  push    rbp
0x180023602  push    rsi
0x180023603  push    rdi
0x180023604  sub     rsp, 0A0h
0x18002360b  mov     rbx, rcx
0x18002360e  mov     rsi, [rcx+8]
0x180023612  lea     rax, off_180028F70
0x180023619  mov     [rsp+0B8h+var_98], rax
0x18002361e  mov     rax, [rcx+18h]
0x180023622  mov     [rsp+0B8h+var_90], rax
0x180023627  lea     rax, [rsp+0B8h+var_98]
0x18002362c  mov     [rsp+0B8h+var_60], rax
0x180023631  lea     rdx, [rsp+0B8h+var_98]
0x180023636  lea     rcx, [rsp+0B8h+var_58]
0x18002363b  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x180023640  mov     rdi, rax
0x180023643  mov     [rsp+0B8h+arg_0], rax
0x18002364b  mov     rbx, [rbx+8]
0x18002364f  add     rbx, 160h
0x180023656  mov     [rsp+0B8h+arg_10], rbx
0x18002365e  mov     rcx, rbx
0x180023661  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180023667  nop
0x180023668  mov     rcx, rdi
0x18002366b  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180023670  mov     bpl, al
0x180023673  mov     rcx, rbx
0x180023676  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18002367c  nop
0x18002367d  mov     rcx, [rdi+38h]
0x180023681  test    rcx, rcx
0x180023684  jz      short loc_1800236A0
0x180023686  mov     rdx, [rcx]
0x180023689  mov     rax, [rdx+20h]
0x18002368d  cmp     rcx, rdi
0x180023690  setnz   dl
0x180023693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023698  mov     qword ptr [rdi+38h], 0
0x1800236a0  mov     dl, bpl
0x1800236a3  mov     rcx, rsi; this
0x1800236a6  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x1800236ab  mov     rbx, [rsp+0B8h+arg_8]
0x1800236b3  add     rsp, 0A0h
0x1800236ba  pop     rdi
0x1800236bb  pop     rsi
0x1800236bc  pop     rbp
0x1800236bd  retn
```
