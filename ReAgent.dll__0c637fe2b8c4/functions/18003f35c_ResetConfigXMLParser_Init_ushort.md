# ResetConfigXMLParser::Init(ushort *)

- ea: `0x18003f35c`
- end: `0x18003f54b`
- name: `?Init@ResetConfigXMLParser@@QEAAKPEAG@Z`
- size: `495`
- prototype: `__int64 __fastcall(ResetConfigXMLParser *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18003b988`

## callees

- `0x1800059fc`
- `0x180014730`
- `0x18003f35c`
- `0x18005cf30`

## import_xrefs

- `ntdll!NtClose` at `0x18003f524`
- `ntdll!NtClose` at `0x18003f524`
- `KERNEL32!GetLastError` at `0x18003f3f5`
- `KERNEL32!GetLastError` at `0x18003f436`
- `KERNEL32!GetLastError` at `0x18003f4b6`
- `KERNEL32!GetLastError` at `0x18003f3f5`
- `KERNEL32!GetLastError` at `0x18003f436`
- `KERNEL32!GetLastError` at `0x18003f4b6`
- `KERNEL32!HeapAlloc` at `0x18003f457`
- `KERNEL32!HeapAlloc` at `0x18003f457`
- `KERNEL32!GetProcessHeap` at `0x18003f443`
- `KERNEL32!GetProcessHeap` at `0x18003f443`
- `KERNEL32!ReadFile` at `0x18003f4ac`
- `KERNEL32!ReadFile` at `0x18003f4ac`
- `KERNEL32!GetFileSize` at `0x18003f427`
- `KERNEL32!GetFileSize` at `0x18003f427`
- `KERNEL32!CreateFileW` at `0x18003f3d7`
- `KERNEL32!CreateFileW` at `0x18003f3d7`
- `ole32!CoTaskMemFree` at `0x18003f3a2`
- `ole32!CoTaskMemFree` at `0x18003f3a2`

## string_xrefs

- `0x18003f4d5`: `failed to read file`
- `0x18003f46e`: `base\diagnosis\srt\reagent2\reagent\parserex.cpp`
- `0x18003f4c6`: `base\diagnosis\srt\reagent2\reagent\parserex.cpp`
- `0x18003f484`: `ResetConfigXMLParser::Init %s (0x%x) in file %S line %d`
- `0x18003f4dc`: `ResetConfigXMLParser::Init %s (0x%x) in file %S line %d`
- `0x18003f505`: `ResetConfigXMLParser::Init failed: 0x%x`

## pseudocode

