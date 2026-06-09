# CLiveDumpProcessor::ReadDumpHeader(void)

- ea: `0x1400418e8`
- end: `0x140041b38`
- name: `?ReadDumpHeader@CLiveDumpProcessor@@AEAAJXZ`
- size: `592`
- prototype: `__int64 __fastcall(CLiveDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400416f4`

## callees

- `0x1400030f8`
- `0x1400054e4`
- `0x1400372dc`
- `0x1400418e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041a9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041a8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041a8a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140041975`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140041975`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140041939`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140041939`

## string_xrefs

- `0x140041abb`: `Unable to open the file %ws for read`
- `0x140041a1b`: `CLiveDumpProcessor::ReadDumpHeader`
- `0x140041a4f`: `CLiveDumpProcessor::ReadDumpHeader`
- `0x140041ace`: `CLiveDumpProcessor::ReadDumpHeader`
- `0x140041b0a`: `CLiveDumpProcessor::ReadDumpHeader`

## pseudocode

```c
__int64 __fastcall CLiveDumpProcessor::ReadDumpHeader(CLiveDumpProcessor *this)
{
  const WCHAR *v1; // rsi
  char *FileW; // rbx
  __int64 v4; // rax
  signed int v5; // edi
  signed int LastError; // eax
  wil::details *lpOverlapped; // [rsp+20h] [rbp-58h]
  wil::details *lpOverlappeda; // [rsp+20h] [rbp-58h]
  wil::details *lpOverlappedb; // [rsp+20h] [rbp-58h]
  wil::details *lpOverlappedc; // [rsp+20h] [rbp-58h]
  char *v12; // [rsp+30h] [rbp-48h]
  char *v13; // [rsp+30h] [rbp-48h]
  wil::details::in1diag4 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+8h] BYREF

  v1 = (const WCHAR *)*((_QWORD *)this + 1049);
  NumberOfBytesRead = 0;
  if ( v1 && *v1 )
  {
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
        (void *)0x2DE,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
        "CLiveDumpProcessor::ReadDumpHeader",
        lpOverlappeda,
        (int)"Unable to open the file %ws for read",
        (const char *)v1);
    }
    else
    {
      if ( ReadFile(FileW, (char *)this + 136, 0x2000u, &NumberOfBytesRead, 0)
        && NumberOfBytesRead == 0x2000
        && *((_DWORD *)this + 34) == 1162297680
        && *((_DWORD *)this + 35) == 875976004 )
      {
        v4 = *((_QWORD *)this + 28);
        *((_DWORD *)this + 48) &= ~0x10000000u;
        v5 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
               (char *)this + 8328,
               L"0x%08x (0x%016I64x, 0x%016I64x, 0x%016I64x, 0x%016I64x)",
               *((unsigned int *)this + 48),
               *((_QWORD *)this + 25),
               *((_QWORD *)this + 26),
               *((_QWORD *)this + 27),
               v4);
        if ( v5 >= 0 )
        {
          v5 = 0;
        }
        else
        {
          LODWORD(lpOverlappedc) = v5;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0x2FA,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
            "CLiveDumpProcessor::ReadDumpHeader",
            lpOverlappedc,
            (int)"Sprintf failed for bug check string",
            v13);
        }
      }
      else
      {
        LODWORD(lpOverlappedb) = -2147467259;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x300,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
          "CLiveDumpProcessor::ReadDumpHeader",
          lpOverlappedb,
          (int)"Invalid dump file %ws",
          (const char *)v1);
        memset_0((char *)this + 136, 0, 0x2000u);
        v5 = -2147467259;
      }
      CloseHandle(FileW);
    }
  }
  else
  {
    LODWORD(lpOverlapped) = -2147467259;
    v5 = -2147467259;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x2CE,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::ReadDumpHeader",
      lpOverlapped,
      (int)"No dump file to get header from",
      v12);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400418e8  mov     rax, rsp
