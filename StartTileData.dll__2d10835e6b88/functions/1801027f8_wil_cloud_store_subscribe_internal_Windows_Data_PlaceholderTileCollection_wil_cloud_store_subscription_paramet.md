# wil::cloud_store::subscribe_internal<Windows::Data::PlaceholderTileCollection>(wil::cloud_store_subscription_parameters const &,Windows::Data::Platform::ItemReference<Windows::Data::PlaceholderTileCollection> const *,std::function<void (wil::cloud_store_notification<Windows::Data::PlaceholderTileCollection> &)>)

- ea: `0x1801027f8`
- end: `0x180102c5a`
- name: `??$subscribe_internal@UPlaceholderTileCollection@Data@Windows@@@cloud_store@wil@@AEAA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@AEBVcloud_store_subscription_parameters@1@PEBU?$ItemReference@UPlaceholderTileCollection@Data@Windows@@@Platform@Data@Windows@@V?$function@$$A6AXAEAV?$cloud_store_notification@UPlaceholderTileCollection@Data@Windows@@@wil@@@Z@3@@Z`
- size: `1122`
- prototype: `__int64 __fastcall(int, int, int, int, DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180102790`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18002d944`
- `0x18005569c`
- `0x180055b74`
- `0x180056798`
- `0x1800574a8`
- `0x180057e7c`
- `0x18007ae80`
- `0x1801027f8`
- `0x180147be8`
- `0x180201e50`
- `0x1802bece0`
- `0x1802beed4`
- `0x18035e140`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180102b6a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180102b6a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801028f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010296e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801029df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102a44`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102c11`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102c27`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102c3d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102c53`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801028f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010296e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801029df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102a44`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102c11`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102c27`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102c3d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102c53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801028de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180102957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801029c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180102a2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801028de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180102957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801029c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180102a2d`

## pseudocode

```c
HMODULE __fastcall wil::cloud_store::subscribe_internal<Windows::Data::PlaceholderTileCollection>(
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
  wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::PlaceholderTileCollection>(v60, a4);
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
    JUMPOUT(0x180102C59LL);
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
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_dba0201cede2f29311085eb75d753b79_>(
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
0x1801027f8  push    rbp
0x1801027fa  push    rbx
0x1801027fb  push    rsi
0x1801027fc  push    rdi
0x1801027fd  push    r12
0x1801027ff  push    r13
0x180102801  push    r14
0x180102803  push    r15
0x180102805  lea     rbp, [rsp-128h]
0x18010280d  sub     rsp, 228h
0x180102814  mov     rax, cs:__security_cookie
0x18010281b  xor     rax, rsp
0x18010281e  mov     [rbp+160h+var_50], rax
0x180102825  mov     r14, r8
0x180102828  mov     r15, rdx
0x18010282b  mov     rbx, rcx
0x18010282e  mov     [rbp+160h+var_1C0], rcx
0x180102832  mov     [rsp+260h+hLibModule], rdx
0x180102837  mov     r12, [rbp+160h+arg_20]
0x18010283e  mov     [rbp+160h+var_1B0], r12
0x180102842  xor     r13d, r13d
0x180102845  mov     rdx, r9
0x180102848  lea     rcx, [rbp+160h+var_100]
0x18010284c  call    ??$validate_cloud_store_data_reference@UPlaceholderTileCollection@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@UPlaceholderTileCollection@Data@Windows@@@Platform@Data@Windows@@@Z; wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::PlaceholderTileCollection>(Windows::Data::Platform::ItemReference<Windows::Data::PlaceholderTileCollection> const *)
0x180102851  nop
0x180102852  mov     [rsp+260h+var_1F0], r13
0x180102857  mov     eax, [r14]
0x18010285a  mov     [rsp+260h+var_1F8], eax
0x18010285e  mov     rcx, [rbx]
0x180102861  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180102866  mov     rax, [rax]
0x180102869  mov     [rsp+260h+var_1E8], rax
0x18010286e  mov     rax, [rax]
0x180102871  mov     [rsp+260h+hLibModule], rax
0x180102876  lea     rcx, [rsp+260h+var_1F0]
0x18010287b  mov     [rbp+160h+var_1E0], rcx
0x18010287f  mov     [rbp+160h+var_1D8], r13
0x180102883  mov     [rbp+160h+var_1D0], 1
0x180102887  lea     rdx, [r14+10h]
0x18010288b  lea     rcx, [rbp+160h+var_128]
0x18010288f  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180102894  mov     rsi, rax
0x180102897  cmp     qword ptr [rax+18h], 7
0x18010289c  jbe     short loc_1801028A1
0x18010289e  mov     rsi, [rax]
0x1801028a1  mov     [rbp+160h+string], r13
0x1801028a5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801028a9  mov     rdi, rbx
0x1801028ac  inc     rdi
0x1801028af  cmp     [rsi+rdi*2], r13w
0x1801028b4  jnz     short loc_1801028AC
0x1801028b6  mov     eax, 0FFFFFFFFh
0x1801028bb  cmp     rdi, rax
0x1801028be  ja      loc_180102C44
0x1801028c4  mov     ecx, edi; unsigned int
0x1801028c6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801028cb  lea     edx, [rax-1]
0x1801028ce  cmp     edi, eax
0x1801028d0  cmovb   edx, edi; length
0x1801028d3  lea     r9, [rbp+160h+string]; string
0x1801028d7  lea     r8, [rbp+160h+hstringHeader]; hstringHeader
0x1801028db  mov     rcx, rsi; sourceString
0x1801028de  call    cs:__imp_WindowsCreateStringReference
0x1801028e4  test    eax, eax
0x1801028e6  jns     short loc_1801028FB
0x1801028e8  xor     r9d, r9d; lpArguments
0x1801028eb  xor     r8d, r8d; nNumberOfArguments
0x1801028ee  lea     edx, [r9+1]; dwExceptionFlags
0x1801028f2  mov     ecx, eax; dwExceptionCode
0x1801028f4  call    cs:__imp_RaiseException
0x1801028fa  nop
0x1801028fb  lea     rsi, [rbp+160h+sourceString]
0x180102902  cmp     [rbp+160h+var_A8], 7
0x18010290a  cmova   rsi, [rbp+160h+sourceString]
0x180102912  mov     [rbp+160h+var_150], r13
0x180102916  mov     rdi, rbx
0x180102919  inc     rdi
0x18010291c  cmp     [rsi+rdi*2], r13w
0x180102921  jnz     short loc_180102919
0x180102923  mov     eax, 0FFFFFFFFh
0x180102928  cmp     rdi, rax
0x18010292b  ja      loc_180102C2E
0x180102931  mov     r13, [rbp+160h+string]
0x180102935  mov     rax, [r14+8]
0x180102939  mov     [rbp+160h+var_1B8], rax
0x18010293d  mov     ecx, edi; unsigned int
0x18010293f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180102944  lea     edx, [rax-1]
0x180102947  cmp     edi, eax
0x180102949  cmovb   edx, edi; length
0x18010294c  lea     r9, [rbp+160h+var_150]; string
0x180102950  lea     r8, [rbp+160h+var_168]; hstringHeader
0x180102954  mov     rcx, rsi; sourceString
0x180102957  call    cs:__imp_WindowsCreateStringReference
0x18010295d  xor     ecx, ecx
0x18010295f  test    eax, eax
0x180102961  jns     short loc_180102975
0x180102963  xor     r9d, r9d; lpArguments
0x180102966  xor     r8d, r8d; nNumberOfArguments
0x180102969  lea     edx, [rcx+1]; dwExceptionFlags
0x18010296c  mov     ecx, eax; dwExceptionCode
0x18010296e  call    cs:__imp_RaiseException
0x180102974  nop
0x180102975  lea     rsi, [rbp+160h+var_E0]
0x18010297c  cmp     [rbp+160h+var_C8], 7
0x180102984  cmova   rsi, [rbp+160h+var_E0]
0x18010298c  mov     [rbp+160h+var_170], rcx
0x180102990  mov     rdi, rbx
0x180102993  inc     rdi
0x180102996  cmp     [rsi+rdi*2], cx
0x18010299a  jnz     short loc_180102993
0x18010299c  mov     eax, 0FFFFFFFFh
0x1801029a1  cmp     rdi, rax
0x1801029a4  ja      loc_180102C18
0x1801029aa  mov     r14, [rbp+160h+var_150]
0x1801029ae  mov     ecx, edi; unsigned int
0x1801029b0  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801029b5  lea     edx, [rax-1]
0x1801029b8  cmp     edi, eax
0x1801029ba  cmovb   edx, edi; length
0x1801029bd  lea     r9, [rbp+160h+var_170]; string
0x1801029c1  lea     r8, [rbp+160h+var_188]; hstringHeader
0x1801029c5  mov     rcx, rsi; sourceString
0x1801029c8  call    cs:__imp_WindowsCreateStringReference
0x1801029ce  xor     ecx, ecx
0x1801029d0  test    eax, eax
0x1801029d2  jns     short loc_1801029E6
0x1801029d4  xor     r9d, r9d; lpArguments
0x1801029d7  xor     r8d, r8d; nNumberOfArguments
0x1801029da  lea     edx, [rcx+1]; dwExceptionFlags
0x1801029dd  mov     ecx, eax; dwExceptionCode
0x1801029df  call    cs:__imp_RaiseException
0x1801029e5  nop
0x1801029e6  lea     rdi, [rbp+160h+var_100]
0x1801029ea  cmp     [rbp+160h+var_E8], 7
0x1801029ef  cmova   rdi, [rbp+160h+var_100]
0x1801029f4  mov     [rbp+160h+var_190], rcx
0x1801029f8  inc     rbx
0x1801029fb  cmp     [rdi+rbx*2], cx
0x1801029ff  jnz     short loc_1801029F8
0x180102a01  mov     eax, 0FFFFFFFFh
0x180102a06  cmp     rbx, rax
0x180102a09  ja      loc_180102C02
0x180102a0f  mov     rsi, [rbp+160h+var_170]
0x180102a13  mov     ecx, ebx; unsigned int
0x180102a15  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180102a1a  lea     edx, [rax-1]
0x180102a1d  cmp     ebx, eax
0x180102a1f  cmovb   edx, ebx; length
0x180102a22  lea     r9, [rbp+160h+var_190]; string
0x180102a26  lea     r8, [rbp+160h+var_1A8]; hstringHeader
0x180102a2a  mov     rcx, rdi; sourceString
0x180102a2d  call    cs:__imp_WindowsCreateStringReference
0x180102a33  xor     edi, edi
0x180102a35  test    eax, eax
0x180102a37  jns     short loc_180102A4B
0x180102a39  xor     r9d, r9d; lpArguments
0x180102a3c  xor     r8d, r8d; nNumberOfArguments
0x180102a3f  lea     edx, [rdi+1]; dwExceptionFlags
0x180102a42  mov     ecx, eax; dwExceptionCode
0x180102a44  call    cs:__imp_RaiseException
0x180102a4a  nop
0x180102a4b  mov     rdx, [rbp+160h+var_1C0]
0x180102a4f  mov     rax, [rdx+18h]
0x180102a53  test    rax, rax
0x180102a56  jz      short loc_180102A5D
0x180102a58  mov     r8, [rax]
0x180102a5b  jmp     short loc_180102A60
0x180102a5d  mov     r8, rdi
0x180102a60  lea     rax, [rbp+160h+var_1D8]
0x180102a64  mov     [rsp+260h+var_218], rax
0x180102a69  mov     [rsp+260h+var_220], r13
0x180102a6e  mov     rax, [rbp+160h+var_1B8]
0x180102a72  mov     [rsp+260h+var_228], rax
0x180102a77  mov     eax, [rsp+260h+var_1F8]
0x180102a7b  mov     [rsp+260h+var_230], eax
0x180102a7f  mov     [rsp+260h+var_238], r14
0x180102a84  mov     qword ptr [rsp+260h+var_240], rsi; int
0x180102a89  mov     r9, [rbp+160h+var_190]
0x180102a8d  mov     edx, [rdx+10h]
0x180102a90  mov     rcx, [rsp+260h+var_1E8]
0x180102a95  mov     rax, [rsp+260h+hLibModule]
0x180102a9a  mov     rax, [rax+70h]
0x180102a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102aa3  mov     rcx, [rbp+168h]; this
0x180102aaa  test    eax, eax
0x180102aac  jns     short loc_180102AC3
0x180102aae  mov     r9d, eax; char *
0x180102ab1  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180102ab8  mov     edx, 631h; void *
0x180102abd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180102ac3  mov     [rbp+160h+var_190], rdi
0x180102ac7  mov     [rbp+160h+var_170], rdi
0x180102acb  mov     [rbp+160h+var_150], rdi
0x180102acf  mov     [rbp+160h+string], rdi
0x180102ad3  mov     rdx, [rbp+160h+var_110]
0x180102ad7  cmp     rdx, 7
0x180102adb  jbe     short loc_180102AEE
0x180102add  lea     rdx, ds:2[rdx*2]
0x180102ae5  mov     rcx, [rbp+160h+var_128]
0x180102ae9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180102aee  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180102af6  movdqu  xmmword ptr [rbp+48h], xmm0
0x180102afb  mov     word ptr [rbp+160h+var_128], di
0x180102aff  cmp     [rbp+160h+var_1D0], dil
0x180102b03  jz      short loc_180102B28
0x180102b05  mov     rcx, [rbp+160h+var_1D8]
0x180102b09  mov     rax, [rbp+160h+var_1E0]
0x180102b0d  mov     rdx, [rax]
0x180102b10  mov     [rax], rcx
0x180102b13  test    rdx, rdx
0x180102b16  jz      short loc_180102B28
0x180102b18  mov     rax, [rdx]
0x180102b1b  mov     rcx, rdx
0x180102b1e  mov     rax, [rax+10h]
0x180102b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102b27  nop
0x180102b28  lea     rcx, [rsp+260h+hLibModule]
0x180102b2d  call    ?AddRefCurrentModule@details@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::details::AddRefCurrentModule(void)
0x180102b32  nop
0x180102b33  mov     r8, rax
0x180102b36  mov     rdx, r12
0x180102b39  lea     rcx, [rbp+160h+var_A0]
0x180102b40  call    ??0_lambda_65204b8627083f4129f6e0117acac874_@@QEAA@AEBV?$function@$$A6AXAEAV?$cloud_store_notification@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@wil@@@Z@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(std::function<void (wil::cloud_store_notification<Windows::Data::CuratedTileCollection::TileCollectionContainer> &)> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x180102b45  mov     rdx, rax
0x180102b48  lea     rcx, [rsp+260h+var_1E8]
0x180102b4d  call    ??$Callback@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@V_lambda_dba0201cede2f29311085eb75d753b79_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@@01@$$QEAV_lambda_dba0201cede2f29311085eb75d753b79_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_dba0201cede2f29311085eb75d753b79_>(_lambda_dba0201cede2f29311085eb75d753b79_ &&)
0x180102b52  nop
0x180102b53  lea     rcx, [rbp+160h+var_A0]; this
0x180102b5a  call    ??1_lambda_2c99ad496c9e815fb4bbcee01809bbab_@@QEAA@XZ; _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_(void)
0x180102b5f  nop
0x180102b60  mov     rcx, [rsp+260h+hLibModule]; hLibModule
0x180102b65  test    rcx, rcx
0x180102b68  jz      short loc_180102B70
0x180102b6a  call    cs:__imp_FreeLibrary
0x180102b70  mov     rbx, [rsp+260h+var_1E8]
0x180102b75  mov     r8, rbx
0x180102b78  mov     rdx, [rsp+260h+var_1F0]
0x180102b7d  mov     rcx, r15
0x180102b80  call    ??$make_cloud_store_watcher@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@YA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@PEAUICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAU?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@8@@Z; wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher *,Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *> *)
0x180102b85  nop
0x180102b86  test    rbx, rbx
0x180102b89  jz      short loc_180102B9B
0x180102b8b  mov     rax, [rbx]
0x180102b8e  mov     rcx, rbx
0x180102b91  mov     rax, [rax+10h]
0x180102b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102b9a  nop
0x180102b9b  mov     rcx, [rsp+260h+var_1F0]
0x180102ba0  test    rcx, rcx
0x180102ba3  jz      short loc_180102BB2
0x180102ba5  mov     rax, [rcx]
0x180102ba8  mov     rax, [rax+10h]
0x180102bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102bb1  nop
0x180102bb2  lea     rcx, [rbp+160h+sourceString]; void *
0x180102bb9  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x180102bbe  lea     rcx, [rbp+160h+var_E0]; void *
0x180102bc5  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x180102bca  lea     rcx, [rbp+160h+var_100]; void *
0x180102bce  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x180102bd3  nop
0x180102bd4  mov     rcx, r12; this
0x180102bd7  call    ??1CloudItemUpdaterTestHook@Internal@CloudUtil@DataStoreCache@@QEAA@XZ; DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook::~CloudItemUpdaterTestHook(void)
0x180102bdc  mov     rax, r15
0x180102bdf  mov     rcx, [rbp+160h+var_50]
0x180102be6  xor     rcx, rsp; StackCookie
0x180102be9  call    __security_check_cookie
0x180102bee  add     rsp, 228h
0x180102bf5  pop     r15
0x180102bf7  pop     r14
0x180102bf9  pop     r13
0x180102bfb  pop     r12
0x180102bfd  pop     rdi
0x180102bfe  pop     rsi
0x180102bff  pop     rbx
0x180102c00  pop     rbp
0x180102c01  retn
0x180102c02  xor     r9d, r9d; lpArguments
0x180102c05  xor     r8d, r8d; nNumberOfArguments
0x180102c08  lea     edx, [r9+1]; dwExceptionFlags
0x180102c0c  mov     ecx, 80070216h; dwExceptionCode
0x180102c11  call    cs:__imp_RaiseException
0x180102c17  nop
0x180102c18  xor     r9d, r9d; lpArguments
0x180102c1b  xor     r8d, r8d; nNumberOfArguments
0x180102c1e  lea     edx, [r9+1]; dwExceptionFlags
0x180102c22  mov     ecx, 80070216h; dwExceptionCode
0x180102c27  call    cs:__imp_RaiseException
0x180102c2d  nop
0x180102c2e  xor     r9d, r9d; lpArguments
0x180102c31  xor     r8d, r8d; nNumberOfArguments
0x180102c34  lea     edx, [r9+1]; dwExceptionFlags
0x180102c38  mov     ecx, 80070216h; dwExceptionCode
0x180102c3d  call    cs:__imp_RaiseException
0x180102c43  nop
0x180102c44  xor     r9d, r9d; lpArguments
0x180102c47  xor     r8d, r8d; nNumberOfArguments
0x180102c4a  lea     edx, [r9+1]; dwExceptionFlags
0x180102c4e  mov     ecx, 80070216h; dwExceptionCode
  ... truncated ...
```
