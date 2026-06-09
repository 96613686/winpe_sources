# Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::ParseJsonAndPopulateInMemoryCache(Platform::String *)

- ea: `0x1800c3e68`
- end: `0x1800c4152`
- name: `?ParseJsonAndPopulateInMemoryCache@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAAXPE$AAVString@Platform@@@Z`
- size: `746`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, loader_planting`

## callers

- `0x1800c0810`
- `0x1800c0894`

## callees

- `0x1800049e0`
- `0x18000617a`
- `0x18000619e`
- `0x180009fa0`
- `0x18000c860`
- `0x18000cdf0`
- `0x18003a5f4`
- `0x18003a900`
- `0x18003feb4`
- `0x18003fee0`
- `0x18003ff8c`
- `0x18007e6b8`
- `0x1800801f0`
- `0x180083160`
- `0x18008ca74`
- `0x180092490`
- `0x180092508`
- `0x180092e54`
- `0x18009c71c`
- `0x18009d9e4`
- `0x18009fce4`
- `0x1800b645c`
- `0x1800bcc90`
- `0x1800bef1c`
- `0x1800c3e68`
- `0x1800c5d44`
- `0x1800cb130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c40b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c40b2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800c401b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800c401b`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c3f8e`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c40c5`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c3f8e`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c40c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::ParseJsonAndPopulateInMemoryCache(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  __int64 i; // r15
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // r14
  void *v8; // rbx
  __int64 Object; // rsi
  __int64 v10; // rdi
  __int64 v11; // rbx
  HSTRING v12; // rbx
  PCWSTR StringRawBuffer_0; // rax
  WCHAR *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  HSTRING v17; // rbx
  std::_Ref_count_base *v18; // rdi
  char *v19; // rbx
  __int64 v20; // rbx
  __int64 v22; // [rsp+20h] [rbp-A9h] BYREF
  void *v23; // [rsp+28h] [rbp-A1h]
  __int64 v24; // [rsp+30h] [rbp-99h] BYREF
  __int64 v25; // [rsp+38h] [rbp-91h]
  std::_Ref_count_base *v26[2]; // [rsp+40h] [rbp-89h] BYREF
  __int64 v27; // [rsp+50h] [rbp-79h]
  __int64 v28; // [rsp+58h] [rbp-71h]
  void *v29; // [rsp+60h] [rbp-69h]
  __int64 v30; // [rsp+68h] [rbp-61h]
  __int64 v31; // [rsp+70h] [rbp-59h]
  HSTRING v32; // [rsp+78h] [rbp-51h]
  __int64 v33; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v34[16]; // [rsp+90h] [rbp-39h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-19h] BYREF
  _QWORD v38[2]; // [rsp+C0h] [rbp-9h] BYREF
  _BYTE v39[32]; // [rsp+D0h] [rbp+7h] BYREF

  v35 = 0;
  if ( (unsigned __int8)Windows::Data::Json::JsonArray::TryParse(a2, &v35) )
  {
    *(_OWORD *)v26 = 0;
    std::enable_shared_from_this<Cortana::ConstraintIndex::Search::SettingsFilterCacheManager>::shared_from_this(
      a1,
      v26);
    v37 = 0;
    std::_Tree<std::_Tmap_traits<Platform::String __gc *,Cortana::ConstraintIndex::Search::SettingResultItem __gc *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String __gc * const,Cortana::ConstraintIndex::Search::SettingResultItem __gc *>>,0>>::_Alloc_sentinel_and_proxy(&v37);
    v3 = __abi_winrt_cast_to(
           0,
           v35,
           _uuidof__AU__IVector_PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows__);
    Platform::Collections::VectorViewIterator<Platform::String __gc *>::VectorViewIterator<Platform::String __gc *>(
      &v24,
      v3);
    __abi_winrt_ptr_dtor(v3);
    v22 = __abi_winrt_cast_to(
            0,
            v35,
            _uuidof__AU__IVector_PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows__);
    Windows::Foundation::Collections::end<WindowsUdk::System::Profile::SystemSettingEntryPoint __gc *>(v38, v22);
    __abi_winrt_ptr_dtor(v22);
    for ( i = v25; i != v38[1]; v25 = i )
    {
      v5 = Platform::Collections::VectorIterator<Windows::Data::Json::IJsonValue __gc *>::operator*(&v24, &v33);
      v6 = Platform::Collections::VectorViewIterator<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>::operator*(v5);
      v27 = v6;
      v7 = __abi_winrt_ptr_ctor(v6);
      v28 = v7;
      __abi_winrt_ptr_dtor(v6);
      __abi_winrt_ptr_dtor(v33);
      v8 = Platform::Details::Heap::Allocate(0xC0u, 0xD8u);
      v29 = v8;
      Object = Windows::Data::Json::IJsonValue::GetObject(v7);
      v30 = Object;
      v10 = Cortana::ConstraintIndex::Search::SettingResultItem::SettingResultItem(v8, Object);
      v31 = v10;
      v11 = __abi_winrt_ptr_ctor(v10);
      v36 = v11;
      __abi_winrt_ptr_dtor(v10);
      __abi_winrt_ptr_dtor(Object);
      v12 = (HSTRING)__abi_winrt_ptrto_string_ctor(*(_QWORD *)(v11 + 136));
      v32 = v12;
      StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v12, 0);
      std::wstring::wstring(v39, StringRawBuffer_0);
      WindowsDeleteString_0(v12);
      v14 = (WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v39);
      PathRemoveExtensionW(v14);
      v22 = 0;
      v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v39);
      v17 = (HSTRING)Platform::String::String(v16, v15);
      v23 = v17;
      v22 = (__int64)v17;
      std::_Tree<std::_Tmap_traits<Platform::String __gc *,Cortana::ConstraintIndex::Search::SettingPath __gc *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String __gc * const,Cortana::ConstraintIndex::Search::SettingPath __gc *>>,0>>::_Emplace<Platform::String __gc * &,Cortana::ConstraintIndex::Search::SettingPath __gc * &>(
        (__int64 *)&v37,
        (__int64)v34,
        (__int64)&v22,
        (__int64)&v36);
      WindowsDeleteString_0(v17);
      std::wstring::_Tidy_deallocate(v39);
      __abi_winrt_ptr_dtor(v36);
      __abi_winrt_ptr_dtor(v7);
      ++i;
    }
    __abi_winrt_ptr_dtor(v38[0]);
    __abi_winrt_ptr_dtor(v24);
    v18 = v26[0];
    v19 = (char *)v26[0] + 80;
    AcquireSRWLockExclusive((PSRWLOCK)v26[0] + 10);
    v22 = (__int64)v19;
    v23 = Platform::Details::Heap::Allocate(0x58u, 0x70u);
    v20 = Platform::Collections::MapView<Platform::String __gc *,Cortana::ConstraintIndex::Search::SettingResultItem __gc *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,1,1>::MapView<Platform::String __gc *,Cortana::ConstraintIndex::Search::SettingResultItem __gc *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,1,1>(
            v23,
            &v37);
    v23 = (void *)v20;
    __abi_winrt_ptr_assign((char *)v18 + 88, v20);
    __abi_winrt_ptr_dtor(v20);
    *((_BYTE *)v18 + 96) = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
    std::_Tree_val<std::_Tree_simple_types<std::pair<Platform::String __gc * const,Cortana::ConstraintIndex::Search::SettingResultItem __gc *>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<Platform::String __gc * const,Cortana::ConstraintIndex::Search::SettingResultItem __gc *>,void *>>>(
      &v37,
      &v37);
    if ( v26[1] )
      std::_Ref_count_base::_Decref(v26[1]);
  }
  return __abi_winrt_ptr_dtor(v35);
}

