# CCbsSession::RemoveDirectoryViaCbsTemp(wchar_t const * const)

- ea: `0x1800e4f40`
- end: `0x1800e52c3`
- name: `?RemoveDirectoryViaCbsTemp@CCbsSession@@QEAAJQEB_W@Z`
- size: `899`
- prototype: `__int64 __fastcall(CCbsSession *this, const WCHAR *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800532d4`
- `0x1800caa88`

## callees

- `0x180013250`
- `0x180015420`
- `0x18004a6d8`
- `0x180059a00`
- `0x18005aa38`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800e4f40`
- `0x1800eb920`
- `0x1800ec920`
- `0x180107120`
- `0x1801c1794`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e516f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e516f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800e5003`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800e5003`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800e504f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800e504f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800e515b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800e515b`

## string_xrefs

- `0x1800e518e`: `Failed to move to CbsTemp`
- `0x1800e5136`: `Moving directory from {} to {}`
- `0x1800e4fbb`: `Failed to get session temp directory`
- `0x1800e523a`: `Failed to remove directory {}`

## pseudocode

```c
__int64 __fastcall CCbsSession::RemoveDirectoryViaCbsTemp(CCbsSession *this, const WCHAR *a2)
{
  int TempDirectory; // eax
  unsigned int v4; // ebx
  int v5; // edx
  __int64 v6; // r9
  __int64 v7; // rdx
  HRESULT v8; // eax
  int v9; // edx
  int v10; // edx
  WCHAR *v11; // rbx
  signed int LastError; // ebx
  int v13; // edx
  unsigned int v14; // eax
  int v15; // eax
  unsigned int v16; // esi
  int v17; // edx
  unsigned int v19; // [rsp+20h] [rbp-69h]
  unsigned int v20[2]; // [rsp+30h] [rbp-59h] BYREF
  LPCWSTR lpNewFileName; // [rsp+38h] [rbp-51h] BYREF
  wchar_t *v22; // [rsp+40h] [rbp-49h] BYREF
  int v23[2]; // [rsp+48h] [rbp-41h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+50h] [rbp-39h] BYREF
  int v25; // [rsp+58h] [rbp-31h] BYREF
  GUID pguid; // [rsp+60h] [rbp-29h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  lpExistingFileName = a2;
  lpNewFileName = 0;
  v22 = 0;
  pguid = 0;
  if ( !(unsigned __int8)DoesDirectoryExist(a2, 0) )
    goto LABEL_34;
  TempDirectory = CCbsSession::GetTempDirectory(this, &v22);
  v4 = TempDirectory;
  if ( TempDirectory < 0 )
  {
    v25 = TempDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get session temp directory");
      *(_QWORD *)v20 = &v25;
      LOBYTE(v5) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)v20);
    }
    v6 = v4;
    v7 = 661;
    goto LABEL_9;
  }
  v8 = CoCreateGuid(&pguid);
  v4 = v8;
  if ( v8 < 0 )
  {
    v7 = 663;
LABEL_8:
    v6 = (unsigned int)v8;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstorage.cpp",
      (const char *)v6,
      v19);
    goto LABEL_35;
  }
  memset_0(sz, 0, 0x4Eu);
  if ( !StringFromGUID2(&pguid, sz, 39) )
  {
    v4 = -2147418113;
    v25 = -2147418113;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to convert guid to string");
      *(_QWORD *)v20 = &v25;
      LOBYTE(v9) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v20);
    }
    v6 = 2147549183LL;
    v7 = 666;
    goto LABEL_9;
  }
  v8 = SczAllocFromSz(&lpNewFileName, *((_QWORD *)this + 138));
  v4 = v8;
  if ( v8 < 0 )
  {
    v7 = 668;
    goto LABEL_8;
  }
  v8 = SczEnsureBackslashTerminated(&lpNewFileName);
  v4 = v8;
  if ( v8 < 0 )
  {
    v7 = 670;
    goto LABEL_8;
  }
  v8 = SczAllocConcatSz(&lpNewFileName, sz);
  v4 = v8;
  if ( v8 < 0 )
  {
    v7 = 672;
    goto LABEL_8;
  }
  v11 = (WCHAR *)lpNewFileName;
  *(_QWORD *)v20 = lpNewFileName;
  if ( LogAdapter::g_Logger )
  {
    LOBYTE(v10) = 1;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      v10,
      1,
      (unsigned int)"Moving directory from {} to {}",
      (__int64)&lpExistingFileName,
      (__int64)v20);
  }
  if ( !MoveFileExW(lpExistingFileName, v11, 1u) )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to move to CbsTemp");
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      else
        v14 = LastError;
      v25 = v14;
      LOBYTE(v13) = 1;
      *(_QWORD *)v20 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v13,
        3,
        (unsigned int)": {0}",
        (__int64)v20);
    }
    if ( LastError )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x2A4,
             (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstorage.cpp",
             (const char *)(unsigned int)LastError,
             v19);
      goto LABEL_35;
    }
LABEL_34:
    v4 = 0;
    goto LABEL_35;
  }
  v15 = RecursiveRemoveDirectoryEx(0, v11, v22);
  v16 = v15;
  if ( v15 >= 0 )
    goto LABEL_34;
  v25 = v15;
  if ( LogAdapter::g_Logger )
  {
    *(_QWORD *)v20 = v11;
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to remove directory {}",
      (__int64)v20);
    *(_QWORD *)v23 = &v25;
    LOBYTE(v17) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v17,
      3,
      (unsigned int)": {}",
      (__int64)v23);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A7,
    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstorage.cpp",
    (const char *)v16,
    v19);
  v4 = v16;
LABEL_35:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v22);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  return v4;
}

```

