# GetQuickIdentity(wchar_t const *,wchar_t * *)

- ea: `0x140023280`
- end: `0x1400236f4`
- name: `?GetQuickIdentity@@YAJPEB_WPEAPEA_W@Z`
- size: `1140`
- prototype: `__int64 __fastcall(const wchar_t *Str, wchar_t **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x140013414`
- `0x140013724`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x140022adc`
- `0x140022edc`
- `0x140023280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1400233eb`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1400233eb`

## string_xrefs

- `0x140023314`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`
- `0x1400232cd`: `No package manifest specified`
- `0x140023487`: `Failed to copy name`
- `0x1400234fd`: `Failed to copy language`
- `0x140023573`: `Failed to copy publicKeyToken`
- `0x14002354c`: `publicKeyToken`
- `0x1400235e9`: `Failed to copy processorArchitecture`
- `0x14002365d`: `Failed to copy version`

## pseudocode

```c
__int64 __fastcall GetQuickIdentity(const wchar_t *Str, wchar_t **a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // rdx
  wchar_t *v9; // rax
  const wchar_t *v10; // rbx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  int v22; // [rsp+20h] [rbp-E0h]
  wchar_t v23; // [rsp+28h] [rbp-D8h]
  int v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v26[256]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v27[256]; // [rsp+250h] [rbp+150h] BYREF
  wchar_t v28[256]; // [rsp+450h] [rbp+350h] BYREF
  wchar_t v29[256]; // [rsp+650h] [rbp+550h] BYREF
  wchar_t v30[256]; // [rsp+850h] [rbp+750h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A78h] [rbp+978h]

  if ( !Str )
  {
    v4 = -2147024809;
    v25 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No package manifest specified");
      *(_QWORD *)v24 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v24);
    }
    v6 = 792;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
      (const char *)v4,
      v22);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    v25 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No identity result specified");
      *(_QWORD *)v24 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v24);
    }
    v6 = 793;
    goto LABEL_5;
  }
  memset_0(v30, 0, 0x1FEu);
  memset_0(v29, 0, 0x1FEu);
  memset_0(v28, 0, 0x1FEu);
  memset_0(v27, 0, 0x1FEu);
  memset_0(v26, 0, 0x1FEu);
  v9 = wcsstr(Str, L"assemblyIdentity");
  v10 = v9;
  if ( !v9 )
  {
    v4 = -2147024809;
    v25 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to find assemblyidentity.");
      *(_QWORD *)v24 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v11,
        3,
        (__int64)": {}",
        (__int64)v24);
    }
    v6 = 802;
    goto LABEL_5;
  }
  v12 = CopyStringConent(v9, L"name", v30);
  v4 = v12;
  if ( v12 < 0 )
  {
    v25 = v12;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy name");
      *(_QWORD *)v24 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v13,
        3,
        (__int64)": {}",
        (__int64)v24);
    }
    v6 = 804;
    goto LABEL_5;
  }
  v14 = CopyStringConent(v10, L"language", v27);
  v4 = v14;
  if ( v14 < 0 )
  {
    v25 = v14;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy language");
      *(_QWORD *)v24 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v15,
        3,
        (__int64)": {}",
        (__int64)v24);
    }
    v6 = 807;
    goto LABEL_5;
  }
  v16 = CopyStringConent(v10, L"publicKeyToken", v29);
  v4 = v16;
  if ( v16 < 0 )
  {
    v25 = v16;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy publicKeyToken");
      *(_QWORD *)v24 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v17,
        3,
        (__int64)": {}",
        (__int64)v24);
    }
    v6 = 811;
    goto LABEL_5;
  }
  v18 = CopyStringConent(v10, L"processorArchitecture", v28);
  v4 = v18;
  if ( v18 < 0 )
  {
    v25 = v18;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy processorArchitecture");
      *(_QWORD *)v24 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v19,
        3,
        (__int64)": {}",
        (__int64)v24);
    }
    v6 = 815;
    goto LABEL_5;
  }
  v20 = CopyStringConent(v10, L"version", v26);
  v4 = v20;
  if ( v20 < 0 )
  {
    v25 = v20;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy version");
      *(_QWORD *)v24 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v21,
        3,
        (__int64)": {}",
        (__int64)v24);
    }
    v6 = 818;
    goto LABEL_5;
  }
  return AllocStringIdFromAttributes(v30, v29, v28, v27, v26, v23, a2);
}

