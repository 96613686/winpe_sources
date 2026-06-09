# FAllocateAndRetrieveUserSid(ulong,void * *)

- ea: `0x1801579f4`
- end: `0x180157c46`
- name: `?FAllocateAndRetrieveUserSid@@YAHKPEAPEAX@Z`
- size: `594`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180158448`
- `0x180158788`
- `0x180158bc8`

## callees

- `0x18001373c`
- `0x1801579f4`
- `0x18056bd00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180157a7d`
- `KERNEL32!GetLastError` at `0x180157ada`
- `KERNEL32!GetLastError` at `0x180157b2c`
- `KERNEL32!GetLastError` at `0x180157b7d`
- `KERNEL32!GetLastError` at `0x180157b9f`
- `KERNEL32!GetLastError` at `0x180157a7d`
- `KERNEL32!GetLastError` at `0x180157ada`
- `KERNEL32!GetLastError` at `0x180157b2c`
- `KERNEL32!GetLastError` at `0x180157b7d`
- `KERNEL32!GetLastError` at `0x180157b9f`
- `KERNEL32!GetCurrentProcess` at `0x180157a9b`
- `KERNEL32!GetCurrentProcess` at `0x180157a9b`
- `KERNEL32!CloseHandle` at `0x180157bd6`
- `KERNEL32!CloseHandle` at `0x180157bd6`
- `KERNEL32!GlobalFree` at `0x180157bb8`
- `KERNEL32!GlobalFree` at `0x180157bb8`
- `KERNEL32!GlobalAlloc` at `0x180157b52`
- `KERNEL32!GlobalAlloc` at `0x180157c13`
- `KERNEL32!GlobalAlloc` at `0x180157b52`
- `KERNEL32!GlobalAlloc` at `0x180157c13`
- `KERNEL32!GetCurrentThread` at `0x180157a5d`
- `KERNEL32!GetCurrentThread` at `0x180157a5d`
- `ADVAPI32!OpenProcessToken` at `0x180157aae`
- `ADVAPI32!OpenProcessToken` at `0x180157aae`
- `ADVAPI32!IsValidSid` at `0x180157b95`
- `ADVAPI32!IsValidSid` at `0x180157b95`
- `ADVAPI32!CopySid` at `0x180157b73`
- `ADVAPI32!CopySid` at `0x180157b73`
- `ADVAPI32!GetLengthSid` at `0x180157b44`
- `ADVAPI32!GetLengthSid` at `0x180157b44`
- `ADVAPI32!OpenThreadToken` at `0x180157a73`
- `ADVAPI32!OpenThreadToken` at `0x180157a73`
- `ADVAPI32!GetTokenInformation` at `0x180157ad4`
- `ADVAPI32!GetTokenInformation` at `0x180157b1c`
- `ADVAPI32!GetTokenInformation` at `0x180157ad4`
- `ADVAPI32!GetTokenInformation` at `0x180157b1c`

## pseudocode

```c
_BOOL8 __fastcall FAllocateAndRetrieveUserSid(int a1, void **a2)
{
  PSID *v4; // rdi
  char v5; // r14
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD v8; // r9d
  PSID *p_TokenInformation; // r14
  signed int LastError; // eax
  signed int v11; // ebx
  HGLOBAL v12; // rax
  signed int v13; // eax
  signed int v14; // eax
  HANDLE v15; // rcx
  BOOL v16; // ebx
  DWORD TokenInformationLength[2]; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C8h] BYREF
  char TokenInformation; // [rsp+48h] [rbp-C0h] BYREF

  if ( !a2 )
    return 0;
  v4 = 0;
  TokenHandle = 0;
  v5 = 0;
  TokenInformationLength[0] = 0;
  *a2 = 0;
  if ( a1 != 1 )
  {
    if ( a1 != 2 )
    {
      MsoShipAssertTagProc(1339788);
      goto LABEL_32;
    }
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      if ( GetLastError() != 1008 )
      {
LABEL_32:
        v11 = -2147467259;
        goto LABEL_29;
      }
      v5 = 1;
    }
    if ( !v5 )
      goto LABEL_10;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    goto LABEL_32;
