# wil::cloud_store::subscribe_internal<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>(wil::cloud_store_subscription_parameters const &,Windows::Data::Platform::ItemReference<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap> const *,std::function<void (wil::cloud_store_notification<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap> &)>)

- ea: `0x18000f03c`
- end: `0x18000f4bc`
- name: `??$subscribe_internal@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@AEBVcloud_store_subscription_parameters@1@PEBU?$ItemReference@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@Platform@Data@Windows@@V?$function@$$A6AXAEAV?$cloud_store_notification@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@wil@@@Z@3@@Z`
- size: `1152`
- prototype: `__int64 __fastcall(int, int, int, int, DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ad724`

## callees

- `0x18000f03c`
- `0x180011188`
- `0x18001dac0`
- `0x18002d944`
- `0x180055b74`
- `0x180056798`
- `0x180057140`
- `0x1800574a8`
- `0x180057e7c`
- `0x18007ae80`
- `0x180147be8`
- `0x180201e50`
- `0x1802bece0`
- `0x1802beed4`
- `0x180323578`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f363`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f363`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f40a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f420`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f436`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f44c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f47a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f48d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f4a0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f40a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f420`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f436`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f44c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f47a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f48d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f4a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f246`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
HMODULE __fastcall wil::cloud_store::subscribe_internal<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>(
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
  unsigned int v15; // eax
  UINT32 v16; // edx
  HRESULT v17; // eax
  unsigned int v18; // eax
  UINT32 v19; // edx
  HRESULT v20; // eax
  unsigned int v21; // eax
  UINT32 v22; // edx
  HRESULT v23; // eax
  _QWORD *v24; // rdx
  unsigned __int64 *v25; // rax
  unsigned __int64 v26; // r8
  int v27; // eax
  wil::details::in1diag3 *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rax
  HMODULE *v32; // rbx
  int v34; // [rsp+20h] [rbp-E0h]
  HMODULE hLibModule; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  __int64 v37; // [rsp+70h] [rbp-90h] BYREF
  HMODULE *v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h]
  char v41; // [rsp+90h] [rbp-70h]
  _QWORD *v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+A8h] [rbp-58h]
  DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *v44; // [rsp+B0h] [rbp-50h]
  HSTRING_HEADER v45; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v46; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING_HEADER v47; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING v48; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING_HEADER v49; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v50; // [rsp+110h] [rbp+10h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+118h] [rbp+18h] BYREF
  HSTRING string; // [rsp+130h] [rbp+30h] BYREF
  __int64 v53; // [rsp+138h] [rbp+38h] BYREF
  __m128i si128; // [rsp+148h] [rbp+48h]
  PCWSTR v55[4]; // [rsp+160h] [rbp+60h] BYREF
  PCWSTR v56[4]; // [rsp+180h] [rbp+80h] BYREF
  PCWSTR sourceString[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v58[80]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v42 = a1;
  hLibModule = a2;
  v44 = a5;
  wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>(
    v55,
    a4);
  v37 = 0;
  v36 = *a3;
  v38 = *(HMODULE **)wil::details::shared_cloud_store_state::get_cloud_store(*a1);
  hLibModule = *v38;
  v39 = &v37;
  v40 = 0;
  v41 = 1;
  v8 = wil::cloud_store::widen_string(&v53, a3 + 4);
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
    goto LABEL_51;
  v12 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v13 = v12 - 1;
  if ( (unsigned int)v11 < v12 )
    v13 = v11;
  v14 = WindowsCreateStringReference(v9, v13, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
LABEL_54:
    RaiseException(v17, 1u, 0, 0);
    goto LABEL_55;
  }
  v9 = (const WCHAR *)sourceString;
  if ( sourceString[3] > (PCWSTR)7 )
    v9 = sourceString[0];
  v50 = 0;
  v11 = -1;
  do
    ++v11;
  while ( v9[v11] );
  if ( v11 > 0xFFFFFFFF )
    goto LABEL_50;
  v43 = *((_QWORD *)a3 + 1);
  v15 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v16 = v15 - 1;
  if ( (unsigned int)v11 < v15 )
    v16 = v11;
  v17 = WindowsCreateStringReference(v9, v16, &v49, &v50);
  if ( v17 < 0 )
    goto LABEL_54;
  v9 = (const WCHAR *)v56;
  if ( v56[3] > (PCWSTR)7 )
    v9 = v56[0];
  v48 = 0;
  v11 = -1;
  do
    ++v11;
  while ( v9[v11] );
  if ( v11 > 0xFFFFFFFF )
    goto LABEL_49;
  v18 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v19 = v18 - 1;
  if ( (unsigned int)v11 < v18 )
    v19 = v11;
  v20 = WindowsCreateStringReference(v9, v19, &v47, &v48);
  if ( v20 < 0 )
  {
LABEL_55:
    RaiseException(v20, 1u, 0, 0);
LABEL_56:
    RaiseException(v23, 1u, 0, 0);
LABEL_57:
    wil::details::in1diag3::Throw_Hr(
      v28,
      (void *)0x631,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v27,
      v34);
  }
  v11 = (unsigned __int64)v55;
  if ( v55[3] > (PCWSTR)7 )
    v11 = (unsigned __int64)v55[0];
  v46 = 0;
  do
    ++v10;
  while ( *(_WORD *)(v11 + 2 * v10) );
  if ( v10 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_49:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_50:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_51:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_52;
  }
  LODWORD(v9) = (_DWORD)v48;
  v21 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v10);
  v22 = v21 - 1;
  if ( (unsigned int)v10 < v21 )
    v22 = v10;
  v23 = WindowsCreateStringReference((PCWSTR)v11, v22, &v45, &v46);
  v11 = 0;
  if ( v23 < 0 )
    goto LABEL_56;
  v24 = v42;
  v25 = (unsigned __int64 *)v42[3];
  if ( v25 )
  {
    v26 = *v25;
    goto LABEL_35;
  }
LABEL_52:
  v26 = v11;
LABEL_35:
  v34 = (int)v9;
  v27 = (*((__int64 (__fastcall **)(HMODULE *, _QWORD, unsigned __int64, HSTRING))hLibModule + 14))(
          v38,
          *((unsigned int *)v24 + 4),
          v26,
          v46);
  v28 = retaddr;
  if ( v27 < 0 )
    goto LABEL_57;
  v46 = (HSTRING)v11;
  v48 = (HSTRING)v11;
  v50 = (HSTRING)v11;
  string = (HSTRING)v11;
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v53, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v53) = v11;
  if ( v41 != (_BYTE)v11 )
  {
    v29 = *v39;
    *v39 = v40;
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = wil::details::AddRefCurrentModule(&hLibModule);
  v31 = _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(v58, a5, v30);
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_d9b8d61763150b59ec367f08040b5bdf_>(
    &v38,
    v31);
  _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_((_lambda_2c99ad496c9e815fb4bbcee01809bbab_ *)v58);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  v32 = v38;
  wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(
    a2,
    v37,
    v38);
  if ( v32 )
    (*((void (__fastcall **)(HMODULE *))*v32 + 2))(v32);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(sourceString);
  std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v56);
  std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v55);
  DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook::~CloudItemUpdaterTestHook(a5);
  return a2;
}

```

