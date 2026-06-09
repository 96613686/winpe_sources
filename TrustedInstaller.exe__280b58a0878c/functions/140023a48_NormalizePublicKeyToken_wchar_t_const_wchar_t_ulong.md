# NormalizePublicKeyToken(wchar_t const *,wchar_t *,ulong)

- ea: `0x140023a48`
- end: `0x140023c17`
- name: `?NormalizePublicKeyToken@@YAJPEB_WPEA_WK@Z`
- size: `463`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x140022adc`
- `0x140025190`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x140023a48`

## string_xrefs

- `0x140023acc`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`
- `0x140023bd2`: `Invalid public key token or insufficient buffer for public key token: {}`
- `0x140023b75`: `Invalid public key token provided: {}`

## pseudocode

```c
__int64 __fastcall NormalizePublicKeyToken(const wchar_t *a1, wchar_t *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-30h]
  int v14[2]; // [rsp+30h] [rbp-20h] BYREF
  const wchar_t *v15; // [rsp+38h] [rbp-18h] BYREF
  int v16; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v15 = a1;
  if ( !a2 )
  {
    v4 = -2147467261;
    v16 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No result buffer specified");
      *(_QWORD *)v14 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v6 = 194;
    goto LABEL_5;
  }
  v8 = 0;
  if ( a1 && *a1 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a1[v9] );
    if ( v9 == 16 )
    {
      while ( 1 )
      {
        v10 = a1[v8];
        a2[v8] = v10;
        if ( (unsigned __int16)(v10 - 65) > 5u )
        {
          if ( (unsigned __int16)(v10 - 97) > 5u )
          {
            LOWORD(v10) = v10 - 48;
            if ( (unsigned __int16)v10 > 9u )
            {
              v4 = -2147024809;
              v16 = -2147024809;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (__int64)LogAdapter::g_Logger,
                  v10,
                  (__int64)a1,
                  (__int64)"Invalid public key token provided: {}",
                  (__int64)&v15);
                *(_QWORD *)v14 = &v16;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  v11,
                  3,
                  (__int64)": {}",
                  (__int64)v14);
              }
              v6 = 216;
              goto LABEL_5;
            }
          }
        }
        else
        {
          a2[v8] = v10 + 32;
        }
        if ( (unsigned __int64)++v8 >= 0x10 )
          goto LABEL_16;
      }
    }
    v4 = -2147024809;
    v16 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        (__int64)a2,
        (__int64)a1,
        (__int64)"Invalid public key token or insufficient buffer for public key token: {}",
        (__int64)&v15);
      *(_QWORD *)v14 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v6 = 203;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
      (const char *)v4,
      v13);
    return v4;
  }
  else
  {
LABEL_16:
    a2[v8] = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x140023a48  mov     [rsp-8+arg_10], rbx
0x140023a4d  push    rbp
0x140023a4e  mov     rbp, rsp
0x140023a51  sub     rsp, 50h
0x140023a55  mov     rax, cs:__security_cookie
0x140023a5c  xor     rax, rsp
0x140023a5f  mov     [rbp+var_8], rax
0x140023a63  xor     r10d, r10d
0x140023a66  mov     [rbp+var_18], rcx
0x140023a6a  mov     r9, rdx
0x140023a6d  mov     r8, rcx
0x140023a70  test    rdx, rdx
0x140023a73  jnz     short loc_140023ADF
0x140023a75  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023a7c  mov     ebx, 80004003h
0x140023a81  mov     [rbp+var_10], ebx
0x140023a84  test    rcx, rcx
0x140023a87  jz      short loc_140023AC3
0x140023a89  lea     r9, aNoResultBuffer; "No result buffer specified"
0x140023a90  lea     r8d, [rdx+3]
0x140023a94  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023a99  lea     rcx, [rbp+var_20]
0x140023a9d  mov     r8d, 3
0x140023aa3  mov     qword ptr [rsp+50h+var_30], rcx; int
0x140023aa8  lea     rax, [rbp+var_10]
0x140023aac  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023ab3  lea     r9, asc_1400353E8; ": {}"
0x140023aba  mov     qword ptr [rbp+var_20], rax
0x140023abe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023ac3  mov     edx, 0C2h; void *
0x140023ac8  mov     rcx, [rbp+8]; this
0x140023acc  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140023ad3  mov     r9d, ebx; char *
0x140023ad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023adb  mov     eax, ebx
0x140023add  jmp     short loc_140023B46
0x140023adf  mov     rcx, r10
0x140023ae2  test    r8, r8
0x140023ae5  jz      short loc_140023B3F
0x140023ae7  cmp     [r8], r10w
0x140023aeb  jz      short loc_140023B3F
0x140023aed  or      rax, 0FFFFFFFFFFFFFFFFh
0x140023af1  inc     rax
0x140023af4  cmp     [r8+rax*2], r10w
0x140023af9  jnz     short loc_140023AF1
0x140023afb  cmp     rax, 10h
0x140023aff  jnz     loc_140023BBA
0x140023b05  movzx   edx, word ptr [r8+rcx*2]
0x140023b0a  mov     [r9+rcx*2], dx
0x140023b0f  lea     eax, [rdx-41h]
0x140023b12  cmp     ax, 5
0x140023b16  ja      short loc_140023B23
0x140023b18  add     dx, 20h ; ' '
0x140023b1c  mov     [r9+rcx*2], dx
0x140023b21  jmp     short loc_140023B36
0x140023b23  lea     eax, [rdx-61h]
0x140023b26  cmp     ax, 5
0x140023b2a  jbe     short loc_140023B36
0x140023b2c  sub     dx, 30h ; '0'
0x140023b30  cmp     dx, 9
0x140023b34  ja      short loc_140023B5D
0x140023b36  inc     rcx
0x140023b39  cmp     rcx, 10h
0x140023b3d  jb      short loc_140023B05
0x140023b3f  mov     [r9+rcx*2], r10w
0x140023b44  xor     eax, eax
0x140023b46  mov     rcx, [rbp+var_8]
0x140023b4a  xor     rcx, rsp; StackCookie
0x140023b4d  call    __security_check_cookie
0x140023b52  mov     rbx, [rsp+50h+arg_10]
0x140023b57  add     rsp, 50h
0x140023b5b  pop     rbp
0x140023b5c  retn
0x140023b5d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023b64  mov     ebx, 80070057h
0x140023b69  mov     [rbp+var_10], ebx
0x140023b6c  test    rcx, rcx
0x140023b6f  jz      short loc_140023BB0
0x140023b71  lea     rax, [rbp+var_18]
0x140023b75  lea     r9, aInvalidPublicK_0; "Invalid public key token provided: {}"
0x140023b7c  mov     qword ptr [rsp+50h+var_30], rax
0x140023b81  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140023b86  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023b8d  lea     rax, [rbp+var_10]
0x140023b91  mov     qword ptr [rbp+var_20], rax
0x140023b95  lea     r9, asc_1400353E8; ": {}"
0x140023b9c  lea     rax, [rbp+var_20]
0x140023ba0  mov     r8d, 3
0x140023ba6  mov     qword ptr [rsp+50h+var_30], rax
0x140023bab  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023bb0  mov     edx, 0D8h
0x140023bb5  jmp     loc_140023AC8
0x140023bba  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023bc1  mov     ebx, 80070057h
0x140023bc6  mov     [rbp+var_10], ebx
0x140023bc9  test    rcx, rcx
0x140023bcc  jz      short loc_140023C0D
0x140023bce  lea     rax, [rbp+var_18]
0x140023bd2  lea     r9, aInvalidPublicK; "Invalid public key token or insufficien"...
0x140023bd9  mov     qword ptr [rsp+50h+var_30], rax
0x140023bde  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140023be3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023bea  lea     rax, [rbp+var_10]
0x140023bee  mov     qword ptr [rbp+var_20], rax
0x140023bf2  lea     r9, asc_1400353E8; ": {}"
0x140023bf9  lea     rax, [rbp+var_20]
0x140023bfd  mov     r8d, 3
0x140023c03  mov     qword ptr [rsp+50h+var_30], rax
0x140023c08  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023c0d  mov     edx, 0CBh
0x140023c12  jmp     loc_140023AC8
```
