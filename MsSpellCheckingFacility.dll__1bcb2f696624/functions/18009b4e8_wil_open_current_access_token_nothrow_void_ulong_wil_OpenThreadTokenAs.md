# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x18009b4e8`
- end: `0x18009b570`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800438a8`

## callees

- `0x18009b4e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009b512`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009b512`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009b537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009b537`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009b548`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009b548`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009b4fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009b4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b51c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b51c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b556`

## pseudocode

```c
signed int __fastcall wil::open_current_access_token_nothrow(void **a1, __int64 a2, int a3)
{
  BOOL v4; // ebx
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax

  v4 = a3 == 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, v4, a1) )
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
0x18009b4e8  mov     [rsp+arg_0], rbx
0x18009b4ed  push    rdi
0x18009b4ee  sub     rsp, 20h
0x18009b4f2  xor     ebx, ebx
0x18009b4f4  mov     rdi, rcx
0x18009b4f7  cmp     r8d, 1
0x18009b4fb  setz    bl
0x18009b4fe  call    cs:__imp_GetCurrentThread
0x18009b504  mov     r9, rdi; TokenHandle
0x18009b507  mov     r8d, ebx; OpenAsSelf
0x18009b50a  mov     rcx, rax; ThreadHandle
0x18009b50d  mov     edx, 8; DesiredAccess
0x18009b512  call    cs:__imp_OpenThreadToken
0x18009b518  test    eax, eax
0x18009b51a  jnz     short loc_18009B552
0x18009b51c  call    cs:__imp_GetLastError
0x18009b522  mov     ebx, 80070000h
0x18009b527  test    eax, eax
0x18009b529  jle     short loc_18009B530
0x18009b52b  movzx   eax, ax
0x18009b52e  or      eax, ebx
0x18009b530  cmp     eax, 800703F0h
0x18009b535  jnz     short loc_18009B565
0x18009b537  call    cs:__imp_GetCurrentProcess
0x18009b53d  mov     r8, rdi; TokenHandle
0x18009b540  mov     edx, 8; DesiredAccess
0x18009b545  mov     rcx, rax; ProcessHandle
0x18009b548  call    cs:__imp_OpenProcessToken
0x18009b54e  test    eax, eax
0x18009b550  jz      short loc_18009B556
0x18009b552  xor     eax, eax
0x18009b554  jmp     short loc_18009B565
0x18009b556  call    cs:__imp_GetLastError
0x18009b55c  test    eax, eax
0x18009b55e  jle     short loc_18009B565
0x18009b560  movzx   eax, ax
0x18009b563  or      eax, ebx
0x18009b565  mov     rbx, [rsp+28h+arg_0]
0x18009b56a  add     rsp, 20h
0x18009b56e  pop     rdi
0x18009b56f  retn
```
