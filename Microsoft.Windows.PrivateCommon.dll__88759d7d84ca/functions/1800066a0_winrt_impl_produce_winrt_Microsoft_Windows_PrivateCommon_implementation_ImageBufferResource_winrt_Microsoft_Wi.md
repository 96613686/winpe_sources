# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::RowStride(uint *)

- ea: `0x1800066a0`
- end: `0x1800066b8`
- name: `?RowStride@?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@UEAAHPEAI@Z`
- size: `24`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::RowStride(
        __int64 a1,
        _DWORD *a2)
{
  __int64 v2; // rax

  v2 = a1 + 20;
  if ( !a1 )
    v2 = 36;
  *a2 = *(_DWORD *)v2;
  return 0;
}

```

## disassembly

```asm
0x1800066a0  test    rcx, rcx
0x1800066a3  lea     rax, [rcx+14h]
0x1800066a7  mov     r8d, 24h ; '$'
0x1800066ad  cmovz   rax, r8
0x1800066b1  mov     eax, [rax]
0x1800066b3  mov     [rdx], eax
0x1800066b5  xor     eax, eax
0x1800066b7  retn
```
