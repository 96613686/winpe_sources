# SbpEnablePrivilege

- ea: `0x140010e28`
- end: `0x140010fde`
- name: `SbpEnablePrivilege`
- size: `438`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010fe4`

## callees

- `0x140010e28`
- `0x140026650`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140010e7f`
- `KERNEL32!GetLastError` at `0x140010ec2`
- `KERNEL32!GetLastError` at `0x140010e7f`
- `KERNEL32!GetLastError` at `0x140010ec2`
- `KERNEL32!GetCurrentThread` at `0x140010ea4`
- `KERNEL32!GetCurrentThread` at `0x140010ea4`
- `KERNEL32!CloseHandle` at `0x140010f96`
- `KERNEL32!CloseHandle` at `0x140010fb0`
- `KERNEL32!CloseHandle` at `0x140010fbf`
- `KERNEL32!CloseHandle` at `0x140010f96`
- `KERNEL32!CloseHandle` at `0x140010fb0`
- `KERNEL32!CloseHandle` at `0x140010fbf`
- `KERNEL32!GetCurrentProcess` at `0x140010ecf`
- `KERNEL32!GetCurrentProcess` at `0x140010ecf`
- `ADVAPI32!SetThreadToken` at `0x140010f53`
- `ADVAPI32!SetThreadToken` at `0x140010f7e`
- `ADVAPI32!SetThreadToken` at `0x140010f53`
- `ADVAPI32!SetThreadToken` at `0x140010f7e`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140010e75`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140010e75`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140010f3f`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140010f3f`
- `ADVAPI32!OpenProcessToken` at `0x140010ee1`
- `ADVAPI32!OpenProcessToken` at `0x140010ee1`
- `ADVAPI32!OpenThreadToken` at `0x140010eb8`
- `ADVAPI32!OpenThreadToken` at `0x140010eb8`
- `ADVAPI32!DuplicateTokenEx` at `0x140010f1a`
- `ADVAPI32!DuplicateTokenEx` at `0x140010f1a`

## pseudocode

```c
__int64 __fastcall SbpEnablePrivilege(LPCWSTR lpName)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v5; // rcx
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  v1 = 0;
  TokenHandle = 0;
  Token = 0;
  if ( lpName )
  {
    NewState = 0;
    NewState.PrivilegeCount = 1;
    if ( !LookupPrivilegeValueW(0, lpName, &NewState.Privileges[0].Luid) )
      goto LABEL_3;
    NewState.Privileges[0].Attributes = 2;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 6u, 0, &TokenHandle) )
    {
      v5 = TokenHandle;
      hObject = TokenHandle;
    }
    else
    {
      if ( GetLastError() != 1008
        || (CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 2u, &TokenHandle)) )
      {
LABEL_3:
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_18;
      }
      v5 = TokenHandle;
    }
    if ( DuplicateTokenEx(v5, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token)
      && AdjustTokenPrivileges(Token, 0, &NewState, 0, 0, 0)
      && SetThreadToken(0, Token) )
    {
      dword_14003F820 = 1;
      goto LABEL_18;
    }
    goto LABEL_3;
  }
  if ( dword_14003F820 )
  {
    SetThreadToken(0, hObject);
    dword_14003F820 = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
LABEL_18:
  if ( TokenHandle != hObject )
    CloseHandle(TokenHandle);
  if ( Token )
    CloseHandle(Token);
  return v1;
}

```

## disassembly

