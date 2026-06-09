# SetPrivileges(void * *)

- ea: `0x180039bbc`
- end: `0x180039cfa`
- name: `?SetPrivileges@@YAJPEAPEAX@Z`
- size: `318`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800341b0`
- `0x18003c89c`

## callees

- `0x1800078b0`
- `0x180039bbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039cb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039bf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039bf6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180039c4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180039c4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039c3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039c3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039c0c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039c0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039cd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039cd1`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180039ca8`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180039ca8`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180039c63`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180039c63`

## string_xrefs

- `0x180039c5c`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c
__int64 __fastcall SetPrivileges(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  HANDLE CurrentProcess; // rax
  signed int v6; // eax
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  int v9; // [rsp+38h] [rbp-40h]
  DWORD ReturnLength; // [rsp+40h] [rbp-38h] BYREF
  struct _LUID Luid; // [rsp+48h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+50h] [rbp-28h] BYREF

  Luid = 0;
  v9 = 0;
  TokenHandle = 0;
  NewState = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
LABEL_8:
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_10;
    }
LABEL_6:
    if ( LookupPrivilegeValueW(0, L"SeSystemEnvironmentPrivilege", &Luid) )
    {
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &previousPrivilege, &ReturnLength) )
      {
        v4 = 0;
        goto LABEL_14;
      }
    }
    goto LABEL_8;
  }
LABEL_10:
  if ( (v4 & 0x80000000) == 0 )
  {
LABEL_14:
    *a1 = TokenHandle;
    return v4;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x180039bbc  push    rbp
0x180039bbe  push    rbx
0x180039bbf  push    rdi
0x180039bc0  push    r14
0x180039bc2  mov     rbp, rsp
0x180039bc5  sub     rsp, 78h
0x180039bc9  mov     rax, cs:__security_cookie
0x180039bd0  xor     rax, rsp
0x180039bd3  mov     [rbp+var_18], rax
0x180039bd7  xor     eax, eax
0x180039bd9  mov     qword ptr [rbp+Luid.LowPart], 0
0x180039be1  xorps   xmm0, xmm0
0x180039be4  mov     [rbp+TokenHandle+4], rax
0x180039be8  mov     [rbp-48h], rax
0x180039bec  mov     rdi, rcx
0x180039bef  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180039bf3  mov     [rbp+var_38], eax
0x180039bf6  call    cs:__imp_GetCurrentThread
0x180039bfc  mov     edx, 28h ; '('; DesiredAccess
0x180039c01  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180039c05  mov     rcx, rax; ThreadHandle
0x180039c08  lea     r8d, [rdx-27h]; OpenAsSelf
0x180039c0c  call    cs:__imp_OpenThreadToken
0x180039c12  mov     r14d, 80070000h
0x180039c18  test    eax, eax
0x180039c1a  jnz     short loc_180039C56
0x180039c1c  call    cs:__imp_GetLastError
0x180039c22  mov     ebx, eax
0x180039c24  test    eax, eax
0x180039c26  jle     short loc_180039C2E
0x180039c28  movzx   ebx, ax
0x180039c2b  or      ebx, r14d
0x180039c2e  cmp     ebx, 800703F0h
0x180039c34  jnz     loc_180039CC4
0x180039c3a  call    cs:__imp_GetCurrentProcess
0x180039c40  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180039c44  mov     edx, 28h ; '('; DesiredAccess
0x180039c49  mov     rcx, rax; ProcessHandle
0x180039c4c  call    cs:__imp_OpenProcessToken
0x180039c52  test    eax, eax
0x180039c54  jz      short loc_180039CB2
0x180039c56  lea     r8, [rbp+Luid]; lpLuid
0x180039c5a  xor     ecx, ecx; lpSystemName
0x180039c5c  lea     rdx, Name; "SeSystemEnvironmentPrivilege"
0x180039c63  call    cs:__imp_LookupPrivilegeValueW
0x180039c69  test    eax, eax
0x180039c6b  jz      short loc_180039CB2
0x180039c6d  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180039c71  lea     r8, [rbp+NewState]; NewState
0x180039c75  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180039c79  mov     r9d, 10h; BufferLength
0x180039c7f  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x180039c83  xor     edx, edx; DisableAllPrivileges
0x180039c85  lea     rax, [rbp+var_38]
0x180039c89  mov     [rbp+NewState.PrivilegeCount], 1
0x180039c90  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180039c95  lea     rax, ?previousPrivilege@@3U_TOKEN_PRIVILEGES@@A; _TOKEN_PRIVILEGES previousPrivilege
0x180039c9c  mov     [rsp+78h+PreviousState], rax; PreviousState
0x180039ca1  mov     [rbp+NewState.Privileges.Attributes], 2
0x180039ca8  call    cs:__imp_AdjustTokenPrivileges
0x180039cae  test    eax, eax
0x180039cb0  jnz     short loc_180039CD9
0x180039cb2  call    cs:__imp_GetLastError
0x180039cb8  mov     ebx, eax
0x180039cba  test    eax, eax
0x180039cbc  jle     short loc_180039CC4
0x180039cbe  movzx   ebx, ax
0x180039cc1  or      ebx, r14d
0x180039cc4  test    ebx, ebx
0x180039cc6  jns     short loc_180039CDB
0x180039cc8  mov     rcx, [rbp+TokenHandle]; hObject
0x180039ccc  test    rcx, rcx
0x180039ccf  jz      short loc_180039CE2
0x180039cd1  call    cs:__imp_CloseHandle
0x180039cd7  jmp     short loc_180039CE2
0x180039cd9  xor     ebx, ebx
0x180039cdb  mov     rcx, [rbp+TokenHandle]
0x180039cdf  mov     [rdi], rcx
0x180039ce2  mov     eax, ebx
0x180039ce4  mov     rcx, [rbp+var_18]
0x180039ce8  xor     rcx, rsp; StackCookie
0x180039ceb  call    __security_check_cookie
0x180039cf0  add     rsp, 78h
0x180039cf4  pop     r14
0x180039cf6  pop     rdi
0x180039cf7  pop     rbx
0x180039cf8  pop     rbp
0x180039cf9  retn
```
