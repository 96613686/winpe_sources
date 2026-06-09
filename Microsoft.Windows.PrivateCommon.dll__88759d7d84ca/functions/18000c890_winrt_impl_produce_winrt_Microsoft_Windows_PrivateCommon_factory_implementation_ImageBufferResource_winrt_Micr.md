# _winrt::impl::produce_winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory_::CreateInstance_::_1_::dtor$3

- ea: `0x18000c890`
- end: `0x18000c8ad`
- name: `_winrt::impl::produce_winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory_::CreateInstance_::_1_::dtor$3`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007660`

## pseudocode

```c
void __fastcall winrt::impl::produce_winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory_::CreateInstance_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x18000c890  push    rbp
0x18000c892  sub     rsp, 20h
0x18000c896  mov     rbp, rdx
0x18000c899  mov     edx, 40h ; '@'; unsigned __int64
0x18000c89e  mov     rcx, [rbp+20h]; void *
0x18000c8a2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c8a7  add     rsp, 20h
0x18000c8ab  pop     rbp
0x18000c8ac  retn
```