```

## disassembly

```asm
0x1800c3e68  mov     [rsp-8+arg_10], rbx
0x1800c3e6d  push    rbp
0x1800c3e6e  push    rsi
0x1800c3e6f  push    rdi
0x1800c3e70  push    r14
0x1800c3e72  push    r15
0x1800c3e74  lea     rbp, [rsp-37h]
0x1800c3e79  sub     rsp, 100h
0x1800c3e80  mov     rax, cs:__security_cookie
0x1800c3e87  xor     rax, rsp
0x1800c3e8a  mov     [rbp+57h+var_30], rax
0x1800c3e8e  mov     rax, rdx
0x1800c3e91  mov     rbx, rcx
0x1800c3e94  mov     [rbp+57h+var_80], 0
0x1800c3e9c  lea     rdx, [rbp+57h+var_80]
0x1800c3ea0  mov     rcx, rax
0x1800c3ea3  call    ?TryParse@JsonArray@Json@Data@Windows@@SA_NPE$AAVString@Platform@@PEAPE$AAV1234@@Z; Windows::Data::Json::JsonArray::TryParse(Platform::String *,Windows::Data::Json::JsonArray * *)
0x1800c3ea8  test    al, al
0x1800c3eaa  jz      loc_1800C4126
0x1800c3eb0  xorps   xmm0, xmm0
0x1800c3eb3  movups  xmmword ptr [rsp+120h+var_E0], xmm0
0x1800c3eb8  lea     rdx, [rsp+120h+var_E0]
0x1800c3ebd  mov     rcx, rbx
0x1800c3ec0  call    ?shared_from_this@?$enable_shared_from_this@VSettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@@std@@QEAA?AV?$shared_ptr@VSettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@@2@XZ; std::enable_shared_from_this<Cortana::ConstraintIndex::Search::SettingsFilterCacheManager>::shared_from_this(void)
0x1800c3ec5  nop
0x1800c3ec6  xorps   xmm1, xmm1
0x1800c3ec9  movdqu  [rbp+57h+var_70], xmm1
0x1800c3ece  lea     rcx, [rbp+57h+var_70]
0x1800c3ed2  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@UStringCaseInsensitiveLess@456@V?$allocator@U?$pair@QE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<Platform::String *,Cortana::ConstraintIndex::Search::SettingResultItem *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingResultItem *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800c3ed7  nop
0x1800c3ed8  lea     r8, __uuidof_?AU?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@
0x1800c3edf  mov     rdx, [rbp+57h+var_80]
0x1800c3ee3  xor     ecx, ecx
0x1800c3ee5  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800c3eea  mov     rbx, rax
0x1800c3eed  mov     [rsp+120h+var_100], rax
0x1800c3ef2  mov     rdx, rax
0x1800c3ef5  lea     rcx, [rsp+120h+var_F0]
0x1800c3efa  call    ??0?$VectorViewIterator@PE$AAVString@Platform@@@Collections@Platform@@QEAA@PE$AAU?$IVectorView@PE$AAVString@Platform@@@1Foundation@Windows@@@Z; Platform::Collections::VectorViewIterator<Platform::String *>::VectorViewIterator<Platform::String *>(Windows::Foundation::Collections::IVectorView<Platform::String *> *)
0x1800c3eff  nop
0x1800c3f00  mov     rcx, rbx
0x1800c3f03  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c3f08  lea     r8, __uuidof_?AU?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@
0x1800c3f0f  mov     rdx, [rbp+57h+var_80]
0x1800c3f13  xor     ecx, ecx
0x1800c3f15  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800c3f1a  mov     rbx, rax
0x1800c3f1d  mov     [rsp+120h+var_100], rax
0x1800c3f22  mov     rdx, rax
0x1800c3f25  lea     rcx, [rbp+57h+var_60]
0x1800c3f29  call    ??$end@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@Collections@Foundation@Windows@@YA?AV?$VectorViewIterator@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@0Platform@@PE$AAU?$IVectorView@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@012@@Z; Windows::Foundation::Collections::end<WindowsUdk::System::Profile::SystemSettingEntryPoint *>(Windows::Foundation::Collections::IVectorView<WindowsUdk::System::Profile::SystemSettingEntryPoint *> *)
0x1800c3f2e  nop
0x1800c3f2f  mov     rcx, rbx
0x1800c3f32  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c3f37  mov     r15, [rsp+120h+var_E8]
0x1800c3f3c  cmp     r15, [rbp+57h+var_58]
0x1800c3f40  jz      loc_1800C4091
0x1800c3f46  lea     rdx, [rbp+57h+var_A0]
0x1800c3f4a  lea     rcx, [rsp+120h+var_F0]
0x1800c3f4f  call    ??D?$VectorIterator@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Platform@@QEBA?AV?$VectorProxy@PE$AAUIJsonValue@Json@Data@Windows@@@Details@12@XZ; Platform::Collections::VectorIterator<Windows::Data::Json::IJsonValue *>::operator*(void)
0x1800c3f54  nop
0x1800c3f55  mov     rcx, rax
0x1800c3f58  call    ??D?$VectorViewIterator@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Platform@@QEBAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@XZ; Platform::Collections::VectorViewIterator<Cortana::ConstraintIndex::Search::SettingResultItem *>::operator*(void)
0x1800c3f5d  mov     rbx, rax
0x1800c3f60  mov     [rbp+57h+var_D0], rax
0x1800c3f64  mov     rcx, rax
0x1800c3f67  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c3f6c  mov     r14, rax
0x1800c3f6f  mov     [rbp+57h+var_C8], rax
0x1800c3f73  mov     rcx, rbx
0x1800c3f76  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c3f7b  nop
0x1800c3f7c  mov     rcx, [rbp+57h+var_A0]
0x1800c3f80  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c3f85  nop
0x1800c3f86  mov     edx, 0D8h
0x1800c3f8b  lea     ecx, [rdx-18h]
0x1800c3f8e  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x1800c3f94  mov     rbx, rax
0x1800c3f97  mov     [rbp+57h+var_C0], rax
0x1800c3f9b  mov     rcx, r14
0x1800c3f9e  call    ?GetObject@IJsonValue@Json@Data@Windows@@UE$AAAPE$AAVJsonObject@234@XZ; Windows::Data::Json::IJsonValue::GetObject(void)
0x1800c3fa3  mov     rsi, rax
0x1800c3fa6  mov     [rbp+57h+var_B8], rax
0x1800c3faa  mov     rdx, rax
0x1800c3fad  mov     rcx, rbx
0x1800c3fb0  call    ??0SettingResultItem@Search@ConstraintIndex@Cortana@@QE$AAA@PE$AAVJsonObject@Json@Data@Windows@@@Z; Cortana::ConstraintIndex::Search::SettingResultItem::SettingResultItem(Windows::Data::Json::JsonObject *)
0x1800c3fb5  mov     rdi, rax
0x1800c3fb8  mov     [rbp+57h+var_B0], rax
0x1800c3fbc  mov     rcx, rax
0x1800c3fbf  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c3fc4  mov     rbx, rax
0x1800c3fc7  mov     [rbp+57h+var_78], rax
0x1800c3fcb  mov     rcx, rdi
0x1800c3fce  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c3fd3  nop
0x1800c3fd4  mov     rcx, rsi
0x1800c3fd7  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c3fdc  nop
0x1800c3fdd  mov     rcx, [rbx+88h]
0x1800c3fe4  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800c3fe9  mov     rbx, rax
0x1800c3fec  mov     [rbp+57h+var_A8], rax
0x1800c3ff0  xor     edx, edx; length
0x1800c3ff2  mov     rcx, rax; string
0x1800c3ff5  call    WindowsGetStringRawBuffer_0
0x1800c3ffa  mov     rdx, rax
0x1800c3ffd  lea     rcx, [rbp+57h+var_50]
0x1800c4001  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c4006  nop
0x1800c4007  mov     rcx, rbx; string
0x1800c400a  call    WindowsDeleteString_0
0x1800c400f  lea     rcx, [rbp+57h+var_50]
0x1800c4013  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800c4018  mov     rcx, rax; pszPath
0x1800c401b  call    cs:__imp_PathRemoveExtensionW
0x1800c4021  mov     [rsp+120h+var_100], 0
0x1800c402a  lea     rcx, [rbp+57h+var_50]
0x1800c402e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800c4033  mov     rdx, rax
0x1800c4036  call    ??0String@Platform@@QE$AAA@PEB_W@Z; Platform::String::String(wchar_t const *)
0x1800c403b  mov     rbx, rax
0x1800c403e  mov     [rsp+120h+var_F8], rax
0x1800c4043  mov     [rsp+120h+var_100], rax
0x1800c4048  lea     r9, [rbp+57h+var_78]
0x1800c404c  lea     r8, [rsp+120h+var_100]
0x1800c4051  lea     rdx, [rbp+57h+var_90]
0x1800c4055  lea     rcx, [rbp+57h+var_70]
0x1800c4059  call    ??$_Emplace@AEAPE$AAVString@Platform@@AEAPE$AAUSettingPath@Search@ConstraintIndex@Cortana@@@?$_Tree@V?$_Tmap_traits@PE$AAVString@Platform@@PE$AAUSettingPath@Search@ConstraintIndex@Cortana@@UStringCaseInsensitiveLess@456@V?$allocator@U?$pair@QE$AAVString@Platform@@PE$AAUSettingPath@Search@ConstraintIndex@Cortana@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QE$AAVString@Platform@@PE$AAUSettingPath@Search@ConstraintIndex@Cortana@@@std@@PEAX@std@@_N@1@AEAPE$AAVString@Platform@@AEAPE$AAUSettingPath@Search@ConstraintIndex@Cortana@@@Z; std::_Tree<std::_Tmap_traits<Platform::String *,Cortana::ConstraintIndex::Search::SettingPath *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingPath *>>,0>>::_Emplace<Platform::String * &,Cortana::ConstraintIndex::Search::SettingPath * &>(Platform::String * &,Cortana::ConstraintIndex::Search::SettingPath * &)
0x1800c405e  nop
0x1800c405f  mov     rcx, rbx; string
0x1800c4062  call    WindowsDeleteString_0
0x1800c4067  nop
0x1800c4068  lea     rcx, [rbp+57h+var_50]
0x1800c406c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c4071  nop
0x1800c4072  mov     rcx, [rbp+57h+var_78]
0x1800c4076  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c407b  nop
0x1800c407c  mov     rcx, r14
0x1800c407f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c4084  inc     r15
0x1800c4087  mov     [rsp+120h+var_E8], r15
0x1800c408c  jmp     loc_1800C3F3C
0x1800c4091  mov     rcx, [rbp+57h+var_60]
0x1800c4095  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c409a  nop
0x1800c409b  mov     rcx, [rsp+120h+var_F0]
0x1800c40a0  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c40a5  nop
0x1800c40a6  mov     rdi, [rsp+120h+var_E0]
0x1800c40ab  lea     rbx, [rdi+50h]
0x1800c40af  mov     rcx, rbx; SRWLock
0x1800c40b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800c40b8  mov     [rsp+120h+var_100], rbx
0x1800c40bd  mov     edx, 70h ; 'p'
0x1800c40c2  lea     ecx, [rdx-18h]
0x1800c40c5  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x1800c40cb  mov     [rsp+120h+var_F8], rax
0x1800c40d0  lea     rdx, [rbp+57h+var_70]
0x1800c40d4  mov     rcx, rax
0x1800c40d7  call    ??0?$MapView@PE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@UStringCaseInsensitiveLess@456@$00$00@Collections@Platform@@QE$AAA@$$QEAV?$map@PE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@UStringCaseInsensitiveLess@456@V?$allocator@U?$pair@QE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@@std@@@std@@@Z; Platform::Collections::MapView<Platform::String *,Cortana::ConstraintIndex::Search::SettingResultItem *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,1,1>::MapView<Platform::String *,Cortana::ConstraintIndex::Search::SettingResultItem *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,1,1>(std::map<Platform::String *,Cortana::ConstraintIndex::Search::SettingResultItem *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingResultItem *>>> &&)
0x1800c40dc  mov     rbx, rax
0x1800c40df  mov     [rsp+120h+var_F8], rax
0x1800c40e4  lea     rcx, [rdi+58h]
0x1800c40e8  mov     rdx, rax
0x1800c40eb  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x1800c40f0  nop
0x1800c40f1  mov     rcx, rbx
0x1800c40f4  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c40f9  mov     byte ptr [rdi+60h], 0
0x1800c40fd  lea     rcx, [rsp+120h+var_100]
0x1800c4102  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800c4107  nop
0x1800c4108  lea     rdx, [rbp+57h+var_70]
0x1800c410c  lea     rcx, [rbp+57h+var_70]
0x1800c4110  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@QE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingResultItem *>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingResultItem *>,void *>>>(std::allocator<std::_Tree_node<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingResultItem *>,void *>> &)
0x1800c4115  nop
0x1800c4116  mov     rcx, [rsp+120h+var_E0+8]; this
0x1800c411b  test    rcx, rcx
0x1800c411e  jz      short loc_1800C4126
0x1800c4120  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c4125  nop
0x1800c4126  mov     rcx, [rbp+57h+var_80]
0x1800c412a  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c412f  mov     rcx, [rbp+57h+var_30]
0x1800c4133  xor     rcx, rsp; StackCookie
0x1800c4136  call    __security_check_cookie
0x1800c413b  mov     rbx, [rsp+120h+arg_10]
0x1800c4143  add     rsp, 100h
0x1800c414a  pop     r15
0x1800c414c  pop     r14
0x1800c414e  pop     rdi
0x1800c414f  pop     rsi
0x1800c4150  pop     rbp
0x1800c4151  retn
```
