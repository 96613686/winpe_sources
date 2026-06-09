# _winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncAction__::_1_::dtor$1

- ea: `0x18001043b`
- end: `0x180010447`
- name: `_winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncAction__::_1_::dtor$1`
- size: `12`
- prototype: `BOOL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800065b0`

## pseudocode

```c
BOOL __fastcall winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncAction__::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return `winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncAction>'::`2'::shared_type::~shared_type((void **)(a2 + 32));
}

```

## disassembly

```asm
0x18001043b  lea     rcx, [rdx+20h]
0x180010442  jmp     ??1shared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBUIAsyncAction@Foundation@Windows@2@I@Z@QEAA@XZ
```
