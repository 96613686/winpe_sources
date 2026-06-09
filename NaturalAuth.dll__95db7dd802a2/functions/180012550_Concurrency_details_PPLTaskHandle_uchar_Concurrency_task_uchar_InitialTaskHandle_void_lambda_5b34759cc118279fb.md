# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(void)

- ea: `0x180012550`
- end: `0x180012592`
- name: `??1?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_5b34759cc118279fbe7c091b1e0eae68_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEAA@XZ`
- size: `66`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800136a0`
- `0x180013780`

## callees

- `0x180012550`
- `0x180017648`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001256e`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001256e`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
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
0x180012550  push    rbx
0x180012552  sub     rsp, 20h
0x180012556  mov     rbx, rcx
0x180012559  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_5b34759cc118279fbe7c091b1e0eae68_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_5b34759cc118279fbe7c091b1e0eae68_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180012560  mov     [rcx], rax
0x180012563  mov     rcx, [rcx+8]
0x180012567  add     rcx, 160h
0x18001256e  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180012574  mov     rcx, [rbx+10h]; this
0x180012578  test    rcx, rcx
0x18001257b  jz      short loc_180012582
0x18001257d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012582  lea     rax, ??_7Factory@TimeSignal@@6B@; const TimeSignal::Factory::`vftable'
0x180012589  mov     [rbx], rax
0x18001258c  add     rsp, 20h
0x180012590  pop     rbx
0x180012591  retn
```
