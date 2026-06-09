# winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource,void>::QueryInterface(winrt::guid const &,void * *)

- ea: `0x180006550`
- end: `0x1800065dd`
- name: `?QueryInterface@?$produce_base@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@X@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `141`
- prototype: `__int64 __fastcall(__int64, const void *, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006550`
- `0x180006c90`
- `0x18000b930`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource,void>::QueryInterface(
        __int64 a1,
        const void *a2,
        __int64 *a3)
{
  volatile signed __int64 *v3; // rbx
  __int64 v6; // rax
  signed __int64 v7; // rax
  signed __int64 v8; // rtt

  v3 = (volatile signed __int64 *)(a1 - 16);
  if ( !a1 )
    v3 = 0;
  v6 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*v3 + 48))(v3);
  *a3 = v6;
  if ( !v6 )
    return winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::query_interface_common(
             v3,
             a2,
             a3);
  v7 = *((_QWORD *)v3 + 1);
  if ( v7 < 0 )
  {
LABEL_7:
    _InterlockedIncrement((volatile signed __int32 *)(2 * v7 + 24));
  }
  else
  {
    while ( 1 )
    {
      v8 = v7;
      v7 = _InterlockedCompareExchange64(v3 + 1, v7 + 1, v7);
      if ( v8 == v7 )
        break;
      if ( v7 < 0 )
        goto LABEL_7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006550  mov     [rsp+arg_0], rbx
0x180006555  mov     [rsp+arg_8], rbp
0x18000655a  mov     [rsp+arg_10], rsi
0x18000655f  push    rdi
0x180006560  sub     rsp, 20h
0x180006564  lea     rbx, [rcx-10h]
0x180006568  xor     ebp, ebp
0x18000656a  test    rcx, rcx
0x18000656d  mov     rdi, r8
0x180006570  mov     rsi, rdx
0x180006573  cmovz   rbx, rbp
0x180006577  mov     rcx, rbx
0x18000657a  mov     rax, [rbx]
0x18000657d  mov     rax, [rax+30h]
0x180006581  call    cs:__guard_dispatch_icall_fptr
0x180006587  mov     [rdi], rax
0x18000658a  test    rax, rax
0x18000658d  jz      short loc_1800065BA
0x18000658f  mov     rax, [rbx+8]
0x180006593  test    rax, rax
0x180006596  js      short loc_1800065B1
0x180006598  nop     dword ptr [rax+rax+00000000h]
0x1800065a0  lea     rcx, [rax+1]
0x1800065a4  lock cmpxchg [rbx+8], rcx
0x1800065aa  jz      short loc_1800065B6
0x1800065ac  test    rax, rax
0x1800065af  jns     short loc_1800065A0
0x1800065b1  lock inc dword ptr [rax+rax+18h]
0x1800065b6  mov     eax, ebp
0x1800065b8  jmp     short loc_1800065C8
0x1800065ba  mov     r8, rdi
0x1800065bd  mov     rdx, rsi
0x1800065c0  mov     rcx, rbx
0x1800065c3  call    ?query_interface_common@?$root_implements@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@UIImageBufferResourceFactory@3456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::query_interface_common(winrt::guid const &,void * *)
0x1800065c8  mov     rbx, [rsp+28h+arg_0]
0x1800065cd  mov     rbp, [rsp+28h+arg_8]
0x1800065d2  mov     rsi, [rsp+28h+arg_10]
0x1800065d7  add     rsp, 20h
0x1800065db  pop     rdi
0x1800065dc  retn
```