0x1400418eb  push    rbx
0x1400418ec  push    rbp
0x1400418ed  push    rsi
0x1400418ee  push    rdi
0x1400418ef  push    r14
0x1400418f1  push    r15
0x1400418f3  sub     rsp, 48h
0x1400418f7  mov     rsi, [rcx+20C8h]
0x1400418fe  xor     r15d, r15d
0x140041901  mov     [rax+8], r15d
0x140041905  mov     rdi, rcx
0x140041908  test    rsi, rsi
0x14004190b  jz      loc_140041AF4
0x140041911  cmp     [rsi], r15w
0x140041915  jz      loc_140041AF4
0x14004191b  mov     [rax-48h], r15
0x14004191f  lea     r8d, [r15+1]; dwShareMode
0x140041923  mov     [rax-50h], r15d
0x140041927  xor     r9d, r9d; lpSecurityAttributes
0x14004192a  mov     edx, 80000000h; dwDesiredAccess
0x14004192f  mov     dword ptr [rax-58h], 3
0x140041936  mov     rcx, rsi; lpFileName
0x140041939  call    cs:__imp_CreateFileW
0x140041940  nop     dword ptr [rax+rax+00h]
0x140041945  mov     rbx, rax
0x140041948  inc     rax
0x14004194b  cmp     rax, 1
0x14004194f  jbe     loc_140041A9B
0x140041955  lea     r14, [rdi+88h]
0x14004195c  mov     [rsp+78h+lpOverlapped], r15; lpOverlapped
0x140041961  mov     rdx, r14; lpBuffer
0x140041964  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14004196c  mov     r8d, 2000h; nNumberOfBytesToRead
0x140041972  mov     rcx, rbx; hFile
0x140041975  call    cs:__imp_ReadFile
0x14004197c  nop     dword ptr [rax+rax+00h]
0x140041981  test    eax, eax
0x140041983  jz      loc_140041A3E
0x140041989  cmp     [rsp+78h+NumberOfBytesRead], 2000h
0x140041994  jnz     loc_140041A3E
0x14004199a  cmp     dword ptr [r14], 45474150h
0x1400419a1  jnz     loc_140041A3E
0x1400419a7  cmp     dword ptr [rdi+8Ch], 34365544h
0x1400419b1  jnz     loc_140041A3E
0x1400419b7  mov     rax, [rdi+0E0h]
0x1400419be  lea     rcx, [rdi+2088h]
0x1400419c5  btr     dword ptr [rdi+0C0h], 1Ch
0x1400419cd  lea     rdx, a0x08x0x016i64x; "0x%08x (0x%016I64x, 0x%016I64x, 0x%016I"...
0x1400419d4  mov     r9, [rdi+0C8h]
0x1400419db  mov     r8d, [rdi+0C0h]
0x1400419e2  mov     [rsp+78h+var_48], rax; char *
0x1400419e7  mov     rax, [rdi+0D8h]
0x1400419ee  mov     qword ptr [rsp+78h+var_50], rax
0x1400419f3  mov     rax, [rdi+0D0h]
0x1400419fa  mov     [rsp+78h+lpOverlapped], rax
0x1400419ff  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140041a04  mov     edi, eax
0x140041a06  test    eax, eax
0x140041a08  jns     short loc_140041A39
0x140041a0a  mov     rcx, [rsp+78h]; this
0x140041a0f  lea     rax, aSprintfFailedF_0; "Sprintf failed for bug check string"
0x140041a16  mov     qword ptr [rsp+78h+var_50], rax; int
0x140041a1b  lea     r9, aClivedumpproce_2; "CLiveDumpProcessor::ReadDumpHeader"
0x140041a22  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140041a29  mov     dword ptr [rsp+78h+lpOverlapped], edi; wil::details *
0x140041a2d  mov     edx, 2FAh; void *
0x140041a32  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041a37  jmp     short loc_140041A87
0x140041a39  mov     edi, r15d
0x140041a3c  jmp     short loc_140041A87
0x140041a3e  mov     rcx, [rsp+78h]; this
0x140041a43  lea     rax, aInvalidDumpFil; "Invalid dump file %ws"
0x140041a4a  mov     [rsp+78h+var_48], rsi; char *
0x140041a4f  lea     r9, aClivedumpproce_2; "CLiveDumpProcessor::ReadDumpHeader"
0x140041a56  mov     qword ptr [rsp+78h+var_50], rax; int
0x140041a5b  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140041a62  mov     ebp, 80004005h
0x140041a67  mov     edx, 300h; void *
0x140041a6c  mov     dword ptr [rsp+78h+lpOverlapped], ebp; wil::details *
0x140041a70  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041a75  xor     edx, edx; Val
0x140041a77  mov     r8d, 2000h; Size
0x140041a7d  mov     rcx, r14; void *
0x140041a80  call    memset_0
0x140041a85  mov     edi, ebp
0x140041a87  mov     rcx, rbx; hObject
0x140041a8a  call    cs:__imp_CloseHandle
0x140041a91  nop     dword ptr [rax+rax+00h]
0x140041a96  jmp     loc_140041B28
0x140041a9b  call    cs:__imp_GetLastError
0x140041aa2  nop     dword ptr [rax+rax+00h]
0x140041aa7  mov     edi, eax
0x140041aa9  test    eax, eax
0x140041aab  jle     short loc_140041AB6
0x140041aad  movzx   edi, ax
0x140041ab0  or      edi, 80070000h
0x140041ab6  mov     rcx, [rsp+78h]; this
0x140041abb  lea     rax, aUnableToOpenTh; "Unable to open the file %ws for read"
0x140041ac2  test    edi, edi
0x140041ac4  mov     [rsp+78h+var_48], rsi; char *
0x140041ac9  mov     qword ptr [rsp+78h+var_50], rax; int
0x140041ace  lea     r9, aClivedumpproce_2; "CLiveDumpProcessor::ReadDumpHeader"
0x140041ad5  mov     ebp, 80004005h
0x140041ada  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140041ae1  cmovns  edi, ebp
0x140041ae4  mov     edx, 2DEh; void *
0x140041ae9  mov     dword ptr [rsp+78h+lpOverlapped], edi; wil::details *
0x140041aed  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041af2  jmp     short loc_140041B28
0x140041af4  mov     rcx, [rsp+78h]; this
0x140041af9  lea     rax, aNoDumpFileToGe; "No dump file to get header from"
0x140041b00  mov     ebp, 80004005h
0x140041b05  mov     qword ptr [rsp+78h+var_50], rax; int
0x140041b0a  lea     r9, aClivedumpproce_2; "CLiveDumpProcessor::ReadDumpHeader"
0x140041b11  mov     dword ptr [rsp+78h+lpOverlapped], ebp; wil::details *
0x140041b15  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140041b1c  mov     edx, 2CEh; void *
0x140041b21  mov     edi, ebp
0x140041b23  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041b28  mov     eax, edi
0x140041b2a  add     rsp, 48h
0x140041b2e  pop     r15
0x140041b30  pop     r14
0x140041b32  pop     rdi
0x140041b33  pop     rsi
0x140041b34  pop     rbp
0x140041b35  pop     rbx
0x140041b36  retn
```
