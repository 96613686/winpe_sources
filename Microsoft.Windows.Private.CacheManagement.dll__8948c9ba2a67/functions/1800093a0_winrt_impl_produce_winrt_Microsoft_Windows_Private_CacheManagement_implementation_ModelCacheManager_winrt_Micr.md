# winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::EnsureModelIsCachedAsync(void *,void * *)

- ea: `0x1800093a0`
- end: `0x180009405`
- name: `?EnsureModelIsCachedAsync@?$produce@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManager2@34567@@impl@winrt@@UEAAHPEAXPEAPEAX@Z`
- size: `101`
- prototype: `__int64 __fastcall(__int64, winrt::impl *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003840`
- `0x180005ba0`
- `0x1800093a0`
- `0x1800127e0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::EnsureModelIsCachedAsync(
        __int64 a1,
        winrt::impl *a2,
        _QWORD *a3)
{
  __int64 v4; // rdi
  __int64 *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct winrt::impl::hstring_header *v8; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v9[4]; // [rsp+28h] [rbp-20h] BYREF

  *a3 = 0;
  v4 = a1 - 24;
  if ( !a1 )
    v4 = 0;
  try
  {
    v8 = winrt::impl::duplicate_hstring(a2, a2);
    v5 = winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync(
           v4,
           v9,
           (volatile signed __int32 **)&v8);
    v6 = *v5;
    *v5 = 0;
    *a3 = v6;
    if ( v9[0] )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800093a0  push    rbx
0x1800093a2  push    rsi
0x1800093a3  push    rdi
0x1800093a4  sub     rsp, 30h
0x1800093a8  mov     rbx, r8
0x1800093ab  xor     esi, esi
0x1800093ad  mov     [r8], rsi
0x1800093b0  lea     rdi, [rcx-18h]
0x1800093b4  test    rcx, rcx
0x1800093b7  cmovz   rdi, rsi
0x1800093bb  mov     rcx, rdx; this
0x1800093be  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800093c3  mov     [rsp+48h+var_28], rax
0x1800093c8  lea     r8, [rsp+48h+var_28]
0x1800093cd  lea     rdx, [rsp+48h+var_20]
0x1800093d2  mov     rcx, rdi
0x1800093d5  call    ?EnsureModelIsCachedAsync@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA?AUIAsyncAction@Foundation@57@Uhstring@7@@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync(winrt::hstring)
0x1800093da  mov     rcx, [rax]
0x1800093dd  mov     [rax], rsi
0x1800093e0  mov     [rbx], rcx
0x1800093e3  cmp     [rsp+48h+var_20], rsi
0x1800093e8  jz      short loc_1800093F4
0x1800093ea  lea     rcx, [rsp+48h+var_20]
0x1800093ef  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800093f4  xor     eax, eax
0x1800093f6  jmp     short loc_1800093FC
0x1800093f8  mov     eax, dword ptr [rsp+48h+var_28]
0x1800093fc  add     rsp, 30h
0x180009400  pop     rdi
0x180009401  pop     rsi
0x180009402  pop     rbx
0x180009403  retn
```
