# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::Capacity(uint *)

- ea: `0x180006600`
- end: `0x18000662f`
- name: `?Capacity@?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@UEAAHPEAI@Z`
- size: `47`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005d90`
- `0x180006600`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::Capacity(
        __int64 a1,
        _DWORD *a2)
{
  winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource *v3; // rcx
  __int64 result; // rax
  int v5; // [rsp+30h] [rbp+8h] BYREF

  v3 = (winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource *)(a1 - 16);
  if ( !a1 )
    v3 = 0;
  try
  {
    *a2 = winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::Capacity(v3);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v5);
  }
  return result;
}

```

## disassembly

```asm
0x180006600  push    rbx
0x180006602  sub     rsp, 20h
0x180006606  mov     rbx, rdx
0x180006609  mov     rax, rcx
0x18000660c  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180006610  xor     edx, edx
0x180006612  test    rax, rax
0x180006615  cmovz   rcx, rdx; this
0x180006619  call    ?Capacity@ImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@QEAAIXZ; winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::Capacity(void)
0x18000661e  mov     [rbx], eax
0x180006620  xor     eax, eax
0x180006622  jmp     short loc_180006628
0x180006624  mov     eax, [rsp+28h+arg_0]
0x180006628  add     rsp, 20h
0x18000662c  pop     rbx
0x18000662d  retn
```
