# Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(void)

- ea: `0x180049264`
- end: `0x1800492a6`
- name: `??1?$_PPLTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@U?$_InitialTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_488856adf621c6ff95a38da0d629ff6c_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@UEAA@XZ`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800490fc`
- `0x18004b1c0`
- `0x18005a80e`

## callees

- `0x180019858`
- `0x180049264`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180049282`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180049282`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
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
0x180049264  push    rbx
0x180049266  sub     rsp, 20h
0x18004926a  mov     rbx, rcx
0x18004926d  lea     rax, ??_7?$_PPLTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@U?$_InitialTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_488856adf621c6ff95a38da0d629ff6c_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180049274  mov     [rcx], rax
0x180049277  mov     rcx, [rcx+8]
0x18004927b  add     rcx, 160h
0x180049282  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180049288  mov     rcx, [rbx+10h]; this
0x18004928c  test    rcx, rcx
0x18004928f  jz      short loc_180049296
0x180049291  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049296  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x18004929d  mov     [rbx], rax
0x1800492a0  add     rsp, 20h
0x1800492a4  pop     rbx
0x1800492a5  retn
```
