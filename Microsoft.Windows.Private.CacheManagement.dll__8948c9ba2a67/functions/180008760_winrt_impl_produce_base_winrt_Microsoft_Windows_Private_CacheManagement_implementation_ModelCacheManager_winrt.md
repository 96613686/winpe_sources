# winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2,void>::AddRef(void)

- ea: `0x180008760`
- end: `0x1800087a2`
- name: `?AddRef@?$produce_base@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManager2@34567@X@impl@winrt@@UEAAIXZ`
- size: `66`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008760`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2,void>::AddRef(
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
0x180008760  test    rcx, rcx
0x180008763  lea     rdx, [rcx-10h]
0x180008767  mov     eax, 8
0x18000876c  cmovz   rdx, rax
0x180008770  mov     rax, [rdx]
0x180008773  test    rax, rax
0x180008776  js      short loc_180008790
0x180008778  nop     dword ptr [rax+rax+00000000h]
0x180008780  lea     rcx, [rax+1]
0x180008784  lock cmpxchg [rdx], rcx
0x180008789  jz      short loc_18000879F
0x18000878b  test    rax, rax
0x18000878e  jns     short loc_180008780
0x180008790  mov     ecx, 1
0x180008795  lock xadd [rax+rax+18h], ecx
0x18000879b  lea     eax, [rcx+1]
0x18000879e  retn
0x18000879f  mov     eax, ecx
0x1800087a1  retn
```
