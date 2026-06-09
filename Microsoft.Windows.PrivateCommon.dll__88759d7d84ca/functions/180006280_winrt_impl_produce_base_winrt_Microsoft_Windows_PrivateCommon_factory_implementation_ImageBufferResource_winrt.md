# winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x180006280`
- end: `0x180006296`
- name: `?GetIids@?$produce_base@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `22`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006850`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,void>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v3; // rax

  v3 = a1 - 16;
  if ( !a1 )
    v3 = 0;
  return winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::GetIids(
           v3,
           a2,
           a3);
}

```

## disassembly

```asm
0x180006280  xor     r9d, r9d
0x180006283  lea     rax, [rcx-10h]
0x180006287  test    rcx, rcx
0x18000628a  cmovz   rax, r9
0x18000628e  mov     rcx, rax
0x180006291  jmp     ?GetIids@?$implements@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@UIImageBufferResourceFactory@3456@@winrt@@QEAAJPEAKPEAPEAU_GUID@@@Z; winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::GetIids(ulong *,_GUID * *)
```
