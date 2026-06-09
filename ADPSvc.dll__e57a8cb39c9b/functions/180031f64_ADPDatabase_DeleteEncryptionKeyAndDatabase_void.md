# ADPDatabase::DeleteEncryptionKeyAndDatabase(void)

- ea: `0x180031f64`
- end: `0x180032404`
- name: `?DeleteEncryptionKeyAndDatabase@ADPDatabase@@AEAAXXZ`
- size: `1184`
- prototype: `void __fastcall(ADPDatabase *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180033814`

## callees

- `0x180001008`
- `0x180002250`
- `0x180002cf8`
- `0x18000c37c`
- `0x18000e1d0`
- `0x180025a28`
- `0x18002a0a8`
- `0x18002a5f4`
- `0x18002a6ac`
- `0x180031f64`
- `0x180032920`
- `0x180032da4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180032013`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180032013`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800320f8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003219e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800322c0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003234c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800323d8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800320f8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003219e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800322c0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003234c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800323d8`

## pseudocode

```c
void __fastcall ADPDatabase::DeleteEncryptionKeyAndDatabase(ADPDatabase *this)
{
  _QWORD *v2; // rbx
  char *v3; // rdi
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  _QWORD *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  const WCHAR *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  _BYTE *v25; // rcx
  __int64 DbPath; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  const WCHAR *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  const WCHAR *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  const WCHAR *v40; // rcx
  char *v41; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+38h] [rbp-C8h] BYREF
  __m128i si128; // [rsp+48h] [rbp-B8h]
  _BYTE v44[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v45[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v46[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v47[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v48[40]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR SubKey[256]; // [rsp+100h] [rbp+0h] BYREF

  v2 = (_QWORD *)((char *)this + 104);
  if ( *((_QWORD *)this + 16) <= 7u )
    v3 = (char *)this + 104;
  else
    v3 = (char *)*v2;
  v4 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
  if ( *v4 > 3u )
  {
    v41 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (_DWORD)v4,
      (unsigned int)word_180100572,
      v5,
      v6,
      (__int64)&v41);
  }
  memset_0(SubKey, 0, 0x1FEu);
  if ( v2[3] <= 7u )
    v7 = v2;
  else
    v7 = (_QWORD *)*v2;
  ADPDatabase::FillEncryptionKeyPath(
    this,
    SubKey,
    255,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\AggregatedDataPlatform\\Keys",
    v7);
  RegDeleteTreeW(HKEY_CURRENT_USER, SubKey);
  *(_OWORD *)lpFileName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpFileName[0]) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55934612>::GetImpl'::`2'::impl) )
  {
    DbPath = ADPDatabase::GetDbPath((__int64)v44);
    v27 = std::operator+<wchar_t>(v45, DbPath, L"\\");
    v28 = std::operator+<wchar_t>(v46, v27, v2);
    v29 = std::operator+<wchar_t>(v47, v28, L".db");
    std::wstring::operator=(lpFileName, v29);
    std::wstring::~wstring(v47);
    std::wstring::~wstring(v46);
    std::wstring::~wstring(v45);
    std::wstring::~wstring(v44);
    v30 = (const WCHAR *)lpFileName;
    if ( si128.m128i_i64[1] > 7uLL )
      v30 = lpFileName[0];
    DeleteFileW(v30);
    v31 = ADPDatabase::GetDbPath((__int64)v44);
    v32 = std::operator+<wchar_t>(v45, v31, L"\\");
    v33 = std::operator+<wchar_t>(v46, v32, v2);
    v34 = std::operator+<wchar_t>(v47, v33, L".db-shm");
    std::wstring::operator=(lpFileName, v34);
    std::wstring::~wstring(v47);
    std::wstring::~wstring(v46);
    std::wstring::~wstring(v45);
    std::wstring::~wstring(v44);
    v35 = (const WCHAR *)lpFileName;
    if ( si128.m128i_i64[1] > 7uLL )
      v35 = lpFileName[0];
    DeleteFileW(v35);
    v36 = ADPDatabase::GetDbPath((__int64)v44);
    v37 = std::operator+<wchar_t>(v45, v36, L"\\");
    v38 = std::operator+<wchar_t>(v46, v37, v2);
    v39 = std::operator+<wchar_t>(v47, v38, L".db-wal");
    std::wstring::operator=(lpFileName, v39);
    std::wstring::~wstring(v47);
    std::wstring::~wstring(v46);
    std::wstring::~wstring(v45);
    v25 = v44;
  }
  else
  {
    v8 = ADPDatabase::GetDbPath((__int64)v47);
    v9 = std::operator+<wchar_t>(v46, v8, L"\\");
    v10 = std::operator+<wchar_t>(v45, v9, v2);
    v11 = std::operator+<wchar_t>(v44, v10, L"_unencrypted");
    v12 = std::operator+<wchar_t>(v48, v11, L".db");
    std::wstring::operator=(lpFileName, v12);
    std::wstring::~wstring(v48);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v45);
    std::wstring::~wstring(v46);
    std::wstring::~wstring(v47);
    v13 = (const WCHAR *)lpFileName;
    if ( si128.m128i_i64[1] > 7uLL )
      v13 = lpFileName[0];
    DeleteFileW(v13);
    v14 = ADPDatabase::GetDbPath((__int64)v48);
    v15 = std::operator+<wchar_t>(v44, v14, L"\\");
    v16 = std::operator+<wchar_t>(v45, v15, v2);
    v17 = std::operator+<wchar_t>(v46, v16, L"_unencrypted");
    v18 = std::operator+<wchar_t>(v47, v17, L".db-shm");
    std::wstring::operator=(lpFileName, v18);
    std::wstring::~wstring(v47);
    std::wstring::~wstring(v46);
    std::wstring::~wstring(v45);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v48);
    v19 = (const WCHAR *)lpFileName;
    if ( si128.m128i_i64[1] > 7uLL )
      v19 = lpFileName[0];
    DeleteFileW(v19);
    v20 = ADPDatabase::GetDbPath((__int64)v48);
    v21 = std::operator+<wchar_t>(v44, v20, L"\\");
    v22 = std::operator+<wchar_t>(v45, v21, v2);
    v23 = std::operator+<wchar_t>(v46, v22, L"_unencrypted");
    v24 = std::operator+<wchar_t>(v47, v23, L".db-wal");
    std::wstring::operator=(lpFileName, v24);
    std::wstring::~wstring(v47);
    std::wstring::~wstring(v46);
    std::wstring::~wstring(v45);
    std::wstring::~wstring(v44);
    v25 = v48;
  }
  std::wstring::~wstring(v25);
  v40 = (const WCHAR *)lpFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v40 = lpFileName[0];
  DeleteFileW(v40);
  std::wstring::~wstring(lpFileName);
}

