# WxIsSystemService

- ea: `0x1800defdc`
- end: `0x1800df1c2`
- name: `WxIsSystemService`
- size: `486`
- prototype: `__int64 __fastcall(LPBOOL AccessStatus)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800de1c0`
- `0x1800dee34`

## callees

- `0x1800701d0`
- `0x1800defdc`
- `0x18014a7a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df063`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800df02a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800df02a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800df042`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800df042`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800df097`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800df097`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800df085`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800df085`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df18a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df1a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df18a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df1a1`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800df151`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800df151`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800df0eb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800df0eb`

## pseudocode

```c
__int64 __fastcall WxIsSystemService(LPBOOL AccessStatus)
{
  HANDLE CurrentThread; // rax
  signed int v3; // eax
  signed int v4; // ebx
  HANDLE CurrentProcess; // rax
  int v6; // eax
  int v7; // eax
  int LastError; // eax
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  HANDLE hExistingToken; // [rsp+50h] [rbp-19h] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp-11h] BYREF
  DWORD PrivilegeSetLength; // [rsp+5Ch] [rbp-Dh] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-9h] BYREF

  TokenHandle = 0;
  hExistingToken = 0;
  PrivilegeSetLength = 44;
  GrantedAccess = 0;
  *AccessStatus = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
LABEL_18:
    if ( AccessCheck(
           &c_rgbSystemServiceSd,
           TokenHandle,
           1u,
           (PGENERIC_MAPPING)&stru_180226A60,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           AccessStatus) )
    {
      v4 = 0;
    }
    else
    {
      LastError = WxGetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147418113;
    }
    goto LABEL_25;
  }
  if ( GetLastError() == 1008 )
    goto LABEL_6;
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_6:
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x2000Au, &hExistingToken) )
    {
      v6 = WxGetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147418113;
      goto LABEL_25;
    }
    if ( !DuplicateTokenEx(hExistingToken, 0x2000Cu, 0, SecurityIdentification, TokenImpersonation, &TokenHandle) )
    {
      v7 = WxGetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147418113;
      goto LABEL_25;
    }
    goto LABEL_18;
  }
LABEL_25:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( hExistingToken )
    CloseHandle(hExistingToken);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800defdc  push    rbp
0x1800defde  push    rbx
0x1800defdf  push    rdi
0x1800defe0  push    r14
0x1800defe2  lea     rbp, [rsp-3Fh]
0x1800defe7  sub     rsp, 0A8h
0x1800defee  mov     rax, cs:__security_cookie
0x1800deff5  xor     rax, rsp
0x1800deff8  mov     [rbp+57h+var_30], rax
0x1800deffc  mov     rdi, rcx
0x1800defff  mov     [rbp+57h+var_7C], 0
0x1800df006  mov     [rbp+57h+TokenHandle], 0
0x1800df00e  mov     [rbp+57h+hExistingToken], 0
0x1800df016  mov     [rbp+57h+PrivilegeSetLength], 2Ch ; ','
0x1800df01d  mov     [rbp+57h+var_68], 0
0x1800df024  mov     dword ptr [rcx], 0
0x1800df02a  call    cs:__imp_GetCurrentThread
0x1800df030  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800df034  mov     edx, 2000Ch; DesiredAccess
0x1800df039  mov     rcx, rax; ThreadHandle
0x1800df03c  mov     r8d, 1; OpenAsSelf
0x1800df042  call    cs:__imp_OpenThreadToken
0x1800df048  mov     r14d, 80070000h
0x1800df04e  test    eax, eax
0x1800df050  jnz     loc_1800DF119
0x1800df056  call    cs:__imp_GetLastError
0x1800df05c  cmp     eax, 3F0h
0x1800df061  jz      short loc_1800DF085
0x1800df063  call    cs:__imp_GetLastError
0x1800df069  mov     ebx, eax
0x1800df06b  test    eax, eax
0x1800df06d  jle     short loc_1800DF075
0x1800df06f  movzx   ebx, ax
0x1800df072  or      ebx, r14d
0x1800df075  test    ebx, ebx
0x1800df077  jns     short loc_1800DF085
0x1800df079  mov     [rbp+57h+var_7C], 289h
0x1800df080  jmp     loc_1800DF181
0x1800df085  call    cs:__imp_GetCurrentProcess
0x1800df08b  lea     r8, [rbp+57h+hExistingToken]; TokenHandle
0x1800df08f  mov     edx, 2000Ah; DesiredAccess
0x1800df094  mov     rcx, rax; ProcessHandle
0x1800df097  call    cs:__imp_OpenProcessToken
0x1800df09d  test    eax, eax
0x1800df09f  jnz     short loc_1800DF0C8
0x1800df0a1  call    WxGetLastError
0x1800df0a6  mov     ebx, eax
0x1800df0a8  test    eax, eax
0x1800df0aa  jle     short loc_1800DF0B2
0x1800df0ac  movzx   ebx, ax
0x1800df0af  or      ebx, r14d
0x1800df0b2  test    ebx, ebx
0x1800df0b4  mov     [rbp+57h+var_7C], 28Eh
0x1800df0bb  mov     eax, 8000FFFFh
0x1800df0c0  cmovns  ebx, eax
0x1800df0c3  jmp     loc_1800DF181
0x1800df0c8  mov     rcx, [rbp+57h+hExistingToken]; hExistingToken
0x1800df0cc  lea     rax, [rbp+57h+TokenHandle]
0x1800df0d0  mov     [rsp+0C0h+phNewToken], rax; phNewToken
0x1800df0d5  mov     r9d, 1; ImpersonationLevel
0x1800df0db  xor     r8d, r8d; lpTokenAttributes
0x1800df0de  mov     [rsp+0C0h+TokenType], 2; TokenType
0x1800df0e6  mov     edx, 2000Ch; dwDesiredAccess
0x1800df0eb  call    cs:__imp_DuplicateTokenEx
0x1800df0f1  test    eax, eax
0x1800df0f3  jnz     short loc_1800DF119
0x1800df0f5  call    WxGetLastError
0x1800df0fa  mov     ebx, eax
0x1800df0fc  test    eax, eax
0x1800df0fe  jle     short loc_1800DF106
0x1800df100  movzx   ebx, ax
0x1800df103  or      ebx, r14d
0x1800df106  test    ebx, ebx
0x1800df108  mov     [rbp+57h+var_7C], 29Ah
0x1800df10f  mov     eax, 8000FFFFh
0x1800df114  cmovns  ebx, eax
0x1800df117  jmp     short loc_1800DF181
0x1800df119  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x1800df11d  lea     rax, [rbp+57h+var_68]
0x1800df121  mov     [rsp+0C0h+AccessStatus], rdi; AccessStatus
0x1800df126  lea     r9, stru_180226A60; GenericMapping
0x1800df12d  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x1800df132  lea     rcx, c_rgbSystemServiceSd; pSecurityDescriptor
0x1800df139  lea     rax, [rbp+57h+PrivilegeSetLength]
0x1800df13d  mov     r8d, 1; DesiredAccess
0x1800df143  mov     [rsp+0C0h+phNewToken], rax; PrivilegeSetLength
0x1800df148  lea     rax, [rbp+57h+PrivilegeSet]
0x1800df14c  mov     qword ptr [rsp+0C0h+TokenType], rax; PrivilegeSet
0x1800df151  call    cs:__imp_AccessCheck
0x1800df157  test    eax, eax
0x1800df159  jnz     short loc_1800DF17F
0x1800df15b  call    WxGetLastError
0x1800df160  mov     ebx, eax
0x1800df162  test    eax, eax
0x1800df164  jle     short loc_1800DF16C
0x1800df166  movzx   ebx, ax
0x1800df169  or      ebx, r14d
0x1800df16c  test    ebx, ebx
0x1800df16e  mov     [rbp+57h+var_7C], 2A8h
0x1800df175  mov     eax, 8000FFFFh
0x1800df17a  cmovns  ebx, eax
0x1800df17d  jmp     short loc_1800DF181
0x1800df17f  xor     ebx, ebx
0x1800df181  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800df185  test    rcx, rcx
0x1800df188  jz      short loc_1800DF198
0x1800df18a  call    cs:__imp_CloseHandle
0x1800df190  mov     [rbp+57h+TokenHandle], 0
0x1800df198  mov     rcx, [rbp+57h+hExistingToken]; hObject
0x1800df19c  test    rcx, rcx
0x1800df19f  jz      short loc_1800DF1A7
0x1800df1a1  call    cs:__imp_CloseHandle
0x1800df1a7  mov     eax, ebx
0x1800df1a9  mov     rcx, [rbp+57h+var_30]
0x1800df1ad  xor     rcx, rsp; StackCookie
0x1800df1b0  call    __security_check_cookie
0x1800df1b5  add     rsp, 0A8h
0x1800df1bc  pop     r14
0x1800df1be  pop     rdi
0x1800df1bf  pop     rbx
0x1800df1c0  pop     rbp
0x1800df1c1  retn
```
