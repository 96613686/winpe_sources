# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<uchar,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(void)

- ea: `0x180021204`
- end: `0x180021243`
- name: `??1?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XV?$function@$$A6AXV?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(Concurrency::details::_ContinuationTaskHandleBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800211a0`
- `0x180032770`
- `0x180050db9`

## callees

- `0x18001134c`
- `0x180021204`
- `0x18002124c`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180021222`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180021222`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<unsigned char,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(
        Concurrency::details::_ContinuationTaskHandleBase *this)
{
  std::_Ref_count_base *v2; // rcx

  *(_QWORD *)this = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(*((_QWORD *)this + 5) + 352LL));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Concurrency::details::_ContinuationTaskHandleBase::~_ContinuationTaskHandleBase(this);
}

```

## disassembly

```asm
0x180021204  push    rbx
0x180021206  sub     rsp, 20h
0x18002120a  mov     rbx, rcx
0x18002120d  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XV?$function@$$A6AXV?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x180021214  mov     [rcx], rax
0x180021217  mov     rcx, [rcx+28h]
0x18002121b  add     rcx, 160h
0x180021222  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180021228  mov     rcx, [rbx+30h]; this
0x18002122c  test    rcx, rcx
0x18002122f  jz      short loc_180021236
0x180021231  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021236  mov     rcx, rbx; this
0x180021239  add     rsp, 20h
0x18002123d  pop     rbx
0x18002123e  jmp     ??1_ContinuationTaskHandleBase@details@Concurrency@@UEAA@XZ; Concurrency::details::_ContinuationTaskHandleBase::~_ContinuationTaskHandleBase(void)
```
