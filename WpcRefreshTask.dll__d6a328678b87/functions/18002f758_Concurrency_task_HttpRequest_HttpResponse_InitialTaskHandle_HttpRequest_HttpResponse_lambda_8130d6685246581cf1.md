# Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync_::_LogWorkItemAndInvokeUserLambda_std::function_HttpRequest::HttpResponse___cdecl(void)___

- ea: `0x18002f758`
- end: `0x18002f7eb`
- name: `Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync_::_LogWorkItemAndInvokeUserLambda_std::function_HttpRequest::HttpResponse___cdecl(void)___`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031db0`
- `0x18005fb98`

## callees

- `0x18002f758`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002f794`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002f794`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002f7ae`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002f7ae`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002f784`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002f784`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync_::_LogWorkItemAndInvokeUserLambda_std::function_HttpRequest::HttpResponse___cdecl_void____(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  Concurrency::details::_TaskEventLogger *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx

  v5 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v5);
  v6 = *(_QWORD *)(a3 + 56);
  if ( !v6 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 16LL))(v6, a2);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v5);
  v8 = *(_QWORD *)(a3 + 56);
  if ( v8 )
  {
    LOBYTE(v7) = v8 != a3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, v7);
    *(_QWORD *)(a3 + 56) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18002f758  mov     rax, rsp
0x18002f75b  mov     [rax+10h], rbx
0x18002f75f  mov     [rax+20h], rsi
0x18002f763  mov     [rax+18h], r8
0x18002f767  push    rdi
0x18002f768  sub     rsp, 30h
0x18002f76c  mov     rbx, r8
0x18002f76f  mov     rdi, rdx
0x18002f772  mov     rsi, [rcx+8]
0x18002f776  add     rsi, 160h
0x18002f77d  mov     [rax+8], rsi
0x18002f781  mov     rcx, rsi
0x18002f784  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18002f78a  nop
0x18002f78b  mov     rcx, [rbx+38h]
0x18002f78f  test    rcx, rcx
0x18002f792  jnz     short loc_18002F79B
0x18002f794  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18002f79a  int     3; Trap to Debugger
0x18002f79b  mov     rax, [rcx]
0x18002f79e  mov     rdx, rdi
0x18002f7a1  mov     rax, [rax+10h]
0x18002f7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7aa  nop
0x18002f7ab  mov     rcx, rsi
0x18002f7ae  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18002f7b4  nop
0x18002f7b5  mov     rcx, [rbx+38h]
0x18002f7b9  test    rcx, rcx
0x18002f7bc  jz      short loc_18002F7D8
0x18002f7be  mov     rax, [rcx]
0x18002f7c1  cmp     rcx, rbx
0x18002f7c4  setnz   dl
0x18002f7c7  mov     rax, [rax+20h]
0x18002f7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7d0  mov     qword ptr [rbx+38h], 0
0x18002f7d8  mov     rax, rdi
0x18002f7db  mov     rbx, [rsp+38h+arg_8]
0x18002f7e0  mov     rsi, [rsp+38h+arg_18]
0x18002f7e5  add     rsp, 30h
0x18002f7e9  pop     rdi
0x18002f7ea  retn
```
