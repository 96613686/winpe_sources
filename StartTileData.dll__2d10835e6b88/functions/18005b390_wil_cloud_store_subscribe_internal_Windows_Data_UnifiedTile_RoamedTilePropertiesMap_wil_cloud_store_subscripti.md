# wil::cloud_store::subscribe_internal<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>(wil::cloud_store_subscription_parameters const &,Windows::Data::Platform::ItemReference<Windows::Data::UnifiedTile::RoamedTilePropertiesMap> const *,std::function<void (wil::cloud_store_notification<Windows::Data::UnifiedTile::RoamedTilePropertiesMap> &)>)

- ea: `0x18005b390`
- end: `0x18005b819`
- name: `??$subscribe_internal@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@AEBVcloud_store_subscription_parameters@1@PEBU?$ItemReference@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@Platform@Data@Windows@@V?$function@$$A6AXAEAV?$cloud_store_notification@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@wil@@@Z@3@@Z`
- size: `1161`
- prototype: `__int64 __fastcall(int, int, int, int, DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005a180`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18002d944`
- `0x180055b74`
- `0x180056798`
- `0x1800574a8`
- `0x180057e7c`
- `0x18005b390`
- `0x180075430`
- `0x18007ae80`
- `0x180147be8`
- `0x180201e50`
- `0x1802bece0`
- `0x1802beed4`
- `0x180323508`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005b6aa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005b6aa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b76f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b785`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b79b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b7b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b7c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b7d7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b7ea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b7fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b76f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b785`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b79b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b7b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b7c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b7d7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b7ea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b7fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b476`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b4e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b59a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b476`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b4e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b59a`

## pseudocode

