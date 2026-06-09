# Concurrency::details::_PPLTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(void)

- ea: `0x180032200`
- end: `0x180032242`
- name: `??1?$_PPLTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@U?$_InitialTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@U_TaskProcHandle@details@6@@details@Concurrency@@UEAA@XZ`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800321d0`
- `0x1800327b0`
- `0x1800505ba`

## callees

- `0x18001134c`
- `0x180032200`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003221e`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003221e`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(a1[1] + 352LL));
  v2 = (std::_Ref_count_base *)a1[2];
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  result = &Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Devices::Geolocation::IGeopoint>>::`vftable';
  *a1 = &Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Devices::Geolocation::IGeopoint>>::`vftable';
  return result;
}

```

## disassembly

```asm
0x180032200  push    rbx
0x180032202  sub     rsp, 20h
0x180032206  mov     rbx, rcx
0x180032209  lea     rax, ??_7?$_PPLTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@U?$_InitialTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@U_TaskProcHandle@details@6@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180032210  mov     [rcx], rax
0x180032213  mov     rcx, [rcx+8]
0x180032217  add     rcx, 160h
0x18003221e  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180032224  mov     rcx, [rbx+10h]; this
0x180032228  test    rcx, rcx
0x18003222b  jz      short loc_180032232
0x18003222d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032232  lea     rax, ??_7?$AsyncCallbackBase@V?$CMarshaledInterfaceResult@UIGeopoint@Geolocation@Devices@Windows@@@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Devices::Geolocation::IGeopoint>>::`vftable'
0x180032239  mov     [rbx], rax
0x18003223c  add     rsp, 20h
0x180032240  pop     rbx
0x180032241  retn
```
