# CreateKernelDump

- ea: `0x140016610`
- end: `0x1400167fa`
- name: `CreateKernelDump`
- size: `490`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140018478`

## callees

- `0x1400070bc`
- `0x140009794`
- `0x14000bb4c`
- `0x140016610`
- `0x1400185fc`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `ntdll!NtSystemDebugControl` at `0x1400167aa`
- `ntdll!NtSystemDebugControl` at `0x1400167aa`
- `ntdll!RtlNtStatusToDosError` at `0x1400167b6`
- `ntdll!RtlNtStatusToDosError` at `0x1400167b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001666a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001666a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400167c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400167c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400167c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400167c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14001667b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14001667b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140016734`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140016734`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140016660`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140016660`

## pseudocode

```c
_BOOL8 __fastcall CreateKernelDump(unsigned __int16 *a1)
{
  ULONG LastError; // ebx
  HANDLE FileW; // rax
  void *v4; // rdi
  int v5; // eax
  _DWORD InputBuffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v8; // [rsp+58h] [rbp-A8h]
  __int64 v9; // [rsp+60h] [rbp-A0h]
  __int64 v10; // [rsp+68h] [rbp-98h]
  __int64 v11; // [rsp+70h] [rbp-90h]
  void *v12; // [rsp+78h] [rbp-88h]
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  size_t v14[66]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t pszDest[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  SystemTime = 0;
  memset_0(InputBuffer, 0, 0x48u);
  if ( !(unsigned int)GetTempPath2W(260, v14) )
    goto LABEL_2;
  GetSystemTime(&SystemTime);
  if ( StringCchPrintfW(
         pszDest,
         0x104u,
         L"DrvInstKernel_%04hd%02hd%02hd_%02hd%02hd%02hd%03hd.dmp",
         SystemTime.wYear,
         SystemTime.wMonth,
         SystemTime.wDay,
         SystemTime.wHour,
         SystemTime.wMinute,
         SystemTime.wSecond,
         SystemTime.wMilliseconds) < 0
    || (int)StringCchCopyW(a1, 0x104u, v14) < 0 )
  {
    LastError = 13;
    goto LABEL_12;
  }
  if ( (unsigned int)pSetupConcatenatePaths(a1, pszDest, 260)
    && (FileW = CreateFileW(a1, 0x40040001u, 0, 0, 2u, 0x80u, 0), v4 = FileW, FileW != (HANDLE)-1LL) )
  {
    LastError = SetDumpFileSecurity(FileW);
    if ( !LastError )
    {
      InputBuffer[0] = 1;
      InputBuffer[1] = 353;
      v8 = 0;
      v9 = 0;
      v10 = 0;
      v11 = 0;
      v12 = v4;
      v5 = NtSystemDebugControl(SysDbgClearUmAttachPid|SysDbgQueryTraceInformation, InputBuffer, 0x48u, 0, 0, 0);
      if ( v5 < 0 )
        LastError = RtlNtStatusToDosError(v5);
    }
    CloseHandle(v4);
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
  }
LABEL_12:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x140016610  mov     [rsp-8+arg_8], rbx
0x140016615  mov     [rsp-8+arg_10], rdi
0x14001661a  push    rbp
0x14001661b  lea     rbp, [rsp-3E0h]
0x140016623  sub     rsp, 4E0h
0x14001662a  mov     rax, cs:__security_cookie
0x140016631  xor     rax, rsp
0x140016634  mov     [rbp+3E0h+var_10], rax
0x14001663b  xor     edx, edx; Val
0x14001663d  mov     rbx, rcx
0x140016640  xorps   xmm0, xmm0
0x140016643  lea     rcx, [rsp+4E0h+InputBuffer]; void *
0x140016648  movups  xmmword ptr [rbp+3E0h+SystemTime.wYear], xmm0
0x14001664c  lea     r8d, [rdx+48h]; Size
0x140016650  call    memset_0
0x140016655  mov     edi, 104h
0x14001665a  lea     rdx, [rbp+3E0h+var_430]
0x14001665e  mov     ecx, edi
0x140016660  call    cs:__imp_GetTempPath2W
0x140016666  test    eax, eax
0x140016668  jnz     short loc_140016677
0x14001666a  call    cs:__imp_GetLastError
0x140016670  mov     ebx, eax
0x140016672  jmp     loc_1400167C7
0x140016677  lea     rcx, [rbp+3E0h+SystemTime]; lpSystemTime
0x14001667b  call    cs:__imp_GetSystemTime
0x140016681  movzx   ecx, [rbp+3E0h+SystemTime.wSecond]
0x140016685  movzx   edx, [rbp+3E0h+SystemTime.wMinute]
0x140016689  movzx   r8d, [rbp+3E0h+SystemTime.wHour]
0x14001668e  movzx   eax, [rbp+3E0h+SystemTime.wMilliseconds]
0x140016692  movzx   r10d, [rbp+3E0h+SystemTime.wDay]
0x140016697  movzx   r11d, [rbp+3E0h+SystemTime.wMonth]
0x14001669c  movzx   r9d, [rbp+3E0h+SystemTime.wYear]
0x1400166a1  mov     [rsp+4E0h+var_498], eax
0x1400166a5  mov     [rsp+4E0h+var_4A0], ecx
0x1400166a9  lea     rcx, [rbp+3E0h+pszDest]; pszDest
0x1400166b0  mov     [rsp+4E0h+var_4A8], edx
0x1400166b4  mov     rdx, rdi; cchDest
0x1400166b7  mov     dword ptr [rsp+4E0h+hTemplateFile], r8d
0x1400166bc  lea     r8, aDrvinstkernel0; "DrvInstKernel_%04hd%02hd%02hd_%02hd%02h"...
0x1400166c3  mov     [rsp+4E0h+dwFlagsAndAttributes], r10d
0x1400166c8  mov     [rsp+4E0h+dwCreationDisposition], r11d
0x1400166cd  call    StringCchPrintfW
0x1400166d2  test    eax, eax
0x1400166d4  jns     short loc_1400166E0
0x1400166d6  mov     ebx, 0Dh
0x1400166db  jmp     loc_1400167C7
0x1400166e0  lea     r8, [rbp+3E0h+var_430]; unsigned __int16 *
0x1400166e4  mov     rdx, rdi; unsigned __int64
0x1400166e7  mov     rcx, rbx; unsigned __int16 *
0x1400166ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400166ef  test    eax, eax
0x1400166f1  js      short loc_1400166D6
0x1400166f3  mov     r8d, edi
0x1400166f6  lea     rdx, [rbp+3E0h+pszDest]
0x1400166fd  mov     rcx, rbx
0x140016700  call    pSetupConcatenatePaths
0x140016705  test    eax, eax
0x140016707  jz      loc_14001666A
0x14001670d  mov     [rsp+4E0h+hTemplateFile], 0; hTemplateFile
0x140016716  xor     r9d, r9d; lpSecurityAttributes
0x140016719  mov     [rsp+4E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140016721  xor     r8d, r8d; dwShareMode
0x140016724  mov     edx, 40040001h; dwDesiredAccess
0x140016729  mov     [rsp+4E0h+dwCreationDisposition], 2; dwCreationDisposition
0x140016731  mov     rcx, rbx; lpFileName
0x140016734  call    cs:__imp_CreateFileW
0x14001673a  mov     rdi, rax
0x14001673d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140016741  jz      loc_14001666A
0x140016747  mov     rcx, rax; handle
0x14001674a  call    SetDumpFileSecurity
0x14001674f  mov     ebx, eax
0x140016751  test    eax, eax
0x140016753  jnz     short loc_1400167BE
0x140016755  mov     qword ptr [rsp+4E0h+dwFlagsAndAttributes], 0; ReturnLength
0x14001675e  lea     r8d, [rax+48h]; InputBufferLength
0x140016762  xor     r9d, r9d; OutputBuffer
0x140016765  mov     [rsp+4E0h+dwCreationDisposition], eax; OutputBufferLength
0x140016769  lea     rdx, [rsp+4E0h+InputBuffer]; InputBuffer
0x14001676e  mov     [rsp+4E0h+InputBuffer], 1
0x140016776  lea     ecx, [rax+25h]; ControlCode
0x140016779  mov     [rsp+4E0h+var_48C], 161h
0x140016781  mov     [rsp+4E0h+var_488], 0
0x14001678a  mov     [rsp+4E0h+var_480], 0
0x140016793  mov     [rsp+4E0h+var_478], 0
0x14001679c  mov     [rsp+4E0h+var_470], 0
0x1400167a5  mov     [rsp+4E0h+var_468], rdi
0x1400167aa  call    cs:__imp_NtSystemDebugControl
0x1400167b0  test    eax, eax
0x1400167b2  jns     short loc_1400167BE
0x1400167b4  mov     ecx, eax; Status
0x1400167b6  call    cs:__imp_RtlNtStatusToDosError
0x1400167bc  mov     ebx, eax
0x1400167be  mov     rcx, rdi; hObject
0x1400167c1  call    cs:__imp_CloseHandle
0x1400167c7  mov     ecx, ebx; dwErrCode
0x1400167c9  call    cs:__imp_SetLastError
0x1400167cf  xor     eax, eax
0x1400167d1  test    ebx, ebx
0x1400167d3  setz    al
0x1400167d6  mov     rcx, [rbp+3E0h+var_10]
0x1400167dd  xor     rcx, rsp; StackCookie
0x1400167e0  call    __security_check_cookie
0x1400167e5  lea     r11, [rsp+4E0h+var_s0]
0x1400167ed  mov     rbx, [r11+18h]
0x1400167f1  mov     rdi, [r11+20h]
0x1400167f5  mov     rsp, r11
0x1400167f8  pop     rbp
0x1400167f9  retn
```
