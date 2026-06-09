# wpc::LogRecorder::LogRecorderChannel::CommitLogToFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18006848c`
- end: `0x1800685da`
- name: `?CommitLogToFile@LogRecorderChannel@LogRecorder@wpc@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(struct Path *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180068730`

## callees

- `0x1800060a0`
- `0x1800093ac`
- `0x180009a80`
- `0x18003ee0c`
- `0x180040888`
- `0x18005a2d8`
- `0x18005aa90`
- `0x18006848c`
- `0x180095fc4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180068519`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180068519`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800684e7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800684e7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18006853b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18006853b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wpc::LogRecorder::LogRecorderChannel::CommitLogToFile(struct Path *a1, _QWORD *a2)
{
  const FILETIME *v4; // rax
  const WCHAR *v5; // rcx
  const WCHAR *v6; // rdx
  const WCHAR *v7; // rcx
  _QWORD *v8; // rdx
  FILETIME FileTime2; // [rsp+20h] [rbp-59h] BYREF
  int v11; // [rsp+28h] [rbp-51h]
  __int64 v12; // [rsp+30h] [rbp-49h] BYREF
  __int64 v13; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v14[24]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v15[16]; // [rsp+58h] [rbp-21h] BYREF
  _QWORD *v16; // [rsp+68h] [rbp-11h]
  LPCWSTR lpFileName[3]; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int64 v18; // [rsp+88h] [rbp+Fh]
  LPCWSTR lpExistingFileName[4]; // [rsp+90h] [rbp+17h] BYREF

  v16 = a2;
  DateTime::GetCurrent(&FileTime2);
  v12 = 12096000000000LL;
  v4 = (const FILETIME *)DateTime::operator+((char *)a1 + 76, v15, &v12);
  if ( CompareFileTime(v4, &FileTime2) < 0 )
  {
    std::wstring::wstring(lpFileName, (char *)a1 + 32);
    std::wstring::wstring(lpExistingFileName, a1);
    v5 = (const WCHAR *)lpFileName;
    if ( v18 > 7 )
      v5 = lpFileName[0];
    DeleteFileW(v5);
    v6 = (const WCHAR *)lpFileName;
    if ( v18 > 7 )
      v6 = lpFileName[0];
    v7 = (const WCHAR *)lpExistingFileName;
    if ( lpExistingFileName[3] > (LPCWSTR)7 )
      v7 = lpExistingFileName[0];
    MoveFileW(v7, v6);
    *(FILETIME *)((char *)a1 + 76) = FileTime2;
    *((_DWORD *)a1 + 21) = v11;
    std::wstring::~wstring(lpExistingFileName);
    std::wstring::~wstring(lpFileName);
  }
  IO::OutputFile::OutputFile((IO::OutputFile *)&v13, a1);
  IO::OutputFile::Seek(v14, 2);
  if ( a2[3] <= 7u )
    v8 = a2;
  else
    v8 = (_QWORD *)*a2;
  (*(void (__fastcall **)(__int64 *, _QWORD *, __int64))(v13 + 8))(&v13, v8, 2LL * a2[2]);
  IO::OutputFile::~OutputFile((IO::OutputFile *)&v13);
  return std::wstring::~wstring(a2);
}

```

## disassembly

