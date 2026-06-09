# EnableThreadSecurityPrivilege(void * *)

- ea: `0x18001aeb8`
- end: `0x18001b144`
- name: `?EnableThreadSecurityPrivilege@@YAJPEAPEAX@Z`
- size: `652`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ce20`

## callees

- `0x180003cf0`
- `0x18001aeb8`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001af92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001af92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001af09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001af09`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b0be`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b0be`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001afa1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001afa1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001af23`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001af23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b105`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b123`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b105`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b123`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001b087`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001b087`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001afea`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001afea`
- `ADVAPI32!LookupPrivilegeValueA` at `0x18001b028`
- `ADVAPI32!LookupPrivilegeValueA` at `0x18001b028`

## string_xrefs

- `0x18001af5b`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`
- `0x18001af62`: `EnableThreadSecurityPrivilege`
- `0x18001b0a6`: `Unable to enable SeSecurityPrivilege`
- `0x18001afc0`: `Failed to open process token`
- `0x18001b047`: `Could not look up the LUID for SeSecurityPrivilege`
- `0x18001af49`: `Failed to open thread token`
- `0x18001b0dd`: `Unable to set thread token`
- `0x18001b009`: `Failed to duplicate the token`
- `0x18001b021`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 __fastcall EnableThreadSecurityPrivilege(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  const wchar_t *v5; // rax
  __int64 v6; // r9
  void *v7; // rcx
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  PHANDLE phNewToken; // [rsp+28h] [rbp-21h]
  void *TokenHandle; // [rsp+40h] [rbp-9h] BYREF
  HANDLE Token; // [rsp+48h] [rbp-1h] BYREF
  HANDLE hExistingToken; // [rsp+50h] [rbp+7h] BYREF
  _LUID Luid; // [rsp+58h] [rbp+Fh] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+60h] [rbp+17h] BYREF

  TokenHandle = 0;
  NewState = 0;
  hExistingToken = 0;
  Token = 0;
  Luid = 0;
  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 6u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v5 = L"Failed to open thread token";
      v6 = 48;
LABEL_6:
      LODWORD(phNewToken) = v4;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
        v6,
        L"EnableThreadSecurityPrivilege",
        phNewToken,
        v5);
      goto LABEL_30;
    }
  }
  v7 = TokenHandle;
  if ( !TokenHandle )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 2u, &hExistingToken) )
    {
      v9 = GetLastError();
      v4 = v9;
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
      v5 = L"Failed to open process token";
      v6 = 67;
      goto LABEL_6;
    }
    v7 = hExistingToken;
  }
  if ( !DuplicateTokenEx(v7, 0x24u, 0, SecurityImpersonation, TokenImpersonation, &Token) )
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    v5 = L"Failed to duplicate the token";
    v6 = 87;
    goto LABEL_6;
  }
  if ( !LookupPrivilegeValueA(0, "SeSecurityPrivilege", &Luid) )
  {
    v11 = GetLastError();
    v4 = v11;
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    v5 = L"Could not look up the LUID for SeSecurityPrivilege";
    v6 = 96;
    goto LABEL_6;
  }
  NewState.Privileges[0].Luid = Luid;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  if ( !AdjustTokenPrivileges(Token, 0, &NewState, 0, 0, 0) )
  {
    v12 = GetLastError();
    v4 = v12;
    if ( v12 > 0 )
      v4 = (unsigned __int16)v12 | 0x80070000;
    v5 = L"Unable to enable SeSecurityPrivilege";
    v6 = 116;
    goto LABEL_6;
  }
  if ( !SetThreadToken(0, Token) )
  {
    v13 = GetLastError();
    v4 = v13;
    if ( v13 > 0 )
      v4 = (unsigned __int16)v13 | 0x80070000;
    v5 = L"Unable to set thread token";
    v6 = 123;
    goto LABEL_6;
  }
  v4 = 0;
  *a1 = TokenHandle;
  TokenHandle = 0;
LABEL_30:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( hExistingToken )
    CloseHandle(hExistingToken);
  if ( Token )
    CloseHandle(Token);
  return v4;
}

