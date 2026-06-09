# _winrt::impl::root_implements_winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource_::NonDelegatingGetRuntimeClassName_::_1_::catch$2

- ea: `0x18000c8f0`
- end: `0x18000c91c`
- name: `_winrt::impl::root_implements_winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource_::NonDelegatingGetRuntimeClassName_::_1_::catch$2`
- size: `44`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001d30`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements_winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource_::NonDelegatingGetRuntimeClassName_::_1_::catch_2(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 32) = *winrt::to_hresult((_DWORD *)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18000c8f0  mov     [rsp+arg_8], rdx
0x18000c8f5  push    rbp
0x18000c8f6  sub     rsp, 20h
0x18000c8fa  mov     rbp, rdx
0x18000c8fd  lea     rcx, [rbp+20h]
0x18000c901  call    ?to_hresult@winrt@@YA?AUhresult@1@XZ; winrt::to_hresult(void)
0x18000c906  mov     ecx, [rax]
0x18000c908  mov     [rbp+20h], ecx
0x18000c90b  mov     rax, 0
0x18000c915  add     rsp, 20h
0x18000c919  pop     rbp
0x18000c91a  retn
```
