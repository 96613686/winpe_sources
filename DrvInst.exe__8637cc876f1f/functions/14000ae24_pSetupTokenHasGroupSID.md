# pSetupTokenHasGroupSID

- ea: `0x14000ae24`
- end: `0x14000aed4`
- name: `pSetupTokenHasGroupSID`
- size: `176`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID SidToCheck)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000ad64`
- `0x140022330`

## callees

- `0x14000ae24`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aec3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aec3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14000aead`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14000aead`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000ae69`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000ae69`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14000ae95`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14000ae95`

## pseudocode

```c
__int64 __fastcall pSetupTokenHasGroupSID(HANDLE TokenHandle, PSID SidToCheck)
{
  HANDLE v3; // rbx
  HANDLE hObject; // [rsp+30h] [rbp-10h] BYREF
  WINBOOL IsMember; // [rsp+60h] [rbp+20h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+30h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+38h] BYREF

  IsMember = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  hObject = 0;
  v3 = TokenHandle;
  if ( GetTokenInformation(TokenHandle, TokenType, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( TokenInformation != 2 )
    {
      if ( !DuplicateTokenEx(v3, 0, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
        return (unsigned int)IsMember;
      v3 = hObject;
    }
    if ( !CheckTokenMembership(v3, SidToCheck, &IsMember) )
      IsMember = 0;
  }
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x14000ae24  push    rbp
0x14000ae26  push    rbx
0x14000ae27  push    rdi
0x14000ae28  mov     rbp, rsp
0x14000ae2b  sub     rsp, 40h
0x14000ae2f  mov     r9d, 4; TokenInformationLength
0x14000ae35  mov     [rbp+IsMember], 0
0x14000ae3c  mov     rdi, rdx
0x14000ae3f  mov     [rbp+TokenInformation], 0
0x14000ae46  lea     rax, [rbp+arg_18]
0x14000ae4a  mov     [rbp+arg_18], 0
0x14000ae51  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14000ae55  mov     [rbp+hObject], 0
0x14000ae5d  lea     edx, [r9+4]; TokenInformationClass
0x14000ae61  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x14000ae66  mov     rbx, rcx
0x14000ae69  call    cs:__imp_GetTokenInformation
0x14000ae6f  test    eax, eax
0x14000ae71  jz      short loc_14000AEBA
0x14000ae73  mov     r9d, 2; ImpersonationLevel
0x14000ae79  cmp     [rbp+TokenInformation], r9d
0x14000ae7d  jz      short loc_14000AEA3
0x14000ae7f  lea     rax, [rbp+hObject]
0x14000ae83  xor     r8d, r8d; lpTokenAttributes
0x14000ae86  mov     [rsp+40h+phNewToken], rax; phNewToken
0x14000ae8b  xor     edx, edx; dwDesiredAccess
0x14000ae8d  mov     rcx, rbx; hExistingToken
0x14000ae90  mov     dword ptr [rsp+40h+ReturnLength], r9d; TokenType
0x14000ae95  call    cs:__imp_DuplicateTokenEx
0x14000ae9b  test    eax, eax
0x14000ae9d  jz      short loc_14000AEC9
0x14000ae9f  mov     rbx, [rbp+hObject]
0x14000aea3  lea     r8, [rbp+IsMember]; IsMember
0x14000aea7  mov     rdx, rdi; SidToCheck
0x14000aeaa  mov     rcx, rbx; TokenHandle
0x14000aead  call    cs:__imp_CheckTokenMembership
0x14000aeb3  test    eax, eax
0x14000aeb5  jnz     short loc_14000AEBA
0x14000aeb7  mov     [rbp+IsMember], eax
0x14000aeba  mov     rcx, [rbp+hObject]; hObject
0x14000aebe  test    rcx, rcx
0x14000aec1  jz      short loc_14000AEC9
0x14000aec3  call    cs:__imp_CloseHandle
0x14000aec9  mov     eax, [rbp+IsMember]
0x14000aecc  add     rsp, 40h
0x14000aed0  pop     rdi
0x14000aed1  pop     rbx
0x14000aed2  pop     rbp
0x14000aed3  retn
```