```c
__int64 __fastcall ResetConfigXMLParser::Init(ResetConfigXMLParser *this, unsigned __int16 *a2)
{
  void *v4; // rcx
  HANDLE FileW; // rax
  char *v6; // rsi
  __int64 LastError; // rbx
  DWORD FileSize; // eax
  HANDLE ProcessHeap; // rax
  SIZE_T v10; // r8
  void *v11; // rax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-40h]
  HANDLE hFile[2]; // [rsp+40h] [rbp-28h] BYREF
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-18h] BYREF

  hFile[1] = (HANDLE)-2LL;
  hFile[0] = 0;
  NumberOfBytesRead = 0;
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 1) = 0;
  }
  FileW = CreateFileW(a2, 0x80000000, 0, 0, 3u, 0x80u, 0);
  Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoFileHandle>::TakeOwnership(
    hFile,
    FileW);
  v6 = (char *)hFile[0];
  if ( hFile[0] == (HANDLE)-1LL )
  {
    LODWORD(LastError) = GetLastError();
    if ( (_DWORD)LastError == 2 )
    {
      if ( !ReAgentError )
        ReAgentError = 24;
      goto LABEL_17;
    }
LABEL_13:
    if ( !(_DWORD)LastError )
      goto LABEL_18;
    goto LABEL_17;
  }
  FileSize = GetFileSize(hFile[0], 0);
  LastError = FileSize;
  *(_DWORD *)this = FileSize;
  if ( FileSize == -1 )
  {
    LODWORD(LastError) = GetLastError();
    goto LABEL_13;
  }
  ProcessHeap = GetProcessHeap();
  v10 = LastError + 2;
  LODWORD(LastError) = 8;
  v11 = HeapAlloc(ProcessHeap, 8u, v10);
  *((_QWORD *)this + 1) = v11;
  if ( v11 )
  {
    if ( !ReadFile(v6, v11, *(_DWORD *)this, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      LODWORD(dwFlagsAndAttributes) = 676;
      UnattendLogW(
        2,
        L"ResetConfigXMLParser::Init %s (0x%x) in file %S line %d",
        L"failed to read file",
        LastError,
        "base\\diagnosis\\srt\\reagent2\\reagent\\parserex.cpp",
        dwFlagsAndAttributes);
      goto LABEL_13;
    }
    LODWORD(LastError) = 0;
    if ( NumberOfBytesRead == *(_DWORD *)this )
      goto LABEL_18;
    LODWORD(LastError) = 13;
  }
  else
  {
    LODWORD(dwFlagsAndAttributes) = 673;
    UnattendLogW(
      2,
      L"ResetConfigXMLParser::Init %s (0x%x) in file %S line %d",
      L"failed to allocate memory",
      8,
      "base\\diagnosis\\srt\\reagent2\\reagent\\parserex.cpp",
      dwFlagsAndAttributes);
  }
LABEL_17:
  UnattendLogW(1, L"ResetConfigXMLParser::Init failed: 0x%x", (unsigned int)LastError);
LABEL_18:
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    NtClose(v6);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18003f35c  mov     r11, rsp
0x18003f35f  push    rdi
0x18003f360  sub     rsp, 60h
0x18003f364  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFEh
0x18003f36c  mov     [r11+18h], rbx
0x18003f370  mov     [r11+20h], rsi
0x18003f374  mov     rax, cs:__security_cookie
0x18003f37b  xor     rax, rsp
0x18003f37e  mov     [rsp+68h+var_10], rax
0x18003f383  mov     rbx, rdx
0x18003f386  mov     rdi, rcx
0x18003f389  mov     qword ptr [r11-28h], 0
0x18003f391  mov     [rsp+68h+NumberOfBytesRead], 0
0x18003f399  mov     rcx, [rcx+8]; pv
0x18003f39d  test    rcx, rcx
0x18003f3a0  jz      short loc_18003F3B0
0x18003f3a2  call    cs:__imp_CoTaskMemFree
0x18003f3a8  mov     qword ptr [rdi+8], 0
0x18003f3b0  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18003f3b9  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003f3c1  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18003f3c9  xor     r9d, r9d; lpSecurityAttributes
0x18003f3cc  xor     r8d, r8d; dwShareMode
0x18003f3cf  mov     edx, 80000000h; dwDesiredAccess
0x18003f3d4  mov     rcx, rbx; lpFileName
0x18003f3d7  call    cs:__imp_CreateFileW
0x18003f3dd  mov     rdx, rax
0x18003f3e0  lea     rcx, [rsp+68h+hFile]
0x18003f3e5  call    ?TakeOwnership@?$AutoHandleBase@V?$AutoHandleDefaultTraits@PEAX@Rtl@Windows@@VAutoFileHandle@23@@Rtl@Windows@@QEAAXPEAX@Z; Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoFileHandle>::TakeOwnership(void *)
0x18003f3ea  mov     rsi, [rsp+68h+hFile]
0x18003f3ef  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18003f3f3  jnz     short loc_18003F422
0x18003f3f5  call    cs:__imp_GetLastError
0x18003f3fb  mov     ebx, eax
0x18003f3fd  cmp     eax, 2
0x18003f400  jnz     loc_18003F4ED
0x18003f406  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x18003f40d  jnz     loc_18003F502
0x18003f413  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 18h; _ReAgentErrorCodes ReAgentError
0x18003f41d  jmp     loc_18003F502
0x18003f422  xor     edx, edx; lpFileSizeHigh
0x18003f424  mov     rcx, rsi; hFile
0x18003f427  call    cs:__imp_GetFileSize
0x18003f42d  mov     ebx, eax
0x18003f42f  mov     [rdi], ebx
0x18003f431  cmp     eax, 0FFFFFFFFh
0x18003f434  jnz     short loc_18003F443
0x18003f436  call    cs:__imp_GetLastError
0x18003f43c  mov     ebx, eax
0x18003f43e  jmp     loc_18003F4ED
0x18003f443  call    cs:__imp_GetProcessHeap
0x18003f449  lea     r8, [rbx+2]; dwBytes
0x18003f44d  mov     ebx, 8
0x18003f452  mov     edx, ebx; dwFlags
0x18003f454  mov     rcx, rax; hHeap
0x18003f457  call    cs:__imp_HeapAlloc
0x18003f45d  mov     [rdi+8], rax
0x18003f461  test    rax, rax
0x18003f464  jnz     short loc_18003F495
0x18003f466  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 2A1h
0x18003f46e  lea     rax, aBaseDiagnosisS; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003f475  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x18003f47a  mov     r9d, ebx
0x18003f47d  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x18003f484  lea     rdx, aResetconfigxml; "ResetConfigXMLParser::Init %s (0x%x) in"...
0x18003f48b  lea     ecx, [rbx-6]
0x18003f48e  call    UnattendLogW
0x18003f493  jmp     short loc_18003F502
0x18003f495  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x18003f49e  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003f4a3  mov     r8d, [rdi]; nNumberOfBytesToRead
0x18003f4a6  mov     rdx, rax; lpBuffer
0x18003f4a9  mov     rcx, rsi; hFile
0x18003f4ac  call    cs:__imp_ReadFile
0x18003f4b2  test    eax, eax
0x18003f4b4  jnz     short loc_18003F4F3
0x18003f4b6  call    cs:__imp_GetLastError
0x18003f4bc  mov     ebx, eax
0x18003f4be  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 2A4h
0x18003f4c6  lea     rax, aBaseDiagnosisS; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003f4cd  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x18003f4d2  mov     r9d, ebx
0x18003f4d5  lea     r8, aFailedToReadFi; "failed to read file"
0x18003f4dc  lea     rdx, aResetconfigxml; "ResetConfigXMLParser::Init %s (0x%x) in"...
0x18003f4e3  mov     ecx, 2
0x18003f4e8  call    UnattendLogW
0x18003f4ed  test    ebx, ebx
0x18003f4ef  jz      short loc_18003F517
0x18003f4f1  jmp     short loc_18003F502
0x18003f4f3  xor     ebx, ebx
0x18003f4f5  mov     eax, [rdi]
0x18003f4f7  cmp     [rsp+68h+NumberOfBytesRead], eax
0x18003f4fb  jz      short loc_18003F517
0x18003f4fd  mov     ebx, 0Dh
0x18003f502  mov     r8d, ebx
0x18003f505  lea     rdx, aResetconfigxml_0; "ResetConfigXMLParser::Init failed: 0x%x"
0x18003f50c  mov     ecx, 1
0x18003f511  call    UnattendLogW
0x18003f516  nop
0x18003f517  lea     rax, [rsi-1]
0x18003f51b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f51f  ja      short loc_18003F52A
0x18003f521  mov     rcx, rsi; Handle
0x18003f524  call    cs:__imp_NtClose
0x18003f52a  mov     eax, ebx
0x18003f52c  mov     rcx, [rsp+68h+var_10]
0x18003f531  xor     rcx, rsp; StackCookie
0x18003f534  call    __security_check_cookie
0x18003f539  lea     r11, [rsp+68h+var_8]
0x18003f53e  mov     rbx, [r11+20h]
0x18003f542  mov     rsi, [r11+28h]
0x18003f546  mov     rsp, r11
0x18003f549  pop     rdi
0x18003f54a  retn
```
