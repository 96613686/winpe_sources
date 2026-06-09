# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x1800236c4`
- end: `0x180023786`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024750`

## callees

- `0x18001e760`
- `0x18002335c`
- `0x1800236c4`
- `0x180023b78`
- `0x180027010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180023729`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180023729`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002373e`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002373e`

## pseudocode

```c
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync_::_Init(
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
  v7[0] = off_180028FD0;
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
0x1800236c4  mov     [rsp+arg_8], rbx
0x1800236c9  push    rbp
0x1800236ca  push    rsi
0x1800236cb  push    rdi
0x1800236cc  sub     rsp, 0A0h
0x1800236d3  mov     rbx, rcx
0x1800236d6  mov     rsi, [rcx+8]
0x1800236da  lea     rax, off_180028FD0
0x1800236e1  mov     [rsp+0B8h+var_98], rax
0x1800236e6  mov     rax, [rcx+18h]
0x1800236ea  mov     [rsp+0B8h+var_90], rax
0x1800236ef  lea     rax, [rsp+0B8h+var_98]
0x1800236f4  mov     [rsp+0B8h+var_60], rax
0x1800236f9  lea     rdx, [rsp+0B8h+var_98]
0x1800236fe  lea     rcx, [rsp+0B8h+var_58]
0x180023703  call    ?_Perform@?$_Init_func_transformer@X@Concurrency@@SA?AV?$function@$$A6AEXZ@std@@V?$function@$$A6AXXZ@4@@Z; Concurrency::_Init_func_transformer<void>::_Perform(std::function<void (void)>)
0x180023708  mov     rdi, rax
0x18002370b  mov     [rsp+0B8h+arg_0], rax
0x180023713  mov     rbx, [rbx+8]
0x180023717  add     rbx, 160h
0x18002371e  mov     [rsp+0B8h+arg_10], rbx
0x180023726  mov     rcx, rbx
0x180023729  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18002372f  nop
0x180023730  mov     rcx, rdi
0x180023733  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180023738  mov     bpl, al
0x18002373b  mov     rcx, rbx
0x18002373e  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180023744  nop
0x180023745  mov     rcx, [rdi+38h]
0x180023749  test    rcx, rcx
0x18002374c  jz      short loc_180023768
0x18002374e  mov     rdx, [rcx]
0x180023751  mov     rax, [rdx+20h]
0x180023755  cmp     rcx, rdi
0x180023758  setnz   dl
0x18002375b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023760  mov     qword ptr [rdi+38h], 0
0x180023768  mov     dl, bpl
0x18002376b  mov     rcx, rsi; this
0x18002376e  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x180023773  mov     rbx, [rsp+0B8h+arg_8]
0x18002377b  add     rsp, 0A0h
0x180023782  pop     rdi
0x180023783  pop     rsi
0x180023784  pop     rbp
0x180023785  retn
```
