# IsSidInToken

- ea: `0x140010820`
- end: `0x140010964`
- name: `IsSidInToken`
- size: `324`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID SidToCheck, PBOOL IsMember)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000de14`
- `0x14000debc`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x140010820`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400108ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400108ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010947`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400108ac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400108ac`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140010917`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140010917`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1400108f6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1400108f6`

## string_xrefs

- `0x140010866`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x14001092b`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

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
0x140010820  push    rbx
0x140010822  push    rsi
0x140010823  push    rdi
0x140010824  sub     rsp, 50h
0x140010828  mov     rax, cs:__security_cookie
0x14001082f  xor     rax, rsp
0x140010832  mov     [rsp+68h+var_20], rax
0x140010837  mov     rbx, rcx
0x14001083a  mov     [rsp+68h+hObject], 0
0x140010843  xor     ecx, ecx
0x140010845  mov     rdi, r8
0x140010848  mov     rsi, rdx
0x14001084b  test    rdx, rdx
0x14001084e  jnz     short loc_140010857
0x140010850  mov     edx, 251h
0x140010855  jmp     short loc_140010861
0x140010857  test    rdi, rdi
0x14001085a  jnz     short loc_14001087F
0x14001085c  mov     edx, 252h; void *
0x140010861  mov     rcx, [rsp+68h]; this
0x140010866  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001086d  mov     ebx, 80004003h
0x140010872  mov     r9d, ebx; char *
0x140010875  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001087a  jmp     loc_14001093D
0x14001087f  test    rbx, rbx
0x140010882  jz      loc_140010911
0x140010888  mov     r9d, 4; TokenInformationLength
0x14001088e  mov     [rsp+68h+TokenInformation], ecx
0x140010892  mov     [rsp+68h+var_28], ecx
0x140010896  lea     rax, [rsp+68h+var_28]
0x14001089b  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x1400108a0  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1400108a5  mov     rcx, rbx; TokenHandle
0x1400108a8  lea     edx, [r9+4]; TokenInformationClass
0x1400108ac  call    cs:__imp_GetTokenInformation
0x1400108b2  test    eax, eax
0x1400108b4  jnz     short loc_1400108BD
0x1400108b6  mov     edx, 25Bh
0x1400108bb  jmp     short loc_140010926
0x1400108bd  cmp     [rsp+68h+TokenInformation], 2
0x1400108c2  jz      short loc_14001090E
0x1400108c4  mov     rcx, [rsp+68h+hObject]; hObject
0x1400108c9  test    rcx, rcx
0x1400108cc  jz      short loc_1400108D4
0x1400108ce  call    cs:__imp_CloseHandle
0x1400108d4  mov     r9d, 1; ImpersonationLevel
0x1400108da  lea     rax, [rsp+68h+hObject]
0x1400108df  mov     [rsp+68h+phNewToken], rax; phNewToken
0x1400108e4  xor     r8d, r8d; lpTokenAttributes
0x1400108e7  mov     rcx, rbx; hExistingToken
0x1400108ea  mov     dword ptr [rsp+68h+ReturnLength], 2; TokenType
0x1400108f2  lea     edx, [r9+7]; dwDesiredAccess
0x1400108f6  call    cs:__imp_DuplicateTokenEx
0x1400108fc  test    eax, eax
0x1400108fe  jnz     short loc_140010907
0x140010900  mov     edx, 264h
0x140010905  jmp     short loc_140010926
0x140010907  mov     rcx, [rsp+68h+hObject]
0x14001090c  jmp     short loc_140010911
0x14001090e  mov     rcx, rbx; TokenHandle
0x140010911  mov     r8, rdi; IsMember
0x140010914  mov     rdx, rsi; SidToCheck
0x140010917  call    cs:__imp_CheckTokenMembership
0x14001091d  test    eax, eax
0x14001091f  jnz     short loc_14001093B
0x140010921  mov     edx, 26Eh; void *
0x140010926  mov     rcx, [rsp+68h]; this
0x14001092b  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140010932  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140010937  mov     ebx, eax
0x140010939  jmp     short loc_14001093D
0x14001093b  xor     ebx, ebx
0x14001093d  mov     rcx, [rsp+68h+hObject]; hObject
0x140010942  test    rcx, rcx
0x140010945  jz      short loc_14001094D
0x140010947  call    cs:__imp_CloseHandle
0x14001094d  mov     eax, ebx
0x14001094f  mov     rcx, [rsp+68h+var_20]
0x140010954  xor     rcx, rsp; StackCookie
0x140010957  call    __security_check_cookie
0x14001095c  add     rsp, 50h
0x140010960  pop     rdi
0x140010961  pop     rsi
0x140010962  pop     rbx
0x140010963  retn
```
