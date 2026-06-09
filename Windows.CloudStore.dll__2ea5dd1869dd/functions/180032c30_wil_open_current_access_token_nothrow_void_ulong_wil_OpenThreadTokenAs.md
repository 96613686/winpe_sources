# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x180032c30`
- end: `0x180032cb9`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180032bd0`

## callees

- `0x180032c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032ca5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180032c8e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180032c8e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180032c5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180032c5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032c46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032c46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032c7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032c7d`

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
  if ( OpenThreadToken(CurrentThread, 0x2000000u, v4, a1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x2000000u, a1) )
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
0x180032c30  mov     [rsp+arg_0], rbx
0x180032c35  push    rdi
0x180032c36  sub     rsp, 20h
0x180032c3a  xor     ebx, ebx
0x180032c3c  mov     rdi, rcx
0x180032c3f  cmp     r8d, 1
0x180032c43  setz    bl
0x180032c46  call    cs:__imp_GetCurrentThread
0x180032c4c  mov     r9, rdi; TokenHandle
0x180032c4f  mov     r8d, ebx; OpenAsSelf
0x180032c52  mov     rcx, rax; ThreadHandle
0x180032c55  mov     edx, 2000000h; DesiredAccess
0x180032c5a  call    cs:__imp_OpenThreadToken
0x180032c60  test    eax, eax
0x180032c62  jnz     short loc_180032C98
0x180032c64  call    cs:__imp_GetLastError
0x180032c6a  test    eax, eax
0x180032c6c  jle     short loc_180032C76
0x180032c6e  movzx   eax, ax
0x180032c71  or      eax, 80070000h
0x180032c76  cmp     eax, 800703F0h
0x180032c7b  jnz     short loc_180032C9A
0x180032c7d  call    cs:__imp_GetCurrentProcess
0x180032c83  mov     r8, rdi; TokenHandle
0x180032c86  mov     edx, 2000000h; DesiredAccess
0x180032c8b  mov     rcx, rax; ProcessHandle
0x180032c8e  call    cs:__imp_OpenProcessToken
0x180032c94  test    eax, eax
0x180032c96  jz      short loc_180032CA5
0x180032c98  xor     eax, eax
0x180032c9a  mov     rbx, [rsp+28h+arg_0]
0x180032c9f  add     rsp, 20h
0x180032ca3  pop     rdi
0x180032ca4  retn
0x180032ca5  call    cs:__imp_GetLastError
0x180032cab  test    eax, eax
0x180032cad  jle     short loc_180032C9A
0x180032caf  movzx   eax, ax
0x180032cb2  or      eax, 80070000h
0x180032cb7  jmp     short loc_180032C9A
```
