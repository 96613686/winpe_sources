# Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(void)

- ea: `0x18004921c`
- end: `0x18004925e`
- name: `??1?$_PPLTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@U?$_InitialTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_45f745786ef9029c1ad2740a163b37bf_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@UEAA@XZ`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800490cc`
- `0x18004b180`
- `0x18005a7fc`

## callees

- `0x180019858`
- `0x18004921c`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004923a`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004923a`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
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
0x18004921c  push    rbx
0x18004921e  sub     rsp, 20h
0x180049222  mov     rbx, rcx
0x180049225  lea     rax, ??_7?$_PPLTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@U?$_InitialTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_45f745786ef9029c1ad2740a163b37bf_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x18004922c  mov     [rcx], rax
0x18004922f  mov     rcx, [rcx+8]
0x180049233  add     rcx, 160h
0x18004923a  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180049240  mov     rcx, [rbx+10h]; this
0x180049244  test    rcx, rcx
0x180049247  jz      short loc_18004924E
0x180049249  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004924e  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x180049255  mov     [rbx], rax
0x180049258  add     rsp, 20h
0x18004925c  pop     rbx
0x18004925d  retn
```
