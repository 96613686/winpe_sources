# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::PixelFormat(int *)

- ea: `0x1800065e0`
- end: `0x1800065f8`
- name: `?PixelFormat@?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@UEAAHPEAH@Z`
- size: `24`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::PixelFormat(
        __int64 a1,
        _DWORD *a2)
{
  __int64 v2; // rax

  v2 = a1 + 16;
  if ( !a1 )
    v2 = 32;
  *a2 = *(_DWORD *)v2;
  return 0;
}

```

## disassembly

```asm
0x1800065e0  test    rcx, rcx
0x1800065e3  lea     rax, [rcx+10h]
0x1800065e7  mov     r8d, 20h ; ' '
0x1800065ed  cmovz   rax, r8
0x1800065f1  mov     eax, [rax]
0x1800065f3  mov     [rdx], eax
0x1800065f5  xor     eax, eax
0x1800065f7  retn
```
