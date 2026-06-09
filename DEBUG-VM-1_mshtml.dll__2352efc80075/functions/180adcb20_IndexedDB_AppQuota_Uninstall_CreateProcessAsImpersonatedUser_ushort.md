# IndexedDB_AppQuota_Uninstall_CreateProcessAsImpersonatedUser(ushort *)

- ea: `0x180adcb20`
- end: `0x180adcceb`
- name: `?IndexedDB_AppQuota_Uninstall_CreateProcessAsImpersonatedUser@@YAJPEAG@Z`
- size: `459`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180adcef0`

## callees

- `0x180adcb20`
- `0x1810c2cb6`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180adcb3d`
- `KERNEL32!GetCurrentThread` at `0x180adcb3d`
- `KERNEL32!GetLastError` at `0x180adcc60`
- `KERNEL32!GetLastError` at `0x180adcc81`
- `KERNEL32!GetLastError` at `0x180adcca2`
- `KERNEL32!GetLastError` at `0x180adccc3`
- `KERNEL32!GetLastError` at `0x180adcc60`
- `KERNEL32!GetLastError` at `0x180adcc81`
- `KERNEL32!GetLastError` at `0x180adcca2`
- `KERNEL32!GetLastError` at `0x180adccc3`
- `KERNEL32!CloseHandle` at `0x180adcc49`
- `KERNEL32!CloseHandle` at `0x180adcc58`
- `KERNEL32!CloseHandle` at `0x180adcc9a`
- `KERNEL32!CloseHandle` at `0x180adccbb`
- `KERNEL32!CloseHandle` at `0x180adcc49`
- `KERNEL32!CloseHandle` at `0x180adcc58`
- `KERNEL32!CloseHandle` at `0x180adcc9a`
- `KERNEL32!CloseHandle` at `0x180adccbb`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenThreadToken` at `0x180adcb55`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenThreadToken` at `0x180adcb55`
- `api-ms-win-downlevel-advapi32-l1-1-0!DuplicateTokenEx` at `0x180adcb8e`
- `api-ms-win-downlevel-advapi32-l1-1-0!DuplicateTokenEx` at `0x180adcb8e`
- `api-ms-win-downlevel-advapi32-l1-1-0!CreateProcessAsUserW` at `0x180adcc34`
- `api-ms-win-downlevel-advapi32-l1-1-0!CreateProcessAsUserW` at `0x180adcc34`
- `USERENV!CreateEnvironmentBlock` at `0x180adcbaf`
- `USERENV!CreateEnvironmentBlock` at `0x180adcbaf`
- `USERENV!DestroyEnvironmentBlock` at `0x180adcc79`
- `USERENV!DestroyEnvironmentBlock` at `0x180adcc79`

## pseudocode

