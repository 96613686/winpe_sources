# winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::find_interface(winrt::guid const &)

- ea: `0x180006430`
- end: `0x180006486`
- name: `?find_interface@?$implements@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@UIImageBufferResourceFactory@3456@@winrt@@UEBAPEAXAEBUguid@2@@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006430`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::find_interface(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory> && a2[1] == 0x46000000000000C0LL )
  {
    result = a1 + 16;
    if ( !a1 )
      return 0;
  }
  else if ( *a2 == winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>
         && a2[1] == 0xB64BCFE6589C9C8BuLL )
  {
    result = a1 + 24;
    if ( !a1 )
      return 0;
  }
  else
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006430  mov     rax, [rdx]
0x180006433  mov     r8, rcx
0x180006436  cmp     rax, cs:??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory>
0x18000643d  jnz     short loc_18000645A
0x18000643f  mov     rax, [rdx+8]
0x180006443  cmp     rax, cs:qword_18000EC00
0x18000644a  jnz     short loc_18000645A
0x18000644c  lea     rax, [rcx+10h]
0x180006450  xor     ecx, ecx
0x180006452  test    r8, r8
0x180006455  cmovz   rax, rcx
0x180006459  retn
0x18000645a  mov     rax, [rdx]
0x18000645d  cmp     rax, cs:??$guid_v@UIImageBufferResourceFactory@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>
0x180006464  jnz     short loc_180006481
0x180006466  mov     rax, [rdx+8]
0x18000646a  cmp     rax, cs:qword_18000EC80
0x180006471  jnz     short loc_180006481
0x180006473  lea     rax, [rcx+18h]
0x180006477  xor     ecx, ecx
0x180006479  test    r8, r8
0x18000647c  cmovz   rax, rcx
0x180006480  retn
0x180006481  xor     ecx, ecx
0x180006483  mov     eax, ecx
0x180006485  retn
```
