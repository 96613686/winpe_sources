# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::Height(uint *)

- ea: `0x1800066c0`
- end: `0x1800066d8`
- name: `?Height@?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@UEAAHPEAI@Z`
- size: `24`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::Height(
        __int64 a1,
        _DWORD *a2)
{
  __int64 v2; // rax

  v2 = a1 + 8;
  if ( !a1 )
    v2 = 24;
  *a2 = *(_DWORD *)v2;
  return 0;
}

```

## disassembly

```asm
0x1800066c0  test    rcx, rcx
0x1800066c3  lea     rax, [rcx+8]
0x1800066c7  mov     r8d, 18h
0x1800066cd  cmovz   rax, r8
0x1800066d1  mov     eax, [rax]
0x1800066d3  mov     [rdx], eax
0x1800066d5  xor     eax, eax
0x1800066d7  retn
```
