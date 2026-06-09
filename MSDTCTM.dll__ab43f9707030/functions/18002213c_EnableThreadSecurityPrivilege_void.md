# EnableThreadSecurityPrivilege(void * *)

- ea: `0x18002213c`
- end: `0x1800223c8`
- name: `?EnableThreadSecurityPrivilege@@YAJPEAPEAX@Z`
- size: `652`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023d98`

## callees

- `0x1800063b0`
- `0x18002213c`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022225`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022225`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800221a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800221a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002218d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002218d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022342`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022342`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002222f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002234c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002222f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002234c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800223a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800223a7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002226e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002226e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002230b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002230b`
- `ADVAPI32!LookupPrivilegeValueA` at `0x1800222ac`
- `ADVAPI32!LookupPrivilegeValueA` at `0x1800222ac`

## string_xrefs

- `0x1800221df`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`
- `0x1800221e6`: `EnableThreadSecurityPrivilege`
- `0x18002232a`: `Unable to enable SeSecurityPrivilege`
- `0x180022244`: `Failed to open process token`
- `0x1800222cb`: `Could not look up the LUID for SeSecurityPrivilege`
- `0x1800221cd`: `Failed to open thread token`
- `0x180022361`: `Unable to set thread token`
- `0x18002228d`: `Failed to duplicate the token`
- `0x1800222a5`: `SeSecurityPrivilege`

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
0x18002213c  push    rbp
0x18002213e  push    rbx
0x18002213f  push    rdi
0x180022140  push    r14
0x180022142  lea     rbp, [rsp-3Fh]
0x180022147  sub     rsp, 88h
0x18002214e  mov     rax, cs:__security_cookie
0x180022155  xor     rax, rsp
0x180022158  mov     [rbp+57h+var_30], rax
0x18002215c  xorps   xmm0, xmm0
0x18002215f  mov     [rbp+57h+TokenHandle], 0
0x180022167  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x18002216b  mov     rdi, rcx
0x18002216e  mov     [rbp+57h+hExistingToken], 0
0x180022176  mov     [rbp+57h+Token], 0
0x18002217e  mov     qword ptr [rbp+57h+Luid.LowPart], 0
0x180022186  mov     qword ptr [rcx], 0
0x18002218d  call    cs:__imp_GetCurrentThread
0x180022193  mov     r14d, 1
0x180022199  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002219d  mov     rcx, rax; ThreadHandle
0x1800221a0  mov     r8d, r14d; OpenAsSelf
0x1800221a3  lea     edx, [r14+5]; DesiredAccess
0x1800221a7  call    cs:__imp_OpenThreadToken
0x1800221ad  test    eax, eax
0x1800221af  jnz     short loc_180022208
0x1800221b1  call    cs:__imp_GetLastError
0x1800221b7  mov     ebx, eax
0x1800221b9  cmp     eax, 3F0h
0x1800221be  jz      short loc_180022208
0x1800221c0  test    eax, eax
0x1800221c2  jle     short loc_1800221CD
0x1800221c4  movzx   ebx, ax
0x1800221c7  or      ebx, 80070000h
0x1800221cd  lea     rax, aFailedToOpenTh; "Failed to open thread token"
0x1800221d4  mov     r9d, 30h ; '0'
0x1800221da  mov     [rsp+0A0h+var_70], rax
0x1800221df  lea     r8, aComComplusDtcS_8; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x1800221e6  lea     rax, aEnablethreadse; "EnableThreadSecurityPrivilege"
0x1800221ed  mov     dword ptr [rsp+0A0h+phNewToken], ebx
0x1800221f1  mov     edx, r14d
0x1800221f4  mov     qword ptr [rsp+0A0h+TokenType], rax
0x1800221f9  mov     ecx, 7
0x1800221fe  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022203  jmp     loc_180022380
0x180022208  mov     rcx, [rbp+57h+TokenHandle]
0x18002220c  mov     ebx, 2
0x180022211  test    rcx, rcx
0x180022214  jnz     short loc_180022257
0x180022216  call    cs:__imp_GetCurrentProcess
0x18002221c  lea     r8, [rbp+57h+hExistingToken]; TokenHandle
0x180022220  mov     edx, ebx; DesiredAccess
0x180022222  mov     rcx, rax; ProcessHandle
0x180022225  call    cs:__imp_OpenProcessToken
0x18002222b  test    eax, eax
0x18002222d  jnz     short loc_180022253
0x18002222f  call    cs:__imp_GetLastError
0x180022235  mov     ebx, eax
0x180022237  test    eax, eax
0x180022239  jle     short loc_180022244
0x18002223b  movzx   ebx, ax
0x18002223e  or      ebx, 80070000h
0x180022244  lea     rax, aFailedToOpenPr; "Failed to open process token"
0x18002224b  mov     r9d, 43h ; 'C'
0x180022251  jmp     short loc_1800221DA
0x180022253  mov     rcx, [rbp+57h+hExistingToken]; hExistingToken
0x180022257  xor     r8d, r8d; lpTokenAttributes
0x18002225a  lea     rax, [rbp+57h+Token]
0x18002225e  mov     [rsp+0A0h+phNewToken], rax; phNewToken
0x180022263  mov     r9d, ebx; ImpersonationLevel
0x180022266  mov     [rsp+0A0h+TokenType], ebx; TokenType
0x18002226a  lea     edx, [r8+24h]; dwDesiredAccess
0x18002226e  call    cs:__imp_DuplicateTokenEx
0x180022274  test    eax, eax
0x180022276  jnz     short loc_18002229F
0x180022278  call    cs:__imp_GetLastError
0x18002227e  mov     ebx, eax
0x180022280  test    eax, eax
0x180022282  jle     short loc_18002228D
0x180022284  movzx   ebx, ax
0x180022287  or      ebx, 80070000h
0x18002228d  lea     rax, aFailedToDuplic; "Failed to duplicate the token"
0x180022294  mov     r9d, 57h ; 'W'
0x18002229a  jmp     loc_1800221DA
0x18002229f  lea     r8, [rbp+57h+Luid]; lpLuid
0x1800222a3  xor     ecx, ecx; lpSystemName
0x1800222a5  lea     rdx, Name; "SeSecurityPrivilege"
0x1800222ac  call    cs:__imp_LookupPrivilegeValueA
0x1800222b2  test    eax, eax
0x1800222b4  jnz     short loc_1800222DD
0x1800222b6  call    cs:__imp_GetLastError
0x1800222bc  mov     ebx, eax
0x1800222be  test    eax, eax
0x1800222c0  jle     short loc_1800222CB
0x1800222c2  movzx   ebx, ax
0x1800222c5  or      ebx, 80070000h
0x1800222cb  lea     rax, aCouldNotLookUp; "Could not look up the LUID for SeSecuri"...
0x1800222d2  mov     r9d, 60h ; '`'
0x1800222d8  jmp     loc_1800221DA
0x1800222dd  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x1800222e1  lea     r8, [rbp+57h+NewState]; NewState
0x1800222e5  mov     rcx, [rbp+57h+Token]; TokenHandle
0x1800222e9  xor     r9d, r9d; BufferLength
0x1800222ec  mov     [rsp+0A0h+phNewToken], 0; ReturnLength
0x1800222f5  xor     edx, edx; DisableAllPrivileges
0x1800222f7  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x1800222fb  mov     [rbp+57h+NewState.PrivilegeCount], r14d
0x1800222ff  mov     [rbp+57h+NewState.Privileges.Attributes], ebx
0x180022302  mov     qword ptr [rsp+0A0h+TokenType], 0; PreviousState
0x18002230b  call    cs:__imp_AdjustTokenPrivileges
0x180022311  test    eax, eax
0x180022313  jnz     short loc_18002233C
0x180022315  call    cs:__imp_GetLastError
0x18002231b  mov     ebx, eax
0x18002231d  test    eax, eax
0x18002231f  jle     short loc_18002232A
0x180022321  movzx   ebx, ax
0x180022324  or      ebx, 80070000h
0x18002232a  lea     rax, aUnableToEnable; "Unable to enable SeSecurityPrivilege"
0x180022331  mov     r9d, 74h ; 't'
0x180022337  jmp     loc_1800221DA
0x18002233c  mov     rdx, [rbp+57h+Token]; Token
0x180022340  xor     ecx, ecx; Thread
0x180022342  call    cs:__imp_SetThreadToken
0x180022348  test    eax, eax
0x18002234a  jnz     short loc_180022373
0x18002234c  call    cs:__imp_GetLastError
0x180022352  mov     ebx, eax
0x180022354  test    eax, eax
0x180022356  jle     short loc_180022361
0x180022358  movzx   ebx, ax
0x18002235b  or      ebx, 80070000h
0x180022361  lea     rax, aUnableToSetThr; "Unable to set thread token"
0x180022368  mov     r9d, 7Bh ; '{'
0x18002236e  jmp     loc_1800221DA
0x180022373  mov     rax, [rbp+57h+TokenHandle]
0x180022377  xor     ebx, ebx
0x180022379  mov     [rdi], rax
0x18002237c  mov     [rbp+57h+TokenHandle], rbx
0x180022380  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180022384  test    rcx, rcx
0x180022387  jz      short loc_18002238F
0x180022389  call    cs:__imp_CloseHandle
0x18002238f  mov     rcx, [rbp+57h+hExistingToken]; hObject
0x180022393  test    rcx, rcx
0x180022396  jz      short loc_18002239E
0x180022398  call    cs:__imp_CloseHandle
0x18002239e  mov     rcx, [rbp+57h+Token]; hObject
0x1800223a2  test    rcx, rcx
0x1800223a5  jz      short loc_1800223AD
0x1800223a7  call    cs:__imp_CloseHandle
0x1800223ad  mov     eax, ebx
0x1800223af  mov     rcx, [rbp+57h+var_30]
0x1800223b3  xor     rcx, rsp; StackCookie
0x1800223b6  call    __security_check_cookie
0x1800223bb  add     rsp, 88h
0x1800223c2  pop     r14
0x1800223c4  pop     rdi
0x1800223c5  pop     rbx
0x1800223c6  pop     rbp
0x1800223c7  retn
```
