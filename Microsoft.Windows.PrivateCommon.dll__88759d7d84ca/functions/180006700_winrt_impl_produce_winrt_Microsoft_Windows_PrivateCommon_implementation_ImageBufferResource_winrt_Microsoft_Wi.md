# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::Buffer(unsigned __int64 *)

- ea: `0x180006700`
- end: `0x18000671a`
- name: `?Buffer@?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@UEAAHPEA_K@Z`
- size: `26`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::Buffer(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // rax

  v2 = a1 + 40;
  if ( !a1 )
    v2 = 56;
  *a2 = *(_QWORD *)v2;
  return 0;
}

```

## disassembly

```asm
0x180006700  test    rcx, rcx
0x180006703  lea     rax, [rcx+28h]
0x180006707  mov     r8d, 38h ; '8'
0x18000670d  cmovz   rax, r8
0x180006711  mov     rax, [rax]
0x180006714  mov     [rdx], rax
0x180006717  xor     eax, eax
0x180006719  retn
```
