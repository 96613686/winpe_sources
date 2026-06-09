# CDumpProcessor::ReadDumpHeader(void)

- ea: `0x14003db48`
- end: `0x14003ddfb`
- name: `?ReadDumpHeader@CDumpProcessor@@AEAAJXZ`
- size: `691`
- prototype: `__int64 __fastcall(CDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14003d7d4`

## callees

- `0x1400030a8`
- `0x140005430`
- `0x140034d9c`
- `0x14003db48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dbb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dd25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dbb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dd25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003dde0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003dde0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14003dc23`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14003dc23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003db9e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003db9e`

## string_xrefs

- `0x14003dbca`: `CDumpProcessor::ReadDumpHeader`
- `0x14003dcbf`: `CDumpProcessor::ReadDumpHeader`
- `0x14003dcf1`: `CDumpProcessor::ReadDumpHeader`
- `0x14003dd3f`: `CDumpProcessor::ReadDumpHeader`
- `0x14003dd8f`: `CDumpProcessor::ReadDumpHeader`
- `0x14003dbec`: `Unable to open the file %ws for read`
- `0x14003dce5`: `Invalid dump file signature, path: %ws`
- `0x14003dd61`: `Failure reading the dump file header, path: %ws`

## pseudocode

```c
__int64 __fastcall CDumpProcessor::ReadDumpHeader(CDumpProcessor *this)
{
  const WCHAR *v1; // rbp
  char *FileW; // rbx
  signed int LastError; // eax
  signed int v5; // edi
  __int64 v6; // rax
  signed int v7; // eax
  wil::details *lpOverlapped; // [rsp+20h] [rbp-38h]
  wil::details *lpOverlappeda; // [rsp+20h] [rbp-38h]
  wil::details *lpOverlappedb; // [rsp+20h] [rbp-38h]
  wil::details *lpOverlappedc; // [rsp+20h] [rbp-38h]
  char *v13; // [rsp+30h] [rbp-28h]
  char *v14; // [rsp+30h] [rbp-28h]
  wil::details::in1diag4 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  v1 = (const WCHAR *)*((_QWORD *)this + 22);
  NumberOfBytesRead = 0;
  if ( !v1 || !*v1 )
  {
    v5 = -2147024894;
    LODWORD(lpOverlapped) = -2147024894;
    FileW = 0;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x1BA,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
      "CDumpProcessor::ReadDumpHeader",
      lpOverlapped,
      (int)"No dump file to get header from",
      v13);
    *((_DWORD *)this + 2136) = -2147024894;
LABEL_23:
    *((_DWORD *)this + 2135) = v5;
    goto LABEL_24;
  }
  FileW = (char *)CreateFileW(v1, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LODWORD(lpOverlappeda) = v5;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
      "CDumpProcessor::ReadDumpHeader",
      lpOverlappeda,
      (int)"Unable to open the file %ws for read",
      (const char *)v1);
    goto LABEL_23;
  }
  if ( !ReadFile(FileW, (char *)this + 208, 0x2000u, &NumberOfBytesRead, 0) )
  {
    v7 = GetLastError();
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LODWORD(lpOverlappedb) = v5;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
      "CDumpProcessor::ReadDumpHeader",
      lpOverlappedb,
      (int)"Failure reading the dump file header, path: %ws",
      (const char *)v1);
    *((_DWORD *)this + 2136) = v5;
    goto LABEL_24;
  }
  if ( NumberOfBytesRead != 0x2000 || *((_DWORD *)this + 52) != 1162297680 || *((_DWORD *)this + 53) != 875976004 )
  {
    LODWORD(lpOverlappedb) = -2147024883;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
      "CDumpProcessor::ReadDumpHeader",
      lpOverlappedb,
      (int)"Invalid dump file signature, path: %ws",
      (const char *)v1);
    *((_DWORD *)this + 2136) = -2147024883;
    goto LABEL_16;
  }
  v6 = *((_QWORD *)this + 37);
  *((_DWORD *)this + 66) &= ~0x10000000u;
  v5 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         (char *)this + 8400,
         L"0x%08x (0x%016I64x, 0x%016I64x, 0x%016I64x, 0x%016I64x)",
         *((unsigned int *)this + 66),
         *((_QWORD *)this + 34),
         *((_QWORD *)this + 35),
         *((_QWORD *)this + 36),
         v6);
  if ( v5 >= 0 )
  {
LABEL_16:
    v5 = 0;
    goto LABEL_25;
  }
  LODWORD(lpOverlappedc) = v5;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x1EC,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
    "CDumpProcessor::ReadDumpHeader",
    lpOverlappedc,
    (int)"Sprintf failed for bug check string",
    v14);
