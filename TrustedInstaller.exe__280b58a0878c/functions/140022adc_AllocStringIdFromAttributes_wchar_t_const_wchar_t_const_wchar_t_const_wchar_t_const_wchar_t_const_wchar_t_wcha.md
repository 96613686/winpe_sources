# AllocStringIdFromAttributes(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t,wchar_t * *)

- ea: `0x140022adc`
- end: `0x140022ed5`
- name: `?AllocStringIdFromAttributes@@YAJPEB_W0000_WPEAPEA_W@Z`
- size: `1017`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t *, wchar_t *, wchar_t *, wchar_t *, wchar_t, wchar_t **)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140023280`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x1400054b0`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x14001cfc4`
- `0x140022adc`
- `0x1400236fc`
- `0x1400238c8`
- `0x140023a48`
- `0x140023c20`
- `0x140024568`

## string_xrefs

- `0x140022bc6`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`
- `0x140022c67`: `Failed to validate component name: {}`
- `0x140022cd4`: `Failed to normalize public key token: {}`

## pseudocode

```c
__int64 __fastcall AllocStringIdFromAttributes(
        const wchar_t *a1,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4,
        wchar_t *a5,
        wchar_t a6,
        wchar_t **a7)
{
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned int v28; // r9d
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  wchar_t *v34; // [rsp+20h] [rbp-E0h]
  int v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v36; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v37; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v38; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v39; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v40; // [rsp+B0h] [rbp-50h] BYREF
  int v41; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t v42[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v43; // [rsp+D8h] [rbp-28h]
  __int16 v44; // [rsp+E8h] [rbp-18h]
  wchar_t v45[32]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t v46[32]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t v47[32]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v39 = a5;
  v40 = a1;
  v36 = a2;
  v38 = a3;
  v37 = a4;
  v44 = 0;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  memset_0(v46, 0, sizeof(v46));
  memset_0(v47, 0, sizeof(v47));
  memset_0(v45, 0, sizeof(v45));
  if ( !a1 )
  {
    v8 = -2147024809;
    v41 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No name specified");
      *(_QWORD *)v35 = &v41;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v35);
    }
    v10 = 580;
    goto LABEL_5;
  }
  if ( !a7 )
  {
    v8 = -2147467261;
    v41 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string id result specified");
      *(_QWORD *)v35 = &v41;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v35);
    }
    v10 = 581;
    goto LABEL_5;
  }
  *a7 = 0;
  v13 = ValidateComponentName(a1, 0x7Eu);
  v8 = v13;
  if ( v13 < 0 )
  {
    v41 = v13;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        v14,
        v15,
        (__int64)"Failed to validate component name: {}",
        (__int64)&v40);
      *(_QWORD *)v35 = &v41;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v16,
        3,
        (__int64)": {}",
        (__int64)v35);
    }
    v10 = 588;
    goto LABEL_5;
  }
  v17 = NormalizePublicKeyToken(v36, v42, v15);
  v8 = v17;
  if ( v17 < 0 )
  {
    v41 = v17;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        v18,
        v19,
        (__int64)"Failed to normalize public key token: {}",
        (__int64)&v36);
      *(_QWORD *)v35 = &v41;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v20,
        3,
        (__int64)": {}",
        (__int64)v35);
    }
    v10 = 592;
    goto LABEL_5;
  }
  v21 = NormalizeLanguage(v37, v46, v19);
  v8 = v21;
  if ( v21 < 0 )
  {
    v41 = v21;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        v22,
        v23,
        (__int64)"Failed to normalize language: {}",
        (__int64)&v37);
      *(_QWORD *)v35 = &v41;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v24,
        3,
        (__int64)": {}",
        (__int64)v35);
    }
    v10 = 596;
    goto LABEL_5;
  }
  v25 = NormalizeProcessor(v38, v47, v23);
  v8 = v25;
  if ( v25 < 0 )
  {
    v41 = v25;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        v26,
        v27,
        (__int64)"Failed to normalize processor: {}",
        (__int64)&v38);
      *(_QWORD *)v35 = &v41;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v29,
        3,
        (__int64)": {}",
        (__int64)v35);
    }
    v10 = 600;
    goto LABEL_5;
  }
  v30 = NormalizeVersion(v39, v26, v45, v28);
  v8 = v30;
  if ( v30 < 0 )
  {
    v41 = v30;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        v31,
        v32,
        (__int64)"Failed to normalize version: {}",
        (__int64)&v39);
      *(_QWORD *)v35 = &v41;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v33,
        3,
        (__int64)": {}",
        (__int64)v35);
    }
    v10 = 604;
    goto LABEL_5;
  }
  v34 = v42;
  v8 = SczAllocFormatted(a7, L"%ws%wc%ws%wc%ws%wc%ws%wc%ws", v40, 126);
  if ( v8 < 0 )
  {
    v10 = 621;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
      (const char *)(unsigned int)v8,
      (int)v34);
    return (unsigned int)v8;
  }
  return 0;
}

```