```

## disassembly

```asm
0x18001aeb8  push    rbp
0x18001aeba  push    rbx
0x18001aebb  push    rdi
0x18001aebc  push    r14
0x18001aebe  lea     rbp, [rsp-3Fh]
0x18001aec3  sub     rsp, 88h
0x18001aeca  mov     rax, cs:__security_cookie
0x18001aed1  xor     rax, rsp
0x18001aed4  mov     [rbp+57h+var_30], rax
0x18001aed8  xorps   xmm0, xmm0
0x18001aedb  mov     [rbp+57h+TokenHandle], 0
0x18001aee3  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x18001aee7  mov     rdi, rcx
0x18001aeea  mov     [rbp+57h+hExistingToken], 0
0x18001aef2  mov     [rbp+57h+Token], 0
0x18001aefa  mov     qword ptr [rbp+57h+Luid.LowPart], 0
0x18001af02  mov     qword ptr [rcx], 0
0x18001af09  call    cs:__imp_GetCurrentThread
0x18001af0f  mov     r14d, 1
0x18001af15  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001af19  mov     rcx, rax; ThreadHandle
0x18001af1c  mov     r8d, r14d; OpenAsSelf
0x18001af1f  lea     edx, [r14+5]; DesiredAccess
0x18001af23  call    cs:__imp_OpenThreadToken
0x18001af29  test    eax, eax
0x18001af2b  jnz     short loc_18001AF84
0x18001af2d  call    cs:__imp_GetLastError
0x18001af33  mov     ebx, eax
0x18001af35  cmp     eax, 3F0h
0x18001af3a  jz      short loc_18001AF84
0x18001af3c  test    eax, eax
0x18001af3e  jle     short loc_18001AF49
0x18001af40  movzx   ebx, ax
0x18001af43  or      ebx, 80070000h
0x18001af49  lea     rax, aFailedToOpenTh; "Failed to open thread token"
0x18001af50  mov     r9d, 30h ; '0'
0x18001af56  mov     [rsp+0A0h+var_70], rax
0x18001af5b  lea     r8, aComComplusDtcS_12; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x18001af62  lea     rax, aEnablethreadse; "EnableThreadSecurityPrivilege"
0x18001af69  mov     dword ptr [rsp+0A0h+phNewToken], ebx
0x18001af6d  mov     edx, r14d
0x18001af70  mov     qword ptr [rsp+0A0h+TokenType], rax
0x18001af75  mov     ecx, 7
0x18001af7a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001af7f  jmp     loc_18001B0FC
0x18001af84  mov     rcx, [rbp+57h+TokenHandle]
0x18001af88  mov     ebx, 2
0x18001af8d  test    rcx, rcx
0x18001af90  jnz     short loc_18001AFD3
0x18001af92  call    cs:__imp_GetCurrentProcess
0x18001af98  lea     r8, [rbp+57h+hExistingToken]; TokenHandle
0x18001af9c  mov     edx, ebx; DesiredAccess
0x18001af9e  mov     rcx, rax; ProcessHandle
0x18001afa1  call    cs:__imp_OpenProcessToken
0x18001afa7  test    eax, eax
0x18001afa9  jnz     short loc_18001AFCF
0x18001afab  call    cs:__imp_GetLastError
0x18001afb1  mov     ebx, eax
0x18001afb3  test    eax, eax
0x18001afb5  jle     short loc_18001AFC0
0x18001afb7  movzx   ebx, ax
0x18001afba  or      ebx, 80070000h
0x18001afc0  lea     rax, aFailedToOpenPr; "Failed to open process token"
0x18001afc7  mov     r9d, 43h ; 'C'
0x18001afcd  jmp     short loc_18001AF56
0x18001afcf  mov     rcx, [rbp+57h+hExistingToken]; hExistingToken
0x18001afd3  xor     r8d, r8d; lpTokenAttributes
0x18001afd6  lea     rax, [rbp+57h+Token]
0x18001afda  mov     [rsp+0A0h+phNewToken], rax; phNewToken
0x18001afdf  mov     r9d, ebx; ImpersonationLevel
0x18001afe2  mov     [rsp+0A0h+TokenType], ebx; TokenType
0x18001afe6  lea     edx, [r8+24h]; dwDesiredAccess
0x18001afea  call    cs:__imp_DuplicateTokenEx
0x18001aff0  test    eax, eax
0x18001aff2  jnz     short loc_18001B01B
0x18001aff4  call    cs:__imp_GetLastError
0x18001affa  mov     ebx, eax
0x18001affc  test    eax, eax
0x18001affe  jle     short loc_18001B009
0x18001b000  movzx   ebx, ax
0x18001b003  or      ebx, 80070000h
0x18001b009  lea     rax, aFailedToDuplic; "Failed to duplicate the token"
0x18001b010  mov     r9d, 57h ; 'W'
0x18001b016  jmp     loc_18001AF56
0x18001b01b  lea     r8, [rbp+57h+Luid]; lpLuid
0x18001b01f  xor     ecx, ecx; lpSystemName
0x18001b021  lea     rdx, Name; "SeSecurityPrivilege"
0x18001b028  call    cs:__imp_LookupPrivilegeValueA
0x18001b02e  test    eax, eax
0x18001b030  jnz     short loc_18001B059
0x18001b032  call    cs:__imp_GetLastError
0x18001b038  mov     ebx, eax
0x18001b03a  test    eax, eax
0x18001b03c  jle     short loc_18001B047
0x18001b03e  movzx   ebx, ax
0x18001b041  or      ebx, 80070000h
0x18001b047  lea     rax, aCouldNotLookUp; "Could not look up the LUID for SeSecuri"...
0x18001b04e  mov     r9d, 60h ; '`'
0x18001b054  jmp     loc_18001AF56
0x18001b059  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x18001b05d  lea     r8, [rbp+57h+NewState]; NewState
0x18001b061  mov     rcx, [rbp+57h+Token]; TokenHandle
0x18001b065  xor     r9d, r9d; BufferLength
0x18001b068  mov     [rsp+0A0h+phNewToken], 0; ReturnLength
0x18001b071  xor     edx, edx; DisableAllPrivileges
0x18001b073  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x18001b077  mov     [rbp+57h+NewState.PrivilegeCount], r14d
0x18001b07b  mov     [rbp+57h+NewState.Privileges.Attributes], ebx
0x18001b07e  mov     qword ptr [rsp+0A0h+TokenType], 0; PreviousState
0x18001b087  call    cs:__imp_AdjustTokenPrivileges
0x18001b08d  test    eax, eax
0x18001b08f  jnz     short loc_18001B0B8
0x18001b091  call    cs:__imp_GetLastError
0x18001b097  mov     ebx, eax
0x18001b099  test    eax, eax
0x18001b09b  jle     short loc_18001B0A6
0x18001b09d  movzx   ebx, ax
0x18001b0a0  or      ebx, 80070000h
0x18001b0a6  lea     rax, aUnableToEnable; "Unable to enable SeSecurityPrivilege"
0x18001b0ad  mov     r9d, 74h ; 't'
0x18001b0b3  jmp     loc_18001AF56
0x18001b0b8  mov     rdx, [rbp+57h+Token]; Token
0x18001b0bc  xor     ecx, ecx; Thread
0x18001b0be  call    cs:__imp_SetThreadToken
0x18001b0c4  test    eax, eax
0x18001b0c6  jnz     short loc_18001B0EF
0x18001b0c8  call    cs:__imp_GetLastError
0x18001b0ce  mov     ebx, eax
0x18001b0d0  test    eax, eax
0x18001b0d2  jle     short loc_18001B0DD
0x18001b0d4  movzx   ebx, ax
0x18001b0d7  or      ebx, 80070000h
0x18001b0dd  lea     rax, aUnableToSetThr; "Unable to set thread token"
0x18001b0e4  mov     r9d, 7Bh ; '{'
0x18001b0ea  jmp     loc_18001AF56
0x18001b0ef  mov     rax, [rbp+57h+TokenHandle]
0x18001b0f3  xor     ebx, ebx
0x18001b0f5  mov     [rdi], rax
0x18001b0f8  mov     [rbp+57h+TokenHandle], rbx
0x18001b0fc  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001b100  test    rcx, rcx
0x18001b103  jz      short loc_18001B10B
0x18001b105  call    cs:__imp_CloseHandle
0x18001b10b  mov     rcx, [rbp+57h+hExistingToken]; hObject
0x18001b10f  test    rcx, rcx
0x18001b112  jz      short loc_18001B11A
0x18001b114  call    cs:__imp_CloseHandle
0x18001b11a  mov     rcx, [rbp+57h+Token]; hObject
0x18001b11e  test    rcx, rcx
0x18001b121  jz      short loc_18001B129
0x18001b123  call    cs:__imp_CloseHandle
0x18001b129  mov     eax, ebx
0x18001b12b  mov     rcx, [rbp+57h+var_30]
0x18001b12f  xor     rcx, rsp; StackCookie
0x18001b132  call    __security_check_cookie
0x18001b137  add     rsp, 88h
0x18001b13e  pop     r14
0x18001b140  pop     rdi
0x18001b141  pop     rbx
0x18001b142  pop     rbp
0x18001b143  retn
```
