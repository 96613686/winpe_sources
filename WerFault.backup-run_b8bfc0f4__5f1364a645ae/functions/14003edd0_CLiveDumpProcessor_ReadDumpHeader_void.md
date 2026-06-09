# CLiveDumpProcessor::ReadDumpHeader(void)

- ea: `0x14003edd0`
- end: `0x14003f007`
- name: `?ReadDumpHeader@CLiveDumpProcessor@@AEAAJXZ`
- size: `567`
- prototype: `__int64 __fastcall(CLiveDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14003ebec`

## callees

- `0x1400030a8`
- `0x140005430`
- `0x140034d9c`
- `0x14003edd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ef71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ef71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ef66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ef66`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14003ee57`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14003ee57`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003ee21`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003ee21`

## string_xrefs

- `0x14003ef8b`: `Unable to open the file %ws for read`
- `0x14003eef7`: `CLiveDumpProcessor::ReadDumpHeader`
- `0x14003ef2b`: `CLiveDumpProcessor::ReadDumpHeader`
- `0x14003ef9e`: `CLiveDumpProcessor::ReadDumpHeader`
- `0x14003efda`: `CLiveDumpProcessor::ReadDumpHeader`

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
0x14003edd0  mov     rax, rsp
0x14003edd3  push    rbx
0x14003edd4  push    rbp
0x14003edd5  push    rsi
0x14003edd6  push    rdi
0x14003edd7  push    r14
0x14003edd9  push    r15
0x14003eddb  sub     rsp, 48h
0x14003eddf  mov     rsi, [rcx+20C8h]
0x14003ede6  xor     r15d, r15d
0x14003ede9  mov     [rax+8], r15d
0x14003eded  mov     rdi, rcx
0x14003edf0  test    rsi, rsi
0x14003edf3  jz      loc_14003EFC4
0x14003edf9  cmp     [rsi], r15w
0x14003edfd  jz      loc_14003EFC4
0x14003ee03  mov     [rax-48h], r15
0x14003ee07  lea     r8d, [r15+1]; dwShareMode
0x14003ee0b  mov     [rax-50h], r15d
0x14003ee0f  xor     r9d, r9d; lpSecurityAttributes
0x14003ee12  mov     edx, 80000000h; dwDesiredAccess
0x14003ee17  mov     dword ptr [rax-58h], 3
0x14003ee1e  mov     rcx, rsi; lpFileName
0x14003ee21  call    cs:__imp_CreateFileW
0x14003ee27  mov     rbx, rax
0x14003ee2a  inc     rax
0x14003ee2d  cmp     rax, 1
0x14003ee31  jbe     loc_14003EF71
0x14003ee37  lea     r14, [rdi+88h]
0x14003ee3e  mov     [rsp+78h+lpOverlapped], r15; lpOverlapped
0x14003ee43  mov     rdx, r14; lpBuffer
0x14003ee46  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14003ee4e  mov     r8d, 2000h; nNumberOfBytesToRead
0x14003ee54  mov     rcx, rbx; hFile
0x14003ee57  call    cs:__imp_ReadFile
0x14003ee5d  test    eax, eax
0x14003ee5f  jz      loc_14003EF1A
0x14003ee65  cmp     [rsp+78h+NumberOfBytesRead], 2000h
0x14003ee70  jnz     loc_14003EF1A
0x14003ee76  cmp     dword ptr [r14], 45474150h
0x14003ee7d  jnz     loc_14003EF1A
0x14003ee83  cmp     dword ptr [rdi+8Ch], 34365544h
0x14003ee8d  jnz     loc_14003EF1A
0x14003ee93  mov     rax, [rdi+0E0h]
0x14003ee9a  lea     rcx, [rdi+2088h]
0x14003eea1  btr     dword ptr [rdi+0C0h], 1Ch
0x14003eea9  lea     rdx, a0x08x0x016i64x; "0x%08x (0x%016I64x, 0x%016I64x, 0x%016I"...
0x14003eeb0  mov     r9, [rdi+0C8h]
0x14003eeb7  mov     r8d, [rdi+0C0h]
0x14003eebe  mov     [rsp+78h+var_48], rax; char *
0x14003eec3  mov     rax, [rdi+0D8h]
0x14003eeca  mov     qword ptr [rsp+78h+var_50], rax
0x14003eecf  mov     rax, [rdi+0D0h]
0x14003eed6  mov     [rsp+78h+lpOverlapped], rax
0x14003eedb  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14003eee0  mov     edi, eax
0x14003eee2  test    eax, eax
0x14003eee4  jns     short loc_14003EF15
0x14003eee6  mov     rcx, [rsp+78h]; this
0x14003eeeb  lea     rax, aSprintfFailedF_0; "Sprintf failed for bug check string"
0x14003eef2  mov     qword ptr [rsp+78h+var_50], rax; int
0x14003eef7  lea     r9, aClivedumpproce_2; "CLiveDumpProcessor::ReadDumpHeader"
0x14003eefe  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003ef05  mov     dword ptr [rsp+78h+lpOverlapped], edi; wil::details *
0x14003ef09  mov     edx, 2FAh; void *
0x14003ef0e  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ef13  jmp     short loc_14003EF63
0x14003ef15  mov     edi, r15d
0x14003ef18  jmp     short loc_14003EF63
0x14003ef1a  mov     rcx, [rsp+78h]; this
0x14003ef1f  lea     rax, aInvalidDumpFil; "Invalid dump file %ws"
0x14003ef26  mov     [rsp+78h+var_48], rsi; char *
0x14003ef2b  lea     r9, aClivedumpproce_2; "CLiveDumpProcessor::ReadDumpHeader"
0x14003ef32  mov     qword ptr [rsp+78h+var_50], rax; int
0x14003ef37  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003ef3e  mov     ebp, 80004005h
0x14003ef43  mov     edx, 300h; void *
0x14003ef48  mov     dword ptr [rsp+78h+lpOverlapped], ebp; wil::details *
0x14003ef4c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ef51  xor     edx, edx; Val
0x14003ef53  mov     r8d, 2000h; Size
0x14003ef59  mov     rcx, r14; void *
0x14003ef5c  call    memset_0
0x14003ef61  mov     edi, ebp
0x14003ef63  mov     rcx, rbx; hObject
0x14003ef66  call    cs:__imp_CloseHandle
0x14003ef6c  jmp     loc_14003EFF8
0x14003ef71  call    cs:__imp_GetLastError
0x14003ef77  mov     edi, eax
0x14003ef79  test    eax, eax
0x14003ef7b  jle     short loc_14003EF86
0x14003ef7d  movzx   edi, ax
0x14003ef80  or      edi, 80070000h
0x14003ef86  mov     rcx, [rsp+78h]; this
0x14003ef8b  lea     rax, aUnableToOpenTh; "Unable to open the file %ws for read"
0x14003ef92  test    edi, edi
0x14003ef94  mov     [rsp+78h+var_48], rsi; char *
0x14003ef99  mov     qword ptr [rsp+78h+var_50], rax; int
0x14003ef9e  lea     r9, aClivedumpproce_2; "CLiveDumpProcessor::ReadDumpHeader"
0x14003efa5  mov     ebp, 80004005h
0x14003efaa  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003efb1  cmovns  edi, ebp
0x14003efb4  mov     edx, 2DEh; void *
0x14003efb9  mov     dword ptr [rsp+78h+lpOverlapped], edi; wil::details *
0x14003efbd  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003efc2  jmp     short loc_14003EFF8
0x14003efc4  mov     rcx, [rsp+78h]; this
0x14003efc9  lea     rax, aNoDumpFileToGe; "No dump file to get header from"
0x14003efd0  mov     ebp, 80004005h
0x14003efd5  mov     qword ptr [rsp+78h+var_50], rax; int
0x14003efda  lea     r9, aClivedumpproce_2; "CLiveDumpProcessor::ReadDumpHeader"
0x14003efe1  mov     dword ptr [rsp+78h+lpOverlapped], ebp; wil::details *
0x14003efe5  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003efec  mov     edx, 2CEh; void *
0x14003eff1  mov     edi, ebp
0x14003eff3  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003eff8  mov     eax, edi
0x14003effa  add     rsp, 48h
0x14003effe  pop     r15
0x14003f000  pop     r14
0x14003f002  pop     rdi
0x14003f003  pop     rsi
0x14003f004  pop     rbp
0x14003f005  pop     rbx
0x14003f006  retn
```
