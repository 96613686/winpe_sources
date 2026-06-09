# GetCurrentUserToken

- ea: `0x1800148bc`
- end: `0x18001496e`
- name: `GetCurrentUserToken`
- size: `178`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800147e8`
- `0x180014abc`

## callees

- `0x1800148bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014941`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800148ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800148ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014931`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014931`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800148e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800148e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001491a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001491a`

## pseudocode

```c
__int64 __fastcall GetCurrentUserToken(PHANDLE TokenHandle)
{
  unsigned int v1; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v6; // eax

  v1 = 0;
  *TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 == -2147023888 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
      {
        return 0;
      }
      else
      {
        v6 = GetLastError();
        v1 = v6;
        if ( v6 > 0 )
          return (unsigned __int16)v6 | 0x80070000;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800148bc  mov     [rsp+arg_0], rbx
0x1800148c1  push    rdi
0x1800148c2  sub     rsp, 20h
0x1800148c6  xor     ebx, ebx
0x1800148c8  mov     rdi, rcx
0x1800148cb  mov     [rcx], rbx
0x1800148ce  call    cs:__imp_GetCurrentThread
0x1800148d5  nop     dword ptr [rax+rax+00h]
0x1800148da  mov     r9, rdi; TokenHandle
0x1800148dd  lea     edx, [rbx+8]; DesiredAccess
0x1800148e0  mov     rcx, rax; ThreadHandle
0x1800148e3  lea     r8d, [rbx+1]; OpenAsSelf
0x1800148e7  call    cs:__imp_OpenThreadToken
0x1800148ee  nop     dword ptr [rax+rax+00h]
0x1800148f3  test    eax, eax
0x1800148f5  jnz     short loc_180014960
0x1800148f7  call    cs:__imp_GetLastError
0x1800148fe  nop     dword ptr [rax+rax+00h]
0x180014903  mov     ebx, eax
0x180014905  test    eax, eax
0x180014907  jle     short loc_180014912
0x180014909  movzx   ebx, ax
0x18001490c  or      ebx, 80070000h
0x180014912  cmp     ebx, 800703F0h
0x180014918  jnz     short loc_180014960
0x18001491a  call    cs:__imp_GetCurrentProcess
0x180014921  nop     dword ptr [rax+rax+00h]
0x180014926  mov     r8, rdi; TokenHandle
0x180014929  mov     edx, 8; DesiredAccess
0x18001492e  mov     rcx, rax; ProcessHandle
0x180014931  call    cs:__imp_OpenProcessToken
0x180014938  nop     dword ptr [rax+rax+00h]
0x18001493d  test    eax, eax
0x18001493f  jnz     short loc_18001495E
0x180014941  call    cs:__imp_GetLastError
0x180014948  nop     dword ptr [rax+rax+00h]
0x18001494d  mov     ebx, eax
0x18001494f  test    eax, eax
0x180014951  jle     short loc_180014960
0x180014953  movzx   ebx, ax
0x180014956  or      ebx, 80070000h
0x18001495c  jmp     short loc_180014960
0x18001495e  xor     ebx, ebx
0x180014960  mov     eax, ebx
0x180014962  mov     rbx, [rsp+28h+arg_0]
0x180014967  add     rsp, 20h
0x18001496b  pop     rdi
0x18001496c  retn
```
