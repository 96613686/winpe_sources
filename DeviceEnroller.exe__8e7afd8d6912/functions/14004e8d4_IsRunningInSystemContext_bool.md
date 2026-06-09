# IsRunningInSystemContext(bool &)

- ea: `0x14004e8d4`
- end: `0x14004e9f2`
- name: `?IsRunningInSystemContext@@YAJAEA_N@Z`
- size: `286`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004daa0`
- `0x14004e740`

## callees

- `0x14004e4bc`
- `0x14004e8d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004e98d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004e98d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004e9bc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004e9bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e90e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e99c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e90e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e99c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14004e904`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14004e904`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14004e91b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14004e91b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14004e92d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14004e92d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14004e8ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14004e8ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e9e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e9e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004e9cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004e9cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14004e978`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14004e978`

## pseudocode

```c
__int64 __fastcall IsRunningInSystemContext(bool *a1)
{
  unsigned int TokenSids; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v6; // eax
  PSID Sid; // [rsp+40h] [rbp+20h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+30h] BYREF

  TokenSids = 0;
  TokenHandle = 0;
  Sid = 0;
  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) && GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      LastError = GetLastError();
      TokenSids = LastError;
      if ( LastError > 0 )
        TokenSids = (unsigned __int16)LastError | 0x80070000;
    }
  }
  StringSid = 0;
  if ( TokenHandle )
  {
    TokenSids = GetTokenSids(TokenHandle, &Sid);
    if ( !TokenSids )
    {
      if ( ConvertSidToStringSidW(Sid, &StringSid) )
      {
        if ( !(unsigned int)_o__wcsicmp(StringSid, L"S-1-5-18") )
          *a1 = 1;
      }
      else
      {
        v6 = GetLastError();
        TokenSids = v6;
        if ( v6 > 0 )
          TokenSids = (unsigned __int16)v6 | 0x80070000;
      }
    }
    if ( Sid )
      free(Sid);
    if ( StringSid )
    {
      LocalFree(StringSid);
      StringSid = 0;
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
  }
  return TokenSids;
}

```

## disassembly

```asm
0x14004e8d4  push    rbp
0x14004e8d6  push    rbx
0x14004e8d7  push    rsi
0x14004e8d8  mov     rbp, rsp
0x14004e8db  sub     rsp, 20h
0x14004e8df  xor     ebx, ebx
0x14004e8e1  mov     rsi, rcx
0x14004e8e4  mov     [rbp+TokenHandle], rbx
0x14004e8e8  mov     [rbp+Sid], rbx
0x14004e8ec  mov     [rcx], bl
0x14004e8ee  call    cs:__imp_GetCurrentThread
0x14004e8f4  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14004e8f8  mov     edx, 20008h; DesiredAccess
0x14004e8fd  mov     rcx, rax; ThreadHandle
0x14004e900  lea     r8d, [rbx+1]; OpenAsSelf
0x14004e904  call    cs:__imp_OpenThreadToken
0x14004e90a  test    eax, eax
0x14004e90c  jnz     short loc_14004E94C
0x14004e90e  call    cs:__imp_GetLastError
0x14004e914  cmp     eax, 3F0h
0x14004e919  jnz     short loc_14004E94C
0x14004e91b  call    cs:__imp_GetCurrentProcess
0x14004e921  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14004e925  mov     edx, 20008h; DesiredAccess
0x14004e92a  mov     rcx, rax; ProcessHandle
0x14004e92d  call    cs:__imp_OpenProcessToken
0x14004e933  test    eax, eax
0x14004e935  jnz     short loc_14004E94C
0x14004e937  call    cs:__imp_GetLastError
0x14004e93d  mov     ebx, eax
0x14004e93f  test    eax, eax
0x14004e941  jle     short loc_14004E94C
0x14004e943  movzx   ebx, ax
0x14004e946  or      ebx, 80070000h
0x14004e94c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14004e950  mov     [rbp+StringSid], 0
0x14004e958  test    rcx, rcx
0x14004e95b  jz      loc_14004E9E8
0x14004e961  lea     rdx, [rbp+Sid]; void **
0x14004e965  call    ?GetTokenSids@@YAJPEAXPEAPEAX@Z; GetTokenSids(void *,void * *)
0x14004e96a  mov     ebx, eax
0x14004e96c  test    eax, eax
0x14004e96e  jnz     short loc_14004E9B1
0x14004e970  mov     rcx, [rbp+Sid]; Sid
0x14004e974  lea     rdx, [rbp+StringSid]; StringSid
0x14004e978  call    cs:__imp_ConvertSidToStringSidW
0x14004e97e  test    eax, eax
0x14004e980  jz      short loc_14004E99C
0x14004e982  mov     rcx, [rbp+StringSid]
0x14004e986  lea     rdx, aS1518; "S-1-5-18"
0x14004e98d  call    cs:__imp__o__wcsicmp
0x14004e993  test    eax, eax
0x14004e995  jnz     short loc_14004E9B1
0x14004e997  mov     byte ptr [rsi], 1
0x14004e99a  jmp     short loc_14004E9B1
0x14004e99c  call    cs:__imp_GetLastError
0x14004e9a2  mov     ebx, eax
0x14004e9a4  test    eax, eax
0x14004e9a6  jle     short loc_14004E9B1
0x14004e9a8  movzx   ebx, ax
0x14004e9ab  or      ebx, 80070000h
0x14004e9b1  cmp     [rbp+Sid], 0
0x14004e9b6  jz      short loc_14004E9C2
0x14004e9b8  mov     rcx, [rbp+Sid]; Block
0x14004e9bc  call    cs:__imp_free
0x14004e9c2  mov     rcx, [rbp+StringSid]; hMem
0x14004e9c6  test    rcx, rcx
0x14004e9c9  jz      short loc_14004E9D9
0x14004e9cb  call    cs:__imp_LocalFree
0x14004e9d1  mov     [rbp+StringSid], 0
0x14004e9d9  mov     rcx, [rbp+TokenHandle]; hObject
0x14004e9dd  test    rcx, rcx
0x14004e9e0  jz      short loc_14004E9E8
0x14004e9e2  call    cs:__imp_CloseHandle
0x14004e9e8  mov     eax, ebx
0x14004e9ea  add     rsp, 20h
0x14004e9ee  pop     rsi
0x14004e9ef  pop     rbx
0x14004e9f0  pop     rbp
0x14004e9f1  retn
```
