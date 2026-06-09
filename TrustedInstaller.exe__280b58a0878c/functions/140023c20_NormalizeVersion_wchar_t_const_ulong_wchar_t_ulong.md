# NormalizeVersion(wchar_t const *,ulong,wchar_t *,ulong)

- ea: `0x140023c20`
- end: `0x140023f5a`
- name: `?NormalizeVersion@@YAJPEB_WKPEA_WK@Z`
- size: `826`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x140022adc`
- `0x140025190`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000580c`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x140023c20`

## string_xrefs

- `0x140023ca5`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`
- `0x140023cf4`: `Failed to copy version to buffer.`

## pseudocode

```c
__int64 __fastcall NormalizeVersion(const wchar_t *a1, __int64 a2, wchar_t *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  int v7; // eax
  _WORD *v8; // r11
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned __int16 *v11; // r10
  __int64 v12; // r8
  int v13; // r9d
  unsigned int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  int v19; // [rsp+20h] [rbp-40h]
  int *v20; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *v21; // [rsp+38h] [rbp-28h] BYREF
  int v22[2]; // [rsp+40h] [rbp-20h] BYREF
  int v23; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v21 = a1;
  if ( !a3 )
  {
    v3 = -2147467261;
    v23 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No result buffer specified");
      *(_QWORD *)v22 = &v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v4,
        3,
        (__int64)": {}",
        (__int64)v22);
    }
    v5 = 265;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
      (const char *)v3,
      v19);
    return v3;
  }
  if ( a1 && *a1 )
  {
    v7 = StringCchCopyW(a3, 0x20u, a1);
    v3 = v7;
    if ( v7 >= 0 )
    {
      v10 = (unsigned __int16)*v8;
      v11 = v8 + 1;
      v12 = 0;
      v13 = 1;
      v14 = 0;
      while ( (_WORD)v10 )
      {
        if ( (_WORD)v10 == 46 )
        {
          if ( !(_DWORD)v12 )
          {
            v3 = -2147024809;
            v22[0] = -2147024809;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                v10,
                v12,
                (__int64)"Invalid empty field found in version: {}",
                (__int64)&v21);
              v20 = v22;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v16,
                3,
                (__int64)": {}",
                (__int64)&v20);
            }
            v5 = 285;
            goto LABEL_5;
          }
          ++v13;
          v12 = 0;
          v14 = 0;
        }
        else
        {
          if ( (unsigned __int16)(v10 - 48) > 9u )
          {
            v3 = -2147024809;
            v22[0] = -2147024809;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                v10,
                v12,
                (__int64)"Invalid non-digit found in version: {}",
                (__int64)&v21);
              v20 = v22;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v18,
                3,
                (__int64)": {}",
                (__int64)&v20);
            }
            v5 = 310;
            goto LABEL_5;
          }
          if ( (_DWORD)v12 != 1 || v14 )
            v12 = (unsigned int)(v12 + 1);
          else
            --v8;
          v14 = (unsigned __int16)v10 + 2 * (5 * v14 - 24);
          if ( v14 > 0xFFFF )
          {
            v3 = -2147024809;
            v22[0] = -2147024809;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                v10,
                v12,
                (__int64)"Numeric overflow in version: {}",
                (__int64)&v21);
              v20 = v22;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v17,
                3,
                (__int64)": {}",
                (__int64)&v20);
            }
            v5 = 305;
            goto LABEL_5;
          }
        }
        *v8++ = v10;
        v10 = *v11++;
      }
      *v8 = 0;
      if ( v13 == 4 )
        return 0;
      v3 = -2147024809;
      v22[0] = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          v10,
          v12,
          (__int64)"Number of fields found did not match expected number of fields in version: {}",
          (__int64)&v21);
        v20 = v22;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v15,
          3,
          (__int64)": {}",
          (__int64)&v20);
      }
      v5 = 322;
    }
    else
    {
      v23 = v7;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy version to buffer.");
        v20 = &v23;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v9,
          3,
          (__int64)": {}",
          (__int64)&v20);
      }
      v5 = 270;
    }
    goto LABEL_5;
  }
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x140023c20  mov     [rsp-8+arg_8], rbx
0x140023c25  mov     [rsp-8+arg_18], rdi
0x140023c2a  push    rbp
0x140023c2b  mov     rbp, rsp
0x140023c2e  sub     rsp, 60h
0x140023c32  mov     rax, cs:__security_cookie
0x140023c39  xor     rax, rsp
0x140023c3c  mov     [rbp+var_10], rax
0x140023c40  xor     edi, edi
0x140023c42  mov     [rbp+var_28], rcx
0x140023c46  mov     r11, r8
0x140023c49  test    r8, r8
0x140023c4c  jnz     short loc_140023CBB
0x140023c4e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023c55  mov     ebx, 80004003h
0x140023c5a  mov     [rbp+var_18], ebx
0x140023c5d  test    rcx, rcx
0x140023c60  jz      short loc_140023C9C
0x140023c62  lea     r9, aNoResultBuffer; "No result buffer specified"
0x140023c69  xor     edx, edx
0x140023c6b  lea     r8d, [r11+3]
0x140023c6f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023c74  lea     rcx, [rbp+var_20]
0x140023c78  mov     qword ptr [rsp+60h+var_40], rcx; int
0x140023c7d  lea     rax, [rbp+var_18]
0x140023c81  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023c88  lea     r9, asc_1400353E8; ": {}"
0x140023c8f  lea     r8d, [rdi+3]
0x140023c93  mov     qword ptr [rbp+var_20], rax
0x140023c97  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023c9c  mov     edx, 109h; void *
0x140023ca1  mov     rcx, [rbp+8]; this
0x140023ca5  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140023cac  mov     r9d, ebx; char *
0x140023caf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023cb4  mov     eax, ebx
0x140023cb6  jmp     loc_140023F3C
0x140023cbb  test    rcx, rcx
0x140023cbe  jz      loc_140023F36
0x140023cc4  cmp     [rcx], di
0x140023cc7  jz      loc_140023F36
0x140023ccd  mov     r8, rcx; wchar_t *
0x140023cd0  mov     edx, 20h ; ' '; unsigned __int64
0x140023cd5  mov     rcx, r11; wchar_t *
0x140023cd8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140023cdd  mov     ebx, eax
0x140023cdf  test    eax, eax
0x140023ce1  jns     short loc_140023D38
0x140023ce3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023cea  mov     [rbp+var_18], eax
0x140023ced  test    rcx, rcx
0x140023cf0  jz      short loc_140023D2E
0x140023cf2  xor     edx, edx
0x140023cf4  lea     r9, aFailedToCopyVe; "Failed to copy version to buffer."
0x140023cfb  lea     r8d, [rdx+3]
0x140023cff  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023d04  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023d0b  lea     rax, [rbp+var_18]
0x140023d0f  mov     [rbp+var_30], rax
0x140023d13  lea     r9, asc_1400353E8; ": {}"
0x140023d1a  lea     rax, [rbp+var_30]
0x140023d1e  mov     r8d, 3
0x140023d24  mov     qword ptr [rsp+60h+var_40], rax
0x140023d29  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023d2e  mov     edx, 10Eh
0x140023d33  jmp     loc_140023CA1
0x140023d38  movzx   edx, word ptr [r11]
0x140023d3c  lea     r10, [r11+2]
0x140023d40  mov     ebx, 1
0x140023d45  mov     r8d, edi
0x140023d48  mov     r9d, ebx
0x140023d4b  mov     ecx, edi
0x140023d4d  jmp     short loc_140023DAF
0x140023d4f  cmp     dx, 2Eh ; '.'
0x140023d53  jnz     short loc_140023D68
0x140023d55  test    r8d, r8d
0x140023d58  jz      loc_140023E1F
0x140023d5e  add     r9d, ebx
0x140023d61  mov     r8d, edi
0x140023d64  mov     ecx, edi
0x140023d66  jmp     short loc_140023D9F
0x140023d68  lea     eax, [rdx-30h]
0x140023d6b  cmp     ax, 9
0x140023d6f  ja      loc_140023ED9
0x140023d75  cmp     r8d, ebx
0x140023d78  jnz     short loc_140023D84
0x140023d7a  test    ecx, ecx
0x140023d7c  jnz     short loc_140023D84
0x140023d7e  sub     r11, 2
0x140023d82  jmp     short loc_140023D87
0x140023d84  add     r8d, ebx
0x140023d87  lea     ecx, [rcx+rcx*4]
0x140023d8a  movzx   eax, dx
0x140023d8d  lea     ecx, [rcx-18h]
0x140023d90  lea     ecx, [rax+rcx*2]
0x140023d93  cmp     ecx, 0FFFFh
0x140023d99  ja      loc_140023E7C
0x140023d9f  mov     [r11], dx
0x140023da3  add     r11, 2
0x140023da7  movzx   edx, word ptr [r10]
0x140023dab  add     r10, 2
0x140023daf  test    dx, dx
0x140023db2  jnz     short loc_140023D4F
0x140023db4  mov     [r11], di
0x140023db8  cmp     r9d, 4
0x140023dbc  jz      loc_140023F3A
0x140023dc2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023dc9  mov     ebx, 80070057h
0x140023dce  mov     [rbp+var_20], ebx
0x140023dd1  test    rcx, rcx
0x140023dd4  jz      short loc_140023E15
0x140023dd6  lea     rax, [rbp+var_28]
0x140023dda  lea     r9, aNumberOfFields; "Number of fields found did not match ex"...
0x140023de1  mov     qword ptr [rsp+60h+var_40], rax
0x140023de6  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140023deb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023df2  lea     rax, [rbp+var_20]
0x140023df6  mov     [rbp+var_30], rax
0x140023dfa  lea     r9, asc_1400353E8; ": {}"
0x140023e01  lea     rax, [rbp+var_30]
0x140023e05  mov     r8d, 3
0x140023e0b  mov     qword ptr [rsp+60h+var_40], rax
0x140023e10  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023e15  mov     edx, 142h
0x140023e1a  jmp     loc_140023CA1
0x140023e1f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023e26  mov     ebx, 80070057h
0x140023e2b  mov     [rbp+var_20], ebx
0x140023e2e  test    rcx, rcx
0x140023e31  jz      short loc_140023E72
0x140023e33  lea     rax, [rbp+var_28]
0x140023e37  lea     r9, aInvalidEmptyFi; "Invalid empty field found in version: {"...
0x140023e3e  mov     qword ptr [rsp+60h+var_40], rax
0x140023e43  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140023e48  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023e4f  lea     rax, [rbp+var_20]
0x140023e53  mov     [rbp+var_30], rax
0x140023e57  lea     r9, asc_1400353E8; ": {}"
0x140023e5e  lea     rax, [rbp+var_30]
0x140023e62  mov     r8d, 3
0x140023e68  mov     qword ptr [rsp+60h+var_40], rax
0x140023e6d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023e72  mov     edx, 11Dh
0x140023e77  jmp     loc_140023CA1
0x140023e7c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023e83  mov     ebx, 80070057h
0x140023e88  mov     [rbp+var_20], ebx
0x140023e8b  test    rcx, rcx
0x140023e8e  jz      short loc_140023ECF
0x140023e90  lea     rax, [rbp+var_28]
0x140023e94  lea     r9, aNumericOverflo; "Numeric overflow in version: {}"
0x140023e9b  mov     qword ptr [rsp+60h+var_40], rax
0x140023ea0  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140023ea5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023eac  lea     rax, [rbp+var_20]
0x140023eb0  mov     [rbp+var_30], rax
0x140023eb4  lea     r9, asc_1400353E8; ": {}"
0x140023ebb  lea     rax, [rbp+var_30]
0x140023ebf  mov     r8d, 3
0x140023ec5  mov     qword ptr [rsp+60h+var_40], rax
0x140023eca  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023ecf  mov     edx, 131h
0x140023ed4  jmp     loc_140023CA1
0x140023ed9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023ee0  mov     ebx, 80070057h
0x140023ee5  mov     [rbp+var_20], ebx
0x140023ee8  test    rcx, rcx
0x140023eeb  jz      short loc_140023F2C
0x140023eed  lea     rax, [rbp+var_28]
0x140023ef1  lea     r9, aInvalidNonDigi; "Invalid non-digit found in version: {}"
0x140023ef8  mov     qword ptr [rsp+60h+var_40], rax
0x140023efd  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140023f02  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023f09  lea     rax, [rbp+var_20]
0x140023f0d  mov     [rbp+var_30], rax
0x140023f11  lea     r9, asc_1400353E8; ": {}"
0x140023f18  lea     rax, [rbp+var_30]
0x140023f1c  mov     r8d, 3
0x140023f22  mov     qword ptr [rsp+60h+var_40], rax
0x140023f27  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023f2c  mov     edx, 136h
0x140023f31  jmp     loc_140023CA1
0x140023f36  mov     [r8], di
0x140023f3a  xor     eax, eax
0x140023f3c  mov     rcx, [rbp+var_10]
0x140023f40  xor     rcx, rsp; StackCookie
0x140023f43  call    __security_check_cookie
0x140023f48  lea     r11, [rsp+60h+var_s0]
0x140023f4d  mov     rbx, [r11+18h]
0x140023f51  mov     rdi, [r11+28h]
0x140023f55  mov     rsp, r11
0x140023f58  pop     rbp
0x140023f59  retn
```
