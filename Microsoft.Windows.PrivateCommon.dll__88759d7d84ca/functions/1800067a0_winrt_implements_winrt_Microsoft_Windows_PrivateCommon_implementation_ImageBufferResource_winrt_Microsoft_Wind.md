# winrt::implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::find_interface(winrt::guid const &)

- ea: `0x1800067a0`
- end: `0x1800067cf`
- name: `?find_interface@?$implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@winrt@@UEBAPEAXAEBUguid@2@@Z`
- size: `47`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800067a0`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::find_interface(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( *a2 != winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>
    || a2[1] != 0x9693862160F5D4BCuLL )
  {
    return 0;
  }
  result = a1 + 16;
  if ( !a1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800067a0  mov     rax, [rdx]
0x1800067a3  mov     r8, rcx
0x1800067a6  cmp     rax, cs:??$guid_v@UIImageBufferResource@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>
0x1800067ad  jnz     short loc_1800067CA
0x1800067af  mov     rax, [rdx+8]
0x1800067b3  cmp     rax, cs:qword_18000EC70
0x1800067ba  jnz     short loc_1800067CA
0x1800067bc  lea     rax, [rcx+10h]
0x1800067c0  xor     ecx, ecx
0x1800067c2  test    r8, r8
0x1800067c5  cmovz   rax, rcx
0x1800067c9  retn
0x1800067ca  xor     ecx, ecx
0x1800067cc  mov     eax, ecx
0x1800067ce  retn
```
