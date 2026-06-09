# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<uchar,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(void)

- ea: `0x18004918c`
- end: `0x1800491cb`
- name: `??1?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@XV?$function@$$A6AXV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@U?$integral_constant@_N$0A@@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(Concurrency::details::_ContinuationTaskHandleBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180048ff8`
- `0x18004b100`
- `0x18005ade5`

## callees

- `0x180019858`
- `0x18004918c`
- `0x180049688`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800491aa`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800491aa`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<unsigned char,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(
        Concurrency::details::_ContinuationTaskHandleBase *this)
{
  std::_Ref_count_base *v2; // rcx

  *(_QWORD *)this = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(*((_QWORD *)this + 5) + 352LL));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Concurrency::details::_ContinuationTaskHandleBase::~_ContinuationTaskHandleBase(this);
}

```

## disassembly

```asm
0x18004918c  push    rbx
0x18004918e  sub     rsp, 20h
0x180049192  mov     rbx, rcx
0x180049195  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@XV?$function@$$A6AXV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@U?$integral_constant@_N$0A@@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x18004919c  mov     [rcx], rax
0x18004919f  mov     rcx, [rcx+28h]
0x1800491a3  add     rcx, 160h
0x1800491aa  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x1800491b0  mov     rcx, [rbx+30h]; this
0x1800491b4  test    rcx, rcx
0x1800491b7  jz      short loc_1800491BE
0x1800491b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800491be  mov     rcx, rbx; this
0x1800491c1  add     rsp, 20h
0x1800491c5  pop     rbx
0x1800491c6  jmp     ??1_ContinuationTaskHandleBase@details@Concurrency@@UEAA@XZ; Concurrency::details::_ContinuationTaskHandleBase::~_ContinuationTaskHandleBase(void)
```
