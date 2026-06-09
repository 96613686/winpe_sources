# ThisUsersSID

- ea: `0x18001612c`
- end: `0x1800161e5`
- name: `ThisUsersSID`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180016098`
- `0x180017ef4`

## callees

- `0x18001612c`
- `0x1800161ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016149`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016149`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001615e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001615e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016177`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016177`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180016188`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180016188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044482`

## pseudocode

```c
__int64 __fastcall ThisUsersSID(LPWSTR *a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  HANDLE CurrentProcess; // rax
  LPWSTR TokenSID; // rax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
LABEL_4:
    TokenSID = GetTokenSID(TokenHandle);
    *a1 = TokenSID;
    v4 = 0;
    if ( !TokenSID )
      v4 = -2147024882;
    goto LABEL_10;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_4;
    LastError = GetLastError();
    v4 = LastError;
  }
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x18001612c  mov     [rsp+arg_0], rbx
0x180016131  mov     [rsp+arg_10], rsi
0x180016136  push    rdi
0x180016137  sub     rsp, 20h
0x18001613b  mov     rdi, rcx
0x18001613e  mov     [rsp+28h+TokenHandle], 0
0x180016147  xor     esi, esi
0x180016149  call    cs:__imp_GetCurrentThread
0x18001614f  mov     rcx, rax; ThreadHandle
0x180016152  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180016157  lea     edx, [rsi+8]; DesiredAccess
0x18001615a  lea     r8d, [rsi+1]; OpenAsSelf
0x18001615e  call    cs:__imp_OpenThreadToken
0x180016164  test    eax, eax
0x180016166  jnz     short loc_180016192
0x180016168  call    cs:__imp_GetLastError
0x18001616e  mov     ebx, eax
0x180016170  cmp     eax, 3F0h
0x180016175  jnz     short loc_1800161B6
0x180016177  call    cs:__imp_GetCurrentProcess
0x18001617d  mov     rcx, rax; ProcessHandle
0x180016180  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180016185  lea     edx, [rsi+8]; DesiredAccess
0x180016188  call    cs:__imp_OpenProcessToken
0x18001618e  test    eax, eax
0x180016190  jz      short loc_1800161AE
0x180016192  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180016197  call    ?GetTokenSID@@YAPEAGPEAX@Z; GetTokenSID(void *)
0x18001619c  mov     [rdi], rax
0x18001619f  mov     ebx, esi
0x1800161a1  mov     ecx, 8007000Eh
0x1800161a6  test    rax, rax
0x1800161a9  cmovz   ebx, ecx
0x1800161ac  jmp     short loc_1800161C3
0x1800161ae  call    cs:__imp_GetLastError
0x1800161b4  mov     ebx, eax
0x1800161b6  test    eax, eax
0x1800161b8  jle     short loc_1800161C3
0x1800161ba  movzx   ebx, ax
0x1800161bd  or      ebx, 80070000h
0x1800161c3  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800161c8  test    rcx, rcx
0x1800161cb  jz      short loc_1800161D3
0x1800161cd  call    cs:__imp_CloseHandle
0x1800161d3  mov     eax, ebx
0x1800161d5  mov     rbx, [rsp+28h+arg_0]
0x1800161da  mov     rsi, [rsp+28h+arg_10]
0x1800161df  add     rsp, 20h
0x1800161e3  pop     rdi
0x1800161e4  retn
0x180044470  push    rbp
0x180044472  sub     rsp, 20h
0x180044476  mov     rbp, rdx
0x180044479  mov     rcx, [rbp+38h]; hObject
0x18004447d  test    rcx, rcx
0x180044480  jz      short loc_180044489
0x180044482  call    cs:__imp_CloseHandle
0x180044488  nop
0x180044489  add     rsp, 20h
0x18004448d  pop     rbp
0x18004448e  retn
```
