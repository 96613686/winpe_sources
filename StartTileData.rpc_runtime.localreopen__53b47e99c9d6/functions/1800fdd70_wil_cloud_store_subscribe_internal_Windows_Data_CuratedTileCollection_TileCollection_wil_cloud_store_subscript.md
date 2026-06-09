# wil::cloud_store::subscribe_internal<Windows::Data::CuratedTileCollection::TileCollection>(wil::cloud_store_subscription_parameters const &,Windows::Data::Platform::ItemReference<Windows::Data::CuratedTileCollection::TileCollection> const *,std::function<void (wil::cloud_store_notification<Windows::Data::CuratedTileCollection::TileCollection> &)>)

- ea: `0x1800fdd70`
- end: `0x1800fe1d2`
- name: `??$subscribe_internal@UTileCollection@CuratedTileCollection@Data@Windows@@@cloud_store@wil@@AEAA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@AEBVcloud_store_subscription_parameters@1@PEBU?$ItemReference@UTileCollection@CuratedTileCollection@Data@Windows@@@Platform@Data@Windows@@V?$function@$$A6AXAEAV?$cloud_store_notification@UTileCollection@CuratedTileCollection@Data@Windows@@@wil@@@Z@3@@Z`
- size: `1122`
- prototype: `__int64 __fastcall(int, int, int, int, DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800fdab0`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18002d944`
- `0x180055b74`
- `0x180056798`
- `0x180057068`
- `0x1800574a8`
- `0x180057e7c`
- `0x18007ae80`
- `0x1800fdd70`
- `0x180147be8`
- `0x180201e50`
- `0x1802bece0`
- `0x1802beed4`
- `0x18033ee64`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fe0e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fe0e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fde6c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fdee6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fdf57`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fdfbc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fe189`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fe19f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fe1b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fe1cb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fde6c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fdee6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fdf57`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fdfbc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fe189`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fe19f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fe1b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fe1cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fde56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fdecf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fdf40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fdfa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fde56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fdecf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fdf40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fdfa5`

## pseudocode

