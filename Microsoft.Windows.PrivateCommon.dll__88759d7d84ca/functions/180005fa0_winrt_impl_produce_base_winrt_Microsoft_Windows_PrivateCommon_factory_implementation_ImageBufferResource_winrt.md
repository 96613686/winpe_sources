# winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory,void>::GetRuntimeClassName(void * *)

- ea: `0x180005fa0`
- end: `0x180005fb6`
- name: `?GetRuntimeClassName@?$produce_base@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResourceFactory@3456@X@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `22`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006ae0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory,void>::GetRuntimeClassName(
        __int64 a1)
{
  __int64 v1; // rax

  v1 = a1 - 24;
  if ( !a1 )
    v1 = 0;
  return winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::NonDelegatingGetRuntimeClassName(v1);
}

```

## disassembly

```asm
0x180005fa0  xor     r8d, r8d
0x180005fa3  lea     rax, [rcx-18h]
0x180005fa7  test    rcx, rcx
0x180005faa  cmovz   rax, r8
0x180005fae  mov     rcx, rax
0x180005fb1  jmp     ?NonDelegatingGetRuntimeClassName@?$root_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@impl@winrt@@IEAAHPEAPEAX@Z; winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::NonDelegatingGetRuntimeClassName(void * *)
```
