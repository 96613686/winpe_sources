# winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800068f0`
- end: `0x180006975`
- name: `?QueryInterface@?$implements@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@UIImageBufferResourceFactory@3456@@winrt@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `133`
- prototype: `__int64 __fastcall(volatile signed __int64 *, const void *, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006090`
- `0x180006350`

## callees

- `0x1800068f0`
- `0x180006c90`
- `0x18000b930`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::QueryInterface(
        volatile signed __int64 *a1,
        const void *a2,
        __int64 *a3)
{
  __int64 v6; // rax
  signed __int64 v7; // rax
  signed __int64 v8; // rtt

  v6 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 48))(a1);
  *a3 = v6;
  if ( !v6 )
    return winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::query_interface_common(
             a1,
             a2,
             a3);
  v7 = *((_QWORD *)a1 + 1);
  if ( v7 < 0 )
  {
LABEL_5:
    _InterlockedIncrement((volatile signed __int32 *)(2 * v7 + 24));
  }
  else
  {
    while ( 1 )
    {
      v8 = v7;
      v7 = _InterlockedCompareExchange64(a1 + 1, v7 + 1, v7);
      if ( v8 == v7 )
        break;
      if ( v7 < 0 )
        goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800068f0  mov     [rsp+arg_0], rbx
0x1800068f5  mov     [rsp+arg_8], rsi
0x1800068fa  push    rdi
0x1800068fb  sub     rsp, 20h
0x1800068ff  mov     rax, [rcx]
0x180006902  mov     rdi, r8
0x180006905  mov     rsi, rdx
0x180006908  mov     rbx, rcx
0x18000690b  mov     rax, [rax+30h]
0x18000690f  call    cs:__guard_dispatch_icall_fptr
0x180006915  mov     [rdi], rax
0x180006918  test    rax, rax
0x18000691b  jz      short loc_180006958
0x18000691d  mov     rax, [rbx+8]
0x180006921  test    rax, rax
0x180006924  js      short loc_180006941
0x180006926  nop     word ptr [rax+rax+00000000h]
0x180006930  lea     rcx, [rax+1]
0x180006934  lock cmpxchg [rbx+8], rcx
0x18000693a  jz      short loc_180006946
0x18000693c  test    rax, rax
0x18000693f  jns     short loc_180006930
0x180006941  lock inc dword ptr [rax+rax+18h]
0x180006946  xor     eax, eax
0x180006948  mov     rbx, [rsp+28h+arg_0]
0x18000694d  mov     rsi, [rsp+28h+arg_8]
0x180006952  add     rsp, 20h
0x180006956  pop     rdi
0x180006957  retn
0x180006958  mov     r8, rdi
0x18000695b  mov     rdx, rsi
0x18000695e  mov     rcx, rbx
0x180006961  mov     rbx, [rsp+28h+arg_0]
0x180006966  mov     rsi, [rsp+28h+arg_8]
0x18000696b  add     rsp, 20h
0x18000696f  pop     rdi
0x180006970  jmp     ?query_interface_common@?$root_implements@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@UIImageBufferResourceFactory@3456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::query_interface_common(winrt::guid const &,void * *)
```
