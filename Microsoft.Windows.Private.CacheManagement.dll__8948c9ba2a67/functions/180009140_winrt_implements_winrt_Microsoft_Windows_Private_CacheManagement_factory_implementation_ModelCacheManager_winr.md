# winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>::find_interface(winrt::guid const &)

- ea: `0x180009140`
- end: `0x180009196`
- name: `?find_interface@?$implements@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@57@UIModelCacheManagerStatics@34567@@winrt@@UEBAPEAXAEBUguid@2@@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009140`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>::find_interface(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory> && a2[1] == 0x46000000000000C0LL )
  {
    result = a1 + 16;
    if ( !a1 )
      return 0;
  }
  else if ( *a2 == winrt::impl::guid_v<winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>
         && a2[1] == 0xD697D5A1EF3AE590uLL )
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
0x180009140  mov     rax, [rdx]
0x180009143  mov     r8, rcx
0x180009146  cmp     rax, cs:??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IActivationFactory>
0x18000914d  jnz     short loc_18000916A
0x18000914f  mov     rax, [rdx+8]
0x180009153  cmp     rax, cs:qword_180025FC0
0x18000915a  jnz     short loc_18000916A
0x18000915c  lea     rax, [rcx+10h]
0x180009160  xor     ecx, ecx
0x180009162  test    r8, r8
0x180009165  cmovz   rax, rcx
0x180009169  retn
0x18000916a  mov     rax, [rdx]
0x18000916d  cmp     rax, cs:??$guid_v@UIModelCacheManagerStatics@CacheManagement@Private@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>
0x180009174  jnz     short loc_180009191
0x180009176  mov     rax, [rdx+8]
0x18000917a  cmp     rax, cs:qword_180025FF0
0x180009181  jnz     short loc_180009191
0x180009183  lea     rax, [rcx+18h]
0x180009187  xor     ecx, ecx
0x180009189  test    r8, r8
0x18000918c  cmovz   rax, rcx
0x180009190  retn
0x180009191  xor     ecx, ecx
0x180009193  mov     eax, ecx
0x180009195  retn
```
