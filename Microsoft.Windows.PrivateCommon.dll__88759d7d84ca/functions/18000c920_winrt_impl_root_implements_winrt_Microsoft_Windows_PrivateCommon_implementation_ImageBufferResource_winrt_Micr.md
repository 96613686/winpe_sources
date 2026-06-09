# _winrt::impl::root_implements_winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource_::NonDelegatingGetTrustLevel_::_1_::catch$0

- ea: `0x18000c920`
- end: `0x18000c94c`
- name: `_winrt::impl::root_implements_winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource_::NonDelegatingGetTrustLevel_::_1_::catch$0`
- size: `44`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001d30`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements_winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource_::NonDelegatingGetTrustLevel_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 48) = *winrt::to_hresult((_DWORD *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x18000c920  mov     [rsp+arg_8], rdx
0x18000c925  push    rbp
0x18000c926  sub     rsp, 20h
0x18000c92a  mov     rbp, rdx
0x18000c92d  lea     rcx, [rbp+30h]
0x18000c931  call    ?to_hresult@winrt@@YA?AUhresult@1@XZ; winrt::to_hresult(void)
0x18000c936  mov     ecx, [rax]
0x18000c938  mov     [rbp+30h], ecx
0x18000c93b  mov     rax, 0
0x18000c945  add     rsp, 20h
0x18000c949  pop     rbp
0x18000c94a  retn
```
