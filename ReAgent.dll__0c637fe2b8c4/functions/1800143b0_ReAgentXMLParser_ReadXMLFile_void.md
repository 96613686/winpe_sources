# ReAgentXMLParser::ReadXMLFile(void)

- ea: `0x1800143b0`
- end: `0x1800145eb`
- name: `?ReadXMLFile@ReAgentXMLParser@@IEAAKXZ`
- size: `571`
- prototype: `unsigned int __fastcall(ReAgentXMLParser *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180012b90`

## callees

- `0x1800059fc`
- `0x1800143b0`
- `0x180014730`
- `0x18005cf30`

## import_xrefs

- `ntdll!NtClose` at `0x1800145c4`
- `ntdll!NtClose` at `0x1800145c4`
- `KERNEL32!GetLastError` at `0x180014434`
- `KERNEL32!GetLastError` at `0x1800144d0`
- `KERNEL32!GetLastError` at `0x180014551`
- `KERNEL32!GetLastError` at `0x180014434`
- `KERNEL32!GetLastError` at `0x1800144d0`
- `KERNEL32!GetLastError` at `0x180014551`
- `KERNEL32!HeapAlloc` at `0x1800144ee`
- `KERNEL32!HeapAlloc` at `0x1800144ee`
- `KERNEL32!GetProcessHeap` at `0x1800144dd`
- `KERNEL32!GetProcessHeap` at `0x1800144dd`
- `KERNEL32!ReadFile` at `0x180014547`
- `KERNEL32!ReadFile` at `0x180014547`
- `KERNEL32!GetFileSize` at `0x1800144c0`
- `KERNEL32!GetFileSize` at `0x1800144c0`
- `KERNEL32!CreateFileW` at `0x180014412`
- `KERNEL32!CreateFileW` at `0x180014412`

## string_xrefs

