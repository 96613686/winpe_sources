# IsRunningInSystemContext(bool &)

- ea: `0x18012bf94`
- end: `0x18012c0b2`
- name: `?IsRunningInSystemContext@@YAJAEA_N@Z`
- size: `286`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012b278`
- `0x18012be00`

## callees

- `0x18012bb7c`
- `0x18012bf94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012c04d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012c04d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18012c07c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18012c07c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bfce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c05c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bfce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c05c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18012bfc4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18012bfc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18012bfae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18012bfae`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18012bfed`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18012bfed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18012bfdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18012bfdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012c0a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012c0a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012c08b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012c08b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18012c038`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18012c038`

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
0x18012bf94  push    rbp
0x18012bf96  push    rbx
0x18012bf97  push    rsi
0x18012bf98  mov     rbp, rsp
0x18012bf9b  sub     rsp, 20h
0x18012bf9f  xor     ebx, ebx
0x18012bfa1  mov     rsi, rcx
0x18012bfa4  mov     [rbp+TokenHandle], rbx
0x18012bfa8  mov     [rbp+Sid], rbx
0x18012bfac  mov     [rcx], bl
0x18012bfae  call    cs:__imp_GetCurrentThread
0x18012bfb4  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18012bfb8  mov     edx, 20008h; DesiredAccess
0x18012bfbd  mov     rcx, rax; ThreadHandle
0x18012bfc0  lea     r8d, [rbx+1]; OpenAsSelf
0x18012bfc4  call    cs:__imp_OpenThreadToken
0x18012bfca  test    eax, eax
0x18012bfcc  jnz     short loc_18012C00C
0x18012bfce  call    cs:__imp_GetLastError
0x18012bfd4  cmp     eax, 3F0h
0x18012bfd9  jnz     short loc_18012C00C
0x18012bfdb  call    cs:__imp_GetCurrentProcess
0x18012bfe1  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18012bfe5  mov     edx, 20008h; DesiredAccess
0x18012bfea  mov     rcx, rax; ProcessHandle
0x18012bfed  call    cs:__imp_OpenProcessToken
0x18012bff3  test    eax, eax
0x18012bff5  jnz     short loc_18012C00C
0x18012bff7  call    cs:__imp_GetLastError
0x18012bffd  mov     ebx, eax
0x18012bfff  test    eax, eax
0x18012c001  jle     short loc_18012C00C
0x18012c003  movzx   ebx, ax
0x18012c006  or      ebx, 80070000h
0x18012c00c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18012c010  mov     [rbp+StringSid], 0
0x18012c018  test    rcx, rcx
0x18012c01b  jz      loc_18012C0A8
0x18012c021  lea     rdx, [rbp+Sid]; void **
0x18012c025  call    ?GetTokenSids@@YAJPEAXPEAPEAX@Z; GetTokenSids(void *,void * *)
0x18012c02a  mov     ebx, eax
0x18012c02c  test    eax, eax
0x18012c02e  jnz     short loc_18012C071
0x18012c030  mov     rcx, [rbp+Sid]; Sid
0x18012c034  lea     rdx, [rbp+StringSid]; StringSid
0x18012c038  call    cs:__imp_ConvertSidToStringSidW
0x18012c03e  test    eax, eax
0x18012c040  jz      short loc_18012C05C
0x18012c042  mov     rcx, [rbp+StringSid]
0x18012c046  lea     rdx, aS1518; "S-1-5-18"
0x18012c04d  call    cs:__imp__o__wcsicmp
0x18012c053  test    eax, eax
0x18012c055  jnz     short loc_18012C071
0x18012c057  mov     byte ptr [rsi], 1
0x18012c05a  jmp     short loc_18012C071
0x18012c05c  call    cs:__imp_GetLastError
0x18012c062  mov     ebx, eax
0x18012c064  test    eax, eax
0x18012c066  jle     short loc_18012C071
0x18012c068  movzx   ebx, ax
0x18012c06b  or      ebx, 80070000h
0x18012c071  cmp     [rbp+Sid], 0
0x18012c076  jz      short loc_18012C082
0x18012c078  mov     rcx, [rbp+Sid]; Block
0x18012c07c  call    cs:__imp_free
0x18012c082  mov     rcx, [rbp+StringSid]; hMem
0x18012c086  test    rcx, rcx
0x18012c089  jz      short loc_18012C099
0x18012c08b  call    cs:__imp_LocalFree
0x18012c091  mov     [rbp+StringSid], 0
0x18012c099  mov     rcx, [rbp+TokenHandle]; hObject
0x18012c09d  test    rcx, rcx
0x18012c0a0  jz      short loc_18012C0A8
0x18012c0a2  call    cs:__imp_CloseHandle
0x18012c0a8  mov     eax, ebx
0x18012c0aa  add     rsp, 20h
0x18012c0ae  pop     rsi
0x18012c0af  pop     rbx
0x18012c0b0  pop     rbp
0x18012c0b1  retn
```
