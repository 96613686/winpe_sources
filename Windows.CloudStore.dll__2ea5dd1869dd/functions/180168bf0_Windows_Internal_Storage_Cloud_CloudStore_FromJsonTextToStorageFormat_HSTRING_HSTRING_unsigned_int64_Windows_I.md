# Windows::Internal::Storage::Cloud::CloudStore::FromJsonTextToStorageFormat(HSTRING__ *,HSTRING__ *,unsigned __int64,Windows::Internal::Storage::Cloud::DataDescriptionLanguage,Windows::Storage::Streams::IBuffer * *)

- ea: `0x180168bf0`
- end: `0x18016917f`
- name: `?FromJsonTextToStorageFormat@CloudStore@Cloud@Storage@Internal@Windows@@UEAAJPEAUHSTRING__@@0_KW4DataDescriptionLanguage@2345@PEAPEAUIBuffer@Streams@35@@Z`
- size: `1423`
- prototype: `int __high(HSTRING, HSTRING, unsigned __int64, enum Windows::Internal::Storage::Cloud::DataDescriptionLanguage, struct Windows::Storage::Streams::IBuffer **)`
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000dfe4`
- `0x18000e828`
- `0x18000fbe0`
- `0x18000fe60`
- `0x180016cf4`
- `0x180019438`
- `0x180019720`
- `0x180021e20`
- `0x1800238d0`
- `0x180024fd0`
- `0x180029da4`
- `0x18002a8a0`
- `0x18002c020`
- `0x18004ee74`
- `0x1800519d0`
- `0x180051a78`
- `0x180051b84`
- `0x180051f38`
- `0x18005ac7c`
- `0x18005edd0`
- `0x180092a34`
- `0x1800c9f2c`
- `0x1800d06f0`
- `0x1800e1d28`
- `0x1800f8390`
- `0x1801021bc`
- `0x1801040b8`
- `0x1801201a0`
- `0x180123882`
- `0x180168bf0`
- `0x180174fc8`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016902e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180168fff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016902e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180168c9b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180168c9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180168d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180168d25`

## string_xrefs