```asm
0x140010e28  mov     [rsp-8+arg_8], rbx
0x140010e2d  push    rbp
0x140010e2e  mov     rbp, rsp
0x140010e31  sub     rsp, 60h
0x140010e35  mov     rax, cs:__security_cookie
0x140010e3c  xor     rax, rsp
0x140010e3f  mov     [rbp+var_10], rax
0x140010e43  xor     ebx, ebx
0x140010e45  mov     [rbp+TokenHandle], 0
0x140010e4d  mov     [rbp+Token], 0
0x140010e55  test    rcx, rcx
0x140010e58  jz      loc_140010F6D
0x140010e5e  xorps   xmm0, xmm0
0x140010e61  lea     r8, [rbp+NewState.Privileges]; lpLuid
0x140010e65  mov     rdx, rcx; lpName
0x140010e68  xor     ecx, ecx; lpSystemName
0x140010e6a  movups  xmmword ptr [rbp-20h], xmm0
0x140010e6e  mov     [rbp+NewState.PrivilegeCount], 1
0x140010e75  call    cs:__imp_LookupPrivilegeValueW
0x140010e7b  test    eax, eax
0x140010e7d  jnz     short loc_140010E9D
0x140010e7f  call    cs:__imp_GetLastError
0x140010e85  mov     ebx, eax
0x140010e87  test    eax, eax
0x140010e89  jle     loc_140010FA3
0x140010e8f  movzx   ebx, ax
0x140010e92  or      ebx, 80070000h
0x140010e98  jmp     loc_140010FA3
0x140010e9d  mov     [rbp+NewState.Privileges.Attributes], 2
0x140010ea4  call    cs:__imp_GetCurrentThread
0x140010eaa  xor     r8d, r8d; OpenAsSelf
0x140010ead  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140010eb1  mov     rcx, rax; ThreadHandle
0x140010eb4  lea     edx, [r8+6]; DesiredAccess
0x140010eb8  call    cs:__imp_OpenThreadToken
0x140010ebe  test    eax, eax
0x140010ec0  jnz     short loc_140010EF1
0x140010ec2  call    cs:__imp_GetLastError
0x140010ec8  cmp     eax, 3F0h
0x140010ecd  jnz     short loc_140010E7F
0x140010ecf  call    cs:__imp_GetCurrentProcess
0x140010ed5  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140010ed9  mov     edx, 2; DesiredAccess
0x140010ede  mov     rcx, rax; ProcessHandle
0x140010ee1  call    cs:__imp_OpenProcessToken
0x140010ee7  test    eax, eax
0x140010ee9  jz      short loc_140010E7F
0x140010eeb  mov     rcx, [rbp+TokenHandle]
0x140010eef  jmp     short loc_140010EFC
0x140010ef1  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x140010ef5  mov     cs:hObject, rcx
0x140010efc  mov     r9d, 2; ImpersonationLevel
0x140010f02  lea     rax, [rbp+Token]
0x140010f06  mov     [rsp+60h+phNewToken], rax; phNewToken
0x140010f0b  xor     r8d, r8d; lpTokenAttributes
0x140010f0e  mov     [rsp+60h+TokenType], 2; TokenType
0x140010f16  lea     edx, [r9+2Ah]; dwDesiredAccess
0x140010f1a  call    cs:__imp_DuplicateTokenEx
0x140010f20  test    eax, eax
0x140010f22  jz      loc_140010E7F
0x140010f28  mov     rcx, [rbp+Token]; TokenHandle
0x140010f2c  lea     r8, [rbp+NewState]; NewState
0x140010f30  mov     [rsp+60h+phNewToken], rbx; ReturnLength
0x140010f35  xor     r9d, r9d; BufferLength
0x140010f38  xor     edx, edx; DisableAllPrivileges
0x140010f3a  mov     qword ptr [rsp+60h+TokenType], rbx; PreviousState
0x140010f3f  call    cs:__imp_AdjustTokenPrivileges
0x140010f45  test    eax, eax
0x140010f47  jz      loc_140010E7F
0x140010f4d  mov     rdx, [rbp+Token]; Token
0x140010f51  xor     ecx, ecx; Thread
0x140010f53  call    cs:__imp_SetThreadToken
0x140010f59  test    eax, eax
0x140010f5b  jz      loc_140010E7F
0x140010f61  mov     cs:dword_14003F820, 1
0x140010f6b  jmp     short loc_140010FA3
0x140010f6d  cmp     cs:dword_14003F820, ebx
0x140010f73  jz      short loc_140010F8A
0x140010f75  mov     rdx, cs:hObject; Token
0x140010f7c  xor     ecx, ecx; Thread
0x140010f7e  call    cs:__imp_SetThreadToken
0x140010f84  mov     cs:dword_14003F820, ebx
0x140010f8a  mov     rcx, cs:hObject; hObject
0x140010f91  test    rcx, rcx
0x140010f94  jz      short loc_140010FA3
0x140010f96  call    cs:__imp_CloseHandle
0x140010f9c  mov     cs:hObject, rbx
0x140010fa3  mov     rcx, [rbp+TokenHandle]; hObject
0x140010fa7  cmp     rcx, cs:hObject
0x140010fae  jz      short loc_140010FB6
0x140010fb0  call    cs:__imp_CloseHandle
0x140010fb6  mov     rcx, [rbp+Token]; hObject
0x140010fba  test    rcx, rcx
0x140010fbd  jz      short loc_140010FC5
0x140010fbf  call    cs:__imp_CloseHandle
0x140010fc5  mov     eax, ebx
0x140010fc7  mov     rcx, [rbp+var_10]
0x140010fcb  xor     rcx, rsp; StackCookie
0x140010fce  call    __security_check_cookie
0x140010fd3  mov     rbx, [rsp+60h+arg_8]
0x140010fd8  add     rsp, 60h
0x140010fdc  pop     rbp
0x140010fdd  retn
```
