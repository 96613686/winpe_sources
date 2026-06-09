# winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::find_interface(winrt::guid const &)

- ea: `0x180009550`
- end: `0x1800095a6`
- name: `?find_interface@?$implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@winrt@@UEBAPEAXAEBUguid@2@@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009550`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::find_interface(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( *a2 == winrt::impl::guid_v<winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>
    && a2[1] == 0xBB7E3121B1D2EF9AuLL )
  {
    result = a1 + 16;
    if ( !a1 )
      return 0;
  }
  else if ( *a2 == winrt::impl::guid_v<winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>
         && a2[1] == 0x290D4D1A1988AC97LL )
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
0x180009550  mov     rax, [rdx]
0x180009553  mov     r8, rcx
0x180009556  cmp     rax, cs:??$guid_v@UIModelCacheManager@CacheManagement@Private@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>
0x18000955d  jnz     short loc_18000957A
0x18000955f  mov     rax, [rdx+8]
0x180009563  cmp     rax, cs:qword_180026010
0x18000956a  jnz     short loc_18000957A
0x18000956c  lea     rax, [rcx+10h]
0x180009570  xor     ecx, ecx
0x180009572  test    r8, r8
0x180009575  cmovz   rax, rcx
0x180009579  retn
0x18000957a  mov     rax, [rdx]
0x18000957d  cmp     rax, cs:??$guid_v@UIModelCacheManager2@CacheManagement@Private@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>
0x180009584  jnz     short loc_1800095A1
0x180009586  mov     rax, [rdx+8]
0x18000958a  cmp     rax, cs:qword_180026000
0x180009591  jnz     short loc_1800095A1
0x180009593  lea     rax, [rcx+18h]
0x180009597  xor     ecx, ecx
0x180009599  test    r8, r8
0x18000959c  cmovz   rax, rcx
0x1800095a0  retn
0x1800095a1  xor     ecx, ecx
0x1800095a3  mov     eax, ecx
0x1800095a5  retn
```
