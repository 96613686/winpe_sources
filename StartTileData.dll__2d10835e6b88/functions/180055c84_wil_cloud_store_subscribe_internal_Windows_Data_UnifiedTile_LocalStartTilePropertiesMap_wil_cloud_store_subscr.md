# wil::cloud_store::subscribe_internal<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(wil::cloud_store_subscription_parameters const &,Windows::Data::Platform::ItemReference<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap> const *,std::function<void (wil::cloud_store_notification<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap> &)>)

- ea: `0x180055c84`
- end: `0x18005610d`
- name: `??$subscribe_internal@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@AEBVcloud_store_subscription_parameters@1@PEBU?$ItemReference@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@Platform@Data@Windows@@V?$function@$$A6AXAEAV?$cloud_store_notification@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@wil@@@Z@3@@Z`
- size: `1161`
- prototype: `__int64 __fastcall(int, int, int, int, DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180055634`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18002d944`
- `0x180055b74`
- `0x180055c84`
- `0x180056798`
- `0x180056f90`
- `0x1800574a8`
- `0x180057e7c`
- `0x18007ae80`
- `0x180147be8`
- `0x180201e50`
- `0x1802bece0`
- `0x1802beed4`
- `0x1803235e8`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180055f9e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180055f9e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056063`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056079`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005608f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560cb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056063`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056079`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005608f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560cb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055d6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055e37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055e8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055d6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055e37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055e8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
HMODULE __fastcall wil::cloud_store::subscribe_internal<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(
        _QWORD *a1,
        HMODULE a2,
        int *a3,
        __int64 a4,
        DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *a5)
{
  __int64 v8; // rax
  const WCHAR *v9; // rsi
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rdi
  unsigned int v12; // eax
  UINT32 v13; // edx
  HRESULT v14; // eax
  const WCHAR *v15; // rsi
  unsigned __int64 v16; // rdi
  unsigned int v17; // eax
  UINT32 v18; // edx
  HRESULT v19; // eax
  const WCHAR *v20; // rsi
  unsigned __int64 v21; // rdi
  unsigned int v22; // eax
  UINT32 v23; // edx
  HRESULT v24; // eax
  const WCHAR *v25; // rdi
  int v26; // esi
  unsigned int v27; // eax
  UINT32 v28; // edx
  HRESULT v29; // eax
  __int64 *v30; // rax
  __int64 v31; // r8
  int v32; // eax
  wil::details::in1diag3 *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rax
  HMODULE *v37; // rbx
  int v39; // [rsp+20h] [rbp-E0h]
  HMODULE hLibModule; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  HMODULE *v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v44; // [rsp+80h] [rbp-80h]
  __int64 v45; // [rsp+88h] [rbp-78h]
  char v46; // [rsp+90h] [rbp-70h]
  _QWORD *v47; // [rsp+A0h] [rbp-60h]
  __int64 v48; // [rsp+A8h] [rbp-58h]
  DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *v49; // [rsp+B0h] [rbp-50h]
  HSTRING_HEADER v50; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v51; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING_HEADER v52; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING v53; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING_HEADER v54; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v55; // [rsp+110h] [rbp+10h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+118h] [rbp+18h] BYREF
  HSTRING string; // [rsp+130h] [rbp+30h] BYREF
  __int64 v58; // [rsp+138h] [rbp+38h] BYREF
  __m128i si128; // [rsp+148h] [rbp+48h]
  PCWSTR v60[4]; // [rsp+160h] [rbp+60h] BYREF
  PCWSTR v61[4]; // [rsp+180h] [rbp+80h] BYREF
  PCWSTR sourceString[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v63[80]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v47 = a1;
  hLibModule = a2;
  v49 = a5;
  wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(
    v60,
    a4);
  v42 = 0;
  v41 = *a3;
  v43 = *(HMODULE **)wil::details::shared_cloud_store_state::get_cloud_store(*a1);
  hLibModule = *v43;
  v44 = &v42;
  v45 = 0;
  v46 = 1;
  v8 = wil::cloud_store::widen_string(&v58, a3 + 4);
  v9 = (const WCHAR *)v8;
  if ( *(_QWORD *)(v8 + 24) > 7u )
    v9 = *(const WCHAR **)v8;
  string = 0;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( v9[v11] );
  if ( v11 > 0xFFFFFFFF )
  {
LABEL_52:
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v12 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v13 = v12 - 1;
  if ( (unsigned int)v11 < v12 )
    v13 = v11;
  v14 = WindowsCreateStringReference(v9, v13, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
LABEL_54:
    RaiseException(v19, 1u, 0, 0);
    goto LABEL_55;
  }
  v15 = (const WCHAR *)sourceString;
  if ( sourceString[3] > (PCWSTR)7 )
    v15 = sourceString[0];
  v55 = 0;
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  if ( v16 > 0xFFFFFFFF )
    goto LABEL_51;
  v48 = *((_QWORD *)a3 + 1);
  v17 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  v18 = v17 - 1;
  if ( (unsigned int)v16 < v17 )
    v18 = v16;
  v19 = WindowsCreateStringReference(v15, v18, &v54, &v55);
  if ( v19 < 0 )
    goto LABEL_54;
  v20 = (const WCHAR *)v61;
  if ( v61[3] > (PCWSTR)7 )
    v20 = v61[0];
  v53 = 0;
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  if ( v21 > 0xFFFFFFFF )
    goto LABEL_50;
  v22 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v21);
  v23 = v22 - 1;
  if ( (unsigned int)v21 < v22 )
    v23 = v21;
  v24 = WindowsCreateStringReference(v20, v23, &v52, &v53);
  if ( v24 < 0 )
  {
LABEL_55:
    RaiseException(v24, 1u, 0, 0);
LABEL_56:
    RaiseException(v29, 1u, 0, 0);
    goto LABEL_57;
  }
  v25 = (const WCHAR *)v60;
  if ( v60[3] > (PCWSTR)7 )
    v25 = v60[0];
  v51 = 0;
  do
    ++v10;
  while ( v25[v10] );
  if ( v10 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_50:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_51:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_52;
  }
  v26 = (int)v53;
  v27 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v10);
  v28 = v27 - 1;
  if ( (unsigned int)v10 < v27 )
    v28 = v10;
  v29 = WindowsCreateStringReference(v25, v28, &v50, &v51);
  if ( v29 < 0 )
    goto LABEL_56;
  v30 = (__int64 *)v47[3];
  if ( v30 )
    v31 = *v30;
  else
    v31 = 0;
  v39 = v26;
  v32 = (*((__int64 (__fastcall **)(HMODULE *, _QWORD, __int64, HSTRING))hLibModule + 14))(
          v43,
          *((unsigned int *)v47 + 4),
          v31,
          v51);
  v33 = retaddr;
  if ( v32 < 0 )
LABEL_57:
    wil::details::in1diag3::Throw_Hr(
      v33,
      (void *)0x631,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v32,
      v39);
  v51 = 0;
  v53 = 0;
  v55 = 0;
  string = 0;
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v58, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v58) = 0;
  if ( v46 )
  {
    v34 = *v44;
    *v44 = v45;
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = wil::details::AddRefCurrentModule(&hLibModule);
  v36 = _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(v63, a5, v35);
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_fb21c0cadb1077cf8bd42dbe3ce5b984_>(
    &v43,
    v36);
  _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_((_lambda_2c99ad496c9e815fb4bbcee01809bbab_ *)v63);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  v37 = v43;
  wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(
    a2,
    v42,
    v43);
  if ( v37 )
    (*((void (__fastcall **)(HMODULE *))*v37 + 2))(v37);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(sourceString);
  std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v61);
  std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v60);
  DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook::~CloudItemUpdaterTestHook(a5);
  return a2;
}

```

