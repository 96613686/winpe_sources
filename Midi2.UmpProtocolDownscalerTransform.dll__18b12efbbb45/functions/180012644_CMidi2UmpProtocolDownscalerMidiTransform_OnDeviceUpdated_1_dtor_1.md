# _CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated_::_1_::dtor$1

- ea: `0x180012644`
- end: `0x180012650`
- name: `_CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d000`

## pseudocode

```c
__int64 __fastcall CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(*(__int64 **)(a2 + 232));
}

```

## disassembly

```asm
0x180012644  mov     rcx, [rdx+0E8h]
0x18001264b  jmp     ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
```
