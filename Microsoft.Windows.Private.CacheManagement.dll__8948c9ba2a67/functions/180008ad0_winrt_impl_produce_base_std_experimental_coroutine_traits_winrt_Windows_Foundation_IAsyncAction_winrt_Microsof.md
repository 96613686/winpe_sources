# winrt::impl::produce_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::QueryInterface(winrt::guid const &,void * *)

- ea: `0x180008ad0`
- end: `0x180008b62`
- name: `?QueryInterface@?$produce_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `146`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008ad0`
- `0x18000bb30`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::QueryInterface(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  volatile signed __int64 *v3; // r9
  volatile signed __int64 *v4; // rax
  signed __int64 v5; // rax
  signed __int64 v6; // rtt

  v3 = (volatile signed __int64 *)(a1 - 16);
  if ( !a1 )
    v3 = 0;
  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncAction> && a2[1] == 0x7BADDFE5269D5B86LL )
  {
    v4 = v3 + 2;
    if ( !v3 )
      v4 = 0;
  }
  else if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncInfo> && a2[1] == 0x46000000000000C0LL )
  {
    v4 = v3 + 3;
    if ( !v3 )
      v4 = 0;
  }
  else
  {
    v4 = 0;
  }
  *a3 = (__int64)v4;
  if ( !v4 )
    return winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::query_interface_common(
             v3,
             a2,
             a3);
  v5 = *((_QWORD *)v3 + 1);
  if ( v5 < 0 )
  {
LABEL_18:
    _InterlockedIncrement((volatile signed __int32 *)(2 * v5 + 24));
  }
  else
  {
    while ( 1 )
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange64(v3 + 1, v5 + 1, v5);
      if ( v6 == v5 )
        break;
      if ( v5 < 0 )
        goto LABEL_18;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008ad0  mov     rax, [rdx]
0x180008ad3  lea     r9, [rcx-10h]
0x180008ad7  xor     r10d, r10d
0x180008ada  test    rcx, rcx
0x180008add  cmovz   r9, r10
0x180008ae1  cmp     rax, cs:??$guid_v@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncAction>
0x180008ae8  jnz     short loc_180008B04
0x180008aea  mov     rax, [rdx+8]
0x180008aee  cmp     rax, cs:qword_180025B68
0x180008af5  jnz     short loc_180008B04
0x180008af7  test    r9, r9
0x180008afa  lea     rax, [r9+10h]
0x180008afe  cmovz   rax, r10
0x180008b02  jmp     short loc_180008B2D
0x180008b04  mov     rax, [rdx]
0x180008b07  cmp     rax, cs:??$guid_v@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncInfo>
0x180008b0e  jnz     short loc_180008B2A
0x180008b10  mov     rax, [rdx+8]
0x180008b14  cmp     rax, cs:qword_180025B58
0x180008b1b  jnz     short loc_180008B2A
0x180008b1d  test    r9, r9
0x180008b20  lea     rax, [r9+18h]
0x180008b24  cmovz   rax, r10
0x180008b28  jmp     short loc_180008B2D
0x180008b2a  mov     rax, r10
0x180008b2d  mov     [r8], rax
0x180008b30  test    rax, rax
0x180008b33  jz      short loc_180008B5A
0x180008b35  mov     rax, [r9+8]
0x180008b39  test    rax, rax
0x180008b3c  js      short loc_180008B51
0x180008b3e  xchg    ax, ax
0x180008b40  lea     rcx, [rax+1]
0x180008b44  lock cmpxchg [r9+8], rcx
0x180008b4a  jz      short loc_180008B56
0x180008b4c  test    rax, rax
0x180008b4f  jns     short loc_180008B40
0x180008b51  lock inc dword ptr [rax+rax+18h]
0x180008b56  mov     eax, r10d
0x180008b59  retn
0x180008b5a  mov     rcx, r9
0x180008b5d  jmp     ?query_interface_common@?$root_implements@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::query_interface_common(winrt::guid const &,void * *)
```
