# winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource,void>::AddRef(void)

- ea: `0x180006300`
- end: `0x180006342`
- name: `?AddRef@?$produce_base@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@X@impl@winrt@@UEAAIXZ`
- size: `66`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006300`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource,void>::AddRef(
        __int64 a1)
{
  __int64 v1; // rdx
  signed __int64 v2; // rax
  unsigned int v3; // ecx
  signed __int64 v4; // rtt

  v1 = a1 - 8;
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
0x180006300  test    rcx, rcx
0x180006303  lea     rdx, [rcx-8]
0x180006307  mov     eax, 8
0x18000630c  cmovz   rdx, rax
0x180006310  mov     rax, [rdx]
0x180006313  test    rax, rax
0x180006316  js      short loc_180006330
0x180006318  nop     dword ptr [rax+rax+00000000h]
0x180006320  lea     rcx, [rax+1]
0x180006324  lock cmpxchg [rdx], rcx
0x180006329  jz      short loc_18000633F
0x18000632b  test    rax, rax
0x18000632e  jns     short loc_180006320
0x180006330  mov     ecx, 1
0x180006335  lock xadd [rax+rax+18h], ecx
0x18000633b  lea     eax, [rcx+1]
0x18000633e  retn
0x18000633f  mov     eax, ecx
0x180006341  retn
```