LABEL_10:
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, TokenInformationLength);
  if ( GetLastError() != 122 )
    goto LABEL_32;
  v8 = TokenInformationLength[0];
  if ( TokenInformationLength[0] < 0x100 )
  {
    p_TokenInformation = (PSID *)&TokenInformation;
    goto LABEL_14;
  }
  v4 = (PSID *)GlobalAlloc(0, TokenInformationLength[0]);
  p_TokenInformation = v4;
  MsoShipAssertTagProc(1339792);
  if ( v4 )
  {
    v8 = TokenInformationLength[0];
LABEL_14:
    if ( GetTokenInformation(TokenHandle, TokenUser, p_TokenInformation, v8, TokenInformationLength) )
      goto LABEL_18;
    LastError = GetLastError();
    v11 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v11 = LastError;
    if ( !v11 )
    {
LABEL_18:
      TokenInformationLength[0] = GetLengthSid(*p_TokenInformation);
      v12 = GlobalAlloc(0, TokenInformationLength[0]);
      *a2 = v12;
      if ( v12 )
      {
        v11 = 0;
        if ( CopySid(TokenInformationLength[0], v12, *p_TokenInformation) )
          goto LABEL_26;
        v13 = GetLastError();
        v11 = (unsigned __int16)v13 | 0x80070000;
        if ( v13 <= 0 )
          v11 = v13;
        if ( !v11 )
        {
LABEL_26:
          if ( !IsValidSid(*a2) )
          {
            v14 = GetLastError();
            v11 = (unsigned __int16)v14 | 0x80070000;
            if ( v14 <= 0 )
              v11 = v14;
          }
        }
      }
      else
      {
        v11 = -2147024882;
      }
    }
    if ( v4 )
      GlobalFree(v4);
    goto LABEL_29;
  }
  v11 = -2147024882;
LABEL_29:
  v15 = TokenHandle;
  v16 = v11 >= 0;
  if ( TokenHandle )
  {
    TokenHandle = 0;
    CloseHandle(v15);
  }
  return v16;
}

