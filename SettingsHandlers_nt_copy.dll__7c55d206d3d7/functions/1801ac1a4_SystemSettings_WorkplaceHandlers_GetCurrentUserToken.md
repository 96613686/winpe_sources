# SystemSettings::WorkplaceHandlers::GetCurrentUserToken

- ea: `0x1801ac1a4`
- end: `0x1801ac248`
- name: `SystemSettings::WorkplaceHandlers::GetCurrentUserToken`
- size: `164`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1801ac080`

## callees

- `0x1801ac1a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801ac1b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801ac1b4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801ac1cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801ac1cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801ac1fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801ac1fe`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801ac215`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801ac215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac1df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac1df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac225`

## pseudocode

```c
signed int __fastcall SystemSettings::WorkplaceHandlers::GetCurrentUserToken(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int result; // eax

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
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1801ac1a4  push    rbx
0x1801ac1a6  sub     rsp, 20h
0x1801ac1aa  mov     rbx, rcx
0x1801ac1ad  mov     qword ptr [rcx], 0
0x1801ac1b4  call    cs:__imp_GetCurrentThread
0x1801ac1bb  nop     dword ptr [rax+rax+00h]
0x1801ac1c0  mov     edx, 8; DesiredAccess
0x1801ac1c5  mov     r9, rbx; TokenHandle
0x1801ac1c8  mov     rcx, rax; ThreadHandle
0x1801ac1cb  lea     r8d, [rdx-7]; OpenAsSelf
0x1801ac1cf  call    cs:__imp_OpenThreadToken
0x1801ac1d6  nop     dword ptr [rax+rax+00h]
0x1801ac1db  test    eax, eax
0x1801ac1dd  jnz     short loc_1801AC23F
0x1801ac1df  call    cs:__imp_GetLastError
0x1801ac1e6  nop     dword ptr [rax+rax+00h]
0x1801ac1eb  test    eax, eax
0x1801ac1ed  jle     short loc_1801AC1F7
0x1801ac1ef  movzx   eax, ax
0x1801ac1f2  or      eax, 80070000h
0x1801ac1f7  cmp     eax, 800703F0h
0x1801ac1fc  jnz     short loc_1801AC23F
0x1801ac1fe  call    cs:__imp_GetCurrentProcess
0x1801ac205  nop     dword ptr [rax+rax+00h]
0x1801ac20a  mov     r8, rbx; TokenHandle
0x1801ac20d  mov     edx, 8; DesiredAccess
0x1801ac212  mov     rcx, rax; ProcessHandle
0x1801ac215  call    cs:__imp_OpenProcessToken
0x1801ac21c  nop     dword ptr [rax+rax+00h]
0x1801ac221  test    eax, eax
0x1801ac223  jnz     short loc_1801AC23F
0x1801ac225  call    cs:__imp_GetLastError
0x1801ac22c  nop     dword ptr [rax+rax+00h]
0x1801ac231  test    eax, eax
0x1801ac233  jle     short loc_1801AC241
0x1801ac235  movzx   eax, ax
0x1801ac238  or      eax, 80070000h
0x1801ac23d  jmp     short loc_1801AC241
0x1801ac23f  xor     eax, eax
0x1801ac241  add     rsp, 20h
0x1801ac245  pop     rbx
0x1801ac246  retn
```
