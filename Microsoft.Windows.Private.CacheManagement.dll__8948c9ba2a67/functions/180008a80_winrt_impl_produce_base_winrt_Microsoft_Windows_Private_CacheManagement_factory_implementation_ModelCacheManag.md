# winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,void>::AddRef(void)

- ea: `0x180008a80`
- end: `0x180008ac2`
- name: `?AddRef@?$produce_base@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@57@X@impl@winrt@@UEAAIXZ`
- size: `66`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008a80`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,void>::AddRef(
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
0x180008a80  test    rcx, rcx
0x180008a83  lea     rdx, [rcx-8]
0x180008a87  mov     eax, 8
0x180008a8c  cmovz   rdx, rax
0x180008a90  mov     rax, [rdx]
0x180008a93  test    rax, rax
0x180008a96  js      short loc_180008AB0
0x180008a98  nop     dword ptr [rax+rax+00000000h]
0x180008aa0  lea     rcx, [rax+1]
0x180008aa4  lock cmpxchg [rdx], rcx
0x180008aa9  jz      short loc_180008ABF
0x180008aab  test    rax, rax
0x180008aae  jns     short loc_180008AA0
0x180008ab0  mov     ecx, 1
0x180008ab5  lock xadd [rax+rax+18h], ecx
0x180008abb  lea     eax, [rcx+1]
0x180008abe  retn
0x180008abf  mov     eax, ecx
0x180008ac1  retn
```
