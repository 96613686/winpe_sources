# _winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::dtor$3

- ea: `0x18000bae4`
- end: `0x18000baf0`
- name: `_winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180006814`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return winrt::Windows::Foundation::IAsyncOperation<unsigned int>::~IAsyncOperation<unsigned int>(a2 + 88);
}

```

## disassembly

```asm
0x18000bae4  lea     rcx, [rdx+58h]
0x18000baeb  jmp     ??1?$IAsyncOperation@I@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<uint>::~IAsyncOperation<uint>(void)
```