- `0x180168c72`: `Windows.Data.Json.JsonObject`
- `0x180169139`: `JsonParseError:0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStore::FromJsonTextToStorageFormat(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        __int64 a4,
        int a5,
        _QWORD *a6)
{
  const char *v10; // r9
  int ActivationFactory; // eax
  __int64 v12; // rax
  int v13; // ebx
  __int64 v14; // rbx
  void (__fastcall *v15)(__int64, _BYTE *, __int64); // rdi
  __int64 v16; // r8
  __int64 v17; // rcx
  const struct bond::blob *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 Buffer; // rax
  HSTRING_HEADER *p_Src; // rdi
  size_t v24; // rbx
  void *v25; // r8
  int v26; // eax
  void *v27; // rcx
  wil *v28; // rcx
  __int64 result; // rax
  const char *v30; // r9
  const char *v31; // r9
  unsigned int v32; // eax
  int v33; // edx
  unsigned int v34; // eax
  unsigned int v35; // eax
  int v36; // [rsp+20h] [rbp-448h]
  char *v37; // [rsp+28h] [rbp-440h]
  int v38; // [rsp+20h] [rbp-448h]
  int v39; // [rsp+20h] [rbp-448h]
  char *v40; // [rsp+28h] [rbp-440h]
  _BYTE v41[8]; // [rsp+30h] [rbp-438h] BYREF
  void *pv; // [rsp+38h] [rbp-430h] BYREF
  __int64 v43; // [rsp+40h] [rbp-428h] BYREF
  char v44; // [rsp+48h] [rbp-420h]
  __int64 v45; // [rsp+50h] [rbp-418h] BYREF
  __int64 *v46; // [rsp+58h] [rbp-410h] BYREF
  __int16 v47; // [rsp+60h] [rbp-408h] BYREF
  char v48; // [rsp+62h] [rbp-406h]
  __int64 v49; // [rsp+68h] [rbp-400h]
  __int64 v50; // [rsp+70h] [rbp-3F8h]
  int v51; // [rsp+78h] [rbp-3F0h]
  __int128 v52; // [rsp+80h] [rbp-3E8h] BYREF
  int v53; // [rsp+90h] [rbp-3D8h]
  _BYTE v54[8]; // [rsp+A0h] [rbp-3C8h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-3C0h]
  __int64 v56; // [rsp+B0h] [rbp-3B8h]
  __int64 v57; // [rsp+B8h] [rbp-3B0h]
  int v58; // [rsp+C0h] [rbp-3A8h]
  int v59; // [rsp+C4h] [rbp-3A4h]
  int v60; // [rsp+C8h] [rbp-3A0h]
  __int128 v61; // [rsp+D0h] [rbp-398h]
  __int128 v62; // [rsp+E0h] [rbp-388h]
  const bond::Exception *v63; // [rsp+F0h] [rbp-378h] BYREF
  _BYTE v64[24]; // [rsp+F8h] [rbp-370h] BYREF
  _BYTE v65[8]; // [rsp+110h] [rbp-358h] BYREF
  _BYTE v66[56]; // [rsp+118h] [rbp-350h] BYREF
  _BYTE v67[80]; // [rsp+150h] [rbp-318h] BYREF
  HSTRING_HEADER Src; // [rsp+1A0h] [rbp-2C8h] BYREF
  unsigned __int64 v69; // [rsp+1B8h] [rbp-2B0h]
  _BYTE v70[8]; // [rsp+1C0h] [rbp-2A8h] BYREF
  _BYTE v71[24]; // [rsp+1C8h] [rbp-2A0h] BYREF
  _QWORD v72[2]; // [rsp+1E0h] [rbp-288h] BYREF
  __int16 v73; // [rsp+1F0h] [rbp-278h]
  int v74; // [rsp+1F8h] [rbp-270h]
  int v75; // [rsp+1FCh] [rbp-26Ch]
  char v76; // [rsp+200h] [rbp-268h] BYREF
  char *v77; // [rsp+300h] [rbp-168h]
  int v78; // [rsp+308h] [rbp-160h]
  int v79; // [rsp+30Ch] [rbp-15Ch]
  char v80; // [rsp+310h] [rbp-158h] BYREF
  char *v81; // [rsp+410h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+468h] [rbp+0h]

  try
  {
    *a6 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableConvertingUdkJsonToStorageBinaryBlobForPCToPCRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableConvertingUdkJsonToStorageBinaryBlobForPCToPCRestore>::GetImpl'::`2'::impl) )
    {
      if ( a5 )
      {
        v31 = (const char *)(unsigned int)wil::verify_hresult<long>(2147946717LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8B5,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          v31,
          v38);
      }
      v46 = 0;
      wil::com_ptr_t<IShellServiceObject,wil::err_exception_policy>::reset(&v46);
      v69 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&Src, L"Windows.Data.Json.JsonObject", 0x1Du, 0x1Cu);
      ActivationFactory = RoGetActivationFactory(v69, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v46);
      if ( ActivationFactory < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x87C,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v38);
      v41[0] = 0;
      v45 = 0;
      v12 = *v46;
      pv = &v45;
      v43 = 0;
      v44 = 1;
      v13 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, _BYTE *))(v12 + 56))(v46, a3, &v43, v41);
      wil::details::out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>(&pv);
      if ( v13 < 0 || !v41[0] )
      {
        v30 = (const char *)(unsigned int)wil::verify_hresult<long>(2205483015LL);
        LODWORD(v40) = v13;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x883,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          v30,
          (int)"JsonParseError:0x%08x",
          v40);
      }
      v14 = *(_QWORD *)(a1 + 208);
      v15 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v14 + 8LL);
      WindowsGetStringRawBuffer(a2, 0);
      std::wstring::wstring(&Src);
      v16 = WideStringToUtf8String(v70, &Src);
      v15(v14, v64, v16);
      std::string::_Tidy_deallocate(v70);
      std::wstring::~wstring(&Src);
      wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>(
        &pv,
        v45);
      JsonStructureToWalkableStructure((walkable::structure *)v67, (__int64)v64, &pv);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&pv);
      v17 = v45;
      v45 = 0;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      wil::com_ptr_t<IShellServiceObject,wil::err_exception_policy>::reset(&v46);
      schematized_data::schematized_data(v66, v64, v67);
      v47 = 0;
      v48 = 0;
      v49 = 0;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 0;
      v18 = schematized_data::as_blob((schematized_data *)v66);
      v19 = *(_QWORD *)v18;
      v20 = *((_QWORD *)v18 + 1);
      if ( v20 )
        _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
      pv = (void *)v52;
      *(_QWORD *)&v52 = v19;
      v21 = *((_QWORD *)&v52 + 1);
      *((_QWORD *)&v52 + 1) = v20;
      v43 = v21;
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)&v43);
      try
      {
        v53 = *((_DWORD *)v18 + 4);
        v51 = 0;
        v50 = a4;
        LOBYTE(v47) = 1;
        v55 = 0;
        v56 = 0;
        v57 = 0;
        v58 = 0;
        v59 = 32;
        v60 = -1;
        v61 = 0;
        v62 = 0;
        v72[0] = v54;
        v72[1] = 0;
        v73 = 1;
        v74 = 0;
        v75 = 64;
        v77 = &v76;
        v78 = 0;
        v79 = 64;
        v81 = &v80;
        bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteVersion(v72);
        bond::Serialize<bond::BuiltInProtocols,Windows::Data::Platform::LocalCache::CurrentCacheEntry,bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>(
          &v47,
          v72);
        Buffer = bond::OutputMemoryStream<std::allocator<char>>::GetBuffer(v54, v70);
        Base64Encode(&Src, Buffer);
        boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v71);
        p_Src = &Src;
        if ( v69 > 0xF )
          p_Src = (HSTRING_HEADER *)Src.Reserved.Reserved1;
        v24 = *(_QWORD *)&Src.Reserved.Reserved2[16];
        if ( *(_QWORD *)&Src.Reserved.Reserved2[16] > 0xFFFFFFFF )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8A0,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)0x80070057LL,
            v38);
        wil::make_unique_cotaskmem<unsigned char [0]>(&pv, *(_QWORD *)&Src.Reserved.Reserved2[16]);
        memcpy_0(pv, p_Src, v24);
        v25 = pv;
        pv = 0;
        v26 = Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(
                v24,
                v24,
                (__int64)v25,
                (void (__fastcall *)(__int64))CoTaskMemFree,
                a6);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8A5,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)v26,
            v39);
        v27 = pv;
        pv = 0;
        if ( v27 )
          CoTaskMemFree(v27);
        std::string::_Tidy_deallocate(&Src);
        bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::~CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>(v72);
        bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(v54);
        boost::detail::shared_count::~shared_count((boost::detail::shared_count *)((char *)&v52 + 8));
        schematized_data::~schematized_data((schematized_data *)v66);
        walkable::structure::~structure((walkable::structure *)v67);
        boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v65);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v45);
        wil::com_ptr_t<CloudStoreUtilities::TestHooks::IAttributeTestHook2,wil::err_exception_policy>::~com_ptr_t<CloudStoreUtilities::TestHooks::IAttributeTestHook2,wil::err_exception_policy>(&v46);
        result = 0;
      }
      catch ( const bond::Exception *v63 )
      {
        (*(void (__fastcall **)(const bond::Exception *))(*(_QWORD *)v63 + 8LL))(v63);
        v32 = wil::verify_hresult<long>(2147942413LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x8AA,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)v32,
          v33,
          v37);
      }
      catch ( ... )
      {
        v34 = wil::ResultFromCaughtException(v28);
        v35 = wil::verify_hresult<long>(v34);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8AF,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)v35,
          v36);
      }
    }
    else
    {
      result = 2147500033LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8BD,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180168bf0  push    rbx
0x180168bf2  push    rsi
0x180168bf3  push    rdi
0x180168bf4  push    r12
0x180168bf6  push    r13
0x180168bf8  push    r14
0x180168bfa  push    r15
0x180168bfc  sub     rsp, 430h
0x180168c03  mov     rax, cs:__security_cookie
0x180168c0a  xor     rax, rsp
0x180168c0d  mov     [rsp+468h+var_48], rax
0x180168c15  mov     r15, r9
0x180168c18  mov     rbx, r8
0x180168c1b  mov     rsi, rdx
0x180168c1e  mov     rdi, rcx
0x180168c21  mov     r14, qword ptr [rsp+468h+arg_28]
0x180168c29  xor     r12d, r12d
0x180168c2c  mov     [r14], r12
0x180168c2f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableConvertingUdkJsonToStorageBinaryBlobForPCToPCRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableConvertingUdkJsonToStorageBinaryBlobForPCToPCRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableConvertingUdkJsonToStorageBinaryBlobForPCToPCRestore> `wil::Feature<__WilFeatureTraits_Feature_EnableConvertingUdkJsonToStorageBinaryBlobForPCToPCRestore>::GetImpl(void)'::`2'::impl
0x180168c36  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableConvertingUdkJsonToStorageBinaryBlobForPCToPCRestore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableConvertingUdkJsonToStorageBinaryBlobForPCToPCRestore>::__private_IsEnabled(void)
0x180168c3b  test    al, al
0x180168c3d  jz      loc_1801690B0
0x180168c43  cmp     [rsp+468h+arg_20], r12d
0x180168c4b  jnz     loc_180169157
0x180168c51  mov     [rsp+468h+var_410], r12
0x180168c56  lea     rcx, [rsp+468h+var_410]
0x180168c5b  call    ?reset@?$com_ptr_t@UIShellServiceObject@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IShellServiceObject,wil::err_exception_policy>::reset(void)
0x180168c60  mov     [rsp+468h+var_2B0], r12
0x180168c68  lea     r9d, [r12+1Ch]; unsigned int
0x180168c6d  lea     r8d, [r12+1Dh]; unsigned int
0x180168c72  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180168c79  lea     rcx, [rsp+468h+Src]; hstringHeader
0x180168c81  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180168c86  nop
0x180168c87  lea     r8, [rsp+468h+var_410]
0x180168c8c  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180168c93  mov     rcx, [rsp+468h+var_2B0]
0x180168c9b  call    cs:__imp_RoGetActivationFactory
0x180168ca1  mov     rcx, [rsp+468h]; this
0x180168ca9  test    eax, eax
0x180168cab  js      loc_1801690DE
0x180168cb1  mov     [rsp+468h+var_438], r12b
0x180168cb6  mov     [rsp+468h+var_418], r12
0x180168cbb  mov     rcx, [rsp+468h+var_410]
0x180168cc0  mov     rax, [rcx]
0x180168cc3  lea     rdx, [rsp+468h+var_418]
0x180168cc8  mov     [rsp+468h+pv], rdx
0x180168ccd  mov     [rsp+468h+var_428], r12
0x180168cd2  mov     r13d, 1
0x180168cd8  mov     [rsp+468h+var_420], r13b
0x180168cdd  lea     r9, [rsp+468h+var_438]
0x180168ce2  lea     r8, [rsp+468h+var_428]
0x180168ce7  mov     rdx, rbx
0x180168cea  mov     rax, [rax+38h]
0x180168cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168cf3  mov     ebx, eax
0x180168cf5  lea     rcx, [rsp+468h+pv]
0x180168cfa  call    ??1?$out_param_t@V?$com_ptr_t@UIMarshal@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>(void)
0x180168cff  test    ebx, ebx
0x180168d01  js      loc_180169120
0x180168d07  cmp     [rsp+468h+var_438], r12b
0x180168d0c  jz      loc_180169120
0x180168d12  mov     rbx, [rdi+0D0h]
0x180168d19  mov     rax, [rbx]
0x180168d1c  mov     rdi, [rax+8]
0x180168d20  xor     edx, edx; length
0x180168d22  mov     rcx, rsi; string
0x180168d25  call    cs:__imp_WindowsGetStringRawBuffer
0x180168d2b  mov     rdx, rax
0x180168d2e  lea     rcx, [rsp+468h+Src]
0x180168d36  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180168d3b  nop
0x180168d3c  lea     rdx, [rsp+468h+Src]
0x180168d44  lea     rcx, [rsp+468h+var_2A8]
0x180168d4c  call    ?WideStringToUtf8String@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideStringToUtf8String(std::wstring const &)
0x180168d51  nop
0x180168d52  mov     r8, rax
0x180168d55  lea     rdx, [rsp+468h+var_370]
0x180168d5d  mov     rcx, rbx
0x180168d60  mov     rax, rdi
0x180168d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168d68  nop
0x180168d69  lea     rcx, [rsp+468h+var_2A8]; void *
0x180168d71  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180168d76  nop
0x180168d77  lea     rcx, [rsp+468h+Src]
0x180168d7f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180168d84  mov     rdx, [rsp+468h+var_418]
0x180168d89  lea     rcx, [rsp+468h+pv]
0x180168d8e  call    ??0?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>(Windows::Internal::Storage::Cloud::ICloudStoreData *)
0x180168d93  nop
0x180168d94  lea     r8, [rsp+468h+pv]
0x180168d99  lea     rdx, [rsp+468h+var_370]
0x180168da1  lea     rcx, [rsp+468h+var_318]
0x180168da9  call    ?JsonStructureToWalkableStructure@@YA?AVstructure@walkable@@AEBVRuntimeSchema@bond@@AEBV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@@Z; JsonStructureToWalkableStructure(bond::RuntimeSchema const &,wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x180168dae  nop
0x180168daf  lea     rcx, [rsp+468h+pv]
0x180168db4  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180168db9  nop
0x180168dba  mov     rcx, [rsp+468h+var_418]
0x180168dbf  mov     [rsp+468h+var_418], r12
0x180168dc4  test    rcx, rcx
0x180168dc7  jz      short loc_180168DD6
0x180168dc9  mov     rax, [rcx]
0x180168dcc  mov     rax, [rax+10h]
0x180168dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168dd5  nop
0x180168dd6  lea     rcx, [rsp+468h+var_410]
0x180168ddb  call    ?reset@?$com_ptr_t@UIShellServiceObject@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IShellServiceObject,wil::err_exception_policy>::reset(void)
0x180168de0  lea     r8, [rsp+468h+var_318]
0x180168de8  lea     rdx, [rsp+468h+var_370]
0x180168df0  lea     rcx, [rsp+468h+var_350]
0x180168df8  call    ??0schematized_data@@QEAA@AEBVRuntimeSchema@bond@@$$QEAVstructure@walkable@@@Z; schematized_data::schematized_data(bond::RuntimeSchema const &,walkable::structure &&)
0x180168dfd  nop
0x180168dfe  mov     [rsp+468h+var_408], r12w
0x180168e04  mov     [rsp+468h+var_406], r12b
0x180168e09  mov     [rsp+468h+var_400], r12
0x180168e0e  mov     [rsp+468h+var_3F8], r12
0x180168e13  mov     [rsp+468h+var_3F0], r12d
0x180168e18  xorps   xmm0, xmm0
0x180168e1b  movdqu  [rsp+468h+var_3E8], xmm0
0x180168e24  mov     [rsp+468h+var_3D8], r12d
0x180168e2c  lea     rcx, [rsp+468h+var_350]; this
0x180168e34  call    ?as_blob@schematized_data@@QEBAAEBVblob@bond@@XZ; schematized_data::as_blob(void)
0x180168e39  mov     rbx, rax
0x180168e3c  mov     rax, [rax]
0x180168e3f  mov     rdx, [rbx+8]
0x180168e43  test    rdx, rdx
0x180168e46  jz      short loc_180168E4C
0x180168e48  lock inc dword ptr [rdx+8]
0x180168e4c  mov     rcx, qword ptr [rsp+468h+var_3E8]
0x180168e54  mov     [rsp+468h+pv], rcx
0x180168e59  mov     qword ptr [rsp+468h+var_3E8], rax
0x180168e61  mov     rax, qword ptr [rsp+468h+var_3E8+8]
0x180168e69  mov     qword ptr [rsp+468h+var_3E8+8], rdx
0x180168e71  mov     [rsp+468h+var_428], rax
0x180168e76  lea     rcx, [rsp+468h+var_428]; this
0x180168e7b  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180168e80  mov     eax, [rbx+10h]
0x180168e83  mov     [rsp+468h+var_3D8], eax
0x180168e8a  mov     [rsp+468h+var_3F0], r12d
0x180168e8f  mov     [rsp+468h+var_3F8], r15
0x180168e94  mov     byte ptr [rsp+468h+var_408], r13b
0x180168e99  mov     [rsp+468h+var_3C0], r12
0x180168ea1  mov     [rsp+468h+var_3B8], r12
0x180168ea9  mov     [rsp+468h+var_3B0], r12
0x180168eb1  mov     [rsp+468h+var_3A8], r12d
0x180168eb9  mov     [rsp+468h+var_3A4], 20h ; ' '
0x180168ec4  mov     esi, 0FFFFFFFFh
0x180168ec9  mov     [rsp+468h+var_3A0], esi
0x180168ed0  xorps   xmm0, xmm0
0x180168ed3  movdqa  [rsp+468h+var_398], xmm0
0x180168edc  xorps   xmm1, xmm1
0x180168edf  movdqa  [rsp+468h+var_388], xmm1
0x180168ee8  lea     rax, [rsp+468h+var_3C8]
0x180168ef0  mov     [rsp+468h+var_288], rax
0x180168ef8  mov     [rsp+468h+var_280], r12
0x180168f00  mov     [rsp+468h+var_278], r13w
0x180168f09  mov     [rsp+468h+var_270], r12d
0x180168f11  mov     ecx, 40h ; '@'
0x180168f16  mov     [rsp+468h+var_26C], ecx
0x180168f1d  lea     rax, [rsp+468h+var_268]
0x180168f25  mov     [rsp+468h+var_168], rax
0x180168f2d  mov     [rsp+468h+var_160], r12d
0x180168f35  mov     [rsp+468h+var_15C], ecx
0x180168f3c  lea     rax, [rsp+468h+var_158]
0x180168f44  mov     [rsp+468h+var_58], rax
0x180168f4c  lea     rcx, [rsp+468h+var_288]
0x180168f54  call    ?WriteVersion@?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAAXXZ; bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteVersion(void)
0x180168f59  lea     rdx, [rsp+468h+var_288]
0x180168f61  lea     rcx, [rsp+468h+var_408]
0x180168f66  call    ??$Serialize@UBuiltInProtocols@bond@@UCurrentCacheEntry@LocalCache@Platform@Data@Windows@@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@2@@bond@@YAXAEBUCurrentCacheEntry@LocalCache@Platform@Data@Windows@@AEAV?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@0@@Z; bond::Serialize<bond::BuiltInProtocols,Windows::Data::Platform::LocalCache::CurrentCacheEntry,bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>(Windows::Data::Platform::LocalCache::CurrentCacheEntry const &,bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>> &)
0x180168f6b  lea     rdx, [rsp+468h+var_2A8]
0x180168f73  lea     rcx, [rsp+468h+var_3C8]
0x180168f7b  call    ?GetBuffer@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEBA?AVblob@2@XZ; bond::OutputMemoryStream<std::allocator<char>>::GetBuffer(void)
0x180168f80  nop
0x180168f81  mov     rdx, rax
0x180168f84  lea     rcx, [rsp+468h+Src]
0x180168f8c  call    ?Base64Encode@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVblob@bond@@@Z; Base64Encode(bond::blob const &)
0x180168f91  nop
0x180168f92  lea     rcx, [rsp+468h+var_2A0]; this
0x180168f9a  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180168f9f  lea     rdi, [rsp+468h+Src]
0x180168fa7  cmp     [rsp+468h+var_2B0], 0Fh
0x180168fb0  cmova   rdi, [rsp+468h+Src]
0x180168fb9  mov     rbx, [rsp+468h+Size]
0x180168fc1  mov     rcx, [rsp+468h]; this
0x180168fc9  cmp     rbx, rsi
0x180168fcc  ja      loc_1801690F3
0x180168fd2  mov     rdx, rbx
0x180168fd5  lea     rcx, [rsp+468h+pv]
0x180168fda  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x180168fdf  nop
0x180168fe0  mov     r8, rbx; Size
0x180168fe3  mov     rdx, rdi; Src
0x180168fe6  mov     rcx, [rsp+468h+pv]; void *
0x180168feb  call    memcpy_0
0x180168ff0  mov     r8, [rsp+468h+pv]
0x180168ff5  mov     [rsp+468h+pv], r12
0x180168ffa  mov     qword ptr [rsp+468h+var_448], r14; int
0x180168fff  mov     r9, cs:__imp_CoTaskMemFree
0x180169006  mov     edx, ebx
0x180169008  mov     ecx, ebx
0x18016900a  call    ??$MakeCBuffer@P6AXPEAX@Z@Streams@Storage@Windows@@YAJIIPEAEP6AXPEAX@ZPEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(uint,uint,uchar *,void (*)(void *),Windows::Storage::Streams::IBuffer * *)
0x18016900f  mov     rcx, [rsp+468h]; this
0x180169017  test    eax, eax
0x180169019  js      loc_18016910B
0x18016901f  mov     rcx, [rsp+468h+pv]; pv
0x180169024  mov     [rsp+468h+pv], r12
0x180169029  test    rcx, rcx
0x18016902c  jz      short loc_180169035
0x18016902e  call    cs:__imp_CoTaskMemFree
0x180169034  nop
0x180169035  lea     rcx, [rsp+468h+Src]; void *
0x18016903d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180169042  nop
0x180169043  lea     rcx, [rsp+468h+var_288]
0x18016904b  call    ??1?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAA@XZ; bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::~CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>(void)
0x180169050  nop
0x180169051  lea     rcx, [rsp+468h+var_3C8]
0x180169059  call    ??1?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@XZ; bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(void)
0x18016905e  nop
0x18016905f  lea     rcx, [rsp+468h+var_3E8+8]; this
0x180169067  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x18016906c  nop
0x18016906d  lea     rcx, [rsp+468h+var_350]; this
0x180169075  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x18016907a  nop
0x18016907b  lea     rcx, [rsp+468h+var_318]; this
0x180169083  call    ??1structure@walkable@@QEAA@XZ; walkable::structure::~structure(void)
0x180169088  nop
0x180169089  lea     rcx, [rsp+468h+var_358]; this
0x180169091  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180169096  nop
0x180169097  lea     rcx, [rsp+468h+var_418]
0x18016909c  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1801690a1  nop
0x1801690a2  lea     rcx, [rsp+468h+var_410]
0x1801690a7  call    ??1?$com_ptr_t@VIAttributeTestHook2@TestHooks@CloudStoreUtilities@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudStoreUtilities::TestHooks::IAttributeTestHook2,wil::err_exception_policy>::~com_ptr_t<CloudStoreUtilities::TestHooks::IAttributeTestHook2,wil::err_exception_policy>(void)
0x1801690ac  xor     eax, eax
0x1801690ae  jmp     short loc_1801690BB
0x1801690b0  mov     eax, 80004001h
0x1801690b5  jmp     short loc_1801690BB
0x1801690b7  mov     eax, dword ptr [rsp+468h+pv]
0x1801690bb  mov     rcx, [rsp+468h+var_48]
0x1801690c3  xor     rcx, rsp; StackCookie
0x1801690c6  call    __security_check_cookie
0x1801690cb  add     rsp, 430h
0x1801690d2  pop     r15
0x1801690d4  pop     r14
0x1801690d6  pop     r13
0x1801690d8  pop     r12
0x1801690da  pop     rdi
0x1801690db  pop     rsi
0x1801690dc  pop     rbx
0x1801690dd  retn
0x1801690de  mov     r9d, eax; char *
0x1801690e1  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1801690e8  mov     edx, 87Ch; void *
0x1801690ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801690f3  mov     r9d, 80070057h; char *
0x1801690f9  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180169100  mov     edx, 8A0h; void *
0x180169105  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18016910b  mov     r9d, eax; char *
0x18016910e  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180169115  mov     edx, 8A5h; void *
0x18016911a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180169120  mov     ecx, 83750007h
0x180169125  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18016912a  mov     r9d, eax; char *
0x18016912d  mov     rcx, [rsp+468h]; this
0x180169135  mov     dword ptr [rsp+468h+var_440], ebx; char *
0x180169139  lea     rax, aJsonparseerror; "JsonParseError:0x%08x"
0x180169140  mov     qword ptr [rsp+468h+var_448], rax; int
0x180169145  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18016914c  mov     edx, 883h; void *
0x180169151  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180169157  mov     ecx, 800710DDh
0x18016915c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180169161  mov     r9d, eax; char *
0x180169164  mov     rcx, [rsp+468h]; this
0x18016916c  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180169173  mov     edx, 8B5h; void *
0x180169178  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