```

## disassembly

```asm
0x180031f64  push    rbp
0x180031f66  push    rbx
0x180031f67  push    rsi
0x180031f68  push    rdi
0x180031f69  lea     rbp, [rsp-218h]
0x180031f71  sub     rsp, 318h
0x180031f78  mov     rax, cs:__security_cookie
0x180031f7f  xor     rax, rsp
0x180031f82  mov     [rbp+230h+var_30], rax
0x180031f89  mov     rsi, rcx
0x180031f8c  lea     rbx, [rcx+68h]
0x180031f90  cmp     qword ptr [rbx+18h], 7
0x180031f95  jbe     short loc_180031F9C
0x180031f97  mov     rdi, [rbx]
0x180031f9a  jmp     short loc_180031F9F
0x180031f9c  mov     rdi, rbx
0x180031f9f  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x180031fa4  mov     rcx, [rax+8]
0x180031fa8  mov     eax, [rcx]
0x180031faa  cmp     eax, 3
0x180031fad  jbe     short loc_180031FCA
0x180031faf  mov     [rsp+330h+var_300], rdi
0x180031fb4  lea     rax, [rsp+330h+var_300]
0x180031fb9  mov     [rsp+330h+var_310], rax
0x180031fbe  lea     rdx, word_180100572
0x180031fc5  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180031fca  xor     edx, edx; Val
0x180031fcc  mov     r8d, 1FEh; Size
0x180031fd2  lea     rcx, [rbp+230h+SubKey]; void *
0x180031fd6  call    memset_0
0x180031fdb  cmp     qword ptr [rbx+18h], 7
0x180031fe0  jbe     short loc_180031FE7
0x180031fe2  mov     rax, [rbx]
0x180031fe5  jmp     short loc_180031FEA
0x180031fe7  mov     rax, rbx
0x180031fea  mov     [rsp+330h+var_310], rax
0x180031fef  mov     r9, cs:off_1800CC760; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180031ff6  mov     r8d, 0FFh; int
0x180031ffc  lea     rdx, [rbp+230h+SubKey]; wchar_t *
0x180032000  mov     rcx, rsi; this
0x180032003  call    ?FillEncryptionKeyPath@ADPDatabase@@AEAAXPEB_WHZZ; ADPDatabase::FillEncryptionKeyPath(wchar_t const *,int,...)
0x180032008  lea     rdx, [rbp+230h+SubKey]; lpSubKey
0x18003200c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180032013  call    cs:__imp_RegDeleteTreeW
0x180032019  xorps   xmm0, xmm0
0x18003201c  movups  xmmword ptr [rsp+330h+lpFileName], xmm0
0x180032021  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180032029  movdqu  [rsp+330h+var_2E8], xmm1
0x18003202f  xor     eax, eax
0x180032031  mov     word ptr [rsp+330h+lpFileName], ax
0x180032036  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55934612@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55934612@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612> `wil::Feature<__WilFeatureTraits_Feature_55934612>::GetImpl(void)'::`2'::impl
0x18003203d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55934612@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612>::__private_IsEnabled(void)
0x180032042  test    al, al
0x180032044  jnz     loc_180032233
0x18003204a  lea     rcx, [rbp+230h+var_278]
0x18003204e  call    ?GetDbPath@ADPDatabase@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ADPDatabase::GetDbPath(void)
0x180032053  nop
0x180032054  lea     rdi, asc_1800ECD70; "\\"
0x18003205b  mov     r8, rdi
0x18003205e  mov     rdx, rax
0x180032061  lea     rcx, [rbp+230h+var_298]
0x180032065  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18003206a  nop
0x18003206b  mov     r8, rbx
0x18003206e  mov     rdx, rax
0x180032071  lea     rcx, [rsp+330h+var_2B8]
0x180032076  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18003207b  nop
0x18003207c  lea     rsi, aUnencrypted; "_unencrypted"
0x180032083  mov     r8, rsi
0x180032086  mov     rdx, rax
0x180032089  lea     rcx, [rsp+330h+var_2D8]
0x18003208e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180032093  nop
0x180032094  lea     r8, aDb; ".db"
0x18003209b  mov     rdx, rax
0x18003209e  lea     rcx, [rbp+230h+var_258]
0x1800320a2  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800320a7  mov     rdx, rax
0x1800320aa  lea     rcx, [rsp+330h+lpFileName]
0x1800320af  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800320b4  lea     rcx, [rbp+230h+var_258]
0x1800320b8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800320bd  nop
0x1800320be  lea     rcx, [rsp+330h+var_2D8]
0x1800320c3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800320c8  nop
0x1800320c9  lea     rcx, [rsp+330h+var_2B8]
0x1800320ce  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800320d3  nop
0x1800320d4  lea     rcx, [rbp+230h+var_298]
0x1800320d8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800320dd  nop
0x1800320de  lea     rcx, [rbp+230h+var_278]
0x1800320e2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800320e7  lea     rcx, [rsp+330h+lpFileName]
0x1800320ec  cmp     qword ptr [rsp+330h+var_2E8+8], 7
0x1800320f2  cmova   rcx, [rsp+330h+lpFileName]; lpFileName
0x1800320f8  call    cs:__imp_DeleteFileW
0x1800320fe  lea     rcx, [rbp+230h+var_258]
0x180032102  call    ?GetDbPath@ADPDatabase@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ADPDatabase::GetDbPath(void)
0x180032107  nop
0x180032108  mov     r8, rdi
0x18003210b  mov     rdx, rax
0x18003210e  lea     rcx, [rsp+330h+var_2D8]
0x180032113  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180032118  nop
0x180032119  mov     r8, rbx
0x18003211c  mov     rdx, rax
0x18003211f  lea     rcx, [rsp+330h+var_2B8]
0x180032124  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x180032129  nop
0x18003212a  mov     r8, rsi
0x18003212d  mov     rdx, rax
0x180032130  lea     rcx, [rbp+230h+var_298]
0x180032134  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180032139  nop
0x18003213a  lea     r8, aDbShm; ".db-shm"
0x180032141  mov     rdx, rax
0x180032144  lea     rcx, [rbp+230h+var_278]
0x180032148  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18003214d  mov     rdx, rax
0x180032150  lea     rcx, [rsp+330h+lpFileName]
0x180032155  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003215a  lea     rcx, [rbp+230h+var_278]
0x18003215e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032163  nop
0x180032164  lea     rcx, [rbp+230h+var_298]
0x180032168  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003216d  nop
0x18003216e  lea     rcx, [rsp+330h+var_2B8]
0x180032173  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032178  nop
0x180032179  lea     rcx, [rsp+330h+var_2D8]
0x18003217e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032183  nop
0x180032184  lea     rcx, [rbp+230h+var_258]
0x180032188  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003218d  lea     rcx, [rsp+330h+lpFileName]
0x180032192  cmp     qword ptr [rsp+330h+var_2E8+8], 7
0x180032198  cmova   rcx, [rsp+330h+lpFileName]; lpFileName
0x18003219e  call    cs:__imp_DeleteFileW
0x1800321a4  lea     rcx, [rbp+230h+var_258]
0x1800321a8  call    ?GetDbPath@ADPDatabase@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ADPDatabase::GetDbPath(void)
0x1800321ad  nop
0x1800321ae  mov     r8, rdi
0x1800321b1  mov     rdx, rax
0x1800321b4  lea     rcx, [rsp+330h+var_2D8]
0x1800321b9  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800321be  nop
0x1800321bf  mov     r8, rbx
0x1800321c2  mov     rdx, rax
0x1800321c5  lea     rcx, [rsp+330h+var_2B8]
0x1800321ca  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x1800321cf  nop
0x1800321d0  mov     r8, rsi
0x1800321d3  mov     rdx, rax
0x1800321d6  lea     rcx, [rbp+230h+var_298]
0x1800321da  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800321df  nop
0x1800321e0  lea     r8, aDbWal; ".db-wal"
0x1800321e7  mov     rdx, rax
0x1800321ea  lea     rcx, [rbp+230h+var_278]
0x1800321ee  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800321f3  mov     rdx, rax
0x1800321f6  lea     rcx, [rsp+330h+lpFileName]
0x1800321fb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180032200  lea     rcx, [rbp+230h+var_278]
0x180032204  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032209  nop
0x18003220a  lea     rcx, [rbp+230h+var_298]
0x18003220e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032213  nop
0x180032214  lea     rcx, [rsp+330h+var_2B8]
0x180032219  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003221e  nop
0x18003221f  lea     rcx, [rsp+330h+var_2D8]
0x180032224  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032229  nop
0x18003222a  lea     rcx, [rbp+230h+var_258]
0x18003222e  jmp     loc_1800323C2
0x180032233  lea     rcx, [rsp+330h+var_2D8]
0x180032238  call    ?GetDbPath@ADPDatabase@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ADPDatabase::GetDbPath(void)
0x18003223d  nop
0x18003223e  lea     rdi, asc_1800ECD70; "\\"
0x180032245  mov     r8, rdi
0x180032248  mov     rdx, rax
0x18003224b  lea     rcx, [rsp+330h+var_2B8]
0x180032250  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180032255  nop
0x180032256  mov     r8, rbx
0x180032259  mov     rdx, rax
0x18003225c  lea     rcx, [rbp+230h+var_298]
0x180032260  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x180032265  nop
0x180032266  lea     r8, aDb; ".db"
0x18003226d  mov     rdx, rax
0x180032270  lea     rcx, [rbp+230h+var_278]
0x180032274  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180032279  mov     rdx, rax
0x18003227c  lea     rcx, [rsp+330h+lpFileName]
0x180032281  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180032286  lea     rcx, [rbp+230h+var_278]
0x18003228a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003228f  nop
0x180032290  lea     rcx, [rbp+230h+var_298]
0x180032294  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032299  nop
0x18003229a  lea     rcx, [rsp+330h+var_2B8]
0x18003229f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800322a4  nop
0x1800322a5  lea     rcx, [rsp+330h+var_2D8]
0x1800322aa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800322af  lea     rcx, [rsp+330h+lpFileName]
0x1800322b4  cmp     qword ptr [rsp+330h+var_2E8+8], 7
0x1800322ba  cmova   rcx, [rsp+330h+lpFileName]; lpFileName
0x1800322c0  call    cs:__imp_DeleteFileW
0x1800322c6  lea     rcx, [rsp+330h+var_2D8]
0x1800322cb  call    ?GetDbPath@ADPDatabase@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ADPDatabase::GetDbPath(void)
0x1800322d0  nop
0x1800322d1  mov     r8, rdi
0x1800322d4  mov     rdx, rax
0x1800322d7  lea     rcx, [rsp+330h+var_2B8]
0x1800322dc  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800322e1  nop
0x1800322e2  mov     r8, rbx
0x1800322e5  mov     rdx, rax
0x1800322e8  lea     rcx, [rbp+230h+var_298]
0x1800322ec  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x1800322f1  nop
0x1800322f2  lea     r8, aDbShm; ".db-shm"
0x1800322f9  mov     rdx, rax
0x1800322fc  lea     rcx, [rbp+230h+var_278]
0x180032300  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180032305  mov     rdx, rax
0x180032308  lea     rcx, [rsp+330h+lpFileName]
0x18003230d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180032312  lea     rcx, [rbp+230h+var_278]
0x180032316  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003231b  nop
0x18003231c  lea     rcx, [rbp+230h+var_298]
0x180032320  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032325  nop
0x180032326  lea     rcx, [rsp+330h+var_2B8]
0x18003232b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032330  nop
0x180032331  lea     rcx, [rsp+330h+var_2D8]
0x180032336  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003233b  lea     rcx, [rsp+330h+lpFileName]
0x180032340  cmp     qword ptr [rsp+330h+var_2E8+8], 7
0x180032346  cmova   rcx, [rsp+330h+lpFileName]; lpFileName
0x18003234c  call    cs:__imp_DeleteFileW
0x180032352  lea     rcx, [rsp+330h+var_2D8]
0x180032357  call    ?GetDbPath@ADPDatabase@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ADPDatabase::GetDbPath(void)
0x18003235c  nop
0x18003235d  mov     r8, rdi
0x180032360  mov     rdx, rax
0x180032363  lea     rcx, [rsp+330h+var_2B8]
0x180032368  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18003236d  nop
0x18003236e  mov     r8, rbx
0x180032371  mov     rdx, rax
0x180032374  lea     rcx, [rbp+230h+var_298]
0x180032378  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18003237d  nop
0x18003237e  lea     r8, aDbWal; ".db-wal"
0x180032385  mov     rdx, rax
0x180032388  lea     rcx, [rbp+230h+var_278]
0x18003238c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180032391  mov     rdx, rax
0x180032394  lea     rcx, [rsp+330h+lpFileName]
0x180032399  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003239e  lea     rcx, [rbp+230h+var_278]
0x1800323a2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800323a7  nop
0x1800323a8  lea     rcx, [rbp+230h+var_298]
0x1800323ac  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800323b1  nop
0x1800323b2  lea     rcx, [rsp+330h+var_2B8]
0x1800323b7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800323bc  nop
0x1800323bd  lea     rcx, [rsp+330h+var_2D8]
0x1800323c2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800323c7  lea     rcx, [rsp+330h+lpFileName]
0x1800323cc  cmp     qword ptr [rsp+330h+var_2E8+8], 7
0x1800323d2  cmova   rcx, [rsp+330h+lpFileName]; lpFileName
0x1800323d8  call    cs:__imp_DeleteFileW
0x1800323de  nop
0x1800323df  lea     rcx, [rsp+330h+lpFileName]
0x1800323e4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800323e9  mov     rcx, [rbp+230h+var_30]
0x1800323f0  xor     rcx, rsp; StackCookie
0x1800323f3  call    __security_check_cookie
0x1800323f8  add     rsp, 318h
0x1800323ff  pop     rdi
0x180032400  pop     rsi
0x180032401  pop     rbx
0x180032402  pop     rbp
0x180032403  retn
```
