# LogBootTime(void)

- ea: `0x140007b40`
- end: `0x140007c92`
- name: `?LogBootTime@@YAXXZ`
- size: `338`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140009650`

## callees

- `0x1400023e0`
- `0x140007b40`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bff`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x140007bbe`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x140007bbe`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x140007bf5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x140007bf5`
- `ntdll!NtQuerySystemInformation` at `0x140007b8a`
- `ntdll!NtQuerySystemInformation` at `0x140007b8a`

## string_xrefs

- `0x140007b98`: `Failed attempting to get the system boot time`

## pseudocode

```c
void LogBootTime(void)
{
  NTSTATUS v0; // eax
  int LastError; // eax
  const char *v2; // r9
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp+7h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+70h] [rbp+17h] BYREF
  int SystemInformation; // [rsp+78h] [rbp+1Fh] BYREF
  __int128 v6; // [rsp+7Ch] [rbp+23h]
  _BYTE v7[28]; // [rsp+8Ch] [rbp+33h] BYREF

  SystemInformation = 0;
  memset(v7, 0, sizeof(v7));
  LocalFileTime = 0;
  v6 = 0;
  SystemTime = 0;
  v0 = NtQuerySystemInformation(SystemTimeOfDayInformation, &SystemInformation, 0x30u, 0);
  if ( v0 < 0 )
  {
    LastError = v0 | 0x10000000;
    v2 = "Failed attempting to get the system boot time";
LABEL_3:
    CBSWdsLogLight(0x4000000u, (unsigned int)LastError, (size_t *)1, v2);
    return;
  }
  if ( !FileTimeToLocalFileTime((const FILETIME *)&SystemInformation, &LocalFileTime) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v2 = "Failed converting filetime to local file time";
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_3;
  }
  if ( !FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v2 = "Failed converting local filetime to system time";
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_3;
  }
  CBSWdsLogLight(
    0x4000000u,
    0,
    0,
    "TI: Last boot time: %04d-%02d-%02d %02d:%02d:%02d.%03d",
    SystemTime.wYear,
    SystemTime.wMonth,
    SystemTime.wDay,
    SystemTime.wHour,
    SystemTime.wMinute,
    SystemTime.wSecond,
    SystemTime.wMilliseconds);
}

```

## disassembly

```asm
0x140007b40  push    rbp
0x140007b42  lea     rbp, [rsp-57h]
0x140007b47  sub     rsp, 0B0h
0x140007b4e  mov     rax, cs:__security_cookie
0x140007b55  xor     rax, rsp
0x140007b58  mov     [rbp+57h+var_8], rax
0x140007b5c  xorps   xmm0, xmm0
0x140007b5f  mov     [rbp+57h+SystemInformation], 0
0x140007b66  xor     eax, eax
0x140007b68  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x140007b6c  movups  xmmword ptr [rbp+57h+var_24], xmm0
0x140007b70  xor     r9d, r9d; ReturnLength
0x140007b73  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], rax
0x140007b77  movups  [rbp+57h+var_34], xmm0
0x140007b7b  lea     r8d, [rax+30h]; SystemInformationLength
0x140007b7f  lea     ecx, [rax+3]; SystemInformationClass
0x140007b82  movups  xmmword ptr [rbp+57h+var_24+0Ch], xmm0
0x140007b86  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x140007b8a  call    cs:__imp_NtQuerySystemInformation
0x140007b90  test    eax, eax
0x140007b92  jns     short loc_140007BB6
0x140007b94  bts     eax, 1Ch
0x140007b98  lea     r9, aFailedAttempti; "Failed attempting to get the system boo"...
0x140007b9f  mov     r8d, 1
0x140007ba5  mov     edx, eax
0x140007ba7  mov     ecx, 4000000h
0x140007bac  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007bb1  jmp     loc_140007C7D
0x140007bb6  lea     rdx, [rbp+57h+LocalFileTime]; lpLocalFileTime
0x140007bba  lea     rcx, [rbp+57h+SystemInformation]; lpFileTime
0x140007bbe  call    cs:__imp_FileTimeToLocalFileTime
0x140007bc4  test    eax, eax
0x140007bc6  jnz     short loc_140007BED
0x140007bc8  call    cs:__imp_GetLastError
0x140007bce  test    eax, eax
0x140007bd0  jle     short loc_140007BDA
0x140007bd2  movzx   eax, ax
0x140007bd5  or      eax, 80070000h
0x140007bda  test    eax, eax
0x140007bdc  lea     r9, aFailedConverti; "Failed converting filetime to local fil"...
0x140007be3  mov     ecx, 80004005h
0x140007be8  cmovns  eax, ecx
0x140007beb  jmp     short loc_140007B9F
0x140007bed  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x140007bf1  lea     rcx, [rbp+57h+LocalFileTime]; lpFileTime
0x140007bf5  call    cs:__imp_FileTimeToSystemTime
0x140007bfb  test    eax, eax
0x140007bfd  jnz     short loc_140007C27
0x140007bff  call    cs:__imp_GetLastError
0x140007c05  test    eax, eax
0x140007c07  jle     short loc_140007C11
0x140007c09  movzx   eax, ax
0x140007c0c  or      eax, 80070000h
0x140007c11  test    eax, eax
0x140007c13  lea     r9, aFailedConverti_0; "Failed converting local filetime to sys"...
0x140007c1a  mov     ecx, 80004005h
0x140007c1f  cmovns  eax, ecx
0x140007c22  jmp     loc_140007B9F
0x140007c27  movzx   ecx, [rbp+57h+SystemTime.wSecond]
0x140007c2b  movzx   edx, [rbp+57h+SystemTime.wMinute]
0x140007c2f  movzx   r8d, [rbp+57h+SystemTime.wHour]
0x140007c34  movzx   r9d, [rbp+57h+SystemTime.wDay]
0x140007c39  movzx   eax, [rbp+57h+SystemTime.wMilliseconds]
0x140007c3d  movzx   r10d, [rbp+57h+SystemTime.wMonth]
0x140007c42  movzx   r11d, [rbp+57h+SystemTime.wYear]
0x140007c47  mov     [rsp+0B0h+var_60], eax
0x140007c4b  mov     [rsp+0B0h+var_68], ecx
0x140007c4f  mov     ecx, 4000000h
0x140007c54  mov     [rsp+0B0h+var_70], edx
0x140007c58  xor     edx, edx
0x140007c5a  mov     [rsp+0B0h+var_78], r8d
0x140007c5f  xor     r8d, r8d
0x140007c62  mov     [rsp+0B0h+var_80], r9d
0x140007c67  lea     r9, aTiLastBootTime; "TI: Last boot time: %04d-%02d-%02d %02d"...
0x140007c6e  mov     [rsp+0B0h+var_88], r10d
0x140007c73  mov     [rsp+0B0h+var_90], r11d
0x140007c78  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007c7d  mov     rcx, [rbp+57h+var_8]
0x140007c81  xor     rcx, rsp; StackCookie
0x140007c84  call    __security_check_cookie
0x140007c89  add     rsp, 0B0h
0x140007c90  pop     rbp
0x140007c91  retn
```
