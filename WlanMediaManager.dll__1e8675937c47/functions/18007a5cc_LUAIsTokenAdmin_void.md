# _LUAIsTokenAdmin(void *)

- ea: `0x18007a5cc`
- end: `0x18007a667`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `155`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007a758`
- `0x18007a868`

## callees

- `0x180003ed0`
- `0x18007a5cc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a645`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a645`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007a63a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007a63a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007a600`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007a600`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007a621`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007a621`

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
0x18007a5cc  sub     rsp, 98h
0x18007a5d3  mov     rax, cs:__security_cookie
0x18007a5da  xor     rax, rsp
0x18007a5dd  mov     [rsp+98h+var_18], rax
0x18007a5e5  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18007a5ea  mov     [rsp+98h+IsMember], 0
0x18007a5f2  mov     edx, 1; ImpersonationLevel
0x18007a5f7  mov     [rsp+98h+DuplicateTokenHandle], 0
0x18007a600  call    cs:__imp_DuplicateToken
0x18007a606  test    eax, eax
0x18007a608  jz      short loc_18007A64B
0x18007a60a  xor     edx, edx; DomainSid
0x18007a60c  mov     [rsp+98h+cbSid], 44h ; 'D'
0x18007a614  lea     r9, [rsp+98h+cbSid]; cbSid
0x18007a619  lea     r8, [rsp+98h+pSid]; pSid
0x18007a61e  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18007a621  call    cs:__imp_CreateWellKnownSid
0x18007a627  test    eax, eax
0x18007a629  jz      short loc_18007A640
0x18007a62b  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x18007a630  lea     r8, [rsp+98h+IsMember]; IsMember
0x18007a635  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x18007a63a  call    cs:__imp_CheckTokenMembership
0x18007a640  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x18007a645  call    cs:__imp_CloseHandle
0x18007a64b  mov     eax, [rsp+98h+IsMember]
0x18007a64f  mov     rcx, [rsp+98h+var_18]
0x18007a657  xor     rcx, rsp; StackCookie
0x18007a65a  call    __security_check_cookie
0x18007a65f  add     rsp, 98h
0x18007a666  retn
```
