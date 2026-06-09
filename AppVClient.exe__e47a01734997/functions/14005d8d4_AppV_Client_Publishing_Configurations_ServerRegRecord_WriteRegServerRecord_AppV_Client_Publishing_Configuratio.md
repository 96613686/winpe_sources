# AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRecord(AppV::Client::Publishing::Configurations::ServerProperties const &)

- ea: `0x14005d8d4`
- end: `0x14005df37`
- name: `?WriteRegServerRecord@ServerRegRecord@Configurations@Publishing@Client@AppV@@CA_KAEBUServerProperties@2345@@Z`
- size: `1635`
- prototype: `__int64 __fastcall(const struct AppV::Client::Publishing::Configurations::ServerProperties *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005bde4`
- `0x14005d688`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140006a94`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14001d488`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14005bf98`
- `0x14005d8d4`
- `0x14005df40`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005de5f`
- `ADVAPI32!RegCloseKey` at `0x14005decc`
- `ADVAPI32!RegCloseKey` at `0x14005df11`
- `ADVAPI32!RegCloseKey` at `0x14005de5f`
- `ADVAPI32!RegCloseKey` at `0x14005decc`
- `ADVAPI32!RegCloseKey` at `0x14005df11`
- `ADVAPI32!RegSetKeyValueW` at `0x14005dafc`
- `ADVAPI32!RegSetKeyValueW` at `0x14005dcab`
- `ADVAPI32!RegSetKeyValueW` at `0x14005dafc`
- `ADVAPI32!RegSetKeyValueW` at `0x14005dcab`
- `ADVAPI32!RegCreateKeyExW` at `0x14005d95a`
- `ADVAPI32!RegCreateKeyExW` at `0x14005d95a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005da62`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005dc1b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005ddca`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005da62`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005dc1b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005ddca`

## string_xrefs

- `0x14005da5b`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005da72`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005dc14`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005dc2b`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005ddc3`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005ddda`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005d99c`: `Couldn't create registry key.\n winerr = %1%\n sub key: %2%`
- `0x14005d96c`: `AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRecord`
- `0x14005db0e`: `AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRecord`
- `0x14005dcbd`: `AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRecord`
- `0x14005db3f`: `Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%`
- `0x14005dcee`: `Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%`

## pseudocode

