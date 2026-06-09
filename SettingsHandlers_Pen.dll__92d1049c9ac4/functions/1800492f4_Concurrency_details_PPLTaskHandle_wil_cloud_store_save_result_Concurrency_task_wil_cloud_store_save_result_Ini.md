# Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(void)

- ea: `0x1800492f4`
- end: `0x180049336`
- name: `??1?$_PPLTaskHandle@Vcloud_store_save_result@wil@@U?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_5841bb6124e075856403c279d110f614_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@UEAA@XZ`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004915c`
- `0x18004b240`
- `0x18005a855`

## callees

- `0x180019858`
- `0x1800492f4`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180049312`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180049312`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
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
0x1800492f4  push    rbx
0x1800492f6  sub     rsp, 20h
0x1800492fa  mov     rbx, rcx
0x1800492fd  lea     rax, ??_7?$_PPLTaskHandle@Vcloud_store_save_result@wil@@U?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_5841bb6124e075856403c279d110f614_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180049304  mov     [rcx], rax
0x180049307  mov     rcx, [rcx+8]
0x18004930b  add     rcx, 160h
0x180049312  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180049318  mov     rcx, [rbx+10h]; this
0x18004931c  test    rcx, rcx
0x18004931f  jz      short loc_180049326
0x180049321  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049326  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x18004932d  mov     [rbx], rax
0x180049330  add     rsp, 20h
0x180049334  pop     rbx
0x180049335  retn
```
