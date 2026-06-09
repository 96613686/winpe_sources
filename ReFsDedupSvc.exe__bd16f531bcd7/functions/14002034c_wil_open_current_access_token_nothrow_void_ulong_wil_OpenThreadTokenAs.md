# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x14002034c`
- end: `0x1400203ff`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400202f0`
- `0x14002cc74`

## callees

- `0x14002034c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400203d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400203d9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400203c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400203c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140020380`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140020380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140020369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140020369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400203b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400203b1`

## pseudocode

```c
signed int __fastcall wil::open_current_access_token_nothrow(void **a1, DWORD a2, int a3)
{
  BOOL v5; // ebx
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax

  v5 = a3 == 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, a2, v5, a1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, a2, a1) )
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
0x14002034c  mov     [rsp+arg_0], rbx
0x140020351  mov     [rsp+arg_8], rsi
0x140020356  push    rdi
0x140020357  sub     rsp, 20h
0x14002035b  xor     ebx, ebx
0x14002035d  mov     edi, edx
0x14002035f  cmp     r8d, 1
0x140020363  mov     rsi, rcx
0x140020366  setz    bl
0x140020369  call    cs:__imp_GetCurrentThread
0x140020370  nop     dword ptr [rax+rax+00h]
0x140020375  mov     r9, rsi; TokenHandle
0x140020378  mov     r8d, ebx; OpenAsSelf
0x14002037b  mov     rcx, rax; ThreadHandle
0x14002037e  mov     edx, edi; DesiredAccess
0x140020380  call    cs:__imp_OpenThreadToken
0x140020387  nop     dword ptr [rax+rax+00h]
0x14002038c  test    eax, eax
0x14002038e  jnz     short loc_1400203D5
0x140020390  call    cs:__imp_GetLastError
0x140020397  nop     dword ptr [rax+rax+00h]
0x14002039c  mov     ebx, 80070000h
0x1400203a1  test    eax, eax
0x1400203a3  jle     short loc_1400203AA
0x1400203a5  movzx   eax, ax
0x1400203a8  or      eax, ebx
0x1400203aa  cmp     eax, 800703F0h
0x1400203af  jnz     short loc_1400203EE
0x1400203b1  call    cs:__imp_GetCurrentProcess
0x1400203b8  nop     dword ptr [rax+rax+00h]
0x1400203bd  mov     r8, rsi; TokenHandle
0x1400203c0  mov     edx, edi; DesiredAccess
0x1400203c2  mov     rcx, rax; ProcessHandle
0x1400203c5  call    cs:__imp_OpenProcessToken
0x1400203cc  nop     dword ptr [rax+rax+00h]
0x1400203d1  test    eax, eax
0x1400203d3  jz      short loc_1400203D9
0x1400203d5  xor     eax, eax
0x1400203d7  jmp     short loc_1400203EE
0x1400203d9  call    cs:__imp_GetLastError
0x1400203e0  nop     dword ptr [rax+rax+00h]
0x1400203e5  test    eax, eax
0x1400203e7  jle     short loc_1400203EE
0x1400203e9  movzx   eax, ax
0x1400203ec  or      eax, ebx
0x1400203ee  mov     rbx, [rsp+28h+arg_0]
0x1400203f3  mov     rsi, [rsp+28h+arg_8]
0x1400203f8  add     rsp, 20h
0x1400203fc  pop     rdi
0x1400203fd  retn
```
