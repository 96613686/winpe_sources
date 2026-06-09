# Cortana::ConstraintIndex::Search::DESettingsQueryStrategy::GetItemCache(void)

- ea: `0x18009e800`
- end: `0x18009e98f`
- name: `?GetItemCache@DESettingsQueryStrategy@Search@ConstraintIndex@Cortana@@UEAAPE$AAU?$IMapView@PE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@XZ`
- size: `399`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18003feb4`
- `0x18003fee0`
- `0x18007e528`
- `0x180080010`
- `0x1800819a8`
- `0x180081a5c`
- `0x18008e508`
- `0x18008fa58`
- `0x180092508`
- `0x180093118`
- `0x18009cf80`
- `0x18009d9b8`
- `0x18009e800`
- `0x18009f370`
- `0x18009f520`
- `0x1800c3138`
- `0x1800c383c`
- `0x1800c45e8`

## import_xrefs

- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18009e909`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18009e909`

## string_xrefs

- `0x18009e83a`: `DESettingsQueryStrategy_GetItemCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Cortana::ConstraintIndex::Search::DESettingsQueryStrategy::GetItemCache(__int64 a1)
{
  char v2; // dl
  __int64 v3; // rbx
  __int64 refreshed; // rdi
  __int64 v5; // rcx
  __int64 AllSettingsCache; // rbx
  __int64 v7; // rdi
  unsigned __int8 v8; // si
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // rbx
  _QWORD v13[2]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v14[96]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v15; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v16[42]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(v16, 0, sizeof(v16));
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v16);
  v16[0] = &ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::`vftable';
  ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::StartActivity(
    (ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache *)v16,
    v2);
  if ( Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::IsCacheEmpty(*(Cortana::ConstraintIndex::Search::SettingsFilterCacheManager **)(a1 + 56)) )
  {
    v15 = v14;
    v3 = Concurrency::task_options::task_options((Concurrency::task_options *)v14);
    refreshed = Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::RefreshCacheIfNecessaryAsync(
                  *(_QWORD *)(a1 + 56),
                  0);
    v15 = (_BYTE *)refreshed;
    v5 = *(_QWORD *)Concurrency::create_task<Windows::Foundation::IAsyncAction __gc *>(v13, refreshed, v3);
    if ( !v5 )
      Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl();
    Concurrency::details::_Task_impl_base::_Wait(v5);
    std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>(v13);
    __abi_winrt_ptr_dtor(refreshed);
  }
  AllSettingsCache = Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::GetAllSettingsCache(*(_QWORD *)(a1 + 56));
  v15 = (_BYTE *)AllSettingsCache;
  v7 = __abi_winrt_ptr_ctor(AllSettingsCache);
  v15 = (_BYTE *)v7;
  __abi_winrt_ptr_dtor(AllSettingsCache);
  if ( v7 )
  {
    v8 = 1;
  }
  else
  {
    v8 = 0;
    v13[0] = Platform::Details::Heap::Allocate(0x58u, 0x70u);
    v9 = Platform::Collections::MapView<Platform::String __gc *,Cortana::ConstraintIndex::Search::SettingResultItem __gc *,std::less<Platform::String __gc *>,1,1>::MapView<Platform::String __gc *,Cortana::ConstraintIndex::Search::SettingResultItem __gc *,std::less<Platform::String __gc *>,1,1>(v13[0]);
    v13[0] = v9;
    __abi_winrt_ptr_assign(&v15, v9);
    __abi_winrt_ptr_dtor(v9);
    v7 = (__int64)v15;
  }
  v10 = Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue __gc *>::Size::get(v7);
  ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::Stop(
    (ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache *)v16,
    v8,
    v10);
  v11 = __abi_winrt_ptr_ctor(v7);
  __abi_winrt_ptr_dtor(v7);
  ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::~DESettingsQueryStrategy_GetItemCache((ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache *)v16);
  return v11;
}

```

## disassembly

