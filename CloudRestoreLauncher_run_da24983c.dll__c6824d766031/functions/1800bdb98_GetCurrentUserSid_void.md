# GetCurrentUserSid(void * *)

- ea: `0x1800bdb98`
- end: `0x1800bdc96`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800bdc9c`
- `0x1800be7ac`

## callees

- `0x18000c6e0`
- `0x1800bc51c`
- `0x1800bdb98`
- `0x1800beb8c`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800bdbca`
- `KERNEL32!GetCurrentThread` at `0x1800bdbca`
- `KERNEL32!GetCurrentProcess` at `0x1800bdbf9`
- `KERNEL32!GetCurrentProcess` at `0x1800bdbf9`
- `KERNEL32!CloseHandle` at `0x1800bdc6d`
- `KERNEL32!CloseHandle` at `0x1800bdc6d`
- `ADVAPI32!OpenThreadToken` at `0x1800bdbe1`
- `ADVAPI32!OpenThreadToken` at `0x1800bdbe1`
- `ADVAPI32!GetTokenInformation` at `0x1800bdc44`
- `ADVAPI32!GetTokenInformation` at `0x1800bdc44`
- `ADVAPI32!OpenProcessToken` at `0x1800bdc0c`
- `ADVAPI32!OpenProcessToken` at `0x1800bdc0c`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  int Error; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    if ( Error != -2147023888 )
      goto LABEL_5;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      Error = ResultFromKnownLastError();
LABEL_5:
      if ( Error < 0 )
        return (unsigned int)Error;
    }
  }
  ReturnLength = 88;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    Error = AllocAndCopySid(TokenInformation[0], a1);
  }
  CloseHandle(TokenHandle);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800bdb98  mov     [rsp+arg_8], rbx
0x1800bdb9d  push    rdi
0x1800bdb9e  sub     rsp, 0B0h
0x1800bdba5  mov     rax, cs:__security_cookie
0x1800bdbac  xor     rax, rsp
0x1800bdbaf  mov     [rsp+0B8h+var_18], rax
0x1800bdbb7  mov     rdi, rcx
0x1800bdbba  mov     qword ptr [rcx], 0
0x1800bdbc1  mov     [rsp+0B8h+TokenHandle], 0
0x1800bdbca  call    cs:__imp_GetCurrentThread
0x1800bdbd0  mov     edx, 8; DesiredAccess
0x1800bdbd5  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800bdbda  mov     rcx, rax; ThreadHandle
0x1800bdbdd  lea     r8d, [rdx-7]; OpenAsSelf
0x1800bdbe1  call    cs:__imp_OpenThreadToken
0x1800bdbe7  test    eax, eax
0x1800bdbe9  jnz     short loc_1800BDC21
0x1800bdbeb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bdbf0  mov     ebx, eax
0x1800bdbf2  cmp     eax, 800703F0h
0x1800bdbf7  jnz     short loc_1800BDC1D
0x1800bdbf9  call    cs:__imp_GetCurrentProcess
0x1800bdbff  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800bdc04  mov     edx, 8; DesiredAccess
0x1800bdc09  mov     rcx, rax; ProcessHandle
0x1800bdc0c  call    cs:__imp_OpenProcessToken
0x1800bdc12  test    eax, eax
0x1800bdc14  jnz     short loc_1800BDC21
0x1800bdc16  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bdc1b  mov     ebx, eax
0x1800bdc1d  test    ebx, ebx
0x1800bdc1f  js      short loc_1800BDC73
0x1800bdc21  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800bdc26  lea     rax, [rsp+0B8h+var_80]
0x1800bdc2b  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800bdc31  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1800bdc36  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1800bdc3b  mov     [rsp+0B8h+var_80], r9d
0x1800bdc40  lea     edx, [r9-57h]; TokenInformationClass
0x1800bdc44  call    cs:__imp_GetTokenInformation
0x1800bdc4a  test    eax, eax
0x1800bdc4c  jnz     short loc_1800BDC59
0x1800bdc4e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bdc53  mov     ebx, eax
0x1800bdc55  test    eax, eax
0x1800bdc57  js      short loc_1800BDC68
0x1800bdc59  mov     rcx, [rsp+0B8h+TokenInformation]; pSourceSid
0x1800bdc5e  mov     rdx, rdi; void **
0x1800bdc61  call    ?AllocAndCopySid@@YAJPEAXPEAPEAX@Z; AllocAndCopySid(void *,void * *)
0x1800bdc66  mov     ebx, eax
0x1800bdc68  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x1800bdc6d  call    cs:__imp_CloseHandle
0x1800bdc73  mov     eax, ebx
0x1800bdc75  mov     rcx, [rsp+0B8h+var_18]
0x1800bdc7d  xor     rcx, rsp; StackCookie
0x1800bdc80  call    __security_check_cookie
0x1800bdc85  mov     rbx, [rsp+0B8h+arg_8]
0x1800bdc8d  add     rsp, 0B0h
0x1800bdc94  pop     rdi
0x1800bdc95  retn
```
