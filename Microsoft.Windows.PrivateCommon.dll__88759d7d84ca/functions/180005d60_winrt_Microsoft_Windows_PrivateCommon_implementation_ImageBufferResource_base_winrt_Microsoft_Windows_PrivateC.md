# winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,>::~ImageBufferResource_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,>(void)

- ea: `0x180005d60`
- end: `0x180005d8b`
- name: `??1?$ImageBufferResource_base@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@$$V@implementation@PrivateCommon@Windows@Microsoft@winrt@@UEAA@XZ`
- size: `43`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c8ad`

## callees

- `0x180005d60`
- `0x1800067d0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005d84`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005d84`

## pseudocode

```c
__int64 winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,>::~ImageBufferResource_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,>()
{
  __int64 result; // rax

  winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::subtract_final_reference();
  result = (unsigned int)_InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock);
  if ( (int)result < 0 )
    abort();
  return result;
}

```

## disassembly

```asm
0x180005d60  sub     rsp, 28h
0x180005d64  call    ?subtract_final_reference@?$root_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::subtract_final_reference(void)
0x180005d69  mov     eax, 0FFFFFFFFh
0x180005d6e  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180005d76  sub     eax, 1
0x180005d79  jnz     short loc_180005D80
0x180005d7b  add     rsp, 28h
0x180005d7f  retn
0x180005d80  test    eax, eax
0x180005d82  jns     short loc_180005D7B
0x180005d84  call    cs:__imp_abort
```