## disassembly

```asm
0x1800e4f40  mov     [rsp-8+arg_10], rbx
0x1800e4f45  push    rbp
0x1800e4f46  push    rsi
0x1800e4f47  push    rdi
0x1800e4f48  lea     rbp, [rsp-47h]
0x1800e4f4d  sub     rsp, 0D0h
0x1800e4f54  mov     rax, cs:__security_cookie
0x1800e4f5b  xor     rax, rsp
0x1800e4f5e  mov     [rbp+57h+var_20], rax
0x1800e4f62  mov     rax, rdx
0x1800e4f65  mov     [rbp+57h+lpExistingFileName], rdx
0x1800e4f69  mov     rdi, rcx
0x1800e4f6c  mov     [rbp+57h+lpNewFileName], 0
0x1800e4f74  xorps   xmm0, xmm0
0x1800e4f77  mov     [rbp+57h+var_A0], 0
0x1800e4f7f  mov     rcx, rax
0x1800e4f82  xor     edx, edx
0x1800e4f84  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800e4f88  call    DoesDirectoryExist
0x1800e4f8d  test    al, al
0x1800e4f8f  jz      loc_1800E528D
0x1800e4f95  lea     rdx, [rbp+57h+var_A0]; wchar_t **
0x1800e4f99  mov     rcx, rdi; this
0x1800e4f9c  call    ?GetTempDirectory@CCbsSession@@QEBAJPEAPEA_W@Z; CCbsSession::GetTempDirectory(wchar_t * *)
0x1800e4fa1  mov     ebx, eax
0x1800e4fa3  test    eax, eax
0x1800e4fa5  jns     short loc_1800E4FFF
0x1800e4fa7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e4fae  mov     [rbp+57h+var_88], eax
0x1800e4fb1  test    rcx, rcx
0x1800e4fb4  jz      short loc_1800E4FF5
0x1800e4fb6  mov     edi, 3
0x1800e4fbb  lea     r9, aFailedToGetSes_7; "Failed to get session temp directory"
0x1800e4fc2  mov     r8d, edi
0x1800e4fc5  xor     edx, edx
0x1800e4fc7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e4fcc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e4fd3  lea     rax, [rbp+57h+var_88]
0x1800e4fd7  mov     qword ptr [rbp+57h+var_B0], rax
0x1800e4fdb  lea     r9, asc_1802EE7AC; ": {}"
0x1800e4fe2  lea     rax, [rbp+57h+var_B0]
0x1800e4fe6  mov     r8d, edi
0x1800e4fe9  mov     dl, 1
0x1800e4feb  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800e4ff0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e4ff5  mov     r9d, ebx
0x1800e4ff8  mov     edx, 295h
0x1800e4ffd  jmp     short loc_1800E501D
0x1800e4fff  lea     rcx, [rbp+57h+pguid]; pguid
0x1800e5003  call    cs:__imp_CoCreateGuid
0x1800e500a  nop     dword ptr [rax+rax+00h]
0x1800e500f  mov     ebx, eax
0x1800e5011  test    eax, eax
0x1800e5013  jns     short loc_1800E5032
0x1800e5015  mov     edx, 297h; void *
0x1800e501a  mov     r9d, eax; char *
0x1800e501d  mov     rcx, [rbp+5Fh]; this
0x1800e5021  lea     r8, aOnecoreBaseCbs_148; "onecore\\base\\cbs\\core\\cbssessionsto"...
0x1800e5028  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e502d  jmp     loc_1800E528F
0x1800e5032  xor     edx, edx; Val
0x1800e5034  lea     rcx, [rbp+57h+sz]; void *
0x1800e5038  lea     r8d, [rdx+4Eh]; Size
0x1800e503c  call    memset_0
0x1800e5041  mov     r8d, 27h ; '''; cchMax
0x1800e5047  lea     rdx, [rbp+57h+sz]; lpsz
0x1800e504b  lea     rcx, [rbp+57h+pguid]; rguid
0x1800e504f  call    cs:__imp_StringFromGUID2
0x1800e5056  nop     dword ptr [rax+rax+00h]
0x1800e505b  test    eax, eax
0x1800e505d  jnz     short loc_1800E50BD
0x1800e505f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5066  mov     ebx, 8000FFFFh
0x1800e506b  mov     [rbp+57h+var_88], ebx
0x1800e506e  test    rcx, rcx
0x1800e5071  jz      short loc_1800E50B0
0x1800e5073  lea     edi, [rax+3]
0x1800e5076  xor     edx, edx
0x1800e5078  mov     r8d, edi
0x1800e507b  lea     r9, aFailedToConver_4; "Failed to convert guid to string"
0x1800e5082  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5087  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e508e  lea     rax, [rbp+57h+var_88]
0x1800e5092  mov     qword ptr [rbp+57h+var_B0], rax
0x1800e5096  lea     r9, asc_1802EE7AC; ": {}"
0x1800e509d  lea     rax, [rbp+57h+var_B0]
0x1800e50a1  mov     r8d, edi
0x1800e50a4  mov     dl, 1
0x1800e50a6  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800e50ab  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e50b0  mov     r9d, ebx
0x1800e50b3  mov     edx, 29Ah
0x1800e50b8  jmp     loc_1800E501D
0x1800e50bd  mov     rdx, [rdi+450h]
0x1800e50c4  lea     rcx, [rbp+57h+lpNewFileName]
0x1800e50c8  call    SczAllocFromSz
0x1800e50cd  mov     ebx, eax
0x1800e50cf  test    eax, eax
0x1800e50d1  jns     short loc_1800E50DD
0x1800e50d3  mov     edx, 29Ch
0x1800e50d8  jmp     loc_1800E501A
0x1800e50dd  lea     rcx, [rbp+57h+lpNewFileName]
0x1800e50e1  call    SczEnsureBackslashTerminated
0x1800e50e6  mov     ebx, eax
0x1800e50e8  test    eax, eax
0x1800e50ea  jns     short loc_1800E50F6
0x1800e50ec  mov     edx, 29Eh
0x1800e50f1  jmp     loc_1800E501A
0x1800e50f6  lea     rdx, [rbp+57h+sz]
0x1800e50fa  lea     rcx, [rbp+57h+lpNewFileName]
0x1800e50fe  call    SczAllocConcatSz
0x1800e5103  mov     ebx, eax
0x1800e5105  test    eax, eax
0x1800e5107  jns     short loc_1800E5113
0x1800e5109  mov     edx, 2A0h
0x1800e510e  jmp     loc_1800E501A
0x1800e5113  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e511a  mov     rbx, [rbp+57h+lpNewFileName]
0x1800e511e  mov     qword ptr [rbp+57h+var_B0], rbx
0x1800e5122  test    rcx, rcx
0x1800e5125  jz      short loc_1800E514E
0x1800e5127  lea     rax, [rbp+57h+var_B0]
0x1800e512b  mov     r8d, 1
0x1800e5131  mov     [rsp+0E0h+var_B8], rax
0x1800e5136  lea     r9, aMovingDirector; "Moving directory from {} to {}"
0x1800e513d  lea     rax, [rbp+57h+lpExistingFileName]
0x1800e5141  mov     dl, r8b
0x1800e5144  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800e5149  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800e514e  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800e5152  mov     r8d, 1; dwFlags
0x1800e5158  mov     rdx, rbx; lpNewFileName
0x1800e515b  call    cs:__imp_MoveFileExW
0x1800e5162  nop     dword ptr [rax+rax+00h]
0x1800e5167  test    eax, eax
0x1800e5169  jnz     loc_1800E5202
0x1800e516f  call    cs:__imp_GetLastError
0x1800e5176  nop     dword ptr [rax+rax+00h]
0x1800e517b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5182  mov     ebx, eax
0x1800e5184  test    rcx, rcx
0x1800e5187  jz      short loc_1800E51DB
0x1800e5189  mov     edi, 3
0x1800e518e  lea     r9, aFailedToMoveTo_0; "Failed to move to CbsTemp"
0x1800e5195  mov     r8d, edi
0x1800e5198  xor     edx, edx
0x1800e519a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e519f  test    ebx, ebx
0x1800e51a1  jg      short loc_1800E51A7
0x1800e51a3  mov     eax, ebx
0x1800e51a5  jmp     short loc_1800E51AF
0x1800e51a7  movzx   eax, bx
0x1800e51aa  or      eax, 80070000h
0x1800e51af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e51b6  lea     r9, a0; ": {0}"
0x1800e51bd  mov     [rbp+57h+var_88], eax
0x1800e51c0  mov     r8d, edi
0x1800e51c3  lea     rax, [rbp+57h+var_88]
0x1800e51c7  mov     dl, 1
0x1800e51c9  mov     qword ptr [rbp+57h+var_B0], rax
0x1800e51cd  lea     rax, [rbp+57h+var_B0]
0x1800e51d1  mov     qword ptr [rsp+0E0h+var_C0], rax; unsigned int
0x1800e51d6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e51db  test    ebx, ebx
0x1800e51dd  jz      loc_1800E528D
0x1800e51e3  mov     rcx, [rbp+5Fh]; this
0x1800e51e7  lea     r8, aOnecoreBaseCbs_148; "onecore\\base\\cbs\\core\\cbssessionsto"...
0x1800e51ee  mov     r9d, ebx; char *
0x1800e51f1  mov     edx, 2A4h; void *
0x1800e51f6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e51fb  mov     ebx, eax
0x1800e51fd  jmp     loc_1800E528F
0x1800e5202  mov     r8, [rbp+57h+var_A0]; wchar_t *
0x1800e5206  mov     rdx, rbx; wchar_t *
0x1800e5209  xor     ecx, ecx; unsigned int
0x1800e520b  call    RecursiveRemoveDirectoryEx
0x1800e5210  mov     esi, eax
0x1800e5212  test    eax, eax
0x1800e5214  jns     short loc_1800E528D
0x1800e5216  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e521d  mov     [rbp+57h+var_88], eax
0x1800e5220  test    rcx, rcx
0x1800e5223  jz      short loc_1800E5271
0x1800e5225  lea     rax, [rbp+57h+var_B0]
0x1800e5229  mov     qword ptr [rbp+57h+var_B0], rbx
0x1800e522d  mov     edi, 3
0x1800e5232  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800e5237  mov     r8d, edi
0x1800e523a  lea     r9, aFailedToRemove_0; "Failed to remove directory {}"
0x1800e5241  xor     edx, edx
0x1800e5243  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800e5248  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e524f  lea     rax, [rbp+57h+var_88]
0x1800e5253  mov     qword ptr [rbp+57h+var_98], rax
0x1800e5257  lea     r9, asc_1802EE7AC; ": {}"
0x1800e525e  lea     rax, [rbp+57h+var_98]
0x1800e5262  mov     r8d, edi
0x1800e5265  mov     dl, 1
0x1800e5267  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800e526c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5271  mov     rcx, [rbp+5Fh]; this
0x1800e5275  lea     r8, aOnecoreBaseCbs_148; "onecore\\base\\cbs\\core\\cbssessionsto"...
0x1800e527c  mov     r9d, esi; char *
0x1800e527f  mov     edx, 2A7h; void *
0x1800e5284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5289  mov     ebx, esi
0x1800e528b  jmp     short loc_1800E528F
0x1800e528d  xor     ebx, ebx
0x1800e528f  lea     rcx, [rbp+57h+var_A0]
0x1800e5293  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800e5298  lea     rcx, [rbp+57h+lpNewFileName]
0x1800e529c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800e52a1  mov     eax, ebx
0x1800e52a3  mov     rcx, [rbp+57h+var_20]
0x1800e52a7  xor     rcx, rsp; StackCookie
0x1800e52aa  call    __security_check_cookie
0x1800e52af  mov     rbx, [rsp+0E0h+arg_10]
0x1800e52b7  add     rsp, 0D0h
0x1800e52be  pop     rdi
0x1800e52bf  pop     rsi
0x1800e52c0  pop     rbp
0x1800e52c1  retn
```
