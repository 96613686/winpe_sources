# IsSidInToken

- ea: `0x18000a45c`
- end: `0x18000a5a0`
- name: `IsSidInToken`
- size: `324`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID SidToCheck, PBOOL IsMember)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dff4`
- `0x18000e094`
- `0x18000e134`
- `0x18000e1dc`
- `0x18000e280`
- `0x18000e494`
- `0x18000e538`
- `0x18000e5dc`
- `0x18000e684`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000a45c`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a50a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a50a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a583`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000a553`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000a553`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a532`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a532`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a4e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a4e8`

## string_xrefs

- `0x18000a4a2`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x18000a567`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall IsSidInToken(HANDLE TokenHandle, PSID SidToCheck, PBOOL IsMember)
{
  HANDLE v4; // rcx
  __int64 v7; // rdx
  unsigned int LastError; // ebx
  const char *v9; // r9
  __int64 v10; // rdx
  int ReturnLength; // [rsp+20h] [rbp-48h]
  int TokenInformation; // [rsp+30h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-30h] BYREF
  DWORD v15; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  hObject = 0;
  v4 = 0;
  if ( !SidToCheck )
  {
    v7 = 593;
LABEL_5:
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)0x80004003LL,
      ReturnLength);
    goto LABEL_20;
  }
  if ( !IsMember )
  {
    v7 = 594;
    goto LABEL_5;
  }
  if ( TokenHandle )
  {
    TokenInformation = 0;
    v15 = 0;
    if ( !GetTokenInformation(TokenHandle, TokenType, &TokenInformation, 4u, &v15) )
    {
      v10 = 603;
LABEL_18:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v10,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
                    v9);
      goto LABEL_20;
    }
    if ( TokenInformation == 2 )
    {
      v4 = TokenHandle;
    }
    else
    {
      if ( hObject )
        CloseHandle(hObject);
      if ( !DuplicateTokenEx(TokenHandle, 8u, 0, SecurityIdentification, TokenImpersonation, &hObject) )
      {
        v10 = 612;
        goto LABEL_18;
      }
      v4 = hObject;
    }
  }
  if ( !CheckTokenMembership(v4, SidToCheck, IsMember) )
  {
    v10 = 622;
    goto LABEL_18;
  }
  LastError = 0;
LABEL_20:
  if ( hObject )
    CloseHandle(hObject);
  return LastError;
}

```

## disassembly

```asm
0x18000a45c  push    rbx
0x18000a45e  push    rsi
0x18000a45f  push    rdi
0x18000a460  sub     rsp, 50h
0x18000a464  mov     rax, cs:__security_cookie
0x18000a46b  xor     rax, rsp
0x18000a46e  mov     [rsp+68h+var_20], rax
0x18000a473  mov     rbx, rcx
0x18000a476  mov     [rsp+68h+hObject], 0
0x18000a47f  xor     ecx, ecx
0x18000a481  mov     rdi, r8
0x18000a484  mov     rsi, rdx
0x18000a487  test    rdx, rdx
0x18000a48a  jnz     short loc_18000A493
0x18000a48c  mov     edx, 251h
0x18000a491  jmp     short loc_18000A49D
0x18000a493  test    rdi, rdi
0x18000a496  jnz     short loc_18000A4BB
0x18000a498  mov     edx, 252h; void *
0x18000a49d  mov     rcx, [rsp+68h]; this
0x18000a4a2  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000a4a9  mov     ebx, 80004003h
0x18000a4ae  mov     r9d, ebx; char *
0x18000a4b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4b6  jmp     loc_18000A579
0x18000a4bb  test    rbx, rbx
0x18000a4be  jz      loc_18000A54D
0x18000a4c4  mov     r9d, 4; TokenInformationLength
0x18000a4ca  mov     [rsp+68h+TokenInformation], ecx
0x18000a4ce  mov     [rsp+68h+var_28], ecx
0x18000a4d2  lea     rax, [rsp+68h+var_28]
0x18000a4d7  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x18000a4dc  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18000a4e1  mov     rcx, rbx; TokenHandle
0x18000a4e4  lea     edx, [r9+4]; TokenInformationClass
0x18000a4e8  call    cs:__imp_GetTokenInformation
0x18000a4ee  test    eax, eax
0x18000a4f0  jnz     short loc_18000A4F9
0x18000a4f2  mov     edx, 25Bh
0x18000a4f7  jmp     short loc_18000A562
0x18000a4f9  cmp     [rsp+68h+TokenInformation], 2
0x18000a4fe  jz      short loc_18000A54A
0x18000a500  mov     rcx, [rsp+68h+hObject]; hObject
0x18000a505  test    rcx, rcx
0x18000a508  jz      short loc_18000A510
0x18000a50a  call    cs:__imp_CloseHandle
0x18000a510  mov     r9d, 1; ImpersonationLevel
0x18000a516  lea     rax, [rsp+68h+hObject]
0x18000a51b  mov     [rsp+68h+phNewToken], rax; phNewToken
0x18000a520  xor     r8d, r8d; lpTokenAttributes
0x18000a523  mov     rcx, rbx; hExistingToken
0x18000a526  mov     dword ptr [rsp+68h+ReturnLength], 2; TokenType
0x18000a52e  lea     edx, [r9+7]; dwDesiredAccess
0x18000a532  call    cs:__imp_DuplicateTokenEx
0x18000a538  test    eax, eax
0x18000a53a  jnz     short loc_18000A543
0x18000a53c  mov     edx, 264h
0x18000a541  jmp     short loc_18000A562
0x18000a543  mov     rcx, [rsp+68h+hObject]
0x18000a548  jmp     short loc_18000A54D
0x18000a54a  mov     rcx, rbx; TokenHandle
0x18000a54d  mov     r8, rdi; IsMember
0x18000a550  mov     rdx, rsi; SidToCheck
0x18000a553  call    cs:__imp_CheckTokenMembership
0x18000a559  test    eax, eax
0x18000a55b  jnz     short loc_18000A577
0x18000a55d  mov     edx, 26Eh; void *
0x18000a562  mov     rcx, [rsp+68h]; this
0x18000a567  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000a56e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a573  mov     ebx, eax
0x18000a575  jmp     short loc_18000A579
0x18000a577  xor     ebx, ebx
0x18000a579  mov     rcx, [rsp+68h+hObject]; hObject
0x18000a57e  test    rcx, rcx
0x18000a581  jz      short loc_18000A589
0x18000a583  call    cs:__imp_CloseHandle
0x18000a589  mov     eax, ebx
0x18000a58b  mov     rcx, [rsp+68h+var_20]
0x18000a590  xor     rcx, rsp; StackCookie
0x18000a593  call    __security_check_cookie
0x18000a598  add     rsp, 50h
0x18000a59c  pop     rdi
0x18000a59d  pop     rsi
0x18000a59e  pop     rbx
0x18000a59f  retn
```