- `0x180014508`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180014561`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x18001451e`: `ReAgentXMLParser::ReadXMLFile %s (0x%x) in file %S line %d`
- `0x180014577`: `ReAgentXMLParser::ReadXMLFile %s (0x%x) in file %S line %d`
- `0x180014570`: `failed to read file`
- `0x1800145a5`: `read xml file (%s) failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReAgentXMLParser::ReadXMLFile(ReAgentXMLParser *this)
{
  HANDLE FileW; // rax
  char *v3; // rbp
  DWORD LastError; // eax
  __int64 v5; // rbx
  DWORD FileSize; // eax
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-40h]
  HANDLE hFile[2]; // [rsp+40h] [rbp-28h] BYREF
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-18h] BYREF

  hFile[1] = (HANDLE)-2LL;
  hFile[0] = 0;
  NumberOfBytesRead = 0;
  FileW = CreateFileW(*((LPCWSTR *)this + 1), 0x80000000, 1u, 0, 3u, 0x80u, 0);
  Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoFileHandle>::TakeOwnership(
    hFile,
    FileW);
  v3 = (char *)hFile[0];
  if ( hFile[0] == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    LODWORD(v5) = LastError;
    switch ( LastError )
    {
      case 5u:
        if ( !ReAgentError )
          ReAgentError = 3;
        goto LABEL_23;
      case 2u:
        if ( !ReAgentError )
          ReAgentError = 1;
        goto LABEL_23;
      case 3u:
        if ( !ReAgentError )
          ReAgentError = 8;
        goto LABEL_23;
    }
    if ( !ReAgentError )
      ReAgentError = 2;
LABEL_19:
    if ( !(_DWORD)v5 )
      goto LABEL_24;
    goto LABEL_23;
  }
  FileSize = GetFileSize(hFile[0], 0);
  v7 = FileSize;
  *((_DWORD *)this + 6) = FileSize;
  if ( FileSize == -1 )
  {
    LODWORD(v5) = GetLastError();
    goto LABEL_19;
  }
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, v7);
  *((_QWORD *)this + 2) = v9;
  if ( v9 )
  {
    if ( !ReadFile(v3, v9, *((_DWORD *)this + 6), &NumberOfBytesRead, 0) )
    {
      v5 = GetLastError();
      LODWORD(dwFlagsAndAttributes) = 788;
      UnattendLogW(
        2,
        L"ReAgentXMLParser::ReadXMLFile %s (0x%x) in file %S line %d",
        L"failed to read file",
        v5,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
        dwFlagsAndAttributes);
      goto LABEL_19;
    }
    LODWORD(v5) = 0;
    if ( NumberOfBytesRead == *((_DWORD *)this + 6) )
      goto LABEL_24;
    LODWORD(v5) = 13;
  }
  else
  {
    LODWORD(v5) = 8;
    LODWORD(dwFlagsAndAttributes) = 785;
    UnattendLogW(
      2,
      L"ReAgentXMLParser::ReadXMLFile %s (0x%x) in file %S line %d",
      L"failed to allocate memory",
      8,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
      dwFlagsAndAttributes);
  }
LABEL_23:
  UnattendLogW(2, L"read xml file (%s) failed: 0x%x", *((_QWORD *)this + 1), (unsigned int)v5);
LABEL_24:
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    NtClose(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800143b0  mov     r11, rsp
0x1800143b3  push    rsi
0x1800143b4  sub     rsp, 60h
0x1800143b8  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFEh
0x1800143c0  mov     [r11+10h], rbx
0x1800143c4  mov     [r11+18h], rbp
0x1800143c8  mov     rax, cs:__security_cookie
0x1800143cf  xor     rax, rsp
0x1800143d2  mov     [rsp+68h+var_10], rax
0x1800143d7  mov     rsi, rcx
0x1800143da  mov     qword ptr [r11-28h], 0
0x1800143e2  mov     [rsp+68h+NumberOfBytesRead], 0
0x1800143ea  mov     qword ptr [r11-38h], 0
0x1800143f2  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800143fa  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180014402  xor     r9d, r9d; lpSecurityAttributes
0x180014405  mov     edx, 80000000h; dwDesiredAccess
0x18001440a  lea     r8d, [r9+1]; dwShareMode
0x18001440e  mov     rcx, [rcx+8]; lpFileName
0x180014412  call    cs:__imp_CreateFileW
0x180014418  mov     rdx, rax
0x18001441b  lea     rcx, [rsp+68h+hFile]
0x180014420  call    ?TakeOwnership@?$AutoHandleBase@V?$AutoHandleDefaultTraits@PEAX@Rtl@Windows@@VAutoFileHandle@23@@Rtl@Windows@@QEAAXPEAX@Z; Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoFileHandle>::TakeOwnership(void *)
0x180014425  mov     rbp, [rsp+68h+hFile]
0x18001442a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18001442e  jnz     loc_1800144BB
0x180014434  call    cs:__imp_GetLastError
0x18001443a  mov     ebx, eax
0x18001443c  cmp     eax, 5
0x18001443f  jnz     short loc_18001445D
0x180014441  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180014448  jnz     loc_18001459E
0x18001444e  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 3; _ReAgentErrorCodes ReAgentError
0x180014458  jmp     loc_18001459E
0x18001445d  cmp     eax, 2
0x180014460  jnz     short loc_18001447E
0x180014462  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180014469  jnz     loc_18001459E
0x18001446f  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 1; _ReAgentErrorCodes ReAgentError
0x180014479  jmp     loc_18001459E
0x18001447e  cmp     eax, 3
0x180014481  jnz     short loc_18001449F
0x180014483  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x18001448a  jnz     loc_18001459E
0x180014490  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 8; _ReAgentErrorCodes ReAgentError
0x18001449a  jmp     loc_18001459E
0x18001449f  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x1800144a6  jnz     loc_180014588
0x1800144ac  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 2; _ReAgentErrorCodes ReAgentError
0x1800144b6  jmp     loc_180014588
0x1800144bb  xor     edx, edx; lpFileSizeHigh
0x1800144bd  mov     rcx, rbp; hFile
0x1800144c0  call    cs:__imp_GetFileSize
0x1800144c6  mov     ebx, eax
0x1800144c8  mov     [rsi+18h], ebx
0x1800144cb  cmp     eax, 0FFFFFFFFh
0x1800144ce  jnz     short loc_1800144DD
0x1800144d0  call    cs:__imp_GetLastError
0x1800144d6  mov     ebx, eax
0x1800144d8  jmp     loc_180014588
0x1800144dd  call    cs:__imp_GetProcessHeap
0x1800144e3  mov     r8, rbx; dwBytes
0x1800144e6  mov     edx, 8; dwFlags
0x1800144eb  mov     rcx, rax; hHeap
0x1800144ee  call    cs:__imp_HeapAlloc
0x1800144f4  mov     [rsi+10h], rax
0x1800144f8  test    rax, rax
0x1800144fb  jnz     short loc_18001452F
0x1800144fd  lea     ebx, [rax+8]
0x180014500  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 311h
0x180014508  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18001450f  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x180014514  mov     r9d, ebx
0x180014517  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x18001451e  lea     rdx, aReagentxmlpars_4; "ReAgentXMLParser::ReadXMLFile %s (0x%x)"...
0x180014525  lea     ecx, [rbx-6]
0x180014528  call    UnattendLogW
0x18001452d  jmp     short loc_18001459E
0x18001452f  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x180014538  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001453d  mov     r8d, [rsi+18h]; nNumberOfBytesToRead
0x180014541  mov     rdx, rax; lpBuffer
0x180014544  mov     rcx, rbp; hFile
0x180014547  call    cs:__imp_ReadFile
0x18001454d  test    eax, eax
0x18001454f  jnz     short loc_18001458E
0x180014551  call    cs:__imp_GetLastError
0x180014557  mov     ebx, eax
0x180014559  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 314h
0x180014561  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180014568  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x18001456d  mov     r9d, ebx
0x180014570  lea     r8, aFailedToReadFi; "failed to read file"
0x180014577  lea     rdx, aReagentxmlpars_4; "ReAgentXMLParser::ReadXMLFile %s (0x%x)"...
0x18001457e  mov     ecx, 2
0x180014583  call    UnattendLogW
0x180014588  test    ebx, ebx
0x18001458a  jz      short loc_1800145B7
0x18001458c  jmp     short loc_18001459E
0x18001458e  xor     ebx, ebx
0x180014590  mov     eax, [rsi+18h]
0x180014593  cmp     [rsp+68h+NumberOfBytesRead], eax
0x180014597  jz      short loc_1800145B7
0x180014599  mov     ebx, 0Dh
0x18001459e  mov     r9d, ebx
0x1800145a1  mov     r8, [rsi+8]
0x1800145a5  lea     rdx, aReadXmlFileSFa; "read xml file (%s) failed: 0x%x"
0x1800145ac  mov     ecx, 2
0x1800145b1  call    UnattendLogW
0x1800145b6  nop
0x1800145b7  lea     rax, [rbp-1]
0x1800145bb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800145bf  ja      short loc_1800145CA
0x1800145c1  mov     rcx, rbp; Handle
0x1800145c4  call    cs:__imp_NtClose
0x1800145ca  mov     eax, ebx
0x1800145cc  mov     rcx, [rsp+68h+var_10]
0x1800145d1  xor     rcx, rsp; StackCookie
0x1800145d4  call    __security_check_cookie
0x1800145d9  lea     r11, [rsp+68h+var_8]
0x1800145de  mov     rbx, [r11+18h]
0x1800145e2  mov     rbp, [r11+20h]
0x1800145e6  mov     rsp, r11
0x1800145e9  pop     rsi
0x1800145ea  retn
```
