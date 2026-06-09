# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x180022d34`
- end: `0x180022dac`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `120`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18001dfb8`
- `0x180022c60`
- `0x18004d970`

## callees

- `0x180022d34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d94`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022d52`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022d52`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022d86`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022d86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022d75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022d75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022d3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022d3d`

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
0x180022d34  push    rbx
0x180022d36  sub     rsp, 20h
0x180022d3a  mov     rbx, rcx
0x180022d3d  call    cs:__imp_GetCurrentThread
0x180022d43  mov     edx, 8; DesiredAccess
0x180022d48  mov     r9, rbx; TokenHandle
0x180022d4b  mov     rcx, rax; ThreadHandle
0x180022d4e  lea     r8d, [rdx-7]; OpenAsSelf
0x180022d52  call    cs:__imp_OpenThreadToken
0x180022d58  test    eax, eax
0x180022d5a  jnz     short loc_180022D90
0x180022d5c  call    cs:__imp_GetLastError
0x180022d62  test    eax, eax
0x180022d64  jle     short loc_180022D6E
0x180022d66  movzx   eax, ax
0x180022d69  or      eax, 80070000h
0x180022d6e  cmp     eax, 800703F0h
0x180022d73  jnz     short loc_180022DA6
0x180022d75  call    cs:__imp_GetCurrentProcess
0x180022d7b  mov     r8, rbx; TokenHandle
0x180022d7e  mov     edx, 8; DesiredAccess
0x180022d83  mov     rcx, rax; ProcessHandle
0x180022d86  call    cs:__imp_OpenProcessToken
0x180022d8c  test    eax, eax
0x180022d8e  jz      short loc_180022D94
0x180022d90  xor     eax, eax
0x180022d92  jmp     short loc_180022DA6
0x180022d94  call    cs:__imp_GetLastError
0x180022d9a  test    eax, eax
0x180022d9c  jle     short loc_180022DA6
0x180022d9e  movzx   eax, ax
0x180022da1  or      eax, 80070000h
0x180022da6  add     rsp, 20h
0x180022daa  pop     rbx
0x180022dab  retn
```
