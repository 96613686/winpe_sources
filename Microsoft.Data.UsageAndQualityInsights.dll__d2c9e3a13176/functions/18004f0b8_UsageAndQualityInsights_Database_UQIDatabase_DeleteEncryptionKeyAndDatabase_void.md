# UsageAndQualityInsights::Database::UQIDatabase::DeleteEncryptionKeyAndDatabase(void)

- ea: `0x18004f0b8`
- end: `0x18004f3a5`
- name: `?DeleteEncryptionKeyAndDatabase@UQIDatabase@Database@UsageAndQualityInsights@@IEAAXXZ`
- size: `749`
- prototype: `void __fastcall(UsageAndQualityInsights::Database::UQIDatabase *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801051c8`
- `0x180105225`

## callees

- `0x1800033d0`
- `0x180003fb8`
- `0x18000eee0`
- `0x1800107b0`
- `0x180019b64`
- `0x18004e5d4`
- `0x18004e68c`
- `0x18004f0b8`
- `0x18004f40c`
- `0x18004f4ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004f14e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004f14e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004f21c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004f2c6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004f370`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004f21c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004f2c6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004f370`

## string_xrefs

- `0x18004f0f9`: `DeleteEncryptionKeyAndDatabase for: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall UsageAndQualityInsights::Database::UQIDatabase::DeleteEncryptionKeyAndDatabase(
        UsageAndQualityInsights::Database::UQIDatabase *this)
{
  char **v2; // rbx
  char *v3; // rdx
  char *v4; // rax
  __int64 DbPath; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  const WCHAR *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  const WCHAR *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  const WCHAR *v22; // rcx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-D0h] BYREF
  __m128i si128; // [rsp+40h] [rbp-C0h]
  _BYTE v25[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v28[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE Src[32]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR SubKey[256]; // [rsp+F0h] [rbp-10h] BYREF

  v2 = (char **)((char *)this + 40);
  if ( *((_QWORD *)this + 8) <= 7u )
    v3 = (char *)this + 40;
  else
    v3 = *v2;
  UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("DeleteEncryptionKeyAndDatabase for: %ws", v3);
  memset_0(SubKey, 0, 0x1FEu);
  if ( (unsigned __int64)v2[3] <= 7 )
    v4 = (char *)v2;
  else
    v4 = *v2;
  UsageAndQualityInsights::Database::UQIDatabase::FillEncryptionKeyPath(
    this,
    SubKey,
    255,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UsageAndQualityInsights\\Keys",
    v4);
  RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
  *(_OWORD *)lpFileName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpFileName[0]) = 0;
  DbPath = UsageAndQualityInsights::Database::UQIDatabase::GetDbPath(Src);
  v6 = std::operator+<wchar_t>(v28, DbPath, L"\\");
  v7 = std::operator+<wchar_t>(v27, v6, v2);
  v8 = std::operator+<wchar_t>(v26, v7, L"_unencrypted");
  v9 = std::operator+<wchar_t>(v25, v8, L".db");
  std::wstring::operator=(lpFileName, v9);
  std::wstring::~wstring(v25);
  std::wstring::~wstring(v26);
  std::wstring::~wstring(v27);
  std::wstring::~wstring(v28);
  std::wstring::~wstring(Src);
  v10 = (const WCHAR *)lpFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v10 = lpFileName[0];
  DeleteFileW(v10);
  v11 = UsageAndQualityInsights::Database::UQIDatabase::GetDbPath(v25);
  v12 = std::operator+<wchar_t>(v26, v11, L"\\");
  v13 = std::operator+<wchar_t>(v27, v12, v2);
  v14 = std::operator+<wchar_t>(v28, v13, L"_unencrypted");
  v15 = std::operator+<wchar_t>(Src, v14, L".db-shm");
  std::wstring::operator=(lpFileName, v15);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v28);
  std::wstring::~wstring(v27);
  std::wstring::~wstring(v26);
  std::wstring::~wstring(v25);
  v16 = (const WCHAR *)lpFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v16 = lpFileName[0];
  DeleteFileW(v16);
  v17 = UsageAndQualityInsights::Database::UQIDatabase::GetDbPath(v25);
  v18 = std::operator+<wchar_t>(v26, v17, L"\\");
  v19 = std::operator+<wchar_t>(v27, v18, v2);
  v20 = std::operator+<wchar_t>(v28, v19, L"_unencrypted");
  v21 = std::operator+<wchar_t>(Src, v20, L".db-wal");
  std::wstring::operator=(lpFileName, v21);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v28);
  std::wstring::~wstring(v27);
  std::wstring::~wstring(v26);
  std::wstring::~wstring(v25);
  v22 = (const WCHAR *)lpFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v22 = lpFileName[0];
  DeleteFileW(v22);
  std::wstring::~wstring(lpFileName);
}

