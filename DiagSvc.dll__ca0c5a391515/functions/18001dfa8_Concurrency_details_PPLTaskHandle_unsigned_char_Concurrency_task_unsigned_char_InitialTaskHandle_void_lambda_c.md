# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_

- ea: `0x18001dfa8`
- end: `0x18001dfea`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e8b0`
- `0x18001e980`

## callees

- `0x18001dfa8`
- `0x180022f00`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001dfc6`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001dfc6`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &off_180029060;
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(a1[1] + 352LL));
  v2 = (std::_Ref_count_base *)a1[2];
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  result = &Windows::Internal::AsyncCallbackBase<Windows::Internal::CHSTRINGResult>::`vftable';
  *a1 = &Windows::Internal::AsyncCallbackBase<Windows::Internal::CHSTRINGResult>::`vftable';
  return result;
}

```

## disassembly

```asm
0x18001dfa8  push    rbx
0x18001dfaa  sub     rsp, 20h
0x18001dfae  mov     rbx, rcx
0x18001dfb1  lea     rax, off_180029060
0x18001dfb8  mov     [rcx], rax
0x18001dfbb  mov     rcx, [rcx+8]
0x18001dfbf  add     rcx, 160h
0x18001dfc6  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x18001dfcc  mov     rcx, [rbx+10h]; this
0x18001dfd0  test    rcx, rcx
0x18001dfd3  jz      short loc_18001DFDA
0x18001dfd5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001dfda  lea     rax, ??_7?$AsyncCallbackBase@VCHSTRINGResult@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::AsyncCallbackBase<Windows::Internal::CHSTRINGResult>::`vftable'
0x18001dfe1  mov     [rbx], rax
0x18001dfe4  add     rsp, 20h
0x18001dfe8  pop     rbx
0x18001dfe9  retn
```
