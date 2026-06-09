# AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy(HKEY__ *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,AppV::Client::Publishing::Configurations::ServerProperties::RefreshPolicy const &)

- ea: `0x14005df40`
- end: `0x14005e7c6`
- name: `?WriteRegServerRefreshPolicy@ServerRegRecord@Configurations@Publishing@Client@AppV@@CA_KPEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEBURefreshPolicy@ServerProperties@2345@@Z`
- size: `2182`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x14005d8d4`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x1400066a8`
- `0x14000697c`
- `0x140006a94`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x140019cc8`
- `0x14001a100`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14005df40`

## import_xrefs

- `ADVAPI32!RegSetKeyValueW` at `0x14005e037`
- `ADVAPI32!RegSetKeyValueW` at `0x14005e237`
- `ADVAPI32!RegSetKeyValueW` at `0x14005e427`
- `ADVAPI32!RegSetKeyValueW` at `0x14005e612`
- `ADVAPI32!RegSetKeyValueW` at `0x14005e037`
- `ADVAPI32!RegSetKeyValueW` at `0x14005e237`
- `ADVAPI32!RegSetKeyValueW` at `0x14005e427`
- `ADVAPI32!RegSetKeyValueW` at `0x14005e612`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005e162`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005e364`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005e554`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005e73f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005e162`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005e364`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005e554`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005e73f`

## string_xrefs

- `0x14005e15b`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005e172`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005e35d`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005e374`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005e54d`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005e564`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005e738`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005e74f`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005e049`: `AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy`
- `0x14005e249`: `AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy`
- `0x14005e439`: `AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy`
- `0x14005e624`: `AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy`
- `0x14005e079`: `Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%`
- `0x14005e27a`: `Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%`
- `0x14005e46a`: `Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%`
- `0x14005e655`: `Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy(
        HKEY hKey,
        WCHAR *a2,
        _QWORD *a3,
        unsigned __int8 *a4)
{
  _QWORD *v5; // rbx
  WCHAR *v6; // rdi
  __int64 v8; // rcx
  _QWORD *v9; // r9
  const WCHAR *v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  LPCWSTR *v17; // rcx
  __int64 v18; // rbx
  char *v19; // rax
  const char *v20; // rax
  unsigned __int64 FileId; // rax
  __int64 v22; // rbx
  __int64 v23; // rcx
  _QWORD *v24; // r9
  const WCHAR *v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  LPCWSTR *v32; // rcx
  __int64 v33; // rbx
  char *v34; // rax
  const char *v35; // rax
  unsigned __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rcx
  _QWORD *v39; // r9
  const WCHAR *v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  LPCWSTR *v47; // rcx
  __int64 v48; // rbx
  char *v49; // rax
  const char *v50; // rax
  __int64 v51; // rax
  const WCHAR *v52; // r8
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  LPCWSTR *v57; // rcx
  __int64 v58; // rbx
  char *v59; // rax
  const char *v60; // rax
  unsigned int v62; // [rsp+40h] [rbp-C0h] BYREF
  int Data; // [rsp+44h] [rbp-BCh] BYREF
  LPCWSTR *v64; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR *v65; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+58h] [rbp-A8h] BYREF
  __m128i si128; // [rsp+68h] [rbp-98h]
  __int128 v68; // [rsp+78h] [rbp-88h] BYREF
  __int128 v69; // [rsp+88h] [rbp-78h]
  __int128 v70; // [rsp+98h] [rbp-68h] BYREF
  __int128 v71; // [rsp+A8h] [rbp-58h]
  char *v72[4]; // [rsp+B8h] [rbp-48h] BYREF
  int v73; // [rsp+D8h] [rbp-28h]
  _QWORD v74[2]; // [rsp+E0h] [rbp-20h] BYREF
  char *v75[4]; // [rsp+F0h] [rbp-10h] BYREF

  v5 = a3;
  v6 = a2;
  v62 = 0;
  *(_OWORD *)lpValueName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpValueName[0]) = 0;
  Data = *a4;
  v8 = a3[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v8) < 7 )
    goto LABEL_63;
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  std::wstring::wstring(&v68, a2, a3, v9, v8, L"Enabled", 7);
  std::wstring::operator=((char **)lpValueName, (__int64)&v68);
  std::wstring::~wstring((char **)&v68);
  v10 = (const WCHAR *)lpValueName;
  if ( si128.m128i_i64[1] > 7uLL )
    v10 = lpValueName[0];
  v62 = RegSetKeyValueW(hKey, 0, v10, 4u, &Data, 4u);
  if ( v62 )
  {
    std::string::string(v72, "AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy");
    v73 = 373;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v68 = 0;
    v69 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v68,
      L"Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      0x4Du);
    v14 = AppV::Log::fmt(v13, v74, &v68);
    v15 = AppV::LogFormatter::operator%<long>(v14, (__int64)&v62);
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(WCHAR **)v6;
    v64 = (LPCWSTR *)v6;
    v16 = AppV::LogFormatter::operator%<wchar_t const *>(v15, &v64);
    v17 = lpValueName;
    if ( si128.m128i_i64[1] > 7uLL )
      v17 = (LPCWSTR *)lpValueName[0];
    v65 = v17;
    v18 = AppV::LogFormatter::operator%<wchar_t const *>(v16, &v65);
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v70, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v72, 1, (int)&v70, v18);
    std::wstring::~wstring((char **)&v70);
    v74[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v75);
    std::wstring::~wstring((char **)&v68);
    std::string::~string(v72);
    v19 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v19 )
      v20 = v19 + 1;
    else
      v20 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v20);
    v22 = v62 | (FileId << 52) | 0x2E2700000000LL;
    goto LABEL_61;
  }
  Data = a4[1];
  v23 = v5[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v23) < 0xC )
    goto LABEL_63;
  if ( v5[3] <= 7u )
    v24 = v5;
  else
    v24 = (_QWORD *)*v5;
  std::wstring::wstring(&v68, v11, v12, v24, v23, L"LogonRefresh", 12);
  std::wstring::operator=((char **)lpValueName, (__int64)&v68);
  std::wstring::~wstring((char **)&v68);
  v25 = (const WCHAR *)lpValueName;
  if ( si128.m128i_i64[1] > 7uLL )
    v25 = lpValueName[0];
  v62 = RegSetKeyValueW(hKey, 0, v25, 4u, &Data, 4u);
  if ( v62 )
  {
    std::string::string(v72, "AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy");
    v73 = 388;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v70,
      L"Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      0x4Du);
    v29 = AppV::Log::fmt(v28, v74, &v70);
    v30 = AppV::LogFormatter::operator%<long>(v29, (__int64)&v62);
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(WCHAR **)v6;
    v65 = (LPCWSTR *)v6;
    v31 = AppV::LogFormatter::operator%<wchar_t const *>(v30, &v65);
    v32 = lpValueName;
    if ( si128.m128i_i64[1] > 7uLL )
      v32 = (LPCWSTR *)lpValueName[0];
    v64 = v32;
    v33 = AppV::LogFormatter::operator%<wchar_t const *>(v31, &v64);
    v68 = 0;
    v69 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v68, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v72, 1, (int)&v68, v33);
    std::wstring::~wstring((char **)&v68);
    v74[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v75);
    std::wstring::~wstring((char **)&v70);
    std::string::~string(v72);
    v34 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v34 )
      v35 = v34 + 1;
    else
      v35 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    v36 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v35);
    v37 = 0x302700000000LL;
