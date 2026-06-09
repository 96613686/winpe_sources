# wil::cloud_store::subscribe_internal<Windows::Data::CuratedTileCollection::TileCollectionContainer>(wil::cloud_store_subscription_parameters const &,Windows::Data::Platform::ItemReference<Windows::Data::CuratedTileCollection::TileCollectionContainer> const *,std::function<void (wil::cloud_store_notification<Windows::Data::CuratedTileCollection::TileCollectionContainer> &)>)

- ea: `0x18009357c`
- end: `0x1800939de`
- name: `??$subscribe_internal@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@cloud_store@wil@@AEAA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@AEBVcloud_store_subscription_parameters@1@PEBU?$ItemReference@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@Platform@Data@Windows@@V?$function@$$A6AXAEAV?$cloud_store_notification@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@wil@@@Z@3@@Z`
- size: `1122`
- prototype: `__int64 __fastcall(int, int, int, int, DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801ad2ec`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18002d944`
- `0x180055b74`
- `0x180056798`
- `0x1800574a8`
- `0x180057e7c`
- `0x18007ae80`
- `0x18009357c`
- `0x180093e60`
- `0x180147be8`
- `0x180201e50`
- `0x1802bece0`
- `0x1802beed4`
- `0x18033eed4`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800938ee`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800938ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093678`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800936f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093763`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800937c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093995`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800939ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800939c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800939d7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093678`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800936f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093763`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800937c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093995`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800939ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800939c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800939d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800936db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009374c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800937b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800936db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009374c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800937b1`

## pseudocode

```c
HMODULE __fastcall wil::cloud_store::subscribe_internal<Windows::Data::CuratedTileCollection::TileCollectionContainer>(
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
  HSTRING v20; // rcx
  const WCHAR *v21; // rsi
  unsigned __int64 v22; // rdi
  unsigned int v23; // eax
  UINT32 v24; // edx
  HRESULT v25; // eax
  HSTRING v26; // rcx
  const WCHAR *v27; // rdi
  int v28; // esi
  unsigned int v29; // eax
  UINT32 v30; // edx
  HRESULT v31; // eax
  __int64 *v32; // rax
  __int64 v33; // r8
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rax
  HMODULE *v38; // rbx
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
  wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::CuratedTileCollection::TileCollectionContainer>(
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
LABEL_57:
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x1800939DDLL);
  }
  v12 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v13 = v12 - 1;
  if ( (unsigned int)v11 < v12 )
    v13 = v11;
  v14 = WindowsCreateStringReference(v9, v13, &hstringHeader, &string);
  if ( v14 < 0 )
    RaiseException(v14, 1u, 0, 0);
  v15 = (const WCHAR *)sourceString;
  if ( sourceString[3] > (PCWSTR)7 )
    v15 = sourceString[0];
  v55 = 0;
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  if ( v16 > 0xFFFFFFFF )
  {
LABEL_56:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_57;
  }
  v48 = *((_QWORD *)a3 + 1);
  v17 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  v18 = v17 - 1;
  if ( (unsigned int)v16 < v17 )
    v18 = v16;
  v19 = WindowsCreateStringReference(v15, v18, &v54, &v55);
  v20 = 0;
  if ( v19 < 0 )
    RaiseException(v19, 1u, 0, 0);
  v21 = (const WCHAR *)v61;
  if ( v61[3] > (PCWSTR)7 )
    v21 = v61[0];
  v53 = v20;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] != (_WORD)v20 );
  if ( v22 > 0xFFFFFFFF )
  {
LABEL_55:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_56;
  }
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v22);
  v24 = v23 - 1;
  if ( (unsigned int)v22 < v23 )
    v24 = v22;
  v25 = WindowsCreateStringReference(v21, v24, &v52, &v53);
  v26 = 0;
  if ( v25 < 0 )
    RaiseException(v25, 1u, 0, 0);
  v27 = (const WCHAR *)v60;
  if ( v60[3] > (PCWSTR)7 )
    v27 = v60[0];
  v51 = v26;
  do
    ++v10;
  while ( v27[v10] != (_WORD)v26 );
  if ( v10 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_55;
  }
  v28 = (int)v53;
  v29 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v10);
  v30 = v29 - 1;
  if ( (unsigned int)v10 < v29 )
    v30 = v10;
  v31 = WindowsCreateStringReference(v27, v30, &v50, &v51);
  if ( v31 < 0 )
    RaiseException(v31, 1u, 0, 0);
  v32 = (__int64 *)v47[3];
  if ( v32 )
    v33 = *v32;
  else
    v33 = 0;
  v34 = (*((__int64 (__fastcall **)(HMODULE *, _QWORD, __int64, HSTRING))hLibModule + 14))(
          v43,
          *((unsigned int *)v47 + 4),
          v33,
          v51);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x631,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v34,
      v28);
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
    v35 = *v44;
    *v44 = v45;
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = wil::details::AddRefCurrentModule(&hLibModule);
  v37 = _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(v63, a5, v36);
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_65204b8627083f4129f6e0117acac874_>(
    &v43,
    v37);
  _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_((_lambda_2c99ad496c9e815fb4bbcee01809bbab_ *)v63);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  v38 = v43;
  wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(
    a2,
    v42,
    v43);
  if ( v38 )
    (*((void (__fastcall **)(HMODULE *))*v38 + 2))(v38);
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
0x18009357c  push    rbp
0x18009357e  push    rbx
0x18009357f  push    rsi
0x180093580  push    rdi
0x180093581  push    r12
0x180093583  push    r13
0x180093585  push    r14
0x180093587  push    r15
0x180093589  lea     rbp, [rsp-128h]
0x180093591  sub     rsp, 228h
0x180093598  mov     rax, cs:__security_cookie
0x18009359f  xor     rax, rsp
0x1800935a2  mov     [rbp+160h+var_50], rax
0x1800935a9  mov     r14, r8
0x1800935ac  mov     r15, rdx
0x1800935af  mov     rbx, rcx
0x1800935b2  mov     [rbp+160h+var_1C0], rcx
0x1800935b6  mov     [rsp+260h+hLibModule], rdx
0x1800935bb  mov     r12, [rbp+160h+arg_20]
0x1800935c2  mov     [rbp+160h+var_1B0], r12
0x1800935c6  xor     r13d, r13d
0x1800935c9  mov     rdx, r9
0x1800935cc  lea     rcx, [rbp+160h+var_100]
0x1800935d0  call    ??$validate_cloud_store_data_reference@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@Platform@Data@Windows@@@Z; wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::CuratedTileCollection::TileCollectionContainer>(Windows::Data::Platform::ItemReference<Windows::Data::CuratedTileCollection::TileCollectionContainer> const *)
0x1800935d5  nop
0x1800935d6  mov     [rsp+260h+var_1F0], r13
0x1800935db  mov     eax, [r14]
0x1800935de  mov     [rsp+260h+var_1F8], eax
0x1800935e2  mov     rcx, [rbx]
0x1800935e5  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x1800935ea  mov     rax, [rax]
0x1800935ed  mov     [rsp+260h+var_1E8], rax
0x1800935f2  mov     rax, [rax]
0x1800935f5  mov     [rsp+260h+hLibModule], rax
0x1800935fa  lea     rcx, [rsp+260h+var_1F0]
0x1800935ff  mov     [rbp+160h+var_1E0], rcx
0x180093603  mov     [rbp+160h+var_1D8], r13
0x180093607  mov     [rbp+160h+var_1D0], 1
0x18009360b  lea     rdx, [r14+10h]
0x18009360f  lea     rcx, [rbp+160h+var_128]
0x180093613  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180093618  mov     rsi, rax
0x18009361b  cmp     qword ptr [rax+18h], 7
0x180093620  jbe     short loc_180093625
0x180093622  mov     rsi, [rax]
0x180093625  mov     [rbp+160h+string], r13
0x180093629  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009362d  mov     rdi, rbx
0x180093630  inc     rdi
0x180093633  cmp     [rsi+rdi*2], r13w
0x180093638  jnz     short loc_180093630
0x18009363a  mov     eax, 0FFFFFFFFh
0x18009363f  cmp     rdi, rax
0x180093642  ja      loc_1800939C8
0x180093648  mov     ecx, edi; unsigned int
0x18009364a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18009364f  lea     edx, [rax-1]
0x180093652  cmp     edi, eax
0x180093654  cmovb   edx, edi; length
0x180093657  lea     r9, [rbp+160h+string]; string
0x18009365b  lea     r8, [rbp+160h+hstringHeader]; hstringHeader
0x18009365f  mov     rcx, rsi; sourceString
0x180093662  call    cs:__imp_WindowsCreateStringReference
0x180093668  test    eax, eax
0x18009366a  jns     short loc_18009367F
0x18009366c  xor     r9d, r9d; lpArguments
0x18009366f  xor     r8d, r8d; nNumberOfArguments
0x180093672  lea     edx, [r9+1]; dwExceptionFlags
0x180093676  mov     ecx, eax; dwExceptionCode
0x180093678  call    cs:__imp_RaiseException
0x18009367e  nop
0x18009367f  lea     rsi, [rbp+160h+sourceString]
0x180093686  cmp     [rbp+160h+var_A8], 7
0x18009368e  cmova   rsi, [rbp+160h+sourceString]
0x180093696  mov     [rbp+160h+var_150], r13
0x18009369a  mov     rdi, rbx
0x18009369d  inc     rdi
0x1800936a0  cmp     [rsi+rdi*2], r13w
0x1800936a5  jnz     short loc_18009369D
0x1800936a7  mov     eax, 0FFFFFFFFh
0x1800936ac  cmp     rdi, rax
0x1800936af  ja      loc_1800939B2
0x1800936b5  mov     r13, [rbp+160h+string]
0x1800936b9  mov     rax, [r14+8]
0x1800936bd  mov     [rbp+160h+var_1B8], rax
0x1800936c1  mov     ecx, edi; unsigned int
0x1800936c3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800936c8  lea     edx, [rax-1]
0x1800936cb  cmp     edi, eax
0x1800936cd  cmovb   edx, edi; length
0x1800936d0  lea     r9, [rbp+160h+var_150]; string
0x1800936d4  lea     r8, [rbp+160h+var_168]; hstringHeader
0x1800936d8  mov     rcx, rsi; sourceString
0x1800936db  call    cs:__imp_WindowsCreateStringReference
0x1800936e1  xor     ecx, ecx
0x1800936e3  test    eax, eax
0x1800936e5  jns     short loc_1800936F9
0x1800936e7  xor     r9d, r9d; lpArguments
0x1800936ea  xor     r8d, r8d; nNumberOfArguments
0x1800936ed  lea     edx, [rcx+1]; dwExceptionFlags
0x1800936f0  mov     ecx, eax; dwExceptionCode
0x1800936f2  call    cs:__imp_RaiseException
0x1800936f8  nop
0x1800936f9  lea     rsi, [rbp+160h+var_E0]
0x180093700  cmp     [rbp+160h+var_C8], 7
0x180093708  cmova   rsi, [rbp+160h+var_E0]
0x180093710  mov     [rbp+160h+var_170], rcx
0x180093714  mov     rdi, rbx
0x180093717  inc     rdi
0x18009371a  cmp     [rsi+rdi*2], cx
0x18009371e  jnz     short loc_180093717
0x180093720  mov     eax, 0FFFFFFFFh
0x180093725  cmp     rdi, rax
0x180093728  ja      loc_18009399C
0x18009372e  mov     r14, [rbp+160h+var_150]
0x180093732  mov     ecx, edi; unsigned int
0x180093734  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180093739  lea     edx, [rax-1]
0x18009373c  cmp     edi, eax
0x18009373e  cmovb   edx, edi; length
0x180093741  lea     r9, [rbp+160h+var_170]; string
0x180093745  lea     r8, [rbp+160h+var_188]; hstringHeader
0x180093749  mov     rcx, rsi; sourceString
0x18009374c  call    cs:__imp_WindowsCreateStringReference
0x180093752  xor     ecx, ecx
0x180093754  test    eax, eax
0x180093756  jns     short loc_18009376A
0x180093758  xor     r9d, r9d; lpArguments
0x18009375b  xor     r8d, r8d; nNumberOfArguments
0x18009375e  lea     edx, [rcx+1]; dwExceptionFlags
0x180093761  mov     ecx, eax; dwExceptionCode
0x180093763  call    cs:__imp_RaiseException
0x180093769  nop
0x18009376a  lea     rdi, [rbp+160h+var_100]
0x18009376e  cmp     [rbp+160h+var_E8], 7
0x180093773  cmova   rdi, [rbp+160h+var_100]
0x180093778  mov     [rbp+160h+var_190], rcx
0x18009377c  inc     rbx
0x18009377f  cmp     [rdi+rbx*2], cx
0x180093783  jnz     short loc_18009377C
0x180093785  mov     eax, 0FFFFFFFFh
0x18009378a  cmp     rbx, rax
0x18009378d  ja      loc_180093986
0x180093793  mov     rsi, [rbp+160h+var_170]
0x180093797  mov     ecx, ebx; unsigned int
0x180093799  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18009379e  lea     edx, [rax-1]
0x1800937a1  cmp     ebx, eax
0x1800937a3  cmovb   edx, ebx; length
0x1800937a6  lea     r9, [rbp+160h+var_190]; string
0x1800937aa  lea     r8, [rbp+160h+var_1A8]; hstringHeader
0x1800937ae  mov     rcx, rdi; sourceString
0x1800937b1  call    cs:__imp_WindowsCreateStringReference
0x1800937b7  xor     edi, edi
0x1800937b9  test    eax, eax
0x1800937bb  jns     short loc_1800937CF
0x1800937bd  xor     r9d, r9d; lpArguments
0x1800937c0  xor     r8d, r8d; nNumberOfArguments
0x1800937c3  lea     edx, [rdi+1]; dwExceptionFlags
0x1800937c6  mov     ecx, eax; dwExceptionCode
0x1800937c8  call    cs:__imp_RaiseException
0x1800937ce  nop
0x1800937cf  mov     rdx, [rbp+160h+var_1C0]
0x1800937d3  mov     rax, [rdx+18h]
0x1800937d7  test    rax, rax
0x1800937da  jz      short loc_1800937E1
0x1800937dc  mov     r8, [rax]
0x1800937df  jmp     short loc_1800937E4
0x1800937e1  mov     r8, rdi
0x1800937e4  lea     rax, [rbp+160h+var_1D8]
0x1800937e8  mov     [rsp+260h+var_218], rax
0x1800937ed  mov     [rsp+260h+var_220], r13
0x1800937f2  mov     rax, [rbp+160h+var_1B8]
0x1800937f6  mov     [rsp+260h+var_228], rax
0x1800937fb  mov     eax, [rsp+260h+var_1F8]
0x1800937ff  mov     [rsp+260h+var_230], eax
0x180093803  mov     [rsp+260h+var_238], r14
0x180093808  mov     qword ptr [rsp+260h+var_240], rsi; int
0x18009380d  mov     r9, [rbp+160h+var_190]
0x180093811  mov     edx, [rdx+10h]
0x180093814  mov     rcx, [rsp+260h+var_1E8]
0x180093819  mov     rax, [rsp+260h+hLibModule]
0x18009381e  mov     rax, [rax+70h]
0x180093822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093827  mov     rcx, [rbp+168h]; this
0x18009382e  test    eax, eax
0x180093830  jns     short loc_180093847
0x180093832  mov     r9d, eax; char *
0x180093835  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18009383c  mov     edx, 631h; void *
0x180093841  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093847  mov     [rbp+160h+var_190], rdi
0x18009384b  mov     [rbp+160h+var_170], rdi
0x18009384f  mov     [rbp+160h+var_150], rdi
0x180093853  mov     [rbp+160h+string], rdi
0x180093857  mov     rdx, [rbp+160h+var_110]
0x18009385b  cmp     rdx, 7
0x18009385f  jbe     short loc_180093872
0x180093861  lea     rdx, ds:2[rdx*2]
0x180093869  mov     rcx, [rbp+160h+var_128]
0x18009386d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180093872  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18009387a  movdqu  xmmword ptr [rbp+48h], xmm0
0x18009387f  mov     word ptr [rbp+160h+var_128], di
0x180093883  cmp     [rbp+160h+var_1D0], dil
0x180093887  jz      short loc_1800938AC
0x180093889  mov     rcx, [rbp+160h+var_1D8]
0x18009388d  mov     rax, [rbp+160h+var_1E0]
0x180093891  mov     rdx, [rax]
0x180093894  mov     [rax], rcx
0x180093897  test    rdx, rdx
0x18009389a  jz      short loc_1800938AC
0x18009389c  mov     rax, [rdx]
0x18009389f  mov     rcx, rdx
0x1800938a2  mov     rax, [rax+10h]
0x1800938a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800938ab  nop
0x1800938ac  lea     rcx, [rsp+260h+hLibModule]
0x1800938b1  call    ?AddRefCurrentModule@details@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::details::AddRefCurrentModule(void)
0x1800938b6  nop
0x1800938b7  mov     r8, rax
0x1800938ba  mov     rdx, r12
0x1800938bd  lea     rcx, [rbp+160h+var_A0]
0x1800938c4  call    ??0_lambda_65204b8627083f4129f6e0117acac874_@@QEAA@AEBV?$function@$$A6AXAEAV?$cloud_store_notification@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@wil@@@Z@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(std::function<void (wil::cloud_store_notification<Windows::Data::CuratedTileCollection::TileCollectionContainer> &)> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800938c9  mov     rdx, rax
0x1800938cc  lea     rcx, [rsp+260h+var_1E8]
0x1800938d1  call    ??$Callback@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@V_lambda_65204b8627083f4129f6e0117acac874_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@@01@$$QEAV_lambda_65204b8627083f4129f6e0117acac874_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_65204b8627083f4129f6e0117acac874_>(_lambda_65204b8627083f4129f6e0117acac874_ &&)
0x1800938d6  nop
0x1800938d7  lea     rcx, [rbp+160h+var_A0]; this
0x1800938de  call    ??1_lambda_2c99ad496c9e815fb4bbcee01809bbab_@@QEAA@XZ; _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_(void)
0x1800938e3  nop
0x1800938e4  mov     rcx, [rsp+260h+hLibModule]; hLibModule
0x1800938e9  test    rcx, rcx
0x1800938ec  jz      short loc_1800938F4
0x1800938ee  call    cs:__imp_FreeLibrary
0x1800938f4  mov     rbx, [rsp+260h+var_1E8]
0x1800938f9  mov     r8, rbx
0x1800938fc  mov     rdx, [rsp+260h+var_1F0]
0x180093901  mov     rcx, r15
0x180093904  call    ??$make_cloud_store_watcher@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@YA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@PEAUICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAU?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@8@@Z; wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher *,Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *> *)
0x180093909  nop
0x18009390a  test    rbx, rbx
0x18009390d  jz      short loc_18009391F
0x18009390f  mov     rax, [rbx]
0x180093912  mov     rcx, rbx
0x180093915  mov     rax, [rax+10h]
0x180093919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009391e  nop
0x18009391f  mov     rcx, [rsp+260h+var_1F0]
0x180093924  test    rcx, rcx
0x180093927  jz      short loc_180093936
0x180093929  mov     rax, [rcx]
0x18009392c  mov     rax, [rax+10h]
0x180093930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093935  nop
0x180093936  lea     rcx, [rbp+160h+sourceString]; void *
0x18009393d  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x180093942  lea     rcx, [rbp+160h+var_E0]; void *
0x180093949  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18009394e  lea     rcx, [rbp+160h+var_100]; void *
0x180093952  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x180093957  nop
0x180093958  mov     rcx, r12; this
0x18009395b  call    ??1CloudItemUpdaterTestHook@Internal@CloudUtil@DataStoreCache@@QEAA@XZ; DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook::~CloudItemUpdaterTestHook(void)
0x180093960  mov     rax, r15
0x180093963  mov     rcx, [rbp+160h+var_50]
0x18009396a  xor     rcx, rsp; StackCookie
0x18009396d  call    __security_check_cookie
0x180093972  add     rsp, 228h
0x180093979  pop     r15
0x18009397b  pop     r14
0x18009397d  pop     r13
0x18009397f  pop     r12
0x180093981  pop     rdi
0x180093982  pop     rsi
0x180093983  pop     rbx
0x180093984  pop     rbp
0x180093985  retn
0x180093986  xor     r9d, r9d; lpArguments
0x180093989  xor     r8d, r8d; nNumberOfArguments
0x18009398c  lea     edx, [r9+1]; dwExceptionFlags
0x180093990  mov     ecx, 80070216h; dwExceptionCode
0x180093995  call    cs:__imp_RaiseException
0x18009399b  nop
0x18009399c  xor     r9d, r9d; lpArguments
0x18009399f  xor     r8d, r8d; nNumberOfArguments
0x1800939a2  lea     edx, [r9+1]; dwExceptionFlags
0x1800939a6  mov     ecx, 80070216h; dwExceptionCode
0x1800939ab  call    cs:__imp_RaiseException
0x1800939b1  nop
0x1800939b2  xor     r9d, r9d; lpArguments
0x1800939b5  xor     r8d, r8d; nNumberOfArguments
0x1800939b8  lea     edx, [r9+1]; dwExceptionFlags
0x1800939bc  mov     ecx, 80070216h; dwExceptionCode
0x1800939c1  call    cs:__imp_RaiseException
0x1800939c7  nop
0x1800939c8  xor     r9d, r9d; lpArguments
0x1800939cb  xor     r8d, r8d; nNumberOfArguments
0x1800939ce  lea     edx, [r9+1]; dwExceptionFlags
0x1800939d2  mov     ecx, 80070216h; dwExceptionCode
  ... truncated ...
```
