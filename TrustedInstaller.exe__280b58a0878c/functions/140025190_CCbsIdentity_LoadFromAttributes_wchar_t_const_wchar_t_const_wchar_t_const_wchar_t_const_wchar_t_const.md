# CCbsIdentity::LoadFromAttributes(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x140025190`
- end: `0x140025533`
- name: `?LoadFromAttributes@CCbsIdentity@@UEAAJPEB_W0000@Z`
- size: `931`
- prototype: `__int64 __fastcall(wchar_t *this, wchar_t *, wchar_t *, wchar_t *, wchar_t *, wchar_t *)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000580c`
- `0x140006778`
- `0x14000e2ac`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x1400236fc`
- `0x1400238c8`
- `0x140023a48`
- `0x140023c20`
- `0x140024568`
- `0x140025190`
- `0x14002b010`

## string_xrefs

- `0x140025273`: `Failed to validate component name: {}`
- `0x1400253a0`: `Failed to normalize public key token: {}`
- `0x1400252b7`: `onecore\base\cbs\identityutil\cbsidentity.cpp`

## pseudocode

```c
__int64 __fastcall CCbsIdentity::LoadFromAttributes(
        wchar_t *this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4,
        wchar_t *a5,
        wchar_t *a6)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // r8d
  __int64 v16; // rdx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  unsigned int v29; // r9d
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  int v35; // [rsp+20h] [rbp-39h]
  int v36[2]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v37[24]; // [rsp+38h] [rbp-21h] BYREF
  wchar_t *v38; // [rsp+50h] [rbp-9h] BYREF
  wchar_t *v39; // [rsp+58h] [rbp-1h] BYREF
  wchar_t *v40; // [rsp+60h] [rbp+7h] BYREF
  wchar_t *v41; // [rsp+68h] [rbp+Fh] BYREF
  wchar_t *v42; // [rsp+70h] [rbp+17h] BYREF
  int v43; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+4Fh]

  v40 = a5;
  v38 = a2;
  v39 = a3;
  v42 = a6;
  v41 = a4;
  CritSecLocker::CritSecLocker((CritSecLocker *)v37, (struct AutoCritSec *)(this + 392), 1);
  if ( v38 )
  {
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)this + 24LL))(this);
    v10 = ValidateComponentName(v38, this[14]);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v14 = StringCchCopyW(this + 15, 0x104u, v38);
      v7 = v14;
      if ( v14 >= 0 )
      {
        if ( *v38 == 64 )
        {
          *((_DWORD *)this + 194) = 1;
        }
        else
        {
          v18 = NormalizePublicKeyToken(v39, this + 275, v15);
          v7 = v18;
          if ( v18 < 0 )
          {
            v43 = v18;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                v19,
                v20,
                (__int64)"Failed to normalize public key token: {}",
                (__int64)&v39);
              *(_QWORD *)v36 = &v43;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v21,
                3,
                (__int64)": {}",
                (__int64)v36);
            }
            v9 = 190;
            goto LABEL_9;
          }
          v22 = NormalizeLanguage(v40, this + 292, v20);
          v7 = v22;
          if ( v22 < 0 )
          {
            v43 = v22;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                v23,
                v24,
                (__int64)"Failed to normalize language: {}",
                (__int64)&v40);
              *(_QWORD *)v36 = &v43;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v25,
                3,
                (__int64)": {}",
                (__int64)v36);
            }
            v9 = 193;
            goto LABEL_9;
          }
          v26 = NormalizeProcessor(v41, this + 324, v24);
          v7 = v26;
          if ( v26 < 0 )
          {
            v43 = v26;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                v27,
                v28,
                (__int64)"Failed to normalize processor: {}",
                (__int64)&v41);
              *(_QWORD *)v36 = &v43;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v30,
                3,
                (__int64)": {}",
                (__int64)v36);
            }
            v9 = 196;
            goto LABEL_9;
          }
          v31 = NormalizeVersion(v42, v27, this + 356, v29);
          v7 = v31;
          if ( v31 < 0 )
          {
            v43 = v31;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                v32,
                v33,
                (__int64)"Failed to normalize version: {}",
                (__int64)&v42);
              *(_QWORD *)v36 = &v43;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v34,
                3,
                (__int64)": {}",
                (__int64)v36);
            }
            v9 = 199;
            goto LABEL_9;
          }
        }
        *((_DWORD *)this + 6) = 1;
        v7 = 0;
        goto LABEL_17;
      }
      v43 = v14;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate identity name");
        *(_QWORD *)v36 = &v43;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v16,
          3,
          (__int64)": {}",
          (__int64)v36);
      }
      v9 = 180;
    }
    else
    {
      v43 = v10;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          v11,
          v12,
          (__int64)"Failed to validate component name: {}",
          (__int64)&v38);
        *(_QWORD *)v36 = &v43;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v13,
          3,
          (__int64)": {}",
          (__int64)v36);
      }
      v9 = 178;
    }
  }
  else
  {
    v7 = -2147467261;
    v43 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid argument: szName");
      *(_QWORD *)v36 = &v43;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v36);
    }
    v9 = 169;
  }
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentity.cpp",
    (const char *)v7,
    v35);
