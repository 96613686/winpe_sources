# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<uchar,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(void)

- ea: `0x1800491d4`
- end: `0x180049213`
- name: `??1?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@XV?$function@$$A6AXV?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@U?$integral_constant@_N$0A@@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(Concurrency::details::_ContinuationTaskHandleBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004905c`
- `0x18004b140`
- `0x18005ae23`

## callees

- `0x180019858`
- `0x1800491d4`
- `0x180049688`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800491f2`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800491f2`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<unsigned char,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(
        Concurrency::details::_ContinuationTaskHandleBase *this)
{
  std::_Ref_count_base *v2; // rcx

  *(_QWORD *)this = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(*((_QWORD *)this + 5) + 352LL));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Concurrency::details::_ContinuationTaskHandleBase::~_ContinuationTaskHandleBase(this);
}

```

## disassembly

```asm
0x1800491d4  push    rbx
0x1800491d6  sub     rsp, 20h
0x1800491da  mov     rbx, rcx
0x1800491dd  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@XV?$function@$$A6AXV?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@U?$integral_constant@_N$0A@@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x1800491e4  mov     [rcx], rax
0x1800491e7  mov     rcx, [rcx+28h]
0x1800491eb  add     rcx, 160h
0x1800491f2  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x1800491f8  mov     rcx, [rbx+30h]; this
0x1800491fc  test    rcx, rcx
0x1800491ff  jz      short loc_180049206
0x180049201  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049206  mov     rcx, rbx; this
0x180049209  add     rsp, 20h
0x18004920d  pop     rbx
0x18004920e  jmp     ??1_ContinuationTaskHandleBase@details@Concurrency@@UEAA@XZ; Concurrency::details::_ContinuationTaskHandleBase::~_ContinuationTaskHandleBase(void)
```