```c
__int64 __fastcall IndexedDB_AppQuota_Uninstall_CreateProcessAsImpersonatedUser(LPWSTR lpCommandLine)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  signed int v6; // eax
  signed int v7; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-39h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-19h] BYREF
  HANDLE hToken; // [rsp+108h] [rbp+6Fh] BYREF
  LPVOID Environment; // [rsp+110h] [rbp+77h] BYREF
  void *TokenHandle; // [rsp+118h] [rbp+7Fh] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle) )
  {
    hToken = 0;
    if ( DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hToken) )
    {
      Environment = 0;
      if ( CreateEnvironmentBlock(&Environment, hToken, 0) )
      {
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        memset_0(&StartupInfo, 0, sizeof(StartupInfo));
        StartupInfo.lpDesktop = L"winsta0\\default";
        StartupInfo.cb = 104;
        if ( CreateProcessAsUserW(
               hToken,
               0,
               lpCommandLine,
               0,
               0,
               0,
               0x400u,
               Environment,
               0,
               &StartupInfo,
               &ProcessInformation) )
        {
          v3 = 0;
          if ( ProcessInformation.hThread )
            CloseHandle(ProcessInformation.hThread);
          if ( ProcessInformation.hProcess )
            CloseHandle(ProcessInformation.hProcess);
        }
        else
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
        }
        DestroyEnvironmentBlock(Environment);
      }
      else
      {
        v5 = GetLastError();
        v3 = v5;
        if ( v5 > 0 )
          v3 = (unsigned __int16)v5 | 0x80070000;
      }
      CloseHandle(hToken);
    }
    else
    {
      v6 = GetLastError();
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180adcb20  mov     [rsp-8+arg_0], rbx
0x180adcb25  push    rbp
0x180adcb26  lea     rbp, [rsp-57h]
0x180adcb2b  sub     rsp, 0F0h
0x180adcb32  mov     rbx, rcx
0x180adcb35  mov     [rbp+57h+TokenHandle], 0
0x180adcb3d  call    cs:__imp_GetCurrentThread
0x180adcb43  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180adcb47  mov     edx, 2000000h; DesiredAccess
0x180adcb4c  mov     rcx, rax; ThreadHandle
0x180adcb4f  mov     r8d, 1; OpenAsSelf
0x180adcb55  call    cs:__imp_OpenThreadToken
0x180adcb5b  test    eax, eax
0x180adcb5d  jz      loc_180ADCCC3
0x180adcb63  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x180adcb67  lea     rax, [rbp+57h+hToken]
0x180adcb6b  mov     [rsp+0F0h+phNewToken], rax; phNewToken
0x180adcb70  mov     r9d, 2; ImpersonationLevel
0x180adcb76  xor     r8d, r8d; lpTokenAttributes
0x180adcb79  mov     [rsp+0F0h+TokenType], 1; TokenType
0x180adcb81  mov     edx, 2000000h; dwDesiredAccess
0x180adcb86  mov     [rbp+57h+hToken], 0
0x180adcb8e  call    cs:__imp_DuplicateTokenEx
0x180adcb94  test    eax, eax
0x180adcb96  jz      loc_180ADCCA2
0x180adcb9c  mov     rdx, [rbp+57h+hToken]; hToken
0x180adcba0  lea     rcx, [rbp+57h+Environment]; lpEnvironment
0x180adcba4  xor     r8d, r8d; bInherit
0x180adcba7  mov     [rbp+57h+Environment], 0
0x180adcbaf  call    cs:__imp_CreateEnvironmentBlock
0x180adcbb5  test    eax, eax
0x180adcbb7  jz      loc_180ADCC81
0x180adcbbd  xor     eax, eax
0x180adcbbf  lea     rcx, [rbp+57h+StartupInfo]; void *
0x180adcbc3  xorps   xmm0, xmm0
0x180adcbc6  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180adcbca  xor     edx, edx; Val
0x180adcbcc  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180adcbd0  lea     r8d, [rax+68h]; Size
0x180adcbd4  call    memset_0
0x180adcbd9  mov     rcx, [rbp+57h+hToken]; hToken
0x180adcbdd  lea     rax, aWinsta0Default; "winsta0\\default"
0x180adcbe4  mov     [rbp+57h+StartupInfo.lpDesktop], rax
0x180adcbe8  xor     r9d, r9d; lpProcessAttributes
0x180adcbeb  lea     rax, [rbp+57h+ProcessInformation]
0x180adcbef  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x180adcbf6  mov     [rsp+0F0h+lpProcessInformation], rax; lpProcessInformation
0x180adcbfb  mov     r8, rbx; lpCommandLine
0x180adcbfe  lea     rax, [rbp+57h+StartupInfo]
0x180adcc02  xor     edx, edx; lpApplicationName
0x180adcc04  mov     [rsp+0F0h+lpStartupInfo], rax; lpStartupInfo
0x180adcc09  mov     rax, [rbp+57h+Environment]
0x180adcc0d  mov     [rsp+0F0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180adcc16  mov     [rsp+0F0h+lpEnvironment], rax; lpEnvironment
0x180adcc1b  mov     [rsp+0F0h+dwCreationFlags], 400h; dwCreationFlags
0x180adcc23  mov     dword ptr [rsp+0F0h+phNewToken], 0; bInheritHandles
0x180adcc2b  mov     qword ptr [rsp+0F0h+TokenType], 0; lpThreadAttributes
0x180adcc34  call    cs:__imp_CreateProcessAsUserW
0x180adcc3a  test    eax, eax
0x180adcc3c  jz      short loc_180ADCC60
0x180adcc3e  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180adcc42  xor     ebx, ebx
0x180adcc44  test    rcx, rcx
0x180adcc47  jz      short loc_180ADCC4F
0x180adcc49  call    cs:__imp_CloseHandle
0x180adcc4f  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x180adcc53  test    rcx, rcx
0x180adcc56  jz      short loc_180ADCC75
0x180adcc58  call    cs:__imp_CloseHandle
0x180adcc5e  jmp     short loc_180ADCC75
0x180adcc60  call    cs:__imp_GetLastError
0x180adcc66  mov     ebx, eax
0x180adcc68  test    eax, eax
0x180adcc6a  jle     short loc_180ADCC75
0x180adcc6c  movzx   ebx, ax
0x180adcc6f  or      ebx, 80070000h
0x180adcc75  mov     rcx, [rbp+57h+Environment]; lpEnvironment
0x180adcc79  call    cs:__imp_DestroyEnvironmentBlock
0x180adcc7f  jmp     short loc_180ADCC96
0x180adcc81  call    cs:__imp_GetLastError
0x180adcc87  mov     ebx, eax
0x180adcc89  test    eax, eax
0x180adcc8b  jle     short loc_180ADCC96
0x180adcc8d  movzx   ebx, ax
0x180adcc90  or      ebx, 80070000h
0x180adcc96  mov     rcx, [rbp+57h+hToken]; hObject
0x180adcc9a  call    cs:__imp_CloseHandle
0x180adcca0  jmp     short loc_180ADCCB7
0x180adcca2  call    cs:__imp_GetLastError
0x180adcca8  mov     ebx, eax
0x180adccaa  test    eax, eax
0x180adccac  jle     short loc_180ADCCB7
0x180adccae  movzx   ebx, ax
0x180adccb1  or      ebx, 80070000h
0x180adccb7  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180adccbb  call    cs:__imp_CloseHandle
0x180adccc1  jmp     short loc_180ADCCD8
0x180adccc3  call    cs:__imp_GetLastError
0x180adccc9  mov     ebx, eax
0x180adcccb  test    eax, eax
0x180adcccd  jle     short loc_180ADCCD8
0x180adcccf  movzx   ebx, ax
0x180adccd2  or      ebx, 80070000h
0x180adccd8  mov     eax, ebx
0x180adccda  mov     rbx, [rsp+0F0h+arg_0]
0x180adcce2  add     rsp, 0F0h
0x180adcce9  pop     rbp
0x180adccea  retn
```