```

## disassembly

```asm
0x18004f0b8  mov     [rsp-8+arg_8], rbx
0x18004f0bd  mov     [rsp-8+arg_10], rdi
0x18004f0c2  push    rbp
0x18004f0c3  lea     rbp, [rsp-200h]
0x18004f0cb  sub     rsp, 300h
0x18004f0d2  mov     rax, cs:__security_cookie
0x18004f0d9  xor     rax, rsp
0x18004f0dc  mov     [rbp+200h+var_10], rax
0x18004f0e3  mov     rdi, rcx
0x18004f0e6  lea     rbx, [rcx+28h]
0x18004f0ea  cmp     qword ptr [rbx+18h], 7
0x18004f0ef  jbe     short loc_18004F0F6
0x18004f0f1  mov     rdx, [rbx]
0x18004f0f4  jmp     short loc_18004F0F9
0x18004f0f6  mov     rdx, rbx
0x18004f0f9  lea     rcx, aDeleteencrypti; "DeleteEncryptionKeyAndDatabase for: %ws"
0x18004f100  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x18004f105  xor     edx, edx; Val
0x18004f107  mov     r8d, 1FEh; Size
0x18004f10d  lea     rcx, [rbp+200h+SubKey]; void *
0x18004f111  call    memset_0
0x18004f116  cmp     qword ptr [rbx+18h], 7
0x18004f11b  jbe     short loc_18004F122
0x18004f11d  mov     rax, [rbx]
0x18004f120  jmp     short loc_18004F125
0x18004f122  mov     rax, rbx
0x18004f125  mov     [rsp+300h+var_2E0], rax
0x18004f12a  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004f131  mov     r8d, 0FFh; int
0x18004f137  lea     rdx, [rbp+200h+SubKey]; wchar_t *
0x18004f13b  mov     rcx, rdi; this
0x18004f13e  call    ?FillEncryptionKeyPath@UQIDatabase@Database@UsageAndQualityInsights@@IEAAXPEB_WHZZ; UsageAndQualityInsights::Database::UQIDatabase::FillEncryptionKeyPath(wchar_t const *,int,...)
0x18004f143  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x18004f147  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004f14e  call    cs:__imp_RegDeleteTreeW
0x18004f154  xorps   xmm0, xmm0
0x18004f157  movups  xmmword ptr [rsp+300h+lpFileName], xmm0
0x18004f15c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004f164  movdqu  [rsp+300h+var_2C0], xmm1
0x18004f16a  xor     eax, eax
0x18004f16c  mov     word ptr [rsp+300h+lpFileName], ax
0x18004f171  lea     rcx, [rbp+200h+Src]; Src
0x18004f175  call    ?GetDbPath@UQIDatabase@Database@UsageAndQualityInsights@@KA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UsageAndQualityInsights::Database::UQIDatabase::GetDbPath(void)
0x18004f17a  nop
0x18004f17b  lea     r8, asc_18012C1F0; "\\"
0x18004f182  mov     rdx, rax
0x18004f185  lea     rcx, [rbp+200h+var_250]
0x18004f189  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f18e  nop
0x18004f18f  mov     r8, rbx
0x18004f192  mov     rdx, rax
0x18004f195  lea     rcx, [rbp+200h+var_270]
0x18004f199  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18004f19e  nop
0x18004f19f  lea     rdi, aUnencrypted; "_unencrypted"
0x18004f1a6  mov     r8, rdi
0x18004f1a9  mov     rdx, rax
0x18004f1ac  lea     rcx, [rsp+300h+var_290]
0x18004f1b1  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f1b6  nop
0x18004f1b7  lea     r8, aDb; ".db"
0x18004f1be  mov     rdx, rax
0x18004f1c1  lea     rcx, [rsp+300h+var_2B0]
0x18004f1c6  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f1cb  mov     rdx, rax
0x18004f1ce  lea     rcx, [rsp+300h+lpFileName]
0x18004f1d3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004f1d8  lea     rcx, [rsp+300h+var_2B0]; void *
0x18004f1dd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f1e2  nop
0x18004f1e3  lea     rcx, [rsp+300h+var_290]; void *
0x18004f1e8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f1ed  nop
0x18004f1ee  lea     rcx, [rbp+200h+var_270]; void *
0x18004f1f2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f1f7  nop
0x18004f1f8  lea     rcx, [rbp+200h+var_250]; void *
0x18004f1fc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f201  nop
0x18004f202  lea     rcx, [rbp+200h+Src]; void *
0x18004f206  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f20b  lea     rcx, [rsp+300h+lpFileName]
0x18004f210  cmp     qword ptr [rsp+300h+var_2C0+8], 7
0x18004f216  cmova   rcx, [rsp+300h+lpFileName]; lpFileName
0x18004f21c  call    cs:__imp_DeleteFileW
0x18004f222  lea     rcx, [rsp+300h+var_2B0]; Src
0x18004f227  call    ?GetDbPath@UQIDatabase@Database@UsageAndQualityInsights@@KA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UsageAndQualityInsights::Database::UQIDatabase::GetDbPath(void)
0x18004f22c  nop
0x18004f22d  lea     r8, asc_18012C1F0; "\\"
0x18004f234  mov     rdx, rax
0x18004f237  lea     rcx, [rsp+300h+var_290]
0x18004f23c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f241  nop
0x18004f242  mov     r8, rbx
0x18004f245  mov     rdx, rax
0x18004f248  lea     rcx, [rbp+200h+var_270]
0x18004f24c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18004f251  nop
0x18004f252  mov     r8, rdi
0x18004f255  mov     rdx, rax
0x18004f258  lea     rcx, [rbp+200h+var_250]
0x18004f25c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f261  nop
0x18004f262  lea     r8, aDbShm; ".db-shm"
0x18004f269  mov     rdx, rax
0x18004f26c  lea     rcx, [rbp+200h+Src]
0x18004f270  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f275  mov     rdx, rax
0x18004f278  lea     rcx, [rsp+300h+lpFileName]
0x18004f27d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004f282  lea     rcx, [rbp+200h+Src]; void *
0x18004f286  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f28b  nop
0x18004f28c  lea     rcx, [rbp+200h+var_250]; void *
0x18004f290  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f295  nop
0x18004f296  lea     rcx, [rbp+200h+var_270]; void *
0x18004f29a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f29f  nop
0x18004f2a0  lea     rcx, [rsp+300h+var_290]; void *
0x18004f2a5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f2aa  nop
0x18004f2ab  lea     rcx, [rsp+300h+var_2B0]; void *
0x18004f2b0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f2b5  lea     rcx, [rsp+300h+lpFileName]
0x18004f2ba  cmp     qword ptr [rsp+300h+var_2C0+8], 7
0x18004f2c0  cmova   rcx, [rsp+300h+lpFileName]; lpFileName
0x18004f2c6  call    cs:__imp_DeleteFileW
0x18004f2cc  lea     rcx, [rsp+300h+var_2B0]; Src
0x18004f2d1  call    ?GetDbPath@UQIDatabase@Database@UsageAndQualityInsights@@KA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UsageAndQualityInsights::Database::UQIDatabase::GetDbPath(void)
0x18004f2d6  nop
0x18004f2d7  lea     r8, asc_18012C1F0; "\\"
0x18004f2de  mov     rdx, rax
0x18004f2e1  lea     rcx, [rsp+300h+var_290]
0x18004f2e6  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f2eb  nop
0x18004f2ec  mov     r8, rbx
0x18004f2ef  mov     rdx, rax
0x18004f2f2  lea     rcx, [rbp+200h+var_270]
0x18004f2f6  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18004f2fb  nop
0x18004f2fc  mov     r8, rdi
0x18004f2ff  mov     rdx, rax
0x18004f302  lea     rcx, [rbp+200h+var_250]
0x18004f306  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f30b  nop
0x18004f30c  lea     r8, aDbWal; ".db-wal"
0x18004f313  mov     rdx, rax
0x18004f316  lea     rcx, [rbp+200h+Src]
0x18004f31a  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f31f  mov     rdx, rax
0x18004f322  lea     rcx, [rsp+300h+lpFileName]
0x18004f327  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004f32c  lea     rcx, [rbp+200h+Src]; void *
0x18004f330  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f335  nop
0x18004f336  lea     rcx, [rbp+200h+var_250]; void *
0x18004f33a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f33f  nop
0x18004f340  lea     rcx, [rbp+200h+var_270]; void *
0x18004f344  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f349  nop
0x18004f34a  lea     rcx, [rsp+300h+var_290]; void *
0x18004f34f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f354  nop
0x18004f355  lea     rcx, [rsp+300h+var_2B0]; void *
0x18004f35a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f35f  lea     rcx, [rsp+300h+lpFileName]
0x18004f364  cmp     qword ptr [rsp+300h+var_2C0+8], 7
0x18004f36a  cmova   rcx, [rsp+300h+lpFileName]; lpFileName
0x18004f370  call    cs:__imp_DeleteFileW
0x18004f376  nop
0x18004f377  lea     rcx, [rsp+300h+lpFileName]; void *
0x18004f37c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f381  mov     rcx, [rbp+200h+var_10]
0x18004f388  xor     rcx, rsp; StackCookie
0x18004f38b  call    __security_check_cookie
0x18004f390  lea     r11, [rsp+300h+var_s0]
0x18004f398  mov     rbx, [r11+18h]
0x18004f39c  mov     rdi, [r11+20h]
0x18004f3a0  mov     rsp, r11
0x18004f3a3  pop     rbp
0x18004f3a4  retn
```
