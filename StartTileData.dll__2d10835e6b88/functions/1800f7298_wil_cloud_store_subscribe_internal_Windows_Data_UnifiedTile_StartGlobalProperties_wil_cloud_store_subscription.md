# wil::cloud_store::subscribe_internal<Windows::Data::UnifiedTile::StartGlobalProperties>(wil::cloud_store_subscription_parameters const &,Windows::Data::Platform::ItemReference<Windows::Data::UnifiedTile::StartGlobalProperties> const *,std::function<void (wil::cloud_store_notification<Windows::Data::UnifiedTile::StartGlobalProperties> &)>)

- ea: `0x1800f7298`
- end: `0x1800f76fa`
- name: `??$subscribe_internal@UStartGlobalProperties@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@AEBVcloud_store_subscription_parameters@1@PEBU?$ItemReference@UStartGlobalProperties@UnifiedTile@Data@Windows@@@Platform@Data@Windows@@V?$function@$$A6AXAEAV?$cloud_store_notification@UStartGlobalProperties@UnifiedTile@Data@Windows@@@wil@@@Z@3@@Z`
- size: `1122`
- prototype: `__int64 __fastcall(int, int, int, int, DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f7230`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18002d944`
- `0x180055b74`
- `0x180056798`
- `0x1800574a8`
- `0x180057e7c`
- `0x18005826c`
- `0x18007ae80`
- `0x1800f7298`
- `0x180147be8`
- `0x180201e50`
- `0x1802bc7ac`
- `0x1802bece0`
- `0x1802beed4`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800f760a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800f760a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f7394`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f740e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f747f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f74e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f76b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f76c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f76dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f76f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f7394`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f740e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f747f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f74e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f76b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f76c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f76dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f76f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f737e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f73f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f7468`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f74cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f737e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f73f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f7468`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f74cd`

## pseudocode

