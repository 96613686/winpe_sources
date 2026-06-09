# winrt::implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::get_unknown(void)

- ea: `0x180006400`
- end: `0x18000640e`
- name: `?get_unknown@?$implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@winrt@@EEBAPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@2@XZ`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::get_unknown(
        __int64 a1)
{
  __int64 result; // rax

  result = a1 + 16;
  if ( !a1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180006400  xor     edx, edx
0x180006402  lea     rax, [rcx+10h]
0x180006406  test    rcx, rcx
0x180006409  cmovz   rax, rdx
0x18000640d  retn
```
