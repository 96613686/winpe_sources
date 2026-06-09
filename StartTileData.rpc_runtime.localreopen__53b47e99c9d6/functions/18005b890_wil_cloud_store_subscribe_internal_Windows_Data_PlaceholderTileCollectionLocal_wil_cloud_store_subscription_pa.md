# wil::cloud_store::subscribe_internal<Windows::Data::PlaceholderTileCollectionLocal>(wil::cloud_store_subscription_parameters const &,Windows::Data::Platform::ItemReference<Windows::Data::PlaceholderTileCollectionLocal> const *,std::function<void (wil::cloud_store_notification<Windows::Data::PlaceholderTileCollectionLocal> &)>)

- ea: `0x18005b890`
- end: `0x18005bcf2`
- name: `??$subscribe_internal@UPlaceholderTileCollectionLocal@Data@Windows@@@cloud_store@wil@@AEAA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@AEBVcloud_store_subscription_parameters@1@PEBU?$ItemReference@UPlaceholderTileCollectionLocal@Data@Windows@@@Platform@Data@Windows@@V?$function@$$A6AXAEAV?$cloud_store_notification@UPlaceholderTileCollectionLocal@Data@Windows@@@wil@@@Z@3@@Z`
- size: `1122`
- prototype: `__int64 __fastcall(int, int, int, int, DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180059dbc`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18002d944`
- `0x180055b74`
- `0x180056798`
- `0x180056b34`
- `0x1800574a8`
- `0x180057e7c`
- `0x18005b890`
- `0x18007ae80`
- `0x180147be8`
- `0x180201e50`
- `0x1802bece0`
- `0x1802beed4`
- `0x18035e1b0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005bc02`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005bc02`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b98c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005ba06`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005ba77`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005badc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005bca9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005bcbf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005bcd5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005bceb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b98c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005ba06`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005ba77`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005badc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005bca9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005bcbf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005bcd5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005bceb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b976`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b9ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005ba60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b976`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b9ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005ba60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bac5`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
HMODULE __fastcall wil::cloud_store::subscribe_internal<Windows::Data::PlaceholderTileCollectionLocal>(
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
  wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::PlaceholderTileCollectionLocal>(v60, a4);
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
    JUMPOUT(0x18005BCF1LL);
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
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_f1a31c41723f86f03c8da74a12ac6e48_>(
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
0x18005b890  push    rbp
0x18005b892  push    rbx
0x18005b893  push    rsi
0x18005b894  push    rdi
0x18005b895  push    r12
0x18005b897  push    r13
0x18005b899  push    r14
0x18005b89b  push    r15
0x18005b89d  lea     rbp, [rsp-128h]
0x18005b8a5  sub     rsp, 228h
0x18005b8ac  mov     rax, cs:__security_cookie
0x18005b8b3  xor     rax, rsp
0x18005b8b6  mov     [rbp+160h+var_50], rax
0x18005b8bd  mov     r14, r8
0x18005b8c0  mov     r15, rdx
0x18005b8c3  mov     rbx, rcx
0x18005b8c6  mov     [rbp+160h+var_1C0], rcx
0x18005b8ca  mov     [rsp+260h+hLibModule], rdx
0x18005b8cf  mov     r12, [rbp+160h+arg_20]
0x18005b8d6  mov     [rbp+160h+var_1B0], r12
0x18005b8da  xor     r13d, r13d
0x18005b8dd  mov     rdx, r9
0x18005b8e0  lea     rcx, [rbp+160h+var_100]
0x18005b8e4  call    ??$validate_cloud_store_data_reference@UPlaceholderTileCollectionLocal@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@UPlaceholderTileCollectionLocal@Data@Windows@@@Platform@Data@Windows@@@Z; wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::PlaceholderTileCollectionLocal>(Windows::Data::Platform::ItemReference<Windows::Data::PlaceholderTileCollectionLocal> const *)
0x18005b8e9  nop
0x18005b8ea  mov     [rsp+260h+var_1F0], r13
0x18005b8ef  mov     eax, [r14]
0x18005b8f2  mov     [rsp+260h+var_1F8], eax
0x18005b8f6  mov     rcx, [rbx]
0x18005b8f9  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x18005b8fe  mov     rax, [rax]
0x18005b901  mov     [rsp+260h+var_1E8], rax
0x18005b906  mov     rax, [rax]
0x18005b909  mov     [rsp+260h+hLibModule], rax
0x18005b90e  lea     rcx, [rsp+260h+var_1F0]
0x18005b913  mov     [rbp+160h+var_1E0], rcx
0x18005b917  mov     [rbp+160h+var_1D8], r13
0x18005b91b  mov     [rbp+160h+var_1D0], 1
0x18005b91f  lea     rdx, [r14+10h]
0x18005b923  lea     rcx, [rbp+160h+var_128]
0x18005b927  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18005b92c  mov     rsi, rax
0x18005b92f  cmp     qword ptr [rax+18h], 7
0x18005b934  jbe     short loc_18005B939
0x18005b936  mov     rsi, [rax]
0x18005b939  mov     [rbp+160h+string], r13
0x18005b93d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005b941  mov     rdi, rbx
0x18005b944  inc     rdi
0x18005b947  cmp     [rsi+rdi*2], r13w
0x18005b94c  jnz     short loc_18005B944
0x18005b94e  mov     eax, 0FFFFFFFFh
0x18005b953  cmp     rdi, rax
0x18005b956  ja      loc_18005BCDC
0x18005b95c  mov     ecx, edi; unsigned int
0x18005b95e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005b963  lea     edx, [rax-1]
0x18005b966  cmp     edi, eax
0x18005b968  cmovb   edx, edi; length
0x18005b96b  lea     r9, [rbp+160h+string]; string
0x18005b96f  lea     r8, [rbp+160h+hstringHeader]; hstringHeader
0x18005b973  mov     rcx, rsi; sourceString
0x18005b976  call    cs:__imp_WindowsCreateStringReference
0x18005b97c  test    eax, eax
0x18005b97e  jns     short loc_18005B993
0x18005b980  xor     r9d, r9d; lpArguments
0x18005b983  xor     r8d, r8d; nNumberOfArguments
0x18005b986  lea     edx, [r9+1]; dwExceptionFlags
0x18005b98a  mov     ecx, eax; dwExceptionCode
0x18005b98c  call    cs:__imp_RaiseException
0x18005b992  nop
0x18005b993  lea     rsi, [rbp+160h+sourceString]
0x18005b99a  cmp     [rbp+160h+var_A8], 7
0x18005b9a2  cmova   rsi, [rbp+160h+sourceString]
0x18005b9aa  mov     [rbp+160h+var_150], r13
0x18005b9ae  mov     rdi, rbx
0x18005b9b1  inc     rdi
0x18005b9b4  cmp     [rsi+rdi*2], r13w
0x18005b9b9  jnz     short loc_18005B9B1
0x18005b9bb  mov     eax, 0FFFFFFFFh
0x18005b9c0  cmp     rdi, rax
0x18005b9c3  ja      loc_18005BCC6
0x18005b9c9  mov     r13, [rbp+160h+string]
0x18005b9cd  mov     rax, [r14+8]
0x18005b9d1  mov     [rbp+160h+var_1B8], rax
0x18005b9d5  mov     ecx, edi; unsigned int
0x18005b9d7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005b9dc  lea     edx, [rax-1]
0x18005b9df  cmp     edi, eax
0x18005b9e1  cmovb   edx, edi; length
0x18005b9e4  lea     r9, [rbp+160h+var_150]; string
0x18005b9e8  lea     r8, [rbp+160h+var_168]; hstringHeader
0x18005b9ec  mov     rcx, rsi; sourceString
0x18005b9ef  call    cs:__imp_WindowsCreateStringReference
0x18005b9f5  xor     ecx, ecx
0x18005b9f7  test    eax, eax
0x18005b9f9  jns     short loc_18005BA0D
0x18005b9fb  xor     r9d, r9d; lpArguments
0x18005b9fe  xor     r8d, r8d; nNumberOfArguments
0x18005ba01  lea     edx, [rcx+1]; dwExceptionFlags
0x18005ba04  mov     ecx, eax; dwExceptionCode
0x18005ba06  call    cs:__imp_RaiseException
0x18005ba0c  nop
0x18005ba0d  lea     rsi, [rbp+160h+var_E0]
0x18005ba14  cmp     [rbp+160h+var_C8], 7
0x18005ba1c  cmova   rsi, [rbp+160h+var_E0]
0x18005ba24  mov     [rbp+160h+var_170], rcx
0x18005ba28  mov     rdi, rbx
0x18005ba2b  inc     rdi
0x18005ba2e  cmp     [rsi+rdi*2], cx
0x18005ba32  jnz     short loc_18005BA2B
0x18005ba34  mov     eax, 0FFFFFFFFh
0x18005ba39  cmp     rdi, rax
0x18005ba3c  ja      loc_18005BCB0
0x18005ba42  mov     r14, [rbp+160h+var_150]
0x18005ba46  mov     ecx, edi; unsigned int
0x18005ba48  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005ba4d  lea     edx, [rax-1]
0x18005ba50  cmp     edi, eax
0x18005ba52  cmovb   edx, edi; length
0x18005ba55  lea     r9, [rbp+160h+var_170]; string
0x18005ba59  lea     r8, [rbp+160h+var_188]; hstringHeader
0x18005ba5d  mov     rcx, rsi; sourceString
0x18005ba60  call    cs:__imp_WindowsCreateStringReference
0x18005ba66  xor     ecx, ecx
0x18005ba68  test    eax, eax
0x18005ba6a  jns     short loc_18005BA7E
0x18005ba6c  xor     r9d, r9d; lpArguments
0x18005ba6f  xor     r8d, r8d; nNumberOfArguments
0x18005ba72  lea     edx, [rcx+1]; dwExceptionFlags
0x18005ba75  mov     ecx, eax; dwExceptionCode
0x18005ba77  call    cs:__imp_RaiseException
0x18005ba7d  nop
0x18005ba7e  lea     rdi, [rbp+160h+var_100]
0x18005ba82  cmp     [rbp+160h+var_E8], 7
0x18005ba87  cmova   rdi, [rbp+160h+var_100]
0x18005ba8c  mov     [rbp+160h+var_190], rcx
0x18005ba90  inc     rbx
0x18005ba93  cmp     [rdi+rbx*2], cx
0x18005ba97  jnz     short loc_18005BA90
0x18005ba99  mov     eax, 0FFFFFFFFh
0x18005ba9e  cmp     rbx, rax
0x18005baa1  ja      loc_18005BC9A
0x18005baa7  mov     rsi, [rbp+160h+var_170]
0x18005baab  mov     ecx, ebx; unsigned int
0x18005baad  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005bab2  lea     edx, [rax-1]
0x18005bab5  cmp     ebx, eax
0x18005bab7  cmovb   edx, ebx; length
0x18005baba  lea     r9, [rbp+160h+var_190]; string
0x18005babe  lea     r8, [rbp+160h+var_1A8]; hstringHeader
0x18005bac2  mov     rcx, rdi; sourceString
0x18005bac5  call    cs:__imp_WindowsCreateStringReference
0x18005bacb  xor     edi, edi
0x18005bacd  test    eax, eax
0x18005bacf  jns     short loc_18005BAE3
0x18005bad1  xor     r9d, r9d; lpArguments
0x18005bad4  xor     r8d, r8d; nNumberOfArguments
0x18005bad7  lea     edx, [rdi+1]; dwExceptionFlags
0x18005bada  mov     ecx, eax; dwExceptionCode
0x18005badc  call    cs:__imp_RaiseException
0x18005bae2  nop
0x18005bae3  mov     rdx, [rbp+160h+var_1C0]
0x18005bae7  mov     rax, [rdx+18h]
0x18005baeb  test    rax, rax
0x18005baee  jz      short loc_18005BAF5
0x18005baf0  mov     r8, [rax]
0x18005baf3  jmp     short loc_18005BAF8
0x18005baf5  mov     r8, rdi
0x18005baf8  lea     rax, [rbp+160h+var_1D8]
0x18005bafc  mov     [rsp+260h+var_218], rax
0x18005bb01  mov     [rsp+260h+var_220], r13
0x18005bb06  mov     rax, [rbp+160h+var_1B8]
0x18005bb0a  mov     [rsp+260h+var_228], rax
0x18005bb0f  mov     eax, [rsp+260h+var_1F8]
0x18005bb13  mov     [rsp+260h+var_230], eax
0x18005bb17  mov     [rsp+260h+var_238], r14
0x18005bb1c  mov     qword ptr [rsp+260h+var_240], rsi; int
0x18005bb21  mov     r9, [rbp+160h+var_190]
0x18005bb25  mov     edx, [rdx+10h]
0x18005bb28  mov     rcx, [rsp+260h+var_1E8]
0x18005bb2d  mov     rax, [rsp+260h+hLibModule]
0x18005bb32  mov     rax, [rax+70h]
0x18005bb36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb3b  mov     rcx, [rbp+168h]; this
0x18005bb42  test    eax, eax
0x18005bb44  jns     short loc_18005BB5B
0x18005bb46  mov     r9d, eax; char *
0x18005bb49  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18005bb50  mov     edx, 631h; void *
0x18005bb55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005bb5b  mov     [rbp+160h+var_190], rdi
0x18005bb5f  mov     [rbp+160h+var_170], rdi
0x18005bb63  mov     [rbp+160h+var_150], rdi
0x18005bb67  mov     [rbp+160h+string], rdi
0x18005bb6b  mov     rdx, [rbp+160h+var_110]
0x18005bb6f  cmp     rdx, 7
0x18005bb73  jbe     short loc_18005BB86
0x18005bb75  lea     rdx, ds:2[rdx*2]
0x18005bb7d  mov     rcx, [rbp+160h+var_128]
0x18005bb81  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005bb86  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18005bb8e  movdqu  xmmword ptr [rbp+48h], xmm0
0x18005bb93  mov     word ptr [rbp+160h+var_128], di
0x18005bb97  cmp     [rbp+160h+var_1D0], dil
0x18005bb9b  jz      short loc_18005BBC0
0x18005bb9d  mov     rcx, [rbp+160h+var_1D8]
0x18005bba1  mov     rax, [rbp+160h+var_1E0]
0x18005bba5  mov     rdx, [rax]
0x18005bba8  mov     [rax], rcx
0x18005bbab  test    rdx, rdx
0x18005bbae  jz      short loc_18005BBC0
0x18005bbb0  mov     rax, [rdx]
0x18005bbb3  mov     rcx, rdx
0x18005bbb6  mov     rax, [rax+10h]
0x18005bbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bbbf  nop
0x18005bbc0  lea     rcx, [rsp+260h+hLibModule]
0x18005bbc5  call    ?AddRefCurrentModule@details@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::details::AddRefCurrentModule(void)
0x18005bbca  nop
0x18005bbcb  mov     r8, rax
0x18005bbce  mov     rdx, r12
0x18005bbd1  lea     rcx, [rbp+160h+var_A0]
0x18005bbd8  call    ??0_lambda_65204b8627083f4129f6e0117acac874_@@QEAA@AEBV?$function@$$A6AXAEAV?$cloud_store_notification@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@wil@@@Z@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(std::function<void (wil::cloud_store_notification<Windows::Data::CuratedTileCollection::TileCollectionContainer> &)> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x18005bbdd  mov     rdx, rax
0x18005bbe0  lea     rcx, [rsp+260h+var_1E8]
0x18005bbe5  call    ??$Callback@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@V_lambda_f1a31c41723f86f03c8da74a12ac6e48_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@@01@$$QEAV_lambda_f1a31c41723f86f03c8da74a12ac6e48_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_f1a31c41723f86f03c8da74a12ac6e48_>(_lambda_f1a31c41723f86f03c8da74a12ac6e48_ &&)
0x18005bbea  nop
0x18005bbeb  lea     rcx, [rbp+160h+var_A0]; this
0x18005bbf2  call    ??1_lambda_2c99ad496c9e815fb4bbcee01809bbab_@@QEAA@XZ; _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_(void)
0x18005bbf7  nop
0x18005bbf8  mov     rcx, [rsp+260h+hLibModule]; hLibModule
0x18005bbfd  test    rcx, rcx
0x18005bc00  jz      short loc_18005BC08
0x18005bc02  call    cs:__imp_FreeLibrary
0x18005bc08  mov     rbx, [rsp+260h+var_1E8]
0x18005bc0d  mov     r8, rbx
0x18005bc10  mov     rdx, [rsp+260h+var_1F0]
0x18005bc15  mov     rcx, r15
0x18005bc18  call    ??$make_cloud_store_watcher@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@YA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@PEAUICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAU?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@8@@Z; wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher *,Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *> *)
0x18005bc1d  nop
0x18005bc1e  test    rbx, rbx
0x18005bc21  jz      short loc_18005BC33
0x18005bc23  mov     rax, [rbx]
0x18005bc26  mov     rcx, rbx
0x18005bc29  mov     rax, [rax+10h]
0x18005bc2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc32  nop
0x18005bc33  mov     rcx, [rsp+260h+var_1F0]
0x18005bc38  test    rcx, rcx
0x18005bc3b  jz      short loc_18005BC4A
0x18005bc3d  mov     rax, [rcx]
0x18005bc40  mov     rax, [rax+10h]
0x18005bc44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc49  nop
0x18005bc4a  lea     rcx, [rbp+160h+sourceString]; void *
0x18005bc51  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18005bc56  lea     rcx, [rbp+160h+var_E0]; void *
0x18005bc5d  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18005bc62  lea     rcx, [rbp+160h+var_100]; void *
0x18005bc66  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18005bc6b  nop
0x18005bc6c  mov     rcx, r12; this
0x18005bc6f  call    ??1CloudItemUpdaterTestHook@Internal@CloudUtil@DataStoreCache@@QEAA@XZ; DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook::~CloudItemUpdaterTestHook(void)
0x18005bc74  mov     rax, r15
0x18005bc77  mov     rcx, [rbp+160h+var_50]
0x18005bc7e  xor     rcx, rsp; StackCookie
0x18005bc81  call    __security_check_cookie
0x18005bc86  add     rsp, 228h
0x18005bc8d  pop     r15
0x18005bc8f  pop     r14
0x18005bc91  pop     r13
0x18005bc93  pop     r12
0x18005bc95  pop     rdi
0x18005bc96  pop     rsi
0x18005bc97  pop     rbx
0x18005bc98  pop     rbp
0x18005bc99  retn
0x18005bc9a  xor     r9d, r9d; lpArguments
0x18005bc9d  xor     r8d, r8d; nNumberOfArguments
0x18005bca0  lea     edx, [r9+1]; dwExceptionFlags
0x18005bca4  mov     ecx, 80070216h; dwExceptionCode
0x18005bca9  call    cs:__imp_RaiseException
0x18005bcaf  nop
0x18005bcb0  xor     r9d, r9d; lpArguments
0x18005bcb3  xor     r8d, r8d; nNumberOfArguments
0x18005bcb6  lea     edx, [r9+1]; dwExceptionFlags
0x18005bcba  mov     ecx, 80070216h; dwExceptionCode
0x18005bcbf  call    cs:__imp_RaiseException
0x18005bcc5  nop
0x18005bcc6  xor     r9d, r9d; lpArguments
0x18005bcc9  xor     r8d, r8d; nNumberOfArguments
0x18005bccc  lea     edx, [r9+1]; dwExceptionFlags
0x18005bcd0  mov     ecx, 80070216h; dwExceptionCode
0x18005bcd5  call    cs:__imp_RaiseException
0x18005bcdb  nop
0x18005bcdc  xor     r9d, r9d; lpArguments
0x18005bcdf  xor     r8d, r8d; nNumberOfArguments
0x18005bce2  lea     edx, [r9+1]; dwExceptionFlags
0x18005bce6  mov     ecx, 80070216h; dwExceptionCode
  ... truncated ...
```
