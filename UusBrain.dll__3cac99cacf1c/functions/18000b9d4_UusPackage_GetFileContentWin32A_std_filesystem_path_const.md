# UusPackage::GetFileContentWin32A(std::filesystem::path const &)

- ea: `0x18000b9d4`
- end: `0x18000bc29`
- name: `?GetFileContentWin32A@UusPackage@@CA?AV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVpath@filesystem@3@@Z`
- size: `597`
- prototype: `__int64 __fastcall(void *, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000b638`

## callees

- `0x18000b9d4`
- `0x180011e0c`
- `0x180013d18`
- `0x1800259dc`
- `0x180026a00`
- `0x1800427d0`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb81`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ba3a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ba3a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000ba7b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000ba7b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000bb59`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000bb59`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000bac7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000bac7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000bb05`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000bb05`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char *__fastcall UusPackage::GetFileContentWin32A(char *a1, const WCHAR *lpFileName)
{
  const WCHAR *v2; // rax
  char *FileW; // rbx
  const char *v5; // r9
  unsigned int v6; // r8d
  const char *v7; // r9
  DWORD LowPart; // edi
  char *FileMappingW; // rsi
  const char *v10; // r9
  const char *v11; // r9
  const void *v12; // r14
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-68h]
  _LARGE_INTEGER FileSize; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = lpFileName;
  if ( *((_QWORD *)lpFileName + 3) > 7u )
    v2 = *(const WCHAR **)lpFileName;
  FileW = (char *)CreateFileW(v2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x331,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UusPackage.hpp",
      v5);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x338,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UusPackage.hpp",
      v7);
  LowPart = FileSize.LowPart;
  if ( !FileSize.QuadPart )
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x33B, v6, (const char *)0xDE, dwCreationDisposition);
  if ( FileSize.QuadPart > 0x100000uLL )
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x340, v6, (const char *)0xDF, dwCreationDisposition);
  FileMappingW = (char *)CreateFileMappingW(FileW, 0, 2u, 0, FileSize.LowPart, 0);
  FileSize.QuadPart = (LONGLONG)FileMappingW;
  if ( (unsigned __int64)(FileMappingW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x34F,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UusPackage.hpp",
      v10);
  v12 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  if ( !v12 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x35A,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UusPackage.hpp",
      v11);
  memset(a1, 0, 0xF8u);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(a1);
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a1 + 16, v12, LowPart);
  UnmapViewOfFile(v12);
  if ( (unsigned __int64)(FileMappingW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileMappingW);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return a1;
}

```

## disassembly

