# CDumpProcessor::ReadDumpHeader(void)

- ea: `0x140040558`
- end: `0x14004082a`
- name: `?ReadDumpHeader@CDumpProcessor@@AEAAJXZ`
- size: `722`
- prototype: `__int64 __fastcall(CDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400401fc`

## callees

- `0x1400030f8`
- `0x1400054e4`
- `0x1400372dc`
- `0x140040558`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400405c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400405c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040747`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140040808`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140040808`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14004063f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14004063f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400405ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400405ae`

## string_xrefs

- `0x1400405e6`: `CDumpProcessor::ReadDumpHeader`
- `0x1400406e1`: `CDumpProcessor::ReadDumpHeader`
- `0x140040713`: `CDumpProcessor::ReadDumpHeader`
- `0x140040767`: `CDumpProcessor::ReadDumpHeader`
- `0x1400407b7`: `CDumpProcessor::ReadDumpHeader`
- `0x140040608`: `Unable to open the file %ws for read`
- `0x140040707`: `Invalid dump file signature, path: %ws`
- `0x140040789`: `Failure reading the dump file header, path: %ws`

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
      (void *)0x1B6,
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
      (void *)0x1C9,
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
      (void *)0x1F7,
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
      (void *)0x1EF,
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
    (void *)0x1E8,
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
0x140040558  mov     rax, rsp
0x14004055b  mov     [rax+10h], rbx
0x14004055f  mov     [rax+18h], rbp
0x140040563  push    rsi
0x140040564  push    rdi
0x140040565  push    r14
0x140040567  sub     rsp, 40h
0x14004056b  mov     rbp, [rcx+0B0h]
0x140040572  xor     r14d, r14d
0x140040575  mov     [rax+8], r14d
0x140040579  mov     rsi, rcx
0x14004057c  test    rbp, rbp
0x14004057f  jz      loc_1400407A6
0x140040585  cmp     [rbp+0], r14w
0x14004058a  jz      loc_1400407A6
0x140040590  mov     [rax-28h], r14
0x140040594  lea     r8d, [r14+1]; dwShareMode
0x140040598  mov     [rax-30h], r14d
0x14004059c  xor     r9d, r9d; lpSecurityAttributes
0x14004059f  mov     edx, 80000000h; dwDesiredAccess
0x1400405a4  mov     dword ptr [rax-38h], 3
0x1400405ab  mov     rcx, rbp; lpFileName
0x1400405ae  call    cs:__imp_CreateFileW
0x1400405b5  nop     dword ptr [rax+rax+00h]
0x1400405ba  mov     rbx, rax
0x1400405bd  inc     rax
0x1400405c0  cmp     rax, 1
0x1400405c4  ja      short loc_140040622
0x1400405c6  call    cs:__imp_GetLastError
0x1400405cd  nop     dword ptr [rax+rax+00h]
0x1400405d2  mov     edi, eax
0x1400405d4  test    eax, eax
0x1400405d6  jle     short loc_1400405E1
0x1400405d8  movzx   edi, ax
0x1400405db  or      edi, 80070000h
0x1400405e1  mov     rcx, [rsp+58h]; this
0x1400405e6  lea     r9, aCdumpprocessor_3; "CDumpProcessor::ReadDumpHeader"
0x1400405ed  test    edi, edi
0x1400405ef  mov     [rsp+58h+var_28], rbp; char *
0x1400405f4  mov     eax, 80004005h
0x1400405f9  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x140040600  cmovns  edi, eax
0x140040603  mov     edx, 1C9h; void *
0x140040608  lea     rax, aUnableToOpenTh; "Unable to open the file %ws for read"
0x14004060f  mov     qword ptr [rsp+58h+var_30], rax; int
0x140040614  mov     dword ptr [rsp+58h+lpOverlapped], edi; wil::details *
0x140040618  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14004061d  jmp     loc_1400407E1
0x140040622  lea     rdi, [rsi+0D0h]
0x140040629  mov     [rsp+58h+lpOverlapped], r14; lpOverlapped
0x14004062e  mov     rdx, rdi; lpBuffer
0x140040631  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140040636  mov     r8d, 2000h; nNumberOfBytesToRead
0x14004063c  mov     rcx, rbx; hFile
0x14004063f  call    cs:__imp_ReadFile
0x140040646  nop     dword ptr [rax+rax+00h]
0x14004064b  test    eax, eax
0x14004064d  jz      loc_140040747
0x140040653  cmp     [rsp+58h+NumberOfBytesRead], 2000h
0x14004065b  jnz     loc_140040702
0x140040661  cmp     dword ptr [rdi], 45474150h
0x140040667  jnz     loc_140040702
0x14004066d  cmp     dword ptr [rsi+0D4h], 34365544h
0x140040677  jnz     loc_140040702
0x14004067d  mov     rax, [rsi+128h]
0x140040684  lea     rcx, [rsi+20D0h]
0x14004068b  btr     dword ptr [rsi+108h], 1Ch
0x140040693  lea     rdx, a0x08x0x016i64x; "0x%08x (0x%016I64x, 0x%016I64x, 0x%016I"...
0x14004069a  mov     r9, [rsi+110h]
0x1400406a1  mov     r8d, [rsi+108h]
0x1400406a8  mov     [rsp+58h+var_28], rax; char *
0x1400406ad  mov     rax, [rsi+120h]
0x1400406b4  mov     qword ptr [rsp+58h+var_30], rax
0x1400406b9  mov     rax, [rsi+118h]
0x1400406c0  mov     [rsp+58h+lpOverlapped], rax
0x1400406c5  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400406ca  mov     edi, eax
0x1400406cc  test    eax, eax
0x1400406ce  jns     short loc_14004073F
0x1400406d0  mov     rcx, [rsp+58h]; this
0x1400406d5  lea     rax, aSprintfFailedF_0; "Sprintf failed for bug check string"
0x1400406dc  mov     qword ptr [rsp+58h+var_30], rax; int
0x1400406e1  lea     r9, aCdumpprocessor_3; "CDumpProcessor::ReadDumpHeader"
0x1400406e8  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x1400406ef  mov     dword ptr [rsp+58h+lpOverlapped], edi; wil::details *
0x1400406f3  mov     edx, 1E8h; void *
0x1400406f8  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400406fd  jmp     loc_1400407E7
0x140040702  mov     rcx, [rsp+58h]; this
0x140040707  lea     rax, aInvalidDumpFil_0; "Invalid dump file signature, path: %ws"
0x14004070e  mov     [rsp+58h+var_28], rbp; char *
0x140040713  lea     r9, aCdumpprocessor_3; "CDumpProcessor::ReadDumpHeader"
0x14004071a  mov     qword ptr [rsp+58h+var_30], rax; int
0x14004071f  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x140040726  mov     edi, 8007000Dh
0x14004072b  mov     edx, 1EFh; void *
0x140040730  mov     dword ptr [rsp+58h+lpOverlapped], edi; wil::details *
0x140040734  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140040739  mov     [rsi+2160h], edi
0x14004073f  mov     edi, r14d
0x140040742  jmp     loc_1400407FB
0x140040747  call    cs:__imp_GetLastError
0x14004074e  nop     dword ptr [rax+rax+00h]
0x140040753  mov     edi, eax
0x140040755  test    eax, eax
0x140040757  jle     short loc_140040762
0x140040759  movzx   edi, ax
0x14004075c  or      edi, 80070000h
0x140040762  mov     rcx, [rsp+58h]; this
0x140040767  lea     r9, aCdumpprocessor_3; "CDumpProcessor::ReadDumpHeader"
0x14004076e  test    edi, edi
0x140040770  mov     [rsp+58h+var_28], rbp; char *
0x140040775  mov     eax, 80004005h
0x14004077a  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x140040781  cmovns  edi, eax
0x140040784  mov     edx, 1F7h; void *
0x140040789  lea     rax, aFailureReading; "Failure reading the dump file header, p"...
0x140040790  mov     qword ptr [rsp+58h+var_30], rax; int
0x140040795  mov     dword ptr [rsp+58h+lpOverlapped], edi; wil::details *
0x140040799  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14004079e  mov     [rsi+2160h], edi
0x1400407a4  jmp     short loc_1400407E7
0x1400407a6  mov     rcx, [rsp+58h]; this
0x1400407ab  lea     rax, aNoDumpFileToGe; "No dump file to get header from"
0x1400407b2  mov     qword ptr [rsp+58h+var_30], rax; int
0x1400407b7  lea     r9, aCdumpprocessor_3; "CDumpProcessor::ReadDumpHeader"
0x1400407be  mov     edi, 80070002h
0x1400407c3  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x1400407ca  mov     edx, 1B6h; void *
0x1400407cf  mov     dword ptr [rsp+58h+lpOverlapped], edi; wil::details *
0x1400407d3  mov     rbx, r14
0x1400407d6  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400407db  mov     [rsi+2160h], edi
0x1400407e1  mov     [rsi+215Ch], edi
0x1400407e7  lea     rcx, [rsi+0D0h]; void *
0x1400407ee  xor     edx, edx; Val
0x1400407f0  mov     r8d, 2000h; Size
0x1400407f6  call    memset_0
0x1400407fb  lea     rax, [rbx+1]
0x1400407ff  cmp     rax, 1
0x140040803  jbe     short loc_140040814
0x140040805  mov     rcx, rbx; hObject
0x140040808  call    cs:__imp_CloseHandle
0x14004080f  nop     dword ptr [rax+rax+00h]
0x140040814  mov     rbx, [rsp+58h+arg_8]
0x140040819  mov     eax, edi
0x14004081b  mov     rbp, [rsp+58h+arg_10]
0x140040820  add     rsp, 40h
0x140040824  pop     r14
0x140040826  pop     rdi
0x140040827  pop     rsi
0x140040828  retn
```
