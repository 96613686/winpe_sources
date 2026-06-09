# GetPublisherIdentityForCurrentThread(void * *,ushort * *)

- ea: `0x180137470`
- end: `0x180137533`
- name: `?GetPublisherIdentityForCurrentThread@@YAKPEAPEAXPEAPEAG@Z`
- size: `195`
- prototype: `__int64 __fastcall(void **, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000f300`
- `0x18011feb0`
- `0x1801216f8`
- `0x180123c30`

## callees

- `0x180137470`
- `0x180137660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801374c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801374ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801374c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801374ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801374d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801374d2`
- `KERNEL32!CloseHandle` at `0x180137520`
- `KERNEL32!CloseHandle` at `0x180137520`
- `KERNEL32!GetCurrentThread` at `0x1801374a2`
- `KERNEL32!GetCurrentThread` at `0x1801374a2`
- `ADVAPI32!OpenThreadToken` at `0x1801374b9`
- `ADVAPI32!OpenThreadToken` at `0x1801374b9`
- `ADVAPI32!OpenProcessToken` at `0x1801374e5`
- `ADVAPI32!OpenProcessToken` at `0x1801374e5`

## pseudocode

```c
__int64 __fastcall GetPublisherIdentityForCurrentThread(void **a1, unsigned __int16 **a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int16 *v8; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  v8 = 0;
  if ( !a2 )
    return 160;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_7;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      return GetLastError();
LABEL_7:
    LastError = GetPublisherIdentityForThread(TokenHandle, &v8);
    if ( !LastError )
      *a2 = v8;
    if ( TokenHandle )
      CloseHandle(TokenHandle);
  }
  return LastError;
}

```

## disassembly

```asm
0x180137470  mov     rax, rsp
0x180137473  mov     [rax+18h], rbx
0x180137477  mov     [rax+8], rcx
0x18013747b  push    rdi
0x18013747c  sub     rsp, 20h
0x180137480  mov     qword ptr [rax+8], 0
0x180137488  mov     rdi, rdx
0x18013748b  mov     qword ptr [rax+10h], 0
0x180137493  test    rdx, rdx
0x180137496  jnz     short loc_1801374A2
0x180137498  mov     eax, 0A0h
0x18013749d  jmp     loc_180137528
0x1801374a2  call    cs:__imp_GetCurrentThread
0x1801374a8  mov     edx, 8; DesiredAccess
0x1801374ad  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1801374b2  mov     rcx, rax; ThreadHandle
0x1801374b5  lea     r8d, [rdx-7]; OpenAsSelf
0x1801374b9  call    cs:__imp_OpenThreadToken
0x1801374bf  test    eax, eax
0x1801374c1  jnz     short loc_1801374F9
0x1801374c3  call    cs:__imp_GetLastError
0x1801374c9  mov     ebx, eax
0x1801374cb  cmp     eax, 3F0h
0x1801374d0  jnz     short loc_180137526
0x1801374d2  call    cs:__imp_GetCurrentProcess
0x1801374d8  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1801374dd  mov     edx, 8; DesiredAccess
0x1801374e2  mov     rcx, rax; ProcessHandle
0x1801374e5  call    cs:__imp_OpenProcessToken
0x1801374eb  test    eax, eax
0x1801374ed  jnz     short loc_1801374F9
0x1801374ef  call    cs:__imp_GetLastError
0x1801374f5  mov     ebx, eax
0x1801374f7  jmp     short loc_180137526
0x1801374f9  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x1801374fe  lea     rdx, [rsp+28h+arg_8]; unsigned __int16 **
0x180137503  call    ?GetPublisherIdentityForThread@@YAKPEAXPEAPEAG@Z; GetPublisherIdentityForThread(void *,ushort * *)
0x180137508  mov     ebx, eax
0x18013750a  test    eax, eax
0x18013750c  jnz     short loc_180137516
0x18013750e  mov     rax, [rsp+28h+arg_8]
0x180137513  mov     [rdi], rax
0x180137516  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18013751b  test    rcx, rcx
0x18013751e  jz      short loc_180137526
0x180137520  call    cs:__imp_CloseHandle
0x180137526  mov     eax, ebx
0x180137528  mov     rbx, [rsp+28h+arg_10]
0x18013752d  add     rsp, 20h
0x180137531  pop     rdi
0x180137532  retn
```
