# StartMmsTransportThroughSmsService(void)

- ea: `0x180026a08`
- end: `0x180026b3c`
- name: `?StartMmsTransportThroughSmsService@@YAJXZ`
- size: `308`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800696a8`
- `0x180069ce0`
- `0x180069f2c`

## callees

- `0x180015050`
- `0x180026914`
- `0x180026a08`
- `0x1800c6902`
- `0x1800c6940`

## import_xrefs

- `msvcrt!_wgetenv` at `0x180026a2a`
- `msvcrt!_wgetenv` at `0x180026a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ae9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180026adf`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180026adf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b1b`

## string_xrefs

- `0x180026a30`: `%s\system32\MessagingMmsTransport.exe`

## pseudocode

```c
__int64 StartMmsTransportThroughSmsService(void)
{
  wchar_t *v0; // rax
  signed int v1; // ebx
  signed int LastError; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-2B8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-298h] BYREF
  WCHAR ApplicationName[264]; // [rsp+E0h] [rbp-228h] BYREF

  v0 = _wgetenv(L"SystemRoot");
  v1 = StringCchPrintfW(ApplicationName, 0x104u, L"%s\\system32\\MessagingMmsTransport.exe", v0);
  if ( v1 < 0 )
    goto LABEL_2;
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(ApplicationName, 0, 0, 0, 0, 0xD000608u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
LABEL_2:
    Log_HREvent_8(v1);
    return (unsigned int)v1;
  }
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  return 0;
}

```

## disassembly

```asm
0x180026a08  push    rbx
0x180026a0a  sub     rsp, 300h
0x180026a11  mov     rax, cs:__security_cookie
0x180026a18  xor     rax, rsp
0x180026a1b  mov     [rsp+308h+var_18], rax
0x180026a23  lea     rcx, aSystemroot; "SystemRoot"
0x180026a2a  call    cs:__imp__wgetenv
0x180026a30  lea     r8, aSSystem32Messa; "%s\\system32\\MessagingMmsTransport.exe"
0x180026a37  mov     edx, 104h; unsigned __int64
0x180026a3c  mov     r9, rax
0x180026a3f  lea     rcx, [rsp+308h+ApplicationName]; unsigned __int16 *
0x180026a47  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026a4c  mov     ebx, eax
0x180026a4e  test    eax, eax
0x180026a50  jns     short loc_180026A72
0x180026a52  mov     r9d, 10Dh
0x180026a58  mov     edx, 1
0x180026a5d  lea     r8, aOnecoreuapBase_57; "onecoreuap\\base\\appmodel\\messagingom"...
0x180026a64  mov     ecx, ebx; int
0x180026a66  call    Log_HREvent_8
0x180026a6b  mov     eax, ebx
0x180026a6d  jmp     loc_180026B23
0x180026a72  xor     edx, edx; Val
0x180026a74  lea     rcx, [rsp+308h+StartupInfo+4]; void *
0x180026a79  lea     r8d, [rdx+64h]; Size
0x180026a7d  call    memset_0
0x180026a82  xor     eax, eax
0x180026a84  mov     [rsp+308h+StartupInfo.cb], 68h ; 'h'
0x180026a8c  mov     qword ptr [rsp+308h+ProcessInformation.dwProcessId], rax
0x180026a91  lea     rcx, [rsp+308h+ApplicationName]; lpApplicationName
0x180026a99  lea     rax, [rsp+308h+ProcessInformation]
0x180026a9e  xorps   xmm0, xmm0
0x180026aa1  mov     [rsp+308h+lpProcessInformation], rax; lpProcessInformation
0x180026aa6  xor     r9d, r9d; lpThreadAttributes
0x180026aa9  lea     rax, [rsp+308h+StartupInfo]
0x180026aae  xor     r8d, r8d; lpProcessAttributes
0x180026ab1  mov     [rsp+308h+lpStartupInfo], rax; lpStartupInfo
0x180026ab6  xor     edx, edx; lpCommandLine
0x180026ab8  mov     [rsp+308h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180026ac1  mov     [rsp+308h+lpEnvironment], 0; lpEnvironment
0x180026aca  mov     [rsp+308h+dwCreationFlags], 0D000608h; dwCreationFlags
0x180026ad2  mov     [rsp+308h+bInheritHandles], 0; bInheritHandles
0x180026ada  movups  xmmword ptr [rsp+308h+ProcessInformation.hProcess], xmm0
0x180026adf  call    cs:__imp_CreateProcessW
0x180026ae5  test    eax, eax
0x180026ae7  jnz     short loc_180026B0B
0x180026ae9  call    cs:__imp_GetLastError
0x180026aef  mov     ebx, eax
0x180026af1  test    eax, eax
0x180026af3  jle     short loc_180026AFE
0x180026af5  movzx   ebx, ax
0x180026af8  or      ebx, 80070000h
0x180026afe  mov     r9d, 116h
0x180026b04  xor     edx, edx
0x180026b06  jmp     loc_180026A5D
0x180026b0b  mov     rcx, [rsp+308h+ProcessInformation.hProcess]; hObject
0x180026b10  call    cs:__imp_CloseHandle
0x180026b16  mov     rcx, [rsp+308h+ProcessInformation.hThread]; hObject
0x180026b1b  call    cs:__imp_CloseHandle
0x180026b21  xor     eax, eax
0x180026b23  mov     rcx, [rsp+308h+var_18]
0x180026b2b  xor     rcx, rsp; StackCookie
0x180026b2e  call    __security_check_cookie
0x180026b33  add     rsp, 300h
0x180026b3a  pop     rbx
0x180026b3b  retn
```
