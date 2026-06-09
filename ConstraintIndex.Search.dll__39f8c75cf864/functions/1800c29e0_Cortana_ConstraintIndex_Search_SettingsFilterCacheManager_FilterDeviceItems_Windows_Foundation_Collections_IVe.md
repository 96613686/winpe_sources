# Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::FilterDeviceItems(Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::SettingResultItem *> *,uint,Concurrency::cancellation_token const &)

- ea: `0x1800c29e0`
- end: `0x1800c2f6c`
- name: `?FilterDeviceItems@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@QEAAPE$AAU?$IVectorView@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@PE$AAU5678@IAEBVcancellation_token@Concurrency@@@Z`
- size: `1420`
- prototype: `__int64 __fastcall(Cortana::ConstraintIndex::Search::SettingsFilterCacheManager *this)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config`

## callers

- `0x18009dec0`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x180005e50`
- `0x18000617a`
- `0x1800062a0`
- `0x18000696c`
- `0x18003feb4`
- `0x18003fee0`
- `0x18003ff8c`
- `0x18007e6b8`
- `0x180080010`
- `0x1800801f0`
- `0x180083160`
- `0x180093118`
- `0x1800a29f4`
- `0x1800a37e4`
- `0x1800a3a80`
- `0x1800a3bd0`
- `0x1800a9c70`
- `0x1800ab9b4`
- `0x1800ac3b8`
- `0x1800ad6a0`
- `0x1800bb480`
- `0x1800c0414`
- `0x1800c29e0`
- `0x1800c4888`
- `0x1800c4c18`
- `0x1800c7594`
- `0x1800c809c`

## import_xrefs

- `wincorlib!??0NotImplementedException@Platform@@QE$AAA@XZ` at `0x1800c2c45`
- `wincorlib!??0NotImplementedException@Platform@@QE$AAA@XZ` at `0x1800c2c45`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c2c37`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c2c37`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c2aa5`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c2e27`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c2aa5`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c2e27`

## string_xrefs

- `0x1800c2a46`: `SettingsFilterCacheManager_FilterDeviceItems`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::FilterDeviceItems(
        Cortana::ConstraintIndex::Search::SettingsFilterCacheManager *this,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  unsigned __int64 v5; // r15
  __int64 v7; // rdi
  int v8; // ebx
  __int128 v9; // xmm0
  void *v10; // rax
  __int64 v11; // r14
  __int64 i; // rsi
  __int64 v13; // rbx
  __int64 v14; // rdi
  int FilterState; // eax
  int v16; // eax
  HSTRING v17; // rbx
  __int64 v18; // rax
  __int128 *v19; // rcx
  unsigned __int64 v20; // rsi
  __int64 View__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ; // rbx
  _QWORD *j; // rbx
  _QWORD *v23; // r15
  __int64 v24; // rdi
  __int64 v25; // rcx
  _QWORD *k; // rdi
  _QWORD *v27; // r15
  __int64 v28; // rbx
  __int64 v29; // rbx
  __int64 v30; // rdi
  int Q__IVectorView_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows__Size___VectorView_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana__U__equal_to_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana___std___00_2Platform__UE_AAAIXZ; // eax
  __int64 v32; // rbx
  __int64 v34; // [rsp+20h] [rbp-E0h] BYREF
  void *Exception; // [rsp+28h] [rbp-D8h]
  __int64 pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+40h] [rbp-C0h]
  __int64 v39; // [rsp+48h] [rbp-B8h]
  __int64 v40; // [rsp+50h] [rbp-B0h]
  __int128 v41; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h]
  __int128 v43; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h]
  __int128 v45; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h]
  _QWORD v47[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v48[42]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = a3;
  v7 = __abi_winrt_ptr_ctor(a2);
  v40 = v7;
  memset_0(v48, 0, sizeof(v48));
  v8 = Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue __gc *>::Size::get(v7);
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v48);
  v48[0] = &ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::`vftable';
  ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::StartActivity(
    (ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems *)v48,
    v8,
    v5);
  v9 = 0;
  v45 = 0;
  v46 = 0;
  *(double *)&v9 = std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(&v45);
  v43 = v9;
  v44 = 0;
  std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(&v43);
  v10 = Platform::Details::Heap::Allocate(0x88u, 0xB0u);
  pExceptionObject = Platform::Collections::Vector<Platform::String __gc *,std::equal_to<Platform::String __gc *>,1>::Vector<Platform::String __gc *,std::equal_to<Platform::String __gc *>,1>(v10);
  v11 = __abi_winrt_ptr_ctor(pExceptionObject);
  v39 = v11;
  __abi_winrt_ptr_dtor(pExceptionObject);
  Platform::Collections::VectorViewIterator<Platform::String __gc *>::VectorViewIterator<Platform::String __gc *>(
    &v37,
    v7);
  Windows::Foundation::Collections::end<WindowsUdk::System::Profile::SystemSettingEntryPoint __gc *>(v47, v7);
  for ( i = v38; i != v47[1]; v38 = i )
  {
    v13 = Platform::Collections::VectorViewIterator<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>::operator*(&v37);
    pExceptionObject = v13;
    v14 = __abi_winrt_ptr_ctor(v13);
    v34 = v14;
    __abi_winrt_ptr_dtor(v13);
    FilterState = Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::_GetFilterState(this);
    if ( !FilterState )
      goto LABEL_18;
    v16 = FilterState - 1;
    if ( v16 )
    {
      if ( v16 != 1 )
      {
        Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
        Exception = (void *)Platform::NotImplementedException::NotImplementedException(Exception);
        pExceptionObject = __abi_winrt_ptr_ctor(Exception);
        throw (Platform::NotImplementedException **)&pExceptionObject;
      }
      if ( *((_QWORD *)&v43 + 1) == v44 )
      {
        std::vector<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>::_Emplace_reallocate<Cortana::ConstraintIndex::Search::SettingResultItem __gc * const &>(
          &v43,
          *((_QWORD *)&v43 + 1),
          &v34);
        v14 = v34;
      }
      else
      {
        std::_Construct_in_place<Cortana::ConstraintIndex::Search::SettingResultItem __gc *,Cortana::ConstraintIndex::Search::SettingResultItem __gc * const &>(*((_QWORD *)&v43 + 1));
        *((_QWORD *)&v43 + 1) += 8LL;
      }
      v17 = (HSTRING)__abi_winrt_ptrto_string_ctor(*(_QWORD *)(v14 + 128));
      Exception = v17;
      _Append__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAXPE_AAVString_6__Z(
        v11,
        v17);
      WindowsDeleteString_0(v17);
    }
    else
    {
      if ( (unsigned __int8)_get__QISettingResultItem_Search_ConstraintIndex_Cortana__IsModernSetting_SettingResultItem_234_UE_AAA_NXZ(v14) )
      {
        v18 = *((_QWORD *)&v45 + 1);
        if ( *((_QWORD *)&v45 + 1) != v46 )
        {
          std::_Construct_in_place<Cortana::ConstraintIndex::Search::SettingResultItem __gc *,Cortana::ConstraintIndex::Search::SettingResultItem __gc * const &>(*((_QWORD *)&v45 + 1));
          *((_QWORD *)&v45 + 1) += 8LL;
          goto LABEL_18;
        }
        v19 = &v45;
      }
      else
      {
        v18 = *((_QWORD *)&v43 + 1);
        if ( *((_QWORD *)&v43 + 1) != v44 )
        {
          std::_Construct_in_place<Cortana::ConstraintIndex::Search::SettingResultItem __gc *,Cortana::ConstraintIndex::Search::SettingResultItem __gc * const &>(*((_QWORD *)&v43 + 1));
          *((_QWORD *)&v43 + 1) += 8LL;
          goto LABEL_18;
        }
        v19 = &v43;
      }
      std::vector<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>::_Emplace_reallocate<Cortana::ConstraintIndex::Search::SettingResultItem __gc * const &>(
        v19,
        v18,
        &v34);
      v14 = v34;
    }
LABEL_18:
    __abi_winrt_ptr_dtor(v14);
    ++i;
  }
  __abi_winrt_ptr_dtor(v47[0]);
  __abi_winrt_ptr_dtor(v37);
  v20 = v5;
  if ( (__int64)(*((_QWORD *)&v45 + 1) - v45) >> 3 < v5
    && (unsigned int)((__int64)(*(_QWORD *)(*(_QWORD *)(v11 + 96) + 8LL) - **(_QWORD **)(v11 + 96)) >> 3) )
  {
    View__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ = _GetView__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ(v11);
    Exception = (void *)View__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ;
    Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::_ResolveAndCacheClassicConditionals(
      this,
      View__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ,
      a4);
    __abi_winrt_ptr_dtor(View__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ);
  }
  v41 = 0;
  v42 = 0;
  std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(&v41);
  v23 = (_QWORD *)*((_QWORD *)&v45 + 1);
  for ( j = (_QWORD *)v45; j != v23; ++j )
  {
    v24 = __abi_winrt_ptr_ctor(*j);
    v34 = v24;
    if ( *((_QWORD *)&v41 + 1) == v42 )
    {
      std::vector<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>::_Emplace_reallocate<Cortana::ConstraintIndex::Search::SettingResultItem __gc * const &>(
        &v41,
        *((_QWORD *)&v41 + 1),
        &v34);
      v25 = *((_QWORD *)&v41 + 1);
      v24 = v34;
    }
    else
    {
      std::_Construct_in_place<Cortana::ConstraintIndex::Search::SettingResultItem __gc *,Cortana::ConstraintIndex::Search::SettingResultItem __gc * const &>(*((_QWORD *)&v41 + 1));
      v25 = *((_QWORD *)&v41 + 1) + 8LL;
      *((_QWORD *)&v41 + 1) += 8LL;
    }
    if ( (v25 - (__int64)v41) >> 3 == v20 )
    {
      __abi_winrt_ptr_dtor(v24);
      break;
    }
    __abi_winrt_ptr_dtor(v24);
  }
  if ( (__int64)(*((_QWORD *)&v41 + 1) - v41) >> 3 < v20 )
  {
    v27 = (_QWORD *)*((_QWORD *)&v43 + 1);
    for ( k = (_QWORD *)v43; k != v27; ++k )
    {
      v28 = __abi_winrt_ptr_ctor(*k);
      v34 = v28;
      if ( (unsigned int)Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::_GetFilterState(this) - 1 <= 1 )
      {
        if ( *((_QWORD *)&v41 + 1) == v42 )
        {
          std::vector<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>::_Emplace_reallocate<Cortana::ConstraintIndex::Search::SettingResultItem __gc * const &>(
            &v41,
            *((_QWORD *)&v41 + 1),
            &v34);
          v28 = v34;
        }
        else
        {
          std::_Construct_in_place<Cortana::ConstraintIndex::Search::SettingResultItem __gc *,Cortana::ConstraintIndex::Search::SettingResultItem __gc * const &>(*((_QWORD *)&v41 + 1));
          *((_QWORD *)&v41 + 1) += 8LL;
        }
      }
      if ( (__int64)(*((_QWORD *)&v41 + 1) - v41) >> 3 == v20 )
      {
        __abi_winrt_ptr_dtor(v28);
        break;
      }
      __abi_winrt_ptr_dtor(v28);
    }
  }
  Exception = Platform::Details::Heap::Allocate(0x68u, 0x80u);
  v29 = Platform::Collections::VectorView<Cortana::ConstraintIndex::Search::SettingResultItem __gc *,std::equal_to<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>,1>::VectorView<Cortana::ConstraintIndex::Search::SettingResultItem __gc *,std::equal_to<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>,1>(
          Exception,
          &v41);
  Exception = (void *)v29;
  v30 = __abi_winrt_ptr_ctor(v29);
  Exception = (void *)v30;
  __abi_winrt_ptr_dtor(v29);
  Q__IVectorView_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows__Size___VectorView_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana__U__equal_to_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana___std___00_2Platform__UE_AAAIXZ = _get__Q__IVectorView_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows__Size___VectorView_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana__U__equal_to_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana___std___00_2Platform__UE_AAAIXZ(v30);
  ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::Stop(
    (ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems *)v48,
    Q__IVectorView_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows__Size___VectorView_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana__U__equal_to_PE_AAVSettingResultItem_Search_ConstraintIndex_Cortana___std___00_2Platform__UE_AAAIXZ);
  v32 = __abi_winrt_ptr_ctor(v30);
  __abi_winrt_ptr_dtor(v30);
  if ( (_QWORD)v41 )
  {
    std::_Destroy_range<std::allocator<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>>(
      v41,
      *((_QWORD *)&v41 + 1));
    std::_Deallocate<16>((void *)v41, (v42 - v41) & 0xFFFFFFFFFFFFFFF8uLL);
    v41 = 0;
    v42 = 0;
  }
  __abi_winrt_ptr_dtor(v11);
  if ( (_QWORD)v43 )
  {
    std::_Destroy_range<std::allocator<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>>(
      v43,
      *((_QWORD *)&v43 + 1));
    std::_Deallocate<16>((void *)v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
    v43 = 0;
    v44 = 0;
  }
  if ( (_QWORD)v45 )
  {
    std::_Destroy_range<std::allocator<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>>(
      v45,
      *((_QWORD *)&v45 + 1));
    std::_Deallocate<16>((void *)v45, (v46 - v45) & 0xFFFFFFFFFFFFFFF8uLL);
    v45 = 0;
    v46 = 0;
  }
  ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::~SettingsFilterCacheManager_FilterDeviceItems((ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems *)v48);
  __abi_winrt_ptr_dtor(v40);
  return v32;
}