LABEL_60:
    v22 = v37 | (v36 << 52) | v62;
LABEL_61:
    std::wstring::~wstring((char **)lpValueName);
    return v22;
  }
  Data = *((_DWORD *)a4 + 1);
  v38 = v5[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v38) < 0x17 )
    goto LABEL_63;
  if ( v5[3] <= 7u )
    v39 = v5;
  else
    v39 = (_QWORD *)*v5;
  std::wstring::wstring(&v68, v26, v27, v39, v38, L"PeriodicRefreshInterval", 23);
  std::wstring::operator=((char **)lpValueName, (__int64)&v68);
  std::wstring::~wstring((char **)&v68);
  v40 = (const WCHAR *)lpValueName;
  if ( si128.m128i_i64[1] > 7uLL )
    v40 = lpValueName[0];
  v62 = RegSetKeyValueW(hKey, 0, v40, 4u, &Data, 4u);
  if ( v62 )
  {
    std::string::string(v72, "AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy");
    v73 = 403;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v70,
      L"Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      0x4Du);
    v44 = AppV::Log::fmt(v43, v74, &v70);
    v45 = AppV::LogFormatter::operator%<long>(v44, (__int64)&v62);
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(WCHAR **)v6;
    v65 = (LPCWSTR *)v6;
    v46 = AppV::LogFormatter::operator%<wchar_t const *>(v45, &v65);
    v47 = lpValueName;
    if ( si128.m128i_i64[1] > 7uLL )
      v47 = (LPCWSTR *)lpValueName[0];
    v64 = v47;
    v48 = AppV::LogFormatter::operator%<wchar_t const *>(v46, &v64);
    v68 = 0;
    v69 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v68, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v72, 1, (int)&v68, v48);
    std::wstring::~wstring((char **)&v68);
    v74[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v75);
    std::wstring::~wstring((char **)&v70);
    std::string::~string(v72);
    v49 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v49 )
      v50 = v49 + 1;
    else
      v50 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    v36 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v50);
    v37 = 0x322700000000LL;
    goto LABEL_60;
  }
  Data = *((_DWORD *)a4 + 2);
  v51 = v5[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v51) < 0x1B )
