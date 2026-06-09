# ReAgentXMLParser::WriteXMLFile(_LUTF8_STRING *)

- ea: `0x180016ce8`
- end: `0x180016e8f`
- name: `?WriteXMLFile@ReAgentXMLParser@@IEAAKPEAU_LUTF8_STRING@@@Z`
- size: `423`
- prototype: `unsigned int __fastcall(ReAgentXMLParser *__hidden this, struct _LUTF8_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180014754`

## callees

- `0x1800059fc`
- `0x180014730`
- `0x180016ce8`
- `0x18005cf30`

## import_xrefs

- `ntdll!NtClose` at `0x180016e6c`
- `ntdll!NtClose` at `0x180016e6c`
- `KERNEL32!GetLastError` at `0x180016d63`
- `KERNEL32!GetLastError` at `0x180016db5`
- `KERNEL32!GetLastError` at `0x180016e10`
- `KERNEL32!GetLastError` at `0x180016e46`
- `KERNEL32!GetLastError` at `0x180016d63`
- `KERNEL32!GetLastError` at `0x180016db5`
- `KERNEL32!GetLastError` at `0x180016e10`
- `KERNEL32!GetLastError` at `0x180016e46`
- `KERNEL32!WriteFile` at `0x180016e06`
- `KERNEL32!WriteFile` at `0x180016e06`
- `KERNEL32!SetEndOfFile` at `0x180016dab`
- `KERNEL32!SetEndOfFile` at `0x180016dab`
- `KERNEL32!CreateFileW` at `0x180016d45`
- `KERNEL32!CreateFileW` at `0x180016d45`
- `KERNEL32!FlushFileBuffers` at `0x180016e3c`
- `KERNEL32!FlushFileBuffers` at `0x180016e3c`

## string_xrefs

- `0x180016dcc`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180016ddb`: `ReAgentXMLParser::WriteXMLFile %s (0x%x) in file %S line %d`
- `0x180016e1e`: `failed to write file`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReAgentXMLParser::WriteXMLFile(LPCWSTR *this, LPCVOID *a2)
{
  HANDLE FileW; // rax
  char *v4; // rdi
  DWORD LastError; // ebx
  DWORD v6; // eax
  const wchar_t *v7; // r8
  DWORD v8; // eax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-40h]
  HANDLE hFile[2]; // [rsp+40h] [rbp-28h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-18h] BYREF

  hFile[1] = (HANDLE)-2LL;
  hFile[0] = 0;
  NumberOfBytesWritten = 0;
  FileW = CreateFileW(this[1], 0x40000000u, 0, 0, 4u, 0x80u, 0);
  Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoFileHandle>::TakeOwnership(
    hFile,
    FileW);
  v4 = (char *)hFile[0];
  if ( hFile[0] == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError == 5 )
    {
      if ( !ReAgentError )
        ReAgentError = 6;
    }
    else if ( !ReAgentError )
    {
      ReAgentError = 5;
    }
    goto LABEL_16;
  }
  if ( !SetEndOfFile(hFile[0]) )
  {
    v6 = GetLastError();
    LODWORD(dwFlagsAndAttributes) = 845;
    v7 = L"failed to set end of file";
LABEL_9:
    LastError = v6;
    UnattendLogW(
      2,
      L"ReAgentXMLParser::WriteXMLFile %s (0x%x) in file %S line %d",
      v7,
      v6,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
      dwFlagsAndAttributes);
    goto LABEL_16;
  }
  if ( !WriteFile(v4, a2[2], *(_DWORD *)a2, &NumberOfBytesWritten, 0) )
  {
    v6 = GetLastError();
    LODWORD(dwFlagsAndAttributes) = 849;
    v7 = L"failed to write file";
    goto LABEL_9;
  }
  if ( (LPCVOID)NumberOfBytesWritten == *a2 )
  {
    LastError = 0;
    if ( !FlushFileBuffers(v4) )
    {
      v8 = GetLastError();
      UnattendLogW(2, L"Flush file buffers failed: 0x%x", v8);
    }
  }
  else
  {
    LastError = 13;
  }
LABEL_16:
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    NtClose(v4);
  return LastError;
}

```

## disassembly

