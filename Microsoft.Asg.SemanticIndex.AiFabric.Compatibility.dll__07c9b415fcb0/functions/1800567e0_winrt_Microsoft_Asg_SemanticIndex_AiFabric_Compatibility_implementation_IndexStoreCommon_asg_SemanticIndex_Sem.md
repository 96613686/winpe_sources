# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>(std::filesystem::path,std::span<uchar const,-1>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexCreationDisposition,asg::SemanticRegistry::VectorSpaceDescriptor const &,asg::SemanticRegistry::SemanticContentType,asg::SemanticIndex::IndexQuantizationPreference,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,std::unique_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile,std::default_delete<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile>>)

- ea: `0x1800567e0`
- end: `0x180056e51`
- name: `??0?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@V?$span@$$CBE$0?0@std@@W4IndexCreationDisposition@234567@AEBVVectorSpaceDescriptor@SemanticRegistry@asg@@W4SemanticContentType@SemanticRegistry@asg@@W4IndexQuantizationPreference@4asg@@UTextEmbeddingsGenerator@234567@6V?$unique_ptr@UIndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@U?$default_delete@UIndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@@Z`
- size: `1649`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18023a270`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180003fb0`
- `0x180004040`
- `0x180004510`
- `0x180007740`
- `0x180007de0`
- `0x18000d230`
- `0x18000d290`
- `0x180012410`
- `0x180019520`
- `0x18001fdb0`
- `0x18002dae0`
- `0x18003e920`
- `0x18003ef60`
- `0x18003f6a0`
- `0x1800442c0`
- `0x180044330`
- `0x1800452a0`
- `0x180045320`
- `0x180045390`
- `0x1800463c0`
- `0x180046f70`
- `0x1800567e0`
- `0x180056e60`
- `0x180067b60`
- `0x1801d2824`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180056940`
- `KERNEL32!GetLastError` at `0x180056940`
- `KERNEL32!CloseHandle` at `0x180056ae8`
- `KERNEL32!CloseHandle` at `0x180056bad`
- `KERNEL32!CloseHandle` at `0x180056ae8`
- `KERNEL32!CloseHandle` at `0x180056bad`
- `KERNEL32!CreateEventExW` at `0x18005692c`
- `KERNEL32!CreateEventExW` at `0x18005692c`

## string_xrefs

- `0x180056c0c`: `could not get exclusive access to the database lock file`
- `0x180056b26`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180056bfb`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180056c6d`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180056cc1`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180056d15`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180056d69`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180056dbd`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180056cd6`: `IndexCreationDisposition::OpenExisting was specified and the database file is not present for the specified basePath`
- `0x180056c82`: `basePath must be a file path, not a directory path`
- `0x180056b32`: `__cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 *a8,
        __int64 *a9,
        _QWORD *a10)
{
  _QWORD *v13; // rax
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 v17; // rax
  __int64 v18; // rax
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation *v19; // rcx
  __int64 v20; // rcx
  __int64 any_status; // rax
  const struct std::filesystem::path *v22; // rdx
  bool v23; // al
  void ***v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rax
  _QWORD *v28; // rbx
  void *v29; // rcx
  _QWORD *v30; // rbx
  void *v31; // rcx
  unsigned int *v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned int *v36; // rax
  __int64 v37; // [rsp+20h] [rbp-E0h] BYREF
  const char *v38; // [rsp+28h] [rbp-D8h]
  const char *v39; // [rsp+30h] [rbp-D0h]
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  const char *v41; // [rsp+48h] [rbp-B8h]
  __int64 v42; // [rsp+50h] [rbp-B0h]
  _QWORD v43[2]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pExceptionObject[16]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v45; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v46[5]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v47[32]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-28h]
  _BYTE v49[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v50[32]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v46[0] = a3;
  v46[1] = a1;
  v48 = a2;
  v46[2] = a8;
  v46[3] = a9;
  v45 = a10;
  v46[4] = a10;
  *(_OWORD *)(a1 + 24) = 0;
  *(_OWORD *)(a1 + 40) = 0;
  *(_OWORD *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 72) = -1;
  *(_DWORD *)a1 = 258;
  *(_DWORD *)(a1 + 76) = 0;
  *(_OWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_OWORD *)(a1 + 80) = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 96) = *(_OWORD *)(a2 + 16);
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  std::basic_string<char16_t>::basic_string<char16_t>(pExceptionObject, a1 + 80);
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(
    a1 + 112,
    (std::filesystem *)pExceptionObject);
  *(_QWORD *)(a1 + 144) = a4;
  *(_DWORD *)(a1 + 152) = a6;
  *(_DWORD *)(a1 + 156) = a7;
  *(_BYTE *)(a1 + 164) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  v13 = (_QWORD *)*v45;
  *v45 = 0;
  *(_QWORD *)(a1 + 192) = v13;
  *(_DWORD *)(a1 + 200) = 0x10000;
  *(_QWORD *)(a1 + 208) = 0;
  v37 = a1 + 216;
  *(_QWORD *)(a1 + 216) = 0;
  v43[0] = CreateEventExW(0, 0, 3u, 0x1F0003u);
  if ( !v43[0] )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v14, v15, v16);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1 + 216,
    v43[0]);
  *(_BYTE *)(a1 + 224) = 0;
  v17 = *a8;
  *a8 = 0;
  *(_QWORD *)(a1 + 232) = v17;
  v18 = *a9;
  *a9 = 0;
  *(_QWORD *)(a1 + 240) = v18;
  std::unordered_set<asg::Guid>::unordered_set<asg::Guid>(a1 + 248);
  std::unordered_map<winrt::guid,std::shared_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession>>::unordered_map<winrt::guid,std::shared_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession>>(a1 + 312);
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::OneTimeInitialization(v19);
  std::basic_string<char16_t>::basic_string<char16_t>(pExceptionObject, a1 + 112);
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::RenameOldFileIfFound(
    v20,
    pExceptionObject);
  any_status = std::filesystem::_Get_any_status(v43, a1 + 80);
  v37 = *(_QWORD *)any_status;
  v22 = (const struct std::filesystem::path *)*(unsigned int *)(any_status + 8);
  if ( (_DWORD)v22 && (((_DWORD)v37 - 1) & 0xFFFFFFF7) != 0 )
    std::filesystem::_Throw_fs_error((unsigned int)v37, v22, a1 + 80);
  if ( (_DWORD)v37 == 3 )
  {
    LODWORD(v37) = 182;
    v38 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
    v39 = 0;
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)pExceptionObject,
      L"basePath must be a file path, not a directory path");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&v40,
      (const struct winrt::param::hstring *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)&v37);
    throw (winrt::hresult_invalid_argument *)&v40;
  }
  v23 = std::filesystem::exists((std::filesystem *)(a1 + 112), v22);
  v24 = (void ***)v23;
  if ( a4 == 2 )
  {
    if ( !v23 )
    {
      LODWORD(v37) = 192;
      v38 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
      v39 = 0;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)pExceptionObject,
        L"IndexCreationDisposition::OpenExisting was specified and the database file is not present for the specified basePath");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)&v40,
        (const struct winrt::param::hstring *)pExceptionObject,
        (const struct winrt::impl::slim_source_location *)&v37);
      throw (winrt::hresult_invalid_argument *)&v40;
    }
    *(_DWORD *)(a1 + 148) = 1;
  }
  else if ( !a4 )
  {
    *(_DWORD *)(a1 + 148) = v23;
  }
  if ( !*(_QWORD *)(a1 + 232) )
  {
    LODWORD(v37) = 207;
    v38 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
    v39 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)pExceptionObject, L"generator cannot be null");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&v40,
      (const struct winrt::param::hstring *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)&v37);
    throw (winrt::hresult_invalid_argument *)&v40;
  }
  if ( !*(_QWORD *)(a1 + 240) )
  {
    LODWORD(v37) = 212;
    v38 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
    v39 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)pExceptionObject, L"textQueryGenerator cannot be null");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&v40,
      (const struct winrt::param::hstring *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)&v37);
    throw (winrt::hresult_invalid_argument *)&v40;
  }
  if ( a4 == 1 )
  {
    *(_DWORD *)(a1 + 148) = 0;
    if ( v23 )
    {
      v25 = a1 + 112;
      if ( *(_QWORD *)(a1 + 136) > 7u )
        v25 = *(_QWORD *)(a1 + 112);
      LODWORD(v37) = (unsigned __int64)_std_fs_remove(v25) >> 32;
      v24 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
      v38 = (const char *)&`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
      if ( (_DWORD)v37 )
      {
        LODWORD(v40) = 227;
        v41 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
        v42 = 0;
        v34 = std::filesystem::path::wstring(a1 + 112, v49);
        v46[0] = std::basic_string<char16_t>::c_str(v34);
        LODWORD(v43[0]) = std::error_code::value((std::error_code *)&v37);
        v35 = asg::wformat<int,wchar_t *>(v50, L"Could not reset existing database file (%d) \"%ls\". ", v43, v46);
        winrt::param::hstring::hstring(v47, v35);
        v36 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v45, -2081706721);
        winrt::hresult_error::hresult_error(pExceptionObject, *v36, v47, &v40);
        throw (winrt::hresult_error *)pExceptionObject;
      }
    }
  }
  if ( !(unsigned __int8)asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_57696949>>(v24) )
  {
    v37 = (__int64)operator new(0x30u);
    std::basic_string<char16_t>::basic_string<char16_t>(pExceptionObject, a1 + 112);
    v27 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(
            v37,
            (__int64)pExceptionObject,
            0);
    v28 = *(_QWORD **)(a1 + 192);
    *(_QWORD *)(a1 + 192) = v27;
    if ( v28 )
    {
      v29 = (void *)v28[5];
      if ( v29 != (void *)-1LL && v29 )
        CloseHandle(v29);
      std::basic_string<char16_t>::_Tidy_deallocate(v28 + 1);
      operator delete(v28);
    }
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 192) + 40LL) == -1 )
    {
      LODWORD(v40) = 249;
      v41 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
      v42 = 0;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v47,
        L"could not get exclusive access to the database lock file");
      v33 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v45, -2081706721);
      winrt::hresult_error::hresult_error(pExceptionObject, *v33, v47, &v40);
      throw (winrt::hresult_error *)pExceptionObject;
    }
  }
  v37 = 0xD000000FDLL;
  v38 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
  v39 = "__cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class as"
        "g::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextE"
        "mbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmb"
        "eddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,s"
        "truct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::I"
        "ndexStoreCommon(class std::filesystem::path,class std::span<unsigned char const ,-1>,enum winrt::Microsoft::Asg:"
        ":SemanticIndex::AiFabric::Compatibility::IndexCreationDisposition,const class asg::SemanticRegistry::VectorSpace"
        "Descriptor &,enum asg::SemanticRegistry::SemanticContentType,enum asg::SemanticIndex::IndexQuantizationPreferenc"
        "e,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Mi"
        "crosoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,class std::unique_ptr<struct winrt"
        "::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile,struct std::default_dele"
        "te<struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile> >)";
  v40 = a1;
  v41 = (const char *)v46[0];
  v42 = a5;
  ((void (__fastcall *)(__int64, __int64 *, __int64, __int64 *))winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::$$A6AXX_E::Z::InvokeDbMethod<`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>'::`2'::_lambda_1_,std::filesystem::Vpath::A * const,std::span<unsigned char const,-1>,enum winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexCreationDisposition,asg::SemanticRegistry::VectorSpaceDescriptor const &,enum asg::SemanticRegistry::SemanticContentType,enum asg::SemanticIndex::IndexQuantizationPreference,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,enum asg::SemanticIndex::IndexQuantizationPreference,std::unique_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile>>)(
    a1,
    &v40,
    v26,
    &v37);
  std::basic_string<char16_t>::_Tidy_deallocate(a2);
  if ( *a8 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a8);
  if ( *a9 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a9);
  v30 = (_QWORD *)*v45;
  if ( *v45 )
  {
    v31 = (void *)v30[5];
    if ( v31 != (void *)-1LL && v31 )
      CloseHandle(v31);
    std::basic_string<char16_t>::_Tidy_deallocate(v30 + 1);
    operator delete(v30);
  }
  return a1;
}

