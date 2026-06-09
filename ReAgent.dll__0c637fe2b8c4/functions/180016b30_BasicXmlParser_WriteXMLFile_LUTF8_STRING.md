# BasicXmlParser::WriteXMLFile(_LUTF8_STRING *)

- ea: `0x180016b30`
- end: `0x180016ce0`
- name: `?WriteXMLFile@BasicXmlParser@@IEAAKPEAU_LUTF8_STRING@@@Z`
- size: `432`
- prototype: `unsigned int __fastcall(BasicXmlParser *__hidden this, struct _LUTF8_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180015800`

## callees

- `0x1800059fc`
- `0x180014730`
- `0x180016b30`
- `0x18005cf30`

## import_xrefs

- `ntdll!NtClose` at `0x180016cbd`
- `ntdll!NtClose` at `0x180016cbd`
- `KERNEL32!GetLastError` at `0x180016bb4`
- `KERNEL32!GetLastError` at `0x180016c06`
- `KERNEL32!GetLastError` at `0x180016c61`
- `KERNEL32!GetLastError` at `0x180016c97`
- `KERNEL32!GetLastError` at `0x180016bb4`
- `KERNEL32!GetLastError` at `0x180016c06`
- `KERNEL32!GetLastError` at `0x180016c61`
- `KERNEL32!GetLastError` at `0x180016c97`
- `KERNEL32!WriteFile` at `0x180016c57`
- `KERNEL32!WriteFile` at `0x180016c57`
- `KERNEL32!SetEndOfFile` at `0x180016bfc`
- `KERNEL32!SetEndOfFile` at `0x180016bfc`
- `KERNEL32!CreateFileW` at `0x180016b96`
- `KERNEL32!CreateFileW` at `0x180016b96`
- `KERNEL32!FlushFileBuffers` at `0x180016c8d`
- `KERNEL32!FlushFileBuffers` at `0x180016c8d`

## string_xrefs

- `0x180016c1d`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180016c6f`: `failed to write file`
- `0x180016c2c`: `BasicXmlParser::WriteXMLFile %s (0x%x) in file %S line %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BasicXmlParser::WriteXMLFile(BasicXmlParser *this, LPCVOID *a2)
{
  char *v3; // rdi
  const WCHAR *v4; // rcx
  DWORD LastError; // ebx
  HANDLE FileW; // rax
  DWORD v7; // eax
  const wchar_t *v8; // r8
  DWORD v9; // eax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-40h]
  HANDLE hFile[2]; // [rsp+40h] [rbp-28h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-18h] BYREF

  hFile[1] = (HANDLE)-2LL;
  v3 = 0;
  hFile[0] = 0;
  NumberOfBytesWritten = 0;
  v4 = (const WCHAR *)*((_QWORD *)this + 1);
  if ( !v4 )
  {
    LastError = 50;
    goto LABEL_18;
  }
  FileW = CreateFileW(v4, 0x40000000u, 0, 0, 4u, 0x80u, 0);
  Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoFileHandle>::TakeOwnership(
    hFile,
    FileW);
  v3 = (char *)hFile[0];
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
    goto LABEL_18;
  }
  if ( !SetEndOfFile(hFile[0]) )
  {
    v7 = GetLastError();
    LODWORD(dwFlagsAndAttributes) = 2561;
    v8 = L"failed to set end of file";
LABEL_11:
    LastError = v7;
    UnattendLogW(
      2,
      L"BasicXmlParser::WriteXMLFile %s (0x%x) in file %S line %d",
      v8,
      v7,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
      dwFlagsAndAttributes);
    goto LABEL_18;
  }
  if ( !WriteFile(v3, a2[2], *(_DWORD *)a2, &NumberOfBytesWritten, 0) )
  {
    v7 = GetLastError();
    LODWORD(dwFlagsAndAttributes) = 2565;
    v8 = L"failed to write file";
    goto LABEL_11;
  }
  if ( (LPCVOID)NumberOfBytesWritten == *a2 )
  {
    LastError = 0;
    if ( !FlushFileBuffers(v3) )
    {
      v9 = GetLastError();
      UnattendLogW(2, L"Flush file buffers failed: 0x%x", v9);
    }
  }
  else
  {
    LastError = 13;
  }
LABEL_18:
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    NtClose(v3);
  return LastError;
}