```c
HMODULE __fastcall wil::cloud_store::subscribe_internal<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>(
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
  wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>(v60, a4);
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
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_566a36f853e38e5647e21734231acbab_>(
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
0x18005b390  push    rbp
0x18005b392  push    rbx
0x18005b393  push    rsi
0x18005b394  push    rdi
0x18005b395  push    r12
0x18005b397  push    r13
0x18005b399  push    r14
0x18005b39b  push    r15
0x18005b39d  lea     rbp, [rsp-128h]
0x18005b3a5  sub     rsp, 228h
0x18005b3ac  mov     rax, cs:__security_cookie
0x18005b3b3  xor     rax, rsp
0x18005b3b6  mov     [rbp+160h+var_50], rax
0x18005b3bd  mov     r14, r8
0x18005b3c0  mov     r15, rdx
0x18005b3c3  mov     rbx, rcx
0x18005b3c6  mov     [rbp+160h+var_1C0], rcx
0x18005b3ca  mov     [rsp+260h+hLibModule], rdx
0x18005b3cf  mov     r12, [rbp+160h+arg_20]
0x18005b3d6  mov     [rbp+160h+var_1B0], r12
0x18005b3da  xor     r13d, r13d
0x18005b3dd  mov     rdx, r9
0x18005b3e0  lea     rcx, [rbp+160h+var_100]
0x18005b3e4  call    ??$validate_cloud_store_data_reference@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@Platform@Data@Windows@@@Z; wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>(Windows::Data::Platform::ItemReference<Windows::Data::UnifiedTile::RoamedTilePropertiesMap> const *)
0x18005b3e9  nop
0x18005b3ea  mov     [rsp+260h+var_1F0], r13
0x18005b3ef  mov     eax, [r14]
0x18005b3f2  mov     [rsp+260h+var_1F8], eax
0x18005b3f6  mov     rcx, [rbx]
0x18005b3f9  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x18005b3fe  mov     rax, [rax]
0x18005b401  mov     [rsp+260h+var_1E8], rax
0x18005b406  mov     rax, [rax]
0x18005b409  mov     [rsp+260h+hLibModule], rax
0x18005b40e  lea     rcx, [rsp+260h+var_1F0]
0x18005b413  mov     [rbp+160h+var_1E0], rcx
0x18005b417  mov     [rbp+160h+var_1D8], r13
0x18005b41b  mov     [rbp+160h+var_1D0], 1
0x18005b41f  lea     rdx, [r14+10h]
0x18005b423  lea     rcx, [rbp+160h+var_128]
0x18005b427  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18005b42c  mov     rsi, rax
0x18005b42f  cmp     qword ptr [rax+18h], 7
0x18005b434  jbe     short loc_18005B439
0x18005b436  mov     rsi, [rax]
0x18005b439  mov     [rbp+160h+string], r13
0x18005b43d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005b441  mov     rdi, rbx
0x18005b444  inc     rdi
0x18005b447  cmp     [rsi+rdi*2], r13w
0x18005b44c  jnz     short loc_18005B444
0x18005b44e  mov     eax, 0FFFFFFFFh
0x18005b453  cmp     rdi, rax
0x18005b456  ja      loc_18005B7A2
0x18005b45c  mov     ecx, edi; unsigned int
0x18005b45e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005b463  lea     edx, [rax-1]
0x18005b466  cmp     edi, eax
0x18005b468  cmovb   edx, edi; length
0x18005b46b  lea     r9, [rbp+160h+string]; string
0x18005b46f  lea     r8, [rbp+160h+hstringHeader]; hstringHeader
0x18005b473  mov     rcx, rsi; sourceString
0x18005b476  call    cs:__imp_WindowsCreateStringReference
0x18005b47c  test    eax, eax
0x18005b47e  js      loc_18005B7B8
0x18005b484  lea     rsi, [rbp+160h+sourceString]
0x18005b48b  cmp     [rbp+160h+var_A8], 7
0x18005b493  cmova   rsi, [rbp+160h+sourceString]
0x18005b49b  mov     [rbp+160h+var_150], r13
0x18005b49f  mov     rdi, rbx
0x18005b4a2  inc     rdi
0x18005b4a5  cmp     [rsi+rdi*2], r13w
0x18005b4aa  jnz     short loc_18005B4A2
0x18005b4ac  mov     eax, 0FFFFFFFFh
0x18005b4b1  cmp     rdi, rax
0x18005b4b4  ja      loc_18005B78C
0x18005b4ba  mov     r13, [rbp+160h+string]
0x18005b4be  mov     rax, [r14+8]
0x18005b4c2  mov     [rbp+160h+var_1B8], rax
0x18005b4c6  mov     ecx, edi; unsigned int
0x18005b4c8  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005b4cd  lea     edx, [rax-1]
0x18005b4d0  cmp     edi, eax
0x18005b4d2  cmovb   edx, edi; length
0x18005b4d5  lea     r9, [rbp+160h+var_150]; string
0x18005b4d9  lea     r8, [rbp+160h+var_168]; hstringHeader
0x18005b4dd  mov     rcx, rsi; sourceString
0x18005b4e0  call    cs:__imp_WindowsCreateStringReference
0x18005b4e6  xor     ecx, ecx
0x18005b4e8  test    eax, eax
0x18005b4ea  js      loc_18005B7CB
0x18005b4f0  lea     rsi, [rbp+160h+var_E0]
0x18005b4f7  cmp     [rbp+160h+var_C8], 7
0x18005b4ff  cmova   rsi, [rbp+160h+var_E0]
0x18005b507  mov     [rbp+160h+var_170], rcx
0x18005b50b  mov     rdi, rbx
0x18005b50e  inc     rdi
0x18005b511  cmp     [rsi+rdi*2], cx
0x18005b515  jnz     short loc_18005B50E
0x18005b517  mov     eax, 0FFFFFFFFh
0x18005b51c  cmp     rdi, rax
0x18005b51f  ja      loc_18005B776
0x18005b525  mov     r14, [rbp+160h+var_150]
0x18005b529  mov     ecx, edi; unsigned int
0x18005b52b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005b530  lea     edx, [rax-1]
0x18005b533  cmp     edi, eax
0x18005b535  cmovb   edx, edi; length
0x18005b538  lea     r9, [rbp+160h+var_170]; string
0x18005b53c  lea     r8, [rbp+160h+var_188]; hstringHeader
0x18005b540  mov     rcx, rsi; sourceString
0x18005b543  call    cs:__imp_WindowsCreateStringReference
0x18005b549  xor     ecx, ecx
0x18005b54b  test    eax, eax
0x18005b54d  js      loc_18005B7DE
0x18005b553  lea     rdi, [rbp+160h+var_100]
0x18005b557  cmp     [rbp+160h+var_E8], 7
0x18005b55c  cmova   rdi, [rbp+160h+var_100]
0x18005b561  mov     [rbp+160h+var_190], rcx
0x18005b565  inc     rbx
0x18005b568  cmp     [rdi+rbx*2], cx
0x18005b56c  jnz     short loc_18005B565
0x18005b56e  mov     eax, 0FFFFFFFFh
0x18005b573  cmp     rbx, rax
0x18005b576  ja      loc_18005B760
0x18005b57c  mov     rsi, [rbp+160h+var_170]
0x18005b580  mov     ecx, ebx; unsigned int
0x18005b582  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005b587  lea     edx, [rax-1]
0x18005b58a  cmp     ebx, eax
0x18005b58c  cmovb   edx, ebx; length
0x18005b58f  lea     r9, [rbp+160h+var_190]; string
0x18005b593  lea     r8, [rbp+160h+var_1A8]; hstringHeader
0x18005b597  mov     rcx, rdi; sourceString
0x18005b59a  call    cs:__imp_WindowsCreateStringReference
0x18005b5a0  xor     edi, edi
0x18005b5a2  test    eax, eax
0x18005b5a4  js      loc_18005B7F1
0x18005b5aa  mov     rdx, [rbp+160h+var_1C0]
0x18005b5ae  mov     rax, [rdx+18h]
0x18005b5b2  test    rax, rax
0x18005b5b5  jz      loc_18005B742
0x18005b5bb  mov     r8, [rax]
0x18005b5be  lea     rax, [rbp+160h+var_1D8]
0x18005b5c2  mov     [rsp+260h+var_218], rax
0x18005b5c7  mov     [rsp+260h+var_220], r13
0x18005b5cc  mov     rax, [rbp+160h+var_1B8]
0x18005b5d0  mov     [rsp+260h+var_228], rax
0x18005b5d5  mov     eax, [rsp+260h+var_1F8]
0x18005b5d9  mov     [rsp+260h+var_230], eax
0x18005b5dd  mov     [rsp+260h+var_238], r14
0x18005b5e2  mov     [rsp+260h+var_240], rsi
0x18005b5e7  mov     r9, [rbp+160h+var_190]
0x18005b5eb  mov     edx, [rdx+10h]
0x18005b5ee  mov     rcx, [rsp+260h+var_1E8]
0x18005b5f3  mov     rax, [rsp+260h+hLibModule]
0x18005b5f8  mov     rax, [rax+70h]
0x18005b5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b601  mov     rcx, [rbp+168h]
0x18005b608  test    eax, eax
0x18005b60a  js      loc_18005B804
0x18005b610  mov     [rbp+160h+var_190], rdi
0x18005b614  mov     [rbp+160h+var_170], rdi
0x18005b618  mov     [rbp+160h+var_150], rdi
0x18005b61c  mov     [rbp+160h+string], rdi
0x18005b620  mov     rdx, [rbp+160h+var_110]
0x18005b624  cmp     rdx, 7
0x18005b628  ja      loc_18005B74A
0x18005b62e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18005b636  movdqu  xmmword ptr [rbp+48h], xmm0
0x18005b63b  mov     word ptr [rbp+160h+var_128], di
0x18005b63f  cmp     [rbp+160h+var_1D0], dil
0x18005b643  jz      short loc_18005B668
0x18005b645  mov     rcx, [rbp+160h+var_1D8]
0x18005b649  mov     rax, [rbp+160h+var_1E0]
0x18005b64d  mov     rdx, [rax]
0x18005b650  mov     [rax], rcx
0x18005b653  test    rdx, rdx
0x18005b656  jz      short loc_18005B668
0x18005b658  mov     rax, [rdx]
0x18005b65b  mov     rcx, rdx
0x18005b65e  mov     rax, [rax+10h]
0x18005b662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b667  nop
0x18005b668  lea     rcx, [rsp+260h+hLibModule]
0x18005b66d  call    ?AddRefCurrentModule@details@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::details::AddRefCurrentModule(void)
0x18005b672  nop
0x18005b673  mov     r8, rax
0x18005b676  mov     rdx, r12
0x18005b679  lea     rcx, [rbp+160h+var_A0]
0x18005b680  call    ??0_lambda_65204b8627083f4129f6e0117acac874_@@QEAA@AEBV?$function@$$A6AXAEAV?$cloud_store_notification@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@wil@@@Z@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(std::function<void (wil::cloud_store_notification<Windows::Data::CuratedTileCollection::TileCollectionContainer> &)> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x18005b685  mov     rdx, rax
0x18005b688  lea     rcx, [rsp+260h+var_1E8]
0x18005b68d  call    ??$Callback@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@V_lambda_566a36f853e38e5647e21734231acbab_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@@01@$$QEAV_lambda_566a36f853e38e5647e21734231acbab_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_566a36f853e38e5647e21734231acbab_>(_lambda_566a36f853e38e5647e21734231acbab_ &&)
0x18005b692  nop
0x18005b693  lea     rcx, [rbp+160h+var_A0]; this
0x18005b69a  call    ??1_lambda_2c99ad496c9e815fb4bbcee01809bbab_@@QEAA@XZ; _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_(void)
0x18005b69f  nop
0x18005b6a0  mov     rcx, [rsp+260h+hLibModule]; hLibModule
0x18005b6a5  test    rcx, rcx
0x18005b6a8  jz      short loc_18005B6B0
0x18005b6aa  call    cs:__imp_FreeLibrary
0x18005b6b0  mov     rbx, [rsp+260h+var_1E8]
0x18005b6b5  mov     r8, rbx
0x18005b6b8  mov     rdx, [rsp+260h+var_1F0]
0x18005b6bd  mov     rcx, r15
0x18005b6c0  call    ??$make_cloud_store_watcher@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@YA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@PEAUICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAU?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@8@@Z; wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher *,Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *> *)
0x18005b6c5  nop
0x18005b6c6  test    rbx, rbx
0x18005b6c9  jz      short loc_18005B6DB
0x18005b6cb  mov     rax, [rbx]
0x18005b6ce  mov     rcx, rbx
0x18005b6d1  mov     rax, [rax+10h]
0x18005b6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6da  nop
0x18005b6db  mov     rcx, [rsp+260h+var_1F0]
0x18005b6e0  test    rcx, rcx
0x18005b6e3  jz      short loc_18005B6F2
0x18005b6e5  mov     rax, [rcx]
0x18005b6e8  mov     rax, [rax+10h]
0x18005b6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6f1  nop
0x18005b6f2  lea     rcx, [rbp+160h+sourceString]; void *
0x18005b6f9  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18005b6fe  lea     rcx, [rbp+160h+var_E0]; void *
0x18005b705  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18005b70a  lea     rcx, [rbp+160h+var_100]; void *
0x18005b70e  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18005b713  nop
0x18005b714  mov     rcx, r12; this
0x18005b717  call    ??1CloudItemUpdaterTestHook@Internal@CloudUtil@DataStoreCache@@QEAA@XZ; DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook::~CloudItemUpdaterTestHook(void)
0x18005b71c  mov     rax, r15
0x18005b71f  mov     rcx, [rbp+160h+var_50]
0x18005b726  xor     rcx, rsp; StackCookie
0x18005b729  call    __security_check_cookie
0x18005b72e  add     rsp, 228h
0x18005b735  pop     r15
0x18005b737  pop     r14
0x18005b739  pop     r13
0x18005b73b  pop     r12
0x18005b73d  pop     rdi
0x18005b73e  pop     rsi
0x18005b73f  pop     rbx
0x18005b740  pop     rbp
0x18005b741  retn
0x18005b742  mov     r8, rdi
0x18005b745  jmp     loc_18005B5BE
0x18005b74a  lea     rdx, ds:2[rdx*2]
0x18005b752  mov     rcx, [rbp+160h+var_128]
0x18005b756  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005b75b  jmp     loc_18005B62E
0x18005b760  xor     r9d, r9d; lpArguments
0x18005b763  xor     r8d, r8d; nNumberOfArguments
0x18005b766  lea     edx, [r9+1]; dwExceptionFlags
0x18005b76a  mov     ecx, 80070216h; dwExceptionCode
0x18005b76f  call    cs:__imp_RaiseException
0x18005b775  nop
0x18005b776  xor     r9d, r9d; lpArguments
0x18005b779  xor     r8d, r8d; nNumberOfArguments
0x18005b77c  lea     edx, [r9+1]; dwExceptionFlags
0x18005b780  mov     ecx, 80070216h; dwExceptionCode
0x18005b785  call    cs:__imp_RaiseException
0x18005b78b  nop
0x18005b78c  xor     r9d, r9d; lpArguments
0x18005b78f  xor     r8d, r8d; nNumberOfArguments
0x18005b792  lea     edx, [r9+1]; dwExceptionFlags
0x18005b796  mov     ecx, 80070216h; dwExceptionCode
0x18005b79b  call    cs:__imp_RaiseException
0x18005b7a1  nop
0x18005b7a2  xor     r9d, r9d; lpArguments
0x18005b7a5  xor     r8d, r8d; nNumberOfArguments
0x18005b7a8  lea     edx, [r9+1]; dwExceptionFlags
0x18005b7ac  mov     ecx, 80070216h; dwExceptionCode
0x18005b7b1  call    cs:__imp_RaiseException
0x18005b7b7  int     3; Trap to Debugger
0x18005b7b8  xor     r9d, r9d; lpArguments
0x18005b7bb  xor     r8d, r8d; nNumberOfArguments
0x18005b7be  lea     edx, [r9+1]; dwExceptionFlags
0x18005b7c2  mov     ecx, eax; dwExceptionCode
0x18005b7c4  call    cs:__imp_RaiseException
0x18005b7ca  nop
0x18005b7cb  xor     r9d, r9d; lpArguments
0x18005b7ce  xor     r8d, r8d; nNumberOfArguments
0x18005b7d1  lea     edx, [r9+1]; dwExceptionFlags
0x18005b7d5  mov     ecx, eax; dwExceptionCode
0x18005b7d7  call    cs:__imp_RaiseException
0x18005b7dd  nop
0x18005b7de  xor     r9d, r9d; lpArguments
0x18005b7e1  xor     r8d, r8d; nNumberOfArguments
0x18005b7e4  lea     edx, [r9+1]; dwExceptionFlags
0x18005b7e8  mov     ecx, eax; dwExceptionCode
0x18005b7ea  call    cs:__imp_RaiseException
0x18005b7f0  nop
0x18005b7f1  xor     r9d, r9d; lpArguments
0x18005b7f4  xor     r8d, r8d; nNumberOfArguments
0x18005b7f7  lea     edx, [r9+1]; dwExceptionFlags
0x18005b7fb  mov     ecx, eax; dwExceptionCode
0x18005b7fd  call    cs:__imp_RaiseException
0x18005b803  nop
0x18005b804  mov     r9d, eax; char *
  ... truncated ...
```
