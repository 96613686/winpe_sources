# Concurrency::task<uchar>::_TaskInitWithFunctor<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_>(_lambda_a7f0a2bc7a848057a70d113d8425a777_ const &)

- ea: `0x180032990`
- end: `0x180032a25`
- name: `??$_TaskInitWithFunctor@XV_lambda_a7f0a2bc7a848057a70d113d8425a777_@@@?$task@E@Concurrency@@AEAAXAEBV_lambda_a7f0a2bc7a848057a70d113d8425a777_@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180031c74`

## callees

- `0x18000459c`
- `0x180011e1c`
- `0x18001a364`
- `0x180032990`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x1800329c6`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x1800329c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::task<unsigned char>::_TaskInitWithFunctor<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_>(
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
  *v6 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v6 + 1,
    a1);
  *v7 = &Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  v7[3] = *a2;
  return Concurrency::details::_Task_impl_base::_ScheduleTask(v5, v7, 0);
}

```

## disassembly

```asm
0x180032990  mov     [rsp+arg_8], rbx
0x180032995  mov     [rsp+arg_10], rsi
0x18003299a  push    rdi
0x18003299b  sub     rsp, 20h
0x18003299f  mov     rsi, rdx
0x1800329a2  mov     rdi, rcx
0x1800329a5  xor     r8d, r8d
0x1800329a8  mov     rax, [rcx]
0x1800329ab  mov     byte ptr [rax+r8+0Ch], 0
0x1800329b1  inc     r8
0x1800329b4  cmp     r8, 2
0x1800329b8  jnz     short loc_1800329A8
0x1800329ba  mov     rcx, [rcx]
0x1800329bd  xor     edx, edx
0x1800329bf  add     rcx, 160h
0x1800329c6  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x1800329cc  mov     rbx, [rdi]
0x1800329cf  mov     ecx, 20h ; ' '; Size
0x1800329d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800329d9  mov     r9, rax
0x1800329dc  mov     [rsp+28h+arg_0], rax
0x1800329e1  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_a7f0a2bc7a848057a70d113d8425a777_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x1800329e8  mov     rdx, rdi
0x1800329eb  lea     rcx, [r9+8]
0x1800329ef  mov     [r9], rax
0x1800329f2  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1800329f7  lea     rcx, ??_7?$_InitialTaskHandle@XV_lambda_a7f0a2bc7a848057a70d113d8425a777_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@6B@; const Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x1800329fe  xor     r8d, r8d
0x180032a01  mov     [r9], rcx
0x180032a04  mov     rcx, rbx
0x180032a07  mov     rdx, [rsi]
0x180032a0a  mov     [r9+18h], rdx
0x180032a0e  mov     rdx, r9
0x180032a11  mov     rbx, [rsp+28h+arg_8]
0x180032a16  mov     rsi, [rsp+28h+arg_10]
0x180032a1b  add     rsp, 20h
0x180032a1f  pop     rdi
0x180032a20  jmp     ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
```
