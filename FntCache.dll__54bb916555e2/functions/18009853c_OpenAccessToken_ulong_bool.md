# OpenAccessToken(ulong,bool)

- ea: `0x18009853c`
- end: `0x1800985f5`
- name: `?OpenAccessToken@@YAPEAXK_N@Z`
- size: `185`
- prototype: `void *__fastcall(unsigned int, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000bd98`

## callees

- `0x1800217ac`
- `0x18002faf0`
- `0x18009853c`
- `0x1800a1558`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800985ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800985ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180098567`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180098567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009854e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009854e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800985da`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800985da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009857b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009857b`

## pseudocode

```c
void *__fastcall OpenAccessToken(__int64 a1, char a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v4; // edx
  HANDLE CurrentProcess; // rax
  int v7; // [rsp+38h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  LOBYTE(v7) = a2;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      else
        v4 = LastError;
      Exception::Exception((Exception *)&v7, v4, LastError);
      LogAndThrow<OSException>(&v7, 0x6E656B6F74LL, 142);
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      OSException::ThrowLastError();
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x18009853c  mov     byte ptr [rsp+arg_8], dl
0x180098540  push    rbx
0x180098541  sub     rsp, 20h
0x180098545  mov     [rsp+28h+TokenHandle], 0
0x18009854e  call    cs:__imp_GetCurrentThread
0x180098554  mov     ebx, 8
0x180098559  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18009855e  mov     rcx, rax; ThreadHandle
0x180098561  mov     edx, ebx; DesiredAccess
0x180098563  lea     r8d, [rbx-7]; OpenAsSelf
0x180098567  call    cs:__imp_OpenThreadToken
0x18009856d  test    eax, eax
0x18009856f  jnz     short loc_1800985EA
0x180098571  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180098576  test    rcx, rcx
0x180098579  jz      short loc_180098581
0x18009857b  call    cs:__imp_CloseHandle
0x180098581  call    cs:__imp_GetLastError
0x180098587  cmp     eax, 3F0h
0x18009858c  jz      short loc_1800985CA
0x18009858e  mov     rbx, 6E656B6F74h
0x180098598  test    eax, eax
0x18009859a  jg      short loc_1800985A0
0x18009859c  mov     edx, eax
0x18009859e  jmp     short loc_1800985A9
0x1800985a0  movzx   edx, ax
0x1800985a3  or      edx, 80070000h; int
0x1800985a9  mov     r8d, eax; unsigned int
0x1800985ac  lea     rcx, [rsp+28h+arg_8]; this
0x1800985b1  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x1800985b6  mov     r8d, 8Eh
0x1800985bc  lea     rcx, [rsp+28h+arg_8]
0x1800985c1  mov     rdx, rbx
0x1800985c4  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x1800985ca  call    cs:__imp_GetCurrentProcess
0x1800985d0  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800985d5  mov     edx, ebx; DesiredAccess
0x1800985d7  mov     rcx, rax; ProcessHandle
0x1800985da  call    cs:__imp_OpenProcessToken
0x1800985e0  test    eax, eax
0x1800985e2  jnz     short loc_1800985EA
0x1800985e4  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x1800985ea  mov     rax, [rsp+28h+TokenHandle]
0x1800985ef  add     rsp, 20h
0x1800985f3  pop     rbx
0x1800985f4  retn
```
