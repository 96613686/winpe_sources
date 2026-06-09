# winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::CacheModelWithOfflineDriverAsync(void *,void *,void * *)

- ea: `0x180009310`
- end: `0x180009399`
- name: `?CacheModelWithOfflineDriverAsync@?$produce@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManager2@34567@@impl@winrt@@UEAAHPEAX0PEAPEAX@Z`
- size: `137`
- prototype: `__int64 __fastcall(__int64, struct winrt::impl::hstring_header *, winrt::impl *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003840`
- `0x180005e70`
- `0x180009310`
- `0x1800127e0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::CacheModelWithOfflineDriverAsync(
        __int64 a1,
        struct winrt::impl::hstring_header *a2,
        winrt::impl *a3,
        _QWORD *a4)
{
  __int64 v6; // rdi
  struct winrt::impl::hstring_header *v7; // rdx
  __int64 *v8; // rax
  __int64 v9; // rcx
  __int64 result; // rax
  struct winrt::impl::hstring_header *v11; // [rsp+20h] [rbp-58h] BYREF
  struct winrt::impl::hstring_header *v12; // [rsp+28h] [rbp-50h] BYREF
  _QWORD v13[9]; // [rsp+30h] [rbp-48h] BYREF

  *a4 = 0;
  v6 = a1 - 24;
  if ( !a1 )
    v6 = 0;
  v13[1] = &v11;
  try
  {
    v11 = winrt::impl::duplicate_hstring(a3, a2);
    v12 = winrt::impl::duplicate_hstring(a2, v7);
    v8 = winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync(
           v6,
           v13,
           (volatile signed __int32 **)&v12,
           (volatile signed __int32 **)&v11);
    v9 = *v8;
    *v8 = 0;
    *a4 = v9;
    if ( v13[0] )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v13);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v11);
  }
  return result;
}

```

## disassembly

```asm
0x180009310  push    rbx
0x180009312  push    rsi
0x180009313  push    rdi
0x180009314  push    r14
0x180009316  sub     rsp, 58h
0x18000931a  mov     rbx, r9
0x18000931d  mov     rsi, rdx
0x180009320  xor     r14d, r14d
0x180009323  mov     [r9], r14
0x180009326  lea     rdi, [rcx-18h]
0x18000932a  test    rcx, rcx
0x18000932d  cmovz   rdi, r14
0x180009331  lea     rax, [rsp+78h+var_58]
0x180009336  mov     [rsp+78h+var_40], rax
0x18000933b  mov     rcx, r8; this
0x18000933e  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180009343  mov     [rsp+78h+var_58], rax
0x180009348  mov     rcx, rsi; this
0x18000934b  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180009350  mov     [rsp+78h+var_50], rax
0x180009355  lea     r9, [rsp+78h+var_58]
0x18000935a  lea     r8, [rsp+78h+var_50]
0x18000935f  lea     rdx, [rsp+78h+var_48]
0x180009364  mov     rcx, rdi
0x180009367  call    ?CacheModelWithOfflineDriverAsync@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA?AUIAsyncAction@Foundation@57@Uhstring@7@0@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync(winrt::hstring,winrt::hstring)
0x18000936c  mov     rcx, [rax]
0x18000936f  mov     [rax], r14
0x180009372  mov     [rbx], rcx
0x180009375  cmp     [rsp+78h+var_48], r14
0x18000937a  jz      short loc_180009386
0x18000937c  lea     rcx, [rsp+78h+var_48]
0x180009381  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009386  xor     eax, eax
0x180009388  jmp     short loc_18000938E
0x18000938a  mov     eax, dword ptr [rsp+78h+var_58]
0x18000938e  add     rsp, 58h
0x180009392  pop     r14
0x180009394  pop     rdi
0x180009395  pop     rsi
0x180009396  pop     rbx
0x180009397  retn
```
