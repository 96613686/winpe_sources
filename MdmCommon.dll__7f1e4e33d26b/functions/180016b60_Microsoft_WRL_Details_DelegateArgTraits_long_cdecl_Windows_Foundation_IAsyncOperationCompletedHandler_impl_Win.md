# Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_80fc5ebc6c75ae438d12ab94b57c3bb1___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::_scalar_deleting_destructor_

- ea: `0x180016b60`
- end: `0x180016b88`
- name: `Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_80fc5ebc6c75ae438d12ab94b57c3bb1___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::_scalar_deleting_destructor_`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001544`
- `0x180016b60`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::___Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_80fc5ebc6c75ae438d12ab94b57c3bb1___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::_scalar_deleting_destructor_(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180016b60  push    rbx
0x180016b62  sub     rsp, 20h
0x180016b66  mov     dword ptr [rcx+0Ch], 0C0000001h
0x180016b6d  mov     rbx, rcx
0x180016b70  test    dl, 1
0x180016b73  jz      short loc_180016B7F
0x180016b75  mov     edx, 28h ; '('; unsigned __int64
0x180016b7a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016b7f  mov     rax, rbx
0x180016b82  add     rsp, 20h
0x180016b86  pop     rbx
0x180016b87  retn
```
