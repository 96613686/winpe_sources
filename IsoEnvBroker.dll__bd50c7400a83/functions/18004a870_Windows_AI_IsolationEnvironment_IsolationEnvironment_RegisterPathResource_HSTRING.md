# Windows::AI::IsolationEnvironment::IsolationEnvironment::RegisterPathResource(HSTRING__ *)

- ea: `0x18004a870`
- end: `0x18004abe3`
- name: `?RegisterPathResource@IsolationEnvironment@1AI@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `883`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironment *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a444`
- `0x18000a464`
- `0x18001045c`
- `0x180013230`
- `0x1800134e8`
- `0x1800309f8`
- `0x180032e60`
- `0x1800357a0`
- `0x180048edc`
- `0x18004a870`
- `0x18004b28c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a911`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004aa65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ab70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004abbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a911`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004aa65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ab70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004abbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aa46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ab51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ab9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aa46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ab51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ab9d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18004aa80`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18004aad3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18004aa80`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18004aad3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a999`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a999`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18004a9f0`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18004a9f0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18004a933`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18004a933`

## string_xrefs

- `0x18004a8ba`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004a8ed`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004a953`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004a9b1`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004aa03`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004aa32`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004ab2f`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004ab7e`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004aa20`: `Path is not a directory`
- `0x18004a941`: `Relative paths are not allowed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironment::RegisterPathResource(
        Windows::AI::IsolationEnvironment::IsolationEnvironment *this,
        HSTRING a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v7; // eax
  RTL_SRWLOCK *v8; // rcx
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rcx
  char *FileW; // rbx
  const char *v12; // r9
  unsigned int LastError; // edi
  const char *v14; // r9
  __int64 v15; // rdx
  RTL_SRWLOCK *v16; // rcx
  DWORD FinalPathNameByHandleW; // edi
  WCHAR *v18; // rdx
  DWORD v19; // eax
  const char *v20; // r9
  int v21; // eax
  RTL_SRWLOCK *v22; // rcx
  RTL_SRWLOCK *v23; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-39h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-39h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-31h]
  const char *dwFlagsAndAttributesa; // [rsp+28h] [rbp-31h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-19h] BYREF
  __int64 FileInformation; // [rsp+48h] [rbp-11h] BYREF
  LPCWSTR pszPath[3]; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int64 v31; // [rsp+68h] [rbp+Fh]
  LPWSTR lpszFilePath[2]; // [rsp+70h] [rbp+17h] BYREF
  __m128i si128; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v5 = CheckCallingProcessCohort(0, 0);
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)v5,
      (int)"Calling user is not in a supported cohort",
      dwFlagsAndAttributes);
    return v5;
  }
  checked_srwlock::lock_exclusive(v4, &SRWLock);
  v7 = Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(this);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v7,
      dwCreationDisposition);
    v8 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v8);
    }
    return v5;
  }
  GetString(pszPath, a2);
  v9 = (const WCHAR *)pszPath;
  if ( v31 > 7 )
    v9 = pszPath[0];
  if ( PathIsRelativeW(v9) )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)0x80070057LL,
      (int)"Relative paths are not allowed",
      dwFlagsAndAttributes);
LABEL_21:
    std::wstring::~wstring(pszPath);
    v16 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v16);
    }
    return 2147942487LL;
  }
  v10 = (const WCHAR *)pszPath;
  if ( v31 > 7 )
    v10 = pszPath[0];
  FileW = (char *)CreateFileW(v10, 0, 7u, 0, 3u, 0x2000000u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xFA,
                  (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
                  v12);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
LABEL_38:
      std::wstring::~wstring(pszPath);
      v23 = SRWLock;
      if ( SRWLock )
      {
        LODWORD(SRWLock[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v23);
      }
      return LastError;
    }
LABEL_37:
    CloseHandle(FileW);
    goto LABEL_38;
  }
  FileInformation = 0;
  if ( !GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u) )
  {
    v15 = 257;
LABEL_18:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v15,
                  (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
                  v14);
    goto LABEL_37;
  }
  if ( (FileInformation & 0x10) == 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)0x80070057LL,
      (int)"Path is not a directory",
      dwFlagsAndAttributesa);
    CloseHandle(FileW);
    goto LABEL_21;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
  if ( !FinalPathNameByHandleW )
  {
    v15 = 269;
    goto LABEL_18;
  }
  *(_OWORD *)lpszFilePath = 0;
  LOWORD(lpszFilePath[0]) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  std::wstring::resize(lpszFilePath);
  v18 = (WCHAR *)lpszFilePath;
  if ( si128.m128i_i64[1] > 7uLL )
    v18 = lpszFilePath[0];
  v19 = GetFinalPathNameByHandleW(FileW, v18, FinalPathNameByHandleW, 0);
  if ( !v19 || v19 >= FinalPathNameByHandleW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
                  v20);
    goto LABEL_36;
  }
  std::wstring::resize(lpszFilePath);
  v21 = Windows::AI::IsolationEnvironment::IsolationEnvironment::RegisterPathResourceInternal(
          (__int64)this,
          lpszFilePath,
          (_QWORD *)(*((_QWORD *)this + 6) + 112LL),
          (_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 112LL)
                   + 168LL
                   + (-(__int64)(**(_BYTE **)(*((_QWORD *)this + 8) + 112LL) != 0) & 0xFFFFFFFFFFFFFFA0uLL)));
  LastError = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v21,
      dwCreationDispositiona);
LABEL_36:
    std::wstring::~wstring(lpszFilePath);
    goto LABEL_37;
  }
  std::wstring::~wstring(lpszFilePath);
  CloseHandle(FileW);
  std::wstring::~wstring(pszPath);
  v22 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v22);
  }
  return 0;
}

```