LABEL_17:
  CritSecLocker::~CritSecLocker((CritSecLocker *)v37);
  return v7;
}

```

## disassembly

```asm
0x140025190  push    rbp
0x140025192  push    rbx
0x140025193  push    rdi
0x140025194  lea     rbp, [rsp-37h]
0x140025199  sub     rsp, 90h
0x1400251a0  mov     rax, cs:__security_cookie
0x1400251a7  xor     rax, rsp
0x1400251aa  mov     [rbp+47h+var_20], rax
0x1400251ae  mov     rax, [rbp+47h+arg_20]
0x1400251b2  mov     rdi, rcx
0x1400251b5  mov     [rbp+47h+var_40], rax
0x1400251b9  mov     rax, [rbp+47h+arg_28]
0x1400251bd  mov     [rbp+47h+var_50], rdx
0x1400251c1  lea     rdx, [rcx+310h]; struct AutoCritSec *
0x1400251c8  mov     [rbp+47h+var_48], r8
0x1400251cc  lea     rcx, [rbp+47h+var_68]; this
0x1400251d0  mov     r8b, 1; bool
0x1400251d3  mov     [rbp+47h+var_30], rax
0x1400251d7  mov     [rbp+47h+var_38], r9
0x1400251db  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1400251e0  cmp     [rbp+47h+var_50], 0
0x1400251e5  jnz     short loc_14002523E
0x1400251e7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400251ee  mov     ebx, 80004003h
0x1400251f3  mov     [rbp+47h+var_28], ebx
0x1400251f6  test    rcx, rcx
0x1400251f9  jz      short loc_140025237
0x1400251fb  xor     edx, edx
0x1400251fd  lea     r9, aInvalidArgumen_4; "Invalid argument: szName"
0x140025204  lea     r8d, [rdx+3]
0x140025208  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002520d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025214  lea     rax, [rbp+47h+var_28]
0x140025218  mov     qword ptr [rbp+47h+var_70], rax
0x14002521c  lea     r9, asc_1400353E8; ": {}"
0x140025223  lea     rax, [rbp+47h+var_70]
0x140025227  mov     r8d, 3
0x14002522d  mov     qword ptr [rsp+0A0h+var_80], rax
0x140025232  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140025237  mov     edx, 0A9h
0x14002523c  jmp     short loc_1400252B3
0x14002523e  mov     rax, [rdi]
0x140025241  mov     rcx, rdi
0x140025244  mov     rax, [rax+18h]
0x140025248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002524d  movzx   edx, word ptr [rdi+1Ch]; wchar_t
0x140025251  mov     rcx, [rbp+47h+var_50]; wchar_t *
0x140025255  call    ?ValidateComponentName@@YAJPEB_W_W@Z; ValidateComponentName(wchar_t const *,wchar_t)
0x14002525a  mov     ebx, eax
0x14002525c  test    eax, eax
0x14002525e  jns     short loc_1400252CB
0x140025260  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025267  mov     [rbp+47h+var_28], eax
0x14002526a  test    rcx, rcx
0x14002526d  jz      short loc_1400252AE
0x14002526f  lea     rax, [rbp+47h+var_50]
0x140025273  lea     r9, aFailedToValida; "Failed to validate component name: {}"
0x14002527a  mov     qword ptr [rsp+0A0h+var_80], rax
0x14002527f  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140025284  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002528b  lea     rax, [rbp+47h+var_28]
0x14002528f  mov     qword ptr [rbp+47h+var_70], rax
0x140025293  lea     r9, asc_1400353E8; ": {}"
0x14002529a  lea     rax, [rbp+47h+var_70]
0x14002529e  mov     r8d, 3
0x1400252a4  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x1400252a9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400252ae  mov     edx, 0B2h; void *
0x1400252b3  mov     rcx, [rbp+4Fh]; this
0x1400252b7  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x1400252be  mov     r9d, ebx; char *
0x1400252c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400252c6  jmp     loc_140025355
0x1400252cb  mov     r8, [rbp+47h+var_50]; wchar_t *
0x1400252cf  lea     rcx, [rdi+1Eh]; wchar_t *
0x1400252d3  mov     edx, 104h; unsigned __int64
0x1400252d8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400252dd  mov     ebx, eax
0x1400252df  test    eax, eax
0x1400252e1  jns     short loc_140025338
0x1400252e3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400252ea  mov     [rbp+47h+var_28], eax
0x1400252ed  test    rcx, rcx
0x1400252f0  jz      short loc_14002532E
0x1400252f2  xor     edx, edx
0x1400252f4  lea     r9, aFailedToAlloca_4; "Failed to allocate identity name"
0x1400252fb  lea     r8d, [rdx+3]
0x1400252ff  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140025304  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002530b  lea     rax, [rbp+47h+var_28]
0x14002530f  mov     qword ptr [rbp+47h+var_70], rax
0x140025313  lea     r9, asc_1400353E8; ": {}"
0x14002531a  lea     rax, [rbp+47h+var_70]
0x14002531e  mov     r8d, 3
0x140025324  mov     qword ptr [rsp+0A0h+var_80], rax
0x140025329  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002532e  mov     edx, 0B4h
0x140025333  jmp     loc_1400252B3
0x140025338  mov     rax, [rbp+47h+var_50]
0x14002533c  cmp     word ptr [rax], 40h ; '@'
0x140025340  jnz     short loc_140025377
0x140025342  mov     dword ptr [rdi+308h], 1
0x14002534c  mov     dword ptr [rdi+18h], 1
0x140025353  xor     ebx, ebx
0x140025355  lea     rcx, [rbp+47h+var_68]; this
0x140025359  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x14002535e  mov     eax, ebx
0x140025360  mov     rcx, [rbp+47h+var_20]
0x140025364  xor     rcx, rsp; StackCookie
0x140025367  call    __security_check_cookie
0x14002536c  add     rsp, 90h
0x140025373  pop     rdi
0x140025374  pop     rbx
0x140025375  pop     rbp
0x140025376  retn
0x140025377  mov     rcx, [rbp+47h+var_48]; wchar_t *
0x14002537b  lea     rdx, [rdi+226h]; wchar_t *
0x140025382  call    ?NormalizePublicKeyToken@@YAJPEB_WPEA_WK@Z; NormalizePublicKeyToken(wchar_t const *,wchar_t *,ulong)
0x140025387  mov     ebx, eax
0x140025389  test    eax, eax
0x14002538b  jns     short loc_1400253E5
0x14002538d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025394  mov     [rbp+47h+var_28], eax
0x140025397  test    rcx, rcx
0x14002539a  jz      short loc_1400253DB
0x14002539c  lea     rax, [rbp+47h+var_48]
0x1400253a0  lea     r9, aFailedToNormal_1; "Failed to normalize public key token: {"...
0x1400253a7  mov     qword ptr [rsp+0A0h+var_80], rax
0x1400253ac  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400253b1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400253b8  lea     rax, [rbp+47h+var_28]
0x1400253bc  mov     qword ptr [rbp+47h+var_70], rax
0x1400253c0  lea     r9, asc_1400353E8; ": {}"
0x1400253c7  lea     rax, [rbp+47h+var_70]
0x1400253cb  mov     r8d, 3
0x1400253d1  mov     qword ptr [rsp+0A0h+var_80], rax
0x1400253d6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400253db  mov     edx, 0BEh
0x1400253e0  jmp     loc_1400252B3
0x1400253e5  mov     rcx, [rbp+47h+var_40]; wchar_t *
0x1400253e9  lea     rdx, [rdi+248h]; wchar_t *
0x1400253f0  call    ?NormalizeLanguage@@YAJPEB_WPEA_WK@Z; NormalizeLanguage(wchar_t const *,wchar_t *,ulong)
0x1400253f5  mov     ebx, eax
0x1400253f7  test    eax, eax
0x1400253f9  jns     short loc_140025453
0x1400253fb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025402  mov     [rbp+47h+var_28], eax
0x140025405  test    rcx, rcx
0x140025408  jz      short loc_140025449
0x14002540a  lea     rax, [rbp+47h+var_40]
0x14002540e  lea     r9, aFailedToNormal_0; "Failed to normalize language: {}"
0x140025415  mov     qword ptr [rsp+0A0h+var_80], rax
0x14002541a  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14002541f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025426  lea     rax, [rbp+47h+var_28]
0x14002542a  mov     qword ptr [rbp+47h+var_70], rax
0x14002542e  lea     r9, asc_1400353E8; ": {}"
0x140025435  lea     rax, [rbp+47h+var_70]
0x140025439  mov     r8d, 3
0x14002543f  mov     qword ptr [rsp+0A0h+var_80], rax
0x140025444  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140025449  mov     edx, 0C1h
0x14002544e  jmp     loc_1400252B3
0x140025453  mov     rcx, [rbp+47h+var_38]; wchar_t *
0x140025457  lea     rdx, [rdi+288h]; wchar_t *
0x14002545e  call    ?NormalizeProcessor@@YAJPEB_WPEA_WK@Z; NormalizeProcessor(wchar_t const *,wchar_t *,ulong)
0x140025463  mov     ebx, eax
0x140025465  test    eax, eax
0x140025467  jns     short loc_1400254C1
0x140025469  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025470  mov     [rbp+47h+var_28], eax
0x140025473  test    rcx, rcx
0x140025476  jz      short loc_1400254B7
0x140025478  lea     rax, [rbp+47h+var_38]
0x14002547c  lea     r9, aFailedToNormal; "Failed to normalize processor: {}"
0x140025483  mov     qword ptr [rsp+0A0h+var_80], rax
0x140025488  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14002548d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025494  lea     rax, [rbp+47h+var_28]
0x140025498  mov     qword ptr [rbp+47h+var_70], rax
0x14002549c  lea     r9, asc_1400353E8; ": {}"
0x1400254a3  lea     rax, [rbp+47h+var_70]
0x1400254a7  mov     r8d, 3
0x1400254ad  mov     qword ptr [rsp+0A0h+var_80], rax
0x1400254b2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400254b7  mov     edx, 0C4h
0x1400254bc  jmp     loc_1400252B3
0x1400254c1  mov     rcx, [rbp+47h+var_30]; wchar_t *
0x1400254c5  lea     r8, [rdi+2C8h]; wchar_t *
0x1400254cc  call    ?NormalizeVersion@@YAJPEB_WKPEA_WK@Z; NormalizeVersion(wchar_t const *,ulong,wchar_t *,ulong)
0x1400254d1  mov     ebx, eax
0x1400254d3  test    eax, eax
0x1400254d5  jns     loc_14002534C
0x1400254db  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400254e2  mov     [rbp+47h+var_28], eax
0x1400254e5  test    rcx, rcx
0x1400254e8  jz      short loc_140025529
0x1400254ea  lea     rax, [rbp+47h+var_30]
0x1400254ee  lea     r9, aFailedToNormal_2; "Failed to normalize version: {}"
0x1400254f5  mov     qword ptr [rsp+0A0h+var_80], rax
0x1400254fa  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400254ff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025506  lea     rax, [rbp+47h+var_28]
0x14002550a  mov     qword ptr [rbp+47h+var_70], rax
0x14002550e  lea     r9, asc_1400353E8; ": {}"
0x140025515  lea     rax, [rbp+47h+var_70]
0x140025519  mov     r8d, 3
0x14002551f  mov     qword ptr [rsp+0A0h+var_80], rax
0x140025524  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140025529  mov     edx, 0C7h
0x14002552e  jmp     loc_1400252B3
```