```c
HMODULE __fastcall wil::cloud_store::subscribe_internal<Windows::Data::CuratedTileCollection::TileCollection>(
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
  wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::CuratedTileCollection::TileCollection>(v60, a4);
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
    JUMPOUT(0x1800FE1D1LL);
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
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_2c99ad496c9e815fb4bbcee01809bbab_>(
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
0x1800fdd70  push    rbp
0x1800fdd72  push    rbx
0x1800fdd73  push    rsi
0x1800fdd74  push    rdi
0x1800fdd75  push    r12
0x1800fdd77  push    r13
0x1800fdd79  push    r14
0x1800fdd7b  push    r15
0x1800fdd7d  lea     rbp, [rsp-128h]
0x1800fdd85  sub     rsp, 228h
0x1800fdd8c  mov     rax, cs:__security_cookie
0x1800fdd93  xor     rax, rsp
0x1800fdd96  mov     [rbp+160h+var_50], rax
0x1800fdd9d  mov     r14, r8
0x1800fdda0  mov     r15, rdx
0x1800fdda3  mov     rbx, rcx
0x1800fdda6  mov     [rbp+160h+var_1C0], rcx
0x1800fddaa  mov     [rsp+260h+hLibModule], rdx
0x1800fddaf  mov     r12, [rbp+160h+arg_20]
0x1800fddb6  mov     [rbp+160h+var_1B0], r12
0x1800fddba  xor     r13d, r13d
0x1800fddbd  mov     rdx, r9
0x1800fddc0  lea     rcx, [rbp+160h+var_100]
0x1800fddc4  call    ??$validate_cloud_store_data_reference@UTileCollection@CuratedTileCollection@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@UTileCollection@CuratedTileCollection@Data@Windows@@@Platform@Data@Windows@@@Z; wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::CuratedTileCollection::TileCollection>(Windows::Data::Platform::ItemReference<Windows::Data::CuratedTileCollection::TileCollection> const *)
0x1800fddc9  nop
0x1800fddca  mov     [rsp+260h+var_1F0], r13
0x1800fddcf  mov     eax, [r14]
0x1800fddd2  mov     [rsp+260h+var_1F8], eax
0x1800fddd6  mov     rcx, [rbx]
0x1800fddd9  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x1800fddde  mov     rax, [rax]
0x1800fdde1  mov     [rsp+260h+var_1E8], rax
0x1800fdde6  mov     rax, [rax]
0x1800fdde9  mov     [rsp+260h+hLibModule], rax
0x1800fddee  lea     rcx, [rsp+260h+var_1F0]
0x1800fddf3  mov     [rbp+160h+var_1E0], rcx
0x1800fddf7  mov     [rbp+160h+var_1D8], r13
0x1800fddfb  mov     [rbp+160h+var_1D0], 1
0x1800fddff  lea     rdx, [r14+10h]
0x1800fde03  lea     rcx, [rbp+160h+var_128]
0x1800fde07  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x1800fde0c  mov     rsi, rax
0x1800fde0f  cmp     qword ptr [rax+18h], 7
0x1800fde14  jbe     short loc_1800FDE19
0x1800fde16  mov     rsi, [rax]
0x1800fde19  mov     [rbp+160h+string], r13
0x1800fde1d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800fde21  mov     rdi, rbx
0x1800fde24  inc     rdi
0x1800fde27  cmp     [rsi+rdi*2], r13w
0x1800fde2c  jnz     short loc_1800FDE24
0x1800fde2e  mov     eax, 0FFFFFFFFh
0x1800fde33  cmp     rdi, rax
0x1800fde36  ja      loc_1800FE1BC
0x1800fde3c  mov     ecx, edi; unsigned int
0x1800fde3e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800fde43  lea     edx, [rax-1]
0x1800fde46  cmp     edi, eax
0x1800fde48  cmovb   edx, edi; length
0x1800fde4b  lea     r9, [rbp+160h+string]; string
0x1800fde4f  lea     r8, [rbp+160h+hstringHeader]; hstringHeader
0x1800fde53  mov     rcx, rsi; sourceString
0x1800fde56  call    cs:__imp_WindowsCreateStringReference
0x1800fde5c  test    eax, eax
0x1800fde5e  jns     short loc_1800FDE73
0x1800fde60  xor     r9d, r9d; lpArguments
0x1800fde63  xor     r8d, r8d; nNumberOfArguments
0x1800fde66  lea     edx, [r9+1]; dwExceptionFlags
0x1800fde6a  mov     ecx, eax; dwExceptionCode
0x1800fde6c  call    cs:__imp_RaiseException
0x1800fde72  nop
0x1800fde73  lea     rsi, [rbp+160h+sourceString]
0x1800fde7a  cmp     [rbp+160h+var_A8], 7
0x1800fde82  cmova   rsi, [rbp+160h+sourceString]
0x1800fde8a  mov     [rbp+160h+var_150], r13
0x1800fde8e  mov     rdi, rbx
0x1800fde91  inc     rdi
0x1800fde94  cmp     [rsi+rdi*2], r13w
0x1800fde99  jnz     short loc_1800FDE91
0x1800fde9b  mov     eax, 0FFFFFFFFh
0x1800fdea0  cmp     rdi, rax
0x1800fdea3  ja      loc_1800FE1A6
0x1800fdea9  mov     r13, [rbp+160h+string]
0x1800fdead  mov     rax, [r14+8]
0x1800fdeb1  mov     [rbp+160h+var_1B8], rax
0x1800fdeb5  mov     ecx, edi; unsigned int
0x1800fdeb7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800fdebc  lea     edx, [rax-1]
0x1800fdebf  cmp     edi, eax
0x1800fdec1  cmovb   edx, edi; length
0x1800fdec4  lea     r9, [rbp+160h+var_150]; string
0x1800fdec8  lea     r8, [rbp+160h+var_168]; hstringHeader
0x1800fdecc  mov     rcx, rsi; sourceString
0x1800fdecf  call    cs:__imp_WindowsCreateStringReference
0x1800fded5  xor     ecx, ecx
0x1800fded7  test    eax, eax
0x1800fded9  jns     short loc_1800FDEED
0x1800fdedb  xor     r9d, r9d; lpArguments
0x1800fdede  xor     r8d, r8d; nNumberOfArguments
0x1800fdee1  lea     edx, [rcx+1]; dwExceptionFlags
0x1800fdee4  mov     ecx, eax; dwExceptionCode
0x1800fdee6  call    cs:__imp_RaiseException
0x1800fdeec  nop
0x1800fdeed  lea     rsi, [rbp+160h+var_E0]
0x1800fdef4  cmp     [rbp+160h+var_C8], 7
0x1800fdefc  cmova   rsi, [rbp+160h+var_E0]
0x1800fdf04  mov     [rbp+160h+var_170], rcx
0x1800fdf08  mov     rdi, rbx
0x1800fdf0b  inc     rdi
0x1800fdf0e  cmp     [rsi+rdi*2], cx
0x1800fdf12  jnz     short loc_1800FDF0B
0x1800fdf14  mov     eax, 0FFFFFFFFh
0x1800fdf19  cmp     rdi, rax
0x1800fdf1c  ja      loc_1800FE190
0x1800fdf22  mov     r14, [rbp+160h+var_150]
0x1800fdf26  mov     ecx, edi; unsigned int
0x1800fdf28  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800fdf2d  lea     edx, [rax-1]
0x1800fdf30  cmp     edi, eax
0x1800fdf32  cmovb   edx, edi; length
0x1800fdf35  lea     r9, [rbp+160h+var_170]; string
0x1800fdf39  lea     r8, [rbp+160h+var_188]; hstringHeader
0x1800fdf3d  mov     rcx, rsi; sourceString
0x1800fdf40  call    cs:__imp_WindowsCreateStringReference
0x1800fdf46  xor     ecx, ecx
0x1800fdf48  test    eax, eax
0x1800fdf4a  jns     short loc_1800FDF5E
0x1800fdf4c  xor     r9d, r9d; lpArguments
0x1800fdf4f  xor     r8d, r8d; nNumberOfArguments
0x1800fdf52  lea     edx, [rcx+1]; dwExceptionFlags
0x1800fdf55  mov     ecx, eax; dwExceptionCode
0x1800fdf57  call    cs:__imp_RaiseException
0x1800fdf5d  nop
0x1800fdf5e  lea     rdi, [rbp+160h+var_100]
0x1800fdf62  cmp     [rbp+160h+var_E8], 7
0x1800fdf67  cmova   rdi, [rbp+160h+var_100]
0x1800fdf6c  mov     [rbp+160h+var_190], rcx
0x1800fdf70  inc     rbx
0x1800fdf73  cmp     [rdi+rbx*2], cx
0x1800fdf77  jnz     short loc_1800FDF70
0x1800fdf79  mov     eax, 0FFFFFFFFh
0x1800fdf7e  cmp     rbx, rax
0x1800fdf81  ja      loc_1800FE17A
0x1800fdf87  mov     rsi, [rbp+160h+var_170]
0x1800fdf8b  mov     ecx, ebx; unsigned int
0x1800fdf8d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800fdf92  lea     edx, [rax-1]
0x1800fdf95  cmp     ebx, eax
0x1800fdf97  cmovb   edx, ebx; length
0x1800fdf9a  lea     r9, [rbp+160h+var_190]; string
0x1800fdf9e  lea     r8, [rbp+160h+var_1A8]; hstringHeader
0x1800fdfa2  mov     rcx, rdi; sourceString
0x1800fdfa5  call    cs:__imp_WindowsCreateStringReference
0x1800fdfab  xor     edi, edi
0x1800fdfad  test    eax, eax
0x1800fdfaf  jns     short loc_1800FDFC3
0x1800fdfb1  xor     r9d, r9d; lpArguments
0x1800fdfb4  xor     r8d, r8d; nNumberOfArguments
0x1800fdfb7  lea     edx, [rdi+1]; dwExceptionFlags
0x1800fdfba  mov     ecx, eax; dwExceptionCode
0x1800fdfbc  call    cs:__imp_RaiseException
0x1800fdfc2  nop
0x1800fdfc3  mov     rdx, [rbp+160h+var_1C0]
0x1800fdfc7  mov     rax, [rdx+18h]
0x1800fdfcb  test    rax, rax
0x1800fdfce  jz      short loc_1800FDFD5
0x1800fdfd0  mov     r8, [rax]
0x1800fdfd3  jmp     short loc_1800FDFD8
0x1800fdfd5  mov     r8, rdi
0x1800fdfd8  lea     rax, [rbp+160h+var_1D8]
0x1800fdfdc  mov     [rsp+260h+var_218], rax
0x1800fdfe1  mov     [rsp+260h+var_220], r13
0x1800fdfe6  mov     rax, [rbp+160h+var_1B8]
0x1800fdfea  mov     [rsp+260h+var_228], rax
0x1800fdfef  mov     eax, [rsp+260h+var_1F8]
0x1800fdff3  mov     [rsp+260h+var_230], eax
0x1800fdff7  mov     [rsp+260h+var_238], r14
0x1800fdffc  mov     qword ptr [rsp+260h+var_240], rsi; int
0x1800fe001  mov     r9, [rbp+160h+var_190]
0x1800fe005  mov     edx, [rdx+10h]
0x1800fe008  mov     rcx, [rsp+260h+var_1E8]
0x1800fe00d  mov     rax, [rsp+260h+hLibModule]
0x1800fe012  mov     rax, [rax+70h]
0x1800fe016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe01b  mov     rcx, [rbp+168h]; this
0x1800fe022  test    eax, eax
0x1800fe024  jns     short loc_1800FE03B
0x1800fe026  mov     r9d, eax; char *
0x1800fe029  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800fe030  mov     edx, 631h; void *
0x1800fe035  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800fe03b  mov     [rbp+160h+var_190], rdi
0x1800fe03f  mov     [rbp+160h+var_170], rdi
0x1800fe043  mov     [rbp+160h+var_150], rdi
0x1800fe047  mov     [rbp+160h+string], rdi
0x1800fe04b  mov     rdx, [rbp+160h+var_110]
0x1800fe04f  cmp     rdx, 7
0x1800fe053  jbe     short loc_1800FE066
0x1800fe055  lea     rdx, ds:2[rdx*2]
0x1800fe05d  mov     rcx, [rbp+160h+var_128]
0x1800fe061  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800fe066  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800fe06e  movdqu  xmmword ptr [rbp+48h], xmm0
0x1800fe073  mov     word ptr [rbp+160h+var_128], di
0x1800fe077  cmp     [rbp+160h+var_1D0], dil
0x1800fe07b  jz      short loc_1800FE0A0
0x1800fe07d  mov     rcx, [rbp+160h+var_1D8]
0x1800fe081  mov     rax, [rbp+160h+var_1E0]
0x1800fe085  mov     rdx, [rax]
0x1800fe088  mov     [rax], rcx
0x1800fe08b  test    rdx, rdx
0x1800fe08e  jz      short loc_1800FE0A0
0x1800fe090  mov     rax, [rdx]
0x1800fe093  mov     rcx, rdx
0x1800fe096  mov     rax, [rax+10h]
0x1800fe09a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe09f  nop
0x1800fe0a0  lea     rcx, [rsp+260h+hLibModule]
0x1800fe0a5  call    ?AddRefCurrentModule@details@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::details::AddRefCurrentModule(void)
0x1800fe0aa  nop
0x1800fe0ab  mov     r8, rax
0x1800fe0ae  mov     rdx, r12
0x1800fe0b1  lea     rcx, [rbp+160h+var_A0]
0x1800fe0b8  call    ??0_lambda_65204b8627083f4129f6e0117acac874_@@QEAA@AEBV?$function@$$A6AXAEAV?$cloud_store_notification@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@wil@@@Z@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _lambda_65204b8627083f4129f6e0117acac874_::_lambda_65204b8627083f4129f6e0117acac874_(std::function<void (wil::cloud_store_notification<Windows::Data::CuratedTileCollection::TileCollectionContainer> &)> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800fe0bd  mov     rdx, rax
0x1800fe0c0  lea     rcx, [rsp+260h+var_1E8]
0x1800fe0c5  call    ??$Callback@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@V_lambda_2c99ad496c9e815fb4bbcee01809bbab_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@Windows@@@01@$$QEAV_lambda_2c99ad496c9e815fb4bbcee01809bbab_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *>,_lambda_2c99ad496c9e815fb4bbcee01809bbab_>(_lambda_2c99ad496c9e815fb4bbcee01809bbab_ &&)
0x1800fe0ca  nop
0x1800fe0cb  lea     rcx, [rbp+160h+var_A0]; this
0x1800fe0d2  call    ??1_lambda_2c99ad496c9e815fb4bbcee01809bbab_@@QEAA@XZ; _lambda_2c99ad496c9e815fb4bbcee01809bbab_::~_lambda_2c99ad496c9e815fb4bbcee01809bbab_(void)
0x1800fe0d7  nop
0x1800fe0d8  mov     rcx, [rsp+260h+hLibModule]; hLibModule
0x1800fe0dd  test    rcx, rcx
0x1800fe0e0  jz      short loc_1800FE0E8
0x1800fe0e2  call    cs:__imp_FreeLibrary
0x1800fe0e8  mov     rbx, [rsp+260h+var_1E8]
0x1800fe0ed  mov     r8, rbx
0x1800fe0f0  mov     rdx, [rsp+260h+var_1F0]
0x1800fe0f5  mov     rcx, r15
0x1800fe0f8  call    ??$make_cloud_store_watcher@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@YA?AV?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@PEAUICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAU?$ITypedEventHandler@PEAVCloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@PEAVCloudStoreDataChangedEventArgs@2345@@Foundation@8@@Z; wil::details::make_cloud_store_watcher<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs>(Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher *,Windows::Foundation::ITypedEventHandler<Windows::Internal::Storage::Cloud::CloudStoreDataWatcher *,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs *> *)
0x1800fe0fd  nop
0x1800fe0fe  test    rbx, rbx
0x1800fe101  jz      short loc_1800FE113
0x1800fe103  mov     rax, [rbx]
0x1800fe106  mov     rcx, rbx
0x1800fe109  mov     rax, [rax+10h]
0x1800fe10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe112  nop
0x1800fe113  mov     rcx, [rsp+260h+var_1F0]
0x1800fe118  test    rcx, rcx
0x1800fe11b  jz      short loc_1800FE12A
0x1800fe11d  mov     rax, [rcx]
0x1800fe120  mov     rax, [rax+10h]
0x1800fe124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe129  nop
0x1800fe12a  lea     rcx, [rbp+160h+sourceString]; void *
0x1800fe131  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800fe136  lea     rcx, [rbp+160h+var_E0]; void *
0x1800fe13d  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800fe142  lea     rcx, [rbp+160h+var_100]; void *
0x1800fe146  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800fe14b  nop
0x1800fe14c  mov     rcx, r12; this
0x1800fe14f  call    ??1CloudItemUpdaterTestHook@Internal@CloudUtil@DataStoreCache@@QEAA@XZ; DataStoreCache::CloudUtil::Internal::CloudItemUpdaterTestHook::~CloudItemUpdaterTestHook(void)
0x1800fe154  mov     rax, r15
0x1800fe157  mov     rcx, [rbp+160h+var_50]
0x1800fe15e  xor     rcx, rsp; StackCookie
0x1800fe161  call    __security_check_cookie
0x1800fe166  add     rsp, 228h
0x1800fe16d  pop     r15
0x1800fe16f  pop     r14
0x1800fe171  pop     r13
0x1800fe173  pop     r12
0x1800fe175  pop     rdi
0x1800fe176  pop     rsi
0x1800fe177  pop     rbx
0x1800fe178  pop     rbp
0x1800fe179  retn
0x1800fe17a  xor     r9d, r9d; lpArguments
0x1800fe17d  xor     r8d, r8d; nNumberOfArguments
0x1800fe180  lea     edx, [r9+1]; dwExceptionFlags
0x1800fe184  mov     ecx, 80070216h; dwExceptionCode
0x1800fe189  call    cs:__imp_RaiseException
0x1800fe18f  nop
0x1800fe190  xor     r9d, r9d; lpArguments
0x1800fe193  xor     r8d, r8d; nNumberOfArguments
0x1800fe196  lea     edx, [r9+1]; dwExceptionFlags
0x1800fe19a  mov     ecx, 80070216h; dwExceptionCode
0x1800fe19f  call    cs:__imp_RaiseException
0x1800fe1a5  nop
0x1800fe1a6  xor     r9d, r9d; lpArguments
0x1800fe1a9  xor     r8d, r8d; nNumberOfArguments
0x1800fe1ac  lea     edx, [r9+1]; dwExceptionFlags
0x1800fe1b0  mov     ecx, 80070216h; dwExceptionCode
0x1800fe1b5  call    cs:__imp_RaiseException
0x1800fe1bb  nop
0x1800fe1bc  xor     r9d, r9d; lpArguments
0x1800fe1bf  xor     r8d, r8d; nNumberOfArguments
0x1800fe1c2  lea     edx, [r9+1]; dwExceptionFlags
0x1800fe1c6  mov     ecx, 80070216h; dwExceptionCode
  ... truncated ...
```
