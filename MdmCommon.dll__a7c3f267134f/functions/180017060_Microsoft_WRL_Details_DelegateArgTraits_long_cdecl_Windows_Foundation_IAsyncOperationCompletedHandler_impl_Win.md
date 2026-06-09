# Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_80fc5ebc6c75ae438d12ab94b57c3bb1___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::_scalar_deleting_destructor_

- ea: `0x180017060`
- end: `0x180017089`
- name: `Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_80fc5ebc6c75ae438d12ab94b57c3bb1___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::_scalar_deleting_destructor_`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001544`
- `0x180017060`

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
0x180017060  push    rbx
0x180017062  sub     rsp, 20h
0x180017066  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18001706d  mov     rbx, rcx
0x180017070  test    dl, 1
0x180017073  jz      short loc_18001707F
0x180017075  mov     edx, 28h ; '('; unsigned __int64
0x18001707a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001707f  mov     rax, rbx
0x180017082  add     rsp, 20h
0x180017086  pop     rbx
0x180017087  retn
```
