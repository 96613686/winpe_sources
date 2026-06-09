# AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy(HKEY__ *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,AppV::Client::Publishing::Configurations::ServerProperties::RefreshPolicy &)

- ea: `0x14005c9e4`
- end: `0x14005d290`
- name: `?ReadRegServerRefreshPolicy@ServerRegRecord@Configurations@Publishing@Client@AppV@@CA_KPEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAURefreshPolicy@ServerProperties@2345@@Z`
- size: `2220`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x14005c32c`

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
- `0x14005c9e4`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14005cadf`
- `ADVAPI32!RegGetValueW` at `0x14005cceb`
- `ADVAPI32!RegGetValueW` at `0x14005cee7`
- `ADVAPI32!RegGetValueW` at `0x14005d0da`
- `ADVAPI32!RegGetValueW` at `0x14005cadf`
- `ADVAPI32!RegGetValueW` at `0x14005cceb`
- `ADVAPI32!RegGetValueW` at `0x14005cee7`
- `ADVAPI32!RegGetValueW` at `0x14005d0da`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005cc08`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005ce14`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005d010`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005d203`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005cc08`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005ce14`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005d010`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005d203`

## string_xrefs

- `0x14005cc01`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005cc18`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005ce0d`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005ce24`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005d009`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005d020`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005d1fc`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005d213`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005caf1`: `AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy`
- `0x14005ccfd`: `AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy`
- `0x14005cef9`: `AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy`
- `0x14005d0ec`: `AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy`
- `0x14005cb22`: `Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%`
- `0x14005cd2e`: `Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%`
- `0x14005cf2a`: `Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%`
- `0x14005d11d`: `Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy(
        HKEY hkey,
        WCHAR *a2,
        _QWORD *a3,
        __int64 a4)
{
  _QWORD *v5; // rbx
  WCHAR *v6; // rdi
  __int64 v8; // rcx
  _QWORD *v9; // r9
  const WCHAR *v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  LPCWSTR *v18; // rcx
  __int64 v19; // rbx
  char *v20; // rax
  const char *v21; // rax
  unsigned __int64 FileId; // rax
  __int64 v23; // rbx
  __int64 v24; // rcx
  _QWORD *v25; // r9
  const WCHAR *v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  LPCWSTR *v34; // rcx
  __int64 v35; // rbx
  char *v36; // rax
  const char *v37; // rax
  unsigned __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  _QWORD *v41; // r9
  const WCHAR *v42; // r8
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  LPCWSTR *v50; // rcx
  __int64 v51; // rbx
  char *v52; // rax
  const char *v53; // rax
  __int64 v54; // rax
  const WCHAR *v55; // r8
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  LPCWSTR *v61; // rcx
  __int64 v62; // rbx
  char *v63; // rax
  const char *v64; // rax
  unsigned int ValueW; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR *v69; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR *v70; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpValue[2]; // [rsp+60h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+70h] [rbp-90h]
  __int128 v73; // [rsp+80h] [rbp-80h] BYREF
  __int128 v74; // [rsp+90h] [rbp-70h]
  __int128 v75; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v76; // [rsp+B0h] [rbp-50h]
  char *v77[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v78; // [rsp+E0h] [rbp-20h]
  _QWORD v79[2]; // [rsp+E8h] [rbp-18h] BYREF
  char *v80[4]; // [rsp+F8h] [rbp-8h] BYREF

  v5 = a3;
  v6 = a2;
  pvData = 0;
  pcbData = 4;
  *(_OWORD *)lpValue = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpValue[0]) = 0;
  v8 = a3[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v8) < 7 )
    goto LABEL_63;
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  std::wstring::wstring(&v73, a2, a3, v9, v8, L"Enabled", 7);
  std::wstring::operator=((char **)lpValue, (__int64)&v73);
  std::wstring::~wstring((char **)&v73);
  v10 = (const WCHAR *)lpValue;
  if ( si128.m128i_i64[1] > 7uLL )
    v10 = lpValue[0];
  ValueW = RegGetValueW(hkey, 0, v10, 0x10u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    std::string::string(v77, "AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy");
    v78 = 246;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v13);
    v73 = 0;
    v74 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v73,
      L"Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      0x4Bu);
    v15 = AppV::Log::fmt(v14, v79, &v73);
    v16 = AppV::LogFormatter::operator%<long>(v15, (__int64)&ValueW);
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(WCHAR **)v6;
    v69 = (LPCWSTR *)v6;
    v17 = AppV::LogFormatter::operator%<wchar_t const *>(v16, &v69);
    v18 = lpValue;
    if ( si128.m128i_i64[1] > 7uLL )
      v18 = (LPCWSTR *)lpValue[0];
    v70 = v18;
    v19 = AppV::LogFormatter::operator%<wchar_t const *>(v17, &v70);
    v75 = 0;
    v76 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v75, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v77, 1, (int)&v75, v19);
    std::wstring::~wstring((char **)&v75);
    v79[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v80);
    std::wstring::~wstring((char **)&v73);
    std::string::~string(v77);
    v20 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v20 )
      v21 = v20 + 1;
    else
      v21 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v21);
    v23 = ValueW | (FileId << 52) | 0x1E2700000000LL;
    goto LABEL_61;
  }
  *(_BYTE *)a4 = pvData != 0;
  v24 = v5[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v24) < 0xC )
    goto LABEL_63;
  if ( v5[3] <= 7u )
    v25 = v5;
  else
    v25 = (_QWORD *)*v5;
  std::wstring::wstring(&v73, v11, v12, v25, v24, L"LogonRefresh", 12);
  std::wstring::operator=((char **)lpValue, (__int64)&v73);
  std::wstring::~wstring((char **)&v73);
  v26 = (const WCHAR *)lpValue;
  if ( si128.m128i_i64[1] > 7uLL )
    v26 = lpValue[0];
  ValueW = RegGetValueW(hkey, 0, v26, 0x10u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    std::string::string(v77, "AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy");
    v78 = 260;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v29);
    v75 = 0;
    v76 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v75,
      L"Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      0x4Bu);
    v31 = AppV::Log::fmt(v30, v79, &v75);
    v32 = AppV::LogFormatter::operator%<long>(v31, (__int64)&ValueW);
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(WCHAR **)v6;
    v70 = (LPCWSTR *)v6;
    v33 = AppV::LogFormatter::operator%<wchar_t const *>(v32, &v70);
    v34 = lpValue;
    if ( si128.m128i_i64[1] > 7uLL )
      v34 = (LPCWSTR *)lpValue[0];
    v69 = v34;
    v35 = AppV::LogFormatter::operator%<wchar_t const *>(v33, &v69);
    v73 = 0;
    v74 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v73, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v77, 1, (int)&v73, v35);
    std::wstring::~wstring((char **)&v73);
    v79[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v80);
    std::wstring::~wstring((char **)&v75);
    std::string::~string(v77);
    v36 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v36 )
      v37 = v36 + 1;
    else
      v37 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    v38 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v37);
    v39 = 0x202700000000LL;
LABEL_60:
    v23 = v39 | (v38 << 52) | ValueW;
LABEL_61:
    std::wstring::~wstring((char **)lpValue);
    return v23;
  }
  *(_BYTE *)(a4 + 1) = pvData != 0;
  v40 = v5[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v40) < 0x17 )
    goto LABEL_63;
  if ( v5[3] <= 7u )
    v41 = v5;
  else
    v41 = (_QWORD *)*v5;
  std::wstring::wstring(&v73, v27, v28, v41, v40, L"PeriodicRefreshInterval", 23);
  std::wstring::operator=((char **)lpValue, (__int64)&v73);
  std::wstring::~wstring((char **)&v73);
  v42 = (const WCHAR *)lpValue;
  if ( si128.m128i_i64[1] > 7uLL )
    v42 = lpValue[0];
  ValueW = RegGetValueW(hkey, 0, v42, 0x10u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    std::string::string(v77, "AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy");
    v78 = 274;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v45);
    v75 = 0;
    v76 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v75,
      L"Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      0x4Bu);
    v47 = AppV::Log::fmt(v46, v79, &v75);
    v48 = AppV::LogFormatter::operator%<long>(v47, (__int64)&ValueW);
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(WCHAR **)v6;
    v70 = (LPCWSTR *)v6;
    v49 = AppV::LogFormatter::operator%<wchar_t const *>(v48, &v70);
    v50 = lpValue;
    if ( si128.m128i_i64[1] > 7uLL )
      v50 = (LPCWSTR *)lpValue[0];
    v69 = v50;
    v51 = AppV::LogFormatter::operator%<wchar_t const *>(v49, &v69);
    v73 = 0;
    v74 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v73, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v77, 1, (int)&v73, v51);
    std::wstring::~wstring((char **)&v73);
    v79[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v80);
    std::wstring::~wstring((char **)&v75);
    std::string::~string(v77);
    v52 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v52 )
      v53 = v52 + 1;
    else
      v53 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    v38 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v53);
    v39 = 0x222700000000LL;
    goto LABEL_60;
  }
  *(_DWORD *)(a4 + 4) = pvData;
  v54 = v5[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v54) < 0x1B )
LABEL_63:
    std::_Xlen_string();
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::wstring(&v73, v43, v44, v5, v54, L"PeriodicRefreshIntervalUnit", 27);
  std::wstring::operator=((char **)lpValue, (__int64)&v73);
  std::wstring::~wstring((char **)&v73);
  v55 = (const WCHAR *)lpValue;
  if ( si128.m128i_i64[1] > 7uLL )
    v55 = lpValue[0];
  ValueW = RegGetValueW(hkey, 0, v55, 0x10u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    std::string::string(v77, "AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRefreshPolicy");
    v78 = 288;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v56);
    v75 = 0;
    v76 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v75,
      L"Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      0x4Bu);
    v58 = AppV::Log::fmt(v57, v79, &v75);
    v59 = AppV::LogFormatter::operator%<long>(v58, (__int64)&ValueW);
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(WCHAR **)v6;
    v70 = (LPCWSTR *)v6;
    v60 = AppV::LogFormatter::operator%<wchar_t const *>(v59, &v70);
    v61 = lpValue;
    if ( si128.m128i_i64[1] > 7uLL )
      v61 = (LPCWSTR *)lpValue[0];
    v69 = v61;
    v62 = AppV::LogFormatter::operator%<wchar_t const *>(v60, &v69);
    v73 = 0;
    v74 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v73, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v77, 1, (int)&v73, v62);
    std::wstring::~wstring((char **)&v73);
    v79[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v80);
    std::wstring::~wstring((char **)&v75);
    std::string::~string(v77);
    v63 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
    if ( v63 )
      v64 = v63 + 1;
    else
      v64 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
    v38 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v64);
    v39 = 0x242700000000LL;
    goto LABEL_60;
  }
  *(_DWORD *)(a4 + 8) = pvData;
  std::wstring::~wstring((char **)lpValue);
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14005c9e4  push    rbp
0x14005c9e6  push    rbx
0x14005c9e7  push    rsi
0x14005c9e8  push    rdi
0x14005c9e9  push    r12
0x14005c9eb  push    r14
0x14005c9ed  push    r15
0x14005c9ef  lea     rbp, [rsp-20h]
0x14005c9f4  sub     rsp, 120h
0x14005c9fb  mov     rax, cs:__security_cookie
0x14005ca02  xor     rax, rsp
0x14005ca05  mov     [rbp+50h+var_38], rax
0x14005ca09  mov     r14, r9
0x14005ca0c  mov     rbx, r8
0x14005ca0f  mov     rdi, rdx
0x14005ca12  mov     r15, rcx
0x14005ca15  mov     [rsp+150h+var_10C], 0
0x14005ca1d  mov     [rsp+150h+var_108], 4
0x14005ca25  xorps   xmm0, xmm0
0x14005ca28  movups  xmmword ptr [rsp+150h+lpValue], xmm0
0x14005ca2d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14005ca35  movdqu  [rsp+150h+var_E0], xmm1
0x14005ca3b  xor     eax, eax
0x14005ca3d  mov     word ptr [rsp+150h+lpValue], ax
0x14005ca42  mov     rcx, [r8+10h]
0x14005ca46  mov     rsi, 7FFFFFFFFFFFFFFEh
0x14005ca50  mov     rax, rsi
0x14005ca53  sub     rax, rcx
0x14005ca56  mov     r12d, 7
0x14005ca5c  cmp     rax, r12
0x14005ca5f  jb      loc_14005D28A
0x14005ca65  cmp     [r8+18h], r12
0x14005ca69  jbe     short loc_14005CA70
0x14005ca6b  mov     r9, [r8]
0x14005ca6e  jmp     short loc_14005CA73
0x14005ca70  mov     r9, rbx
0x14005ca73  mov     [rsp+150h+pcbData], r12
0x14005ca78  lea     rax, aEnabled; "Enabled"
0x14005ca7f  mov     [rsp+150h+pvData], rax
0x14005ca84  mov     [rsp+150h+pdwType], rcx
0x14005ca89  lea     rcx, [rbp+50h+var_D0]
0x14005ca8d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14005ca92  lea     rdx, [rbp+50h+var_D0]
0x14005ca96  lea     rcx, [rsp+150h+lpValue]
0x14005ca9b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14005caa0  lea     rcx, [rbp+50h+var_D0]
0x14005caa4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005caa9  lea     r8, [rsp+150h+lpValue]
0x14005caae  cmp     qword ptr [rsp+150h+var_E0+8], r12
0x14005cab3  cmova   r8, [rsp+150h+lpValue]; lpValue
0x14005cab9  lea     rax, [rsp+150h+var_108]
0x14005cabe  mov     [rsp+150h+pcbData], rax; pcbData
0x14005cac3  lea     rax, [rsp+150h+var_10C]
0x14005cac8  mov     [rsp+150h+pvData], rax; pvData
0x14005cacd  mov     [rsp+150h+pdwType], 0; pdwType
0x14005cad6  xor     edx, edx; lpSubKey
0x14005cad8  lea     r9d, [rdx+10h]; dwFlags
0x14005cadc  mov     rcx, r15; hkey
0x14005cadf  call    cs:__imp_RegGetValueW
0x14005cae5  mov     [rsp+150h+var_110], eax
0x14005cae9  test    eax, eax
0x14005caeb  jz      loc_14005CC4E
0x14005caf1  lea     rdx, aAppvClientPubl_8; "AppV::Client::Publishing::Configuration"...
0x14005caf8  lea     rcx, [rbp+50h+var_90]
0x14005cafc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005cb01  mov     [rbp+50h+var_70], 0F6h
0x14005cb08  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005cb0d  xorps   xmm0, xmm0
0x14005cb10  movups  [rbp+50h+var_D0], xmm0
0x14005cb14  xorps   xmm1, xmm1
0x14005cb17  movdqu  [rbp+50h+var_C0], xmm1
0x14005cb1c  mov     r8d, 4Bh ; 'K'
0x14005cb22  lea     rdx, aCouldnTReadReg; "Couldn't read registry string.\n winerr"...
0x14005cb29  lea     rcx, [rbp+50h+var_D0]
0x14005cb2d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005cb32  nop
0x14005cb33  lea     r8, [rbp+50h+var_D0]
0x14005cb37  lea     rdx, [rbp+50h+var_68]
0x14005cb3b  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005cb40  nop
0x14005cb41  lea     rdx, [rsp+150h+var_110]
0x14005cb46  mov     rcx, rax
0x14005cb49  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005cb4e  cmp     [rdi+18h], r12
0x14005cb52  jbe     short loc_14005CB57
0x14005cb54  mov     rdi, [rdi]
0x14005cb57  mov     [rsp+150h+var_100], rdi
0x14005cb5c  lea     rdx, [rsp+150h+var_100]
0x14005cb61  mov     rcx, rax
0x14005cb64  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005cb69  lea     rcx, [rsp+150h+lpValue]
0x14005cb6e  cmp     qword ptr [rsp+150h+var_E0+8], r12
0x14005cb73  cmova   rcx, [rsp+150h+lpValue]
0x14005cb79  mov     [rsp+150h+var_F8], rcx
0x14005cb7e  lea     rdx, [rsp+150h+var_F8]
0x14005cb83  mov     rcx, rax
0x14005cb86  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005cb8b  mov     rbx, rax
0x14005cb8e  xorps   xmm0, xmm0
0x14005cb91  movups  [rbp+50h+var_B0], xmm0
0x14005cb95  xorps   xmm1, xmm1
0x14005cb98  movdqu  [rbp+50h+var_A0], xmm1
0x14005cb9d  mov     r8d, 0Ah
0x14005cba3  lea     rdx, aPublishing; "Publishing"
0x14005cbaa  lea     rcx, [rbp+50h+var_B0]
0x14005cbae  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005cbb3  nop
0x14005cbb4  mov     r9, rbx
0x14005cbb7  lea     r8, [rbp+50h+var_B0]
0x14005cbbb  mov     edx, 1
0x14005cbc0  lea     rcx, [rbp+50h+var_90]
0x14005cbc4  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005cbc9  nop
0x14005cbca  lea     rcx, [rbp+50h+var_B0]
0x14005cbce  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005cbd3  nop
0x14005cbd4  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005cbdb  mov     [rbp+50h+var_68], rax
0x14005cbdf  lea     rcx, [rbp+50h+var_58]
0x14005cbe3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005cbe8  nop
0x14005cbe9  lea     rcx, [rbp+50h+var_D0]
0x14005cbed  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005cbf2  nop
0x14005cbf3  lea     rcx, [rbp+50h+var_90]
0x14005cbf7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005cbfc  mov     edx, 5Ch ; '\'; Ch
0x14005cc01  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005cc08  call    cs:__imp_strrchr
0x14005cc0e  test    rax, rax
0x14005cc11  jz      short loc_14005CC18
0x14005cc13  inc     rax
0x14005cc16  jmp     short loc_14005CC1F
0x14005cc18  lea     rax, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005cc1f  mov     rdx, rax; char *
0x14005cc22  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005cc29  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005cc2e  mov     rbx, rax
0x14005cc31  shl     rbx, 34h
0x14005cc35  mov     ecx, [rsp+150h+var_110]
0x14005cc39  or      rbx, rcx
0x14005cc3c  mov     rax, 1E2700000000h
0x14005cc46  or      rbx, rax
0x14005cc49  jmp     loc_14005D241
0x14005cc4e  cmp     [rsp+150h+var_10C], 0
0x14005cc53  setnz   al
0x14005cc56  mov     [r14], al
0x14005cc59  mov     rcx, [rbx+10h]
0x14005cc5d  mov     rax, rsi
0x14005cc60  sub     rax, rcx
0x14005cc63  cmp     rax, 0Ch
0x14005cc67  jb      loc_14005D28A
0x14005cc6d  cmp     [rbx+18h], r12
0x14005cc71  jbe     short loc_14005CC78
0x14005cc73  mov     r9, [rbx]
0x14005cc76  jmp     short loc_14005CC7B
0x14005cc78  mov     r9, rbx
0x14005cc7b  mov     [rsp+150h+pcbData], 0Ch
0x14005cc84  lea     rax, aLogonrefresh; "LogonRefresh"
0x14005cc8b  mov     [rsp+150h+pvData], rax
0x14005cc90  mov     [rsp+150h+pdwType], rcx
0x14005cc95  lea     rcx, [rbp+50h+var_D0]
0x14005cc99  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14005cc9e  lea     rdx, [rbp+50h+var_D0]
0x14005cca2  lea     rcx, [rsp+150h+lpValue]
0x14005cca7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14005ccac  lea     rcx, [rbp+50h+var_D0]
0x14005ccb0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005ccb5  lea     r8, [rsp+150h+lpValue]
0x14005ccba  cmp     qword ptr [rsp+150h+var_E0+8], r12
0x14005ccbf  cmova   r8, [rsp+150h+lpValue]; lpValue
0x14005ccc5  lea     rax, [rsp+150h+var_108]
0x14005ccca  mov     [rsp+150h+pcbData], rax; pcbData
0x14005cccf  lea     rax, [rsp+150h+var_10C]
0x14005ccd4  mov     [rsp+150h+pvData], rax; pvData
0x14005ccd9  mov     [rsp+150h+pdwType], 0; pdwType
0x14005cce2  xor     edx, edx; lpSubKey
0x14005cce4  lea     r9d, [rdx+10h]; dwFlags
0x14005cce8  mov     rcx, r15; hkey
0x14005cceb  call    cs:__imp_RegGetValueW
0x14005ccf1  mov     [rsp+150h+var_110], eax
0x14005ccf5  test    eax, eax
0x14005ccf7  jz      loc_14005CE49
0x14005ccfd  lea     rdx, aAppvClientPubl_8; "AppV::Client::Publishing::Configuration"...
0x14005cd04  lea     rcx, [rbp+50h+var_90]
0x14005cd08  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005cd0d  mov     [rbp+50h+var_70], 104h
0x14005cd14  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005cd19  xorps   xmm0, xmm0
0x14005cd1c  movups  [rbp+50h+var_B0], xmm0
0x14005cd20  xorps   xmm1, xmm1
0x14005cd23  movdqu  [rbp+50h+var_A0], xmm1
0x14005cd28  mov     r8d, 4Bh ; 'K'
0x14005cd2e  lea     rdx, aCouldnTReadReg; "Couldn't read registry string.\n winerr"...
0x14005cd35  lea     rcx, [rbp+50h+var_B0]
0x14005cd39  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005cd3e  nop
0x14005cd3f  lea     r8, [rbp+50h+var_B0]
0x14005cd43  lea     rdx, [rbp+50h+var_68]
0x14005cd47  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005cd4c  nop
0x14005cd4d  lea     rdx, [rsp+150h+var_110]
0x14005cd52  mov     rcx, rax
0x14005cd55  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005cd5a  cmp     [rdi+18h], r12
0x14005cd5e  jbe     short loc_14005CD63
0x14005cd60  mov     rdi, [rdi]
0x14005cd63  mov     [rsp+150h+var_F8], rdi
0x14005cd68  lea     rdx, [rsp+150h+var_F8]
0x14005cd6d  mov     rcx, rax
0x14005cd70  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005cd75  lea     rcx, [rsp+150h+lpValue]
0x14005cd7a  cmp     qword ptr [rsp+150h+var_E0+8], r12
0x14005cd7f  cmova   rcx, [rsp+150h+lpValue]
0x14005cd85  mov     [rsp+150h+var_100], rcx
0x14005cd8a  lea     rdx, [rsp+150h+var_100]
0x14005cd8f  mov     rcx, rax
0x14005cd92  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005cd97  mov     rbx, rax
0x14005cd9a  xorps   xmm0, xmm0
0x14005cd9d  movups  [rbp+50h+var_D0], xmm0
0x14005cda1  xorps   xmm1, xmm1
0x14005cda4  movdqu  [rbp+50h+var_C0], xmm1
0x14005cda9  mov     r8d, 0Ah
0x14005cdaf  lea     rdx, aPublishing; "Publishing"
0x14005cdb6  lea     rcx, [rbp+50h+var_D0]
0x14005cdba  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005cdbf  nop
0x14005cdc0  mov     r9, rbx
0x14005cdc3  lea     r8, [rbp+50h+var_D0]
0x14005cdc7  mov     edx, 1
0x14005cdcc  lea     rcx, [rbp+50h+var_90]
0x14005cdd0  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005cdd5  nop
0x14005cdd6  lea     rcx, [rbp+50h+var_D0]
0x14005cdda  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005cddf  nop
0x14005cde0  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005cde7  mov     [rbp+50h+var_68], rax
0x14005cdeb  lea     rcx, [rbp+50h+var_58]
0x14005cdef  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005cdf4  nop
0x14005cdf5  lea     rcx, [rbp+50h+var_B0]
0x14005cdf9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005cdfe  nop
0x14005cdff  lea     rcx, [rbp+50h+var_90]
0x14005ce03  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005ce08  mov     edx, 5Ch ; '\'; Ch
0x14005ce0d  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005ce14  call    cs:__imp_strrchr
0x14005ce1a  test    rax, rax
0x14005ce1d  jz      short loc_14005CE24
0x14005ce1f  inc     rax
0x14005ce22  jmp     short loc_14005CE2B
0x14005ce24  lea     rax, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005ce2b  mov     rdx, rax; char *
0x14005ce2e  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005ce35  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005ce3a  mov     rcx, 202700000000h
0x14005ce44  jmp     loc_14005D233
0x14005ce49  cmp     [rsp+150h+var_10C], 0
0x14005ce4e  setnz   al
0x14005ce51  mov     [r14+1], al
0x14005ce55  mov     rcx, [rbx+10h]
0x14005ce59  mov     rax, rsi
0x14005ce5c  sub     rax, rcx
0x14005ce5f  cmp     rax, 17h
0x14005ce63  jb      loc_14005D28A
0x14005ce69  cmp     [rbx+18h], r12
0x14005ce6d  jbe     short loc_14005CE74
0x14005ce6f  mov     r9, [rbx]
0x14005ce72  jmp     short loc_14005CE77
0x14005ce74  mov     r9, rbx
0x14005ce77  mov     [rsp+150h+pcbData], 17h
0x14005ce80  lea     rax, aPeriodicrefres_0; "PeriodicRefreshInterval"
0x14005ce87  mov     [rsp+150h+pvData], rax
0x14005ce8c  mov     [rsp+150h+pdwType], rcx
0x14005ce91  lea     rcx, [rbp+50h+var_D0]
0x14005ce95  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14005ce9a  lea     rdx, [rbp+50h+var_D0]
0x14005ce9e  lea     rcx, [rsp+150h+lpValue]
0x14005cea3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14005cea8  lea     rcx, [rbp+50h+var_D0]
0x14005ceac  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005ceb1  lea     r8, [rsp+150h+lpValue]
0x14005ceb6  cmp     qword ptr [rsp+150h+var_E0+8], r12
0x14005cebb  cmova   r8, [rsp+150h+lpValue]; lpValue
0x14005cec1  lea     rax, [rsp+150h+var_108]
0x14005cec6  mov     [rsp+150h+pcbData], rax; pcbData
0x14005cecb  lea     rax, [rsp+150h+var_10C]
0x14005ced0  mov     [rsp+150h+pvData], rax; pvData
0x14005ced5  mov     [rsp+150h+pdwType], 0; pdwType
0x14005cede  xor     edx, edx; lpSubKey
0x14005cee0  lea     r9d, [rdx+10h]; dwFlags
0x14005cee4  mov     rcx, r15; hkey
0x14005cee7  call    cs:__imp_RegGetValueW
0x14005ceed  mov     [rsp+150h+var_110], eax
0x14005cef1  test    eax, eax
0x14005cef3  jz      loc_14005D045
0x14005cef9  lea     rdx, aAppvClientPubl_8; "AppV::Client::Publishing::Configuration"...
  ... truncated ...
```
