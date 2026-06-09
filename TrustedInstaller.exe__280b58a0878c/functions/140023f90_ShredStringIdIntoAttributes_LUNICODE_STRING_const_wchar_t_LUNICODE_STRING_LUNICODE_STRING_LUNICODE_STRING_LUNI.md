# ShredStringIdIntoAttributes(_LUNICODE_STRING const &,wchar_t,_LUNICODE_STRING *,_LUNICODE_STRING *,_LUNICODE_STRING *,_LUNICODE_STRING *,_LUNICODE_STRING *)

- ea: `0x140023f90`
- end: `0x14002431c`
- name: `?ShredStringIdIntoAttributes@@YAJAEBU_LUNICODE_STRING@@_WPEAU1@2222@Z`
- size: `908`
- prototype: `__int64 __fastcall(const struct _LUNICODE_STRING *, wchar_t, struct _LUNICODE_STRING *, struct _LUNICODE_STRING *, struct _LUNICODE_STRING *, struct _LUNICODE_STRING *, struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140024324`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x1400228d8`
- `0x140022a04`
- `0x140023f90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14002404c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14002404c`

## string_xrefs

- `0x1400242e3`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`
- `0x1400241e7`: `Identity contains invalid public key token: {}.`

## pseudocode

```c
__int64 __fastcall ShredStringIdIntoAttributes(
        const struct _LUNICODE_STRING *a1,
        wchar_t a2,
        struct _LUNICODE_STRING *a3,
        struct _LUNICODE_STRING *a4,
        struct _LUNICODE_STRING *a5,
        struct _LUNICODE_STRING *a6,
        struct _LUNICODE_STRING *a7)
{
  __int128 v9; // xmm6
  wchar_t *v10; // rax
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  char v16; // r13
  char v17; // r15
  __int64 v18; // r8
  __int64 v19; // xmm1_8
  __int64 v20; // xmm1_8
  __int64 v21; // xmm1_8
  __int64 v22; // xmm1_8
  __int64 v23; // xmm1_8
  __int64 v24; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  int v28; // [rsp+28h] [rbp-91h]
  char v29; // [rsp+38h] [rbp-81h]
  char v30; // [rsp+39h] [rbp-80h]
  char v31; // [rsp+3Ah] [rbp-7Fh]
  int v32[2]; // [rsp+40h] [rbp-79h] BYREF
  __int128 v33; // [rsp+48h] [rbp-71h] BYREF
  __int64 v34; // [rsp+58h] [rbp-61h]
  int v35; // [rsp+60h] [rbp-59h] BYREF
  wchar_t v36; // [rsp+68h] [rbp-51h] BYREF
  __int128 v37; // [rsp+70h] [rbp-49h] BYREF
  __int64 v38; // [rsp+80h] [rbp-39h]
  __int128 v39; // [rsp+88h] [rbp-31h]
  __int64 v40; // [rsp+98h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+47h]

  v38 = *((_QWORD *)a1 + 2);
  v36 = a2;
  v34 = 0;
  v40 = 0;
  v9 = *(_OWORD *)a1;
  v39 = 0;
  v37 = v9;
  v33 = 0;
  if ( a3 )
  {
    *(_OWORD *)a3 = 0;
    *((_QWORD *)a3 + 2) = 0;
  }
  if ( a4 )
  {
    *(_OWORD *)a4 = 0;
    *((_QWORD *)a4 + 2) = 0;
  }
  if ( a5 )
  {
    *(_OWORD *)a5 = 0;
    *((_QWORD *)a5 + 2) = 0;
  }
  if ( a6 )
  {
    *(_OWORD *)a6 = 0;
    *((_QWORD *)a6 + 2) = 0;
  }
  if ( a7 )
  {
    *(_OWORD *)a7 = 0;
    *((_QWORD *)a7 + 2) = 0;
  }
  v10 = wcschr(L";,=~#@^&'$%", a2);
  v13 = 0;
  if ( v10 )
  {
    v29 = 0;
    v30 = 0;
    v16 = 0;
    v31 = 0;
    v17 = 0;
    if ( (_QWORD)v9 )
    {
      do
      {
        LOBYTE(v13) = v36;
        Windows::StringUtil::TrySplitStringOnFirstAsciiChar<_LUNICODE_STRING>(&v37, v13, &v37, &v33);
        v13 = 0;
        if ( v29 )
        {
          if ( v16 )
          {
            if ( v30 )
            {
              if ( v17 )
              {
                if ( v31 )
                {
                  v35 = -2147024809;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Too many delimiters in string id.");
                    *(_QWORD *)v32 = &v35;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      v26,
                      3,
                      (__int64)": {}",
                      (__int64)v32);
                  }
                  v15 = 456;
                  goto LABEL_49;
                }
                if ( a7 )
                {
                  v23 = v38;
                  *(_OWORD *)a7 = v37;
                  *((_QWORD *)a7 + 2) = v23;
                }
                v31 = 1;
              }
              else
              {
                if ( a6 )
                {
                  v22 = v38;
                  *(_OWORD *)a6 = v37;
                  *((_QWORD *)a6 + 2) = v22;
                }
                v17 = 1;
              }
            }
            else
            {
              if ( a5 )
              {
                v21 = v38;
                *(_OWORD *)a5 = v37;
                *((_QWORD *)a5 + 2) = v21;
              }
              v30 = 1;
            }
          }
          else
          {
            v20 = v38;
            v40 = v38;
            v39 = v37;
            if ( a4 )
            {
              *(_OWORD *)a4 = v37;
              *((_QWORD *)a4 + 2) = v20;
            }
            v16 = 1;
          }
        }
        else
        {
          if ( a3 )
          {
            v19 = v38;
            *(_OWORD *)a3 = v37;
            *((_QWORD *)a3 + 2) = v19;
          }
          v29 = 1;
        }
        v38 = v34;
        v37 = v33;
      }
      while ( (_QWORD)v33 );
      if ( !v17 )
        goto LABEL_46;
      if ( (v39 & 0xFFFFFFFFFFFFFFDFuLL) == 0 )
        return 0;
      v35 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          v18,
          (__int64)"Identity contains invalid public key token: {}.",
          (__int64)&v40);
        *(_QWORD *)v32 = &v35;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v24,
          3,
          (__int64)": {}",
          (__int64)v32);
      }
      v15 = 472;
    }
    else
    {
LABEL_46:
      v35 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Identity missing language.");
        *(_QWORD *)v32 = &v35;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v27,
          3,
          (__int64)": {}",
          (__int64)v32);
      }
      v15 = 466;
    }
  }
  else
  {
    v35 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t>((_DWORD)LogAdapter::g_Logger, 0, v11, v12, (__int64)&v36);
      *(_QWORD *)v32 = &v35;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v14,
        3,
        (__int64)": {}",
        (__int64)v32);
    }
    v15 = 412;
  }
LABEL_49:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
    (const char *)0x80070057LL,
    v28);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140023f90  mov     rax, rsp
0x140023f93  push    rbp
0x140023f94  push    rbx
0x140023f95  push    rsi
0x140023f96  push    rdi
0x140023f97  push    r12
0x140023f99  push    r13
0x140023f9b  push    r14
0x140023f9d  push    r15
0x140023f9f  lea     rbp, [rax-47h]
0x140023fa3  sub     rsp, 0B8h
0x140023faa  movaps  xmmword ptr [rax-58h], xmm6
0x140023fae  mov     rax, cs:__security_cookie
0x140023fb5  xor     rax, rsp
0x140023fb8  mov     qword ptr [rbp+3Fh+var_58], rax
0x140023fbc  movsd   xmm0, qword ptr [rcx+10h]
0x140023fc1  xor     eax, eax
0x140023fc3  mov     rbx, [rbp+3Fh+arg_20]
0x140023fc7  xorps   xmm1, xmm1
0x140023fca  mov     rdi, [rbp+3Fh+arg_28]
0x140023fce  mov     r14, r9
0x140023fd1  mov     rsi, [rbp+3Fh+arg_30]
0x140023fd5  mov     r12, r8
0x140023fd8  movsd   [rbp+3Fh+var_78], xmm0
0x140023fdd  xorps   xmm0, xmm0
0x140023fe0  mov     [rbp+3Fh+var_90], dx
0x140023fe4  mov     [rbp+3Fh+var_A0], rax
0x140023fe8  mov     [rbp+3Fh+var_60], rax
0x140023fec  movups  xmm6, xmmword ptr [rcx]
0x140023fef  movups  [rbp+3Fh+var_70], xmm0
0x140023ff3  movups  [rbp+3Fh+var_88], xmm6
0x140023ff7  movups  [rbp+3Fh+var_B0], xmm1
0x140023ffb  test    r8, r8
0x140023ffe  jz      short loc_140024008
0x140024000  movups  xmmword ptr [r8], xmm0
0x140024004  mov     [r8+10h], rax
0x140024008  xorps   xmm0, xmm0
0x14002400b  test    r14, r14
0x14002400e  jz      short loc_140024018
0x140024010  movups  xmmword ptr [r9], xmm0
0x140024014  mov     [r9+10h], rax
0x140024018  xorps   xmm0, xmm0
0x14002401b  test    rbx, rbx
0x14002401e  jz      short loc_140024027
0x140024020  movups  xmmword ptr [rbx], xmm0
0x140024023  mov     [rbx+10h], rax
0x140024027  xorps   xmm0, xmm0
0x14002402a  test    rdi, rdi
0x14002402d  jz      short loc_140024036
0x14002402f  movups  xmmword ptr [rdi], xmm0
0x140024032  mov     [rdi+10h], rax
0x140024036  xorps   xmm0, xmm0
0x140024039  test    rsi, rsi
0x14002403c  jz      short loc_140024045
0x14002403e  movups  xmmword ptr [rsi], xmm0
0x140024041  mov     [rsi+10h], rax
0x140024045  lea     rcx, ?CbsAllowedIdentityDelimiters@@3QB_WB; ";,=~#@^&'$%"
0x14002404c  call    cs:__imp_wcschr
0x140024052  xor     edx, edx
0x140024054  test    rax, rax
0x140024057  jnz     short loc_1400240AF
0x140024059  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024060  mov     ebx, 80070057h
0x140024065  mov     [rbp+3Fh+var_98], ebx
0x140024068  test    rcx, rcx
0x14002406b  jz      short loc_1400240A5
0x14002406d  lea     rax, [rbp+3Fh+var_90]
0x140024071  mov     [rsp+20h], rax
0x140024076  call    ??$LogNumObjects@_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t>(bool,LogAdapter::LogLevel,char const * const,wchar_t const &)
0x14002407b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024082  lea     rax, [rbp+3Fh+var_98]
0x140024086  mov     qword ptr [rbp+3Fh+var_B8], rax
0x14002408a  lea     r9, asc_1400353E8; ": {}"
0x140024091  lea     rax, [rbp+3Fh+var_B8]
0x140024095  mov     r8d, 3
0x14002409b  mov     [rsp+20h], rax
0x1400240a0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400240a5  mov     edx, 19Ch
0x1400240aa  jmp     loc_1400242DF
0x1400240af  movq    rax, xmm6
0x1400240b4  mov     [rsp+30h], dl
0x1400240b8  mov     [rbp+3Fh+var_BF], dl
0x1400240bb  mov     r13b, dl
0x1400240be  mov     [rbp+3Fh+var_BE], dl
0x1400240c1  mov     r15b, dl
0x1400240c4  test    rax, rax
0x1400240c7  jz      loc_14002428A
0x1400240cd  mov     dl, byte ptr [rbp+3Fh+var_90]
0x1400240d0  lea     r9, [rbp+3Fh+var_B0]
0x1400240d4  lea     r8, [rbp+3Fh+var_88]
0x1400240d8  lea     rcx, [rbp+3Fh+var_88]
0x1400240dc  call    ??$TrySplitStringOnFirstAsciiChar@U_LUNICODE_STRING@@@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@DPEAU2@1@Z; Windows::StringUtil::TrySplitStringOnFirstAsciiChar<_LUNICODE_STRING>(_LUNICODE_STRING const &,char,_LUNICODE_STRING *,_LUNICODE_STRING *)
0x1400240e1  xor     edx, edx
0x1400240e3  cmp     [rsp+30h], dl
0x1400240e7  jnz     short loc_14002410D
0x1400240e9  test    r12, r12
0x1400240ec  jz      short loc_140024103
0x1400240ee  movups  xmm0, [rbp+3Fh+var_88]
0x1400240f2  movsd   xmm1, [rbp+3Fh+var_78]
0x1400240f7  movups  xmmword ptr [r12], xmm0
0x1400240fc  movsd   qword ptr [r12+10h], xmm1
0x140024103  mov     byte ptr [rsp+30h], 1
0x140024108  jmp     loc_14002419C
0x14002410d  test    r13b, r13b
0x140024110  jnz     short loc_140024138
0x140024112  movsd   xmm1, [rbp+3Fh+var_78]
0x140024117  movsd   [rbp+3Fh+var_60], xmm1
0x14002411c  movups  xmm0, [rbp+3Fh+var_88]
0x140024120  movups  [rbp+3Fh+var_70], xmm0
0x140024124  test    r14, r14
0x140024127  jz      short loc_140024133
0x140024129  movups  xmmword ptr [r14], xmm0
0x14002412d  movsd   qword ptr [r14+10h], xmm1
0x140024133  mov     r13b, 1
0x140024136  jmp     short loc_14002419C
0x140024138  cmp     [rbp+3Fh+var_BF], dl
0x14002413b  jnz     short loc_140024159
0x14002413d  test    rbx, rbx
0x140024140  jz      short loc_140024153
0x140024142  movups  xmm0, [rbp+3Fh+var_88]
0x140024146  movsd   xmm1, [rbp+3Fh+var_78]
0x14002414b  movups  xmmword ptr [rbx], xmm0
0x14002414e  movsd   qword ptr [rbx+10h], xmm1
0x140024153  mov     [rbp+3Fh+var_BF], 1
0x140024157  jmp     short loc_14002419C
0x140024159  test    r15b, r15b
0x14002415c  jnz     short loc_140024179
0x14002415e  test    rdi, rdi
0x140024161  jz      short loc_140024174
0x140024163  movups  xmm0, [rbp+3Fh+var_88]
0x140024167  movsd   xmm1, [rbp+3Fh+var_78]
0x14002416c  movups  xmmword ptr [rdi], xmm0
0x14002416f  movsd   qword ptr [rdi+10h], xmm1
0x140024174  mov     r15b, 1
0x140024177  jmp     short loc_14002419C
0x140024179  cmp     [rbp+3Fh+var_BE], dl
0x14002417c  jnz     loc_140024233
0x140024182  test    rsi, rsi
0x140024185  jz      short loc_140024198
0x140024187  movups  xmm0, [rbp+3Fh+var_88]
0x14002418b  movsd   xmm1, [rbp+3Fh+var_78]
0x140024190  movups  xmmword ptr [rsi], xmm0
0x140024193  movsd   qword ptr [rsi+10h], xmm1
0x140024198  mov     [rbp+3Fh+var_BE], 1
0x14002419c  movups  xmm1, [rbp+3Fh+var_B0]
0x1400241a0  movsd   xmm0, [rbp+3Fh+var_A0]
0x1400241a5  movq    rax, xmm1
0x1400241aa  movsd   [rbp+3Fh+var_78], xmm0
0x1400241af  movups  [rbp+3Fh+var_88], xmm1
0x1400241b3  test    rax, rax
0x1400241b6  jnz     loc_1400240CD
0x1400241bc  test    r15b, r15b
0x1400241bf  jz      loc_14002428A
0x1400241c5  test    qword ptr [rbp+3Fh+var_70], 0FFFFFFFFFFFFFFDFh
0x1400241cd  jz      short loc_14002422C
0x1400241cf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400241d6  mov     ebx, 80070057h
0x1400241db  mov     [rbp+3Fh+var_98], ebx
0x1400241de  test    rcx, rcx
0x1400241e1  jz      short loc_140024222
0x1400241e3  lea     rax, [rbp+3Fh+var_60]
0x1400241e7  lea     r9, aIdentityContai; "Identity contains invalid public key to"...
0x1400241ee  mov     [rsp+20h], rax
0x1400241f3  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400241f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400241ff  lea     rax, [rbp+3Fh+var_98]
0x140024203  mov     qword ptr [rbp+3Fh+var_B8], rax
0x140024207  lea     r9, asc_1400353E8; ": {}"
0x14002420e  lea     rax, [rbp+3Fh+var_B8]
0x140024212  mov     r8d, 3
0x140024218  mov     [rsp+20h], rax
0x14002421d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024222  mov     edx, 1D8h
0x140024227  jmp     loc_1400242DF
0x14002422c  xor     eax, eax
0x14002422e  jmp     loc_1400242F4
0x140024233  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002423a  mov     ebx, 80070057h
0x14002423f  mov     [rbp+3Fh+var_98], ebx
0x140024242  test    rcx, rcx
0x140024245  jz      short loc_140024283
0x140024247  lea     r9, aTooManyDelimit; "Too many delimiters in string id."
0x14002424e  mov     r8d, 3
0x140024254  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024259  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024260  lea     rax, [rbp+3Fh+var_98]
0x140024264  mov     qword ptr [rbp+3Fh+var_B8], rax
0x140024268  lea     r9, asc_1400353E8; ": {}"
0x14002426f  lea     rax, [rbp+3Fh+var_B8]
0x140024273  mov     r8d, 3
0x140024279  mov     [rsp+20h], rax
0x14002427e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024283  mov     edx, 1C8h
0x140024288  jmp     short loc_1400242DF
0x14002428a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024291  mov     ebx, 80070057h
0x140024296  mov     [rbp+3Fh+var_98], ebx
0x140024299  test    rcx, rcx
0x14002429c  jz      short loc_1400242DA
0x14002429e  xor     edx, edx
0x1400242a0  lea     r9, aIdentityMissin; "Identity missing language."
0x1400242a7  lea     r8d, [rdx+3]
0x1400242ab  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400242b0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400242b7  lea     rax, [rbp+3Fh+var_98]
0x1400242bb  mov     qword ptr [rbp+3Fh+var_B8], rax
0x1400242bf  lea     r9, asc_1400353E8; ": {}"
0x1400242c6  lea     rax, [rbp+3Fh+var_B8]
0x1400242ca  mov     r8d, 3
0x1400242d0  mov     [rsp+20h], rax; int
0x1400242d5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400242da  mov     edx, 1D2h; void *
0x1400242df  mov     rcx, [rbp+47h]; this
0x1400242e3  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x1400242ea  mov     r9d, ebx; char *
0x1400242ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400242f2  mov     eax, ebx
0x1400242f4  mov     rcx, qword ptr [rbp+3Fh+var_58]
0x1400242f8  xor     rcx, rsp; StackCookie
0x1400242fb  call    __security_check_cookie
0x140024300  movaps  xmm6, [rsp+0F0h+var_58+8]
0x140024308  add     rsp, 0B8h
0x14002430f  pop     r15
0x140024311  pop     r14
0x140024313  pop     r13
0x140024315  pop     r12
0x140024317  pop     rdi
0x140024318  pop     rsi
0x140024319  pop     rbx
0x14002431a  pop     rbp
0x14002431b  retn
```
