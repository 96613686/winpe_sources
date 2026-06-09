# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(void)

- ea: `0x180025a38`
- end: `0x180025a7a`
- name: `??1?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV?$function@$$A6AXXZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEAA@XZ`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800259e0`
- `0x180036750`
- `0x18004f7d3`

## callees

- `0x18001134c`
- `0x180025a38`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180025a56`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180025a56`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(
        _QWORD *a1)
{
  std::_Ref_count_base *v2; // rcx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
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
0x180025a38  push    rbx
0x180025a3a  sub     rsp, 20h
0x180025a3e  mov     rbx, rcx
0x180025a41  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV?$function@$$A6AXXZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180025a48  mov     [rcx], rax
0x180025a4b  mov     rcx, [rcx+8]
0x180025a4f  add     rcx, 160h
0x180025a56  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180025a5c  mov     rcx, [rbx+10h]; this
0x180025a60  test    rcx, rcx
0x180025a63  jz      short loc_180025A6A
0x180025a65  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025a6a  lea     rax, ??_7?$AsyncCallbackBase@V?$CMarshaledInterfaceResult@UIGeopoint@Geolocation@Devices@Windows@@@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Devices::Geolocation::IGeopoint>>::`vftable'
0x180025a71  mov     [rbx], rax
0x180025a74  add     rsp, 20h
0x180025a78  pop     rbx
0x180025a79  retn
```
