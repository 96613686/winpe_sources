# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::put_BufferData(winrt::impl::struct_Microsoft_Windows_PrivateCommon_ImageBufferData)

- ea: `0x180006720`
- end: `0x180006742`
- name: `?put_BufferData@?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@UEAAHUstruct_Microsoft_Windows_PrivateCommon_ImageBufferData@23@@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::put_BufferData(
        __int64 a1,
        _OWORD *a2)
{
  __int64 v2; // rax
  __int128 v3; // xmm1

  v2 = a1 + 8;
  v3 = a2[1];
  if ( !a1 )
    v2 = 24;
  *(_OWORD *)v2 = *a2;
  *(_OWORD *)(v2 + 16) = v3;
  return 0;
}

```

## disassembly

```asm
0x180006720  movups  xmm0, xmmword ptr [rdx]
0x180006723  test    rcx, rcx
0x180006726  lea     rax, [rcx+8]
0x18000672a  movups  xmm1, xmmword ptr [rdx+10h]
0x18000672e  mov     r8d, 18h
0x180006734  cmovz   rax, r8
0x180006738  movups  xmmword ptr [rax], xmm0
0x18000673b  movups  xmmword ptr [rax+10h], xmm1
0x18000673f  xor     eax, eax
0x180006741  retn
```
