# Windows::AI::IsolationEnvironment::IsolationEnvironment::RegisterPathResource2(uint,HSTRING__ * *,uint *,Windows::AI::IsolationEnvironment::IsolationRegisterPathResourceResult * *)

- ea: `0x18004a440`
- end: `0x18004a85f`
- name: `?RegisterPathResource2@IsolationEnvironment@1AI@Windows@@UEAAJIPEAPEAUHSTRING__@@PEAIPEAPEAUIsolationRegisterPathResourceResult@123@@Z`
- size: `1055`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironment *__hidden this, unsigned int, HSTRING *, unsigned int *, struct Windows::AI::IsolationEnvironment::IsolationRegisterPathResourceResult **)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a464`
- `0x18001045c`
- `0x180013230`
- `0x1800134e8`
- `0x1800309f8`
- `0x180032e60`
- `0x1800357a0`
- `0x180048edc`
- `0x18004a124`
- `0x18004a440`
- `0x18004b28c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a512`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a82f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a512`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a82f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a7b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a7b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a7f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a52a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a52a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18004a68c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18004a6f7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18004a68c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18004a6f7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a5ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a5ea`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18004a615`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18004a615`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18004a585`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18004a585`

## string_xrefs

- `0x18004a4ba`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004a4f6`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004a558`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004a666`: `Path is not a directory`
- `0x18004a593`: `Relative paths are not allowed`
- `0x18004a7c6`: `Failed to open handle for path`
- `0x18004a79d`: `Failed to get canonical path`
- `0x18004a752`: `Failed to register path resource`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironment::RegisterPathResource2(
        Windows::AI::IsolationEnvironment::IsolationEnvironment *this,
        unsigned int a2,
        HSTRING *a3,
        unsigned int *a4,
        struct Windows::AI::IsolationEnvironment::IsolationRegisterPathResourceResult **a5)
{
  HSTRING *v6; // rdi
  __int64 v7; // r15
  __int64 v8; // rcx
  int v9; // ebx
  __int64 v11; // rdx
  RTL_SRWLOCK *v12; // rcx
  struct Windows::AI::IsolationEnvironment::IsolationRegisterPathResourceResult *v13; // rbx
  unsigned int v14; // r12d
  __m128i si128; // xmm6
  const WCHAR *v16; // rcx
  const WCHAR *v17; // rcx
  char *FileW; // rdi
  signed int v19; // eax
  __int64 v20; // rdx
  DWORD FinalPathNameByHandleW; // r13d
  WCHAR *v22; // rdx
  DWORD v23; // eax
  signed int v24; // eax
  __int64 v25; // rdx
  signed int LastError; // eax
  RTL_SRWLOCK *v27; // rcx
  DWORD dwCreationDisposition; // [rsp+28h] [rbp-A1h]
  const char *dwCreationDispositiona; // [rsp+28h] [rbp-A1h]
  const char *dwCreationDispositionb; // [rsp+28h] [rbp-A1h]
  const char *dwFlagsAndAttributes; // [rsp+30h] [rbp-99h]
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-79h] BYREF
  __int64 FileInformation; // [rsp+58h] [rbp-71h] BYREF
  Windows::AI::IsolationEnvironment::IsolationEnvironment *v35; // [rsp+60h] [rbp-69h]
  unsigned int *v36; // [rsp+68h] [rbp-61h]
  struct Windows::AI::IsolationEnvironment::IsolationRegisterPathResourceResult **v37; // [rsp+70h] [rbp-59h]
  LPWSTR lpszFilePath[2]; // [rsp+78h] [rbp-51h] BYREF
  __m128i v39; // [rsp+88h] [rbp-41h]
  LPCWSTR pszPath[3]; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int64 v41; // [rsp+B0h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+57h]

  v35 = this;
  v6 = a3;
  *a4 = 0;
  v7 = a2;
  v37 = a5;
  *a5 = 0;
  v36 = a4;
  v9 = CheckCallingProcessCohort(0, 0);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v9,
      (int)"Calling user is not in a supported cohort",
      dwFlagsAndAttributes);
    return (unsigned int)v9;
  }
  checked_srwlock::lock_exclusive(v8, &SRWLock);
  v9 = Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry((Windows::AI::IsolationEnvironment::IsolationEnvironment *)((char *)this - 16));
  if ( v9 < 0 )
  {
    v11 = 307;
    goto LABEL_6;
  }
  if ( !(_DWORD)v7 )
    goto LABEL_51;
  v13 = (struct Windows::AI::IsolationEnvironment::IsolationRegisterPathResourceResult *)CoTaskMemAlloc(8 * v7);
  if ( !v13 )
  {
    v9 = -2147024882;
    v11 = 317;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v9,
      dwCreationDisposition);
    v12 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v12);
    }
    return (unsigned int)v9;
  }
  v14 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    *((_QWORD *)v13 + v14) = 1;
    GetString(pszPath, v6[v14]);
    v16 = (const WCHAR *)pszPath;
    if ( v41 > 7 )
      v16 = pszPath[0];
    if ( PathIsRelativeW(v16) )
    {
      *((_DWORD *)v13 + 2 * v14 + 1) = -2147024809;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x149,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
        (const char *)0x80070057LL,
        (int)"Relative paths are not allowed",
        dwFlagsAndAttributes);
      goto LABEL_49;
    }
    v17 = (const WCHAR *)pszPath;
    if ( v41 > 7 )
      v17 = pszPath[0];
    FileW = (char *)CreateFileW(v17, 0, 7u, 0, 3u, 0x2000000u, 0);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *((_DWORD *)v13 + 2 * v14 + 1) = LastError;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x159,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
        (const char *)(unsigned int)LastError,
        (int)"Failed to open handle for path",
        dwFlagsAndAttributes);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_48;
      goto LABEL_47;
    }
    FileInformation = 0;
    if ( !GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u) )
    {
      v19 = GetLastError();
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      dwCreationDispositiona = "Failed to get file information";
      v20 = 358;
LABEL_24:
      *((_DWORD *)v13 + 2 * v14 + 1) = v19;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v20,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
        (const char *)(unsigned int)v19,
        (int)dwCreationDispositiona,
        dwFlagsAndAttributes);
      goto LABEL_47;
    }
    if ( (FileInformation & 0x10) != 0 )
    {
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
      if ( !FinalPathNameByHandleW )
      {
        v19 = GetLastError();
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        dwCreationDispositiona = "Failed to get buffer size";
        v20 = 378;
        goto LABEL_24;
      }
      *(_OWORD *)lpszFilePath = 0;
      LOWORD(lpszFilePath[0]) = 0;
      v39 = si128;
      std::wstring::resize(lpszFilePath);
      v22 = (WCHAR *)lpszFilePath;
      if ( v39.m128i_i64[1] > 7uLL )
        v22 = lpszFilePath[0];
      v23 = GetFinalPathNameByHandleW(FileW, v22, FinalPathNameByHandleW, 0);
      if ( v23 && v23 < FinalPathNameByHandleW )
      {
        std::wstring::resize(lpszFilePath);
        v24 = Windows::AI::IsolationEnvironment::IsolationEnvironment::RegisterPathResourceInternal(
                (char *)v35 - 16,
                lpszFilePath,
                *((_QWORD *)v35 + 4) + 112LL,
                *(_QWORD *)(*((_QWORD *)v35 + 6) + 112LL)
              + 168LL
              + (-(__int64)(**(_BYTE **)(*((_QWORD *)v35 + 6) + 112LL) != 0) & 0xFFFFFFFFFFFFFFA0uLL));
        if ( v24 >= 0 )
        {
          *((_QWORD *)v13 + v14) = 0;
          goto LABEL_39;
        }
        dwCreationDispositionb = "Failed to register path resource";
        v25 = 407;
      }
      else
      {
        v24 = GetLastError();
        if ( v24 > 0 )
          v24 = (unsigned __int16)v24 | 0x80070000;
        dwCreationDispositionb = "Failed to get canonical path";
        v25 = 394;
      }
      *((_DWORD *)v13 + 2 * v14 + 1) = v24;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v25,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
        (const char *)(unsigned int)v24,
        (int)dwCreationDispositionb,
        dwFlagsAndAttributes);
