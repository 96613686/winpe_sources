# GetCurrentUserToken

- ea: `0x18006c710`
- end: `0x18006c7c2`
- name: `GetCurrentUserToken`
- size: `178`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18006a670`
- `0x18006a730`
- `0x18006c63c`
- `0x18006c910`

## callees

- `0x18006c710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c74b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c74b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c795`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c73b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c73b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006c76e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006c76e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006c785`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006c785`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c722`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c722`

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
0x18006c710  mov     [rsp+arg_0], rbx
0x18006c715  push    rdi
0x18006c716  sub     rsp, 20h
0x18006c71a  xor     ebx, ebx
0x18006c71c  mov     rdi, rcx
0x18006c71f  mov     [rcx], rbx
0x18006c722  call    cs:__imp_GetCurrentThread
0x18006c729  nop     dword ptr [rax+rax+00h]
0x18006c72e  mov     r9, rdi; TokenHandle
0x18006c731  lea     edx, [rbx+8]; DesiredAccess
0x18006c734  mov     rcx, rax; ThreadHandle
0x18006c737  lea     r8d, [rbx+1]; OpenAsSelf
0x18006c73b  call    cs:__imp_OpenThreadToken
0x18006c742  nop     dword ptr [rax+rax+00h]
0x18006c747  test    eax, eax
0x18006c749  jnz     short loc_18006C7B4
0x18006c74b  call    cs:__imp_GetLastError
0x18006c752  nop     dword ptr [rax+rax+00h]
0x18006c757  mov     ebx, eax
0x18006c759  test    eax, eax
0x18006c75b  jle     short loc_18006C766
0x18006c75d  movzx   ebx, ax
0x18006c760  or      ebx, 80070000h
0x18006c766  cmp     ebx, 800703F0h
0x18006c76c  jnz     short loc_18006C7B4
0x18006c76e  call    cs:__imp_GetCurrentProcess
0x18006c775  nop     dword ptr [rax+rax+00h]
0x18006c77a  mov     r8, rdi; TokenHandle
0x18006c77d  mov     edx, 8; DesiredAccess
0x18006c782  mov     rcx, rax; ProcessHandle
0x18006c785  call    cs:__imp_OpenProcessToken
0x18006c78c  nop     dword ptr [rax+rax+00h]
0x18006c791  test    eax, eax
0x18006c793  jnz     short loc_18006C7B2
0x18006c795  call    cs:__imp_GetLastError
0x18006c79c  nop     dword ptr [rax+rax+00h]
0x18006c7a1  mov     ebx, eax
0x18006c7a3  test    eax, eax
0x18006c7a5  jle     short loc_18006C7B4
0x18006c7a7  movzx   ebx, ax
0x18006c7aa  or      ebx, 80070000h
0x18006c7b0  jmp     short loc_18006C7B4
0x18006c7b2  xor     ebx, ebx
0x18006c7b4  mov     eax, ebx
0x18006c7b6  mov     rbx, [rsp+28h+arg_0]
0x18006c7bb  add     rsp, 20h
0x18006c7bf  pop     rdi
0x18006c7c0  retn
```
