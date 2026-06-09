# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x14005ce5c`
- end: `0x14005cef9`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14005ca90`

## callees

- `0x14005ce5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ce90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ceda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ce90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ceda`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005ce80`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005ce80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005ce65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005ce65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14005ceaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14005ceaf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14005cec6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14005cec6`

## pseudocode

```c
signed int __fastcall wil::open_current_access_token_nothrow(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, a1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, a1) )
      return 0;
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x14005ce5c  push    rbx
0x14005ce5e  sub     rsp, 20h
0x14005ce62  mov     rbx, rcx
0x14005ce65  call    cs:__imp_GetCurrentThread
0x14005ce6c  nop     dword ptr [rax+rax+00h]
0x14005ce71  mov     edx, 8; DesiredAccess
0x14005ce76  mov     r9, rbx; TokenHandle
0x14005ce79  mov     rcx, rax; ThreadHandle
0x14005ce7c  lea     r8d, [rdx-7]; OpenAsSelf
0x14005ce80  call    cs:__imp_OpenThreadToken
0x14005ce87  nop     dword ptr [rax+rax+00h]
0x14005ce8c  test    eax, eax
0x14005ce8e  jnz     short loc_14005CED6
0x14005ce90  call    cs:__imp_GetLastError
0x14005ce97  nop     dword ptr [rax+rax+00h]
0x14005ce9c  test    eax, eax
0x14005ce9e  jle     short loc_14005CEA8
0x14005cea0  movzx   eax, ax
0x14005cea3  or      eax, 80070000h
0x14005cea8  cmp     eax, 800703F0h
0x14005cead  jnz     short loc_14005CEF2
0x14005ceaf  call    cs:__imp_GetCurrentProcess
0x14005ceb6  nop     dword ptr [rax+rax+00h]
0x14005cebb  mov     r8, rbx; TokenHandle
0x14005cebe  mov     edx, 8; DesiredAccess
0x14005cec3  mov     rcx, rax; ProcessHandle
0x14005cec6  call    cs:__imp_OpenProcessToken
0x14005cecd  nop     dword ptr [rax+rax+00h]
0x14005ced2  test    eax, eax
0x14005ced4  jz      short loc_14005CEDA
0x14005ced6  xor     eax, eax
0x14005ced8  jmp     short loc_14005CEF2
0x14005ceda  call    cs:__imp_GetLastError
0x14005cee1  nop     dword ptr [rax+rax+00h]
0x14005cee6  test    eax, eax
0x14005cee8  jle     short loc_14005CEF2
0x14005ceea  movzx   eax, ax
0x14005ceed  or      eax, 80070000h
0x14005cef2  add     rsp, 20h
0x14005cef6  pop     rbx
0x14005cef7  retn
```