```

## disassembly

```asm
0x1800567e0  mov     [rsp-8+arg_10], rbx
0x1800567e5  push    rbp
0x1800567e6  push    rsi
0x1800567e7  push    rdi
0x1800567e8  push    r12
0x1800567ea  push    r13
0x1800567ec  push    r14
0x1800567ee  push    r15
0x1800567f0  lea     rbp, [rsp-30h]
0x1800567f5  sub     rsp, 130h
0x1800567fc  mov     rax, cs:__security_cookie
0x180056803  xor     rax, rsp
0x180056806  mov     [rbp+60h+var_40], rax
0x18005680a  mov     ebx, r9d
0x18005680d  mov     [rbp+60h+var_D0], r8
0x180056811  mov     r12, rdx
0x180056814  mov     rdi, rcx
0x180056817  mov     [rbp+60h+var_C8], rcx
0x18005681b  mov     [rbp+60h+var_88], rdx
0x18005681f  mov     r15, [rbp+60h+arg_38]
0x180056826  mov     [rbp+60h+var_C0], r15
0x18005682a  mov     r14, [rbp+60h+arg_40]
0x180056831  mov     [rbp+60h+var_B8], r14
0x180056835  mov     rax, [rbp+60h+arg_48]
0x18005683c  mov     [rbp+60h+var_D8], rax
0x180056840  mov     [rbp+60h+var_B0], rax
0x180056844  xor     eax, eax
0x180056846  xorps   xmm0, xmm0
0x180056849  movups  xmmword ptr [rcx+18h], xmm0
0x18005684d  movups  xmmword ptr [rcx+28h], xmm0
0x180056851  movups  xmmword ptr [rcx+38h], xmm0
0x180056855  xorps   xmm1, xmm1
0x180056858  movups  xmmword ptr [rcx+8], xmm1
0x18005685c  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x180056863  mov     dword ptr [rcx], 102h
0x180056869  mov     [rcx+4Ch], eax
0x18005686c  movups  xmmword ptr [rcx+50h], xmm0
0x180056870  mov     [rcx+60h], rax
0x180056874  mov     [rcx+68h], rax
0x180056878  movups  xmm0, xmmword ptr [rdx]
0x18005687b  movups  xmmword ptr [rcx+50h], xmm0
0x18005687f  movups  xmm1, xmmword ptr [rdx+10h]
0x180056883  movups  xmmword ptr [rcx+60h], xmm1
0x180056887  mov     [rdx+10h], rax
0x18005688b  mov     qword ptr [rdx+18h], 7
0x180056893  mov     [rdx], ax
0x180056896  lea     rdx, [rcx+50h]
0x18005689a  lea     rcx, [rsp+160h+pExceptionObject]
0x18005689f  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@AEBV01@@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::basic_string<char16_t> const &)
0x1800568a4  lea     rdx, [rsp+160h+pExceptionObject]
0x1800568a9  lea     rcx, [rdi+70h]
0x1800568ad  call    ?AppendDbExtensionIfRequired@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AVpath@filesystem@std@@V89std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(std::filesystem::path)
0x1800568b2  nop
0x1800568b3  mov     [rdi+90h], ebx
0x1800568b9  xor     edx, edx; lpName
0x1800568bb  mov     [rdi+94h], edx
0x1800568c1  mov     eax, [rbp+60h+arg_28]
0x1800568c7  mov     [rdi+98h], eax
0x1800568cd  mov     eax, [rbp+60h+arg_30]
0x1800568d3  mov     [rdi+9Ch], eax
0x1800568d9  mov     [rdi+0A4h], dl
0x1800568df  mov     [rdi+0A8h], rdx
0x1800568e6  mov     [rdi+0B0h], rdx
0x1800568ed  mov     rcx, [rbp+60h+var_D8]
0x1800568f1  mov     rax, [rcx]
0x1800568f4  mov     [rcx], rdx
0x1800568f7  mov     [rdi+0C0h], rax
0x1800568fe  mov     dword ptr [rdi+0C8h], 10000h
0x180056908  mov     [rdi+0D0h], rdx
0x18005690f  lea     rax, [rdi+0D8h]
0x180056916  mov     qword ptr [rsp+160h+var_140], rax
0x18005691b  mov     [rax], rdx
0x18005691e  xor     ecx, ecx; lpEventAttributes
0x180056920  mov     r9d, 1F0003h; dwDesiredAccess
0x180056926  mov     r8d, 3; dwFlags
0x18005692c  call    cs:__imp_CreateEventExW
0x180056932  mov     [rsp+160h+var_108], rax
0x180056937  test    rax, rax
0x18005693a  jz      loc_180056C51
0x180056940  call    cs:__imp_GetLastError
0x180056946  mov     rdx, [rsp+160h+var_108]
0x18005694b  lea     rcx, [rdi+0D8h]
0x180056952  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180056957  nop
0x180056958  mov     byte ptr [rdi+0E0h], 0
0x18005695f  mov     rax, [r15]
0x180056962  xor     ecx, ecx
0x180056964  mov     [r15], rcx
0x180056967  mov     [rdi+0E8h], rax
0x18005696e  mov     rax, [r14]
0x180056971  mov     [r14], rcx
0x180056974  mov     [rdi+0F0h], rax
0x18005697b  lea     rcx, [rdi+0F8h]
0x180056982  call    ??0?$unordered_set@UGuid@asg@@U?$hash@UGuid@asg@@@std@@U?$equal_to@UGuid@asg@@@4@V?$allocator@UGuid@asg@@@4@@std@@QEAA@XZ; std::unordered_set<asg::Guid>::unordered_set<asg::Guid>(void)
0x180056987  nop
0x180056988  lea     rcx, [rdi+138h]
0x18005698f  call    ??0?$unordered_map@Uguid@winrt@@V?$shared_ptr@UItemEmbeddingGenerationSession@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@U?$hash@Uguid@winrt@@@4@U?$equal_to@Uguid@winrt@@@4@V?$allocator@U?$pair@$$CBUguid@winrt@@V?$shared_ptr@UItemEmbeddingGenerationSession@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@@4@@std@@QEAA@XZ; std::unordered_map<winrt::guid,std::shared_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession>>::unordered_map<winrt::guid,std::shared_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession>>(void)
0x180056994  nop
0x180056995  call    ?OneTimeInitialization@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA_NXZ; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::OneTimeInitialization(void)
0x18005699a  lea     rdx, [rdi+70h]
0x18005699e  lea     rcx, [rsp+160h+pExceptionObject]
0x1800569a3  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@AEBV01@@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::basic_string<char16_t> const &)
0x1800569a8  lea     rdx, [rsp+160h+pExceptionObject]
0x1800569ad  call    ?RenameOldFileIfFound@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAAXVpath@filesystem@std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::RenameOldFileIfFound(std::filesystem::path)
0x1800569b2  lea     rdx, [rdi+50h]
0x1800569b6  lea     rcx, [rsp+160h+var_108]
0x1800569bb  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x1800569c0  movsd   xmm0, qword ptr [rax]
0x1800569c4  movsd   qword ptr [rsp+160h+var_140], xmm0
0x1800569ca  mov     edx, [rax+8]; struct std::filesystem::path *
0x1800569cd  mov     ecx, dword ptr [rsp+160h+var_140]
0x1800569d1  test    edx, edx
0x1800569d3  jz      short loc_1800569E3
0x1800569d5  lea     eax, [rcx-1]
0x1800569d8  test    eax, 0FFFFFFF7h
0x1800569dd  jnz     loc_180056C5B
0x1800569e3  cmp     ecx, 3
0x1800569e6  jz      loc_180056C65
0x1800569ec  lea     rcx, [rdi+70h]; this
0x1800569f0  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1800569f5  movzx   ecx, al
0x1800569f8  cmp     ebx, 2
0x1800569fb  jnz     short loc_180056A11
0x1800569fd  test    al, al
0x1800569ff  jz      loc_180056CB9
0x180056a05  mov     dword ptr [rdi+94h], 1
0x180056a0f  jmp     short loc_180056A1B
0x180056a11  test    ebx, ebx
0x180056a13  jnz     short loc_180056A1B
0x180056a15  mov     [rdi+94h], ecx
0x180056a1b  cmp     qword ptr [rdi+0E8h], 0
0x180056a23  jz      loc_180056D0D
0x180056a29  cmp     qword ptr [rdi+0F0h], 0
0x180056a31  jz      loc_180056D61
0x180056a37  xor     r13d, r13d
0x180056a3a  cmp     ebx, 1
0x180056a3d  jnz     short loc_180056A88
0x180056a3f  mov     [rdi+94h], r13d
0x180056a46  test    al, al
0x180056a48  jz      short loc_180056A88
0x180056a4a  lea     rcx, [rdi+70h]
0x180056a4e  cmp     qword ptr [rdi+88h], 7
0x180056a56  jbe     short loc_180056A5C
0x180056a58  mov     rcx, [rdi+70h]
0x180056a5c  call    __std_fs_remove
0x180056a61  shr     rax, 20h
0x180056a65  mov     dword ptr [rsp+160h+var_140], eax
0x180056a69  lea     rcx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180056a70  mov     qword ptr [rsp+160h+var_140+8], rcx
0x180056a75  movaps  xmm0, [rsp+160h+var_140]
0x180056a7a  movdqa  [rsp+160h+var_140], xmm0
0x180056a80  test    eax, eax
0x180056a82  jnz     loc_180056DB5
0x180056a88  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_57696949@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_57696949>>(void)
0x180056a8d  test    al, al
0x180056a8f  jnz     loc_180056B16
0x180056a95  mov     ecx, 30h ; '0'; Size
0x180056a9a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180056a9f  mov     rbx, rax
0x180056aa2  mov     qword ptr [rsp+160h+var_140], rax
0x180056aa7  lea     rdx, [rdi+70h]
0x180056aab  lea     rcx, [rsp+160h+pExceptionObject]
0x180056ab0  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@AEBV01@@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::basic_string<char16_t> const &)
0x180056ab5  xor     r8d, r8d
0x180056ab8  lea     rdx, [rsp+160h+pExceptionObject]
0x180056abd  mov     rcx, rbx
0x180056ac0  call    ??0IndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(std::filesystem::path,bool)
0x180056ac5  nop
0x180056ac6  mov     rbx, [rdi+0C0h]
0x180056acd  mov     [rdi+0C0h], rax
0x180056ad4  test    rbx, rbx
0x180056ad7  jz      short loc_180056B04
0x180056ad9  mov     rcx, [rbx+28h]; hObject
0x180056add  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180056ae1  jz      short loc_180056AEE
0x180056ae3  test    rcx, rcx
0x180056ae6  jz      short loc_180056AEE
0x180056ae8  call    cs:__imp_CloseHandle
0x180056aee  lea     rcx, [rbx+8]
0x180056af2  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x180056af7  mov     edx, 30h ; '0'
0x180056afc  mov     rcx, rbx; Block
0x180056aff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180056b04  mov     rax, [rdi+0C0h]
0x180056b0b  cmp     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x180056b10  jz      loc_180056BF3
0x180056b16  mov     dword ptr [rsp+160h+var_140], 0FDh
0x180056b1e  mov     dword ptr [rsp+160h+var_140+4], 0Dh
0x180056b26  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180056b2d  mov     qword ptr [rsp+160h+var_140+8], rax
0x180056b32  lea     rax, aCdeclWinrtMicr_0; "__cdecl winrt::Microsoft::Asg::Semantic"...
0x180056b39  mov     [rsp+160h+var_130], rax
0x180056b3e  mov     [rsp+160h+var_120], rdi
0x180056b43  mov     rax, [rbp+60h+var_D0]
0x180056b47  mov     [rsp+160h+var_118], rax
0x180056b4c  mov     rax, [rbp+60h+arg_20]
0x180056b53  mov     [rsp+160h+var_110], rax
0x180056b58  lea     r9, [rsp+160h+var_140]
0x180056b5d  lea     rdx, [rsp+160h+var_120]
0x180056b62  mov     rcx, rdi
0x180056b65  call    ??$InvokeDbMethod@V_lambda_1_@?1???0?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@V?$span@$$CBE$0?0@std@@W4IndexCreationDisposition@456789@AEBVVectorSpaceDescriptor@SemanticRegistry@asg@@W4SemanticContentType@SemanticRegistry@asg@@W4IndexQuantizationPreference@6asg@@UTextEmbeddingsGenerator@456789@6V?$unique_ptr@UIndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@U?$default_delete@UIndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@@Z@$$A6AXX_E@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_1_@?1???001234567@QEAA@Vpath@filesystem@std@@V?$span@$$CBE$0?0@std@@W4IndexCreationDisposition@234567@AEBVVectorSpaceDescriptor@SemanticRegistry@asg@@W4SemanticContentType@SemanticRegistry@asg@@W4IndexQuantizationPreference@4asg@@UTextEmbeddingsGenerator@234567@6V?$unique_ptr@UIndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@U?$default_delete@UIndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@@Z@$$Q6AXX_EAEBUsource_location@std@@@Z
0x180056b6a  nop
0x180056b6b  mov     rcx, r12
0x180056b6e  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x180056b73  nop
0x180056b74  cmp     qword ptr [r15], 0
0x180056b78  jz      short loc_180056B83
0x180056b7a  mov     rcx, r15
0x180056b7d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180056b82  nop
0x180056b83  cmp     qword ptr [r14], 0
0x180056b87  jz      short loc_180056B92
0x180056b89  mov     rcx, r14
0x180056b8c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180056b91  nop
0x180056b92  mov     rbx, [rbp+60h+var_D8]
0x180056b96  mov     rbx, [rbx]
0x180056b99  test    rbx, rbx
0x180056b9c  jz      short loc_180056BC9
0x180056b9e  mov     rcx, [rbx+28h]; hObject
0x180056ba2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180056ba6  jz      short loc_180056BB3
0x180056ba8  test    rcx, rcx
0x180056bab  jz      short loc_180056BB3
0x180056bad  call    cs:__imp_CloseHandle
0x180056bb3  lea     rcx, [rbx+8]
0x180056bb7  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x180056bbc  mov     edx, 30h ; '0'
0x180056bc1  mov     rcx, rbx; Block
0x180056bc4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180056bc9  mov     rax, rdi
0x180056bcc  mov     rcx, [rbp+60h+var_40]
0x180056bd0  xor     rcx, rsp; StackCookie
0x180056bd3  call    __security_check_cookie
0x180056bd8  mov     rbx, [rsp+160h+arg_10]
0x180056be0  add     rsp, 130h
0x180056be7  pop     r15
0x180056be9  pop     r14
0x180056beb  pop     r13
0x180056bed  pop     r12
0x180056bef  pop     rdi
0x180056bf0  pop     rsi
0x180056bf1  pop     rbp
0x180056bf2  retn
0x180056bf3  mov     dword ptr [rsp+160h+var_120], 0F9h
0x180056bfb  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180056c02  mov     [rsp+160h+var_118], rax
0x180056c07  mov     [rsp+160h+var_110], r13
0x180056c0c  lea     rdx, aCouldNotGetExc; "could not get exclusive access to the d"...
0x180056c13  lea     rcx, [rbp+60h+var_A8]; this
0x180056c17  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180056c1c  mov     edx, 83EBAD1Fh; int
0x180056c21  lea     rcx, [rbp+60h+var_D8]; this
0x180056c25  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180056c2a  lea     r9, [rsp+160h+var_120]
0x180056c2f  lea     r8, [rbp+60h+var_A8]
0x180056c33  mov     edx, [rax]
0x180056c35  lea     rcx, [rsp+160h+pExceptionObject]
0x180056c3a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180056c3f  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180056c46  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180056c4b  call    _CxxThrowException
0x180056c51  mov     rcx, [rbp+68h]; this
0x180056c55  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180056c5b  lea     r8, [rdi+50h]
0x180056c5f  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
0x180056c65  mov     dword ptr [rsp+160h+var_140], 0B6h
0x180056c6d  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180056c74  mov     qword ptr [rsp+160h+var_140+8], rax
0x180056c79  mov     [rsp+160h+var_130], 0
0x180056c82  lea     rdx, aBasepathMustBe; "basePath must be a file path, not a dir"...
0x180056c89  lea     rcx, [rsp+160h+pExceptionObject]; this
0x180056c8e  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180056c93  lea     r8, [rsp+160h+var_140]; struct winrt::impl::slim_source_location *
0x180056c98  lea     rdx, [rsp+160h+pExceptionObject]; struct winrt::param::hstring *
0x180056c9d  lea     rcx, [rsp+160h+var_120]; this
0x180056ca2  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180056ca7  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180056cae  lea     rcx, [rsp+160h+var_120]; pExceptionObject
0x180056cb3  call    _CxxThrowException
0x180056cb9  mov     dword ptr [rsp+160h+var_140], 0C0h
0x180056cc1  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180056cc8  mov     qword ptr [rsp+160h+var_140+8], rax
0x180056ccd  mov     [rsp+160h+var_130], 0
0x180056cd6  lea     rdx, aIndexcreationd; "IndexCreationDisposition::OpenExisting "...
0x180056cdd  lea     rcx, [rsp+160h+pExceptionObject]; this
0x180056ce2  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180056ce7  lea     r8, [rsp+160h+var_140]; struct winrt::impl::slim_source_location *
0x180056cec  lea     rdx, [rsp+160h+pExceptionObject]; struct winrt::param::hstring *
0x180056cf1  lea     rcx, [rsp+160h+var_120]; this
0x180056cf6  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180056cfb  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180056d02  lea     rcx, [rsp+160h+var_120]; pExceptionObject
0x180056d07  call    _CxxThrowException
0x180056d0d  mov     dword ptr [rsp+160h+var_140], 0CFh
0x180056d15  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180056d1c  mov     qword ptr [rsp+160h+var_140+8], rax
0x180056d21  mov     [rsp+160h+var_130], 0
0x180056d2a  lea     rdx, aGeneratorCanno; "generator cannot be null"
0x180056d31  lea     rcx, [rsp+160h+pExceptionObject]; this
  ... truncated ...
```
