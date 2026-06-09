# winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory,void>::AddRef(void)

- ea: `0x180006040`
- end: `0x180006082`
- name: `?AddRef@?$produce_base@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResourceFactory@3456@X@impl@winrt@@UEAAIXZ`
- size: `66`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006040`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory,void>::AddRef(
        __int64 a1)
{
  __int64 v1; // rdx
  signed __int64 v2; // rax
  unsigned int v3; // ecx
  signed __int64 v4; // rtt

  v1 = a1 - 16;
  if ( !a1 )
    v1 = 8;
  v2 = *(_QWORD *)v1;
  if ( *(__int64 *)v1 < 0 )
    return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(2 * v2 + 24));
  while ( 1 )
  {
    v3 = v2 + 1;
    v4 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)v1, v2 + 1, v2);
    if ( v4 == v2 )
      break;
    if ( v2 < 0 )
      return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(2 * v2 + 24));
  }
  return v3;
}

```

## disassembly

```asm
0x180006040  test    rcx, rcx
0x180006043  lea     rdx, [rcx-10h]
0x180006047  mov     eax, 8
0x18000604c  cmovz   rdx, rax
0x180006050  mov     rax, [rdx]
0x180006053  test    rax, rax
0x180006056  js      short loc_180006070
0x180006058  nop     dword ptr [rax+rax+00000000h]
0x180006060  lea     rcx, [rax+1]
0x180006064  lock cmpxchg [rdx], rcx
0x180006069  jz      short loc_18000607F
0x18000606b  test    rax, rax
0x18000606e  jns     short loc_180006060
0x180006070  mov     ecx, 1
0x180006075  lock xadd [rax+rax+18h], ecx
0x18000607b  lea     eax, [rcx+1]
0x18000607e  retn
0x18000607f  mov     eax, ecx
0x180006081  retn
```