LABEL_63:
    std::_Xlen_string();
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::wstring(&v68, v41, v42, v5, v51, L"PeriodicRefreshIntervalUnit", 27);
  std::wstring::operator=((char **)lpValueName, (__int64)&v68);
  std::wstring::~wstring((char **)&v68);
  v52 = (const WCHAR *)lpValueName;
  if ( si128.m128i_i64[1] > 7uLL )
    v52 = lpValueName[0];
  v62 = RegSetKeyValueW(hKey, 0, v52, 4u, &Data, 4u);
  if ( v62 )
  {
    std::string::string(v72, "AppV::Client::Publishing::Configurations::ServerRegRecord::WriteRegServerRefreshPolicy");
    v73 = 418;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v70,
      L"Couldn't set registry key value.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      0x4Du);
    v54 = AppV::Log::fmt(v53, v74, &v70);
    v55 = AppV::LogFormatter::operator%<long>(v54, (__int64)&v62);
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(WCHAR **)v6;
    v65 = (LPCWSTR *)v6;
    v56 = AppV::LogFormatter::operator%<wchar_t const *>(v55, &v65);
    v57 = lpValueName;
    if ( si128.m128i_i64[1] > 7uLL )
      v57 = (LPCWSTR *)lpValueName[0];
    v64 = v57;
    v58 = AppV::LogFormatter::operator%<wchar_t const *>(v56, &v64);
    v68 = 0;
    v69 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v68, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v72, 1, (int)&v68, v58);
    std::wstring::~wstring((char **)&v68);
    v74[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v75);
    std::wstring::~wstring((char **)&v70);
    std::string::~string(v72);
    v59 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v59 )
      v60 = v59 + 1;
    else
      v60 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    v36 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v60);
    v37 = 0x342700000000LL;
    goto LABEL_60;
  }
  std::wstring::~wstring((char **)lpValueName);
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14005df40  push    rbp
0x14005df42  push    rbx
0x14005df43  push    rsi
0x14005df44  push    rdi
0x14005df45  push    r12
0x14005df47  push    r13
0x14005df49  push    r14
0x14005df4b  push    r15
0x14005df4d  lea     rbp, [rsp-28h]
0x14005df52  sub     rsp, 128h
0x14005df59  mov     rax, cs:__security_cookie
0x14005df60  xor     rax, rsp
0x14005df63  mov     [rbp+60h+var_50], rax
0x14005df67  mov     r14, r9
0x14005df6a  mov     rbx, r8
0x14005df6d  mov     rdi, rdx
0x14005df70  mov     r15, rcx
0x14005df73  mov     [rsp+160h+var_120], 0
0x14005df7b  xorps   xmm0, xmm0
0x14005df7e  movups  xmmword ptr [rsp+160h+lpValueName], xmm0
0x14005df83  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14005df8b  movdqu  [rsp+160h+var_F8], xmm1
0x14005df91  xor     eax, eax
0x14005df93  mov     word ptr [rsp+160h+lpValueName], ax
0x14005df98  movzx   eax, byte ptr [r9]
0x14005df9c  mov     [rsp+160h+Data], eax
0x14005dfa0  mov     rcx, [r8+10h]
0x14005dfa4  mov     rsi, 7FFFFFFFFFFFFFFEh
0x14005dfae  mov     rax, rsi
0x14005dfb1  sub     rax, rcx
0x14005dfb4  mov     r12d, 7
0x14005dfba  cmp     rax, r12
0x14005dfbd  jb      loc_14005E7C0
0x14005dfc3  cmp     [r8+18h], r12
0x14005dfc7  jbe     short loc_14005DFCE
0x14005dfc9  mov     r9, [r8]
0x14005dfcc  jmp     short loc_14005DFD1
0x14005dfce  mov     r9, rbx
0x14005dfd1  mov     [rsp+160h+var_130], r12
0x14005dfd6  lea     rax, aEnabled; "Enabled"
0x14005dfdd  mov     qword ptr [rsp+160h+cbData], rax
0x14005dfe2  mov     [rsp+160h+lpData], rcx
0x14005dfe7  lea     rcx, [rsp+160h+var_E8]
0x14005dfec  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14005dff1  lea     rdx, [rsp+160h+var_E8]
0x14005dff6  lea     rcx, [rsp+160h+lpValueName]
0x14005dffb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14005e000  lea     rcx, [rsp+160h+var_E8]
0x14005e005  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005e00a  lea     r8, [rsp+160h+lpValueName]
0x14005e00f  cmp     qword ptr [rsp+160h+var_F8+8], r12
0x14005e014  cmova   r8, [rsp+160h+lpValueName]; lpValueName
0x14005e01a  mov     r13d, 4
0x14005e020  mov     [rsp+160h+cbData], r13d; cbData
0x14005e025  lea     rax, [rsp+160h+Data]
0x14005e02a  mov     [rsp+160h+lpData], rax; lpData
0x14005e02f  mov     r9d, r13d; dwType
0x14005e032  xor     edx, edx; lpSubKey
0x14005e034  mov     rcx, r15; hKey
0x14005e037  call    cs:__imp_RegSetKeyValueW
0x14005e03d  mov     [rsp+160h+var_120], eax
0x14005e041  test    eax, eax
0x14005e043  jz      loc_14005E1A8
0x14005e049  lea     rdx, aAppvClientPubl_7; "AppV::Client::Publishing::Configuration"...
0x14005e050  lea     rcx, [rbp+60h+var_A8]
0x14005e054  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005e059  mov     [rbp+60h+var_88], 175h
0x14005e060  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005e065  xorps   xmm0, xmm0
0x14005e068  movups  [rsp+160h+var_E8], xmm0
0x14005e06d  xorps   xmm1, xmm1
0x14005e070  movdqu  [rbp+60h+var_D8], xmm1
0x14005e075  lea     r8d, [r13+49h]
0x14005e079  lea     rdx, aCouldnTSetRegi; "Couldn't set registry key value.\n wine"...
0x14005e080  lea     rcx, [rsp+160h+var_E8]
0x14005e085  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005e08a  nop
0x14005e08b  lea     r8, [rsp+160h+var_E8]
0x14005e090  lea     rdx, [rbp+60h+var_80]
0x14005e094  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005e099  nop
0x14005e09a  lea     rdx, [rsp+160h+var_120]
0x14005e09f  mov     rcx, rax
0x14005e0a2  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005e0a7  cmp     [rdi+18h], r12
0x14005e0ab  jbe     short loc_14005E0B0
0x14005e0ad  mov     rdi, [rdi]
0x14005e0b0  mov     [rsp+160h+var_118], rdi
0x14005e0b5  lea     rdx, [rsp+160h+var_118]
0x14005e0ba  mov     rcx, rax
0x14005e0bd  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005e0c2  lea     rcx, [rsp+160h+lpValueName]
0x14005e0c7  cmp     qword ptr [rsp+160h+var_F8+8], r12
0x14005e0cc  cmova   rcx, [rsp+160h+lpValueName]
0x14005e0d2  mov     [rsp+160h+var_110], rcx
0x14005e0d7  lea     rdx, [rsp+160h+var_110]
0x14005e0dc  mov     rcx, rax
0x14005e0df  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005e0e4  mov     rbx, rax
0x14005e0e7  xorps   xmm0, xmm0
0x14005e0ea  movups  [rbp+60h+var_C8], xmm0
0x14005e0ee  xorps   xmm1, xmm1
0x14005e0f1  movdqu  [rbp+60h+var_B8], xmm1
0x14005e0f6  mov     r8d, 0Ah
0x14005e0fc  lea     rdx, aPublishing; "Publishing"
0x14005e103  lea     rcx, [rbp+60h+var_C8]
0x14005e107  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005e10c  nop
0x14005e10d  mov     r9, rbx
0x14005e110  lea     r8, [rbp+60h+var_C8]
0x14005e114  mov     edx, 1
0x14005e119  lea     rcx, [rbp+60h+var_A8]
0x14005e11d  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005e122  nop
0x14005e123  lea     rcx, [rbp+60h+var_C8]
0x14005e127  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005e12c  nop
0x14005e12d  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005e134  mov     [rbp+60h+var_80], rax
0x14005e138  lea     rcx, [rbp+60h+var_70]
0x14005e13c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005e141  nop
0x14005e142  lea     rcx, [rsp+160h+var_E8]
0x14005e147  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005e14c  nop
0x14005e14d  lea     rcx, [rbp+60h+var_A8]
0x14005e151  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005e156  mov     edx, 5Ch ; '\'; Ch
0x14005e15b  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005e162  call    cs:__imp_strrchr
0x14005e168  test    rax, rax
0x14005e16b  jz      short loc_14005E172
0x14005e16d  inc     rax
0x14005e170  jmp     short loc_14005E179
0x14005e172  lea     rax, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005e179  mov     rdx, rax; char *
0x14005e17c  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005e183  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005e188  mov     rbx, rax
0x14005e18b  shl     rbx, 34h
0x14005e18f  mov     ecx, [rsp+160h+var_120]
0x14005e193  or      rbx, rcx
0x14005e196  mov     rax, 2E2700000000h
0x14005e1a0  or      rbx, rax
0x14005e1a3  jmp     loc_14005E77D
0x14005e1a8  movzx   eax, byte ptr [r14+1]
0x14005e1ad  mov     [rsp+160h+Data], eax
0x14005e1b1  mov     rcx, [rbx+10h]
0x14005e1b5  mov     rax, rsi
0x14005e1b8  sub     rax, rcx
0x14005e1bb  cmp     rax, 0Ch
0x14005e1bf  jb      loc_14005E7C0
0x14005e1c5  cmp     [rbx+18h], r12
0x14005e1c9  jbe     short loc_14005E1D0
0x14005e1cb  mov     r9, [rbx]
0x14005e1ce  jmp     short loc_14005E1D3
0x14005e1d0  mov     r9, rbx
0x14005e1d3  mov     [rsp+160h+var_130], 0Ch
0x14005e1dc  lea     rax, aLogonrefresh; "LogonRefresh"
0x14005e1e3  mov     qword ptr [rsp+160h+cbData], rax
0x14005e1e8  mov     [rsp+160h+lpData], rcx
0x14005e1ed  lea     rcx, [rsp+160h+var_E8]
0x14005e1f2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14005e1f7  lea     rdx, [rsp+160h+var_E8]
0x14005e1fc  lea     rcx, [rsp+160h+lpValueName]
0x14005e201  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14005e206  lea     rcx, [rsp+160h+var_E8]
0x14005e20b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005e210  lea     r8, [rsp+160h+lpValueName]
0x14005e215  cmp     qword ptr [rsp+160h+var_F8+8], r12
0x14005e21a  cmova   r8, [rsp+160h+lpValueName]; lpValueName
0x14005e220  mov     [rsp+160h+cbData], r13d; cbData
0x14005e225  lea     rax, [rsp+160h+Data]
0x14005e22a  mov     [rsp+160h+lpData], rax; lpData
0x14005e22f  mov     r9d, r13d; dwType
0x14005e232  xor     edx, edx; lpSubKey
0x14005e234  mov     rcx, r15; hKey
0x14005e237  call    cs:__imp_RegSetKeyValueW
0x14005e23d  mov     [rsp+160h+var_120], eax
0x14005e241  test    eax, eax
0x14005e243  jz      loc_14005E399
0x14005e249  lea     rdx, aAppvClientPubl_7; "AppV::Client::Publishing::Configuration"...
0x14005e250  lea     rcx, [rbp+60h+var_A8]
0x14005e254  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005e259  mov     [rbp+60h+var_88], 184h
0x14005e260  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005e265  xorps   xmm0, xmm0
0x14005e268  movups  [rbp+60h+var_C8], xmm0
0x14005e26c  xorps   xmm1, xmm1
0x14005e26f  movdqu  [rbp+60h+var_B8], xmm1
0x14005e274  mov     r8d, 4Dh ; 'M'
0x14005e27a  lea     rdx, aCouldnTSetRegi; "Couldn't set registry key value.\n wine"...
0x14005e281  lea     rcx, [rbp+60h+var_C8]
0x14005e285  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005e28a  nop
0x14005e28b  lea     r8, [rbp+60h+var_C8]
0x14005e28f  lea     rdx, [rbp+60h+var_80]
0x14005e293  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005e298  nop
0x14005e299  lea     rdx, [rsp+160h+var_120]
0x14005e29e  mov     rcx, rax
0x14005e2a1  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005e2a6  cmp     [rdi+18h], r12
0x14005e2aa  jbe     short loc_14005E2AF
0x14005e2ac  mov     rdi, [rdi]
0x14005e2af  mov     [rsp+160h+var_110], rdi
0x14005e2b4  lea     rdx, [rsp+160h+var_110]
0x14005e2b9  mov     rcx, rax
0x14005e2bc  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005e2c1  lea     rcx, [rsp+160h+lpValueName]
0x14005e2c6  cmp     qword ptr [rsp+160h+var_F8+8], r12
0x14005e2cb  cmova   rcx, [rsp+160h+lpValueName]
0x14005e2d1  mov     [rsp+160h+var_118], rcx
0x14005e2d6  lea     rdx, [rsp+160h+var_118]
0x14005e2db  mov     rcx, rax
0x14005e2de  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005e2e3  mov     rbx, rax
0x14005e2e6  xorps   xmm0, xmm0
0x14005e2e9  movups  [rsp+160h+var_E8], xmm0
0x14005e2ee  xorps   xmm1, xmm1
0x14005e2f1  movdqu  [rbp+60h+var_D8], xmm1
0x14005e2f6  mov     r8d, 0Ah
0x14005e2fc  lea     rdx, aPublishing; "Publishing"
0x14005e303  lea     rcx, [rsp+160h+var_E8]
0x14005e308  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005e30d  nop
0x14005e30e  mov     r9, rbx
0x14005e311  lea     r8, [rsp+160h+var_E8]
0x14005e316  mov     edx, 1
0x14005e31b  lea     rcx, [rbp+60h+var_A8]
0x14005e31f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005e324  nop
0x14005e325  lea     rcx, [rsp+160h+var_E8]
0x14005e32a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005e32f  nop
0x14005e330  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005e337  mov     [rbp+60h+var_80], rax
0x14005e33b  lea     rcx, [rbp+60h+var_70]
0x14005e33f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005e344  nop
0x14005e345  lea     rcx, [rbp+60h+var_C8]
0x14005e349  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005e34e  nop
0x14005e34f  lea     rcx, [rbp+60h+var_A8]
0x14005e353  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005e358  mov     edx, 5Ch ; '\'; Ch
0x14005e35d  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005e364  call    cs:__imp_strrchr
0x14005e36a  test    rax, rax
0x14005e36d  jz      short loc_14005E374
0x14005e36f  inc     rax
0x14005e372  jmp     short loc_14005E37B
0x14005e374  lea     rax, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005e37b  mov     rdx, rax; char *
0x14005e37e  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005e385  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005e38a  mov     rcx, 302700000000h
0x14005e394  jmp     loc_14005E76F
0x14005e399  mov     eax, [r14+4]
0x14005e39d  mov     [rsp+160h+Data], eax
0x14005e3a1  mov     rcx, [rbx+10h]
0x14005e3a5  mov     rax, rsi
0x14005e3a8  sub     rax, rcx
0x14005e3ab  cmp     rax, 17h
0x14005e3af  jb      loc_14005E7C0
0x14005e3b5  cmp     [rbx+18h], r12
0x14005e3b9  jbe     short loc_14005E3C0
0x14005e3bb  mov     r9, [rbx]
0x14005e3be  jmp     short loc_14005E3C3
0x14005e3c0  mov     r9, rbx
0x14005e3c3  mov     [rsp+160h+var_130], 17h
0x14005e3cc  lea     rax, aPeriodicrefres_0; "PeriodicRefreshInterval"
0x14005e3d3  mov     qword ptr [rsp+160h+cbData], rax
0x14005e3d8  mov     [rsp+160h+lpData], rcx
0x14005e3dd  lea     rcx, [rsp+160h+var_E8]
0x14005e3e2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14005e3e7  lea     rdx, [rsp+160h+var_E8]
0x14005e3ec  lea     rcx, [rsp+160h+lpValueName]
0x14005e3f1  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14005e3f6  lea     rcx, [rsp+160h+var_E8]
0x14005e3fb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005e400  lea     r8, [rsp+160h+lpValueName]
0x14005e405  cmp     qword ptr [rsp+160h+var_F8+8], r12
0x14005e40a  cmova   r8, [rsp+160h+lpValueName]; lpValueName
0x14005e410  mov     [rsp+160h+cbData], r13d; cbData
0x14005e415  lea     rax, [rsp+160h+Data]
0x14005e41a  mov     [rsp+160h+lpData], rax; lpData
0x14005e41f  mov     r9d, r13d; dwType
0x14005e422  xor     edx, edx; lpSubKey
0x14005e424  mov     rcx, r15; hKey
0x14005e427  call    cs:__imp_RegSetKeyValueW
0x14005e42d  mov     [rsp+160h+var_120], eax
0x14005e431  test    eax, eax
0x14005e433  jz      loc_14005E589
0x14005e439  lea     rdx, aAppvClientPubl_7; "AppV::Client::Publishing::Configuration"...
0x14005e440  lea     rcx, [rbp+60h+var_A8]
0x14005e444  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005e449  mov     [rbp+60h+var_88], 193h
0x14005e450  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005e455  xorps   xmm0, xmm0
  ... truncated ...
```
