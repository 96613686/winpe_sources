# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(void)

- ea: `0x1800335d0`
- end: `0x180033612`
- name: `??1?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_a7f0a2bc7a848057a70d113d8425a777_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEAA@XZ`
- size: `66`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033e70`
- `0x180033ec0`

## callees

- `0x180017648`
- `0x1800335d0`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800335ee`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800335ee`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(a1[1] + 352LL));
  v2 = (std::_Ref_count_base *)a1[2];
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  result = &TimeSignal::Factory::`vftable';
  *a1 = &TimeSignal::Factory::`vftable';
  return result;
}

```

## disassembly

```asm
0x1800335d0  push    rbx
0x1800335d2  sub     rsp, 20h
0x1800335d6  mov     rbx, rcx
0x1800335d9  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_a7f0a2bc7a848057a70d113d8425a777_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_a7f0a2bc7a848057a70d113d8425a777_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x1800335e0  mov     [rcx], rax
0x1800335e3  mov     rcx, [rcx+8]
0x1800335e7  add     rcx, 160h
0x1800335ee  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x1800335f4  mov     rcx, [rbx+10h]; this
0x1800335f8  test    rcx, rcx
0x1800335fb  jz      short loc_180033602
0x1800335fd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180033602  lea     rax, ??_7Factory@TimeSignal@@6B@; const TimeSignal::Factory::`vftable'
0x180033609  mov     [rbx], rax
0x18003360c  add     rsp, 20h
0x180033610  pop     rbx
0x180033611  retn
```
