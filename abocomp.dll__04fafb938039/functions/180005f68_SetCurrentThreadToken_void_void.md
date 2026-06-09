# SetCurrentThreadToken(void *,void * *)

- ea: `0x180005f68`
- end: `0x18000603a`
- name: `?SetCurrentThreadToken@@YAJPEAXPEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(HANDLE Token, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002a070`

## callees

- `0x180001f90`
- `0x180005f68`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006027`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ff3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005fe9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005fe9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005f8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005f8a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005fa5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005fa5`

## string_xrefs

- `0x180005fc4`: `Failed to OpenThreadToken due to error %X`
- `0x180006008`: ` Could not set thread token due to error %X`

## pseudocode

```c
__int64 __fastcall SetCurrentThreadToken(HANDLE Token, void **a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  void *v6; // rcx
  signed int v7; // eax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF
  void *Thread; // [rsp+48h] [rbp+20h] BYREF

  Thread = 0;
  TokenHandle = 0;
  Thread = GetCurrentThread();
  if ( !OpenThreadToken(Thread, 0x2004Cu, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Failed to OpenThreadToken due to error %X", v5);
LABEL_5:
    v6 = TokenHandle;
    goto LABEL_11;
  }
  if ( !SetThreadToken(&Thread, Token) )
  {
    v7 = GetLastError();
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L" Could not set thread token due to error %X", v5);
    goto LABEL_5;
  }
  v5 = 0;
  *a2 = TokenHandle;
  v6 = 0;
  TokenHandle = 0;
LABEL_11:
  if ( v6 )
    CloseHandle(v6);
  return v5;
}

```

## disassembly

```asm
0x180005f68  mov     [rsp+arg_0], rbx
0x180005f6d  push    rdi
0x180005f6e  sub     rsp, 20h
0x180005f72  mov     rdi, rdx
0x180005f75  mov     [rsp+28h+Thread], 0
0x180005f7e  mov     rbx, rcx
0x180005f81  mov     [rsp+28h+TokenHandle], 0
0x180005f8a  call    cs:__imp_GetCurrentThread
0x180005f90  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180005f95  xor     r8d, r8d; OpenAsSelf
0x180005f98  mov     rcx, rax; ThreadHandle
0x180005f9b  mov     [rsp+28h+Thread], rax
0x180005fa0  mov     edx, 2004Ch; DesiredAccess
0x180005fa5  call    cs:__imp_OpenThreadToken
0x180005fab  test    eax, eax
0x180005fad  jnz     short loc_180005FE1
0x180005faf  call    cs:__imp_GetLastError
0x180005fb5  mov     ebx, eax
0x180005fb7  test    eax, eax
0x180005fb9  jle     short loc_180005FC4
0x180005fbb  movzx   ebx, ax
0x180005fbe  or      ebx, 80070000h
0x180005fc4  lea     rdx, aFailedToOpenth; "Failed to OpenThreadToken due to error "...
0x180005fcb  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180005fd2  mov     r8d, ebx
0x180005fd5  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180005fda  mov     rcx, [rsp+28h+TokenHandle]
0x180005fdf  jmp     short loc_180006022
0x180005fe1  mov     rdx, rbx; Token
0x180005fe4  lea     rcx, [rsp+28h+Thread]; Thread
0x180005fe9  call    cs:__imp_SetThreadToken
0x180005fef  test    eax, eax
0x180005ff1  jnz     short loc_180006011
0x180005ff3  call    cs:__imp_GetLastError
0x180005ff9  mov     ebx, eax
0x180005ffb  test    eax, eax
0x180005ffd  jle     short loc_180006008
0x180005fff  movzx   ebx, ax
0x180006002  or      ebx, 80070000h
0x180006008  lea     rdx, aCouldNotSetThr; " Could not set thread token due to erro"...
0x18000600f  jmp     short loc_180005FCB
0x180006011  mov     rcx, [rsp+28h+TokenHandle]
0x180006016  xor     ebx, ebx
0x180006018  mov     [rdi], rcx
0x18000601b  xor     ecx, ecx; hObject
0x18000601d  mov     [rsp+28h+TokenHandle], rcx
0x180006022  test    rcx, rcx
0x180006025  jz      short loc_18000602D
0x180006027  call    cs:__imp_CloseHandle
0x18000602d  mov     eax, ebx
0x18000602f  mov     rbx, [rsp+28h+arg_0]
0x180006034  add     rsp, 20h
0x180006038  pop     rdi
0x180006039  retn
```