## disassembly

```asm
0x18000f03c  push    rbp
0x18000f03e  push    rbx
0x18000f03f  push    rsi
0x18000f040  push    rdi
0x18000f041  push    r12
0x18000f043  push    r13
0x18000f045  push    r14
0x18000f047  push    r15
0x18000f049  lea     rbp, [rsp-128h]
0x18000f051  sub     rsp, 228h
0x18000f058  mov     rax, cs:__security_cookie
0x18000f05f  xor     rax, rsp
0x18000f062  mov     [rbp+160h+var_50], rax
0x18000f069  mov     r14, r8
0x18000f06c  mov     r15, rdx
0x18000f06f  mov     rbx, rcx
0x18000f072  mov     [rbp+160h+var_1C0], rcx
0x18000f076  mov     [rsp+260h+hLibModule], rdx
0x18000f07b  mov     r12, [rbp+160h+arg_20]
0x18000f082  mov     [rbp+160h+var_1B0], r12
0x18000f086  xor     r13d, r13d
0x18000f089  mov     rdx, r9
0x18000f08c  lea     rcx, [rbp+160h+var_100]
0x18000f090  call    ??$validate_cloud_store_data_reference@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@Platform@Data@Windows@@@Z; wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>(Windows::Data::Platform::ItemReference<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap> const *)
0x18000f095  nop
0x18000f096  mov     [rsp+260h+var_1F0], r13
0x18000f09b  mov     eax, [r14]
0x18000f09e  mov     [rsp+260h+var_1F8], eax
0x18000f0a2  mov     rcx, [rbx]
0x18000f0a5  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x18000f0aa  mov     rax, [rax]
0x18000f0ad  mov     [rsp+260h+var_1E8], rax
0x18000f0b2  mov     rax, [rax]
0x18000f0b5  mov     [rsp+260h+hLibModule], rax
0x18000f0ba  lea     rcx, [rsp+260h+var_1F0]
0x18000f0bf  mov     [rbp+160h+var_1E0], rcx
0x18000f0c3  mov     [rbp+160h+var_1D8], r13
0x18000f0c7  mov     [rbp+160h+var_1D0], 1
0x18000f0cb  lea     rdx, [r14+10h]
0x18000f0cf  lea     rcx, [rbp+160h+var_128]
0x18000f0d3  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18000f0d8  mov     rsi, rax
0x18000f0db  cmp     qword ptr [rax+18h], 7
0x18000f0e0  jbe     short loc_18000F0E5
0x18000f0e2  mov     rsi, [rax]
0x18000f0e5  mov     [rbp+160h+string], r13
0x18000f0e9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f0ed  mov     rdi, rbx
0x18000f0f0  inc     rdi
0x18000f0f3  cmp     [rsi+rdi*2], r13w
0x18000f0f8  jnz     short loc_18000F0F0
0x18000f0fa  mov     eax, 0FFFFFFFFh
0x18000f0ff  cmp     rdi, rax
0x18000f102  ja      loc_18000F43D
0x18000f108  mov     ecx, edi; unsigned int
0x18000f10a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000f10f  lea     edx, [rax-1]
0x18000f112  cmp     edi, eax
0x18000f114  cmovb   edx, edi; length
0x18000f117  lea     r9, [rbp+160h+string]; string
0x18000f11b  lea     r8, [rbp+160h+hstringHeader]; hstringHeader
0x18000f11f  mov     rcx, rsi; sourceString
0x18000f122  call    cs:__imp_WindowsCreateStringReference
0x18000f128  test    eax, eax
0x18000f12a  js      loc_18000F45B
0x18000f130  lea     rsi, [rbp+160h+sourceString]
0x18000f137  cmp     [rbp+160h+var_A8], 7
0x18000f13f  cmova   rsi, [rbp+160h+sourceString]
0x18000f147  mov     [rbp+160h+var_150], r13
0x18000f14b  mov     rdi, rbx
0x18000f14e  inc     rdi
0x18000f151  cmp     [rsi+rdi*2], r13w
0x18000f156  jnz     short loc_18000F14E
0x18000f158  mov     eax, 0FFFFFFFFh
0x18000f15d  cmp     rdi, rax
0x18000f160  ja      loc_18000F427
0x18000f166  mov     r13, [rbp+160h+string]
0x18000f16a  mov     rax, [r14+8]
0x18000f16e  mov     [rbp+160h+var_1B8], rax
0x18000f172  mov     ecx, edi; unsigned int
0x18000f174  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000f179  lea     edx, [rax-1]
0x18000f17c  cmp     edi, eax
0x18000f17e  cmovb   edx, edi; length
0x18000f181  lea     r9, [rbp+160h+var_150]; string
0x18000f185  lea     r8, [rbp+160h+var_168]; hstringHeader
0x18000f189  mov     rcx, rsi; sourceString
0x18000f18c  call    cs:__imp_WindowsCreateStringReference
0x18000f192  xor     ecx, ecx
0x18000f194  test    eax, eax
0x18000f196  js      loc_18000F46E
0x18000f19c  lea     rsi, [rbp+160h+var_E0]
0x18000f1a3  cmp     [rbp+160h+var_C8], 7
0x18000f1ab  cmova   rsi, [rbp+160h+var_E0]
0x18000f1b3  mov     [rbp+160h+var_170], rcx
0x18000f1b7  mov     rdi, rbx
0x18000f1ba  inc     rdi
0x18000f1bd  cmp     [rsi+rdi*2], cx
0x18000f1c1  jnz     short loc_18000F1BA
0x18000f1c3  mov     eax, 0FFFFFFFFh
0x18000f1c8  cmp     rdi, rax
0x18000f1cb  ja      loc_18000F411
0x18000f1d1  mov     r14, [rbp+160h+var_150]
0x18000f1d5  mov     ecx, edi; unsigned int
0x18000f1d7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000f1dc  lea     edx, [rax-1]
0x18000f1df  cmp     edi, eax
0x18000f1e1  cmovb   edx, edi; length
0x18000f1e4  lea     r9, [rbp+160h+var_170]; string
0x18000f1e8  lea     r8, [rbp+160h+var_188]; hstringHeader
0x18000f1ec  mov     rcx, rsi; sourceString
0x18000f1ef  call    cs:__imp_WindowsCreateStringReference
0x18000f1f5  xor     ecx, ecx
0x18000f1f7  test    eax, eax
0x18000f1f9  js      loc_18000F481
0x18000f1ff  lea     rdi, [rbp+160h+var_100]
0x18000f203  cmp     [rbp+160h+var_E8], 7
0x18000f208  cmova   rdi, [rbp+160h+var_100]
0x18000f20d  mov     [rbp+160h+var_190], rcx
0x18000f211  inc     rbx
0x18000f214  cmp     [rdi+rbx*2], cx
0x18000f218  jnz     short loc_18000F211
0x18000f21a  mov     eax, 0FFFFFFFFh
0x18000f21f  cmp     rbx, rax
0x18000f222  ja      loc_18000F3FB
0x18000f228  mov     rsi, [rbp+160h+var_170]
0x18000f22c  mov     ecx, ebx; unsigned int
0x18000f22e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000f233  lea     edx, [rax-1]
0x18000f236  cmp     ebx, eax
0x18000f238  cmovb   edx, ebx; length
0x18000f23b  lea     r9, [rbp+160h+var_190]; string
0x18000f23f  lea     r8, [rbp+160h+var_1A8]; hstringHeader
0x18000f243  mov     rcx, rdi; sourceString
0x18000f246  call    cs:__imp_WindowsCreateStringReference
0x18000f24c  xor     edi, edi
0x18000f24e  test    eax, eax
0x18000f250  js      loc_18000F494
0x18000f256  mov     rdx, [rbp+160h+var_1C0]
0x18000f25a  mov     rax, [rdx+18h]
0x18000f25e  test    rax, rax
0x18000f261  jz      loc_18000F453
0x18000f267  mov     r8, [rax]
0x18000f26a  lea     rax, [rbp+160h+var_1D8]
0x18000f26e  mov     [rsp+260h+var_218], rax
0x18000f273  mov     [rsp+260h+var_220], r13
0x18000f278  mov     rax, [rbp+160h+var_1B8]
0x18000f27c  mov     [rsp+260h+var_228], rax
0x18000f281  mov     eax, [rsp+260h+var_1F8]
0x18000f285  mov     [rsp+260h+var_230], eax
0x18000f289  mov     [rsp+260h+var_238], r14
0x18000f28e  mov     [rsp+260h+var_240], rsi
0x18000f293  mov     r9, [rbp+160h+var_190]
0x18000f297  mov     edx, [rdx+10h]
0x18000f29a  mov     rcx, [rsp+260h+var_1E8]
0x18000f29f  mov     rax, [rsp+260h+hLibModule]
0x18000f2a4  mov     rax, [rax+70h]
0x18000f2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2ad  mov     rcx, [rbp+168h]
0x18000f2b4  test    eax, eax
0x18000f2b6  js      loc_18000F4A7
0x18000f2bc  mov     [rbp+160h+var_190], rdi
0x18000f2c0  mov     [rbp+160h+var_170], rdi
0x18000f2c4  mov     [rbp+160h+var_150], rdi
0x18000f2c8  mov     [rbp+160h+string], rdi
0x18000f2cc  mov     rdx, [rbp+160h+var_110]
0x18000f2d0  cmp     rdx, 7
0x18000f2d4  jbe     short loc_18000F2E7
0x18000f2d6  lea     rdx, ds:2[rdx*2]
0x18000f2de  mov     rcx, [rbp+160h+var_128]
0x18000f2e2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f2e7  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18000f2ef  movdqu  xmmword ptr [rbp+48h], xmm0
0x18000f2f4  mov     word ptr [rbp+160h+var_128], di
0x18000f2f8  cmp     [rbp+160h+var_1D0], dil
0x18000f2fc  jz      short loc_18000F321
0x18000f2fe  mov     rcx, [rbp+160h+var_1D8]
0x18000f302  mov     rax, [rbp+160h+var_1E0]
0x18000f306  mov     rdx, [rax]
0x18000f309  mov     [rax], rcx
0x18000f30c  test    rdx, rdx
0x18000f30f  jz      short loc_18000F321
0x18000f311  mov     rax, [rdx]
0x18000f314  mov     rcx, rdx
0x18000f317  mov     rax, [rax+10h]
0x18000f31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f320  nop
0x18000f321  lea     rcx, [rsp+260h+hLibModule]
0x18000f326  call    ?AddRefCurrentModule@details@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::details::AddRefCurrentModule(void)
0x18000f32b  nop
0x18000f32c  mov     r8, rax
0x18000f32f  mov     rdx, r12
0x18000f332  lea     rcx, [rbp+160h+var_A0]
0x18000f339  call    ??0_lambda_65204b8627083f4129f6e0117acac874_@@QEAA@AEBV?$function@$$A6AXAEAV?$cloud_store_notification@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@wil@@@Z@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(std::function<void (wil::cloud_store_notification<Windows::Data::CuratedTileCollection::TileCollectionContainer> &)> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x18000f33e  mov     rdx, rax
0x18000f341  lea     rcx, [rsp+260h+var_1E8]
0x18000f346  call    ??$Callback@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@V_lambda_d9b8d61763150b59ec367f08040b5bdf_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@@01@$$QEAV_lambda_d9b8d61763150b59ec367f08040b5bdf_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_d9b8d61763150b59ec367f08040b5bdf_>(_lambda_d9b8d61763150b59ec367f08040b5bdf_ &&)
0x18000f34b  nop
0x18000f34c  lea     rcx, [rbp+160h+var_A0]; this
0x18000f353  call    ??1_lambda_2c99ad496c9e815fb4bbcee01809bbab_@@QEAA@XZ; _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_(void)
0x18000f358  nop
0x18000f359  mov     rcx, [rsp+260h+hLibModule]; hLibModule
0x18000f35e  test    rcx, rcx
0x18000f361  jz      short loc_18000F369
0x18000f363  call    cs:__imp_FreeLibrary
0x18000f369  mov     rbx, [rsp+260h+var_1E8]
0x18000f36e  mov     r8, rbx
0x18000f371  mov     rdx, [rsp+260h+var_1F0]
0x18000f376  mov     rcx, r15
0x18000f379  call    ??$make_cloud_store_watcher@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@YA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@PEAUICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAU?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@8@@Z; wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher *,Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *> *)
0x18000f37e  nop
0x18000f37f  test    rbx, rbx
0x18000f382  jz      short loc_18000F394
0x18000f384  mov     rax, [rbx]
0x18000f387  mov     rcx, rbx
0x18000f38a  mov     rax, [rax+10h]
0x18000f38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f393  nop
0x18000f394  mov     rcx, [rsp+260h+var_1F0]
0x18000f399  test    rcx, rcx
0x18000f39c  jz      short loc_18000F3AB
0x18000f39e  mov     rax, [rcx]
0x18000f3a1  mov     rax, [rax+10h]
0x18000f3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3aa  nop
0x18000f3ab  lea     rcx, [rbp+160h+sourceString]; void *
0x18000f3b2  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18000f3b7  lea     rcx, [rbp+160h+var_E0]; void *
0x18000f3be  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18000f3c3  lea     rcx, [rbp+160h+var_100]; void *
0x18000f3c7  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18000f3cc  nop
0x18000f3cd  mov     rcx, r12; this
0x18000f3d0  call    ??1CloudItemUpdaterTestHook@Internal@CloudUtil@DataStoreCache@@QEAA@XZ; DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook::~CloudItemUpdaterTestHook(void)
0x18000f3d5  mov     rax, r15
0x18000f3d8  mov     rcx, [rbp+160h+var_50]
0x18000f3df  xor     rcx, rsp; StackCookie
0x18000f3e2  call    __security_check_cookie
0x18000f3e7  add     rsp, 228h
0x18000f3ee  pop     r15
0x18000f3f0  pop     r14
0x18000f3f2  pop     r13
0x18000f3f4  pop     r12
0x18000f3f6  pop     rdi
0x18000f3f7  pop     rsi
0x18000f3f8  pop     rbx
0x18000f3f9  pop     rbp
0x18000f3fa  retn
0x18000f3fb  xor     r9d, r9d; lpArguments
0x18000f3fe  xor     r8d, r8d; nNumberOfArguments
0x18000f401  lea     edx, [r9+1]; dwExceptionFlags
0x18000f405  mov     ecx, 80070216h; dwExceptionCode
0x18000f40a  call    cs:__imp_RaiseException
0x18000f410  nop
0x18000f411  xor     r9d, r9d; lpArguments
0x18000f414  xor     r8d, r8d; nNumberOfArguments
0x18000f417  lea     edx, [r9+1]; dwExceptionFlags
0x18000f41b  mov     ecx, 80070216h; dwExceptionCode
0x18000f420  call    cs:__imp_RaiseException
0x18000f426  nop
0x18000f427  xor     r9d, r9d; lpArguments
0x18000f42a  xor     r8d, r8d; nNumberOfArguments
0x18000f42d  lea     edx, [r9+1]; dwExceptionFlags
0x18000f431  mov     ecx, 80070216h; dwExceptionCode
0x18000f436  call    cs:__imp_RaiseException
0x18000f43c  nop
0x18000f43d  xor     r9d, r9d; lpArguments
0x18000f440  xor     r8d, r8d; nNumberOfArguments
0x18000f443  lea     edx, [r9+1]; dwExceptionFlags
0x18000f447  mov     ecx, 80070216h; dwExceptionCode
0x18000f44c  call    cs:__imp_RaiseException
0x18000f452  nop
0x18000f453  mov     r8, rdi
0x18000f456  jmp     loc_18000F26A
0x18000f45b  xor     r9d, r9d; lpArguments
0x18000f45e  xor     r8d, r8d; nNumberOfArguments
0x18000f461  lea     edx, [r9+1]; dwExceptionFlags
0x18000f465  mov     ecx, eax; dwExceptionCode
0x18000f467  call    cs:__imp_RaiseException
0x18000f46d  nop
0x18000f46e  xor     r9d, r9d; lpArguments
0x18000f471  xor     r8d, r8d; nNumberOfArguments
0x18000f474  lea     edx, [r9+1]; dwExceptionFlags
0x18000f478  mov     ecx, eax; dwExceptionCode
0x18000f47a  call    cs:__imp_RaiseException
0x18000f480  nop
0x18000f481  xor     r9d, r9d; lpArguments
0x18000f484  xor     r8d, r8d; nNumberOfArguments
0x18000f487  lea     edx, [r9+1]; dwExceptionFlags
0x18000f48b  mov     ecx, eax; dwExceptionCode
0x18000f48d  call    cs:__imp_RaiseException
0x18000f493  nop
0x18000f494  xor     r9d, r9d; lpArguments
0x18000f497  xor     r8d, r8d; nNumberOfArguments
0x18000f49a  lea     edx, [r9+1]; dwExceptionFlags
0x18000f49e  mov     ecx, eax; dwExceptionCode
0x18000f4a0  call    cs:__imp_RaiseException
0x18000f4a6  nop
0x18000f4a7  mov     r9d, eax; char *
0x18000f4aa  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
  ... truncated ...
```
