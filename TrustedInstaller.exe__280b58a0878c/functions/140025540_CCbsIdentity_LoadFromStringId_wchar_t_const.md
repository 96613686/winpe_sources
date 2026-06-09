# CCbsIdentity::LoadFromStringId(wchar_t const *)

- ea: `0x140025540`
- end: `0x140025886`
- name: `?LoadFromStringId@CCbsIdentity@@UEAAJPEB_W@Z`
- size: `838`
- prototype: `__int64 __fastcall(wchar_t *this, wchar_t *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x1400054b0`
- `0x14000580c`
- `0x140006778`
- `0x14000e2ac`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x140024324`
- `0x1400246c0`
- `0x140025540`
- `0x14002b010`

## string_xrefs

- `0x1400256a4`: `onecore\base\cbs\identityutil\cbsidentity.cpp`
- `0x140025720`: `Failed to copy identity: {}`

## pseudocode

```c
__int64 __fastcall CCbsIdentity::LoadFromStringId(wchar_t *this, wchar_t *a2)
{
  wchar_t *v3; // rbx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  bool v7; // zf
  int v8; // eax
  __int64 v9; // rdx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  int v22; // [rsp+20h] [rbp-E0h]
  wchar_t *v23; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v24; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v25; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v26; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v27[24]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v28; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v29[2]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v30[256]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v28 = a2;
  CritSecLocker::CritSecLocker((CritSecLocker *)v27, (struct AutoCritSec *)(this + 392), 1);
  v3 = v28;
  if ( v28 )
  {
    memset_0(v30, 0, sizeof(v30));
    v7 = *v3 == 64;
    v23 = 0;
    v26 = 0;
    v25 = 0;
    v24 = 0;
    v29[0] = 0;
    if ( v7 )
    {
      v8 = StringCchCopyW(this + 15, 0x104u, v3);
      v4 = v8;
      if ( v8 < 0 )
      {
        LODWORD(v29[0]) = v8;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate identity name");
          v23 = (wchar_t *)v29;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v9,
            3,
            (__int64)": {}",
            (__int64)&v23);
        }
        v6 = 223;
        goto LABEL_10;
      }
      *((_DWORD *)this + 194) = 1;
    }
    else
    {
      v11 = StringCchCopyW(v30, 0x100u, v3);
      v4 = v11;
      if ( v11 < 0 )
      {
        LODWORD(v29[0]) = v11;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            v12,
            v13,
            (__int64)"Failed to copy identity: {}",
            (__int64)&v28);
          v23 = (wchar_t *)v29;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v14,
            3,
            (__int64)": {}",
            (__int64)&v23);
        }
        v6 = 230;
        goto LABEL_10;
      }
      v15 = ShredStringIdIntoAttributes(
              v30,
              this[14],
              (const wchar_t **)&v23,
              (const wchar_t **)&v26,
              (const wchar_t **)&v25,
              (const wchar_t **)&v24,
              (const wchar_t **)v29);
      v4 = v15;
      if ( v15 < 0 )
      {
        LODWORD(v29[0]) = v15;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t [256]>((_DWORD)LogAdapter::g_Logger, v16, v17, v18, (__int64)v30);
          v23 = (wchar_t *)v29;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v19,
            3,
            (__int64)": {}",
            (__int64)&v23);
        }
        v6 = 235;
        goto LABEL_10;
      }
      v22 = (int)v24;
      v20 = (*(__int64 (__fastcall **)(wchar_t *, wchar_t *, wchar_t *, wchar_t *))(*(_QWORD *)this + 48LL))(
              this,
              v23,
              v26,
              v25);
      v4 = v20;
      if ( v20 < 0 )
      {
        LODWORD(v29[0]) = v20;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load identity from attributes.");
          v23 = (wchar_t *)v29;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v21,
            3,
            (__int64)": {}",
            (__int64)&v23);
        }
        v6 = 243;
        goto LABEL_10;
      }
    }
    *((_DWORD *)this + 6) = 1;
    v4 = 0;
    goto LABEL_13;
  }
  v4 = -2147467261;
  LODWORD(v29[0]) = -2147467261;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid argument: szIdentity");
    v23 = (wchar_t *)v29;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v5,
      3,
      (__int64)": {}",
      (__int64)&v23);
  }
  v6 = 211;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentity.cpp",
    (const char *)v4,
    v22);
LABEL_13:
  CritSecLocker::~CritSecLocker((CritSecLocker *)v27);
  return v4;
}