## disassembly

```asm
0x18004a870  mov     [rsp-8+arg_10], rbx
0x18004a875  push    rbp
0x18004a876  push    rsi
0x18004a877  push    rdi
0x18004a878  lea     rbp, [rsp-47h]
0x18004a87d  sub     rsp, 0A0h
0x18004a884  mov     rax, cs:__security_cookie
0x18004a88b  xor     rax, rsp
0x18004a88e  mov     [rbp+57h+var_20], rax
0x18004a892  mov     rdi, rdx
0x18004a895  mov     rsi, rcx
0x18004a898  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x18004a89a  xor     ecx, ecx; bool
0x18004a89c  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x18004a8a1  mov     ebx, eax
0x18004a8a3  test    eax, eax
0x18004a8a5  jns     short loc_18004A8D2
0x18004a8a7  mov     rcx, [rbp+5Fh]; this
0x18004a8ab  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x18004a8b2  mov     r9d, ebx; char *
0x18004a8b5  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x18004a8ba  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004a8c1  mov     edx, 0E3h; void *
0x18004a8c6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a8cb  mov     eax, ebx
0x18004a8cd  jmp     loc_18004ABC4
0x18004a8d2  lea     rdx, [rbp+57h+SRWLock]
0x18004a8d6  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x18004a8db  mov     rcx, rsi; this
0x18004a8de  call    ?CheckEntry@IsolationEnvironment@1AI@Windows@@AEBAJXZ; Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(void)
0x18004a8e3  mov     ebx, eax
0x18004a8e5  test    eax, eax
0x18004a8e7  jns     short loc_18004A919
0x18004a8e9  mov     rcx, [rbp+5Fh]; this
0x18004a8ed  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004a8f4  mov     r9d, eax; char *
0x18004a8f7  mov     edx, 0E7h; void *
0x18004a8fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a901  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004a905  test    rcx, rcx
0x18004a908  jz      short loc_18004A8CB
0x18004a90a  mov     dword ptr [rcx+8], 0
0x18004a911  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a917  jmp     short loc_18004A8CB
0x18004a919  mov     rdx, rdi
0x18004a91c  lea     rcx, [rbp+57h+pszPath]
0x18004a920  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x18004a925  cmp     [rbp+57h+var_48], 7
0x18004a92a  lea     rcx, [rbp+57h+pszPath]
0x18004a92e  cmova   rcx, [rbp+57h+pszPath]; pszPath
0x18004a933  call    cs:__imp_PathIsRelativeW
0x18004a939  test    eax, eax
0x18004a93b  jz      short loc_18004A969
0x18004a93d  mov     rcx, [rbp+5Fh]; this
0x18004a941  lea     rax, aRelativePathsA; "Relative paths are not allowed"
0x18004a948  mov     r9d, 80070057h; char *
0x18004a94e  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x18004a953  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004a95a  mov     edx, 0EFh; void *
0x18004a95f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a964  jmp     loc_18004AA4C
0x18004a969  cmp     [rbp+57h+var_48], 7
0x18004a96e  lea     rcx, [rbp+57h+pszPath]
0x18004a972  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18004a97b  cmova   rcx, [rbp+57h+pszPath]; lpFileName
0x18004a980  xor     r9d, r9d; lpSecurityAttributes
0x18004a983  mov     dword ptr [rsp+0B0h+dwFlagsAndAttributes], 2000000h; char *
0x18004a98b  xor     edx, edx; dwDesiredAccess
0x18004a98d  mov     [rsp+0B0h+dwCreationDisposition], 3; int
0x18004a995  lea     r8d, [r9+7]; dwShareMode
0x18004a999  call    cs:__imp_CreateFileW
0x18004a99f  mov     rbx, rax
0x18004a9a2  inc     rax
0x18004a9a5  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004a9ab  jnz     short loc_18004A9D7
0x18004a9ad  mov     rcx, [rbp+5Fh]; this
0x18004a9b1  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004a9b8  mov     edx, 0FAh; void *
0x18004a9bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004a9c2  lea     rcx, [rbx-1]
0x18004a9c6  mov     edi, eax
0x18004a9c8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18004a9cc  ja      loc_18004ABA3
0x18004a9d2  jmp     loc_18004AB9A
0x18004a9d7  mov     r9d, 8; dwBufferSize
0x18004a9dd  mov     [rbp+57h+FileInformation], 0
0x18004a9e5  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18004a9e9  mov     rcx, rbx; hFile
0x18004a9ec  lea     edx, [r9+1]; FileInformationClass
0x18004a9f0  call    cs:__imp_GetFileInformationByHandleEx
0x18004a9f6  test    eax, eax
0x18004a9f8  jnz     short loc_18004AA16
0x18004a9fa  mov     edx, 101h; void *
0x18004a9ff  mov     rcx, [rbp+5Fh]; this
0x18004aa03  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004aa0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004aa0f  mov     edi, eax
0x18004aa11  jmp     loc_18004AB9A
0x18004aa16  test    byte ptr [rbp+57h+FileInformation], 10h
0x18004aa1a  jnz     short loc_18004AA75
0x18004aa1c  mov     rcx, [rbp+5Fh]; this
0x18004aa20  lea     rax, aPathIsNotADire; "Path is not a directory"
0x18004aa27  mov     r9d, 80070057h; char *
0x18004aa2d  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x18004aa32  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004aa39  mov     edx, 106h; void *
0x18004aa3e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004aa43  mov     rcx, rbx; hObject
0x18004aa46  call    cs:__imp_CloseHandle
0x18004aa4c  lea     rcx, [rbp+57h+pszPath]
0x18004aa50  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004aa55  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004aa59  test    rcx, rcx
0x18004aa5c  jz      short loc_18004AA6B
0x18004aa5e  mov     dword ptr [rcx+8], 0
0x18004aa65  call    cs:__imp_ReleaseSRWLockExclusive
0x18004aa6b  mov     eax, 80070057h
0x18004aa70  jmp     loc_18004ABC4
0x18004aa75  xor     r9d, r9d; dwFlags
0x18004aa78  xor     r8d, r8d; cchFilePath
0x18004aa7b  xor     edx, edx; lpszFilePath
0x18004aa7d  mov     rcx, rbx; hFile
0x18004aa80  call    cs:__imp_GetFinalPathNameByHandleW
0x18004aa86  mov     edi, eax
0x18004aa88  test    eax, eax
0x18004aa8a  jnz     short loc_18004AA96
0x18004aa8c  mov     edx, 10Dh
0x18004aa91  jmp     loc_18004A9FF
0x18004aa96  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004aa9e  lea     edx, [rdi-1]
0x18004aaa1  xorps   xmm0, xmm0
0x18004aaa4  lea     rcx, [rbp+57h+lpszFilePath]; Src
0x18004aaa8  xor     eax, eax
0x18004aaaa  movups  xmmword ptr [rbp+57h+lpszFilePath], xmm0
0x18004aaae  mov     word ptr [rbp+57h+lpszFilePath], ax
0x18004aab2  movdqu  [rbp+57h+var_30], xmm1
0x18004aab7  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18004aabc  cmp     qword ptr [rbp+57h+var_30+8], 7
0x18004aac1  lea     rdx, [rbp+57h+lpszFilePath]
0x18004aac5  mov     r8d, edi; cchFilePath
0x18004aac8  mov     rcx, rbx; hFile
0x18004aacb  cmova   rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x18004aad0  xor     r9d, r9d; dwFlags
0x18004aad3  call    cs:__imp_GetFinalPathNameByHandleW
0x18004aad9  test    eax, eax
0x18004aadb  jz      loc_18004AB7A
0x18004aae1  cmp     eax, edi
0x18004aae3  jnb     loc_18004AB7A
0x18004aae9  mov     edx, eax
0x18004aaeb  lea     rcx, [rbp+57h+lpszFilePath]; Src
0x18004aaef  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18004aaf4  mov     rax, [rsi+40h]
0x18004aaf8  mov     rcx, rsi
0x18004aafb  mov     r8, [rsi+30h]
0x18004aaff  mov     rdx, [rax+70h]
0x18004ab03  mov     al, [rdx]
0x18004ab05  neg     al
0x18004ab07  sbb     r9, r9
0x18004ab0a  add     rdx, 0A8h
0x18004ab11  and     r9, 0FFFFFFFFFFFFFFA0h
0x18004ab15  add     r8, 70h ; 'p'
0x18004ab19  add     r9, rdx
0x18004ab1c  lea     rdx, [rbp+57h+lpszFilePath]
0x18004ab20  call    ?RegisterPathResourceInternal@IsolationEnvironment@1AI@Windows@@AEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00@Z; Windows::AI::IsolationEnvironment::IsolationEnvironment::RegisterPathResourceInternal(std::wstring const &,std::wstring const &,std::wstring const &)
0x18004ab25  mov     edi, eax
0x18004ab27  test    eax, eax
0x18004ab29  jns     short loc_18004AB45
0x18004ab2b  mov     rcx, [rbp+5Fh]; this
0x18004ab2f  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004ab36  mov     r9d, eax; char *
0x18004ab39  mov     edx, 11Eh; void *
0x18004ab3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ab43  jmp     short loc_18004AB91
0x18004ab45  lea     rcx, [rbp+57h+lpszFilePath]
0x18004ab49  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ab4e  mov     rcx, rbx; hObject
0x18004ab51  call    cs:__imp_CloseHandle
0x18004ab57  lea     rcx, [rbp+57h+pszPath]
0x18004ab5b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ab60  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004ab64  test    rcx, rcx
0x18004ab67  jz      short loc_18004AB76
0x18004ab69  mov     dword ptr [rcx+8], 0
0x18004ab70  call    cs:__imp_ReleaseSRWLockExclusive
0x18004ab76  xor     eax, eax
0x18004ab78  jmp     short loc_18004ABC4
0x18004ab7a  mov     rcx, [rbp+5Fh]; this
0x18004ab7e  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004ab85  mov     edx, 117h; void *
0x18004ab8a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004ab8f  mov     edi, eax
0x18004ab91  lea     rcx, [rbp+57h+lpszFilePath]
0x18004ab95  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ab9a  mov     rcx, rbx; hObject
0x18004ab9d  call    cs:__imp_CloseHandle
0x18004aba3  lea     rcx, [rbp+57h+pszPath]
0x18004aba7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004abac  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004abb0  test    rcx, rcx
0x18004abb3  jz      short loc_18004ABC2
0x18004abb5  mov     dword ptr [rcx+8], 0
0x18004abbc  call    cs:__imp_ReleaseSRWLockExclusive
0x18004abc2  mov     eax, edi
0x18004abc4  mov     rcx, [rbp+57h+var_20]
0x18004abc8  xor     rcx, rsp; StackCookie
0x18004abcb  call    __security_check_cookie
0x18004abd0  mov     rbx, [rsp+0B0h+arg_10]
0x18004abd8  add     rsp, 0A0h
0x18004abdf  pop     rdi
0x18004abe0  pop     rsi
0x18004abe1  pop     rbp
0x18004abe2  retn
```
