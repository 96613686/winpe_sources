# _winrt::impl::produce_winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory_::CreateInstance_::_1_::catch$16

- ea: `0x18000c8b9`
- end: `0x18000c8e5`
- name: `_winrt::impl::produce_winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory_::CreateInstance_::_1_::catch$16`
- size: `44`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001d30`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory_::CreateInstance_::_1_::catch_16(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 32) = *winrt::to_hresult((_DWORD *)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18000c8b9  mov     [rsp+arg_8], rdx
0x18000c8be  push    rbp
0x18000c8bf  sub     rsp, 20h
0x18000c8c3  mov     rbp, rdx
0x18000c8c6  lea     rcx, [rbp+20h]
0x18000c8ca  call    ?to_hresult@winrt@@YA?AUhresult@1@XZ; winrt::to_hresult(void)
0x18000c8cf  mov     ecx, [rax]
0x18000c8d1  mov     [rbp+20h], ecx
0x18000c8d4  mov     rax, 0
0x18000c8de  add     rsp, 20h
0x18000c8e2  pop     rbp
0x18000c8e3  retn
```
