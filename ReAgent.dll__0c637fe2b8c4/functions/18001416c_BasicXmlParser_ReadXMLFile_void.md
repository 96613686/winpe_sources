# BasicXmlParser::ReadXMLFile(void)

- ea: `0x18001416c`
- end: `0x1800143a7`
- name: `?ReadXMLFile@BasicXmlParser@@IEAAKXZ`
- size: `571`
- prototype: `unsigned int __fastcall(BasicXmlParser *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180012880`

## callees

- `0x1800059fc`
- `0x18001416c`
- `0x180014730`
- `0x18005cf30`

## import_xrefs

- `ntdll!NtClose` at `0x180014380`
- `ntdll!NtClose` at `0x180014380`
- `KERNEL32!GetLastError` at `0x1800141f0`
- `KERNEL32!GetLastError` at `0x18001428c`
- `KERNEL32!GetLastError` at `0x18001430d`
- `KERNEL32!GetLastError` at `0x1800141f0`
- `KERNEL32!GetLastError` at `0x18001428c`
- `KERNEL32!GetLastError` at `0x18001430d`
- `KERNEL32!HeapAlloc` at `0x1800142aa`
- `KERNEL32!HeapAlloc` at `0x1800142aa`
- `KERNEL32!GetProcessHeap` at `0x180014299`
- `KERNEL32!GetProcessHeap` at `0x180014299`
- `KERNEL32!ReadFile` at `0x180014303`
- `KERNEL32!ReadFile` at `0x180014303`
- `KERNEL32!GetFileSize` at `0x18001427c`
- `KERNEL32!GetFileSize` at `0x18001427c`
- `KERNEL32!CreateFileW` at `0x1800141ce`
- `KERNEL32!CreateFileW` at `0x1800141ce`

## string_xrefs

