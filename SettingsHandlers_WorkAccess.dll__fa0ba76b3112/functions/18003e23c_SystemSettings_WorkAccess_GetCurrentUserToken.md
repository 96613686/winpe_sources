# SystemSettings::WorkAccess::GetCurrentUserToken

- ea: `0x18003e23c`
- end: `0x18003e2df`
- name: `SystemSettings::WorkAccess::GetCurrentUserToken`
- size: `163`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003e154`

## callees

- `0x1800096cc`
- `0x18003e23c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e277`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003e2ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003e2ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e296`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e296`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003e267`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003e267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003e24c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003e24c`

## string_xrefs

- `0x18003e2c2`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::GetCurrentUserToken(PHANDLE TokenHandle)
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
             (void *)0x51,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
             v5);
}

```

## disassembly

```asm
0x18003e23c  push    rbx
0x18003e23e  sub     rsp, 20h
0x18003e242  mov     rbx, rcx
0x18003e245  mov     qword ptr [rcx], 0
0x18003e24c  call    cs:__imp_GetCurrentThread
0x18003e253  nop     dword ptr [rax+rax+00h]
0x18003e258  mov     edx, 8; DesiredAccess
0x18003e25d  mov     r9, rbx; TokenHandle
0x18003e260  mov     rcx, rax; ThreadHandle
0x18003e263  lea     r8d, [rdx-7]; OpenAsSelf
0x18003e267  call    cs:__imp_OpenThreadToken
0x18003e26e  nop     dword ptr [rax+rax+00h]
0x18003e273  test    eax, eax
0x18003e275  jnz     short loc_18003E2D6
0x18003e277  call    cs:__imp_GetLastError
0x18003e27e  nop     dword ptr [rax+rax+00h]
0x18003e283  test    eax, eax
0x18003e285  jle     short loc_18003E28F
0x18003e287  movzx   eax, ax
0x18003e28a  or      eax, 80070000h
0x18003e28f  cmp     eax, 800703F0h
0x18003e294  jnz     short loc_18003E2D6
0x18003e296  call    cs:__imp_GetCurrentProcess
0x18003e29d  nop     dword ptr [rax+rax+00h]
0x18003e2a2  mov     r8, rbx; TokenHandle
0x18003e2a5  mov     edx, 8; DesiredAccess
0x18003e2aa  mov     rcx, rax; ProcessHandle
0x18003e2ad  call    cs:__imp_OpenProcessToken
0x18003e2b4  nop     dword ptr [rax+rax+00h]
0x18003e2b9  test    eax, eax
0x18003e2bb  jnz     short loc_18003E2D6
0x18003e2bd  mov     rcx, [rsp+28h]; this
0x18003e2c2  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e2c9  lea     edx, [rax+51h]; void *
0x18003e2cc  add     rsp, 20h
0x18003e2d0  pop     rbx
0x18003e2d1  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e2d6  xor     eax, eax
0x18003e2d8  add     rsp, 20h
0x18003e2dc  pop     rbx
0x18003e2dd  retn
```