LABEL_39:
      std::wstring::~wstring(lpszFilePath);
      goto LABEL_47;
    }
    *((_DWORD *)v13 + 2 * v14 + 1) = -2147024809;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)0x80070057LL,
      (int)"Path is not a directory",
      dwFlagsAndAttributes);
LABEL_47:
    CloseHandle(FileW);
LABEL_48:
    v6 = a3;
LABEL_49:
    std::wstring::~wstring(pszPath);
    ++v14;
  }
  while ( v14 < (unsigned int)v7 );
  *v36 = v7;
  *v37 = v13;
LABEL_51:
  v27 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v27);
  }
  return 0;
}

```

## disassembly

```asm
0x18004a440  mov     rax, rsp
0x18004a443  push    rbp
0x18004a444  push    rbx
0x18004a445  push    rsi
0x18004a446  push    rdi
0x18004a447  push    r12
0x18004a449  push    r13
0x18004a44b  push    r14
0x18004a44d  push    r15
0x18004a44f  lea     rbp, [rax-57h]
0x18004a453  sub     rsp, 0D8h
0x18004a45a  movaps  xmmword ptr [rax-58h], xmm6
0x18004a45e  mov     rax, cs:__security_cookie
0x18004a465  xor     rax, rsp
0x18004a468  mov     [rbp+4Fh+var_60], rax
0x18004a46c  mov     r13, rcx
0x18004a46f  mov     [rbp+4Fh+var_B8], rcx
0x18004a473  mov     rcx, [rbp+4Fh+arg_20]
0x18004a477  mov     rdi, r8
0x18004a47a  mov     dword ptr [r9], 0
0x18004a481  mov     r15d, edx
0x18004a484  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x18004a486  mov     [rbp+4Fh+var_A8], rcx
0x18004a48a  mov     qword ptr [rcx], 0
0x18004a491  xor     ecx, ecx; bool
0x18004a493  mov     [rbp+4Fh+var_B0], r9
0x18004a497  mov     [rsp+40h], r8
0x18004a49c  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x18004a4a1  mov     ebx, eax
0x18004a4a3  test    eax, eax
0x18004a4a5  jns     short loc_18004A4D2
0x18004a4a7  mov     rcx, [rbp+57h]; this
0x18004a4ab  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x18004a4b2  mov     r9d, ebx; char *
0x18004a4b5  mov     [rsp+110h+dwCreationDisposition], rax; int
0x18004a4ba  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004a4c1  mov     edx, 12Fh; void *
0x18004a4c6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a4cb  mov     eax, ebx
0x18004a4cd  jmp     loc_18004A837
0x18004a4d2  lea     rdx, [rbp+4Fh+SRWLock]
0x18004a4d6  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x18004a4db  lea     rcx, [r13-10h]; this
0x18004a4df  call    ?CheckEntry@IsolationEnvironment@1AI@Windows@@AEBAJXZ; Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(void)
0x18004a4e4  xor     r13d, r13d
0x18004a4e7  mov     ebx, eax
0x18004a4e9  test    eax, eax
0x18004a4eb  jns     short loc_18004A51A
0x18004a4ed  mov     edx, 133h; void *
0x18004a4f2  mov     rcx, [rbp+57h]; this
0x18004a4f6  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004a4fd  mov     r9d, ebx; char *
0x18004a500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a505  mov     rcx, [rbp+4Fh+SRWLock]; SRWLock
0x18004a509  test    rcx, rcx
0x18004a50c  jz      short loc_18004A4CB
0x18004a50e  mov     [rcx+8], r13d
0x18004a512  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a518  jmp     short loc_18004A4CB
0x18004a51a  test    r15d, r15d
0x18004a51d  jz      loc_18004A822
0x18004a523  mov     rcx, r15
0x18004a526  shl     rcx, 3; cb
0x18004a52a  call    cs:__imp_CoTaskMemAlloc
0x18004a530  mov     rbx, rax
0x18004a533  test    rax, rax
0x18004a536  jnz     short loc_18004A544
0x18004a538  mov     ebx, 8007000Eh
0x18004a53d  mov     edx, 13Dh
0x18004a542  jmp     short loc_18004A4F2
0x18004a544  mov     r12d, r13d
0x18004a547  test    r15d, r15d
0x18004a54a  jz      loc_18004A814
0x18004a550  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18004a558  lea     rsi, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004a55f  mov     r14d, r12d
0x18004a562  lea     rcx, [rbp+4Fh+pszPath]
0x18004a566  mov     qword ptr [rbx+r14*8], 1
0x18004a56e  mov     rdx, [rdi+r14*8]
0x18004a572  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x18004a577  cmp     [rbp+4Fh+var_68], 7
0x18004a57c  lea     rcx, [rbp+4Fh+pszPath]
0x18004a580  cmova   rcx, [rbp+4Fh+pszPath]; pszPath
0x18004a585  call    cs:__imp_PathIsRelativeW
0x18004a58b  test    eax, eax
0x18004a58d  jz      short loc_18004A5BE
0x18004a58f  mov     rcx, [rbp+57h]; this
0x18004a593  lea     rax, aRelativePathsA; "Relative paths are not allowed"
0x18004a59a  mov     edx, 80070057h
0x18004a59f  mov     [rsp+110h+dwCreationDisposition], rax; int
0x18004a5a4  mov     [rbx+r14*8+4], edx
0x18004a5a9  mov     r9d, edx; char *
0x18004a5ac  mov     edx, 149h; void *
0x18004a5b1  mov     r8, rsi; unsigned int
0x18004a5b4  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a5b9  jmp     loc_18004A7FF
0x18004a5be  cmp     [rbp+4Fh+var_68], 7
0x18004a5c3  lea     rcx, [rbp+4Fh+pszPath]
0x18004a5c7  mov     [rsp+30h], r13; hTemplateFile
0x18004a5cc  cmova   rcx, [rbp+4Fh+pszPath]; lpFileName
0x18004a5d1  xor     r9d, r9d; lpSecurityAttributes
0x18004a5d4  mov     [rsp+110h+dwFlagsAndAttributes], 2000000h; char *
0x18004a5dc  xor     edx, edx; dwDesiredAccess
0x18004a5de  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x18004a5e6  lea     r8d, [r9+7]; dwShareMode
0x18004a5ea  call    cs:__imp_CreateFileW
0x18004a5f0  mov     rdi, rax
0x18004a5f3  dec     rax
0x18004a5f6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004a5fa  ja      loc_18004A7B0
0x18004a600  mov     r9d, 8; dwBufferSize
0x18004a606  mov     [rbp+4Fh+FileInformation], r13
0x18004a60a  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x18004a60e  mov     rcx, rdi; hFile
0x18004a611  lea     edx, [r9+1]; FileInformationClass
0x18004a615  call    cs:__imp_GetFileInformationByHandleEx
0x18004a61b  test    eax, eax
0x18004a61d  jnz     short loc_18004A65B
0x18004a61f  call    cs:__imp_GetLastError
0x18004a625  test    eax, eax
0x18004a627  jle     short loc_18004A631
0x18004a629  movzx   eax, ax
0x18004a62c  or      eax, 80070000h
0x18004a631  lea     rdx, aFailedToGetFil; "Failed to get file information"
0x18004a638  mov     [rsp+110h+dwCreationDisposition], rdx; int
0x18004a63d  mov     edx, 166h; void *
0x18004a642  mov     r9d, eax; char *
0x18004a645  mov     [rbx+r14*8+4], eax
0x18004a64a  mov     rcx, [rbp+57h]; this
0x18004a64e  mov     r8, rsi; unsigned int
0x18004a651  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a656  jmp     loc_18004A7F1
0x18004a65b  test    byte ptr [rbp+4Fh+FileInformation], 10h
0x18004a65f  jnz     short loc_18004A681
0x18004a661  mov     edx, 80070057h
0x18004a666  lea     rax, aPathIsNotADire; "Path is not a directory"
0x18004a66d  mov     [rbx+r14*8+4], edx
0x18004a672  mov     r9d, edx
0x18004a675  mov     edx, 16Dh
0x18004a67a  mov     [rsp+110h+dwCreationDisposition], rax
0x18004a67f  jmp     short loc_18004A64A
0x18004a681  xor     r9d, r9d; dwFlags
0x18004a684  xor     r8d, r8d; cchFilePath
0x18004a687  xor     edx, edx; lpszFilePath
0x18004a689  mov     rcx, rdi; hFile
0x18004a68c  call    cs:__imp_GetFinalPathNameByHandleW
0x18004a692  mov     r13d, eax
0x18004a695  test    eax, eax
0x18004a697  jnz     short loc_18004A6C1
0x18004a699  call    cs:__imp_GetLastError
0x18004a69f  xor     r13d, r13d
0x18004a6a2  test    eax, eax
0x18004a6a4  jle     short loc_18004A6AE
0x18004a6a6  movzx   eax, ax
0x18004a6a9  or      eax, 80070000h
0x18004a6ae  lea     rdx, aFailedToGetBuf; "Failed to get buffer size"
0x18004a6b5  mov     [rsp+110h+dwCreationDisposition], rdx
0x18004a6ba  mov     edx, 17Ah
0x18004a6bf  jmp     short loc_18004A642
0x18004a6c1  xorps   xmm0, xmm0
0x18004a6c4  lea     edx, [r13-1]
0x18004a6c8  xor     eax, eax
0x18004a6ca  lea     rcx, [rbp+4Fh+lpszFilePath]; Src
0x18004a6ce  movups  xmmword ptr [rbp+4Fh+lpszFilePath], xmm0
0x18004a6d2  mov     word ptr [rbp+4Fh+lpszFilePath], ax
0x18004a6d6  movdqu  [rbp+4Fh+var_90], xmm6
0x18004a6db  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18004a6e0  cmp     qword ptr [rbp+4Fh+var_90+8], 7
0x18004a6e5  lea     rdx, [rbp+4Fh+lpszFilePath]
0x18004a6e9  mov     r8d, r13d; cchFilePath
0x18004a6ec  mov     rcx, rdi; hFile
0x18004a6ef  cmova   rdx, [rbp+4Fh+lpszFilePath]; lpszFilePath
0x18004a6f4  xor     r9d, r9d; dwFlags
0x18004a6f7  call    cs:__imp_GetFinalPathNameByHandleW
0x18004a6fd  test    eax, eax
0x18004a6ff  jz      loc_18004A788
0x18004a705  cmp     eax, r13d
0x18004a708  jnb     short loc_18004A788
0x18004a70a  mov     edx, eax
0x18004a70c  lea     rcx, [rbp+4Fh+lpszFilePath]; Src
0x18004a710  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18004a715  mov     r13, [rbp+4Fh+var_B8]
0x18004a719  lea     rdx, [rbp+4Fh+lpszFilePath]
0x18004a71d  mov     rax, [r13+30h]
0x18004a721  mov     r8, [r13+20h]
0x18004a725  mov     rcx, [rax+70h]
0x18004a729  mov     al, [rcx]
0x18004a72b  neg     al
0x18004a72d  sbb     r9, r9
0x18004a730  add     rcx, 0A8h
0x18004a737  and     r9, 0FFFFFFFFFFFFFFA0h
0x18004a73b  add     r8, 70h ; 'p'
0x18004a73f  add     r9, rcx
0x18004a742  lea     rcx, [r13-10h]
0x18004a746  call    ?RegisterPathResourceInternal@IsolationEnvironment@1AI@Windows@@AEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00@Z; Windows::AI::IsolationEnvironment::IsolationEnvironment::RegisterPathResourceInternal(std::wstring const &,std::wstring const &,std::wstring const &)
0x18004a74b  xor     r13d, r13d
0x18004a74e  test    eax, eax
0x18004a750  jns     short loc_18004A782
0x18004a752  lea     rdx, aFailedToRegist; "Failed to register path resource"
0x18004a759  mov     [rsp+110h+dwCreationDisposition], rdx; int
0x18004a75e  mov     edx, 197h; void *
0x18004a763  mov     rcx, [rbp+57h]; this
0x18004a767  mov     r8, rsi; unsigned int
0x18004a76a  mov     r9d, eax; char *
0x18004a76d  mov     [rbx+r14*8+4], eax
0x18004a772  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a777  lea     rcx, [rbp+4Fh+lpszFilePath]
0x18004a77b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004a780  jmp     short loc_18004A7F1
0x18004a782  mov     [rbx+r14*8], r13
0x18004a786  jmp     short loc_18004A777
0x18004a788  call    cs:__imp_GetLastError
0x18004a78e  xor     r13d, r13d
0x18004a791  test    eax, eax
0x18004a793  jle     short loc_18004A79D
0x18004a795  movzx   eax, ax
0x18004a798  or      eax, 80070000h
0x18004a79d  lea     rdx, aFailedToGetCan; "Failed to get canonical path"
0x18004a7a4  mov     [rsp+110h+dwCreationDisposition], rdx
0x18004a7a9  mov     edx, 18Ah
0x18004a7ae  jmp     short loc_18004A763
0x18004a7b0  call    cs:__imp_GetLastError
0x18004a7b6  test    eax, eax
0x18004a7b8  jle     short loc_18004A7C2
0x18004a7ba  movzx   eax, ax
0x18004a7bd  or      eax, 80070000h
0x18004a7c2  mov     rcx, [rbp+57h]; this
0x18004a7c6  lea     rdx, aFailedToOpenHa; "Failed to open handle for path"
0x18004a7cd  mov     [rsp+110h+dwCreationDisposition], rdx; int
0x18004a7d2  mov     r9d, eax; char *
0x18004a7d5  mov     edx, 159h; void *
0x18004a7da  mov     [rbx+r14*8+4], eax
0x18004a7df  mov     r8, rsi; unsigned int
0x18004a7e2  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a7e7  lea     rax, [rdi-1]
0x18004a7eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004a7ef  ja      short loc_18004A7FA
0x18004a7f1  mov     rcx, rdi; hObject
0x18004a7f4  call    cs:__imp_CloseHandle
0x18004a7fa  mov     rdi, [rsp+40h]
0x18004a7ff  lea     rcx, [rbp+4Fh+pszPath]
0x18004a803  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004a808  inc     r12d
0x18004a80b  cmp     r12d, r15d
0x18004a80e  jb      loc_18004A55F
0x18004a814  mov     rax, [rbp+4Fh+var_B0]
0x18004a818  mov     [rax], r15d
0x18004a81b  mov     rax, [rbp+4Fh+var_A8]
0x18004a81f  mov     [rax], rbx
0x18004a822  mov     rcx, [rbp+4Fh+SRWLock]; SRWLock
0x18004a826  test    rcx, rcx
0x18004a829  jz      short loc_18004A835
0x18004a82b  mov     [rcx+8], r13d
0x18004a82f  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a835  xor     eax, eax
0x18004a837  mov     rcx, [rbp+4Fh+var_60]
0x18004a83b  xor     rcx, rsp; StackCookie
0x18004a83e  call    __security_check_cookie
0x18004a843  movaps  xmm6, [rsp+110h+var_58+8]
0x18004a84b  add     rsp, 0D8h
0x18004a852  pop     r15
0x18004a854  pop     r14
0x18004a856  pop     r13
0x18004a858  pop     r12
0x18004a85a  pop     rdi
0x18004a85b  pop     rsi
0x18004a85c  pop     rbx
0x18004a85d  pop     rbp
0x18004a85e  retn
```