- `0x1800142c4`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x18001431d`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x18001432c`: `failed to read file`
- `0x180014361`: `read xml file (%s) failed: 0x%x`
- `0x1800142da`: `BasicXmlParser::ReadXMLFile %s (0x%x) in file %S line %d`
- `0x180014333`: `BasicXmlParser::ReadXMLFile %s (0x%x) in file %S line %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BasicXmlParser::ReadXMLFile(BasicXmlParser *this)
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
      LODWORD(dwFlagsAndAttributes) = 2499;
      UnattendLogW(
        2,
        L"BasicXmlParser::ReadXMLFile %s (0x%x) in file %S line %d",
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
    LODWORD(dwFlagsAndAttributes) = 2496;
    UnattendLogW(
      2,
      L"BasicXmlParser::ReadXMLFile %s (0x%x) in file %S line %d",
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
0x18001416c  mov     r11, rsp
0x18001416f  push    rsi
0x180014170  sub     rsp, 60h
0x180014174  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFEh
0x18001417c  mov     [r11+10h], rbx
0x180014180  mov     [r11+18h], rbp
0x180014184  mov     rax, cs:__security_cookie
0x18001418b  xor     rax, rsp
0x18001418e  mov     [rsp+68h+var_10], rax
0x180014193  mov     rsi, rcx
0x180014196  mov     qword ptr [r11-28h], 0
0x18001419e  mov     [rsp+68h+NumberOfBytesRead], 0
0x1800141a6  mov     qword ptr [r11-38h], 0
0x1800141ae  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800141b6  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800141be  xor     r9d, r9d; lpSecurityAttributes
0x1800141c1  mov     edx, 80000000h; dwDesiredAccess
0x1800141c6  lea     r8d, [r9+1]; dwShareMode
0x1800141ca  mov     rcx, [rcx+8]; lpFileName
0x1800141ce  call    cs:__imp_CreateFileW
0x1800141d4  mov     rdx, rax
0x1800141d7  lea     rcx, [rsp+68h+hFile]
0x1800141dc  call    ?TakeOwnership@?$AutoHandleBase@V?$AutoHandleDefaultTraits@PEAX@Rtl@Windows@@VAutoFileHandle@23@@Rtl@Windows@@QEAAXPEAX@Z; Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoFileHandle>::TakeOwnership(void *)
0x1800141e1  mov     rbp, [rsp+68h+hFile]
0x1800141e6  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800141ea  jnz     loc_180014277
0x1800141f0  call    cs:__imp_GetLastError
0x1800141f6  mov     ebx, eax
0x1800141f8  cmp     eax, 5
0x1800141fb  jnz     short loc_180014219
0x1800141fd  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180014204  jnz     loc_18001435A
0x18001420a  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 3; _ReAgentErrorCodes ReAgentError
0x180014214  jmp     loc_18001435A
0x180014219  cmp     eax, 2
0x18001421c  jnz     short loc_18001423A
0x18001421e  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180014225  jnz     loc_18001435A
0x18001422b  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 1; _ReAgentErrorCodes ReAgentError
0x180014235  jmp     loc_18001435A
0x18001423a  cmp     eax, 3
0x18001423d  jnz     short loc_18001425B
0x18001423f  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180014246  jnz     loc_18001435A
0x18001424c  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 8; _ReAgentErrorCodes ReAgentError
0x180014256  jmp     loc_18001435A
0x18001425b  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180014262  jnz     loc_180014344
0x180014268  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 2; _ReAgentErrorCodes ReAgentError
0x180014272  jmp     loc_180014344
0x180014277  xor     edx, edx; lpFileSizeHigh
0x180014279  mov     rcx, rbp; hFile
0x18001427c  call    cs:__imp_GetFileSize
0x180014282  mov     ebx, eax
0x180014284  mov     [rsi+18h], ebx
0x180014287  cmp     eax, 0FFFFFFFFh
0x18001428a  jnz     short loc_180014299
0x18001428c  call    cs:__imp_GetLastError
0x180014292  mov     ebx, eax
0x180014294  jmp     loc_180014344
0x180014299  call    cs:__imp_GetProcessHeap
0x18001429f  mov     r8, rbx; dwBytes
0x1800142a2  mov     edx, 8; dwFlags
0x1800142a7  mov     rcx, rax; hHeap
0x1800142aa  call    cs:__imp_HeapAlloc
0x1800142b0  mov     [rsi+10h], rax
0x1800142b4  test    rax, rax
0x1800142b7  jnz     short loc_1800142EB
0x1800142b9  lea     ebx, [rax+8]
0x1800142bc  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 9C0h
0x1800142c4  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x1800142cb  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1800142d0  mov     r9d, ebx
0x1800142d3  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x1800142da  lea     rdx, aBasicxmlparser_9; "BasicXmlParser::ReadXMLFile %s (0x%x) i"...
0x1800142e1  lea     ecx, [rbx-6]
0x1800142e4  call    UnattendLogW
0x1800142e9  jmp     short loc_18001435A
0x1800142eb  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x1800142f4  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800142f9  mov     r8d, [rsi+18h]; nNumberOfBytesToRead
0x1800142fd  mov     rdx, rax; lpBuffer
0x180014300  mov     rcx, rbp; hFile
0x180014303  call    cs:__imp_ReadFile
0x180014309  test    eax, eax
0x18001430b  jnz     short loc_18001434A
0x18001430d  call    cs:__imp_GetLastError
0x180014313  mov     ebx, eax
0x180014315  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 9C3h
0x18001431d  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180014324  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x180014329  mov     r9d, ebx
0x18001432c  lea     r8, aFailedToReadFi; "failed to read file"
0x180014333  lea     rdx, aBasicxmlparser_9; "BasicXmlParser::ReadXMLFile %s (0x%x) i"...
0x18001433a  mov     ecx, 2
0x18001433f  call    UnattendLogW
0x180014344  test    ebx, ebx
0x180014346  jz      short loc_180014373
0x180014348  jmp     short loc_18001435A
0x18001434a  xor     ebx, ebx
0x18001434c  mov     eax, [rsi+18h]
0x18001434f  cmp     [rsp+68h+NumberOfBytesRead], eax
0x180014353  jz      short loc_180014373
0x180014355  mov     ebx, 0Dh
0x18001435a  mov     r9d, ebx
0x18001435d  mov     r8, [rsi+8]
0x180014361  lea     rdx, aReadXmlFileSFa; "read xml file (%s) failed: 0x%x"
0x180014368  mov     ecx, 2
0x18001436d  call    UnattendLogW
0x180014372  nop
0x180014373  lea     rax, [rbp-1]
0x180014377  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001437b  ja      short loc_180014386
0x18001437d  mov     rcx, rbp; Handle
0x180014380  call    cs:__imp_NtClose
0x180014386  mov     eax, ebx
0x180014388  mov     rcx, [rsp+68h+var_10]
0x18001438d  xor     rcx, rsp; StackCookie
0x180014390  call    __security_check_cookie
0x180014395  lea     r11, [rsp+68h+var_8]
0x18001439a  mov     rbx, [r11+18h]
0x18001439e  mov     rbp, [r11+20h]
0x1800143a2  mov     rsp, r11
0x1800143a5  pop     rsi
0x1800143a6  retn
```
