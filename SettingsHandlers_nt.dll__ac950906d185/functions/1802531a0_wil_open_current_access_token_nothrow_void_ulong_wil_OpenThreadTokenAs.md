# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x1802531a0`
- end: `0x18025324d`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180252604`

## callees

- `0x1802531a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802531b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802531b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802531d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802531d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180253201`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180253201`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180253218`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180253218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802531e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18025322c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802531e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18025322c`

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
0x1802531a0  mov     [rsp+arg_0], rbx
0x1802531a5  push    rdi
0x1802531a6  sub     rsp, 20h
0x1802531aa  xor     ebx, ebx
0x1802531ac  mov     rdi, rcx
0x1802531af  cmp     r8d, 1
0x1802531b3  setz    bl
0x1802531b6  call    cs:__imp_GetCurrentThread
0x1802531bd  nop     dword ptr [rax+rax+00h]
0x1802531c2  mov     r9, rdi; TokenHandle
0x1802531c5  mov     r8d, ebx; OpenAsSelf
0x1802531c8  mov     rcx, rax; ThreadHandle
0x1802531cb  mov     edx, 8; DesiredAccess
0x1802531d0  call    cs:__imp_OpenThreadToken
0x1802531d7  nop     dword ptr [rax+rax+00h]
0x1802531dc  test    eax, eax
0x1802531de  jnz     short loc_180253228
0x1802531e0  call    cs:__imp_GetLastError
0x1802531e7  nop     dword ptr [rax+rax+00h]
0x1802531ec  mov     ebx, 80070000h
0x1802531f1  test    eax, eax
0x1802531f3  jle     short loc_1802531FA
0x1802531f5  movzx   eax, ax
0x1802531f8  or      eax, ebx
0x1802531fa  cmp     eax, 800703F0h
0x1802531ff  jnz     short loc_180253241
0x180253201  call    cs:__imp_GetCurrentProcess
0x180253208  nop     dword ptr [rax+rax+00h]
0x18025320d  mov     r8, rdi; TokenHandle
0x180253210  mov     edx, 8; DesiredAccess
0x180253215  mov     rcx, rax; ProcessHandle
0x180253218  call    cs:__imp_OpenProcessToken
0x18025321f  nop     dword ptr [rax+rax+00h]
0x180253224  test    eax, eax
0x180253226  jz      short loc_18025322C
0x180253228  xor     eax, eax
0x18025322a  jmp     short loc_180253241
0x18025322c  call    cs:__imp_GetLastError
0x180253233  nop     dword ptr [rax+rax+00h]
0x180253238  test    eax, eax
0x18025323a  jle     short loc_180253241
0x18025323c  movzx   eax, ax
0x18025323f  or      eax, ebx
0x180253241  mov     rbx, [rsp+28h+arg_0]
0x180253246  add     rsp, 20h
0x18025324a  pop     rdi
0x18025324b  retn
```
