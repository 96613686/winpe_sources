# _LUAIsTokenAdmin(void *)

- ea: `0x180027260`
- end: `0x1800272fa`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027434`
- `0x180027544`

## callees

- `0x180003520`
- `0x180004223`
- `0x180027260`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800272d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800272d8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800272b5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800272b5`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180027294`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180027294`

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
      CheckTokenMembership_0(DuplicateTokenHandle, pSid, &IsMember);
    CloseHandle(DuplicateTokenHandle);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180027260  sub     rsp, 98h
0x180027267  mov     rax, cs:__security_cookie
0x18002726e  xor     rax, rsp
0x180027271  mov     [rsp+98h+var_18], rax
0x180027279  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18002727e  mov     [rsp+98h+IsMember], 0
0x180027286  mov     edx, 1; ImpersonationLevel
0x18002728b  mov     [rsp+98h+DuplicateTokenHandle], 0
0x180027294  call    cs:__imp_DuplicateToken
0x18002729a  test    eax, eax
0x18002729c  jz      short loc_1800272DE
0x18002729e  xor     edx, edx; DomainSid
0x1800272a0  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800272a8  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800272ad  lea     r8, [rsp+98h+pSid]; pSid
0x1800272b2  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800272b5  call    cs:__imp_CreateWellKnownSid
0x1800272bb  test    eax, eax
0x1800272bd  jz      short loc_1800272D3
0x1800272bf  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x1800272c4  lea     r8, [rsp+98h+IsMember]; IsMember
0x1800272c9  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x1800272ce  call    CheckTokenMembership_0
0x1800272d3  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x1800272d8  call    cs:__imp_CloseHandle
0x1800272de  mov     eax, [rsp+98h+IsMember]
0x1800272e2  mov     rcx, [rsp+98h+var_18]
0x1800272ea  xor     rcx, rsp; StackCookie
0x1800272ed  call    __security_check_cookie
0x1800272f2  add     rsp, 98h
0x1800272f9  retn
```
