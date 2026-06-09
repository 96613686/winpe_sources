# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_

- ea: `0x18001df18`
- end: `0x18001df5a`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e810`
- `0x18001e900`

## callees

- `0x18001df18`
- `0x180022f00`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001df36`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001df36`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &off_180029080;
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
0x18001df18  push    rbx
0x18001df1a  sub     rsp, 20h
0x18001df1e  mov     rbx, rcx
0x18001df21  lea     rax, off_180029080
0x18001df28  mov     [rcx], rax
0x18001df2b  mov     rcx, [rcx+8]
0x18001df2f  add     rcx, 160h
0x18001df36  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x18001df3c  mov     rcx, [rbx+10h]; this
0x18001df40  test    rcx, rcx
0x18001df43  jz      short loc_18001DF4A
0x18001df45  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001df4a  lea     rax, ??_7?$AsyncCallbackBase@VCHSTRINGResult@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::AsyncCallbackBase<Windows::Internal::CHSTRINGResult>::`vftable'
0x18001df51  mov     [rbx], rax
0x18001df54  add     rsp, 20h
0x18001df58  pop     rbx
0x18001df59  retn
```
