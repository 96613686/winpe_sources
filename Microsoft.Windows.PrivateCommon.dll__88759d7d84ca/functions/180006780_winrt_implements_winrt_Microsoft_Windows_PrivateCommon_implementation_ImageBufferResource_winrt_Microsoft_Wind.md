# winrt::implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::get_local_iids(void)

- ea: `0x180006780`
- end: `0x180006795`
- name: `?get_local_iids@?$implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@winrt@@UEBA?AU?$pair@IPEBUguid@winrt@@@std@@XZ`
- size: `21`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::get_local_iids(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)a2 = 1;
  *(_QWORD *)(a2 + 8) = winrt::impl::uncloaked_iids<winrt::impl::interface_list<winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>>::value;
  return a2;
}

```

## disassembly

```asm
0x180006780  lea     rax, ?value@?$uncloaked_iids@U?$interface_list@UImageBufferResource@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@@impl@winrt@@2V?$array@Uguid@winrt@@$00@std@@B; std::array<winrt::guid,1> const winrt::impl::uncloaked_iids<winrt::impl::interface_list<winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>>::value
0x180006787  mov     dword ptr [rdx], 1
0x18000678d  mov     [rdx+8], rax
0x180006791  mov     rax, rdx
0x180006794  retn
```