```asm
0x18006848c  mov     [rsp-8+arg_10], rbx
0x180068491  push    rbp
0x180068492  push    rsi
0x180068493  push    rdi
0x180068494  lea     rbp, [rsp-47h]
0x180068499  sub     rsp, 0C0h
0x1800684a0  mov     rax, cs:__security_cookie
0x1800684a7  xor     rax, rsp
0x1800684aa  mov     [rbp+57h+var_20], rax
0x1800684ae  mov     rbx, rdx
0x1800684b1  mov     rdi, rcx
0x1800684b4  mov     [rbp+57h+var_68], rdx
0x1800684b8  lea     rcx, [rbp+57h+FileTime2]
0x1800684bc  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x1800684c1  mov     rax, 0B0051C88000h
0x1800684cb  mov     [rbp+57h+var_A0], rax
0x1800684cf  lea     r8, [rbp+57h+var_A0]
0x1800684d3  lea     rdx, [rbp+57h+var_78]
0x1800684d7  lea     rcx, [rdi+4Ch]
0x1800684db  call    ??HDateTime@@QEBA?AV0@AEBVTimeSpan@@@Z; DateTime::operator+(TimeSpan const &)
0x1800684e0  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x1800684e4  mov     rcx, rax; lpFileTime1
0x1800684e7  call    cs:__imp_CompareFileTime
0x1800684ed  test    eax, eax
0x1800684ef  jns     short loc_180068564
0x1800684f1  lea     rdx, [rdi+20h]
0x1800684f5  lea     rcx, [rbp+57h+lpFileName]
0x1800684f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800684fe  nop
0x1800684ff  mov     rdx, rdi
0x180068502  lea     rcx, [rbp+57h+lpExistingFileName]
0x180068506  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006850b  lea     rcx, [rbp+57h+lpFileName]
0x18006850f  cmp     [rbp+57h+var_48], 7
0x180068514  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180068519  call    cs:__imp_DeleteFileW
0x18006851f  lea     rdx, [rbp+57h+lpFileName]
0x180068523  cmp     [rbp+57h+var_48], 7
0x180068528  cmova   rdx, [rbp+57h+lpFileName]; lpNewFileName
0x18006852d  lea     rcx, [rbp+57h+lpExistingFileName]
0x180068531  cmp     [rbp+57h+var_28], 7
0x180068536  cmova   rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x18006853b  call    cs:__imp_MoveFileW
0x180068541  movsd   xmm0, qword ptr [rbp+57h+FileTime2.dwLowDateTime]
0x180068546  movsd   qword ptr [rdi+4Ch], xmm0
0x18006854b  mov     eax, [rbp+57h+var_A8]
0x18006854e  mov     [rdi+54h], eax
0x180068551  lea     rcx, [rbp+57h+lpExistingFileName]
0x180068555  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006855a  nop
0x18006855b  lea     rcx, [rbp+57h+lpFileName]
0x18006855f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180068564  mov     rdx, rdi; struct Path *
0x180068567  lea     rcx, [rbp+57h+var_98]; this
0x18006856b  call    ??0OutputFile@IO@@QEAA@AEBVPath@1@@Z; IO::OutputFile::OutputFile(IO::Path const &)
0x180068570  nop
0x180068571  xor     r8d, r8d
0x180068574  lea     edx, [r8+2]
0x180068578  lea     rcx, [rbp+57h+var_90]
0x18006857c  call    ?Seek@OutputFile@IO@@UEAA_KW4Location@SeekableStream@@H@Z; IO::OutputFile::Seek(SeekableStream::Location,int)
0x180068581  mov     r8, [rbx+10h]
0x180068585  cmp     qword ptr [rbx+18h], 7
0x18006858a  jbe     short loc_180068591
0x18006858c  mov     rdx, [rbx]
0x18006858f  jmp     short loc_180068594
0x180068591  mov     rdx, rbx
0x180068594  add     r8, r8
0x180068597  mov     rax, [rbp+57h+var_98]
0x18006859b  lea     rcx, [rbp+57h+var_98]
0x18006859f  mov     rax, [rax+8]
0x1800685a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800685a8  nop
0x1800685a9  lea     rcx, [rbp+57h+var_98]; this
0x1800685ad  call    ??1OutputFile@IO@@UEAA@XZ; IO::OutputFile::~OutputFile(void)
0x1800685b2  nop
0x1800685b3  mov     rcx, rbx
0x1800685b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800685bb  mov     rcx, [rbp+57h+var_20]
0x1800685bf  xor     rcx, rsp; StackCookie
0x1800685c2  call    __security_check_cookie
0x1800685c7  mov     rbx, [rsp+0D0h+arg_10]
0x1800685cf  add     rsp, 0C0h
0x1800685d6  pop     rdi
0x1800685d7  pop     rsi
0x1800685d8  pop     rbp
0x1800685d9  retn
```
