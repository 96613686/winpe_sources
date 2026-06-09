# Windows::Globalization::Spelling::ThirdPartySpellerCreator::ImpersonateProcess(ulong)

- ea: `0x180067648`
- end: `0x18006770d`
- name: `?ImpersonateProcess@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJK@Z`
- size: `197`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003912c`

## callees

- `0x180067648`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006769b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006769b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006766c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800676a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800676cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006766c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800676a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800676cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800676ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800676fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800676ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800676fa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800676c3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800676c3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006765e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006765e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Globalization::Spelling::ThirdPartySpellerCreator::ImpersonateProcess(DWORD dwProcessId)
{
  signed int v1; // ebx
  HANDLE v2; // rdi
  signed int LastError; // eax
  signed int v4; // eax
  signed int v5; // eax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v2 = OpenProcess(0x400u, 0, dwProcessId);
  if ( !v2 )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
  }
  TokenHandle = 0;
  if ( v1 >= 0 )
  {
    if ( OpenProcessToken(v2, 0xEu, &TokenHandle) )
      goto LABEL_19;
    v4 = GetLastError();
    v1 = v4;
    if ( v4 > 0 )
      v1 = (unsigned __int16)v4 | 0x80070000;
    if ( v1 >= 0 )
    {
LABEL_19:
      if ( !ImpersonateLoggedOnUser(TokenHandle) )
      {
        v5 = GetLastError();
        v1 = v5;
        if ( v5 > 0 )
          v1 = (unsigned __int16)v5 | 0x80070000;
      }
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
  }
  if ( v2 )
    CloseHandle(v2);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180067648  mov     [rsp+arg_0], rbx
0x18006764d  push    rdi
0x18006764e  sub     rsp, 20h
0x180067652  mov     r8d, ecx; dwProcessId
0x180067655  xor     edx, edx; bInheritHandle
0x180067657  mov     ecx, 400h; dwDesiredAccess
0x18006765c  xor     ebx, ebx
0x18006765e  call    cs:__imp_OpenProcess
0x180067664  mov     rdi, rax
0x180067667  test    rax, rax
0x18006766a  jnz     short loc_180067681
0x18006766c  call    cs:__imp_GetLastError
0x180067672  mov     ebx, eax
0x180067674  test    eax, eax
0x180067676  jle     short loc_180067681
0x180067678  movzx   ebx, ax
0x18006767b  or      ebx, 80070000h
0x180067681  mov     [rsp+28h+TokenHandle], 0
0x18006768a  test    ebx, ebx
0x18006768c  js      short loc_1800676F2
0x18006768e  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180067693  mov     edx, 0Eh; DesiredAccess
0x180067698  mov     rcx, rdi; ProcessHandle
0x18006769b  call    cs:__imp_OpenProcessToken
0x1800676a1  test    eax, eax
0x1800676a3  jnz     short loc_1800676BE
0x1800676a5  call    cs:__imp_GetLastError
0x1800676ab  mov     ebx, eax
0x1800676ad  test    eax, eax
0x1800676af  jle     short loc_1800676BA
0x1800676b1  movzx   ebx, ax
0x1800676b4  or      ebx, 80070000h
0x1800676ba  test    ebx, ebx
0x1800676bc  js      short loc_1800676E2
0x1800676be  mov     rcx, [rsp+28h+TokenHandle]; hToken
0x1800676c3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800676c9  test    eax, eax
0x1800676cb  jnz     short loc_1800676E2
0x1800676cd  call    cs:__imp_GetLastError
0x1800676d3  mov     ebx, eax
0x1800676d5  test    eax, eax
0x1800676d7  jle     short loc_1800676E2
0x1800676d9  movzx   ebx, ax
0x1800676dc  or      ebx, 80070000h
0x1800676e2  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800676e7  test    rcx, rcx
0x1800676ea  jz      short loc_1800676F2
0x1800676ec  call    cs:__imp_CloseHandle
0x1800676f2  test    rdi, rdi
0x1800676f5  jz      short loc_180067700
0x1800676f7  mov     rcx, rdi; hObject
0x1800676fa  call    cs:__imp_CloseHandle
0x180067700  mov     eax, ebx
0x180067702  mov     rbx, [rsp+28h+arg_0]
0x180067707  add     rsp, 20h
0x18006770b  pop     rdi
0x18006770c  retn
```