```

## disassembly

```asm
0x140023280  mov     [rsp-8+arg_10], rbx
0x140023285  push    rbp
0x140023286  push    rsi
0x140023287  push    rdi
0x140023288  lea     rbp, [rsp-960h]
0x140023290  sub     rsp, 0A60h
0x140023297  mov     rax, cs:__security_cookie
0x14002329e  xor     rax, rsp
0x1400232a1  mov     [rbp+970h+var_20], rax
0x1400232a8  mov     rsi, rdx
0x1400232ab  mov     rbx, rcx
0x1400232ae  test    rcx, rcx
0x1400232b1  jnz     short loc_14002332A
0x1400232b3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400232ba  mov     edi, 80070057h
0x1400232bf  mov     [rsp+0A70h+var_A28], edi
0x1400232c3  test    rcx, rcx
0x1400232c6  jz      short loc_140023308
0x1400232c8  mov     ebx, 3
0x1400232cd  lea     r9, aNoPackageManif; "No package manifest specified"
0x1400232d4  mov     r8d, ebx
0x1400232d7  xor     edx, edx
0x1400232d9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400232de  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400232e5  lea     rax, [rsp+0A70h+var_A28]
0x1400232ea  mov     qword ptr [rsp+0A70h+var_A30], rax
0x1400232ef  lea     r9, asc_1400353E8; ": {}"
0x1400232f6  lea     rax, [rsp+0A70h+var_A30]
0x1400232fb  mov     r8d, ebx
0x1400232fe  mov     [rsp+0A70h+var_A50], rax; int
0x140023303  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023308  mov     edx, 318h; void *
0x14002330d  mov     rcx, [rbp+978h]; this
0x140023314  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x14002331b  mov     r9d, edi; char *
0x14002331e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023323  mov     eax, edi
0x140023325  jmp     loc_1400236D2
0x14002332a  test    rsi, rsi
0x14002332d  jnz     short loc_140023389
0x14002332f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023336  mov     edi, 80004003h
0x14002333b  mov     [rsp+0A70h+var_A28], edi
0x14002333f  test    rcx, rcx
0x140023342  jz      short loc_140023382
0x140023344  lea     ebx, [rsi+3]
0x140023347  xor     edx, edx
0x140023349  mov     r8d, ebx
0x14002334c  lea     r9, aNoIdentityResu; "No identity result specified"
0x140023353  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023358  lea     rcx, [rsp+0A70h+var_A30]
0x14002335d  mov     r8d, ebx
0x140023360  mov     [rsp+0A70h+var_A50], rcx
0x140023365  lea     rax, [rsp+0A70h+var_A28]
0x14002336a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023371  lea     r9, asc_1400353E8; ": {}"
0x140023378  mov     qword ptr [rsp+0A70h+var_A30], rax
0x14002337d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023382  mov     edx, 319h
0x140023387  jmp     short loc_14002330D
0x140023389  mov     edi, 1FEh
0x14002338e  lea     rcx, [rbp+970h+var_220]; void *
0x140023395  mov     r8d, edi; Size
0x140023398  xor     edx, edx; Val
0x14002339a  call    memset_0
0x14002339f  mov     r8d, edi; Size
0x1400233a2  lea     rcx, [rbp+970h+var_420]; void *
0x1400233a9  xor     edx, edx; Val
0x1400233ab  call    memset_0
0x1400233b0  mov     r8d, edi; Size
0x1400233b3  lea     rcx, [rbp+970h+var_620]; void *
0x1400233ba  xor     edx, edx; Val
0x1400233bc  call    memset_0
0x1400233c1  mov     r8d, edi; Size
0x1400233c4  lea     rcx, [rbp+970h+var_820]; void *
0x1400233cb  xor     edx, edx; Val
0x1400233cd  call    memset_0
0x1400233d2  mov     r8d, edi; Size
0x1400233d5  lea     rcx, [rsp+0A70h+var_A20]; void *
0x1400233da  xor     edx, edx; Val
0x1400233dc  call    memset_0
0x1400233e1  lea     rdx, aAssemblyidenti; "assemblyIdentity"
0x1400233e8  mov     rcx, rbx; Str
0x1400233eb  call    cs:__imp_wcsstr
0x1400233f1  mov     rbx, rax
0x1400233f4  test    rax, rax
0x1400233f7  jnz     short loc_140023456
0x1400233f9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023400  mov     edi, 80070057h
0x140023405  mov     [rsp+0A70h+var_A28], edi
0x140023409  test    rcx, rcx
0x14002340c  jz      short loc_14002344C
0x14002340e  lea     ebx, [rax+3]
0x140023411  xor     edx, edx
0x140023413  mov     r8d, ebx
0x140023416  lea     r9, aFailedToFindAs; "Failed to find assemblyidentity."
0x14002341d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023422  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023429  lea     rax, [rsp+0A70h+var_A28]
0x14002342e  mov     qword ptr [rsp+0A70h+var_A30], rax
0x140023433  lea     r9, asc_1400353E8; ": {}"
0x14002343a  lea     rax, [rsp+0A70h+var_A30]
0x14002343f  mov     r8d, ebx
0x140023442  mov     [rsp+0A70h+var_A50], rax
0x140023447  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002344c  mov     edx, 322h
0x140023451  jmp     loc_14002330D
0x140023456  lea     r8, [rbp+970h+var_220]; wchar_t *
0x14002345d  mov     rcx, rbx; wchar_t *
0x140023460  lea     rdx, aName; "name"
0x140023467  call    ?CopyStringConent@@YAJPEB_W0PEA_W_K@Z; CopyStringConent(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x14002346c  mov     edi, eax
0x14002346e  test    eax, eax
0x140023470  jns     short loc_1400234CC
0x140023472  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023479  mov     [rsp+0A70h+var_A28], eax
0x14002347d  test    rcx, rcx
0x140023480  jz      short loc_1400234C2
0x140023482  mov     ebx, 3
0x140023487  lea     r9, aFailedToCopyNa; "Failed to copy name"
0x14002348e  mov     r8d, ebx
0x140023491  xor     edx, edx
0x140023493  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023498  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002349f  lea     rax, [rsp+0A70h+var_A28]
0x1400234a4  mov     qword ptr [rsp+0A70h+var_A30], rax
0x1400234a9  lea     r9, asc_1400353E8; ": {}"
0x1400234b0  lea     rax, [rsp+0A70h+var_A30]
0x1400234b5  mov     r8d, ebx
0x1400234b8  mov     [rsp+0A70h+var_A50], rax
0x1400234bd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400234c2  mov     edx, 324h
0x1400234c7  jmp     loc_14002330D
0x1400234cc  lea     r8, [rbp+970h+var_820]; wchar_t *
0x1400234d3  mov     rcx, rbx; wchar_t *
0x1400234d6  lea     rdx, aLanguage; "language"
0x1400234dd  call    ?CopyStringConent@@YAJPEB_W0PEA_W_K@Z; CopyStringConent(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x1400234e2  mov     edi, eax
0x1400234e4  test    eax, eax
0x1400234e6  jns     short loc_140023542
0x1400234e8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400234ef  mov     [rsp+0A70h+var_A28], eax
0x1400234f3  test    rcx, rcx
0x1400234f6  jz      short loc_140023538
0x1400234f8  mov     ebx, 3
0x1400234fd  lea     r9, aFailedToCopyLa_0; "Failed to copy language"
0x140023504  mov     r8d, ebx
0x140023507  xor     edx, edx
0x140023509  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002350e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023515  lea     rax, [rsp+0A70h+var_A28]
0x14002351a  mov     qword ptr [rsp+0A70h+var_A30], rax
0x14002351f  lea     r9, asc_1400353E8; ": {}"
0x140023526  lea     rax, [rsp+0A70h+var_A30]
0x14002352b  mov     r8d, ebx
0x14002352e  mov     [rsp+0A70h+var_A50], rax
0x140023533  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023538  mov     edx, 327h
0x14002353d  jmp     loc_14002330D
0x140023542  lea     r8, [rbp+970h+var_420]; wchar_t *
0x140023549  mov     rcx, rbx; wchar_t *
0x14002354c  lea     rdx, aPublickeytoken; "publicKeyToken"
0x140023553  call    ?CopyStringConent@@YAJPEB_W0PEA_W_K@Z; CopyStringConent(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x140023558  mov     edi, eax
0x14002355a  test    eax, eax
0x14002355c  jns     short loc_1400235B8
0x14002355e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023565  mov     [rsp+0A70h+var_A28], eax
0x140023569  test    rcx, rcx
0x14002356c  jz      short loc_1400235AE
0x14002356e  mov     ebx, 3
0x140023573  lea     r9, aFailedToCopyPu; "Failed to copy publicKeyToken"
0x14002357a  mov     r8d, ebx
0x14002357d  xor     edx, edx
0x14002357f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023584  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002358b  lea     rax, [rsp+0A70h+var_A28]
0x140023590  mov     qword ptr [rsp+0A70h+var_A30], rax
0x140023595  lea     r9, asc_1400353E8; ": {}"
0x14002359c  lea     rax, [rsp+0A70h+var_A30]
0x1400235a1  mov     r8d, ebx
0x1400235a4  mov     [rsp+0A70h+var_A50], rax
0x1400235a9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400235ae  mov     edx, 32Bh
0x1400235b3  jmp     loc_14002330D
0x1400235b8  lea     r8, [rbp+970h+var_620]; wchar_t *
0x1400235bf  mov     rcx, rbx; wchar_t *
0x1400235c2  lea     rdx, aProcessorarchi; "processorArchitecture"
0x1400235c9  call    ?CopyStringConent@@YAJPEB_W0PEA_W_K@Z; CopyStringConent(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x1400235ce  mov     edi, eax
0x1400235d0  test    eax, eax
0x1400235d2  jns     short loc_14002362E
0x1400235d4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400235db  mov     [rsp+0A70h+var_A28], eax
0x1400235df  test    rcx, rcx
0x1400235e2  jz      short loc_140023624
0x1400235e4  mov     ebx, 3
0x1400235e9  lea     r9, aFailedToCopyPr_0; "Failed to copy processorArchitecture"
0x1400235f0  mov     r8d, ebx
0x1400235f3  xor     edx, edx
0x1400235f5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400235fa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023601  lea     rax, [rsp+0A70h+var_A28]
0x140023606  mov     qword ptr [rsp+0A70h+var_A30], rax
0x14002360b  lea     r9, asc_1400353E8; ": {}"
0x140023612  lea     rax, [rsp+0A70h+var_A30]
0x140023617  mov     r8d, ebx
0x14002361a  mov     [rsp+0A70h+var_A50], rax
0x14002361f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023624  mov     edx, 32Fh
0x140023629  jmp     loc_14002330D
0x14002362e  lea     r8, [rsp+0A70h+var_A20]; wchar_t *
0x140023633  mov     rcx, rbx; wchar_t *
0x140023636  lea     rdx, aVersion; "version"
0x14002363d  call    ?CopyStringConent@@YAJPEB_W0PEA_W_K@Z; CopyStringConent(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x140023642  mov     edi, eax
0x140023644  test    eax, eax
0x140023646  jns     short loc_1400236A2
0x140023648  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002364f  mov     [rsp+0A70h+var_A28], eax
0x140023653  test    rcx, rcx
0x140023656  jz      short loc_140023698
0x140023658  mov     ebx, 3
0x14002365d  lea     r9, aFailedToCopyVe_0; "Failed to copy version"
0x140023664  mov     r8d, ebx
0x140023667  xor     edx, edx
0x140023669  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002366e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023675  lea     rax, [rsp+0A70h+var_A28]
0x14002367a  mov     qword ptr [rsp+0A70h+var_A30], rax
0x14002367f  lea     r9, asc_1400353E8; ": {}"
0x140023686  lea     rax, [rsp+0A70h+var_A30]
0x14002368b  mov     r8d, ebx
0x14002368e  mov     [rsp+0A70h+var_A50], rax
0x140023693  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023698  mov     edx, 332h
0x14002369d  jmp     loc_14002330D
0x1400236a2  lea     rax, [rsp+0A70h+var_A20]
0x1400236a7  mov     [rsp+0A70h+var_A40], rsi; wchar_t **
0x1400236ac  lea     r9, [rbp+970h+var_820]; wchar_t *
0x1400236b3  mov     [rsp+0A70h+var_A50], rax; wchar_t *
0x1400236b8  lea     r8, [rbp+970h+var_620]; wchar_t *
0x1400236bf  lea     rdx, [rbp+970h+var_420]; wchar_t *
0x1400236c6  lea     rcx, [rbp+970h+var_220]; wchar_t *
0x1400236cd  call    ?AllocStringIdFromAttributes@@YAJPEB_W0000_WPEAPEA_W@Z; AllocStringIdFromAttributes(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t,wchar_t * *)
0x1400236d2  mov     rcx, [rbp+970h+var_20]
0x1400236d9  xor     rcx, rsp; StackCookie
0x1400236dc  call    __security_check_cookie
0x1400236e1  mov     rbx, [rsp+0A70h+arg_10]
0x1400236e9  add     rsp, 0A60h
0x1400236f0  pop     rdi
0x1400236f1  pop     rsi
0x1400236f2  pop     rbp
0x1400236f3  retn
```