```asm
0x180016ce8  mov     r11, rsp
0x180016ceb  push    rdi
0x180016cec  sub     rsp, 60h
0x180016cf0  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFEh
0x180016cf8  mov     [r11+18h], rbx
0x180016cfc  mov     rax, cs:__security_cookie
0x180016d03  xor     rax, rsp
0x180016d06  mov     [rsp+68h+var_10], rax
0x180016d0b  mov     rbx, rdx
0x180016d0e  mov     qword ptr [r11-28h], 0
0x180016d16  mov     [rsp+68h+NumberOfBytesWritten], 0
0x180016d1e  mov     qword ptr [r11-38h], 0
0x180016d26  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180016d2e  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x180016d36  xor     r9d, r9d; lpSecurityAttributes
0x180016d39  xor     r8d, r8d; dwShareMode
0x180016d3c  mov     edx, 40000000h; dwDesiredAccess
0x180016d41  mov     rcx, [rcx+8]; lpFileName
0x180016d45  call    cs:__imp_CreateFileW
0x180016d4b  mov     rdx, rax
0x180016d4e  lea     rcx, [rsp+68h+hFile]
0x180016d53  call    ?TakeOwnership@?$AutoHandleBase@V?$AutoHandleDefaultTraits@PEAX@Rtl@Windows@@VAutoFileHandle@23@@Rtl@Windows@@QEAAXPEAX@Z; Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoFileHandle>::TakeOwnership(void *)
0x180016d58  mov     rdi, [rsp+68h+hFile]
0x180016d5d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180016d61  jnz     short loc_180016DA8
0x180016d63  call    cs:__imp_GetLastError
0x180016d69  mov     ebx, eax
0x180016d6b  cmp     eax, 5
0x180016d6e  jnz     short loc_180016D8C
0x180016d70  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180016d77  jnz     loc_180016E5F
0x180016d7d  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 6; _ReAgentErrorCodes ReAgentError
0x180016d87  jmp     loc_180016E5F
0x180016d8c  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180016d93  jnz     loc_180016E5F
0x180016d99  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 5; _ReAgentErrorCodes ReAgentError
0x180016da3  jmp     loc_180016E5F
0x180016da8  mov     rcx, rdi; hFile
0x180016dab  call    cs:__imp_SetEndOfFile
0x180016db1  test    eax, eax
0x180016db3  jnz     short loc_180016DEE
0x180016db5  call    cs:__imp_GetLastError
0x180016dbb  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 34Dh
0x180016dc3  lea     r8, aFailedToSetEnd; "failed to set end of file"
0x180016dca  mov     ebx, eax
0x180016dcc  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180016dd3  mov     r9d, ebx
0x180016dd6  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x180016ddb  lea     rdx, aReagentxmlpars_8; "ReAgentXMLParser::WriteXMLFile %s (0x%x"...
0x180016de2  mov     ecx, 2
0x180016de7  call    UnattendLogW
0x180016dec  jmp     short loc_180016E5F
0x180016dee  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x180016df7  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016dfc  mov     r8d, [rbx]; nNumberOfBytesToWrite
0x180016dff  mov     rdx, [rbx+10h]; lpBuffer
0x180016e03  mov     rcx, rdi; hFile
0x180016e06  call    cs:__imp_WriteFile
0x180016e0c  test    eax, eax
0x180016e0e  jnz     short loc_180016E27
0x180016e10  call    cs:__imp_GetLastError
0x180016e16  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 351h
0x180016e1e  lea     r8, aFailedToWriteF; "failed to write file"
0x180016e25  jmp     short loc_180016DCA
0x180016e27  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x180016e2b  cmp     rax, [rbx]
0x180016e2e  jz      short loc_180016E37
0x180016e30  mov     ebx, 0Dh
0x180016e35  jmp     short loc_180016E5F
0x180016e37  xor     ebx, ebx
0x180016e39  mov     rcx, rdi; hFile
0x180016e3c  call    cs:__imp_FlushFileBuffers
0x180016e42  test    eax, eax
0x180016e44  jnz     short loc_180016E5F
0x180016e46  call    cs:__imp_GetLastError
0x180016e4c  mov     r8d, eax
0x180016e4f  lea     rdx, aFlushFileBuffe; "Flush file buffers failed: 0x%x"
0x180016e56  lea     ecx, [rbx+2]
0x180016e59  call    UnattendLogW
0x180016e5e  nop
0x180016e5f  lea     rax, [rdi-1]
0x180016e63  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016e67  ja      short loc_180016E72
0x180016e69  mov     rcx, rdi; Handle
0x180016e6c  call    cs:__imp_NtClose
0x180016e72  mov     eax, ebx
0x180016e74  mov     rcx, [rsp+68h+var_10]
0x180016e79  xor     rcx, rsp; StackCookie
0x180016e7c  call    __security_check_cookie
0x180016e81  mov     rbx, [rsp+68h+arg_10]
0x180016e89  add     rsp, 60h
0x180016e8d  pop     rdi
0x180016e8e  retn
```