```asm
0x18009e800  push    rbp
0x18009e802  push    rbx
0x18009e803  push    rsi
0x18009e804  push    rdi
0x18009e805  lea     rbp, [rsp-108h]
0x18009e80d  sub     rsp, 208h
0x18009e814  mov     rax, cs:__security_cookie
0x18009e81b  xor     rax, rsp
0x18009e81e  mov     [rbp+120h+var_30], rax
0x18009e825  mov     rsi, rcx
0x18009e828  xor     edx, edx; Val
0x18009e82a  mov     r8d, 150h; Size
0x18009e830  lea     rcx, [rbp+120h+var_180]; void *
0x18009e834  call    memset_0
0x18009e839  nop
0x18009e83a  lea     rdx, aDesettingsquer; "DESettingsQueryStrategy_GetItemCache"
0x18009e841  lea     rcx, [rbp+120h+var_180]; struct wil::details::IFailureCallback *
0x18009e845  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009e84a  lea     rax, ??_7DESettingsQueryStrategy_GetItemCache@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::`vftable'
0x18009e851  mov     [rbp+120h+var_180], rax
0x18009e855  lea     rcx, [rbp+120h+var_180]; this
0x18009e859  call    ?StartActivity@DESettingsQueryStrategy_GetItemCache@ConstraintIndexTelemetry@@QEAAX_N@Z; ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::StartActivity(bool)
0x18009e85e  nop
0x18009e85f  mov     rcx, [rsi+38h]; this
0x18009e863  call    ?IsCacheEmpty@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@QEAA_NXZ; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::IsCacheEmpty(void)
0x18009e868  test    al, al
0x18009e86a  jz      short loc_18009E8CC
0x18009e86c  lea     rax, [rsp+220h+var_1F0]
0x18009e871  mov     [rbp+120h+var_190], rax
0x18009e875  lea     rcx, [rsp+220h+var_1F0]; this
0x18009e87a  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x18009e87f  mov     rbx, rax
0x18009e882  xor     edx, edx
0x18009e884  mov     rcx, [rsi+38h]
0x18009e888  call    ?RefreshCacheIfNecessaryAsync@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@QEAAPE$AAUIAsyncAction@Foundation@Windows@@_N@Z; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::RefreshCacheIfNecessaryAsync(bool)
0x18009e88d  mov     rdi, rax
0x18009e890  mov     [rbp+120h+var_190], rax
0x18009e894  mov     r8, rbx
0x18009e897  mov     rdx, rax
0x18009e89a  lea     rcx, [rsp+220h+var_200]
0x18009e89f  call    ??$create_task@PE$AAUIAsyncAction@Foundation@Windows@@@Concurrency@@YA?AV?$task@X@0@PE$AAUIAsyncAction@Foundation@Windows@@Vtask_options@0@@Z; Concurrency::create_task<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,Concurrency::task_options)
0x18009e8a4  nop
0x18009e8a5  mov     rcx, [rax]
0x18009e8a8  test    rcx, rcx
0x18009e8ab  jnz     short loc_18009E8B3
0x18009e8ad  call    ?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ; Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
0x18009e8b3  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x18009e8b8  nop
0x18009e8b9  lea     rcx, [rsp+220h+var_200]
0x18009e8be  call    ??1?$shared_ptr@U?$_Task_impl@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>>(void)
0x18009e8c3  nop
0x18009e8c4  mov     rcx, rdi
0x18009e8c7  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e8cc  mov     rcx, [rsi+38h]
0x18009e8d0  call    ?GetAllSettingsCache@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@QEAAPE$AAU?$IMapView@PE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@XZ; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::GetAllSettingsCache(void)
0x18009e8d5  mov     rbx, rax
0x18009e8d8  mov     [rbp+120h+var_190], rax
0x18009e8dc  mov     rcx, rax
0x18009e8df  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009e8e4  mov     rdi, rax
0x18009e8e7  mov     [rbp+120h+var_190], rax
0x18009e8eb  mov     rcx, rbx
0x18009e8ee  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e8f3  nop
0x18009e8f4  test    rdi, rdi
0x18009e8f7  jz      short loc_18009E8FE
0x18009e8f9  mov     sil, 1
0x18009e8fc  jmp     short loc_18009E93D
0x18009e8fe  xor     sil, sil
0x18009e901  mov     edx, 70h ; 'p'
0x18009e906  lea     ecx, [rdx-18h]
0x18009e909  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x18009e90f  mov     [rsp+220h+var_200], rax
0x18009e914  mov     rcx, rax
0x18009e917  call    ??0?$MapView@PE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@U?$less@PE$AAVString@Platform@@@std@@$00$00@Collections@Platform@@QE$AAA@AEBU?$less@PE$AAVString@Platform@@@std@@@Z; Platform::Collections::MapView<Platform::String *,Cortana::ConstraintIndex::Search::SettingResultItem *,std::less<Platform::String *>,1,1>::MapView<Platform::String *,Cortana::ConstraintIndex::Search::SettingResultItem *,std::less<Platform::String *>,1,1>(std::less<Platform::String *> const &)
0x18009e91c  mov     rbx, rax
0x18009e91f  mov     [rsp+220h+var_200], rax
0x18009e924  mov     rdx, rax
0x18009e927  lea     rcx, [rbp+120h+var_190]
0x18009e92b  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x18009e930  nop
0x18009e931  mov     rcx, rbx
0x18009e934  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e939  mov     rdi, [rbp+120h+var_190]
0x18009e93d  mov     rcx, rdi
0x18009e940  call    ?get@Size@?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@UE$AAAIXZ; Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>::Size::get(void)
0x18009e945  mov     r8d, eax; int
0x18009e948  mov     dl, sil; bool
0x18009e94b  lea     rcx, [rbp+120h+var_180]; this
0x18009e94f  call    ?Stop@DESettingsQueryStrategy_GetItemCache@ConstraintIndexTelemetry@@QEAAX_NH@Z; ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::Stop(bool,int)
0x18009e954  mov     rcx, rdi
0x18009e957  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009e95c  mov     rbx, rax
0x18009e95f  mov     rcx, rdi
0x18009e962  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e967  nop
0x18009e968  lea     rcx, [rbp+120h+var_180]; this
0x18009e96c  call    ??1DESettingsQueryStrategy_GetItemCache@ConstraintIndexTelemetry@@QEAA@XZ; ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::~DESettingsQueryStrategy_GetItemCache(void)
0x18009e971  mov     rax, rbx
0x18009e974  mov     rcx, [rbp+120h+var_30]
0x18009e97b  xor     rcx, rsp; StackCookie
0x18009e97e  call    __security_check_cookie
0x18009e983  add     rsp, 208h
0x18009e98a  pop     rdi
0x18009e98b  pop     rsi
0x18009e98c  pop     rbx
0x18009e98d  pop     rbp
0x18009e98e  retn
```