```

## disassembly

```asm
0x1801579f4  mov     rax, rsp
0x1801579f7  mov     [rax+8], rbx
0x1801579fb  mov     [rax+18h], rsi
0x1801579ff  mov     [rax+20h], rdi
0x180157a03  push    rbp
0x180157a04  push    r12
0x180157a06  push    r14
0x180157a08  lea     rbp, [rax-68h]
0x180157a0c  sub     rsp, 150h
0x180157a13  mov     rax, cs:__security_cookie
0x180157a1a  xor     rax, rsp
0x180157a1d  mov     [rbp+60h+var_20], rax
0x180157a21  mov     rsi, rdx
0x180157a24  mov     ebx, ecx
0x180157a26  test    rdx, rdx
0x180157a29  jnz     short loc_180157A32
0x180157a2b  xor     eax, eax
0x180157a2d  jmp     loc_180157BDE
0x180157a32  xor     edi, edi
0x180157a34  mov     [rsp+160h+TokenHandle], 0
0x180157a3d  xor     r14b, r14b
0x180157a40  mov     [rsp+160h+TokenInformationLength], 0
0x180157a48  mov     [rdx], rdi
0x180157a4b  lea     r12d, [rdi+1]
0x180157a4f  cmp     ebx, r12d
0x180157a52  jz      short loc_180157A9B
0x180157a54  cmp     ebx, 2
0x180157a57  jnz     loc_180157C39
0x180157a5d  call    cs:__imp_GetCurrentThread
0x180157a63  lea     r9, [rsp+160h+TokenHandle]; TokenHandle
0x180157a68  mov     r8d, r12d; OpenAsSelf
0x180157a6b  mov     rcx, rax; ThreadHandle
0x180157a6e  mov     edx, 8; DesiredAccess
0x180157a73  call    cs:__imp_OpenThreadToken
0x180157a79  test    eax, eax
0x180157a7b  jnz     short loc_180157A91
0x180157a7d  call    cs:__imp_GetLastError
0x180157a83  cmp     eax, 3F0h
0x180157a88  jnz     loc_180157C07
0x180157a8e  mov     r14b, r12b
0x180157a91  cmp     ebx, r12d
0x180157a94  jz      short loc_180157A9B
0x180157a96  test    r14b, r14b
0x180157a99  jz      short loc_180157ABC
0x180157a9b  call    cs:__imp_GetCurrentProcess
0x180157aa1  lea     r8, [rsp+160h+TokenHandle]; TokenHandle
0x180157aa6  mov     edx, 8; DesiredAccess
0x180157aab  mov     rcx, rax; ProcessHandle
0x180157aae  call    cs:__imp_OpenProcessToken
0x180157ab4  test    eax, eax
0x180157ab6  jz      loc_180157C07
0x180157abc  mov     rcx, [rsp+160h+TokenHandle]; TokenHandle
0x180157ac1  lea     rax, [rsp+160h+TokenInformationLength]
0x180157ac6  xor     r9d, r9d; TokenInformationLength
0x180157ac9  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x180157ace  xor     r8d, r8d; TokenInformation
0x180157ad1  mov     edx, r12d; TokenInformationClass
0x180157ad4  call    cs:__imp_GetTokenInformation
0x180157ada  call    cs:__imp_GetLastError
0x180157ae0  cmp     eax, 7Ah ; 'z'
0x180157ae3  jnz     loc_180157C07
0x180157ae9  mov     r9d, [rsp+160h+TokenInformationLength]
0x180157aee  cmp     r9d, 100h
0x180157af5  jnb     loc_180157C0E
0x180157afb  lea     r14, [rsp+160h+TokenInformation]
0x180157b00  jmp     short loc_180157B07
0x180157b02  mov     r9d, [rsp+160h+TokenInformationLength]; TokenInformationLength
0x180157b07  mov     rcx, [rsp+160h+TokenHandle]; TokenHandle
0x180157b0c  lea     rax, [rsp+160h+TokenInformationLength]
0x180157b11  mov     r8, r14; TokenInformation
0x180157b14  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x180157b19  mov     edx, r12d; TokenInformationClass
0x180157b1c  call    cs:__imp_GetTokenInformation
0x180157b22  mov     r12d, 80070000h
0x180157b28  test    eax, eax
0x180157b2a  jnz     short loc_180157B41
0x180157b2c  call    cs:__imp_GetLastError
0x180157b32  movzx   ebx, ax
0x180157b35  or      ebx, r12d
0x180157b38  test    eax, eax
0x180157b3a  cmovle  ebx, eax
0x180157b3d  test    ebx, ebx
0x180157b3f  jnz     short loc_180157BB0
0x180157b41  mov     rcx, [r14]; pSid
0x180157b44  call    cs:__imp_GetLengthSid
0x180157b4a  mov     edx, eax; dwBytes
0x180157b4c  xor     ecx, ecx; uFlags
0x180157b4e  mov     [rsp+160h+TokenInformationLength], edx
0x180157b52  call    cs:__imp_GlobalAlloc
0x180157b58  mov     [rsi], rax
0x180157b5b  test    rax, rax
0x180157b5e  jnz     short loc_180157B67
0x180157b60  mov     ebx, 8007000Eh
0x180157b65  jmp     short loc_180157BB0
0x180157b67  mov     r8, [r14]; pSourceSid
0x180157b6a  mov     rdx, rax; pDestinationSid
0x180157b6d  mov     ecx, [rsp+160h+TokenInformationLength]; nDestinationSidLength
0x180157b71  xor     ebx, ebx
0x180157b73  call    cs:__imp_CopySid
0x180157b79  test    eax, eax
0x180157b7b  jnz     short loc_180157B92
0x180157b7d  call    cs:__imp_GetLastError
0x180157b83  movzx   ebx, ax
0x180157b86  or      ebx, r12d
0x180157b89  test    eax, eax
0x180157b8b  cmovle  ebx, eax
0x180157b8e  test    ebx, ebx
0x180157b90  jnz     short loc_180157BB0
0x180157b92  mov     rcx, [rsi]; pSid
0x180157b95  call    cs:__imp_IsValidSid
0x180157b9b  test    eax, eax
0x180157b9d  jnz     short loc_180157BB0
0x180157b9f  call    cs:__imp_GetLastError
0x180157ba5  movzx   ebx, ax
0x180157ba8  or      ebx, r12d
0x180157bab  test    eax, eax
0x180157bad  cmovle  ebx, eax
0x180157bb0  test    rdi, rdi
0x180157bb3  jz      short loc_180157BBE
0x180157bb5  mov     rcx, rdi; hMem
0x180157bb8  call    cs:__imp_GlobalFree
0x180157bbe  mov     rcx, [rsp+160h+TokenHandle]; hObject
0x180157bc3  not     ebx
0x180157bc5  shr     ebx, 1Fh
0x180157bc8  test    rcx, rcx
0x180157bcb  jz      short loc_180157BDC
0x180157bcd  mov     [rsp+160h+TokenHandle], 0
0x180157bd6  call    cs:__imp_CloseHandle
0x180157bdc  mov     eax, ebx
0x180157bde  mov     rcx, [rbp+60h+var_20]
0x180157be2  xor     rcx, rsp; StackCookie
0x180157be5  call    __security_check_cookie
0x180157bea  lea     r11, [rsp+160h+var_10]
0x180157bf2  mov     rbx, [r11+20h]
0x180157bf6  mov     rsi, [r11+30h]
0x180157bfa  mov     rdi, [r11+38h]
0x180157bfe  mov     rsp, r11
0x180157c01  pop     r14
0x180157c03  pop     r12
0x180157c05  pop     rbp
0x180157c06  retn
0x180157c07  mov     ebx, 80004005h
0x180157c0c  jmp     short loc_180157BBE
0x180157c0e  mov     rdx, r9; dwBytes
0x180157c11  xor     ecx, ecx; uFlags
0x180157c13  call    cs:__imp_GlobalAlloc
0x180157c19  mov     ecx, 147190h
0x180157c1e  mov     rdi, rax
0x180157c21  mov     r14, rax
0x180157c24  call    MsoShipAssertTagProc
0x180157c29  test    r14, r14
0x180157c2c  jnz     loc_180157B02
0x180157c32  mov     ebx, 8007000Eh
0x180157c37  jmp     short loc_180157BBE
0x180157c39  mov     ecx, 14718Ch
0x180157c3e  call    MsoShipAssertTagProc
0x180157c43  jmp     short loc_180157C07
```
