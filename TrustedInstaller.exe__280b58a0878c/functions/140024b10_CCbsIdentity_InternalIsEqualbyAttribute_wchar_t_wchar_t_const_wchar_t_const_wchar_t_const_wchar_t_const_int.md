# CCbsIdentity::InternalIsEqualbyAttribute(wchar_t *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int *)

- ea: `0x140024b10`
- end: `0x140024e37`
- name: `?InternalIsEqualbyAttribute@CCbsIdentity@@UEAAJPEA_WPEB_W111PEAH@Z`
- size: `807`
- prototype: `__int64 __fastcall(const wchar_t *this, wchar_t *, const wchar_t *, const wchar_t *, wchar_t *String2, wchar_t *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1400023e0`
- `0x140002d78`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x140024b10`

## string_xrefs

- `0x140024ba2`: `onecore\base\cbs\identityutil\cbsidentity.cpp`
- `0x140024c5c`: `No public key token specified`

## pseudocode

```c
__int64 __fastcall CCbsIdentity::InternalIsEqualbyAttribute(
        const wchar_t *this,
        wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        wchar_t *String2,
        wchar_t *a6,
        int *a7)
{
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v14; // rdx
  BOOL v15; // edi
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-38h]
  int v21[2]; // [rsp+30h] [rbp-28h] BYREF
  int v22; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  if ( !a2 )
  {
    v10 = -2147024809;
    v22 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No name specified");
      *(_QWORD *)v21 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v11,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v12 = 124;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentity.cpp",
      (const char *)v10,
      v20);
    return v10;
  }
  if ( !a7 )
  {
    v10 = -2147467261;
    v22 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No is equal result specified");
      *(_QWORD *)v21 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v14,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v12 = 125;
    goto LABEL_5;
  }
  v15 = 0;
  if ( *((_DWORD *)this + 6) )
  {
    if ( *((_DWORD *)this + 194) )
    {
      LOBYTE(v15) = wcsicmp(this + 15, a2) == 0;
    }
    else
    {
      if ( !a3 )
      {
        v10 = -2147024809;
        v22 = -2147024809;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"No public key token specified");
          *(_QWORD *)v21 = &v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v16,
            3,
            (__int64)": {}",
            (__int64)v21);
        }
        v12 = 138;
        goto LABEL_5;
      }
      if ( !a4 )
      {
        v10 = -2147024809;
        v22 = -2147024809;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"No processor specified");
          *(_QWORD *)v21 = &v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v17,
            3,
            (__int64)": {}",
            (__int64)v21);
        }
        v12 = 139;
        goto LABEL_5;
      }
      if ( !String2 )
      {
        v10 = -2147024809;
        v22 = -2147024809;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"No language specified");
          *(_QWORD *)v21 = &v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v18,
            3,
            (__int64)": {}",
            (__int64)v21);
        }
        v12 = 140;
        goto LABEL_5;
      }
      if ( !a6 )
      {
        v10 = -2147024809;
        v22 = -2147024809;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"No version specified");
          *(_QWORD *)v21 = &v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v19,
            3,
            (__int64)": {}",
            (__int64)v21);
        }
        v12 = 141;
        goto LABEL_5;
      }
      if ( !wcsicmp(this + 15, a2)
        && !wcsicmp(this + 292, String2)
        && !wcsicmp(this + 324, a4)
        && !wcsicmp(this + 356, a6) )
      {
        v15 = wcsicmp(this + 275, a3) == 0;
      }
    }
  }
  *a7 = v15;
  return 0;
}

