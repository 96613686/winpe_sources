# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_

- ea: `0x18001df60`
- end: `0x18001dfa2`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e860`
- `0x18001e940`

## callees

- `0x18001df60`
- `0x180022f00`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001df7e`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001df7e`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_74fff73db5622b7bcf36501e7db7f309__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &off_180029040;
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
0x18001df60  push    rbx
0x18001df62  sub     rsp, 20h
0x18001df66  mov     rbx, rcx
0x18001df69  lea     rax, off_180029040
0x18001df70  mov     [rcx], rax
0x18001df73  mov     rcx, [rcx+8]
0x18001df77  add     rcx, 160h
0x18001df7e  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x18001df84  mov     rcx, [rbx+10h]; this
0x18001df88  test    rcx, rcx
0x18001df8b  jz      short loc_18001DF92
0x18001df8d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001df92  lea     rax, ??_7?$AsyncCallbackBase@VCHSTRINGResult@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::AsyncCallbackBase<Windows::Internal::CHSTRINGResult>::`vftable'
0x18001df99  mov     [rbx], rax
0x18001df9c  add     rsp, 20h
0x18001dfa0  pop     rbx
0x18001dfa1  retn
```
