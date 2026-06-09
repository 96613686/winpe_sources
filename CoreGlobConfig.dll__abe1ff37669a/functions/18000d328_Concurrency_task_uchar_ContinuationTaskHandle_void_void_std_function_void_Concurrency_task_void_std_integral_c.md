# Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<uchar (Concurrency::task<void>)>,Concurrency::task<void>>(std::function<uchar (Concurrency::task<void>)> &&,Concurrency::task<void> &&)

- ea: `0x18000d328`
- end: `0x18000d3cb`
- name: `??$_LogWorkItemAndInvokeUserLambda@V?$function@$$A6AEV?$task@X@Concurrency@@@Z@std@@V?$task@X@Concurrency@@@?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAE$$QEAV?$function@$$A6AEV?$task@X@Concurrency@@@Z@std@@$$QEAV?$task@X@2@@Z`
- size: `163`
- prototype: `char __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c644`

## callees

- `0x18000d328`
- `0x180011090`
- `0x180025010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000d38a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000d38a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18000d3b2`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18000d3b2`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18000d350`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18000d350`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<unsigned char (Concurrency::task<void>)>,Concurrency::task<void>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  Concurrency::details::_TaskEventLogger *v5; // rsi
  __int64 v6; // rcx
  char v7; // bl
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF

  v5 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v5);
  v9[0] = *a3;
  v9[1] = a3[1];
  *a3 = 0;
  a3[1] = 0;
  v6 = *(_QWORD *)(a2 + 56);
  if ( !v6 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v6 + 16LL))(v6, v9);
  std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(v9);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v5);
  return v7;
}

```

## disassembly

```asm
0x18000d328  mov     [rsp+arg_10], rbx
0x18000d32d  mov     [rsp+arg_18], rsi
0x18000d332  push    rdi
0x18000d333  sub     rsp, 30h
0x18000d337  mov     rbx, r8
0x18000d33a  mov     rdi, rdx
0x18000d33d  mov     rsi, [rcx+28h]
0x18000d341  add     rsi, 160h
0x18000d348  mov     [rsp+38h+arg_0], rsi
0x18000d34d  mov     rcx, rsi
0x18000d350  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18000d356  nop
0x18000d357  mov     rax, [rbx]
0x18000d35a  mov     [rsp+38h+var_18], rax
0x18000d35f  mov     rax, [rbx+8]
0x18000d363  mov     [rsp+38h+var_10], rax
0x18000d368  mov     qword ptr [rbx], 0
0x18000d36f  mov     qword ptr [rbx+8], 0
0x18000d377  lea     rax, [rsp+38h+var_18]
0x18000d37c  mov     [rsp+38h+arg_8], rax
0x18000d381  mov     rcx, [rdi+38h]
0x18000d385  test    rcx, rcx
0x18000d388  jnz     short loc_18000D391
0x18000d38a  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18000d390  int     3; Trap to Debugger
0x18000d391  mov     rax, [rcx]
0x18000d394  lea     rdx, [rsp+38h+var_18]
0x18000d399  mov     rax, [rax+10h]
0x18000d39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a2  mov     bl, al
0x18000d3a4  lea     rcx, [rsp+38h+var_18]
0x18000d3a9  call    ??1?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(void)
0x18000d3ae  nop
0x18000d3af  mov     rcx, rsi
0x18000d3b2  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18000d3b8  nop
0x18000d3b9  mov     al, bl
0x18000d3bb  mov     rbx, [rsp+38h+arg_10]
0x18000d3c0  mov     rsi, [rsp+38h+arg_18]
0x18000d3c5  add     rsp, 30h
0x18000d3c9  pop     rdi
0x18000d3ca  retn
```