```

## disassembly

```asm
0x140024b10  push    rbp
0x140024b12  push    rbx
0x140024b13  push    rsi
0x140024b14  push    rdi
0x140024b15  push    r12
0x140024b17  push    r13
0x140024b19  push    r14
0x140024b1b  push    r15
0x140024b1d  mov     rbp, rsp
0x140024b20  sub     rsp, 58h
0x140024b24  mov     rax, cs:__security_cookie
0x140024b2b  xor     rax, rsp
0x140024b2e  mov     [rbp+var_18], rax
0x140024b32  mov     r14, [rbp+String2]
0x140024b36  mov     r15, r9
0x140024b39  mov     r12, [rbp+arg_28]
0x140024b3d  mov     r13, r8
0x140024b40  mov     rsi, [rbp+arg_30]
0x140024b44  mov     rbx, rcx
0x140024b47  test    rdx, rdx
0x140024b4a  jnz     short loc_140024BB8
0x140024b4c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024b53  mov     ebx, 80070057h
0x140024b58  mov     [rbp+var_20], ebx
0x140024b5b  test    rcx, rcx
0x140024b5e  jz      short loc_140024B99
0x140024b60  lea     edi, [rdx+3]
0x140024b63  mov     r8d, edi
0x140024b66  lea     r9, aNoNameSpecifie; "No name specified"
0x140024b6d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024b72  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024b79  lea     rax, [rbp+var_20]
0x140024b7d  mov     qword ptr [rbp+var_28], rax
0x140024b81  lea     r9, asc_1400353E8; ": {}"
0x140024b88  lea     rax, [rbp+var_28]
0x140024b8c  mov     r8d, edi
0x140024b8f  mov     qword ptr [rsp+58h+var_38], rax; int
0x140024b94  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024b99  mov     edx, 7Ch ; '|'; void *
0x140024b9e  mov     rcx, [rbp+40h]; this
0x140024ba2  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140024ba9  mov     r9d, ebx; char *
0x140024bac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024bb1  mov     eax, ebx
0x140024bb3  jmp     loc_140024E1A
0x140024bb8  test    rsi, rsi
0x140024bbb  jnz     short loc_140024C13
0x140024bbd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024bc4  mov     ebx, 80004003h
0x140024bc9  mov     [rbp+var_20], ebx
0x140024bcc  test    rcx, rcx
0x140024bcf  jz      short loc_140024C0C
0x140024bd1  lea     edi, [rsi+3]
0x140024bd4  xor     edx, edx
0x140024bd6  mov     r8d, edi
0x140024bd9  lea     r9, aNoIsEqualResul; "No is equal result specified"
0x140024be0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024be5  lea     rcx, [rbp+var_28]
0x140024be9  mov     r8d, edi
0x140024bec  mov     qword ptr [rsp+58h+var_38], rcx
0x140024bf1  lea     rax, [rbp+var_20]
0x140024bf5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024bfc  lea     r9, asc_1400353E8; ": {}"
0x140024c03  mov     qword ptr [rbp+var_28], rax
0x140024c07  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024c0c  mov     edx, 7Dh ; '}'; String2
0x140024c11  jmp     short loc_140024B9E
0x140024c13  xor     edi, edi
0x140024c15  cmp     [rcx+18h], edi
0x140024c18  jz      loc_140024E16
0x140024c1e  cmp     [rcx+308h], edi
0x140024c24  jz      short loc_140024C3A
0x140024c26  add     rcx, 1Eh; String1
0x140024c2a  call    _wcsicmp
0x140024c2f  test    eax, eax
0x140024c31  setz    dil
0x140024c35  jmp     loc_140024E16
0x140024c3a  test    r13, r13
0x140024c3d  jnz     short loc_140024C99
0x140024c3f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024c46  mov     ebx, 80070057h
0x140024c4b  mov     [rbp+var_20], ebx
0x140024c4e  test    rcx, rcx
0x140024c51  jz      short loc_140024C8F
0x140024c53  lea     edi, [r13+3]
0x140024c57  xor     edx, edx
0x140024c59  mov     r8d, edi
0x140024c5c  lea     r9, aNoPublicKeyTok; "No public key token specified"
0x140024c63  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024c68  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024c6f  lea     rax, [rbp+var_20]
0x140024c73  mov     qword ptr [rbp+var_28], rax
0x140024c77  lea     r9, asc_1400353E8; ": {}"
0x140024c7e  lea     rax, [rbp+var_28]
0x140024c82  mov     r8d, edi
0x140024c85  mov     qword ptr [rsp+58h+var_38], rax
0x140024c8a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024c8f  mov     edx, 8Ah
0x140024c94  jmp     loc_140024B9E
0x140024c99  test    r15, r15
0x140024c9c  jnz     short loc_140024CF8
0x140024c9e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024ca5  mov     ebx, 80070057h
0x140024caa  mov     [rbp+var_20], ebx
0x140024cad  test    rcx, rcx
0x140024cb0  jz      short loc_140024CEE
0x140024cb2  lea     edi, [r15+3]
0x140024cb6  xor     edx, edx
0x140024cb8  mov     r8d, edi
0x140024cbb  lea     r9, aNoProcessorSpe; "No processor specified"
0x140024cc2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024cc7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024cce  lea     rax, [rbp+var_20]
0x140024cd2  mov     qword ptr [rbp+var_28], rax
0x140024cd6  lea     r9, asc_1400353E8; ": {}"
0x140024cdd  lea     rax, [rbp+var_28]
0x140024ce1  mov     r8d, edi
0x140024ce4  mov     qword ptr [rsp+58h+var_38], rax
0x140024ce9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024cee  mov     edx, 8Bh
0x140024cf3  jmp     loc_140024B9E
0x140024cf8  test    r14, r14
0x140024cfb  jnz     short loc_140024D57
0x140024cfd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024d04  mov     ebx, 80070057h
0x140024d09  mov     [rbp+var_20], ebx
0x140024d0c  test    rcx, rcx
0x140024d0f  jz      short loc_140024D4D
0x140024d11  lea     edi, [r14+3]
0x140024d15  xor     edx, edx
0x140024d17  mov     r8d, edi
0x140024d1a  lea     r9, aNoLanguageSpec; "No language specified"
0x140024d21  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024d26  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024d2d  lea     rax, [rbp+var_20]
0x140024d31  mov     qword ptr [rbp+var_28], rax
0x140024d35  lea     r9, asc_1400353E8; ": {}"
0x140024d3c  lea     rax, [rbp+var_28]
0x140024d40  mov     r8d, edi
0x140024d43  mov     qword ptr [rsp+58h+var_38], rax
0x140024d48  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024d4d  mov     edx, 8Ch
0x140024d52  jmp     loc_140024B9E
0x140024d57  test    r12, r12
0x140024d5a  jnz     short loc_140024DB7
0x140024d5c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024d63  mov     ebx, 80070057h
0x140024d68  mov     [rbp+var_20], ebx
0x140024d6b  test    rcx, rcx
0x140024d6e  jz      short loc_140024DAD
0x140024d70  lea     edi, [r12+3]
0x140024d75  xor     edx, edx
0x140024d77  mov     r8d, edi
0x140024d7a  lea     r9, aNoVersionSpeci; "No version specified"
0x140024d81  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024d86  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024d8d  lea     rax, [rbp+var_20]
0x140024d91  mov     qword ptr [rbp+var_28], rax
0x140024d95  lea     r9, asc_1400353E8; ": {}"
0x140024d9c  lea     rax, [rbp+var_28]
0x140024da0  mov     r8d, edi
0x140024da3  mov     qword ptr [rsp+58h+var_38], rax
0x140024da8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024dad  mov     edx, 8Dh; String2
0x140024db2  jmp     loc_140024B9E
0x140024db7  add     rcx, 1Eh; String1
0x140024dbb  call    _wcsicmp
0x140024dc0  test    eax, eax
0x140024dc2  jnz     short loc_140024E16
0x140024dc4  lea     rcx, [rbx+248h]; String1
0x140024dcb  mov     rdx, r14; String2
0x140024dce  call    _wcsicmp
0x140024dd3  test    eax, eax
0x140024dd5  jnz     short loc_140024E16
0x140024dd7  lea     rcx, [rbx+288h]; String1
0x140024dde  mov     rdx, r15; String2
0x140024de1  call    _wcsicmp
0x140024de6  test    eax, eax
0x140024de8  jnz     short loc_140024E16
0x140024dea  lea     rcx, [rbx+2C8h]; String1
0x140024df1  mov     rdx, r12; String2
0x140024df4  call    _wcsicmp
0x140024df9  test    eax, eax
0x140024dfb  jnz     short loc_140024E16
0x140024dfd  lea     rcx, [rbx+226h]; String1
0x140024e04  mov     rdx, r13; String2
0x140024e07  call    _wcsicmp
0x140024e0c  test    eax, eax
0x140024e0e  mov     ecx, 1
0x140024e13  cmovz   edi, ecx
0x140024e16  mov     [rsi], edi
0x140024e18  xor     eax, eax
0x140024e1a  mov     rcx, [rbp+var_18]
0x140024e1e  xor     rcx, rsp; StackCookie
0x140024e21  call    __security_check_cookie
0x140024e26  add     rsp, 58h
0x140024e2a  pop     r15
0x140024e2c  pop     r14
0x140024e2e  pop     r13
0x140024e30  pop     r12
0x140024e32  pop     rdi
0x140024e33  pop     rsi
0x140024e34  pop     rbx
0x140024e35  pop     rbp
0x140024e36  retn
```