```

## disassembly

```asm
0x180016b30  mov     rax, rsp
0x180016b33  push    rdi
0x180016b34  sub     rsp, 60h
0x180016b38  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x180016b40  mov     [rax+18h], rbx
0x180016b44  mov     rax, cs:__security_cookie
0x180016b4b  xor     rax, rsp
0x180016b4e  mov     [rsp+68h+var_10], rax
0x180016b53  mov     rbx, rdx
0x180016b56  xor     edi, edi
0x180016b58  mov     [rsp+68h+hFile], rdi
0x180016b5d  mov     [rsp+68h+NumberOfBytesWritten], edi
0x180016b61  mov     rcx, [rcx+8]; lpFileName
0x180016b65  test    rcx, rcx
0x180016b68  jnz     short loc_180016B72
0x180016b6a  lea     ebx, [rdi+32h]
0x180016b6d  jmp     loc_180016CB0
0x180016b72  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180016b7b  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180016b83  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x180016b8b  xor     r9d, r9d; lpSecurityAttributes
0x180016b8e  xor     r8d, r8d; dwShareMode
0x180016b91  mov     edx, 40000000h; dwDesiredAccess
0x180016b96  call    cs:__imp_CreateFileW
0x180016b9c  mov     rdx, rax
0x180016b9f  lea     rcx, [rsp+68h+hFile]
0x180016ba4  call    ?TakeOwnership@?$AutoHandleBase@V?$AutoHandleDefaultTraits@PEAX@Rtl@Windows@@VAutoFileHandle@23@@Rtl@Windows@@QEAAXPEAX@Z; Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoFileHandle>::TakeOwnership(void *)
0x180016ba9  mov     rdi, [rsp+68h+hFile]
0x180016bae  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180016bb2  jnz     short loc_180016BF9
0x180016bb4  call    cs:__imp_GetLastError
0x180016bba  mov     ebx, eax
0x180016bbc  cmp     eax, 5
0x180016bbf  jnz     short loc_180016BDD
0x180016bc1  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180016bc8  jnz     loc_180016CB0
0x180016bce  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 6; _ReAgentErrorCodes ReAgentError
0x180016bd8  jmp     loc_180016CB0
0x180016bdd  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180016be4  jnz     loc_180016CB0
0x180016bea  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 5; _ReAgentErrorCodes ReAgentError
0x180016bf4  jmp     loc_180016CB0
0x180016bf9  mov     rcx, rdi; hFile
0x180016bfc  call    cs:__imp_SetEndOfFile
0x180016c02  test    eax, eax
0x180016c04  jnz     short loc_180016C3F
0x180016c06  call    cs:__imp_GetLastError
0x180016c0c  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 0A01h
0x180016c14  lea     r8, aFailedToSetEnd; "failed to set end of file"
0x180016c1b  mov     ebx, eax
0x180016c1d  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180016c24  mov     r9d, ebx
0x180016c27  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x180016c2c  lea     rdx, aBasicxmlparser_6; "BasicXmlParser::WriteXMLFile %s (0x%x) "...
0x180016c33  mov     ecx, 2
0x180016c38  call    UnattendLogW
0x180016c3d  jmp     short loc_180016CB0
0x180016c3f  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x180016c48  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016c4d  mov     r8d, [rbx]; nNumberOfBytesToWrite
0x180016c50  mov     rdx, [rbx+10h]; lpBuffer
0x180016c54  mov     rcx, rdi; hFile
0x180016c57  call    cs:__imp_WriteFile
0x180016c5d  test    eax, eax
0x180016c5f  jnz     short loc_180016C78
0x180016c61  call    cs:__imp_GetLastError
0x180016c67  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 0A05h
0x180016c6f  lea     r8, aFailedToWriteF; "failed to write file"
0x180016c76  jmp     short loc_180016C1B
0x180016c78  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x180016c7c  cmp     rax, [rbx]
0x180016c7f  jz      short loc_180016C88
0x180016c81  mov     ebx, 0Dh
0x180016c86  jmp     short loc_180016CB0
0x180016c88  xor     ebx, ebx
0x180016c8a  mov     rcx, rdi; hFile
0x180016c8d  call    cs:__imp_FlushFileBuffers
0x180016c93  test    eax, eax
0x180016c95  jnz     short loc_180016CB0
0x180016c97  call    cs:__imp_GetLastError
0x180016c9d  mov     r8d, eax
0x180016ca0  lea     rdx, aFlushFileBuffe; "Flush file buffers failed: 0x%x"
0x180016ca7  lea     ecx, [rbx+2]
0x180016caa  call    UnattendLogW
0x180016caf  nop
0x180016cb0  lea     rax, [rdi-1]
0x180016cb4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016cb8  ja      short loc_180016CC3
0x180016cba  mov     rcx, rdi; Handle
0x180016cbd  call    cs:__imp_NtClose
0x180016cc3  mov     eax, ebx
0x180016cc5  mov     rcx, [rsp+68h+var_10]
0x180016cca  xor     rcx, rsp; StackCookie
0x180016ccd  call    __security_check_cookie
0x180016cd2  mov     rbx, [rsp+68h+arg_10]
0x180016cda  add     rsp, 60h
0x180016cde  pop     rdi
0x180016cdf  retn
```
