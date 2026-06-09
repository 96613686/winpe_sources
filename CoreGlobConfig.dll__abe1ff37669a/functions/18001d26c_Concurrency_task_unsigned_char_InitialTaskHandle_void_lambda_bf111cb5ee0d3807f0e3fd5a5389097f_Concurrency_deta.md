# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x18001d26c`
- end: `0x18001d366`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e800`

## callees

- `0x18001d12c`
- `0x18001d26c`
- `0x18001d42c`
- `0x180025010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001d301`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001d301`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001d31a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001d31a`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001d2f1`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001d2f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync_::_Init(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rsi
  _QWORD *v3; // rdx
  Concurrency::details::_TaskEventLogger *v4; // rbx
  char v5; // di
  _BYTE *v6; // rdx
  _QWORD v7[7]; // [rsp+20h] [rbp-39h] BYREF
  _QWORD *v8; // [rsp+58h] [rbp-1h]
  _BYTE v9[56]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE *v10; // [rsp+98h] [rbp+3Fh]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
  v7[0] = off_1800262F8;
  v8 = v7;
  Concurrency::details::_MakeVoidToUnitFunc(v9, v7);
  if ( v8 )
  {
    v3 = v7;
    LOBYTE(v3) = v8 != v7;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v8 + 32LL))(v8, v3);
    v8 = 0;
  }
  v4 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v4);
  if ( !v10 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v5 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v10 + 16LL))(v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v4);
  if ( v10 )
  {
    v6 = v9;
    LOBYTE(v6) = v10 != v9;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v10 + 32LL))(v10, v6);
    v10 = 0;
  }
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2, v5);
}

```

## disassembly

```asm
0x18001d26c  mov     [rsp-8+arg_18], rbx
0x18001d271  push    rbp
0x18001d272  push    rsi
0x18001d273  push    rdi
0x18001d274  lea     rbp, [rsp-47h]
0x18001d279  sub     rsp, 0A0h
0x18001d280  mov     rbx, rcx
0x18001d283  mov     rsi, [rcx+8]
0x18001d287  lea     rax, off_1800262F8
0x18001d28e  mov     [rbp+57h+var_90], rax
0x18001d292  lea     rax, [rbp+57h+var_90]
0x18001d296  mov     [rbp+57h+var_58], rax
0x18001d29a  lea     rax, [rbp+57h+var_90]
0x18001d29e  mov     [rbp+57h+arg_0], rax
0x18001d2a2  lea     rdx, [rbp+57h+var_90]
0x18001d2a6  lea     rcx, [rbp+57h+var_50]
0x18001d2aa  call    ?_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@std@@AEBV?$function@$$A6AXXZ@4@@Z; Concurrency::details::_MakeVoidToUnitFunc(std::function<void (void)> const &)
0x18001d2af  nop
0x18001d2b0  mov     rcx, [rbp+57h+var_58]
0x18001d2b4  test    rcx, rcx
0x18001d2b7  jz      short loc_18001D2D7
0x18001d2b9  mov     rax, [rcx]
0x18001d2bc  lea     rdx, [rbp+57h+var_90]
0x18001d2c0  cmp     rcx, rdx
0x18001d2c3  setnz   dl
0x18001d2c6  mov     rax, [rax+20h]
0x18001d2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2cf  mov     [rbp+57h+var_58], 0
0x18001d2d7  lea     rax, [rbp+57h+var_50]
0x18001d2db  mov     [rbp+57h+arg_0], rax
0x18001d2df  mov     rbx, [rbx+8]
0x18001d2e3  add     rbx, 160h
0x18001d2ea  mov     [rbp+57h+arg_10], rbx
0x18001d2ee  mov     rcx, rbx
0x18001d2f1  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18001d2f7  nop
0x18001d2f8  mov     rcx, [rbp+57h+var_18]
0x18001d2fc  test    rcx, rcx
0x18001d2ff  jnz     short loc_18001D308
0x18001d301  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001d307  int     3; Trap to Debugger
0x18001d308  mov     rax, [rcx]
0x18001d30b  mov     rax, [rax+10h]
0x18001d30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d314  mov     dil, al
0x18001d317  mov     rcx, rbx
0x18001d31a  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18001d320  nop
0x18001d321  mov     rcx, [rbp+57h+var_18]
0x18001d325  test    rcx, rcx
0x18001d328  jz      short loc_18001D348
0x18001d32a  mov     rax, [rcx]
0x18001d32d  lea     rdx, [rbp+57h+var_50]
0x18001d331  cmp     rcx, rdx
0x18001d334  setnz   dl
0x18001d337  mov     rax, [rax+20h]
0x18001d33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d340  mov     [rbp+57h+var_18], 0
0x18001d348  mov     dl, dil
0x18001d34b  mov     rcx, rsi; this
0x18001d34e  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18001d353  mov     rbx, [rsp+0B0h+arg_18]
0x18001d35b  add     rsp, 0A0h
0x18001d362  pop     rdi
0x18001d363  pop     rsi
0x18001d364  pop     rbp
0x18001d365  retn
```