```

## disassembly

```asm
0x1800c29e0  push    rbp
0x1800c29e2  push    rbx
0x1800c29e3  push    rsi
0x1800c29e4  push    rdi
0x1800c29e5  push    r12
0x1800c29e7  push    r13
0x1800c29e9  push    r14
0x1800c29eb  push    r15
0x1800c29ed  lea     rbp, [rsp-118h]
0x1800c29f5  sub     rsp, 218h
0x1800c29fc  mov     rax, cs:__security_cookie
0x1800c2a03  xor     rax, rsp
0x1800c2a06  mov     [rbp+150h+var_50], rax
0x1800c2a0d  mov     r13, r9
0x1800c2a10  mov     r15d, r8d
0x1800c2a13  mov     r12, rcx
0x1800c2a16  mov     [rsp+250h+var_200], rdx
0x1800c2a1b  mov     rcx, rdx
0x1800c2a1e  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c2a23  mov     rdi, rax
0x1800c2a26  mov     [rsp+250h+var_200], rax
0x1800c2a2b  xor     edx, edx; Val
0x1800c2a2d  mov     r8d, 150h; Size
0x1800c2a33  lea     rcx, [rbp+150h+var_1A0]; void *
0x1800c2a37  call    memset_0
0x1800c2a3c  mov     rcx, rdi
0x1800c2a3f  call    ?get@Size@?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@UE$AAAIXZ; Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>::Size::get(void)
0x1800c2a44  mov     ebx, eax
0x1800c2a46  lea     rdx, aSettingsfilter; "SettingsFilterCacheManager_FilterDevice"...
0x1800c2a4d  lea     rcx, [rbp+150h+var_1A0]; struct wil::details::IFailureCallback *
0x1800c2a51  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c2a56  lea     rax, ??_7SettingsFilterCacheManager_FilterDeviceItems@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::`vftable'
0x1800c2a5d  mov     [rbp+150h+var_1A0], rax
0x1800c2a61  mov     r8d, r15d; unsigned int
0x1800c2a64  mov     edx, ebx; unsigned int
0x1800c2a66  lea     rcx, [rbp+150h+var_1A0]; this
0x1800c2a6a  call    ?StartActivity@SettingsFilterCacheManager_FilterDeviceItems@ConstraintIndexTelemetry@@QEAAXII@Z; ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::StartActivity(uint,uint)
0x1800c2a6f  nop
0x1800c2a70  xorps   xmm0, xmm0
0x1800c2a73  xor     eax, eax
0x1800c2a75  movups  [rbp+150h+var_1C8], xmm0
0x1800c2a79  mov     [rbp+150h+var_1B8], rax
0x1800c2a7d  lea     rcx, [rbp+150h+var_1C8]
0x1800c2a81  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x1800c2a86  nop
0x1800c2a87  xor     eax, eax
0x1800c2a89  movups  [rsp+250h+var_1E0], xmm0
0x1800c2a8e  mov     [rbp+150h+var_1D0], rax
0x1800c2a92  lea     rcx, [rsp+250h+var_1E0]
0x1800c2a97  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x1800c2a9c  nop
0x1800c2a9d  mov     edx, 0B0h
0x1800c2aa2  lea     ecx, [rdx-28h]
0x1800c2aa5  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x1800c2aab  mov     [rsp+250h+pExceptionObject], rax
0x1800c2ab0  mov     rcx, rax
0x1800c2ab3  call    ??0?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@Collections@Platform@@QE$AAA@XZ; Platform::Collections::Vector<Platform::String *,std::equal_to<Platform::String *>,1>::Vector<Platform::String *,std::equal_to<Platform::String *>,1>(void)
0x1800c2ab8  mov     rbx, rax
0x1800c2abb  mov     [rsp+250h+pExceptionObject], rax
0x1800c2ac0  mov     rcx, rax
0x1800c2ac3  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c2ac8  mov     r14, rax
0x1800c2acb  mov     [rsp+250h+var_208], rax
0x1800c2ad0  mov     rcx, rbx
0x1800c2ad3  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2ad8  nop
0x1800c2ad9  mov     rdx, rdi
0x1800c2adc  lea     rcx, [rsp+250h+var_218]
0x1800c2ae1  call    ??0?$VectorViewIterator@PE$AAVString@Platform@@@Collections@Platform@@QEAA@PE$AAU?$IVectorView@PE$AAVString@Platform@@@1Foundation@Windows@@@Z; Platform::Collections::VectorViewIterator<Platform::String *>::VectorViewIterator<Platform::String *>(Windows::Foundation::Collections::IVectorView<Platform::String *> *)
0x1800c2ae6  nop
0x1800c2ae7  mov     rdx, rdi
0x1800c2aea  lea     rcx, [rbp+150h+var_1B0]
0x1800c2aee  call    ??$end@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@Collections@Foundation@Windows@@YA?AV?$VectorViewIterator@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@0Platform@@PE$AAU?$IVectorView@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@012@@Z; Windows::Foundation::Collections::end<WindowsUdk::System::Profile::SystemSettingEntryPoint *>(Windows::Foundation::Collections::IVectorView<WindowsUdk::System::Profile::SystemSettingEntryPoint *> *)
0x1800c2af3  nop
0x1800c2af4  mov     rsi, [rsp+250h+var_210]
0x1800c2af9  cmp     rsi, [rbp+150h+var_1A8]
0x1800c2afd  jz      loc_1800C2C6F
0x1800c2b03  lea     rcx, [rsp+250h+var_218]
0x1800c2b08  call    ??D?$VectorViewIterator@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Platform@@QEBAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@XZ; Platform::Collections::VectorViewIterator<Cortana::ConstraintIndex::Search::SettingResultItem *>::operator*(void)
0x1800c2b0d  mov     rbx, rax
0x1800c2b10  mov     [rsp+250h+pExceptionObject], rax
0x1800c2b15  mov     rcx, rax
0x1800c2b18  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c2b1d  mov     rdi, rax
0x1800c2b20  mov     [rsp+250h+var_230], rax
0x1800c2b25  mov     rcx, rbx
0x1800c2b28  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2b2d  nop
0x1800c2b2e  mov     r8, r13
0x1800c2b31  mov     rdx, rdi
0x1800c2b34  mov     rcx, r12; this
0x1800c2b37  call    ?_GetFilterState@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAA?AW4FilterState@234@PE$AAVSettingResultItem@234@AEBVcancellation_token@Concurrency@@@Z; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::_GetFilterState(Cortana::ConstraintIndex::Search::SettingResultItem *,Concurrency::cancellation_token const &)
0x1800c2b3c  test    eax, eax
0x1800c2b3e  jz      loc_1800C2C1A
0x1800c2b44  sub     eax, 1
0x1800c2b47  jz      short loc_1800C2BB3
0x1800c2b49  cmp     eax, 1
0x1800c2b4c  jnz     loc_1800C2C2F
0x1800c2b52  mov     rax, qword ptr [rsp+250h+var_1E0+8]
0x1800c2b57  cmp     rax, [rbp+150h+var_1D0]
0x1800c2b5b  jz      short loc_1800C2B72
0x1800c2b5d  lea     rdx, [rsp+250h+var_230]
0x1800c2b62  mov     rcx, rax
0x1800c2b65  call    ??$_Construct_in_place@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@AEBQE$AAV1234@@std@@YAXAEAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@AEBQE$AAV1234@@Z; std::_Construct_in_place<Cortana::ConstraintIndex::Search::SettingResultItem *,Cortana::ConstraintIndex::Search::SettingResultItem * const &>(Cortana::ConstraintIndex::Search::SettingResultItem * &,Cortana::ConstraintIndex::Search::SettingResultItem * const &)
0x1800c2b6a  add     qword ptr [rsp+250h+var_1E0+8], 8
0x1800c2b70  jmp     short loc_1800C2B89
0x1800c2b72  lea     r8, [rsp+250h+var_230]
0x1800c2b77  mov     rdx, rax
0x1800c2b7a  lea     rcx, [rsp+250h+var_1E0]
0x1800c2b7f  call    ??$_Emplace_reallocate@AEBQE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@?$vector@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@V?$allocator@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@@std@@AEAAPEAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@QEAPE$AAV2345@AEBQE$AAV2345@@Z; std::vector<Cortana::ConstraintIndex::Search::SettingResultItem *>::_Emplace_reallocate<Cortana::ConstraintIndex::Search::SettingResultItem * const &>(Cortana::ConstraintIndex::Search::SettingResultItem * * const,Cortana::ConstraintIndex::Search::SettingResultItem * const &)
0x1800c2b84  mov     rdi, [rsp+250h+var_230]
0x1800c2b89  mov     rcx, [rdi+80h]
0x1800c2b90  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800c2b95  mov     rbx, rax
0x1800c2b98  mov     [rsp+250h+var_228], rax
0x1800c2b9d  mov     rdx, rax
0x1800c2ba0  mov     rcx, r14
0x1800c2ba3  call    ?Append@?Q?$IVector@PE$AAVString@Platform@@@Collections@Foundation@Windows@@?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@2Platform@@UE$AAAXPE$AAVString@6@@Z
0x1800c2ba8  nop
0x1800c2ba9  mov     rcx, rbx; string
0x1800c2bac  call    WindowsDeleteString_0
0x1800c2bb1  jmp     short loc_1800C2C1A
0x1800c2bb3  mov     rcx, rdi
0x1800c2bb6  call    ?get@?QISettingResultItem@Search@ConstraintIndex@Cortana@@IsModernSetting@SettingResultItem@234@UE$AAA_NXZ
0x1800c2bbb  test    al, al
0x1800c2bbd  jz      short loc_1800C2BE3
0x1800c2bbf  mov     rax, qword ptr [rbp+150h+var_1C8+8]
0x1800c2bc3  cmp     rax, [rbp+150h+var_1B8]
0x1800c2bc7  jz      short loc_1800C2BDD
0x1800c2bc9  lea     rdx, [rsp+250h+var_230]
0x1800c2bce  mov     rcx, rax
0x1800c2bd1  call    ??$_Construct_in_place@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@AEBQE$AAV1234@@std@@YAXAEAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@AEBQE$AAV1234@@Z; std::_Construct_in_place<Cortana::ConstraintIndex::Search::SettingResultItem *,Cortana::ConstraintIndex::Search::SettingResultItem * const &>(Cortana::ConstraintIndex::Search::SettingResultItem * &,Cortana::ConstraintIndex::Search::SettingResultItem * const &)
0x1800c2bd6  add     qword ptr [rbp+150h+var_1C8+8], 8
0x1800c2bdb  jmp     short loc_1800C2C1A
0x1800c2bdd  lea     rcx, [rbp+150h+var_1C8]
0x1800c2be1  jmp     short loc_1800C2C08
0x1800c2be3  mov     rax, qword ptr [rsp+250h+var_1E0+8]
0x1800c2be8  cmp     rax, [rbp+150h+var_1D0]
0x1800c2bec  jz      short loc_1800C2C03
0x1800c2bee  lea     rdx, [rsp+250h+var_230]
0x1800c2bf3  mov     rcx, rax
0x1800c2bf6  call    ??$_Construct_in_place@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@AEBQE$AAV1234@@std@@YAXAEAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@AEBQE$AAV1234@@Z; std::_Construct_in_place<Cortana::ConstraintIndex::Search::SettingResultItem *,Cortana::ConstraintIndex::Search::SettingResultItem * const &>(Cortana::ConstraintIndex::Search::SettingResultItem * &,Cortana::ConstraintIndex::Search::SettingResultItem * const &)
0x1800c2bfb  add     qword ptr [rsp+250h+var_1E0+8], 8
0x1800c2c01  jmp     short loc_1800C2C1A
0x1800c2c03  lea     rcx, [rsp+250h+var_1E0]
0x1800c2c08  lea     r8, [rsp+250h+var_230]
0x1800c2c0d  mov     rdx, rax
0x1800c2c10  call    ??$_Emplace_reallocate@AEBQE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@?$vector@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@V?$allocator@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@@std@@AEAAPEAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@QEAPE$AAV2345@AEBQE$AAV2345@@Z; std::vector<Cortana::ConstraintIndex::Search::SettingResultItem *>::_Emplace_reallocate<Cortana::ConstraintIndex::Search::SettingResultItem * const &>(Cortana::ConstraintIndex::Search::SettingResultItem * * const,Cortana::ConstraintIndex::Search::SettingResultItem * const &)
0x1800c2c15  mov     rdi, [rsp+250h+var_230]
0x1800c2c1a  mov     rcx, rdi
0x1800c2c1d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2c22  inc     rsi
0x1800c2c25  mov     [rsp+250h+var_210], rsi
0x1800c2c2a  jmp     loc_1800C2AF9
0x1800c2c2f  mov     edx, 90h
0x1800c2c34  lea     ecx, [rdx-28h]
0x1800c2c37  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x1800c2c3d  mov     [rsp+250h+var_228], rax
0x1800c2c42  mov     rcx, rax
0x1800c2c45  call    cs:__imp_??0NotImplementedException@Platform@@QE$AAA@XZ; Platform::NotImplementedException::NotImplementedException(void)
0x1800c2c4b  mov     [rsp+250h+var_228], rax
0x1800c2c50  mov     rcx, rax
0x1800c2c53  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c2c58  mov     [rsp+250h+pExceptionObject], rax
0x1800c2c5d  lea     rdx, _TI11PE$AAVNotImplementedException@Platform@@; pThrowInfo
0x1800c2c64  lea     rcx, [rsp+250h+pExceptionObject]; pExceptionObject
0x1800c2c69  call    _CxxThrowException_0
0x1800c2c6f  mov     rcx, [rbp+150h+var_1B0]
0x1800c2c73  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2c78  nop
0x1800c2c79  mov     rcx, [rsp+250h+var_218]
0x1800c2c7e  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2c83  nop
0x1800c2c84  mov     rsi, r15
0x1800c2c87  mov     rax, qword ptr [rbp+150h+var_1C8+8]
0x1800c2c8b  sub     rax, qword ptr [rbp+150h+var_1C8]
0x1800c2c8f  sar     rax, 3
0x1800c2c93  cmp     rax, r15
0x1800c2c96  jnb     short loc_1800C2CD2
0x1800c2c98  mov     rax, [r14+60h]
0x1800c2c9c  mov     rcx, [rax+8]
0x1800c2ca0  sub     rcx, [rax]
0x1800c2ca3  sar     rcx, 3
0x1800c2ca7  test    ecx, ecx
0x1800c2ca9  jz      short loc_1800C2CD2
0x1800c2cab  mov     rcx, r14
0x1800c2cae  call    ?GetView@?Q?$IVector@PE$AAVString@Platform@@@Collections@Foundation@Windows@@?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@2Platform@@UE$AAAPE$AAU?$IVectorView@PE$AAVString@Platform@@@234@XZ
0x1800c2cb3  mov     rbx, rax
0x1800c2cb6  mov     [rsp+250h+var_228], rax
0x1800c2cbb  mov     r8, r13
0x1800c2cbe  mov     rdx, rax
0x1800c2cc1  mov     rcx, r12
0x1800c2cc4  call    ?_ResolveAndCacheClassicConditionals@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAAXPE$AAU?$IVectorView@PE$AAVString@Platform@@@Collections@Foundation@Windows@@AEBVcancellation_token@Concurrency@@@Z; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::_ResolveAndCacheClassicConditionals(Windows::Foundation::Collections::IVectorView<Platform::String *> *,Concurrency::cancellation_token const &)
0x1800c2cc9  nop
0x1800c2cca  mov     rcx, rbx
0x1800c2ccd  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2cd2  xorps   xmm0, xmm0
0x1800c2cd5  xor     eax, eax
0x1800c2cd7  movups  [rsp+250h+var_1F8], xmm0
0x1800c2cdc  mov     [rsp+250h+var_1E8], rax
0x1800c2ce1  lea     rcx, [rsp+250h+var_1F8]
0x1800c2ce6  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x1800c2ceb  nop
0x1800c2cec  mov     rbx, qword ptr [rbp+150h+var_1C8]
0x1800c2cf0  mov     r15, qword ptr [rbp+150h+var_1C8+8]
0x1800c2cf4  cmp     rbx, r15
0x1800c2cf7  jz      short loc_1800C2D6F
0x1800c2cf9  mov     rcx, [rbx]
0x1800c2cfc  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c2d01  mov     rdi, rax
0x1800c2d04  mov     [rsp+250h+var_230], rax
0x1800c2d09  mov     rax, qword ptr [rsp+250h+var_1F8+8]
0x1800c2d0e  cmp     rax, [rsp+250h+var_1E8]
0x1800c2d13  jz      short loc_1800C2D32
0x1800c2d15  lea     rdx, [rsp+250h+var_230]
0x1800c2d1a  mov     rcx, rax
0x1800c2d1d  call    ??$_Construct_in_place@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@AEBQE$AAV1234@@std@@YAXAEAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@AEBQE$AAV1234@@Z; std::_Construct_in_place<Cortana::ConstraintIndex::Search::SettingResultItem *,Cortana::ConstraintIndex::Search::SettingResultItem * const &>(Cortana::ConstraintIndex::Search::SettingResultItem * &,Cortana::ConstraintIndex::Search::SettingResultItem * const &)
0x1800c2d22  mov     rcx, qword ptr [rsp+250h+var_1F8+8]
0x1800c2d27  add     rcx, 8
0x1800c2d2b  mov     qword ptr [rsp+250h+var_1F8+8], rcx
0x1800c2d30  jmp     short loc_1800C2D4E
0x1800c2d32  lea     r8, [rsp+250h+var_230]
0x1800c2d37  mov     rdx, rax
0x1800c2d3a  lea     rcx, [rsp+250h+var_1F8]
0x1800c2d3f  call    ??$_Emplace_reallocate@AEBQE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@?$vector@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@V?$allocator@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@@std@@AEAAPEAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@QEAPE$AAV2345@AEBQE$AAV2345@@Z; std::vector<Cortana::ConstraintIndex::Search::SettingResultItem *>::_Emplace_reallocate<Cortana::ConstraintIndex::Search::SettingResultItem * const &>(Cortana::ConstraintIndex::Search::SettingResultItem * * const,Cortana::ConstraintIndex::Search::SettingResultItem * const &)
0x1800c2d44  mov     rcx, qword ptr [rsp+250h+var_1F8+8]
0x1800c2d49  mov     rdi, [rsp+250h+var_230]
0x1800c2d4e  sub     rcx, qword ptr [rsp+250h+var_1F8]
0x1800c2d53  sar     rcx, 3
0x1800c2d57  cmp     rcx, rsi
0x1800c2d5a  mov     rcx, rdi
0x1800c2d5d  jz      short loc_1800C2D6A
0x1800c2d5f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2d64  add     rbx, 8
0x1800c2d68  jmp     short loc_1800C2CF4
0x1800c2d6a  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2d6f  mov     rax, qword ptr [rsp+250h+var_1F8+8]
0x1800c2d74  sub     rax, qword ptr [rsp+250h+var_1F8]
0x1800c2d79  sar     rax, 3
0x1800c2d7d  cmp     rax, rsi
0x1800c2d80  jnb     loc_1800C2E1F
0x1800c2d86  mov     rdi, qword ptr [rsp+250h+var_1E0]
0x1800c2d8b  mov     r15, qword ptr [rsp+250h+var_1E0+8]
0x1800c2d90  cmp     rdi, r15
0x1800c2d93  jz      loc_1800C2E1F
0x1800c2d99  mov     rcx, [rdi]
0x1800c2d9c  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c2da1  mov     rbx, rax
0x1800c2da4  mov     [rsp+250h+var_230], rax
0x1800c2da9  mov     r8, r13
0x1800c2dac  mov     rdx, rax
0x1800c2daf  mov     rcx, r12; this
0x1800c2db2  call    ?_GetFilterState@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAA?AW4FilterState@234@PE$AAVSettingResultItem@234@AEBVcancellation_token@Concurrency@@@Z; Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::_GetFilterState(Cortana::ConstraintIndex::Search::SettingResultItem *,Concurrency::cancellation_token const &)
0x1800c2db7  dec     eax
0x1800c2db9  cmp     eax, 1
0x1800c2dbc  ja      short loc_1800C2DF6
0x1800c2dbe  mov     rax, qword ptr [rsp+250h+var_1F8+8]
0x1800c2dc3  cmp     rax, [rsp+250h+var_1E8]
0x1800c2dc8  jz      short loc_1800C2DDF
0x1800c2dca  lea     rdx, [rsp+250h+var_230]
0x1800c2dcf  mov     rcx, rax
0x1800c2dd2  call    ??$_Construct_in_place@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@AEBQE$AAV1234@@std@@YAXAEAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@AEBQE$AAV1234@@Z; std::_Construct_in_place<Cortana::ConstraintIndex::Search::SettingResultItem *,Cortana::ConstraintIndex::Search::SettingResultItem * const &>(Cortana::ConstraintIndex::Search::SettingResultItem * &,Cortana::ConstraintIndex::Search::SettingResultItem * const &)
0x1800c2dd7  add     qword ptr [rsp+250h+var_1F8+8], 8
0x1800c2ddd  jmp     short loc_1800C2DF6
0x1800c2ddf  lea     r8, [rsp+250h+var_230]
0x1800c2de4  mov     rdx, rax
0x1800c2de7  lea     rcx, [rsp+250h+var_1F8]
0x1800c2dec  call    ??$_Emplace_reallocate@AEBQE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@?$vector@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@V?$allocator@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@@std@@AEAAPEAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@QEAPE$AAV2345@AEBQE$AAV2345@@Z; std::vector<Cortana::ConstraintIndex::Search::SettingResultItem *>::_Emplace_reallocate<Cortana::ConstraintIndex::Search::SettingResultItem * const &>(Cortana::ConstraintIndex::Search::SettingResultItem * * const,Cortana::ConstraintIndex::Search::SettingResultItem * const &)
0x1800c2df1  mov     rbx, [rsp+250h+var_230]
0x1800c2df6  mov     rax, qword ptr [rsp+250h+var_1F8+8]
0x1800c2dfb  sub     rax, qword ptr [rsp+250h+var_1F8]
0x1800c2e00  sar     rax, 3
0x1800c2e04  mov     rcx, rbx
0x1800c2e07  cmp     rax, rsi
0x1800c2e0a  jz      short loc_1800C2E1A
0x1800c2e0c  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2e11  add     rdi, 8
0x1800c2e15  jmp     loc_1800C2D90
0x1800c2e1a  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2e1f  mov     edx, 80h
0x1800c2e24  lea     ecx, [rdx-18h]
0x1800c2e27  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x1800c2e2d  mov     [rsp+250h+var_228], rax
0x1800c2e32  lea     rdx, [rsp+250h+var_1F8]
0x1800c2e37  mov     rcx, rax
0x1800c2e3a  call    ??$?0PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@?$VectorView@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@U?$equal_to@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@$00@Collections@Platform@@QE$AAA@$$QEAV?$vector@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@V?$allocator@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@@std@@PEAPEAX@Z; Platform::Collections::VectorView<Cortana::ConstraintIndex::Search::SettingResultItem *,std::equal_to<Cortana::ConstraintIndex::Search::SettingResultItem *>,1>::VectorView<Cortana::ConstraintIndex::Search::SettingResultItem *,std::equal_to<Cortana::ConstraintIndex::Search::SettingResultItem *>,1>(std::vector<Cortana::ConstraintIndex::Search::SettingResultItem *> &&,void * *)
0x1800c2e3f  mov     rbx, rax
0x1800c2e42  mov     [rsp+250h+var_228], rax
0x1800c2e47  mov     rcx, rax
0x1800c2e4a  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c2e4f  mov     rdi, rax
0x1800c2e52  mov     [rsp+250h+var_228], rax
0x1800c2e57  mov     rcx, rbx
0x1800c2e5a  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c2e5f  nop
0x1800c2e60  mov     rcx, rdi
0x1800c2e63  call    ?get@?Q?$IVectorView@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@Size@?$VectorView@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@U?$equal_to@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@$00@2Platform@@UE$AAAIXZ
0x1800c2e68  mov     edx, eax; unsigned int
0x1800c2e6a  lea     rcx, [rbp+150h+var_1A0]; this
0x1800c2e6e  call    ?Stop@SettingsFilterCacheManager_FilterDeviceItems@ConstraintIndexTelemetry@@QEAAXI@Z; ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::Stop(uint)
  ... truncated ...
```