LABEL_24:
  memset_0((char *)this + 208, 0, 0x2000u);
LABEL_25:
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003db48  mov     rax, rsp
0x14003db4b  mov     [rax+10h], rbx
0x14003db4f  mov     [rax+18h], rbp
0x14003db53  push    rsi
0x14003db54  push    rdi
0x14003db55  push    r14
0x14003db57  sub     rsp, 40h
0x14003db5b  mov     rbp, [rcx+0B0h]
0x14003db62  xor     r14d, r14d
0x14003db65  mov     [rax+8], r14d
0x14003db69  mov     rsi, rcx
0x14003db6c  test    rbp, rbp
0x14003db6f  jz      loc_14003DD7E
0x14003db75  cmp     [rbp+0], r14w
0x14003db7a  jz      loc_14003DD7E
0x14003db80  mov     [rax-28h], r14
0x14003db84  lea     r8d, [r14+1]; dwShareMode
0x14003db88  mov     [rax-30h], r14d
0x14003db8c  xor     r9d, r9d; lpSecurityAttributes
0x14003db8f  mov     edx, 80000000h; dwDesiredAccess
0x14003db94  mov     dword ptr [rax-38h], 3
0x14003db9b  mov     rcx, rbp; lpFileName
0x14003db9e  call    cs:__imp_CreateFileW
0x14003dba4  mov     rbx, rax
0x14003dba7  inc     rax
0x14003dbaa  cmp     rax, 1
0x14003dbae  ja      short loc_14003DC06
0x14003dbb0  call    cs:__imp_GetLastError
0x14003dbb6  mov     edi, eax
0x14003dbb8  test    eax, eax
0x14003dbba  jle     short loc_14003DBC5
0x14003dbbc  movzx   edi, ax
0x14003dbbf  or      edi, 80070000h
0x14003dbc5  mov     rcx, [rsp+58h]; this
0x14003dbca  lea     r9, aCdumpprocessor_3; "CDumpProcessor::ReadDumpHeader"
0x14003dbd1  test    edi, edi
0x14003dbd3  mov     [rsp+58h+var_28], rbp; char *
0x14003dbd8  mov     eax, 80004005h
0x14003dbdd  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003dbe4  cmovns  edi, eax
0x14003dbe7  mov     edx, 1CDh; void *
0x14003dbec  lea     rax, aUnableToOpenTh; "Unable to open the file %ws for read"
0x14003dbf3  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003dbf8  mov     dword ptr [rsp+58h+lpOverlapped], edi; wil::details *
0x14003dbfc  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003dc01  jmp     loc_14003DDB9
0x14003dc06  lea     rdi, [rsi+0D0h]
0x14003dc0d  mov     [rsp+58h+lpOverlapped], r14; lpOverlapped
0x14003dc12  mov     rdx, rdi; lpBuffer
0x14003dc15  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14003dc1a  mov     r8d, 2000h; nNumberOfBytesToRead
0x14003dc20  mov     rcx, rbx; hFile
0x14003dc23  call    cs:__imp_ReadFile
0x14003dc29  test    eax, eax
0x14003dc2b  jz      loc_14003DD25
0x14003dc31  cmp     [rsp+58h+NumberOfBytesRead], 2000h
0x14003dc39  jnz     loc_14003DCE0
0x14003dc3f  cmp     dword ptr [rdi], 45474150h
0x14003dc45  jnz     loc_14003DCE0
0x14003dc4b  cmp     dword ptr [rsi+0D4h], 34365544h
0x14003dc55  jnz     loc_14003DCE0
0x14003dc5b  mov     rax, [rsi+128h]
0x14003dc62  lea     rcx, [rsi+20D0h]
0x14003dc69  btr     dword ptr [rsi+108h], 1Ch
0x14003dc71  lea     rdx, a0x08x0x016i64x; "0x%08x (0x%016I64x, 0x%016I64x, 0x%016I"...
0x14003dc78  mov     r9, [rsi+110h]
0x14003dc7f  mov     r8d, [rsi+108h]
0x14003dc86  mov     [rsp+58h+var_28], rax; char *
0x14003dc8b  mov     rax, [rsi+120h]
0x14003dc92  mov     qword ptr [rsp+58h+var_30], rax
0x14003dc97  mov     rax, [rsi+118h]
0x14003dc9e  mov     [rsp+58h+lpOverlapped], rax
0x14003dca3  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14003dca8  mov     edi, eax
0x14003dcaa  test    eax, eax
0x14003dcac  jns     short loc_14003DD1D
0x14003dcae  mov     rcx, [rsp+58h]; this
0x14003dcb3  lea     rax, aSprintfFailedF_0; "Sprintf failed for bug check string"
0x14003dcba  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003dcbf  lea     r9, aCdumpprocessor_3; "CDumpProcessor::ReadDumpHeader"
0x14003dcc6  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003dccd  mov     dword ptr [rsp+58h+lpOverlapped], edi; wil::details *
0x14003dcd1  mov     edx, 1ECh; void *
0x14003dcd6  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003dcdb  jmp     loc_14003DDBF
0x14003dce0  mov     rcx, [rsp+58h]; this
0x14003dce5  lea     rax, aInvalidDumpFil_0; "Invalid dump file signature, path: %ws"
0x14003dcec  mov     [rsp+58h+var_28], rbp; char *
0x14003dcf1  lea     r9, aCdumpprocessor_3; "CDumpProcessor::ReadDumpHeader"
0x14003dcf8  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003dcfd  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003dd04  mov     edi, 8007000Dh
0x14003dd09  mov     edx, 1F3h; void *
0x14003dd0e  mov     dword ptr [rsp+58h+lpOverlapped], edi; wil::details *
0x14003dd12  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003dd17  mov     [rsi+2160h], edi
0x14003dd1d  mov     edi, r14d
0x14003dd20  jmp     loc_14003DDD3
0x14003dd25  call    cs:__imp_GetLastError
0x14003dd2b  mov     edi, eax
0x14003dd2d  test    eax, eax
0x14003dd2f  jle     short loc_14003DD3A
0x14003dd31  movzx   edi, ax
0x14003dd34  or      edi, 80070000h
0x14003dd3a  mov     rcx, [rsp+58h]; this
0x14003dd3f  lea     r9, aCdumpprocessor_3; "CDumpProcessor::ReadDumpHeader"
0x14003dd46  test    edi, edi
0x14003dd48  mov     [rsp+58h+var_28], rbp; char *
0x14003dd4d  mov     eax, 80004005h
0x14003dd52  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003dd59  cmovns  edi, eax
0x14003dd5c  mov     edx, 1FBh; void *
0x14003dd61  lea     rax, aFailureReading; "Failure reading the dump file header, p"...
0x14003dd68  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003dd6d  mov     dword ptr [rsp+58h+lpOverlapped], edi; wil::details *
0x14003dd71  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003dd76  mov     [rsi+2160h], edi
0x14003dd7c  jmp     short loc_14003DDBF
0x14003dd7e  mov     rcx, [rsp+58h]; this
0x14003dd83  lea     rax, aNoDumpFileToGe; "No dump file to get header from"
0x14003dd8a  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003dd8f  lea     r9, aCdumpprocessor_3; "CDumpProcessor::ReadDumpHeader"
0x14003dd96  mov     edi, 80070002h
0x14003dd9b  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003dda2  mov     edx, 1BAh; void *
0x14003dda7  mov     dword ptr [rsp+58h+lpOverlapped], edi; wil::details *
0x14003ddab  mov     rbx, r14
0x14003ddae  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ddb3  mov     [rsi+2160h], edi
0x14003ddb9  mov     [rsi+215Ch], edi
0x14003ddbf  lea     rcx, [rsi+0D0h]; void *
0x14003ddc6  xor     edx, edx; Val
0x14003ddc8  mov     r8d, 2000h; Size
0x14003ddce  call    memset_0
0x14003ddd3  lea     rax, [rbx+1]
0x14003ddd7  cmp     rax, 1
0x14003dddb  jbe     short loc_14003DDE6
0x14003dddd  mov     rcx, rbx; hObject
0x14003dde0  call    cs:__imp_CloseHandle
0x14003dde6  mov     rbx, [rsp+58h+arg_8]
0x14003ddeb  mov     eax, edi
0x14003dded  mov     rbp, [rsp+58h+arg_10]
0x14003ddf2  add     rsp, 40h
0x14003ddf6  pop     r14
0x14003ddf8  pop     rdi
0x14003ddf9  pop     rsi
0x14003ddfa  retn
```