```c
HMODULE __fastcall wil::cloud_store::subscribe_internal<Windows::Data::UnifiedTile::StartGlobalProperties>(
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
  wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::UnifiedTile::StartGlobalProperties>(v60, a4);
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
    JUMPOUT(0x1800F76F9LL);
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
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_8a919aecede9ef220313ef10ec478dac_>(
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
0x1800f7298  push    rbp
0x1800f729a  push    rbx
0x1800f729b  push    rsi
0x1800f729c  push    rdi
0x1800f729d  push    r12
0x1800f729f  push    r13
0x1800f72a1  push    r14
0x1800f72a3  push    r15
0x1800f72a5  lea     rbp, [rsp-128h]
0x1800f72ad  sub     rsp, 228h
0x1800f72b4  mov     rax, cs:__security_cookie
0x1800f72bb  xor     rax, rsp
0x1800f72be  mov     [rbp+160h+var_50], rax
0x1800f72c5  mov     r14, r8
0x1800f72c8  mov     r15, rdx
0x1800f72cb  mov     rbx, rcx
0x1800f72ce  mov     [rbp+160h+var_1C0], rcx
0x1800f72d2  mov     [rsp+260h+hLibModule], rdx
0x1800f72d7  mov     r12, [rbp+160h+arg_20]
0x1800f72de  mov     [rbp+160h+var_1B0], r12
0x1800f72e2  xor     r13d, r13d
0x1800f72e5  mov     rdx, r9
0x1800f72e8  lea     rcx, [rbp+160h+var_100]
0x1800f72ec  call    ??$validate_cloud_store_data_reference@UStartGlobalProperties@UnifiedTile@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@UStartGlobalProperties@UnifiedTile@Data@Windows@@@Platform@Data@Windows@@@Z; wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::UnifiedTile::StartGlobalProperties>(Windows::Data::Platform::ItemReference<Windows::Data::UnifiedTile::StartGlobalProperties> const *)
0x1800f72f1  nop
0x1800f72f2  mov     [rsp+260h+var_1F0], r13
0x1800f72f7  mov     eax, [r14]
0x1800f72fa  mov     [rsp+260h+var_1F8], eax
0x1800f72fe  mov     rcx, [rbx]
0x1800f7301  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x1800f7306  mov     rax, [rax]
0x1800f7309  mov     [rsp+260h+var_1E8], rax
0x1800f730e  mov     rax, [rax]
0x1800f7311  mov     [rsp+260h+hLibModule], rax
0x1800f7316  lea     rcx, [rsp+260h+var_1F0]
0x1800f731b  mov     [rbp+160h+var_1E0], rcx
0x1800f731f  mov     [rbp+160h+var_1D8], r13
0x1800f7323  mov     [rbp+160h+var_1D0], 1
0x1800f7327  lea     rdx, [r14+10h]
0x1800f732b  lea     rcx, [rbp+160h+var_128]
0x1800f732f  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x1800f7334  mov     rsi, rax
0x1800f7337  cmp     qword ptr [rax+18h], 7
0x1800f733c  jbe     short loc_1800F7341
0x1800f733e  mov     rsi, [rax]
0x1800f7341  mov     [rbp+160h+string], r13
0x1800f7345  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f7349  mov     rdi, rbx
0x1800f734c  inc     rdi
0x1800f734f  cmp     [rsi+rdi*2], r13w
0x1800f7354  jnz     short loc_1800F734C
0x1800f7356  mov     eax, 0FFFFFFFFh
0x1800f735b  cmp     rdi, rax
0x1800f735e  ja      loc_1800F76E4
0x1800f7364  mov     ecx, edi; unsigned int
0x1800f7366  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800f736b  lea     edx, [rax-1]
0x1800f736e  cmp     edi, eax
0x1800f7370  cmovb   edx, edi; length
0x1800f7373  lea     r9, [rbp+160h+string]; string
0x1800f7377  lea     r8, [rbp+160h+hstringHeader]; hstringHeader
0x1800f737b  mov     rcx, rsi; sourceString
0x1800f737e  call    cs:__imp_WindowsCreateStringReference
0x1800f7384  test    eax, eax
0x1800f7386  jns     short loc_1800F739B
0x1800f7388  xor     r9d, r9d; lpArguments
0x1800f738b  xor     r8d, r8d; nNumberOfArguments
0x1800f738e  lea     edx, [r9+1]; dwExceptionFlags
0x1800f7392  mov     ecx, eax; dwExceptionCode
0x1800f7394  call    cs:__imp_RaiseException
0x1800f739a  nop
0x1800f739b  lea     rsi, [rbp+160h+sourceString]
0x1800f73a2  cmp     [rbp+160h+var_A8], 7
0x1800f73aa  cmova   rsi, [rbp+160h+sourceString]
0x1800f73b2  mov     [rbp+160h+var_150], r13
0x1800f73b6  mov     rdi, rbx
0x1800f73b9  inc     rdi
0x1800f73bc  cmp     [rsi+rdi*2], r13w
0x1800f73c1  jnz     short loc_1800F73B9
0x1800f73c3  mov     eax, 0FFFFFFFFh
0x1800f73c8  cmp     rdi, rax
0x1800f73cb  ja      loc_1800F76CE
0x1800f73d1  mov     r13, [rbp+160h+string]
0x1800f73d5  mov     rax, [r14+8]
0x1800f73d9  mov     [rbp+160h+var_1B8], rax
0x1800f73dd  mov     ecx, edi; unsigned int
0x1800f73df  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800f73e4  lea     edx, [rax-1]
0x1800f73e7  cmp     edi, eax
0x1800f73e9  cmovb   edx, edi; length
0x1800f73ec  lea     r9, [rbp+160h+var_150]; string
0x1800f73f0  lea     r8, [rbp+160h+var_168]; hstringHeader
0x1800f73f4  mov     rcx, rsi; sourceString
0x1800f73f7  call    cs:__imp_WindowsCreateStringReference
0x1800f73fd  xor     ecx, ecx
0x1800f73ff  test    eax, eax
0x1800f7401  jns     short loc_1800F7415
0x1800f7403  xor     r9d, r9d; lpArguments
0x1800f7406  xor     r8d, r8d; nNumberOfArguments
0x1800f7409  lea     edx, [rcx+1]; dwExceptionFlags
0x1800f740c  mov     ecx, eax; dwExceptionCode
0x1800f740e  call    cs:__imp_RaiseException
0x1800f7414  nop
0x1800f7415  lea     rsi, [rbp+160h+var_E0]
0x1800f741c  cmp     [rbp+160h+var_C8], 7
0x1800f7424  cmova   rsi, [rbp+160h+var_E0]
0x1800f742c  mov     [rbp+160h+var_170], rcx
0x1800f7430  mov     rdi, rbx
0x1800f7433  inc     rdi
0x1800f7436  cmp     [rsi+rdi*2], cx
0x1800f743a  jnz     short loc_1800F7433
0x1800f743c  mov     eax, 0FFFFFFFFh
0x1800f7441  cmp     rdi, rax
0x1800f7444  ja      loc_1800F76B8
0x1800f744a  mov     r14, [rbp+160h+var_150]
0x1800f744e  mov     ecx, edi; unsigned int
0x1800f7450  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800f7455  lea     edx, [rax-1]
0x1800f7458  cmp     edi, eax
0x1800f745a  cmovb   edx, edi; length
0x1800f745d  lea     r9, [rbp+160h+var_170]; string
0x1800f7461  lea     r8, [rbp+160h+var_188]; hstringHeader
0x1800f7465  mov     rcx, rsi; sourceString
0x1800f7468  call    cs:__imp_WindowsCreateStringReference
0x1800f746e  xor     ecx, ecx
0x1800f7470  test    eax, eax
0x1800f7472  jns     short loc_1800F7486
0x1800f7474  xor     r9d, r9d; lpArguments
0x1800f7477  xor     r8d, r8d; nNumberOfArguments
0x1800f747a  lea     edx, [rcx+1]; dwExceptionFlags
0x1800f747d  mov     ecx, eax; dwExceptionCode
0x1800f747f  call    cs:__imp_RaiseException
0x1800f7485  nop
0x1800f7486  lea     rdi, [rbp+160h+var_100]
0x1800f748a  cmp     [rbp+160h+var_E8], 7
0x1800f748f  cmova   rdi, [rbp+160h+var_100]
0x1800f7494  mov     [rbp+160h+var_190], rcx
0x1800f7498  inc     rbx
0x1800f749b  cmp     [rdi+rbx*2], cx
0x1800f749f  jnz     short loc_1800F7498
0x1800f74a1  mov     eax, 0FFFFFFFFh
0x1800f74a6  cmp     rbx, rax
0x1800f74a9  ja      loc_1800F76A2
0x1800f74af  mov     rsi, [rbp+160h+var_170]
0x1800f74b3  mov     ecx, ebx; unsigned int
0x1800f74b5  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800f74ba  lea     edx, [rax-1]
0x1800f74bd  cmp     ebx, eax
0x1800f74bf  cmovb   edx, ebx; length
0x1800f74c2  lea     r9, [rbp+160h+var_190]; string
0x1800f74c6  lea     r8, [rbp+160h+var_1A8]; hstringHeader
0x1800f74ca  mov     rcx, rdi; sourceString
0x1800f74cd  call    cs:__imp_WindowsCreateStringReference
0x1800f74d3  xor     edi, edi
0x1800f74d5  test    eax, eax
0x1800f74d7  jns     short loc_1800F74EB
0x1800f74d9  xor     r9d, r9d; lpArguments
0x1800f74dc  xor     r8d, r8d; nNumberOfArguments
0x1800f74df  lea     edx, [rdi+1]; dwExceptionFlags
0x1800f74e2  mov     ecx, eax; dwExceptionCode
0x1800f74e4  call    cs:__imp_RaiseException
0x1800f74ea  nop
0x1800f74eb  mov     rdx, [rbp+160h+var_1C0]
0x1800f74ef  mov     rax, [rdx+18h]
0x1800f74f3  test    rax, rax
0x1800f74f6  jz      short loc_1800F74FD
0x1800f74f8  mov     r8, [rax]
0x1800f74fb  jmp     short loc_1800F7500
0x1800f74fd  mov     r8, rdi
0x1800f7500  lea     rax, [rbp+160h+var_1D8]
0x1800f7504  mov     [rsp+260h+var_218], rax
0x1800f7509  mov     [rsp+260h+var_220], r13
0x1800f750e  mov     rax, [rbp+160h+var_1B8]
0x1800f7512  mov     [rsp+260h+var_228], rax
0x1800f7517  mov     eax, [rsp+260h+var_1F8]
0x1800f751b  mov     [rsp+260h+var_230], eax
0x1800f751f  mov     [rsp+260h+var_238], r14
0x1800f7524  mov     qword ptr [rsp+260h+var_240], rsi; int
0x1800f7529  mov     r9, [rbp+160h+var_190]
0x1800f752d  mov     edx, [rdx+10h]
0x1800f7530  mov     rcx, [rsp+260h+var_1E8]
0x1800f7535  mov     rax, [rsp+260h+hLibModule]
0x1800f753a  mov     rax, [rax+70h]
0x1800f753e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7543  mov     rcx, [rbp+168h]; this
0x1800f754a  test    eax, eax
0x1800f754c  jns     short loc_1800F7563
0x1800f754e  mov     r9d, eax; char *
0x1800f7551  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800f7558  mov     edx, 631h; void *
0x1800f755d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f7563  mov     [rbp+160h+var_190], rdi
0x1800f7567  mov     [rbp+160h+var_170], rdi
0x1800f756b  mov     [rbp+160h+var_150], rdi
0x1800f756f  mov     [rbp+160h+string], rdi
0x1800f7573  mov     rdx, [rbp+160h+var_110]
0x1800f7577  cmp     rdx, 7
0x1800f757b  jbe     short loc_1800F758E
0x1800f757d  lea     rdx, ds:2[rdx*2]
0x1800f7585  mov     rcx, [rbp+160h+var_128]
0x1800f7589  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800f758e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800f7596  movdqu  xmmword ptr [rbp+48h], xmm0
0x1800f759b  mov     word ptr [rbp+160h+var_128], di
0x1800f759f  cmp     [rbp+160h+var_1D0], dil
0x1800f75a3  jz      short loc_1800F75C8
0x1800f75a5  mov     rcx, [rbp+160h+var_1D8]
0x1800f75a9  mov     rax, [rbp+160h+var_1E0]
0x1800f75ad  mov     rdx, [rax]
0x1800f75b0  mov     [rax], rcx
0x1800f75b3  test    rdx, rdx
0x1800f75b6  jz      short loc_1800F75C8
0x1800f75b8  mov     rax, [rdx]
0x1800f75bb  mov     rcx, rdx
0x1800f75be  mov     rax, [rax+10h]
0x1800f75c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f75c7  nop
0x1800f75c8  lea     rcx, [rsp+260h+hLibModule]
0x1800f75cd  call    ?AddRefCurrentModule@details@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::details::AddRefCurrentModule(void)
0x1800f75d2  nop
0x1800f75d3  mov     r8, rax
0x1800f75d6  mov     rdx, r12
0x1800f75d9  lea     rcx, [rbp+160h+var_A0]
0x1800f75e0  call    ??0_lambda_65204b8627083f4129f6e0117acac874_@@QEAA@AEBV?$function@$$A6AXAEAV?$cloud_store_notification@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@wil@@@Z@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(std::function<void (wil::cloud_store_notification<Windows::Data::CuratedTileCollection::TileCollectionContainer> &)> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800f75e5  mov     rdx, rax
0x1800f75e8  lea     rcx, [rsp+260h+var_1E8]
0x1800f75ed  call    ??$Callback@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@V_lambda_8a919aecede9ef220313ef10ec478dac_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@@01@$$QEAV_lambda_8a919aecede9ef220313ef10ec478dac_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_8a919aecede9ef220313ef10ec478dac_>(_lambda_8a919aecede9ef220313ef10ec478dac_ &&)
0x1800f75f2  nop
0x1800f75f3  lea     rcx, [rbp+160h+var_A0]; this
0x1800f75fa  call    ??1_lambda_2c99ad496c9e815fb4bbcee01809bbab_@@QEAA@XZ; _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_(void)
0x1800f75ff  nop
0x1800f7600  mov     rcx, [rsp+260h+hLibModule]; hLibModule
0x1800f7605  test    rcx, rcx
0x1800f7608  jz      short loc_1800F7610
0x1800f760a  call    cs:__imp_FreeLibrary
0x1800f7610  mov     rbx, [rsp+260h+var_1E8]
0x1800f7615  mov     r8, rbx
0x1800f7618  mov     rdx, [rsp+260h+var_1F0]
0x1800f761d  mov     rcx, r15
0x1800f7620  call    ??$make_cloud_store_watcher@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@YA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@PEAUICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAU?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@8@@Z; wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher *,Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *> *)
0x1800f7625  nop
0x1800f7626  test    rbx, rbx
0x1800f7629  jz      short loc_1800F763B
0x1800f762b  mov     rax, [rbx]
0x1800f762e  mov     rcx, rbx
0x1800f7631  mov     rax, [rax+10h]
0x1800f7635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f763a  nop
0x1800f763b  mov     rcx, [rsp+260h+var_1F0]
0x1800f7640  test    rcx, rcx
0x1800f7643  jz      short loc_1800F7652
0x1800f7645  mov     rax, [rcx]
0x1800f7648  mov     rax, [rax+10h]
0x1800f764c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7651  nop
0x1800f7652  lea     rcx, [rbp+160h+sourceString]; void *
0x1800f7659  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800f765e  lea     rcx, [rbp+160h+var_E0]; void *
0x1800f7665  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800f766a  lea     rcx, [rbp+160h+var_100]; void *
0x1800f766e  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800f7673  nop
0x1800f7674  mov     rcx, r12; this
0x1800f7677  call    ??1CloudItemUpdaterTestHook@Internal@CloudUtil@DataStoreCache@@QEAA@XZ; DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook::~CloudItemUpdaterTestHook(void)
0x1800f767c  mov     rax, r15
0x1800f767f  mov     rcx, [rbp+160h+var_50]
0x1800f7686  xor     rcx, rsp; StackCookie
0x1800f7689  call    __security_check_cookie
0x1800f768e  add     rsp, 228h
0x1800f7695  pop     r15
0x1800f7697  pop     r14
0x1800f7699  pop     r13
0x1800f769b  pop     r12
0x1800f769d  pop     rdi
0x1800f769e  pop     rsi
0x1800f769f  pop     rbx
0x1800f76a0  pop     rbp
0x1800f76a1  retn
0x1800f76a2  xor     r9d, r9d; lpArguments
0x1800f76a5  xor     r8d, r8d; nNumberOfArguments
0x1800f76a8  lea     edx, [r9+1]; dwExceptionFlags
0x1800f76ac  mov     ecx, 80070216h; dwExceptionCode
0x1800f76b1  call    cs:__imp_RaiseException
0x1800f76b7  nop
0x1800f76b8  xor     r9d, r9d; lpArguments
0x1800f76bb  xor     r8d, r8d; nNumberOfArguments
0x1800f76be  lea     edx, [r9+1]; dwExceptionFlags
0x1800f76c2  mov     ecx, 80070216h; dwExceptionCode
0x1800f76c7  call    cs:__imp_RaiseException
0x1800f76cd  nop
0x1800f76ce  xor     r9d, r9d; lpArguments
0x1800f76d1  xor     r8d, r8d; nNumberOfArguments
0x1800f76d4  lea     edx, [r9+1]; dwExceptionFlags
0x1800f76d8  mov     ecx, 80070216h; dwExceptionCode
0x1800f76dd  call    cs:__imp_RaiseException
0x1800f76e3  nop
0x1800f76e4  xor     r9d, r9d; lpArguments
0x1800f76e7  xor     r8d, r8d; nNumberOfArguments
0x1800f76ea  lea     edx, [r9+1]; dwExceptionFlags
0x1800f76ee  mov     ecx, 80070216h; dwExceptionCode
  ... truncated ...
```