```asm
0x18000b9d4  mov     [rsp+arg_10], rbx
0x18000b9d9  mov     [rsp+arg_18], rbp
0x18000b9de  push    rsi
0x18000b9df  push    rdi
0x18000b9e0  push    r14
0x18000b9e2  sub     rsp, 70h
0x18000b9e6  mov     rax, cs:__security_cookie
0x18000b9ed  xor     rax, rsp
0x18000b9f0  mov     [rsp+88h+var_20], rax
0x18000b9f5  mov     rax, rdx
0x18000b9f8  mov     rbp, rcx
0x18000b9fb  mov     [rsp+88h+var_40], rcx
0x18000ba00  mov     [rsp+88h+var_48], 0
0x18000ba08  cmp     qword ptr [rdx+18h], 7
0x18000ba0d  jbe     short loc_18000BA12
0x18000ba0f  mov     rax, [rdx]
0x18000ba12  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18000ba1b  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000ba23  mov     [rsp+88h+dwCreationDisposition], 3; unsigned int
0x18000ba2b  xor     r9d, r9d; lpSecurityAttributes
0x18000ba2e  mov     edx, 80000000h; dwDesiredAccess
0x18000ba33  lea     r8d, [r9+1]; dwShareMode
0x18000ba37  mov     rcx, rax; lpFileName
0x18000ba3a  call    cs:__imp_CreateFileW
0x18000ba40  mov     rbx, rax
0x18000ba43  mov     [rsp+88h+var_38], rax
0x18000ba48  dec     rax
0x18000ba4b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ba4f  setnbe  al
0x18000ba52  mov     rcx, [rsp+88h]; this
0x18000ba5a  test    al, al
0x18000ba5c  jnz     loc_18000BBD7
0x18000ba62  mov     qword ptr [rsp+88h+FileSize], 0
0x18000ba6b  mov     rdi, [rsp+88h]
0x18000ba73  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x18000ba78  mov     rcx, rbx; hFile
0x18000ba7b  call    cs:__imp_GetFileSizeEx
0x18000ba81  test    eax, eax
0x18000ba83  jz      loc_18000BBE9
0x18000ba89  mov     rdi, qword ptr [rsp+88h+FileSize]
0x18000ba8e  test    rdi, rdi
0x18000ba91  jz      loc_18000BBFE
0x18000ba97  cmp     dword ptr [rsp+88h+FileSize+4], 0
0x18000ba9c  jnz     loc_18000BBBE
0x18000baa2  cmp     edi, 100000h
0x18000baa8  ja      loc_18000BBBE
0x18000baae  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], 0; lpName
0x18000bab7  mov     [rsp+88h+dwCreationDisposition], edi; dwMaximumSizeLow
0x18000babb  xor     r9d, r9d; dwMaximumSizeHigh
0x18000babe  xor     edx, edx; lpFileMappingAttributes
0x18000bac0  lea     r8d, [r9+2]; flProtect
0x18000bac4  mov     rcx, rbx; hFile
0x18000bac7  call    cs:__imp_CreateFileMappingW
0x18000bacd  mov     rsi, rax
0x18000bad0  mov     qword ptr [rsp+88h+FileSize], rax
0x18000bad5  dec     rax
0x18000bad8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000badc  setnbe  al
0x18000badf  mov     rcx, [rsp+88h]; this
0x18000bae7  test    al, al
0x18000bae9  jnz     loc_18000BC17
0x18000baef  mov     qword ptr [rsp+88h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18000baf8  xor     r9d, r9d; dwFileOffsetLow
0x18000bafb  xor     r8d, r8d; dwFileOffsetHigh
0x18000bafe  lea     edx, [r9+4]; dwDesiredAccess
0x18000bb02  mov     rcx, rsi; hFileMappingObject
0x18000bb05  call    cs:__imp_MapViewOfFile
0x18000bb0b  mov     r14, rax
0x18000bb0e  mov     [rsp+88h+var_30], rax
0x18000bb13  mov     rcx, [rsp+88h]; this
0x18000bb1b  test    rax, rax
0x18000bb1e  jz      loc_18000BBAC
0x18000bb24  mov     edi, edi
0x18000bb26  xor     edx, edx; Val
0x18000bb28  mov     r8d, 0F8h; Size
0x18000bb2e  mov     rcx, rbp; void *
0x18000bb31  call    memset
0x18000bb36  mov     rcx, rbp
0x18000bb39  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18000bb3e  mov     [rsp+88h+var_48], 1
0x18000bb46  lea     rcx, [rbp+10h]
0x18000bb4a  mov     r8d, edi
0x18000bb4d  mov     rdx, r14
0x18000bb50  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18000bb55  nop
0x18000bb56  mov     rcx, r14; lpBaseAddress
0x18000bb59  call    cs:__imp_UnmapViewOfFile
0x18000bb5f  nop
0x18000bb60  lea     rax, [rsi-1]
0x18000bb64  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bb68  ja      short loc_18000BB74
0x18000bb6a  mov     rcx, rsi; hObject
0x18000bb6d  call    cs:__imp_CloseHandle
0x18000bb73  nop
0x18000bb74  lea     rcx, [rbx-1]
0x18000bb78  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000bb7c  ja      short loc_18000BB87
0x18000bb7e  mov     rcx, rbx; hObject
0x18000bb81  call    cs:__imp_CloseHandle
0x18000bb87  mov     rax, rbp
0x18000bb8a  mov     rcx, [rsp+88h+var_20]
0x18000bb8f  xor     rcx, rsp; StackCookie
0x18000bb92  call    __security_check_cookie
0x18000bb97  lea     r11, [rsp+88h+var_18]
0x18000bb9c  mov     rbx, [r11+30h]
0x18000bba0  mov     rbp, [r11+38h]
0x18000bba4  mov     rsp, r11
0x18000bba7  pop     r14
0x18000bba9  pop     rdi
0x18000bbaa  pop     rsi
0x18000bbab  retn
0x18000bbac  lea     r8, aCW1SSrcIncUusp; "C:\\__w\\1\\s\\src\\inc\\UusPackage.hpp"
0x18000bbb3  mov     edx, 35Ah; void *
0x18000bbb8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000bbbe  mov     rcx, [rsp+88h]; this
0x18000bbc6  mov     edx, 340h; void *
0x18000bbcb  mov     r9d, 0DFh; char *
0x18000bbd1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000bbd7  lea     r8, aCW1SSrcIncUusp; "C:\\__w\\1\\s\\src\\inc\\UusPackage.hpp"
0x18000bbde  mov     edx, 331h; void *
0x18000bbe3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000bbe9  lea     r8, aCW1SSrcIncUusp; "C:\\__w\\1\\s\\src\\inc\\UusPackage.hpp"
0x18000bbf0  mov     edx, 338h; void *
0x18000bbf5  mov     rcx, rdi; this
0x18000bbf8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000bbfe  mov     rcx, [rsp+88h]; this
0x18000bc06  mov     edx, 33Bh; void *
0x18000bc0b  mov     r9d, 0DEh; char *
0x18000bc11  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000bc17  lea     r8, aCW1SSrcIncUusp; "C:\\__w\\1\\s\\src\\inc\\UusPackage.hpp"
0x18000bc1e  mov     edx, 34Fh; void *
0x18000bc23  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