```c
__int64 __fastcall AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRecord(
        const struct AppV::Client::Publishing::Configurations::ServerProperties *a1)
{
  const WCHAR *v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rax
  LPCWSTR *v6; // rcx
  __int64 v7; // rbx
  char *v8; // rax
  const char *v9; // rax
  unsigned __int64 FileId; // rbx
  __int64 v11; // rax
  __int64 v12; // rbx
  unsigned __int64 v13; // rax
  DWORD v14; // ecx
  _QWORD *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  LPCWSTR *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rbx
  char *v22; // rax
  const char *v23; // rax
  unsigned __int64 v24; // rax
  DWORD v25; // ecx
  _QWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  LPCWSTR *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rbx
  char *v33; // rax
  const char *v34; // rax
  __int64 v35; // rdi
  unsigned int Key; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey[3]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR *v39; // [rsp+70h] [rbp-90h] BYREF
  __int128 v40; // [rsp+78h] [rbp-88h] BYREF
  __int128 v41; // [rsp+88h] [rbp-78h]
  LPCWSTR lpSubKey[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v43; // [rsp+B0h] [rbp-50h]
  __int128 v44; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v45; // [rsp+C8h] [rbp-38h]
  _BYTE v46[32]; // [rsp+D8h] [rbp-28h] BYREF
  int v47; // [rsp+F8h] [rbp-8h]
  _QWORD v48[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v49[32]; // [rsp+110h] [rbp+10h] BYREF

  AppV::Client::Publishing::Configurations::ServerRegRecord::GetRegServerKeyPath((__int64)lpSubKey, 0, *(_DWORD *)a1);
  memset(hKey, 0, sizeof(hKey));
  v2 = (const WCHAR *)lpSubKey;
  if ( v43 > 7 )
    v2 = lpSubKey[0];
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0, 0, 0x20006u, 0, hKey, 0);
  if ( Key )
  {
    std::string::string(v46, "AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRecord");
    v47 = 310;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v40 = 0;
    v41 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &v40,
      L"Couldn't create registry key.\n winerr = %1%\n sub key: %2%",
      57);
    v4 = AppV::Log::fmt(v3, v48, &v40);
    v5 = AppV::LogFormatter::operator%<long>(v4, &Key);
    v6 = lpSubKey;
    if ( v43 > 7 )
      v6 = (LPCWSTR *)lpSubKey[0];
    v39 = v6;
    v7 = AppV::LogFormatter::operator%<wchar_t const *>(v5, &v39);
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v44, L"Publishing", 10);
    AppV::DecoratedLog::operator()(v46, 1, &v44, v7);
    std::wstring::~wstring(&v44);
    v48[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v49);
    std::wstring::~wstring(&v40);
    std::string::~string(v46);
    v8 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v8 )
      v9 = v8 + 1;
    else
      v9 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v9);
    v11 = 0x262700000000LL;
LABEL_10:
    v12 = v11 | Key | (FileId << 52);
    goto LABEL_39;
  }
  v13 = *((_QWORD *)a1 + 3) + 1LL;
  if ( v13 > 0xFFFFFFFF )
    goto LABEL_45;
  v14 = 2 * v13;
  if ( !is_mul_ok(2u, v13) )
    goto LABEL_45;
  v15 = (_QWORD *)((char *)a1 + 8);
  if ( *((_QWORD *)a1 + 4) > 7u )
    v15 = (_QWORD *)*v15;
  Key = RegSetKeyValueW(hKey[0], 0, L"Name", 1u, v15, v14);
  if ( Key )
  {
    std::string::string(v46, "AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRecord");
    v47 = 324;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &v44,
      L"Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      77);
    v17 = AppV::Log::fmt(v16, v48, &v44);
    v18 = AppV::LogFormatter::operator%<long>(v17, &Key);
    v19 = lpSubKey;
    if ( v43 > 7 )
      v19 = (LPCWSTR *)lpSubKey[0];
    v39 = v19;
    v20 = AppV::LogFormatter::operator%<wchar_t const *>(v18, &v39);
    v21 = AppV::LogFormatter::operator%<wchar_t const *>(v20, off_140072470);
    v40 = 0;
    v41 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v40, L"Publishing", 10);
    AppV::DecoratedLog::operator()(v46, 1, &v40, v21);
    std::wstring::~wstring(&v40);
    v48[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v49);
    std::wstring::~wstring(&v44);
    std::string::~string(v46);
    v22 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v22 )
      v23 = v22 + 1;
    else
      v23 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v23);
    v11 = 0x282700000000LL;
    goto LABEL_10;
  }
  if ( *((_QWORD *)a1 + 7) > 0xFFFFFFFF
    || (v24 = *((unsigned int *)a1 + 14) + 1LL, v24 > 0xFFFFFFFF)
    || (v25 = 2 * v24, !is_mul_ok(2u, v24)) )
  {
LABEL_45:
    msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow();
  }
  v26 = (_QWORD *)((char *)a1 + 40);
  if ( *((_QWORD *)a1 + 8) > 7u )
    v26 = (_QWORD *)*v26;
  Key = RegSetKeyValueW(hKey[0], 0, L"URL", 1u, v26, v25);
  if ( Key )
  {
    std::string::string(v46, "AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRecord");
    v47 = 337;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &v44,
      L"Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      77);
    v28 = AppV::Log::fmt(v27, v48, &v44);
    v29 = AppV::LogFormatter::operator%<long>(v28, &Key);
    v30 = lpSubKey;
    if ( v43 > 7 )
      v30 = (LPCWSTR *)lpSubKey[0];
    v39 = v30;
    v31 = AppV::LogFormatter::operator%<wchar_t const *>(v29, &v39);
    v32 = AppV::LogFormatter::operator%<wchar_t const *>(v31, off_140072478);
    v40 = 0;
    v41 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v40, L"Publishing", 10);
    AppV::DecoratedLog::operator()(v46, 1, &v40, v32);
    std::wstring::~wstring(&v40);
    v48[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v49);
    std::wstring::~wstring(&v44);
    std::string::~string(v46);
    v33 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v33 )
      v34 = v33 + 1;
    else
      v34 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v34);
    v11 = 0x2A2700000000LL;
    goto LABEL_10;
  }
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v40, L"Global", 6);
  v35 = AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy(hKey[0]);
  std::wstring::~wstring(&v40);
  if ( (v35 & 0x8000000000LL) == 0 )
  {
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v12 = v35;
    goto LABEL_41;
  }
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v40, L"User", 4);
  v12 = AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy(hKey[0]);
  std::wstring::~wstring(&v40);
  if ( (v12 & 0x8000000000LL) == 0 )
  {
LABEL_39:
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
LABEL_41:
    std::wstring::~wstring(lpSubKey);
    return v12;
  }
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
  }
  std::wstring::~wstring(lpSubKey);
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14005d8d4  mov     [rsp-8+arg_8], rbx
0x14005d8d9  mov     [rsp-8+arg_10], rsi
0x14005d8de  push    rbp
0x14005d8df  push    rdi
0x14005d8e0  push    r14
0x14005d8e2  lea     rbp, [rsp-40h]
0x14005d8e7  sub     rsp, 140h
0x14005d8ee  mov     rax, cs:__security_cookie
0x14005d8f5  xor     rax, rsp
0x14005d8f8  mov     [rbp+50h+var_20], rax
0x14005d8fc  mov     rbx, rcx
0x14005d8ff  mov     r8d, [rcx]
0x14005d902  xor     edx, edx
0x14005d904  lea     rcx, [rbp+50h+lpSubKey]
0x14005d908  call    ?GetRegServerKeyPath@ServerRegRecord@Configurations@Publishing@Client@AppV@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NI@Z; AppV::Client::Publishing::Configurations::ServerRegRecord::GetRegServerKeyPath(bool,uint)
0x14005d90d  nop
0x14005d90e  xor     esi, esi
0x14005d910  mov     [rsp+150h+hKey], rsi
0x14005d915  mov     [rsp+150h+var_F0], rsi
0x14005d91a  mov     [rsp+150h+var_E8], rsi
0x14005d91f  lea     rdx, [rbp+50h+lpSubKey]
0x14005d923  cmp     [rbp+50h+var_A0], 7
0x14005d928  cmova   rdx, [rbp+50h+lpSubKey]; lpSubKey
0x14005d92d  mov     [rsp+150h+lpdwDisposition], rsi; lpdwDisposition
0x14005d932  lea     rax, [rsp+150h+hKey]
0x14005d937  mov     [rsp+150h+phkResult], rax; phkResult
0x14005d93c  mov     [rsp+150h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x14005d941  mov     [rsp+150h+samDesired], 20006h; samDesired
0x14005d949  mov     [rsp+150h+dwOptions], esi; dwOptions
0x14005d94d  xor     r9d, r9d; lpClass
0x14005d950  xor     r8d, r8d; Reserved
0x14005d953  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005d95a  call    cs:__imp_RegCreateKeyExW
0x14005d960  mov     [rsp+150h+var_100], eax
0x14005d964  test    eax, eax
0x14005d966  jz      loc_14005DAA8
0x14005d96c  lea     rdx, aAppvClientPubl_2; "AppV::Client::Publishing::Configuration"...
0x14005d973  lea     rcx, [rbp+50h+var_78]
0x14005d977  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005d97c  mov     [rbp+50h+var_58], 136h
0x14005d983  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005d988  xorps   xmm0, xmm0
0x14005d98b  movups  [rsp+150h+var_D8], xmm0
0x14005d990  xorps   xmm1, xmm1
0x14005d993  movdqu  [rbp+50h+var_C8], xmm1
0x14005d998  lea     r8d, [rsi+39h]
0x14005d99c  lea     rdx, aCouldnTCreateR; "Couldn't create registry key.\n winerr "...
0x14005d9a3  lea     rcx, [rsp+150h+var_D8]
0x14005d9a8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005d9ad  nop
0x14005d9ae  lea     r8, [rsp+150h+var_D8]
0x14005d9b3  lea     rdx, [rbp+50h+var_50]
0x14005d9b7  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005d9bc  nop
0x14005d9bd  lea     rdx, [rsp+150h+var_100]
0x14005d9c2  mov     rcx, rax
0x14005d9c5  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005d9ca  lea     rcx, [rbp+50h+lpSubKey]
0x14005d9ce  cmp     [rbp+50h+var_A0], 7
0x14005d9d3  cmova   rcx, [rbp+50h+lpSubKey]
0x14005d9d8  mov     [rsp+150h+var_E0], rcx
0x14005d9dd  lea     rdx, [rsp+150h+var_E0]
0x14005d9e2  mov     rcx, rax
0x14005d9e5  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005d9ea  mov     rbx, rax
0x14005d9ed  xorps   xmm0, xmm0
0x14005d9f0  movups  [rbp+50h+var_98], xmm0
0x14005d9f4  xorps   xmm1, xmm1
0x14005d9f7  movdqu  [rbp+50h+var_88], xmm1
0x14005d9fc  lea     r8d, [rsi+0Ah]
0x14005da00  lea     rdx, aPublishing; "Publishing"
0x14005da07  lea     rcx, [rbp+50h+var_98]
0x14005da0b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005da10  nop
0x14005da11  mov     r9, rbx
0x14005da14  lea     r8, [rbp+50h+var_98]
0x14005da18  lea     edx, [rsi+1]
0x14005da1b  lea     rcx, [rbp+50h+var_78]
0x14005da1f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005da24  nop
0x14005da25  lea     rcx, [rbp+50h+var_98]
0x14005da29  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005da2e  nop
0x14005da2f  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005da36  mov     [rbp+50h+var_50], rax
0x14005da3a  lea     rcx, [rbp+50h+var_40]
0x14005da3e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005da43  nop
0x14005da44  lea     rcx, [rsp+150h+var_D8]
0x14005da49  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005da4e  nop
0x14005da4f  lea     rcx, [rbp+50h+var_78]
0x14005da53  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005da58  lea     edx, [rsi+5Ch]; Ch
0x14005da5b  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005da62  call    cs:__imp_strrchr
0x14005da68  test    rax, rax
0x14005da6b  jz      short loc_14005DA72
0x14005da6d  inc     rax
0x14005da70  jmp     short loc_14005DA79
0x14005da72  lea     rax, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005da79  mov     rdx, rax; char *
0x14005da7c  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005da83  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005da88  mov     rbx, rax
0x14005da8b  mov     rax, 262700000000h
0x14005da95  mov     ecx, [rsp+150h+var_100]
0x14005da99  shl     rbx, 34h
0x14005da9d  or      rbx, rcx
0x14005daa0  or      rbx, rax
0x14005daa3  jmp     loc_14005DEC2
0x14005daa8  mov     rax, [rbx+18h]
0x14005daac  inc     rax
0x14005daaf  mov     edi, 0FFFFFFFFh
0x14005dab4  cmp     rax, rdi
0x14005dab7  ja      loc_14005DF31
0x14005dabd  mov     ecx, eax
0x14005dabf  add     rcx, rcx
0x14005dac2  mov     rax, rcx
0x14005dac5  shr     rax, 20h
0x14005dac9  test    eax, eax
0x14005dacb  jnz     loc_14005DF31
0x14005dad1  lea     rax, [rbx+8]
0x14005dad5  cmp     qword ptr [rax+18h], 7
0x14005dada  jbe     short loc_14005DADF
0x14005dadc  mov     rax, [rax]
0x14005dadf  mov     [rsp+150h+samDesired], ecx; cbData
0x14005dae3  mov     qword ptr [rsp+150h+dwOptions], rax; lpData
0x14005dae8  mov     r9d, 1; dwType
0x14005daee  lea     r8, ValueName; "Name"
0x14005daf5  xor     edx, edx; lpSubKey
0x14005daf7  mov     rcx, [rsp+150h+hKey]; hKey
0x14005dafc  call    cs:__imp_RegSetKeyValueW
0x14005db02  mov     [rsp+150h+var_100], eax
0x14005db06  test    eax, eax
0x14005db08  jz      loc_14005DC53
0x14005db0e  lea     rdx, aAppvClientPubl_2; "AppV::Client::Publishing::Configuration"...
0x14005db15  lea     rcx, [rbp+50h+var_78]
0x14005db19  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005db1e  mov     [rbp+50h+var_58], 144h
0x14005db25  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005db2a  xorps   xmm0, xmm0
0x14005db2d  movups  [rbp+50h+var_98], xmm0
0x14005db31  xorps   xmm1, xmm1
0x14005db34  movdqu  [rbp+50h+var_88], xmm1
0x14005db39  mov     r8d, 4Dh ; 'M'
0x14005db3f  lea     rdx, aCouldnTSetRegi; "Couldn't set registry key value.\n wine"...
0x14005db46  lea     rcx, [rbp+50h+var_98]
0x14005db4a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005db4f  nop
0x14005db50  lea     r8, [rbp+50h+var_98]
0x14005db54  lea     rdx, [rbp+50h+var_50]
0x14005db58  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005db5d  nop
0x14005db5e  lea     rdx, [rsp+150h+var_100]
0x14005db63  mov     rcx, rax
0x14005db66  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005db6b  lea     rcx, [rbp+50h+lpSubKey]
0x14005db6f  cmp     [rbp+50h+var_A0], 7
0x14005db74  cmova   rcx, [rbp+50h+lpSubKey]
0x14005db79  mov     [rsp+150h+var_E0], rcx
0x14005db7e  lea     rdx, [rsp+150h+var_E0]
0x14005db83  mov     rcx, rax
0x14005db86  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005db8b  lea     rdx, off_140072470; "Name"
0x14005db92  mov     rcx, rax
0x14005db95  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005db9a  mov     rbx, rax
0x14005db9d  xorps   xmm0, xmm0
0x14005dba0  movups  [rsp+150h+var_D8], xmm0
0x14005dba5  xorps   xmm1, xmm1
0x14005dba8  movdqu  [rbp+50h+var_C8], xmm1
0x14005dbad  mov     r8d, 0Ah
0x14005dbb3  lea     rdx, aPublishing; "Publishing"
0x14005dbba  lea     rcx, [rsp+150h+var_D8]
0x14005dbbf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005dbc4  nop
0x14005dbc5  mov     r9, rbx
0x14005dbc8  lea     r8, [rsp+150h+var_D8]
0x14005dbcd  mov     edx, 1
0x14005dbd2  lea     rcx, [rbp+50h+var_78]
0x14005dbd6  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005dbdb  nop
0x14005dbdc  lea     rcx, [rsp+150h+var_D8]
0x14005dbe1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005dbe6  nop
0x14005dbe7  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005dbee  mov     [rbp+50h+var_50], rax
0x14005dbf2  lea     rcx, [rbp+50h+var_40]
0x14005dbf6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005dbfb  nop
0x14005dbfc  lea     rcx, [rbp+50h+var_98]
0x14005dc00  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005dc05  nop
0x14005dc06  lea     rcx, [rbp+50h+var_78]
0x14005dc0a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005dc0f  mov     edx, 5Ch ; '\'; Ch
0x14005dc14  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005dc1b  call    cs:__imp_strrchr
0x14005dc21  test    rax, rax
0x14005dc24  jz      short loc_14005DC2B
0x14005dc26  inc     rax
0x14005dc29  jmp     short loc_14005DC32
0x14005dc2b  lea     rax, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005dc32  mov     rdx, rax; char *
0x14005dc35  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005dc3c  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005dc41  mov     rbx, rax
0x14005dc44  mov     rax, 282700000000h
0x14005dc4e  jmp     loc_14005DA95
0x14005dc53  cmp     [rbx+38h], rdi
0x14005dc57  ja      loc_14005DF31
0x14005dc5d  mov     eax, [rbx+38h]
0x14005dc60  inc     rax
0x14005dc63  cmp     rax, rdi
0x14005dc66  ja      loc_14005DF31
0x14005dc6c  mov     ecx, eax
0x14005dc6e  add     rcx, rcx
0x14005dc71  mov     rax, rcx
0x14005dc74  shr     rax, 20h
0x14005dc78  test    eax, eax
0x14005dc7a  jnz     loc_14005DF31
0x14005dc80  lea     rax, [rbx+28h]
0x14005dc84  cmp     qword ptr [rax+18h], 7
0x14005dc89  jbe     short loc_14005DC8E
0x14005dc8b  mov     rax, [rax]
0x14005dc8e  mov     [rsp+150h+samDesired], ecx; cbData
0x14005dc92  mov     qword ptr [rsp+150h+dwOptions], rax; lpData
0x14005dc97  mov     r9d, 1; dwType
0x14005dc9d  lea     r8, aUrl; "URL"
0x14005dca4  xor     edx, edx; lpSubKey
0x14005dca6  mov     rcx, [rsp+150h+hKey]; hKey
0x14005dcab  call    cs:__imp_RegSetKeyValueW
0x14005dcb1  mov     [rsp+150h+var_100], eax
0x14005dcb5  test    eax, eax
0x14005dcb7  jz      loc_14005DE02
0x14005dcbd  lea     rdx, aAppvClientPubl_2; "AppV::Client::Publishing::Configuration"...
0x14005dcc4  lea     rcx, [rbp+50h+var_78]
0x14005dcc8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005dccd  mov     [rbp+50h+var_58], 151h
0x14005dcd4  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005dcd9  xorps   xmm0, xmm0
0x14005dcdc  movups  [rbp+50h+var_98], xmm0
0x14005dce0  xorps   xmm1, xmm1
0x14005dce3  movdqu  [rbp+50h+var_88], xmm1
0x14005dce8  mov     r8d, 4Dh ; 'M'
0x14005dcee  lea     rdx, aCouldnTSetRegi; "Couldn't set registry key value.\n wine"...
0x14005dcf5  lea     rcx, [rbp+50h+var_98]
0x14005dcf9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005dcfe  nop
0x14005dcff  lea     r8, [rbp+50h+var_98]
0x14005dd03  lea     rdx, [rbp+50h+var_50]
0x14005dd07  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005dd0c  nop
0x14005dd0d  lea     rdx, [rsp+150h+var_100]
0x14005dd12  mov     rcx, rax
0x14005dd15  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005dd1a  lea     rcx, [rbp+50h+lpSubKey]
0x14005dd1e  cmp     [rbp+50h+var_A0], 7
0x14005dd23  cmova   rcx, [rbp+50h+lpSubKey]
0x14005dd28  mov     [rsp+150h+var_E0], rcx
0x14005dd2d  lea     rdx, [rsp+150h+var_E0]
0x14005dd32  mov     rcx, rax
0x14005dd35  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005dd3a  lea     rdx, off_140072478; "URL"
0x14005dd41  mov     rcx, rax
0x14005dd44  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005dd49  mov     rbx, rax
0x14005dd4c  xorps   xmm0, xmm0
0x14005dd4f  movups  [rsp+150h+var_D8], xmm0
0x14005dd54  xorps   xmm1, xmm1
0x14005dd57  movdqu  [rbp+50h+var_C8], xmm1
0x14005dd5c  mov     r8d, 0Ah
0x14005dd62  lea     rdx, aPublishing; "Publishing"
0x14005dd69  lea     rcx, [rsp+150h+var_D8]
0x14005dd6e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005dd73  nop
0x14005dd74  mov     r9, rbx
0x14005dd77  lea     r8, [rsp+150h+var_D8]
0x14005dd7c  mov     edx, 1
0x14005dd81  lea     rcx, [rbp+50h+var_78]
0x14005dd85  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005dd8a  nop
0x14005dd8b  lea     rcx, [rsp+150h+var_D8]
0x14005dd90  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005dd95  nop
0x14005dd96  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005dd9d  mov     [rbp+50h+var_50], rax
0x14005dda1  lea     rcx, [rbp+50h+var_40]
0x14005dda5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005ddaa  nop
0x14005ddab  lea     rcx, [rbp+50h+var_98]
0x14005ddaf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005ddb4  nop
0x14005ddb5  lea     rcx, [rbp+50h+var_78]
0x14005ddb9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005ddbe  mov     edx, 5Ch ; '\'; Ch
0x14005ddc3  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005ddca  call    cs:__imp_strrchr
0x14005ddd0  test    rax, rax
  ... truncated ...
```
