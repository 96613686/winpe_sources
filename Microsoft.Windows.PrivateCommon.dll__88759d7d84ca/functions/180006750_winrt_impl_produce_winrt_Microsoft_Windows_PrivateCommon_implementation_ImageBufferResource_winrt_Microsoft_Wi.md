# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::get_BufferData(winrt::impl::struct_Microsoft_Windows_PrivateCommon_ImageBufferData *)

- ea: `0x180006750`
- end: `0x180006772`
- name: `?get_BufferData@?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@UEAAHPEAUstruct_Microsoft_Windows_PrivateCommon_ImageBufferData@23@@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::get_BufferData(
        __int64 a1,
        _OWORD *a2)
{
  __int64 v2; // rax
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  __int64 result; // rax

  v2 = a1 + 8;
  if ( !a1 )
    v2 = 24;
  v3 = *(_OWORD *)v2;
  v4 = *(_OWORD *)(v2 + 16);
  result = 0;
  *a2 = v3;
  a2[1] = v4;
  return result;
}

```

## disassembly

```asm
0x180006750  test    rcx, rcx
0x180006753  lea     rax, [rcx+8]
0x180006757  mov     r8d, 18h
0x18000675d  cmovz   rax, r8
0x180006761  movups  xmm0, xmmword ptr [rax]
0x180006764  movups  xmm1, xmmword ptr [rax+10h]
0x180006768  xor     eax, eax
0x18000676a  movups  xmmword ptr [rdx], xmm0
0x18000676d  movups  xmmword ptr [rdx+10h], xmm1
0x180006771  retn
```
