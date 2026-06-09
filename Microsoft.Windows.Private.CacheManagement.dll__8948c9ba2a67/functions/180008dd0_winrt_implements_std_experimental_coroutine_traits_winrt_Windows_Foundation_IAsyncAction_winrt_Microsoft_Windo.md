# winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::find_interface(winrt::guid const &)

- ea: `0x180008dd0`
- end: `0x180008e26`
- name: `?find_interface@?$implements@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@678@@winrt@@UEBAPEAXAEBUguid@2@@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008dd0`

## pseudocode

```c
__int64 __fastcall winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::find_interface(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncAction> && a2[1] == 0x7BADDFE5269D5B86LL )
  {
    result = a1 + 16;
    if ( !a1 )
      return 0;
  }
  else if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncInfo> && a2[1] == 0x46000000000000C0LL )
  {
    result = a1 + 24;
    if ( !a1 )
      return 0;
  }
  else
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008dd0  mov     rax, [rdx]
0x180008dd3  mov     r8, rcx
0x180008dd6  cmp     rax, cs:??$guid_v@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncAction>
0x180008ddd  jnz     short loc_180008DFA
0x180008ddf  mov     rax, [rdx+8]
0x180008de3  cmp     rax, cs:qword_180025B68
0x180008dea  jnz     short loc_180008DFA
0x180008dec  lea     rax, [rcx+10h]
0x180008df0  xor     ecx, ecx
0x180008df2  test    r8, r8
0x180008df5  cmovz   rax, rcx
0x180008df9  retn
0x180008dfa  mov     rax, [rdx]
0x180008dfd  cmp     rax, cs:??$guid_v@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncInfo>
0x180008e04  jnz     short loc_180008E21
0x180008e06  mov     rax, [rdx+8]
0x180008e0a  cmp     rax, cs:qword_180025B58
0x180008e11  jnz     short loc_180008E21
0x180008e13  lea     rax, [rcx+18h]
0x180008e17  xor     ecx, ecx
0x180008e19  test    r8, r8
0x180008e1c  cmovz   rax, rcx
0x180008e20  retn
0x180008e21  xor     ecx, ecx
0x180008e23  mov     eax, ecx
0x180008e25  retn
```
