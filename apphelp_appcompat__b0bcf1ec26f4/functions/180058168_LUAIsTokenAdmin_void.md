# _LUAIsTokenAdmin(void *)

- ea: `0x180058168`
- end: `0x180058203`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `155`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800582fc`
- `0x18005840c`

## callees

- `0x180058168`
- `0x180059270`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800581e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800581e1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800581bd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800581bd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800581d6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800581d6`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18005819c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18005819c`

## pseudocode

```c
__int64 __fastcall _LUAIsTokenAdmin(void *a1)
{
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid; // [rsp+24h] [rbp-74h] BYREF
  void *DuplicateTokenHandle; // [rsp+28h] [rbp-70h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  IsMember = 0;
  DuplicateTokenHandle = 0;
  if ( DuplicateToken(a1, SecurityIdentification, &DuplicateTokenHandle) )
  {
    cbSid = 68;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
      CheckTokenMembership(DuplicateTokenHandle, pSid, &IsMember);
    CloseHandle(DuplicateTokenHandle);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180058168  sub     rsp, 98h
0x18005816f  mov     rax, cs:__security_cookie
0x180058176  xor     rax, rsp
0x180058179  mov     [rsp+98h+var_18], rax
0x180058181  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180058186  mov     [rsp+98h+IsMember], 0
0x18005818e  mov     edx, 1; ImpersonationLevel
0x180058193  mov     [rsp+98h+DuplicateTokenHandle], 0
0x18005819c  call    cs:__imp_DuplicateToken
0x1800581a2  test    eax, eax
0x1800581a4  jz      short loc_1800581E7
0x1800581a6  xor     edx, edx; DomainSid
0x1800581a8  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800581b0  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800581b5  lea     r8, [rsp+98h+pSid]; pSid
0x1800581ba  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800581bd  call    cs:__imp_CreateWellKnownSid
0x1800581c3  test    eax, eax
0x1800581c5  jz      short loc_1800581DC
0x1800581c7  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x1800581cc  lea     r8, [rsp+98h+IsMember]; IsMember
0x1800581d1  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x1800581d6  call    cs:__imp_CheckTokenMembership
0x1800581dc  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x1800581e1  call    cs:__imp_CloseHandle
0x1800581e7  mov     eax, [rsp+98h+IsMember]
0x1800581eb  mov     rcx, [rsp+98h+var_18]
0x1800581f3  xor     rcx, rsp; StackCookie
0x1800581f6  call    __security_check_cookie
0x1800581fb  add     rsp, 98h
0x180058202  retn
```
