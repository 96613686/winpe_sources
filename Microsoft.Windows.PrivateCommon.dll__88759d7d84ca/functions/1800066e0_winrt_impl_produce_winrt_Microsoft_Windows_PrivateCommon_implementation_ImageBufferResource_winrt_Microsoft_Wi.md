# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::Width(uint *)

- ea: `0x1800066e0`
- end: `0x1800066f8`
- name: `?Width@?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@UEAAHPEAI@Z`
- size: `24`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::Width(
        __int64 a1,
        _DWORD *a2)
{
  __int64 v2; // rax

  v2 = a1 + 12;
  if ( !a1 )
    v2 = 28;
  *a2 = *(_DWORD *)v2;
  return 0;
}

```

## disassembly

```asm
0x1800066e0  test    rcx, rcx
0x1800066e3  lea     rax, [rcx+0Ch]
0x1800066e7  mov     r8d, 1Ch
0x1800066ed  cmovz   rax, r8
0x1800066f1  mov     eax, [rax]
0x1800066f3  mov     [rdx], eax
0x1800066f5  xor     eax, eax
0x1800066f7  retn
```
