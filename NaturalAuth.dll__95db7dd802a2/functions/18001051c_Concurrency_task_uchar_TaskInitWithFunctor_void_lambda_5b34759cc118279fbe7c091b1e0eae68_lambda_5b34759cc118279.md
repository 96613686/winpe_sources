# Concurrency::task<uchar>::_TaskInitWithFunctor<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_>(_lambda_5b34759cc118279fbe7c091b1e0eae68_ const &)

- ea: `0x18001051c`
- end: `0x1800105b1`
- name: `??$_TaskInitWithFunctor@XV_lambda_5b34759cc118279fbe7c091b1e0eae68_@@@?$task@E@Concurrency@@AEAAXAEBV_lambda_5b34759cc118279fbe7c091b1e0eae68_@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000d634`

## callees

- `0x18000459c`
- `0x18001051c`
- `0x180011e1c`
- `0x18001a364`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180010552`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180010552`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::task<unsigned char>::_TaskInitWithFunctor<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_>(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 i; // r8
  __int64 v5; // rbx
  _QWORD *v6; // rax
  _QWORD *v7; // r9

  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(*a1 + i + 12) = 0;
  Concurrency::details::_TaskEventLogger::_LogScheduleTask((Concurrency::details::_TaskEventLogger *)(*a1 + 352), 0);
  v5 = *a1;
  v6 = operator new(0x20u);
  *v6 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v6 + 1,
    a1);
  *v7 = &Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  v7[3] = *a2;
  return Concurrency::details::_Task_impl_base::_ScheduleTask(v5, v7, 0);
}

```

## disassembly

```asm
0x18001051c  mov     [rsp+arg_8], rbx
0x180010521  mov     [rsp+arg_10], rsi
0x180010526  push    rdi
0x180010527  sub     rsp, 20h
0x18001052b  mov     rsi, rdx
0x18001052e  mov     rdi, rcx
0x180010531  xor     r8d, r8d
0x180010534  mov     rax, [rcx]
0x180010537  mov     byte ptr [rax+r8+0Ch], 0
0x18001053d  inc     r8
0x180010540  cmp     r8, 2
0x180010544  jnz     short loc_180010534
0x180010546  mov     rcx, [rcx]
0x180010549  xor     edx, edx
0x18001054b  add     rcx, 160h
0x180010552  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x180010558  mov     rbx, [rdi]
0x18001055b  mov     ecx, 20h ; ' '; Size
0x180010560  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010565  mov     r9, rax
0x180010568  mov     [rsp+28h+arg_0], rax
0x18001056d  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_5b34759cc118279fbe7c091b1e0eae68_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180010574  mov     rdx, rdi
0x180010577  lea     rcx, [r9+8]
0x18001057b  mov     [r9], rax
0x18001057e  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x180010583  lea     rcx, ??_7?$_InitialTaskHandle@XV_lambda_5b34759cc118279fbe7c091b1e0eae68_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@6B@; const Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18001058a  xor     r8d, r8d
0x18001058d  mov     [r9], rcx
0x180010590  mov     rcx, rbx
0x180010593  mov     rdx, [rsi]
0x180010596  mov     [r9+18h], rdx
0x18001059a  mov     rdx, r9
0x18001059d  mov     rbx, [rsp+28h+arg_8]
0x1800105a2  mov     rsi, [rsp+28h+arg_10]
0x1800105a7  add     rsp, 20h
0x1800105ab  pop     rdi
0x1800105ac  jmp     ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
```
