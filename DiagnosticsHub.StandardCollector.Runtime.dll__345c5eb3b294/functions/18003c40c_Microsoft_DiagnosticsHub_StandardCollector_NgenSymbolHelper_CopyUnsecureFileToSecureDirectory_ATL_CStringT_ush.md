# Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::CopyUnsecureFileToSecureDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18003c40c`
- end: `0x18003c73a`
- name: `?CopyUnsecureFileToSecureDirectory@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@AEAA_NAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z`
- size: `814`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003ba48`

## callees

- `0x180009e14`
- `0x1800253cc`
- `0x180026fec`
- `0x18003c078`
- `0x18003c13c`
- `0x18003c40c`
- `0x18003d864`
- `0x18004165c`
- `0x180049b50`

## import_xrefs

- `VCRUNTIME140!memset` at `0x18003c5da`
- `VCRUNTIME140!memset` at `0x18003c5da`
- `KERNEL32!ReadFile` at `0x18003c618`
- `KERNEL32!ReadFile` at `0x18003c618`
- `KERNEL32!CreateFileW` at `0x18003c497`
- `KERNEL32!CreateFileW` at `0x18003c54e`
- `KERNEL32!CreateFileW` at `0x18003c497`
- `KERNEL32!CreateFileW` at `0x18003c54e`
- `KERNEL32!CloseHandle` at `0x18003c704`
- `KERNEL32!CloseHandle` at `0x18003c713`
- `KERNEL32!CloseHandle` at `0x18003c704`
- `KERNEL32!CloseHandle` at `0x18003c713`
- `KERNEL32!GetLastError` at `0x18003c4a6`
- `KERNEL32!GetLastError` at `0x18003c574`
- `KERNEL32!GetLastError` at `0x18003c6a6`
- `KERNEL32!GetLastError` at `0x18003c6cc`
- `KERNEL32!GetLastError` at `0x18003c4a6`
- `KERNEL32!GetLastError` at `0x18003c574`
- `KERNEL32!GetLastError` at `0x18003c6a6`
- `KERNEL32!GetLastError` at `0x18003c6cc`
- `KERNEL32!WriteFile` at `0x18003c63e`
- `KERNEL32!WriteFile` at `0x18003c63e`

## string_xrefs

- `0x18003c452`: `Unable to impersonate user, unable to copy file`
- `0x18003c4cd`: `Unexpected failure when grabbing file handle for file to copy. (ErrorCode:  %#08x)`
- `0x18003c4f2`: `Unable to revert impersonation, unable to write to secure directory.`
- `0x18003c507`: `Unable to verify or write to secure directory path, copy failed.`
- `0x18003c6d2`: `Unexpected failure when reading original file, unable to copy it over. (ErrorCode:  %#08x)`
- `0x18003c6ac`: `Unexpected failure when writing to destination file, unable to copy it over. (ErrorCode:  %#08x)`
- `0x18003c67a`: `Number of bytes read was %s while number of bytes written was %s during the copy, unable to copy it over.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::CopyUnsecureFileToSecureDirectory(
        Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper *this,
        LPCWSTR *a2,
        LPCWSTR *a3,
        DiagHubCommon **a4)
{
  char v9; // di
  HANDLE FileW; // rax
  void *v11; // r14
  DWORD LastError; // eax
  const unsigned __int16 *v13; // rdx
  HANDLE v14; // rax
  void *v15; // rsi
  DiagHubCommon::LogStream *v16; // rbx
  DWORD v17; // eax
  __int64 v18; // r12
  DiagHubCommon::LogStream *v19; // rbx
  DWORD v20; // eax
  DiagHubCommon::LogStream *v21; // rbx
  DWORD v22; // eax
  LPVOID lpBuffer[2]; // [rsp+40h] [rbp-40h] BYREF
  char *v24; // [rsp+50h] [rbp-30h]
  HANDLE v25; // [rsp+58h] [rbp-28h]
  HANDLE v26; // [rsp+60h] [rbp-20h]
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-18h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+70h] [rbp-10h] BYREF

  if ( !Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ImpersonateUser(this) )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
      L"Unable to impersonate user, unable to copy file");
    return 0;
  }
  v9 = 1;
  FileW = CreateFileW(*a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v11 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( *((_QWORD *)_logger + 21) != *((_QWORD *)_logger + 22) && LastError - 2 > 1 )
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
        L"Unexpected failure when grabbing file handle for file to copy. (ErrorCode:  %#08x)",
        LastError);
    return 0;
  }
  v25 = FileW;
  if ( Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::RevertImpersonation(this) )
  {
    if ( (unsigned int)DiagHubCommon::VerifyOrCreateDirectoryPath(*a4, v13) )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
        L"Unable to verify or write to secure directory path, copy failed.");
    }
    else
    {
      v14 = CreateFileW(*a3, 0x40000000u, 0, 0, 1u, 0x80u, 0);
      v15 = v14;
      if ( v14 != (HANDLE)-1LL )
      {
        v26 = v14;
        v18 = *((unsigned int *)this + 22);
        *(_OWORD *)lpBuffer = 0;
        v24 = 0;
        if ( v18 )
        {
          lpBuffer[0] = (LPVOID)std::_Allocate<16,std::_Default_allocate_traits>((unsigned int)v18);
          v24 = (char *)lpBuffer[0] + v18;
          memset(lpBuffer[0], 0, (unsigned int)v18);
          lpBuffer[1] = (char *)lpBuffer[0] + v18;
          *(_QWORD *)NumberOfBytesWritten = 0;
          std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(NumberOfBytesWritten);
        }
        NumberOfBytesRead = 1;
        while ( 1 )
        {
          NumberOfBytesWritten[0] = 0;
          if ( !ReadFile(v11, lpBuffer[0], *((_DWORD *)this + 22), &NumberOfBytesRead, 0) )
            break;
          if ( !WriteFile(v15, lpBuffer[0], NumberOfBytesRead, NumberOfBytesWritten, 0) )
          {
            v19 = _logger;
            if ( *((_QWORD *)_logger + 21) != *((_QWORD *)_logger + 22) )
            {
              v20 = GetLastError();
              DiagHubCommon::LogStream::Write(
                (DiagHubCommon::LogStream *)((char *)v19 + 168),
                L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
                L"Unexpected failure when writing to destination file, unable to copy it over. (ErrorCode:  %#08x)",
                v20);
            }
            goto LABEL_31;
          }
          if ( NumberOfBytesRead != NumberOfBytesWritten[0] )
          {
            if ( *((_QWORD *)_logger + 21) != *((_QWORD *)_logger + 22) )
              DiagHubCommon::LogStream::Write(
                (DiagHubCommon::LogStream *)((char *)_logger + 168),
                L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
                L"Number of bytes read was %s while number of bytes written was %s during the copy, unable to copy it over.");
            goto LABEL_31;
          }
          if ( NumberOfBytesRead != *((_DWORD *)this + 22) )
            goto LABEL_32;
        }
        v21 = _logger;
        if ( *((_QWORD *)_logger + 21) != *((_QWORD *)_logger + 22) )
        {
          v22 = GetLastError();
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)v21 + 168),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
            L"Unexpected failure when reading original file, unable to copy it over. (ErrorCode:  %#08x)",
            v22);
        }
LABEL_31:
        v9 = 0;
LABEL_32:
        std::vector<unsigned char>::~vector<unsigned char>(lpBuffer);
        if ( v15 )
          CloseHandle(v15);
        goto LABEL_34;
      }
      v16 = _logger;
      if ( *((_QWORD *)_logger + 21) != *((_QWORD *)_logger + 22) )
      {
        v17 = GetLastError();
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)v16 + 168),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
          L"Unexpected failure when creating destination file. (ErrorCode:  %#08x)",
          v17);
      }
    }
  }
  else
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
      L"Unable to revert impersonation, unable to write to secure directory.");
  }
  v9 = 0;
LABEL_34:
  if ( v11 )
    CloseHandle(v11);
  return v9;
}

```

## disassembly

```asm
0x18003c40c  push    rbp
0x18003c40e  push    rbx
0x18003c40f  push    rsi
0x18003c410  push    rdi
0x18003c411  push    r12
0x18003c413  push    r14
0x18003c415  push    r15
0x18003c417  mov     rbp, rsp
0x18003c41a  sub     rsp, 80h
0x18003c421  mov     rax, cs:__security_cookie
0x18003c428  xor     rax, rsp
0x18003c42b  mov     [rbp+var_8], rax
0x18003c42f  mov     rsi, r9
0x18003c432  mov     r12, r8
0x18003c435  mov     rbx, rdx
0x18003c438  mov     r15, rcx
0x18003c43b  call    ?ImpersonateUser@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@AEAA_NXZ; Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ImpersonateUser(void)
0x18003c440  test    al, al
0x18003c442  jnz     short loc_18003C46C
0x18003c444  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c44b  add     rcx, 0A8h; this
0x18003c452  lea     r8, aUnableToImpers_1; "Unable to impersonate user, unable to c"...
0x18003c459  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c460  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c465  xor     al, al
0x18003c467  jmp     loc_18003C71C
0x18003c46c  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18003c475  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003c47d  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x18003c485  xor     r9d, r9d; lpSecurityAttributes
0x18003c488  lea     edi, [r9+1]
0x18003c48c  mov     r8d, edi; dwShareMode
0x18003c48f  mov     edx, 80000000h; dwDesiredAccess
0x18003c494  mov     rcx, [rbx]; lpFileName
0x18003c497  call    cs:__imp_CreateFileW
0x18003c49d  mov     r14, rax
0x18003c4a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c4a4  jnz     short loc_18003C4E2
0x18003c4a6  call    cs:__imp_GetLastError
0x18003c4ac  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c4b3  add     rcx, 0A8h; this
0x18003c4ba  mov     rdx, [rcx+8]
0x18003c4be  cmp     [rcx], rdx
0x18003c4c1  jz      short loc_18003C465
0x18003c4c3  lea     edx, [rax-2]
0x18003c4c6  cmp     edx, edi
0x18003c4c8  jbe     short loc_18003C465
0x18003c4ca  mov     r9d, eax
0x18003c4cd  lea     r8, aUnexpectedFail_1; "Unexpected failure when grabbing file h"...
0x18003c4d4  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c4db  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c4e0  jmp     short loc_18003C465
0x18003c4e2  mov     [rbp+var_28], r14
0x18003c4e6  mov     rcx, r15; this
0x18003c4e9  call    ?RevertImpersonation@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@AEAA_NXZ; Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::RevertImpersonation(void)
0x18003c4ee  test    al, al
0x18003c4f0  jnz     short loc_18003C4FB
0x18003c4f2  lea     r8, aUnableToRevert; "Unable to revert impersonation, unable "...
0x18003c4f9  jmp     short loc_18003C50E
0x18003c4fb  mov     rcx, [rsi]; this
0x18003c4fe  call    ?VerifyOrCreateDirectoryPath@DiagHubCommon@@YAJPEBG@Z; DiagHubCommon::VerifyOrCreateDirectoryPath(ushort const *)
0x18003c503  test    eax, eax
0x18003c505  jz      short loc_18003C52A
0x18003c507  lea     r8, aUnableToVerify_1; "Unable to verify or write to secure dir"...
0x18003c50e  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c515  add     rcx, 0A8h; this
0x18003c51c  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c523  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c528  jmp     short loc_18003C597
0x18003c52a  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18003c533  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003c53b  mov     [rsp+80h+dwCreationDisposition], edi; dwCreationDisposition
0x18003c53f  xor     r9d, r9d; lpSecurityAttributes
0x18003c542  xor     r8d, r8d; dwShareMode
0x18003c545  mov     edx, 40000000h; dwDesiredAccess
0x18003c54a  mov     rcx, [r12]; lpFileName
0x18003c54e  call    cs:__imp_CreateFileW
0x18003c554  mov     rsi, rax
0x18003c557  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c55b  jnz     short loc_18003C59F
0x18003c55d  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c564  mov     rax, [rbx+0B0h]
0x18003c56b  cmp     [rbx+0A8h], rax
0x18003c572  jz      short loc_18003C597
0x18003c574  call    cs:__imp_GetLastError
0x18003c57a  mov     r9d, eax
0x18003c57d  lea     r8, aUnexpectedFail_0; "Unexpected failure when creating destin"...
0x18003c584  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c58b  lea     rcx, [rbx+0A8h]; this
0x18003c592  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c597  xor     dil, dil
0x18003c59a  jmp     loc_18003C70B
0x18003c59f  mov     [rbp+var_20], rsi
0x18003c5a3  xorps   xmm0, xmm0
0x18003c5a6  xor     eax, eax
0x18003c5a8  mov     r12d, [r15+58h]
0x18003c5ac  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x18003c5b1  mov     [rbp+var_30], rax
0x18003c5b5  test    r12, r12
0x18003c5b8  jz      short loc_18003C5F6
0x18003c5ba  mov     ecx, r12d
0x18003c5bd  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003c5c2  mov     [rbp+lpBuffer], rax
0x18003c5c6  mov     [rbp+lpBuffer+8], rax
0x18003c5ca  lea     rbx, [rax+r12]
0x18003c5ce  mov     [rbp+var_30], rbx
0x18003c5d2  mov     r8d, r12d; Size
0x18003c5d5  xor     edx, edx; Val
0x18003c5d7  mov     rcx, rax; void *
0x18003c5da  call    cs:__imp_memset
0x18003c5e0  mov     [rbp+lpBuffer+8], rbx
0x18003c5e4  mov     qword ptr [rbp+NumberOfBytesWritten], 0
0x18003c5ec  lea     rcx, [rbp+NumberOfBytesWritten]
0x18003c5f0  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18003c5f5  nop
0x18003c5f6  mov     [rbp+NumberOfBytesRead], edi
0x18003c5f9  mov     [rbp+NumberOfBytesWritten], 0
0x18003c600  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOverlapped
0x18003c609  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003c60d  mov     r8d, [r15+58h]; nNumberOfBytesToRead
0x18003c611  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18003c615  mov     rcx, r14; hFile
0x18003c618  call    cs:__imp_ReadFile
0x18003c61e  test    eax, eax
0x18003c620  jz      loc_18003C6B5
0x18003c626  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOverlapped
0x18003c62f  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003c633  mov     r8d, [rbp+NumberOfBytesRead]; nNumberOfBytesToWrite
0x18003c637  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18003c63b  mov     rcx, rsi; hFile
0x18003c63e  call    cs:__imp_WriteFile
0x18003c644  test    eax, eax
0x18003c646  jz      short loc_18003C68F
0x18003c648  mov     r9d, [rbp+NumberOfBytesRead]
0x18003c64c  mov     edx, [rbp+NumberOfBytesWritten]
0x18003c64f  cmp     r9d, edx
0x18003c652  jnz     short loc_18003C65F
0x18003c654  cmp     r9d, [r15+58h]
0x18003c658  jz      short loc_18003C5F9
0x18003c65a  jmp     loc_18003C6F2
0x18003c65f  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c666  add     rcx, 0A8h; this
0x18003c66d  mov     rax, [rcx+8]
0x18003c671  cmp     [rcx], rax
0x18003c674  jz      short loc_18003C6EF
0x18003c676  mov     [rsp+80h+dwCreationDisposition], edx
0x18003c67a  lea     r8, aNumberOfBytesR; "Number of bytes read was %s while numbe"...
0x18003c681  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c688  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c68d  jmp     short loc_18003C6EF
0x18003c68f  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c696  mov     rax, [rbx+0B0h]
0x18003c69d  cmp     [rbx+0A8h], rax
0x18003c6a4  jz      short loc_18003C6EF
0x18003c6a6  call    cs:__imp_GetLastError
0x18003c6ac  lea     r8, aUnexpectedFail_2; "Unexpected failure when writing to dest"...
0x18003c6b3  jmp     short loc_18003C6D9
0x18003c6b5  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c6bc  mov     rax, [rbx+0B0h]
0x18003c6c3  cmp     [rbx+0A8h], rax
0x18003c6ca  jz      short loc_18003C6EF
0x18003c6cc  call    cs:__imp_GetLastError
0x18003c6d2  lea     r8, aUnexpectedFail; "Unexpected failure when reading origina"...
0x18003c6d9  mov     r9d, eax
0x18003c6dc  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c6e3  lea     rcx, [rbx+0A8h]; this
0x18003c6ea  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c6ef  xor     dil, dil
0x18003c6f2  lea     rcx, [rbp+lpBuffer]
0x18003c6f6  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18003c6fb  nop
0x18003c6fc  test    rsi, rsi
0x18003c6ff  jz      short loc_18003C70B
0x18003c701  mov     rcx, rsi; hObject
0x18003c704  call    cs:__imp_CloseHandle
0x18003c70a  nop
0x18003c70b  test    r14, r14
0x18003c70e  jz      short loc_18003C719
0x18003c710  mov     rcx, r14; hObject
0x18003c713  call    cs:__imp_CloseHandle
0x18003c719  mov     al, dil
0x18003c71c  mov     rcx, [rbp+var_8]
0x18003c720  xor     rcx, rsp; StackCookie
0x18003c723  call    __security_check_cookie
0x18003c728  add     rsp, 80h
0x18003c72f  pop     r15
0x18003c731  pop     r14
0x18003c733  pop     r12
0x18003c735  pop     rdi
0x18003c736  pop     rsi
0x18003c737  pop     rbx
0x18003c738  pop     rbp
0x18003c739  retn
```
