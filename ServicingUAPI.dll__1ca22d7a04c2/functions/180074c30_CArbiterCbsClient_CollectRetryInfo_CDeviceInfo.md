# CArbiterCbsClient::CollectRetryInfo(CDeviceInfo *)

- ea: `0x180074c30`
- end: `0x1800751ba`
- name: `?CollectRetryInfo@CArbiterCbsClient@@QEAAJPEAVCDeviceInfo@@@Z`
- size: `1418`
- prototype: `int(CArbiterCbsClient *__hidden this, struct CDeviceInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180091aac`

## callees

- `0x1800031d0`
- `0x180007f68`
- `0x180009750`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x180074c30`
- `0x180077278`
- `0x18008716c`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074ed3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007508c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075155`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007516e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075187`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074ed3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007508c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075155`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007516e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075187`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CArbiterCbsClient::CollectRetryInfo(CArbiterCbsClient *this, struct CDeviceInfo *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // edi
  __int64 v6; // rdx
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  int RetryFeatureList; // eax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rdx
  void *v20; // rcx
  void *v21; // [rsp+28h] [rbp-29h]
  int v22[2]; // [rsp+38h] [rbp-19h] BYREF
  __int128 v23; // [rsp+40h] [rbp-11h] BYREF
  __int128 v24; // [rsp+50h] [rbp-1h]
  __int64 v25; // [rsp+60h] [rbp+Fh]
  int v26; // [rsp+68h] [rbp+17h] BYREF
  wchar_t *v27; // [rsp+70h] [rbp+1Fh] BYREF
  LPVOID v28; // [rsp+78h] [rbp+27h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+2Fh] BYREF
  LPVOID v30; // [rsp+88h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  v25 = -2;
  v4 = *((_QWORD *)this + 2);
  if ( !v4 )
  {
    v5 = -2147024846;
    v26 = -2147024846;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Cannot get capability retry status without an ICbsSession");
      v27 = (wchar_t *)&v26;
      v21 = &v27;
      LOBYTE(v6) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v6,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F5,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)0x80070032LL,
      (int)v21);
    return v5;
  }
  pv = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v4 + 96LL))(v4, 20, &pv);
  v5 = v8;
  if ( v8 < 0 )
  {
    v26 = v8;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get FODRetry flag");
      v27 = (wchar_t *)&v26;
      v21 = &v27;
      LOBYTE(v9) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v9,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F8,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v5,
      (int)v21);
LABEL_10:
    if ( pv )
      CoTaskMemFree(pv);
    return v5;
  }
  if ( pv && *(_WORD *)pv == 49 )
  {
    v27 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, wchar_t **))(**((_QWORD **)this + 2) + 96LL))(
            *((_QWORD *)this + 2),
            19,
            &v27);
    v5 = v10;
    if ( v10 < 0 )
    {
      v26 = v10;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get FODRetry feature list");
        *(_QWORD *)v22 = &v26;
        v21 = v22;
        LOBYTE(v11) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v11,
          3,
          ": {}");
      }
      v12 = 1022;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v5,
        (int)v21);
      if ( v27 )
      {
        CoTaskMemFree(v27);
        v27 = 0;
      }
      goto LABEL_10;
    }
    v13 = v27;
    if ( v27 && *v27 )
    {
      RetryFeatureList = CDeviceInfo::LoadRetryFeatureList(a2, v27);
      v5 = RetryFeatureList;
      if ( RetryFeatureList < 0 )
      {
        v26 = RetryFeatureList;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to load retry feature list");
          *(_QWORD *)v22 = &v26;
          v21 = v22;
          LOBYTE(v15) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v15,
            3,
            ": {}");
        }
        v12 = 1026;
        goto LABEL_18;
      }
      v13 = v27;
    }
    if ( v13 )
      CoTaskMemFree(v13);
  }
  v28 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(**((_QWORD **)this + 2) + 96LL))(
          *((_QWORD *)this + 2),
          21,
          &v28);
  v5 = v16;
  if ( v16 < 0 )
  {
    v26 = v16;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get LCUReoffer flag");
      *(_QWORD *)v22 = &v26;
      v21 = v22;
      LOBYTE(v17) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v17,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x407,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v5,
      (int)v21);
LABEL_33:
    if ( v28 )
    {
      CoTaskMemFree(v28);
      v28 = 0;
    }
    goto LABEL_10;
  }
  if ( v28 && *(_WORD *)v28 == 49 )
  {
    v23 = 0;
    v24 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v23);
    CDeviceInfo::AddValuePair(a2, &v23, L"1");
    std::wstring::~wstring(&v23);
    *((_BYTE *)a2 + 236) = 1;
  }
  v30 = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(**((_QWORD **)this + 2) + 96LL))(
          *((_QWORD *)this + 2),
          28,
          &v30);
  v5 = 0;
  if ( v18 != -2147024809 )
    v5 = v18;
  if ( (v5 & 0x80000000) != 0 )
  {
    v26 = v5;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get DeepReoffer flag");
      *(_QWORD *)v22 = &v26;
      v21 = v22;
      LOBYTE(v19) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v19,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x417,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v5,
      (int)v21);
    if ( v30 )
    {
      CoTaskMemFree(v30);
      v30 = 0;
    }
    goto LABEL_33;
  }
  v20 = v30;
  if ( v30 && *(_WORD *)v30 == 49 )
  {
    v23 = 0;
    v24 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v23);
    CDeviceInfo::AddValuePair(a2, &v23, L"1");
    std::wstring::~wstring(&v23);
    *((_BYTE *)a2 + 236) = 1;
    v23 = 0;
    v24 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v23);
    CDeviceInfo::AddValuePair(a2, &v23, L"1");
    std::wstring::~wstring(&v23);
    *((_BYTE *)a2 + 237) = 1;
    v20 = v30;
  }
  if ( v20 )
  {
    CoTaskMemFree(v20);
    v30 = 0;
  }
  if ( v28 )
  {
    CoTaskMemFree(v28);
    v28 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x180074c30  mov     rax, rsp
0x180074c33  push    rbp
0x180074c34  push    rdi
0x180074c35  push    r14
0x180074c37  lea     rbp, [rax-5Fh]
0x180074c3b  sub     rsp, 90h
0x180074c42  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFEh
0x180074c4a  mov     [rax+18h], rbx
0x180074c4e  mov     [rax+20h], rsi
0x180074c52  mov     rax, cs:__security_cookie
0x180074c59  xor     rax, rsp
0x180074c5c  mov     [rbp+57h+var_18], rax
0x180074c60  mov     rsi, rdx
0x180074c63  mov     rbx, rcx
0x180074c66  mov     rcx, [rcx+10h]
0x180074c6a  xor     r14d, r14d
0x180074c6d  test    rcx, rcx
0x180074c70  jnz     short loc_180074CE3
0x180074c72  mov     edi, 80070032h
0x180074c77  mov     [rbp+57h+var_40], edi
0x180074c7a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180074c81  test    rcx, rcx
0x180074c84  jz      short loc_180074CC4
0x180074c86  lea     r9, aCannotGetCapab; "Cannot get capability retry status with"...
0x180074c8d  lea     ebx, [r14+3]
0x180074c91  mov     r8d, ebx
0x180074c94  xor     edx, edx
0x180074c96  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180074c9b  lea     rax, [rbp+57h+var_40]
0x180074c9f  mov     [rbp+57h+var_38], rax
0x180074ca3  lea     rax, [rbp+57h+var_38]
0x180074ca7  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180074cac  lea     r9, asc_1801CAFB4; ": {}"
0x180074cb3  mov     r8d, ebx
0x180074cb6  mov     dl, 1
0x180074cb8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180074cbf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180074cc4  mov     rcx, [rbp+5Fh]; this
0x180074cc8  mov     r9d, edi; char *
0x180074ccb  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x180074cd2  mov     edx, 3F5h; void *
0x180074cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074cdc  mov     eax, edi
0x180074cde  jmp     loc_180075195
0x180074ce3  mov     [rbp+57h+pv], r14
0x180074ce7  mov     rax, [rcx]
0x180074cea  lea     r8, [rbp+57h+pv]
0x180074cee  mov     edx, 14h
0x180074cf3  mov     rax, [rax+60h]
0x180074cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074cfc  mov     edi, eax
0x180074cfe  test    eax, eax
0x180074d00  jns     loc_180074D8B
0x180074d06  mov     [rbp+57h+var_40], eax
0x180074d09  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180074d10  test    rcx, rcx
0x180074d13  jz      short loc_180074D54
0x180074d15  lea     r9, aFailedToGetFod; "Failed to get FODRetry flag"
0x180074d1c  mov     ebx, 3
0x180074d21  mov     r8d, ebx
0x180074d24  xor     edx, edx
0x180074d26  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180074d2b  lea     rax, [rbp+57h+var_40]
0x180074d2f  mov     [rbp+57h+var_38], rax
0x180074d33  lea     rax, [rbp+57h+var_38]
0x180074d37  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180074d3c  lea     r9, asc_1801CAFB4; ": {}"
0x180074d43  mov     r8d, ebx
0x180074d46  mov     dl, 1
0x180074d48  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180074d4f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180074d54  mov     rcx, [rbp+5Fh]; this
0x180074d58  mov     r9d, edi; char *
0x180074d5b  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x180074d62  mov     edx, 3F8h; void *
0x180074d67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074d6c  nop
0x180074d6d  mov     rcx, [rbp+57h+pv]; pv
0x180074d71  test    rcx, rcx
0x180074d74  jz      loc_180074CDC
0x180074d7a  call    cs:__imp_CoTaskMemFree
0x180074d81  nop     dword ptr [rax+rax+00h]
0x180074d86  jmp     loc_180074CDC
0x180074d8b  mov     rax, [rbp+57h+pv]
0x180074d8f  test    rax, rax
0x180074d92  jz      loc_180074EDF
0x180074d98  cmp     word ptr [rax], 31h ; '1'
0x180074d9c  jnz     loc_180074EDF
0x180074da2  mov     [rbp+57h+var_38], r14
0x180074da6  mov     rcx, [rbx+10h]
0x180074daa  mov     rax, [rcx]
0x180074dad  lea     r8, [rbp+57h+var_38]
0x180074db1  mov     edx, 13h
0x180074db6  mov     rax, [rax+60h]
0x180074dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074dbf  mov     edi, eax
0x180074dc1  test    eax, eax
0x180074dc3  jns     loc_180074E52
0x180074dc9  mov     [rbp+57h+var_40], eax
0x180074dcc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180074dd3  test    rcx, rcx
0x180074dd6  jz      short loc_180074E17
0x180074dd8  lea     r9, aFailedToGetFod_0; "Failed to get FODRetry feature list"
0x180074ddf  mov     ebx, 3
0x180074de4  mov     r8d, ebx
0x180074de7  xor     edx, edx
0x180074de9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180074dee  lea     rax, [rbp+57h+var_40]
0x180074df2  mov     qword ptr [rbp+57h+var_70], rax
0x180074df6  lea     rax, [rbp+57h+var_70]
0x180074dfa  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180074dff  lea     r9, asc_1801CAFB4; ": {}"
0x180074e06  mov     r8d, ebx
0x180074e09  mov     dl, 1
0x180074e0b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180074e12  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180074e17  mov     edx, 3FEh; void *
0x180074e1c  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x180074e23  mov     r9d, edi; char *
0x180074e26  mov     rcx, [rbp+5Fh]; this
0x180074e2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074e2f  nop
0x180074e30  mov     rcx, [rbp+57h+var_38]; pv
0x180074e34  test    rcx, rcx
0x180074e37  jz      loc_180074D6D
0x180074e3d  call    cs:__imp_CoTaskMemFree
0x180074e44  nop     dword ptr [rax+rax+00h]
0x180074e49  mov     [rbp+57h+var_38], r14
0x180074e4d  jmp     loc_180074D6D
0x180074e52  mov     rcx, [rbp+57h+var_38]
0x180074e56  test    rcx, rcx
0x180074e59  jz      short loc_180074ECE
0x180074e5b  cmp     [rcx], r14w
0x180074e5f  jz      short loc_180074ECE
0x180074e61  mov     rdx, rcx; wchar_t *
0x180074e64  mov     rcx, rsi; this
0x180074e67  call    ?LoadRetryFeatureList@CDeviceInfo@@QEAAJQEB_W@Z; CDeviceInfo::LoadRetryFeatureList(wchar_t const * const)
0x180074e6c  mov     edi, eax
0x180074e6e  test    eax, eax
0x180074e70  jns     short loc_180074ECA
0x180074e72  mov     [rbp+57h+var_40], eax
0x180074e75  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180074e7c  test    rcx, rcx
0x180074e7f  jz      short loc_180074EC0
0x180074e81  lea     r9, aFailedToLoadRe_0; "Failed to load retry feature list"
0x180074e88  mov     ebx, 3
0x180074e8d  mov     r8d, ebx
0x180074e90  xor     edx, edx
0x180074e92  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180074e97  lea     rax, [rbp+57h+var_40]
0x180074e9b  mov     qword ptr [rbp+57h+var_70], rax
0x180074e9f  lea     rax, [rbp+57h+var_70]
0x180074ea3  mov     qword ptr [rsp+0A0h+var_80], rax
0x180074ea8  lea     r9, asc_1801CAFB4; ": {}"
0x180074eaf  mov     r8d, ebx
0x180074eb2  mov     dl, 1
0x180074eb4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180074ebb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180074ec0  mov     edx, 402h
0x180074ec5  jmp     loc_180074E1C
0x180074eca  mov     rcx, [rbp+57h+var_38]; pv
0x180074ece  test    rcx, rcx
0x180074ed1  jz      short loc_180074EDF
0x180074ed3  call    cs:__imp_CoTaskMemFree
0x180074eda  nop     dword ptr [rax+rax+00h]
0x180074edf  mov     [rbp+57h+var_30], r14
0x180074ee3  mov     rcx, [rbx+10h]
0x180074ee7  mov     rax, [rcx]
0x180074eea  lea     r8, [rbp+57h+var_30]
0x180074eee  mov     edx, 15h
0x180074ef3  mov     rax, [rax+60h]
0x180074ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074efc  mov     edi, eax
0x180074efe  test    eax, eax
0x180074f00  jns     loc_180074F8F
0x180074f06  mov     [rbp+57h+var_40], eax
0x180074f09  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180074f10  test    rcx, rcx
0x180074f13  jz      short loc_180074F54
0x180074f15  lea     r9, aFailedToGetLcu; "Failed to get LCUReoffer flag"
0x180074f1c  mov     ebx, 3
0x180074f21  mov     r8d, ebx
0x180074f24  xor     edx, edx
0x180074f26  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180074f2b  lea     rax, [rbp+57h+var_40]
0x180074f2f  mov     qword ptr [rbp+57h+var_70], rax
0x180074f33  lea     rax, [rbp+57h+var_70]
0x180074f37  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180074f3c  lea     r9, asc_1801CAFB4; ": {}"
0x180074f43  mov     r8d, ebx
0x180074f46  mov     dl, 1
0x180074f48  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180074f4f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180074f54  mov     rcx, [rbp+5Fh]; this
0x180074f58  mov     r9d, edi; char *
0x180074f5b  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x180074f62  mov     edx, 407h; void *
0x180074f67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074f6c  nop
0x180074f6d  mov     rcx, [rbp+57h+var_30]; pv
0x180074f71  test    rcx, rcx
0x180074f74  jz      loc_180074D6D
0x180074f7a  call    cs:__imp_CoTaskMemFree
0x180074f81  nop     dword ptr [rax+rax+00h]
0x180074f86  mov     [rbp+57h+var_30], r14
0x180074f8a  jmp     loc_180074D6D
0x180074f8f  mov     rax, [rbp+57h+var_30]
0x180074f93  test    rax, rax
0x180074f96  jz      short loc_180074FE8
0x180074f98  cmp     word ptr [rax], 31h ; '1'
0x180074f9c  jnz     short loc_180074FE8
0x180074f9e  xorps   xmm0, xmm0
0x180074fa1  movups  [rbp+57h+var_68], xmm0
0x180074fa5  xorps   xmm1, xmm1
0x180074fa8  movdqu  [rbp+57h+var_58], xmm1
0x180074fad  mov     r8d, 0Ah
0x180074fb3  lea     rdx, aReofferlcu; "ReofferLCU"
0x180074fba  lea     rcx, [rbp+57h+var_68]
0x180074fbe  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180074fc3  nop
0x180074fc4  lea     r8, a1; "1"
0x180074fcb  lea     rdx, [rbp+57h+var_68]
0x180074fcf  mov     rcx, rsi
0x180074fd2  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x180074fd7  nop
0x180074fd8  lea     rcx, [rbp+57h+var_68]; void *
0x180074fdc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180074fe1  mov     byte ptr [rsi+0ECh], 1
0x180074fe8  mov     [rbp+57h+var_20], r14
0x180074fec  mov     rcx, [rbx+10h]
0x180074ff0  mov     rax, [rcx]
0x180074ff3  lea     r8, [rbp+57h+var_20]
0x180074ff7  mov     edx, 1Ch
0x180074ffc  mov     rax, [rax+60h]
0x180075000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075005  mov     edi, r14d
0x180075008  cmp     eax, 80070057h
0x18007500d  cmovnz  edi, eax
0x180075010  test    edi, edi
0x180075012  jns     loc_1800750A1
0x180075018  mov     [rbp+57h+var_40], edi
0x18007501b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180075022  test    rcx, rcx
0x180075025  jz      short loc_180075066
0x180075027  lea     r9, aFailedToGetDee; "Failed to get DeepReoffer flag"
0x18007502e  mov     ebx, 3
0x180075033  mov     r8d, ebx
0x180075036  xor     edx, edx
0x180075038  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007503d  lea     rax, [rbp+57h+var_40]
0x180075041  mov     qword ptr [rbp+57h+var_70], rax
0x180075045  lea     rax, [rbp+57h+var_70]
0x180075049  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x18007504e  lea     r9, asc_1801CAFB4; ": {}"
0x180075055  mov     r8d, ebx
0x180075058  mov     dl, 1
0x18007505a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180075061  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180075066  mov     rcx, [rbp+5Fh]; this
0x18007506a  mov     r9d, edi; char *
0x18007506d  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x180075074  mov     edx, 417h; void *
0x180075079  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007507e  nop
0x18007507f  mov     rcx, [rbp+57h+var_20]; pv
0x180075083  test    rcx, rcx
0x180075086  jz      loc_180074F6D
0x18007508c  call    cs:__imp_CoTaskMemFree
0x180075093  nop     dword ptr [rax+rax+00h]
0x180075098  mov     [rbp+57h+var_20], r14
0x18007509c  jmp     loc_180074F6D
0x1800750a1  mov     rcx, [rbp+57h+var_20]
0x1800750a5  test    rcx, rcx
0x1800750a8  jz      loc_180075150
0x1800750ae  cmp     word ptr [rcx], 31h ; '1'
0x1800750b2  jnz     loc_180075150
0x1800750b8  xorps   xmm0, xmm0
0x1800750bb  movups  [rbp+57h+var_68], xmm0
0x1800750bf  xorps   xmm1, xmm1
0x1800750c2  movdqu  [rbp+57h+var_58], xmm1
0x1800750c7  mov     r8d, 0Ah
0x1800750cd  lea     rdx, aReofferlcu; "ReofferLCU"
0x1800750d4  lea     rcx, [rbp+57h+var_68]
0x1800750d8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800750dd  nop
0x1800750de  lea     r8, a1; "1"
0x1800750e5  lea     rdx, [rbp+57h+var_68]
0x1800750e9  mov     rcx, rsi
0x1800750ec  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x1800750f1  nop
0x1800750f2  lea     rcx, [rbp+57h+var_68]; void *
0x1800750f6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800750fb  mov     byte ptr [rsi+0ECh], 1
0x180075102  xorps   xmm0, xmm0
0x180075105  movups  [rbp+57h+var_68], xmm0
0x180075109  xorps   xmm1, xmm1
0x18007510c  movdqu  [rbp+57h+var_58], xmm1
0x180075111  mov     r8d, 0Bh
0x180075117  lea     rdx, aReofferdeep; "ReofferDeep"
0x18007511e  lea     rcx, [rbp+57h+var_68]
  ... truncated ...
```
