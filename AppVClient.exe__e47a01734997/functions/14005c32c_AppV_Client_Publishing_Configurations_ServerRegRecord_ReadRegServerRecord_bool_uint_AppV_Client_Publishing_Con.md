# AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRecord(bool,uint,AppV::Client::Publishing::Configurations::ServerProperties &,bool &)

- ea: `0x14005c32c`
- end: `0x14005c9dd`
- name: `?ReadRegServerRecord@ServerRegRecord@Configurations@Publishing@Client@AppV@@CA_K_NIAEAUServerProperties@2345@AEA_N@Z`
- size: `1713`
- prototype: `__int64 __fastcall(char, __int64, struct AppV::Client::Publishing::Configurations::ServerProperties *, bool *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005c06c`
- `0x14005d298`
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
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x140040698`
- `0x14005bf98`
- `0x14005c32c`
- `0x14005c9e4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14005c3a4`
- `ADVAPI32!RegOpenKeyExW` at `0x14005c3a4`
- `ADVAPI32!RegCloseKey` at `0x14005c6f0`
- `ADVAPI32!RegCloseKey` at `0x14005c930`
- `ADVAPI32!RegCloseKey` at `0x14005c9a5`
- `ADVAPI32!RegCloseKey` at `0x14005c6f0`
- `ADVAPI32!RegCloseKey` at `0x14005c930`
- `ADVAPI32!RegCloseKey` at `0x14005c9a5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005c4c9`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005c6a1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005c89c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005c4c9`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005c6a1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005c89c`

## string_xrefs

- `0x14005c4c2`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005c4d9`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005c69a`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005c6b1`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005c895`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005c8ac`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005c3fd`: `Couldn't open registry key.\n winerr = %1%\n sub key: %2%`
- `0x14005c3cc`: `AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRecord`
- `0x14005c595`: `AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRecord`
- `0x14005c78a`: `AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRecord`
- `0x14005c5c5`: `Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%`
- `0x14005c7bc`: `Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRecord(
        char a1,
        __int64 a2,
        struct AppV::Client::Publishing::Configurations::ServerProperties *a3,
        bool *a4)
{
  int v6; // r14d
  __int64 v8; // r8
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  LPCWSTR *v14; // rcx
  __int64 v15; // rbx
  char *v16; // rax
  const char *v17; // rax
  unsigned __int64 FileId; // rbx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  LPCWSTR *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rbx
  char *v26; // rax
  const char *v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  LPCWSTR *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rbx
  char *v35; // rax
  const char *v36; // rax
  __int64 RegServerRefreshPolicy; // rdi
  unsigned int v39; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR *v41; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v42; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v43; // [rsp+68h] [rbp-98h]
  __int128 v44; // [rsp+78h] [rbp-88h] BYREF
  __int128 v45; // [rsp+88h] [rbp-78h]
  LPCWSTR lpSubKey[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v47; // [rsp+B0h] [rbp-50h]
  _BYTE v48[32]; // [rsp+B8h] [rbp-48h] BYREF
  int v49; // [rsp+D8h] [rbp-28h]
  _QWORD v50[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v51[32]; // [rsp+F0h] [rbp-10h] BYREF

  v6 = a2;
  v8 = (unsigned int)a2;
  LOBYTE(a2) = a1;
  AppV::Client::Publishing::Configurations::ServerRegRecord::GetRegServerKeyPath(lpSubKey, a2, v8);
  memset(hKey, 0, sizeof(hKey));
  v9 = (const WCHAR *)lpSubKey;
  if ( v47 > 7 )
    v9 = lpSubKey[0];
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 1u, hKey);
  v39 = v10;
  if ( (unsigned int)(v10 - 2) <= 1 )
  {
    *a4 = 1;
  }
  else
  {
    if ( v10 )
    {
      std::string::string(v48, "AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRecord");
      v49 = 182;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      v42 = 0;
      v43 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        &v42,
        L"Couldn't open registry key.\n winerr = %1%\n sub key: %2%",
        55);
      v12 = AppV::Log::fmt(v11, v50, &v42);
      v13 = AppV::LogFormatter::operator%<long>(v12, &v39);
      v14 = lpSubKey;
      if ( v47 > 7 )
        v14 = (LPCWSTR *)lpSubKey[0];
      v41 = v14;
      v15 = AppV::LogFormatter::operator%<wchar_t const *>(v13, &v41);
      v44 = 0;
      v45 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v44, L"Publishing", 10);
      AppV::DecoratedLog::operator()(v48, 1, &v44, v15);
      std::wstring::~wstring(&v44);
      v50[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v51);
      std::wstring::~wstring(&v42);
      std::string::~string(v48);
      v16 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
      if ( v16 )
        v17 = v16 + 1;
      else
        v17 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
      FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v17);
      v19 = 0x162700000000LL;
LABEL_18:
      v28 = v19 | v39 | (FileId << 52);
      goto LABEL_19;
    }
    *(_DWORD *)a3 = v6;
    *((_BYTE *)a3 + 4) = a1;
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v44, L"Name", 4);
    v42 = 0;
    v43 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v42, &qword_140088C88, 0);
    v39 = softgrid::registry::RegReadString(hKey[0], &v42, &v44, (char *)a3 + 8);
    std::wstring::~wstring(&v42);
    std::wstring::~wstring(&v44);
    if ( v39 )
    {
      std::string::string(v48, "AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRecord");
      v49 = 200;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      v44 = 0;
      v45 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        &v44,
        L"Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%",
        75);
      v21 = AppV::Log::fmt(v20, v50, &v44);
      v22 = AppV::LogFormatter::operator%<long>(v21, &v39);
      v23 = lpSubKey;
      if ( v47 > 7 )
        v23 = (LPCWSTR *)lpSubKey[0];
      v41 = v23;
      v24 = AppV::LogFormatter::operator%<wchar_t const *>(v22, &v41);
      v25 = AppV::LogFormatter::operator%<wchar_t const *>(v24, off_140072470);
      v42 = 0;
      v43 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v42, L"Publishing", 10);
      AppV::DecoratedLog::operator()(v48, 1, &v42, v25);
      std::wstring::~wstring(&v42);
      v50[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v51);
      std::wstring::~wstring(&v44);
      std::string::~string(v48);
      v26 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
      if ( v26 )
        v27 = v26 + 1;
      else
        v27 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
      FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v27);
      v19 = 0x192700000000LL;
      goto LABEL_18;
    }
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v44, L"URL", 3);
    v42 = 0;
    v43 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v42, &qword_140088C88, 0);
    v39 = softgrid::registry::RegReadString(hKey[0], &v42, &v44, (char *)a3 + 40);
    std::wstring::~wstring(&v42);
    std::wstring::~wstring(&v44);
    if ( v39 )
    {
      std::string::string(v48, "AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRecord");
      v49 = 212;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      v44 = 0;
      v45 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        &v44,
        L"Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%",
        75);
      v30 = AppV::Log::fmt(v29, v50, &v44);
      v31 = AppV::LogFormatter::operator%<long>(v30, &v39);
      v32 = lpSubKey;
      if ( v47 > 7 )
        v32 = (LPCWSTR *)lpSubKey[0];
      v41 = v32;
      v33 = AppV::LogFormatter::operator%<wchar_t const *>(v31, &v41);
      v34 = AppV::LogFormatter::operator%<wchar_t const *>(v33, off_140072478);
      v42 = 0;
      v43 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v42, L"Publishing", 10);
      AppV::DecoratedLog::operator()(v48, 1, &v42, v34);
      std::wstring::~wstring(&v42);
      v50[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v51);
      std::wstring::~wstring(&v44);
      std::string::~string(v48);
      v35 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
      if ( v35 )
        v36 = v35 + 1;
      else
        v36 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
      FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v36);
      v19 = 0x1A2700000000LL;
      goto LABEL_18;
    }
    v42 = 0;
    v43 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v42, L"Global", 6);
    RegServerRefreshPolicy = AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy(hKey[0]);
    std::wstring::~wstring(&v42);
    if ( (RegServerRefreshPolicy & 0x8000000000LL) == 0 )
    {
      if ( hKey[0] )
      {
        RegCloseKey(hKey[0]);
        hKey[0] = 0;
      }
      v28 = RegServerRefreshPolicy;
      goto LABEL_38;
    }
    v42 = 0;
    v43 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v42, L"User", 4);
    v28 = AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy(hKey[0]);
    std::wstring::~wstring(&v42);
    if ( (v28 & 0x8000000000LL) == 0 )
    {
LABEL_19:
      if ( hKey[0] )
      {
        RegCloseKey(hKey[0]);
        hKey[0] = 0;
      }
      goto LABEL_38;
    }
    *a4 = 0;
  }
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
  }
  v28 = 0x8000000000LL;
LABEL_38:
  std::wstring::~wstring(lpSubKey);
  return v28;
}

```

