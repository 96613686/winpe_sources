# _LUAIsTokenAdmin(void *)

- ea: `0x1800964ec`
- end: `0x180096586`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180096674`
- `0x180096784`

## callees

- `0x180004b80`
- `0x180006e72`
- `0x1800964ec`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096564`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096564`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180096541`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180096541`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180096520`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180096520`

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
0x1800964ec  sub     rsp, 98h
0x1800964f3  mov     rax, cs:__security_cookie
0x1800964fa  xor     rax, rsp
0x1800964fd  mov     [rsp+98h+var_18], rax
0x180096505  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18009650a  mov     [rsp+98h+IsMember], 0
0x180096512  mov     edx, 1; ImpersonationLevel
0x180096517  mov     [rsp+98h+DuplicateTokenHandle], 0
0x180096520  call    cs:__imp_DuplicateToken
0x180096526  test    eax, eax
0x180096528  jz      short loc_18009656A
0x18009652a  xor     edx, edx; DomainSid
0x18009652c  mov     [rsp+98h+cbSid], 44h ; 'D'
0x180096534  lea     r9, [rsp+98h+cbSid]; cbSid
0x180096539  lea     r8, [rsp+98h+pSid]; pSid
0x18009653e  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180096541  call    cs:__imp_CreateWellKnownSid
0x180096547  test    eax, eax
0x180096549  jz      short loc_18009655F
0x18009654b  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x180096550  lea     r8, [rsp+98h+IsMember]; IsMember
0x180096555  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x18009655a  call    CheckTokenMembership_0
0x18009655f  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x180096564  call    cs:__imp_CloseHandle
0x18009656a  mov     eax, [rsp+98h+IsMember]
0x18009656e  mov     rcx, [rsp+98h+var_18]
0x180096576  xor     rcx, rsp; StackCookie
0x180096579  call    __security_check_cookie
0x18009657e  add     rsp, 98h
0x180096585  retn
```
