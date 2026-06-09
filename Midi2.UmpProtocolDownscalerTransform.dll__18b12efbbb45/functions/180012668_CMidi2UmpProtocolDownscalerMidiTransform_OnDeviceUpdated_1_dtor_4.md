# _CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated_::_1_::dtor$4

- ea: `0x180012668`
- end: `0x180012674`
- name: `_CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d000`

## pseudocode

```c
__int64 __fastcall CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((__int64 *)(a2 + 248));
}

```

## disassembly

```asm
0x180012668  lea     rcx, [rdx+0F8h]
0x18001266f  jmp     ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
```