## disassembly

```asm
0x14005c32c  push    rbp
0x14005c32e  push    rbx
0x14005c32f  push    rsi
0x14005c330  push    rdi
0x14005c331  push    r13
0x14005c333  push    r14
0x14005c335  push    r15
0x14005c337  lea     rbp, [rsp-20h]
0x14005c33c  sub     rsp, 120h
0x14005c343  mov     rax, cs:__security_cookie
0x14005c34a  xor     rax, rsp
0x14005c34d  mov     [rbp+50h+var_40], rax
0x14005c351  mov     rsi, r9
0x14005c354  mov     rbx, r8
0x14005c357  mov     r14d, edx
0x14005c35a  mov     dil, cl
0x14005c35d  mov     r8d, edx
0x14005c360  mov     dl, cl
0x14005c362  lea     rcx, [rbp+50h+lpSubKey]
0x14005c366  call    ?GetRegServerKeyPath@ServerRegRecord@Configurations@Publishing@Client@AppV@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NI@Z; AppV::Client::Publishing::Configurations::ServerRegRecord::GetRegServerKeyPath(bool,uint)
0x14005c36b  nop
0x14005c36c  xor     r15d, r15d
0x14005c36f  mov     [rsp+150h+hKey], r15
0x14005c374  mov     [rsp+150h+var_110], r15
0x14005c379  mov     [rsp+150h+var_108], r15
0x14005c37e  lea     rdx, [rbp+50h+lpSubKey]
0x14005c382  cmp     [rbp+50h+var_A0], 7
0x14005c387  cmova   rdx, [rbp+50h+lpSubKey]; lpSubKey
0x14005c38c  lea     rax, [rsp+150h+hKey]
0x14005c391  mov     [rsp+150h+phkResult], rax; phkResult
0x14005c396  lea     r9d, [r15+1]; samDesired
0x14005c39a  xor     r8d, r8d; ulOptions
0x14005c39d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005c3a4  call    cs:__imp_RegOpenKeyExW
0x14005c3aa  mov     [rsp+150h+var_120], eax
0x14005c3ae  lea     ecx, [rax-2]
0x14005c3b1  mov     r13, 8000000000h
0x14005c3bb  cmp     ecx, 1
0x14005c3be  jbe     loc_14005C998
0x14005c3c4  test    eax, eax
0x14005c3c6  jz      loc_14005C501
0x14005c3cc  lea     rdx, aAppvClientPubl; "AppV::Client::Publishing::Configuration"...
0x14005c3d3  lea     rcx, [rbp+50h+var_98]
0x14005c3d7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005c3dc  mov     [rbp+50h+var_78], 0B6h
0x14005c3e3  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005c3e8  xorps   xmm0, xmm0
0x14005c3eb  movups  [rsp+150h+var_F8], xmm0
0x14005c3f0  xorps   xmm1, xmm1
0x14005c3f3  movdqu  [rsp+150h+var_E8], xmm1
0x14005c3f9  lea     r8d, [r15+37h]
0x14005c3fd  lea     rdx, aCouldnTOpenReg; "Couldn't open registry key.\n winerr = "...
0x14005c404  lea     rcx, [rsp+150h+var_F8]
0x14005c409  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005c40e  nop
0x14005c40f  lea     r8, [rsp+150h+var_F8]
0x14005c414  lea     rdx, [rbp+50h+var_70]
0x14005c418  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005c41d  nop
0x14005c41e  lea     rdx, [rsp+150h+var_120]
0x14005c423  mov     rcx, rax
0x14005c426  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005c42b  lea     rcx, [rbp+50h+lpSubKey]
0x14005c42f  cmp     [rbp+50h+var_A0], 7
0x14005c434  cmova   rcx, [rbp+50h+lpSubKey]
0x14005c439  mov     [rsp+150h+var_100], rcx
0x14005c43e  lea     rdx, [rsp+150h+var_100]
0x14005c443  mov     rcx, rax
0x14005c446  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005c44b  mov     rbx, rax
0x14005c44e  xorps   xmm0, xmm0
0x14005c451  movups  [rsp+150h+var_D8], xmm0
0x14005c456  xorps   xmm1, xmm1
0x14005c459  movdqu  [rbp+50h+var_C8], xmm1
0x14005c45e  lea     r8d, [r15+0Ah]
0x14005c462  lea     rdx, aPublishing; "Publishing"
0x14005c469  lea     rcx, [rsp+150h+var_D8]
0x14005c46e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005c473  nop
0x14005c474  mov     r9, rbx
0x14005c477  lea     r8, [rsp+150h+var_D8]
0x14005c47c  lea     edx, [r15+1]
0x14005c480  lea     rcx, [rbp+50h+var_98]
0x14005c484  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005c489  nop
0x14005c48a  lea     rcx, [rsp+150h+var_D8]
0x14005c48f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005c494  nop
0x14005c495  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005c49c  mov     [rbp+50h+var_70], rax
0x14005c4a0  lea     rcx, [rbp+50h+var_60]
0x14005c4a4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005c4a9  nop
0x14005c4aa  lea     rcx, [rsp+150h+var_F8]
0x14005c4af  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005c4b4  nop
0x14005c4b5  lea     rcx, [rbp+50h+var_98]
0x14005c4b9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005c4be  lea     edx, [r15+5Ch]; Ch
0x14005c4c2  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005c4c9  call    cs:__imp_strrchr
0x14005c4cf  test    rax, rax
0x14005c4d2  jz      short loc_14005C4D9
0x14005c4d4  inc     rax
0x14005c4d7  jmp     short loc_14005C4E0
0x14005c4d9  lea     rax, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005c4e0  mov     rdx, rax; char *
0x14005c4e3  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005c4ea  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005c4ef  mov     rbx, rax
0x14005c4f2  mov     rax, 162700000000h
0x14005c4fc  jmp     loc_14005C6D4
0x14005c501  mov     [rbx], r14d
0x14005c504  mov     [rbx+4], dil
0x14005c508  xorps   xmm0, xmm0
0x14005c50b  movups  [rsp+150h+var_D8], xmm0
0x14005c510  xorps   xmm1, xmm1
0x14005c513  movdqu  [rbp+50h+var_C8], xmm1
0x14005c518  mov     r14d, 4
0x14005c51e  mov     r8d, r14d
0x14005c521  lea     rdx, ValueName; "Name"
0x14005c528  lea     rcx, [rsp+150h+var_D8]
0x14005c52d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005c532  nop
0x14005c533  xorps   xmm0, xmm0
0x14005c536  movups  [rsp+150h+var_F8], xmm0
0x14005c53b  xorps   xmm1, xmm1
0x14005c53e  movdqu  [rsp+150h+var_E8], xmm1
0x14005c544  xor     r8d, r8d
0x14005c547  lea     rdx, qword_140088C88
0x14005c54e  lea     rcx, [rsp+150h+var_F8]
0x14005c553  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005c558  nop
0x14005c559  lea     r9, [rbx+8]
0x14005c55d  lea     r8, [rsp+150h+var_D8]
0x14005c562  lea     rdx, [rsp+150h+var_F8]
0x14005c567  mov     rcx, [rsp+150h+hKey]
0x14005c56c  call    ?RegReadString@registry@softgrid@@YAJPEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAV45@K@Z; softgrid::registry::RegReadString(HKEY__ *,std::wstring const &,std::wstring const &,std::wstring &,ulong)
0x14005c571  mov     [rsp+150h+var_120], eax
0x14005c575  lea     rcx, [rsp+150h+var_F8]
0x14005c57a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005c57f  nop
0x14005c580  lea     rcx, [rsp+150h+var_D8]
0x14005c585  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005c58a  cmp     [rsp+150h+var_120], r15d
0x14005c58f  jz      loc_14005C700
0x14005c595  lea     rdx, aAppvClientPubl; "AppV::Client::Publishing::Configuration"...
0x14005c59c  lea     rcx, [rbp+50h+var_98]
0x14005c5a0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005c5a5  mov     [rbp+50h+var_78], 0C8h
0x14005c5ac  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005c5b1  xorps   xmm0, xmm0
0x14005c5b4  movups  [rsp+150h+var_D8], xmm0
0x14005c5b9  xorps   xmm1, xmm1
0x14005c5bc  movdqu  [rbp+50h+var_C8], xmm1
0x14005c5c1  lea     r8d, [r14+47h]
0x14005c5c5  lea     rdx, aCouldnTReadReg; "Couldn't read registry string.\n winerr"...
0x14005c5cc  lea     rcx, [rsp+150h+var_D8]
0x14005c5d1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005c5d6  nop
0x14005c5d7  lea     r8, [rsp+150h+var_D8]
0x14005c5dc  lea     rdx, [rbp+50h+var_70]
0x14005c5e0  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005c5e5  nop
0x14005c5e6  lea     rdx, [rsp+150h+var_120]
0x14005c5eb  mov     rcx, rax
0x14005c5ee  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005c5f3  lea     rcx, [rbp+50h+lpSubKey]
0x14005c5f7  cmp     [rbp+50h+var_A0], 7
0x14005c5fc  cmova   rcx, [rbp+50h+lpSubKey]
0x14005c601  mov     [rsp+150h+var_100], rcx
0x14005c606  lea     rdx, [rsp+150h+var_100]
0x14005c60b  mov     rcx, rax
0x14005c60e  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005c613  lea     rdx, off_140072470; "Name"
0x14005c61a  mov     rcx, rax
0x14005c61d  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005c622  mov     rbx, rax
0x14005c625  xorps   xmm0, xmm0
0x14005c628  movups  [rsp+150h+var_F8], xmm0
0x14005c62d  xorps   xmm1, xmm1
0x14005c630  movdqu  [rsp+150h+var_E8], xmm1
0x14005c636  lea     r8d, [r14+6]
0x14005c63a  lea     rdx, aPublishing; "Publishing"
0x14005c641  lea     rcx, [rsp+150h+var_F8]
0x14005c646  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005c64b  nop
0x14005c64c  mov     r9, rbx
0x14005c64f  lea     r8, [rsp+150h+var_F8]
0x14005c654  lea     edx, [r14-3]
0x14005c658  lea     rcx, [rbp+50h+var_98]
0x14005c65c  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005c661  nop
0x14005c662  lea     rcx, [rsp+150h+var_F8]
0x14005c667  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005c66c  nop
0x14005c66d  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005c674  mov     [rbp+50h+var_70], rax
0x14005c678  lea     rcx, [rbp+50h+var_60]
0x14005c67c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005c681  nop
0x14005c682  lea     rcx, [rsp+150h+var_D8]
0x14005c687  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005c68c  nop
0x14005c68d  lea     rcx, [rbp+50h+var_98]
0x14005c691  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005c696  lea     edx, [r14+58h]; Ch
0x14005c69a  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005c6a1  call    cs:__imp_strrchr
0x14005c6a7  test    rax, rax
0x14005c6aa  jz      short loc_14005C6B1
0x14005c6ac  inc     rax
0x14005c6af  jmp     short loc_14005C6B8
0x14005c6b1  lea     rax, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005c6b8  mov     rdx, rax; char *
0x14005c6bb  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005c6c2  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005c6c7  mov     rbx, rax
0x14005c6ca  mov     rax, 192700000000h
0x14005c6d4  mov     ecx, [rsp+150h+var_120]
0x14005c6d8  shl     rbx, 34h
0x14005c6dc  or      rbx, rcx
0x14005c6df  or      rbx, rax
0x14005c6e2  mov     rcx, [rsp+150h+hKey]; hKey
0x14005c6e7  test    rcx, rcx
0x14005c6ea  jz      loc_14005C9B3
0x14005c6f0  call    cs:__imp_RegCloseKey
0x14005c6f6  mov     [rsp+150h+hKey], r15
0x14005c6fb  jmp     loc_14005C9B3
0x14005c700  xorps   xmm0, xmm0
0x14005c703  movups  [rsp+150h+var_D8], xmm0
0x14005c708  xorps   xmm1, xmm1
0x14005c70b  movdqu  [rbp+50h+var_C8], xmm1
0x14005c710  mov     r8d, 3
0x14005c716  lea     rdx, aUrl; "URL"
0x14005c71d  lea     rcx, [rsp+150h+var_D8]
0x14005c722  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005c727  nop
0x14005c728  xorps   xmm0, xmm0
0x14005c72b  movups  [rsp+150h+var_F8], xmm0
0x14005c730  xorps   xmm1, xmm1
0x14005c733  movdqu  [rsp+150h+var_E8], xmm1
0x14005c739  xor     r8d, r8d
0x14005c73c  lea     rdx, qword_140088C88
0x14005c743  lea     rcx, [rsp+150h+var_F8]
0x14005c748  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005c74d  nop
0x14005c74e  lea     r9, [rbx+28h]
0x14005c752  lea     r8, [rsp+150h+var_D8]
0x14005c757  lea     rdx, [rsp+150h+var_F8]
0x14005c75c  mov     rcx, [rsp+150h+hKey]
0x14005c761  call    ?RegReadString@registry@softgrid@@YAJPEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAV45@K@Z; softgrid::registry::RegReadString(HKEY__ *,std::wstring const &,std::wstring const &,std::wstring &,ulong)
0x14005c766  mov     [rsp+150h+var_120], eax
0x14005c76a  lea     rcx, [rsp+150h+var_F8]
0x14005c76f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005c774  nop
0x14005c775  lea     rcx, [rsp+150h+var_D8]
0x14005c77a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005c77f  cmp     [rsp+150h+var_120], r15d
0x14005c784  jz      loc_14005C8D4
0x14005c78a  lea     rdx, aAppvClientPubl; "AppV::Client::Publishing::Configuration"...
0x14005c791  lea     rcx, [rbp+50h+var_98]
0x14005c795  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005c79a  mov     [rbp+50h+var_78], 0D4h
0x14005c7a1  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005c7a6  xorps   xmm0, xmm0
0x14005c7a9  movups  [rsp+150h+var_D8], xmm0
0x14005c7ae  xorps   xmm1, xmm1
0x14005c7b1  movdqu  [rbp+50h+var_C8], xmm1
0x14005c7b6  mov     r8d, 4Bh ; 'K'
0x14005c7bc  lea     rdx, aCouldnTReadReg; "Couldn't read registry string.\n winerr"...
0x14005c7c3  lea     rcx, [rsp+150h+var_D8]
0x14005c7c8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005c7cd  nop
0x14005c7ce  lea     r8, [rsp+150h+var_D8]
0x14005c7d3  lea     rdx, [rbp+50h+var_70]
0x14005c7d7  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005c7dc  nop
0x14005c7dd  lea     rdx, [rsp+150h+var_120]
0x14005c7e2  mov     rcx, rax
0x14005c7e5  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005c7ea  lea     rcx, [rbp+50h+lpSubKey]
0x14005c7ee  cmp     [rbp+50h+var_A0], 7
0x14005c7f3  cmova   rcx, [rbp+50h+lpSubKey]
0x14005c7f8  mov     [rsp+150h+var_100], rcx
0x14005c7fd  lea     rdx, [rsp+150h+var_100]
0x14005c802  mov     rcx, rax
0x14005c805  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005c80a  lea     rdx, off_140072478; "URL"
0x14005c811  mov     rcx, rax
0x14005c814  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005c819  mov     rbx, rax
0x14005c81c  xorps   xmm0, xmm0
0x14005c81f  movups  [rsp+150h+var_F8], xmm0
0x14005c824  xorps   xmm1, xmm1
0x14005c827  movdqu  [rsp+150h+var_E8], xmm1
0x14005c82d  mov     r8d, 0Ah
0x14005c833  lea     rdx, aPublishing; "Publishing"
0x14005c83a  lea     rcx, [rsp+150h+var_F8]
0x14005c83f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
  ... truncated ...
```
