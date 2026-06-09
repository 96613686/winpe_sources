# GetCurrentUserToken

- ea: `0x180032da0`
- end: `0x180032e43`
- name: `GetCurrentUserToken`
- size: `163`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032cb4`

## callees

- `0x1800096cc`
- `0x180032da0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032ddb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180032e11`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180032e11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032dfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032dfa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180032dcb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180032dcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032db0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032db0`

## string_xrefs

- `0x180032e26`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
__int64 __fastcall GetCurrentUserToken(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    return 0;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147023888 )
    return 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x6D,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
             v5);
}

```

## disassembly

```asm
0x180032da0  push    rbx
0x180032da2  sub     rsp, 20h
0x180032da6  mov     rbx, rcx
0x180032da9  mov     qword ptr [rcx], 0
0x180032db0  call    cs:__imp_GetCurrentThread
0x180032db7  nop     dword ptr [rax+rax+00h]
0x180032dbc  mov     edx, 8; DesiredAccess
0x180032dc1  mov     r9, rbx; TokenHandle
0x180032dc4  mov     rcx, rax; ThreadHandle
0x180032dc7  lea     r8d, [rdx-7]; OpenAsSelf
0x180032dcb  call    cs:__imp_OpenThreadToken
0x180032dd2  nop     dword ptr [rax+rax+00h]
0x180032dd7  test    eax, eax
0x180032dd9  jnz     short loc_180032E3A
0x180032ddb  call    cs:__imp_GetLastError
0x180032de2  nop     dword ptr [rax+rax+00h]
0x180032de7  test    eax, eax
0x180032de9  jle     short loc_180032DF3
0x180032deb  movzx   eax, ax
0x180032dee  or      eax, 80070000h
0x180032df3  cmp     eax, 800703F0h
0x180032df8  jnz     short loc_180032E3A
0x180032dfa  call    cs:__imp_GetCurrentProcess
0x180032e01  nop     dword ptr [rax+rax+00h]
0x180032e06  mov     r8, rbx; TokenHandle
0x180032e09  mov     edx, 8; DesiredAccess
0x180032e0e  mov     rcx, rax; ProcessHandle
0x180032e11  call    cs:__imp_OpenProcessToken
0x180032e18  nop     dword ptr [rax+rax+00h]
0x180032e1d  test    eax, eax
0x180032e1f  jnz     short loc_180032E3A
0x180032e21  mov     rcx, [rsp+28h]; this
0x180032e26  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180032e2d  lea     edx, [rax+6Dh]; void *
0x180032e30  add     rsp, 20h
0x180032e34  pop     rbx
0x180032e35  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032e3a  xor     eax, eax
0x180032e3c  add     rsp, 20h
0x180032e40  pop     rbx
0x180032e41  retn
```