## disassembly

```asm
0x180055c84  push    rbp
0x180055c86  push    rbx
0x180055c87  push    rsi
0x180055c88  push    rdi
0x180055c89  push    r12
0x180055c8b  push    r13
0x180055c8d  push    r14
0x180055c8f  push    r15
0x180055c91  lea     rbp, [rsp-128h]
0x180055c99  sub     rsp, 228h
0x180055ca0  mov     rax, cs:__security_cookie
0x180055ca7  xor     rax, rsp
0x180055caa  mov     [rbp+160h+var_50], rax
0x180055cb1  mov     r14, r8
0x180055cb4  mov     r15, rdx
0x180055cb7  mov     rbx, rcx
0x180055cba  mov     [rbp+160h+var_1C0], rcx
0x180055cbe  mov     [rsp+260h+hLibModule], rdx
0x180055cc3  mov     r12, [rbp+160h+arg_20]
0x180055cca  mov     [rbp+160h+var_1B0], r12
0x180055cce  xor     r13d, r13d
0x180055cd1  mov     rdx, r9
0x180055cd4  lea     rcx, [rbp+160h+var_100]
0x180055cd8  call    ??$validate_cloud_store_data_reference@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@Platform@Data@Windows@@@Z; wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(Windows::Data::Platform::ItemReference<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap> const *)
0x180055cdd  nop
0x180055cde  mov     [rsp+260h+var_1F0], r13
0x180055ce3  mov     eax, [r14]
0x180055ce6  mov     [rsp+260h+var_1F8], eax
0x180055cea  mov     rcx, [rbx]
0x180055ced  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180055cf2  mov     rax, [rax]
0x180055cf5  mov     [rsp+260h+var_1E8], rax
0x180055cfa  mov     rax, [rax]
0x180055cfd  mov     [rsp+260h+hLibModule], rax
0x180055d02  lea     rcx, [rsp+260h+var_1F0]
0x180055d07  mov     [rbp+160h+var_1E0], rcx
0x180055d0b  mov     [rbp+160h+var_1D8], r13
0x180055d0f  mov     [rbp+160h+var_1D0], 1
0x180055d13  lea     rdx, [r14+10h]
0x180055d17  lea     rcx, [rbp+160h+var_128]
0x180055d1b  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180055d20  mov     rsi, rax
0x180055d23  cmp     qword ptr [rax+18h], 7
0x180055d28  jbe     short loc_180055D2D
0x180055d2a  mov     rsi, [rax]
0x180055d2d  mov     [rbp+160h+string], r13
0x180055d31  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180055d35  mov     rdi, rbx
0x180055d38  inc     rdi
0x180055d3b  cmp     [rsi+rdi*2], r13w
0x180055d40  jnz     short loc_180055D38
0x180055d42  mov     eax, 0FFFFFFFFh
0x180055d47  cmp     rdi, rax
0x180055d4a  ja      loc_180056096
0x180055d50  mov     ecx, edi; unsigned int
0x180055d52  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180055d57  lea     edx, [rax-1]
0x180055d5a  cmp     edi, eax
0x180055d5c  cmovb   edx, edi; length
0x180055d5f  lea     r9, [rbp+160h+string]; string
0x180055d63  lea     r8, [rbp+160h+hstringHeader]; hstringHeader
0x180055d67  mov     rcx, rsi; sourceString
0x180055d6a  call    cs:__imp_WindowsCreateStringReference
0x180055d70  test    eax, eax
0x180055d72  js      loc_1800560AC
0x180055d78  lea     rsi, [rbp+160h+sourceString]
0x180055d7f  cmp     [rbp+160h+var_A8], 7
0x180055d87  cmova   rsi, [rbp+160h+sourceString]
0x180055d8f  mov     [rbp+160h+var_150], r13
0x180055d93  mov     rdi, rbx
0x180055d96  inc     rdi
0x180055d99  cmp     [rsi+rdi*2], r13w
0x180055d9e  jnz     short loc_180055D96
0x180055da0  mov     eax, 0FFFFFFFFh
0x180055da5  cmp     rdi, rax
0x180055da8  ja      loc_180056080
0x180055dae  mov     r13, [rbp+160h+string]
0x180055db2  mov     rax, [r14+8]
0x180055db6  mov     [rbp+160h+var_1B8], rax
0x180055dba  mov     ecx, edi; unsigned int
0x180055dbc  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180055dc1  lea     edx, [rax-1]
0x180055dc4  cmp     edi, eax
0x180055dc6  cmovb   edx, edi; length
0x180055dc9  lea     r9, [rbp+160h+var_150]; string
0x180055dcd  lea     r8, [rbp+160h+var_168]; hstringHeader
0x180055dd1  mov     rcx, rsi; sourceString
0x180055dd4  call    cs:__imp_WindowsCreateStringReference
0x180055dda  xor     ecx, ecx
0x180055ddc  test    eax, eax
0x180055dde  js      loc_1800560BF
0x180055de4  lea     rsi, [rbp+160h+var_E0]
0x180055deb  cmp     [rbp+160h+var_C8], 7
0x180055df3  cmova   rsi, [rbp+160h+var_E0]
0x180055dfb  mov     [rbp+160h+var_170], rcx
0x180055dff  mov     rdi, rbx
0x180055e02  inc     rdi
0x180055e05  cmp     [rsi+rdi*2], cx
0x180055e09  jnz     short loc_180055E02
0x180055e0b  mov     eax, 0FFFFFFFFh
0x180055e10  cmp     rdi, rax
0x180055e13  ja      loc_18005606A
0x180055e19  mov     r14, [rbp+160h+var_150]
0x180055e1d  mov     ecx, edi; unsigned int
0x180055e1f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180055e24  lea     edx, [rax-1]
0x180055e27  cmp     edi, eax
0x180055e29  cmovb   edx, edi; length
0x180055e2c  lea     r9, [rbp+160h+var_170]; string
0x180055e30  lea     r8, [rbp+160h+var_188]; hstringHeader
0x180055e34  mov     rcx, rsi; sourceString
0x180055e37  call    cs:__imp_WindowsCreateStringReference
0x180055e3d  xor     ecx, ecx
0x180055e3f  test    eax, eax
0x180055e41  js      loc_1800560D2
0x180055e47  lea     rdi, [rbp+160h+var_100]
0x180055e4b  cmp     [rbp+160h+var_E8], 7
0x180055e50  cmova   rdi, [rbp+160h+var_100]
0x180055e55  mov     [rbp+160h+var_190], rcx
0x180055e59  inc     rbx
0x180055e5c  cmp     [rdi+rbx*2], cx
0x180055e60  jnz     short loc_180055E59
0x180055e62  mov     eax, 0FFFFFFFFh
0x180055e67  cmp     rbx, rax
0x180055e6a  ja      loc_180056054
0x180055e70  mov     rsi, [rbp+160h+var_170]
0x180055e74  mov     ecx, ebx; unsigned int
0x180055e76  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180055e7b  lea     edx, [rax-1]
0x180055e7e  cmp     ebx, eax
0x180055e80  cmovb   edx, ebx; length
0x180055e83  lea     r9, [rbp+160h+var_190]; string
0x180055e87  lea     r8, [rbp+160h+var_1A8]; hstringHeader
0x180055e8b  mov     rcx, rdi; sourceString
0x180055e8e  call    cs:__imp_WindowsCreateStringReference
0x180055e94  xor     edi, edi
0x180055e96  test    eax, eax
0x180055e98  js      loc_1800560E5
0x180055e9e  mov     rdx, [rbp+160h+var_1C0]
0x180055ea2  mov     rax, [rdx+18h]
0x180055ea6  test    rax, rax
0x180055ea9  jz      loc_180056036
0x180055eaf  mov     r8, [rax]
0x180055eb2  lea     rax, [rbp+160h+var_1D8]
0x180055eb6  mov     [rsp+260h+var_218], rax
0x180055ebb  mov     [rsp+260h+var_220], r13
0x180055ec0  mov     rax, [rbp+160h+var_1B8]
0x180055ec4  mov     [rsp+260h+var_228], rax
0x180055ec9  mov     eax, [rsp+260h+var_1F8]
0x180055ecd  mov     [rsp+260h+var_230], eax
0x180055ed1  mov     [rsp+260h+var_238], r14
0x180055ed6  mov     [rsp+260h+var_240], rsi
0x180055edb  mov     r9, [rbp+160h+var_190]
0x180055edf  mov     edx, [rdx+10h]
0x180055ee2  mov     rcx, [rsp+260h+var_1E8]
0x180055ee7  mov     rax, [rsp+260h+hLibModule]
0x180055eec  mov     rax, [rax+70h]
0x180055ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ef5  mov     rcx, [rbp+168h]
0x180055efc  test    eax, eax
0x180055efe  js      loc_1800560F8
0x180055f04  mov     [rbp+160h+var_190], rdi
0x180055f08  mov     [rbp+160h+var_170], rdi
0x180055f0c  mov     [rbp+160h+var_150], rdi
0x180055f10  mov     [rbp+160h+string], rdi
0x180055f14  mov     rdx, [rbp+160h+var_110]
0x180055f18  cmp     rdx, 7
0x180055f1c  ja      loc_18005603E
0x180055f22  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180055f2a  movdqu  xmmword ptr [rbp+48h], xmm0
0x180055f2f  mov     word ptr [rbp+160h+var_128], di
0x180055f33  cmp     [rbp+160h+var_1D0], dil
0x180055f37  jz      short loc_180055F5C
0x180055f39  mov     rcx, [rbp+160h+var_1D8]
0x180055f3d  mov     rax, [rbp+160h+var_1E0]
0x180055f41  mov     rdx, [rax]
0x180055f44  mov     [rax], rcx
0x180055f47  test    rdx, rdx
0x180055f4a  jz      short loc_180055F5C
0x180055f4c  mov     rax, [rdx]
0x180055f4f  mov     rcx, rdx
0x180055f52  mov     rax, [rax+10h]
0x180055f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f5b  nop
0x180055f5c  lea     rcx, [rsp+260h+hLibModule]
0x180055f61  call    ?AddRefCurrentModule@details@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::details::AddRefCurrentModule(void)
0x180055f66  nop
0x180055f67  mov     r8, rax
0x180055f6a  mov     rdx, r12
0x180055f6d  lea     rcx, [rbp+160h+var_A0]
0x180055f74  call    ??0_lambda_65204b8627083f4129f6e0117acac874_@@QEAA@AEBV?$function@$$A6AXAEAV?$cloud_store_notification@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@wil@@@Z@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(std::function<void (wil::cloud_store_notification<Windows::Data::CuratedTileCollection::TileCollectionContainer> &)> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x180055f79  mov     rdx, rax
0x180055f7c  lea     rcx, [rsp+260h+var_1E8]
0x180055f81  call    ??$Callback@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@V_lambda_fb21c0cadb1077cf8bd42dbe3ce5b984_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@@01@$$QEAV_lambda_fb21c0cadb1077cf8bd42dbe3ce5b984_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_fb21c0cadb1077cf8bd42dbe3ce5b984_>(_lambda_fb21c0cadb1077cf8bd42dbe3ce5b984_ &&)
0x180055f86  nop
0x180055f87  lea     rcx, [rbp+160h+var_A0]; this
0x180055f8e  call    ??1_lambda_2c99ad496c9e815fb4bbcee01809bbab_@@QEAA@XZ; _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_(void)
0x180055f93  nop
0x180055f94  mov     rcx, [rsp+260h+hLibModule]; hLibModule
0x180055f99  test    rcx, rcx
0x180055f9c  jz      short loc_180055FA4
0x180055f9e  call    cs:__imp_FreeLibrary
0x180055fa4  mov     rbx, [rsp+260h+var_1E8]
0x180055fa9  mov     r8, rbx
0x180055fac  mov     rdx, [rsp+260h+var_1F0]
0x180055fb1  mov     rcx, r15
0x180055fb4  call    ??$make_cloud_store_watcher@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@YA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@PEAUICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAU?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@8@@Z; wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher *,Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *> *)
0x180055fb9  nop
0x180055fba  test    rbx, rbx
0x180055fbd  jz      short loc_180055FCF
0x180055fbf  mov     rax, [rbx]
0x180055fc2  mov     rcx, rbx
0x180055fc5  mov     rax, [rax+10h]
0x180055fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fce  nop
0x180055fcf  mov     rcx, [rsp+260h+var_1F0]
0x180055fd4  test    rcx, rcx
0x180055fd7  jz      short loc_180055FE6
0x180055fd9  mov     rax, [rcx]
0x180055fdc  mov     rax, [rax+10h]
0x180055fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fe5  nop
0x180055fe6  lea     rcx, [rbp+160h+sourceString]; void *
0x180055fed  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x180055ff2  lea     rcx, [rbp+160h+var_E0]; void *
0x180055ff9  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x180055ffe  lea     rcx, [rbp+160h+var_100]; void *
0x180056002  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x180056007  nop
0x180056008  mov     rcx, r12; this
0x18005600b  call    ??1CloudItemUpdaterTestHook@Internal@CloudUtil@DataStoreCache@@QEAA@XZ; DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook::~CloudItemUpdaterTestHook(void)
0x180056010  mov     rax, r15
0x180056013  mov     rcx, [rbp+160h+var_50]
0x18005601a  xor     rcx, rsp; StackCookie
0x18005601d  call    __security_check_cookie
0x180056022  add     rsp, 228h
0x180056029  pop     r15
0x18005602b  pop     r14
0x18005602d  pop     r13
0x18005602f  pop     r12
0x180056031  pop     rdi
0x180056032  pop     rsi
0x180056033  pop     rbx
0x180056034  pop     rbp
0x180056035  retn
0x180056036  mov     r8, rdi
0x180056039  jmp     loc_180055EB2
0x18005603e  lea     rdx, ds:2[rdx*2]
0x180056046  mov     rcx, [rbp+160h+var_128]
0x18005604a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005604f  jmp     loc_180055F22
0x180056054  xor     r9d, r9d; lpArguments
0x180056057  xor     r8d, r8d; nNumberOfArguments
0x18005605a  lea     edx, [r9+1]; dwExceptionFlags
0x18005605e  mov     ecx, 80070216h; dwExceptionCode
0x180056063  call    cs:__imp_RaiseException
0x180056069  nop
0x18005606a  xor     r9d, r9d; lpArguments
0x18005606d  xor     r8d, r8d; nNumberOfArguments
0x180056070  lea     edx, [r9+1]; dwExceptionFlags
0x180056074  mov     ecx, 80070216h; dwExceptionCode
0x180056079  call    cs:__imp_RaiseException
0x18005607f  nop
0x180056080  xor     r9d, r9d; lpArguments
0x180056083  xor     r8d, r8d; nNumberOfArguments
0x180056086  lea     edx, [r9+1]; dwExceptionFlags
0x18005608a  mov     ecx, 80070216h; dwExceptionCode
0x18005608f  call    cs:__imp_RaiseException
0x180056095  nop
0x180056096  xor     r9d, r9d; lpArguments
0x180056099  xor     r8d, r8d; nNumberOfArguments
0x18005609c  lea     edx, [r9+1]; dwExceptionFlags
0x1800560a0  mov     ecx, 80070216h; dwExceptionCode
0x1800560a5  call    cs:__imp_RaiseException
0x1800560ab  int     3; Trap to Debugger
0x1800560ac  xor     r9d, r9d; lpArguments
0x1800560af  xor     r8d, r8d; nNumberOfArguments
0x1800560b2  lea     edx, [r9+1]; dwExceptionFlags
0x1800560b6  mov     ecx, eax; dwExceptionCode
0x1800560b8  call    cs:__imp_RaiseException
0x1800560be  nop
0x1800560bf  xor     r9d, r9d; lpArguments
0x1800560c2  xor     r8d, r8d; nNumberOfArguments
0x1800560c5  lea     edx, [r9+1]; dwExceptionFlags
0x1800560c9  mov     ecx, eax; dwExceptionCode
0x1800560cb  call    cs:__imp_RaiseException
0x1800560d1  nop
0x1800560d2  xor     r9d, r9d; lpArguments
0x1800560d5  xor     r8d, r8d; nNumberOfArguments
0x1800560d8  lea     edx, [r9+1]; dwExceptionFlags
0x1800560dc  mov     ecx, eax; dwExceptionCode
0x1800560de  call    cs:__imp_RaiseException
0x1800560e4  nop
0x1800560e5  xor     r9d, r9d; lpArguments
0x1800560e8  xor     r8d, r8d; nNumberOfArguments
0x1800560eb  lea     edx, [r9+1]; dwExceptionFlags
0x1800560ef  mov     ecx, eax; dwExceptionCode
0x1800560f1  call    cs:__imp_RaiseException
0x1800560f7  nop
0x1800560f8  mov     r9d, eax; char *
  ... truncated ...
```
