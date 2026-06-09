# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_

- ea: `0x180010dd0`
- end: `0x180010e12`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800129c0`
- `0x180012a50`

## callees

- `0x180010dd0`
- `0x18001cc40`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180010dee`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180010dee`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &off_1800263C8;
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
0x180010dd0  push    rbx
0x180010dd2  sub     rsp, 20h
0x180010dd6  mov     rbx, rcx
0x180010dd9  lea     rax, off_1800263C8
0x180010de0  mov     [rcx], rax
0x180010de3  mov     rcx, [rcx+8]
0x180010de7  add     rcx, 160h
0x180010dee  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180010df4  mov     rcx, [rbx+10h]; this
0x180010df8  test    rcx, rcx
0x180010dfb  jz      short loc_180010E02
0x180010dfd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010e02  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x180010e09  mov     [rbx], rax
0x180010e0c  add     rsp, 20h
0x180010e10  pop     rbx
0x180010e11  retn
```