## disassembly

```asm
0x140022adc  push    rbp
0x140022ade  push    rbx
0x140022adf  push    rsi
0x140022ae0  push    rdi
0x140022ae1  lea     rbp, [rsp-0C8h]
0x140022ae9  sub     rsp, 1C8h
0x140022af0  mov     rax, cs:__security_cookie
0x140022af7  xor     rax, rsp
0x140022afa  mov     [rbp+0E0h+var_30], rax
0x140022b01  mov     rax, [rbp+0E0h+arg_20]
0x140022b08  xorps   xmm0, xmm0
0x140022b0b  mov     rdi, [rbp+0E0h+arg_30]
0x140022b12  mov     rbx, rcx
0x140022b15  mov     [rbp+0E0h+var_140], rax
0x140022b19  xor     eax, eax
0x140022b1b  mov     [rbp+0E0h+var_130], rcx
0x140022b1f  lea     rcx, [rbp+0E0h+var_B0]; void *
0x140022b23  mov     [rsp+1E0h+var_170], rdx
0x140022b28  xor     edx, edx; Val
0x140022b2a  mov     [rbp+0E0h+var_150], r8
0x140022b2e  lea     esi, [rax+40h]
0x140022b31  mov     [rbp+0E0h+var_160], r9
0x140022b35  mov     r8d, esi; Size
0x140022b38  mov     [rbp+0E0h+var_F8], ax
0x140022b3c  movups  xmmword ptr [rbp+0E0h+var_118], xmm0
0x140022b40  movups  [rbp+0E0h+var_108], xmm0
0x140022b44  call    memset_0
0x140022b49  mov     r8d, esi; Size
0x140022b4c  lea     rcx, [rbp+0E0h+var_70]; void *
0x140022b50  xor     edx, edx; Val
0x140022b52  call    memset_0
0x140022b57  mov     r8d, esi; Size
0x140022b5a  lea     rcx, [rbp+0E0h+var_F0]; void *
0x140022b5e  xor     edx, edx; Val
0x140022b60  call    memset_0
0x140022b65  test    rbx, rbx
0x140022b68  jnz     short loc_140022BDC
0x140022b6a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022b71  mov     ebx, 80070057h
0x140022b76  mov     [rbp+0E0h+var_120], ebx
0x140022b79  test    rcx, rcx
0x140022b7c  jz      short loc_140022BBA
0x140022b7e  lea     r9, aNoNameSpecifie; "No name specified"
0x140022b85  xor     edx, edx
0x140022b87  lea     r8d, [rsi-3Dh]
0x140022b8b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140022b90  lea     rcx, [rsp+1E0h+var_180]
0x140022b95  mov     qword ptr [rsp+1E0h+var_1C0], rcx; int
0x140022b9a  lea     rax, [rbp+0E0h+var_120]
0x140022b9e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022ba5  lea     r9, asc_1400353E8; ": {}"
0x140022bac  lea     r8d, [rsi-3Dh]
0x140022bb0  mov     qword ptr [rsp+1E0h+var_180], rax
0x140022bb5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022bba  mov     edx, 244h; void *
0x140022bbf  mov     rcx, [rbp+0E8h]; this
0x140022bc6  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140022bcd  mov     r9d, ebx; char *
0x140022bd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022bd5  mov     eax, ebx
0x140022bd7  jmp     loc_140022EBA
0x140022bdc  test    rdi, rdi
0x140022bdf  jnz     short loc_140022C38
0x140022be1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022be8  mov     ebx, 80004003h
0x140022bed  mov     [rbp+0E0h+var_120], ebx
0x140022bf0  test    rcx, rcx
0x140022bf3  jz      short loc_140022C31
0x140022bf5  lea     r9, aNoStringIdResu; "No string id result specified"
0x140022bfc  xor     edx, edx
0x140022bfe  lea     r8d, [rdi+3]
0x140022c02  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140022c07  lea     rcx, [rsp+1E0h+var_180]
0x140022c0c  mov     qword ptr [rsp+1E0h+var_1C0], rcx
0x140022c11  lea     rax, [rbp+0E0h+var_120]
0x140022c15  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022c1c  lea     r9, asc_1400353E8; ": {}"
0x140022c23  lea     r8d, [rdi+3]
0x140022c27  mov     qword ptr [rsp+1E0h+var_180], rax
0x140022c2c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022c31  mov     edx, 245h
0x140022c36  jmp     short loc_140022BBF
0x140022c38  mov     esi, 7Eh ; '~'
0x140022c3d  mov     qword ptr [rdi], 0
0x140022c44  mov     edx, esi; wchar_t
0x140022c46  mov     rcx, rbx; wchar_t *
0x140022c49  call    ?ValidateComponentName@@YAJPEB_W_W@Z; ValidateComponentName(wchar_t const *,wchar_t)
0x140022c4e  mov     ebx, eax
0x140022c50  test    eax, eax
0x140022c52  jns     short loc_140022CAC
0x140022c54  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022c5b  mov     [rbp+0E0h+var_120], eax
0x140022c5e  test    rcx, rcx
0x140022c61  jz      short loc_140022CA2
0x140022c63  lea     rax, [rbp+0E0h+var_130]
0x140022c67  lea     r9, aFailedToValida; "Failed to validate component name: {}"
0x140022c6e  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022c73  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140022c78  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022c7f  lea     rax, [rbp+0E0h+var_120]
0x140022c83  mov     qword ptr [rsp+1E0h+var_180], rax
0x140022c88  lea     r9, asc_1400353E8; ": {}"
0x140022c8f  lea     rax, [rsp+1E0h+var_180]
0x140022c94  lea     r8d, [rsi-7Bh]
0x140022c98  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022c9d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022ca2  mov     edx, 24Ch
0x140022ca7  jmp     loc_140022BBF
0x140022cac  mov     rcx, [rsp+1E0h+var_170]; wchar_t *
0x140022cb1  lea     rdx, [rbp+0E0h+var_118]; wchar_t *
0x140022cb5  call    ?NormalizePublicKeyToken@@YAJPEB_WPEA_WK@Z; NormalizePublicKeyToken(wchar_t const *,wchar_t *,ulong)
0x140022cba  mov     ebx, eax
0x140022cbc  test    eax, eax
0x140022cbe  jns     short loc_140022D1B
0x140022cc0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022cc7  mov     [rbp+0E0h+var_120], eax
0x140022cca  test    rcx, rcx
0x140022ccd  jz      short loc_140022D11
0x140022ccf  lea     rax, [rsp+1E0h+var_170]
0x140022cd4  lea     r9, aFailedToNormal_1; "Failed to normalize public key token: {"...
0x140022cdb  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022ce0  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140022ce5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022cec  lea     rax, [rbp+0E0h+var_120]
0x140022cf0  mov     qword ptr [rsp+1E0h+var_180], rax
0x140022cf5  lea     r9, asc_1400353E8; ": {}"
0x140022cfc  lea     rax, [rsp+1E0h+var_180]
0x140022d01  mov     r8d, 3
0x140022d07  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022d0c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022d11  mov     edx, 250h
0x140022d16  jmp     loc_140022BBF
0x140022d1b  mov     rcx, [rbp+0E0h+var_160]; wchar_t *
0x140022d1f  lea     rdx, [rbp+0E0h+var_B0]; wchar_t *
0x140022d23  call    ?NormalizeLanguage@@YAJPEB_WPEA_WK@Z; NormalizeLanguage(wchar_t const *,wchar_t *,ulong)
0x140022d28  mov     ebx, eax
0x140022d2a  test    eax, eax
0x140022d2c  jns     short loc_140022D88
0x140022d2e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022d35  mov     [rbp+0E0h+var_120], eax
0x140022d38  test    rcx, rcx
0x140022d3b  jz      short loc_140022D7E
0x140022d3d  lea     rax, [rbp+0E0h+var_160]
0x140022d41  lea     r9, aFailedToNormal_0; "Failed to normalize language: {}"
0x140022d48  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022d4d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140022d52  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022d59  lea     rax, [rbp+0E0h+var_120]
0x140022d5d  mov     qword ptr [rsp+1E0h+var_180], rax
0x140022d62  lea     r9, asc_1400353E8; ": {}"
0x140022d69  lea     rax, [rsp+1E0h+var_180]
0x140022d6e  mov     r8d, 3
0x140022d74  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022d79  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022d7e  mov     edx, 254h
0x140022d83  jmp     loc_140022BBF
0x140022d88  mov     rcx, [rbp+0E0h+var_150]; wchar_t *
0x140022d8c  lea     rdx, [rbp+0E0h+var_70]; wchar_t *
0x140022d90  call    ?NormalizeProcessor@@YAJPEB_WPEA_WK@Z; NormalizeProcessor(wchar_t const *,wchar_t *,ulong)
0x140022d95  mov     ebx, eax
0x140022d97  test    eax, eax
0x140022d99  jns     short loc_140022DF5
0x140022d9b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022da2  mov     [rbp+0E0h+var_120], eax
0x140022da5  test    rcx, rcx
0x140022da8  jz      short loc_140022DEB
0x140022daa  lea     rax, [rbp+0E0h+var_150]
0x140022dae  lea     r9, aFailedToNormal; "Failed to normalize processor: {}"
0x140022db5  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022dba  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140022dbf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022dc6  lea     rax, [rbp+0E0h+var_120]
0x140022dca  mov     qword ptr [rsp+1E0h+var_180], rax
0x140022dcf  lea     r9, asc_1400353E8; ": {}"
0x140022dd6  lea     rax, [rsp+1E0h+var_180]
0x140022ddb  mov     r8d, 3
0x140022de1  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022de6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022deb  mov     edx, 258h
0x140022df0  jmp     loc_140022BBF
0x140022df5  mov     rcx, [rbp+0E0h+var_140]; wchar_t *
0x140022df9  lea     r8, [rbp+0E0h+var_F0]; wchar_t *
0x140022dfd  call    ?NormalizeVersion@@YAJPEB_WKPEA_WK@Z; NormalizeVersion(wchar_t const *,ulong,wchar_t *,ulong)
0x140022e02  mov     ebx, eax
0x140022e04  test    eax, eax
0x140022e06  jns     short loc_140022E62
0x140022e08  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022e0f  mov     [rbp+0E0h+var_120], eax
0x140022e12  test    rcx, rcx
0x140022e15  jz      short loc_140022E58
0x140022e17  lea     rax, [rbp+0E0h+var_140]
0x140022e1b  lea     r9, aFailedToNormal_2; "Failed to normalize version: {}"
0x140022e22  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022e27  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140022e2c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022e33  lea     rax, [rbp+0E0h+var_120]
0x140022e37  mov     qword ptr [rsp+1E0h+var_180], rax
0x140022e3c  lea     r9, asc_1400353E8; ": {}"
0x140022e43  lea     rax, [rsp+1E0h+var_180]
0x140022e48  mov     r8d, 3
0x140022e4e  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022e53  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022e58  mov     edx, 25Ch
0x140022e5d  jmp     loc_140022BBF
0x140022e62  mov     r8, [rbp+0E0h+var_130]
0x140022e66  lea     rax, [rbp+0E0h+var_F0]
0x140022e6a  mov     [rsp+1E0h+var_190], rax
0x140022e6f  lea     rdx, aWsWcWsWcWsWcWs; "%ws%wc%ws%wc%ws%wc%ws%wc%ws"
0x140022e76  mov     [rsp+1E0h+var_198], esi
0x140022e7a  lea     rax, [rbp+0E0h+var_B0]
0x140022e7e  mov     [rsp+1E0h+var_1A0], rax
0x140022e83  mov     r9d, esi
0x140022e86  mov     [rsp+1E0h+var_1A8], esi
0x140022e8a  lea     rax, [rbp+0E0h+var_70]
0x140022e8e  mov     [rsp+1E0h+var_1B0], rax
0x140022e93  mov     rcx, rdi
0x140022e96  lea     rax, [rbp+0E0h+var_118]
0x140022e9a  mov     [rsp+1E0h+var_1B8], esi
0x140022e9e  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x140022ea3  call    SczAllocFormatted
0x140022ea8  mov     ebx, eax
0x140022eaa  test    eax, eax
0x140022eac  jns     short loc_140022EB8
0x140022eae  mov     edx, 26Dh
0x140022eb3  jmp     loc_140022BBF
0x140022eb8  xor     eax, eax
0x140022eba  mov     rcx, [rbp+0E0h+var_30]
0x140022ec1  xor     rcx, rsp; StackCookie
0x140022ec4  call    __security_check_cookie
0x140022ec9  add     rsp, 1C8h
0x140022ed0  pop     rdi
0x140022ed1  pop     rsi
0x140022ed2  pop     rbx
0x140022ed3  pop     rbp
0x140022ed4  retn
```
