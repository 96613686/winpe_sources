# CDsmAccessCheck::AccessCheck(void *,void *)

- ea: `0x18002d1bc`
- end: `0x18002d2c0`
- name: `?AccessCheck@CDsmAccessCheck@@SA_NPEAX0@Z`
- size: `260`
- prototype: `bool __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, HANDLE ExistingTokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002da44`

## callees

- `0x18001af70`
- `0x18002d1bc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d296`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18002d236`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18002d236`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18002d1fd`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18002d1fd`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18002d285`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18002d285`

## pseudocode

```c
bool __fastcall CDsmAccessCheck::AccessCheck(PSECURITY_DESCRIPTOR pSecurityDescriptor, HANDLE ExistingTokenHandle)
{
  WINBOOL AccessStatus; // [rsp+40h] [rbp+7h] BYREF
  DWORD AccessMask; // [rsp+44h] [rbp+Bh] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp+Fh] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp+13h] BYREF
  void *DuplicateTokenHandle; // [rsp+50h] [rbp+17h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp+1Fh] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+68h] [rbp+2Fh] BYREF

  AccessStatus = 0;
  DuplicateTokenHandle = 0;
  if ( DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
  {
    GenericMapping.GenericRead = 1179785;
    GenericMapping.GenericWrite = 1179926;
    GenericMapping.GenericExecute = 1179808;
    GenericMapping.GenericAll = 2032127;
    AccessMask = 0x10000;
    MapGenericMask(&AccessMask, &GenericMapping);
    GrantedAccess = 0;
    PrivilegeSetLength = 20;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( !AccessCheck(
            pSecurityDescriptor,
            DuplicateTokenHandle,
            AccessMask,
            &GenericMapping,
            &PrivilegeSet,
            &PrivilegeSetLength,
            &GrantedAccess,
            &AccessStatus) )
      AccessStatus = 0;
    CloseHandle(DuplicateTokenHandle);
  }
  return AccessStatus != 0;
}

```

## disassembly

```asm
0x18002d1bc  mov     [rsp-8+arg_10], rbx
0x18002d1c1  push    rbp
0x18002d1c2  lea     rbp, [rsp-57h]
0x18002d1c7  sub     rsp, 90h
0x18002d1ce  mov     rax, cs:__security_cookie
0x18002d1d5  xor     rax, rsp
0x18002d1d8  mov     [rbp+57h+var_10], rax
0x18002d1dc  mov     rax, rdx
0x18002d1df  mov     [rbp+57h+var_50], 0
0x18002d1e6  mov     rbx, rcx
0x18002d1e9  mov     [rbp+57h+DuplicateTokenHandle], 0
0x18002d1f1  mov     rcx, rax; ExistingTokenHandle
0x18002d1f4  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18002d1f8  mov     edx, 2; ImpersonationLevel
0x18002d1fd  call    cs:__imp_DuplicateToken
0x18002d203  test    eax, eax
0x18002d205  jz      loc_18002D29C
0x18002d20b  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18002d20f  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x18002d216  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18002d21a  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x18002d221  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x18002d228  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x18002d22f  mov     [rbp+57h+AccessMask], 10000h
0x18002d236  call    cs:__imp_MapGenericMask
0x18002d23c  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18002d240  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18002d244  mov     rdx, [rbp+57h+DuplicateTokenHandle]; ClientToken
0x18002d248  xor     eax, eax
0x18002d24a  mov     [rbp+57h+var_28.Privilege.Attributes], eax
0x18002d24d  xorps   xmm0, xmm0
0x18002d250  mov     [rbp+57h+var_48], eax
0x18002d253  mov     rcx, rbx; pSecurityDescriptor
0x18002d256  lea     rax, [rbp+57h+var_50]
0x18002d25a  mov     [rbp+57h+var_44], 14h
0x18002d261  mov     [rsp+90h+AccessStatus], rax; AccessStatus
0x18002d266  lea     rax, [rbp+57h+var_48]
0x18002d26a  mov     [rsp+90h+GrantedAccess], rax; GrantedAccess
0x18002d26f  lea     rax, [rbp+57h+var_44]
0x18002d273  mov     [rsp+90h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18002d278  lea     rax, [rbp+57h+var_28]
0x18002d27c  mov     [rsp+90h+PrivilegeSet], rax; PrivilegeSet
0x18002d281  movups  xmmword ptr [rbp+57h+var_28.PrivilegeCount], xmm0
0x18002d285  call    cs:__imp_AccessCheck
0x18002d28b  test    eax, eax
0x18002d28d  jnz     short loc_18002D292
0x18002d28f  mov     [rbp+57h+var_50], eax
0x18002d292  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x18002d296  call    cs:__imp_CloseHandle
0x18002d29c  cmp     [rbp+57h+var_50], 0
0x18002d2a0  setnz   al
0x18002d2a3  mov     rcx, [rbp+57h+var_10]
0x18002d2a7  xor     rcx, rsp; StackCookie
0x18002d2aa  call    __security_check_cookie
0x18002d2af  mov     rbx, [rsp+90h+arg_10]
0x18002d2b7  add     rsp, 90h
0x18002d2be  pop     rbp
0x18002d2bf  retn
```
