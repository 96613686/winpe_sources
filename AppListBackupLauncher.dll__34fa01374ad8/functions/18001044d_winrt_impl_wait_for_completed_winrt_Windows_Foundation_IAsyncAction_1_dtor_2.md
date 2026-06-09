# _winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncAction__::_1_::dtor$2

- ea: `0x18001044d`
- end: `0x180010459`
- name: `_winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncAction__::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005b54`

## pseudocode

```c
void __fastcall winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncAction__::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)(a2 + 32));
}

```

## disassembly

```asm
0x18001044d  lea     rcx, [rdx+20h]; this
0x180010454  jmp     ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
```
