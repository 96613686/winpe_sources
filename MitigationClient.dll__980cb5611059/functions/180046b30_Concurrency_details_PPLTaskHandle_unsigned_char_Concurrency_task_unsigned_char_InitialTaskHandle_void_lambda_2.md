# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_

- ea: `0x180046b30`
- end: `0x180046b72`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800472f0`
- `0x180047340`

## callees

- `0x18003330c`
- `0x180046b30`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180046b4e`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180046b4e`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &off_18005EAE0;
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(a1[1] + 352LL));
  v2 = (std::_Ref_count_base *)a1[2];
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  result = &Concurrency::details::_TaskProcHandle::`vftable';
  *a1 = &Concurrency::details::_TaskProcHandle::`vftable';
  return result;
}

```

## disassembly

```asm
0x180046b30  push    rbx
0x180046b32  sub     rsp, 20h
0x180046b36  mov     rbx, rcx
0x180046b39  lea     rax, off_18005EAE0
0x180046b40  mov     [rcx], rax
0x180046b43  mov     rcx, [rcx+8]
0x180046b47  add     rcx, 160h
0x180046b4e  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180046b54  mov     rcx, [rbx+10h]; this
0x180046b58  test    rcx, rcx
0x180046b5b  jz      short loc_180046B62
0x180046b5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180046b62  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x180046b69  mov     [rbx], rax
0x180046b6c  add     rsp, 20h
0x180046b70  pop     rbx
0x180046b71  retn
```
