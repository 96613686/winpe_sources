# _winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::dtor$2

- ea: `0x18000bace`
- end: `0x18000bade`
- name: `_winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::dtor$2`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180006a0c`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type::~promise_type(*(_QWORD *)(a2 + 80) - 112LL);
}

```

## disassembly

```asm
0x18000bace  mov     rcx, [rdx+50h]
0x18000bad5  sub     rcx, 70h ; 'p'
0x18000bad9  jmp     ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@UEAA@XZ; std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type::~promise_type(void)
```