```

## disassembly

```asm
0x140025540  mov     [rsp-8+arg_10], rbx
0x140025545  mov     [rsp-8+arg_18], rdi
0x14002554a  push    rbp
0x14002554b  lea     rbp, [rsp-1A0h]
0x140025553  sub     rsp, 2A0h
0x14002555a  mov     rax, cs:__security_cookie
0x140025561  xor     rax, rsp
0x140025564  mov     [rbp+1A0h+var_10], rax
0x14002556b  mov     [rsp+2A0h+var_228], rdx
0x140025570  mov     rdi, rcx
0x140025573  lea     rdx, [rcx+310h]; struct AutoCritSec *
0x14002557a  mov     r8b, 1; bool
0x14002557d  lea     rcx, [rsp+2A0h+var_240]; this
0x140025582  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x140025587  mov     rbx, [rsp+2A0h+var_228]
0x14002558c  test    rbx, rbx
0x14002558f  jnz     short loc_1400255ED
0x140025591  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025598  mov     ebx, 80004003h
0x14002559d  mov     dword ptr [rbp+1A0h+var_220], ebx
0x1400255a0  test    rcx, rcx
0x1400255a3  jz      short loc_1400255E3
0x1400255a5  xor     edx, edx
0x1400255a7  lea     r9, aInvalidArgumen_14; "Invalid argument: szIdentity"
0x1400255ae  lea     r8d, [rdx+3]
0x1400255b2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400255b7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400255be  lea     rax, [rbp+1A0h+var_220]
0x1400255c2  mov     [rsp+2A0h+var_260], rax
0x1400255c7  lea     r9, asc_1400353E8; ": {}"
0x1400255ce  lea     rax, [rsp+2A0h+var_260]
0x1400255d3  mov     r8d, 3
0x1400255d9  mov     [rsp+2A0h+var_280], rax
0x1400255de  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400255e3  mov     edx, 0D3h
0x1400255e8  jmp     loc_14002569D
0x1400255ed  xor     edx, edx; Val
0x1400255ef  lea     rcx, [rbp+1A0h+var_210]; void *
0x1400255f3  mov     r8d, 200h; Size
0x1400255f9  call    memset_0
0x1400255fe  cmp     word ptr [rbx], 40h ; '@'
0x140025602  mov     r8, rbx; wchar_t *
0x140025605  mov     [rsp+2A0h+var_260], 0
0x14002560e  mov     [rsp+2A0h+var_248], 0
0x140025617  mov     [rsp+2A0h+var_250], 0
0x140025620  mov     [rsp+2A0h+var_258], 0
0x140025629  mov     [rbp+1A0h+var_220], 0
0x140025631  jnz     loc_1400256F8
0x140025637  lea     rcx, [rdi+1Eh]; wchar_t *
0x14002563b  mov     edx, 104h; unsigned __int64
0x140025640  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140025645  mov     ebx, eax
0x140025647  test    eax, eax
0x140025649  jns     short loc_1400256B5
0x14002564b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025652  mov     dword ptr [rbp+1A0h+var_220], eax
0x140025655  test    rcx, rcx
0x140025658  jz      short loc_140025698
0x14002565a  xor     edx, edx
0x14002565c  lea     r9, aFailedToAlloca_4; "Failed to allocate identity name"
0x140025663  lea     r8d, [rdx+3]
0x140025667  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002566c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025673  lea     rax, [rbp+1A0h+var_220]
0x140025677  mov     [rsp+2A0h+var_260], rax
0x14002567c  lea     r9, asc_1400353E8; ": {}"
0x140025683  lea     rax, [rsp+2A0h+var_260]
0x140025688  mov     r8d, 3
0x14002568e  mov     [rsp+2A0h+var_280], rax; int
0x140025693  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140025698  mov     edx, 0DFh; void *
0x14002569d  mov     rcx, [rbp+1A8h]; this
0x1400256a4  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x1400256ab  mov     r9d, ebx; char *
0x1400256ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400256b3  jmp     short loc_1400256C8
0x1400256b5  mov     dword ptr [rdi+308h], 1
0x1400256bf  mov     dword ptr [rdi+18h], 1
0x1400256c6  xor     ebx, ebx
0x1400256c8  lea     rcx, [rsp+2A0h+var_240]; this
0x1400256cd  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1400256d2  mov     eax, ebx
0x1400256d4  mov     rcx, [rbp+1A0h+var_10]
0x1400256db  xor     rcx, rsp; StackCookie
0x1400256de  call    __security_check_cookie
0x1400256e3  lea     r11, [rsp+2A0h+var_s0]
0x1400256eb  mov     rbx, [r11+20h]
0x1400256ef  mov     rdi, [r11+28h]
0x1400256f3  mov     rsp, r11
0x1400256f6  pop     rbp
0x1400256f7  retn
0x1400256f8  mov     edx, 100h; unsigned __int64
0x1400256fd  lea     rcx, [rbp+1A0h+var_210]; wchar_t *
0x140025701  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140025706  mov     ebx, eax
0x140025708  test    eax, eax
0x14002570a  jns     short loc_140025767
0x14002570c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025713  mov     dword ptr [rbp+1A0h+var_220], eax
0x140025716  test    rcx, rcx
0x140025719  jz      short loc_14002575D
0x14002571b  lea     rax, [rsp+2A0h+var_228]
0x140025720  lea     r9, aFailedToCopyId; "Failed to copy identity: {}"
0x140025727  mov     [rsp+2A0h+var_280], rax
0x14002572c  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140025731  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025738  lea     rax, [rbp+1A0h+var_220]
0x14002573c  mov     [rsp+2A0h+var_260], rax
0x140025741  lea     r9, asc_1400353E8; ": {}"
0x140025748  lea     rax, [rsp+2A0h+var_260]
0x14002574d  mov     r8d, 3
0x140025753  mov     [rsp+2A0h+var_280], rax
0x140025758  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002575d  mov     edx, 0E6h
0x140025762  jmp     loc_14002569D
0x140025767  movzx   edx, word ptr [rdi+1Ch]; wchar_t
0x14002576b  lea     rax, [rbp+1A0h+var_220]
0x14002576f  mov     [rsp+2A0h+var_270], rax; wchar_t **
0x140025774  lea     r9, [rsp+2A0h+var_248]; wchar_t **
0x140025779  lea     rax, [rsp+2A0h+var_258]
0x14002577e  mov     [rsp+2A0h+var_278], rax; wchar_t **
0x140025783  lea     r8, [rsp+2A0h+var_260]; wchar_t **
0x140025788  lea     rax, [rsp+2A0h+var_250]
0x14002578d  lea     rcx, [rbp+1A0h+var_210]; wchar_t *
0x140025791  mov     [rsp+2A0h+var_280], rax; wchar_t **
0x140025796  call    ?ShredStringIdIntoAttributes@@YAJPEA_W_WPEAPEB_W2222@Z; ShredStringIdIntoAttributes(wchar_t *,wchar_t,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *)
0x14002579b  mov     ebx, eax
0x14002579d  test    eax, eax
0x14002579f  jns     short loc_1400257F4
0x1400257a1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400257a8  mov     dword ptr [rbp+1A0h+var_220], eax
0x1400257ab  test    rcx, rcx
0x1400257ae  jz      short loc_1400257EA
0x1400257b0  lea     rax, [rbp+1A0h+var_210]
0x1400257b4  mov     [rsp+2A0h+var_280], rax
0x1400257b9  call    ??$LogNumObjects@$$BY0BAA@_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEAY0BAA@$$CB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t [256]>(bool,LogAdapter::LogLevel,char const * const,wchar_t const (&)[256])
0x1400257be  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400257c5  lea     rax, [rbp+1A0h+var_220]
0x1400257c9  mov     [rsp+2A0h+var_260], rax
0x1400257ce  lea     r9, asc_1400353E8; ": {}"
0x1400257d5  lea     rax, [rsp+2A0h+var_260]
0x1400257da  mov     r8d, 3
0x1400257e0  mov     [rsp+2A0h+var_280], rax
0x1400257e5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400257ea  mov     edx, 0EBh
0x1400257ef  jmp     loc_14002569D
0x1400257f4  mov     rcx, [rbp+1A0h+var_220]
0x1400257f8  mov     rax, [rdi]
0x1400257fb  mov     r9, [rsp+2A0h+var_250]
0x140025800  mov     r8, [rsp+2A0h+var_248]
0x140025805  mov     rdx, [rsp+2A0h+var_260]
0x14002580a  mov     rax, [rax+30h]
0x14002580e  mov     [rsp+2A0h+var_278], rcx
0x140025813  mov     rcx, [rsp+2A0h+var_258]
0x140025818  mov     [rsp+2A0h+var_280], rcx
0x14002581d  mov     rcx, rdi
0x140025820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025825  mov     ebx, eax
0x140025827  test    eax, eax
0x140025829  jns     loc_1400256BF
0x14002582f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025836  mov     dword ptr [rbp+1A0h+var_220], eax
0x140025839  test    rcx, rcx
0x14002583c  jz      short loc_14002587C
0x14002583e  xor     edx, edx
0x140025840  lea     r9, aFailedToLoadId; "Failed to load identity from attributes"...
0x140025847  lea     r8d, [rdx+3]
0x14002584b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140025850  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025857  lea     rax, [rbp+1A0h+var_220]
0x14002585b  mov     [rsp+2A0h+var_260], rax
0x140025860  lea     r9, asc_1400353E8; ": {}"
0x140025867  lea     rax, [rsp+2A0h+var_260]
0x14002586c  mov     r8d, 3
0x140025872  mov     [rsp+2A0h+var_280], rax
0x140025877  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002587c  mov     edx, 0F3h
0x140025881  jmp     loc_14002569D
```
