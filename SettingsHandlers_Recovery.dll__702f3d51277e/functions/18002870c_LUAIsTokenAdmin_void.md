# _LUAIsTokenAdmin(void *)

- ea: `0x18002870c`
- end: `0x1800287a7`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `155`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028898`
- `0x1800289a8`

## callees

- `0x180002350`
- `0x18002870c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028785`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028785`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180028761`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180028761`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002877a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002877a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180028740`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180028740`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
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
0x18002870c  sub     rsp, 98h
0x180028713  mov     rax, cs:__security_cookie
0x18002871a  xor     rax, rsp
0x18002871d  mov     [rsp+98h+var_18], rax
0x180028725  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18002872a  mov     [rsp+98h+IsMember], 0
0x180028732  mov     edx, 1; ImpersonationLevel
0x180028737  mov     [rsp+98h+DuplicateTokenHandle], 0
0x180028740  call    cs:__imp_DuplicateToken
0x180028746  test    eax, eax
0x180028748  jz      short loc_18002878B
0x18002874a  xor     edx, edx; DomainSid
0x18002874c  mov     [rsp+98h+cbSid], 44h ; 'D'
0x180028754  lea     r9, [rsp+98h+cbSid]; cbSid
0x180028759  lea     r8, [rsp+98h+pSid]; pSid
0x18002875e  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180028761  call    cs:__imp_CreateWellKnownSid
0x180028767  test    eax, eax
0x180028769  jz      short loc_180028780
0x18002876b  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x180028770  lea     r8, [rsp+98h+IsMember]; IsMember
0x180028775  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x18002877a  call    cs:__imp_CheckTokenMembership
0x180028780  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x180028785  call    cs:__imp_CloseHandle
0x18002878b  mov     eax, [rsp+98h+IsMember]
0x18002878f  mov     rcx, [rsp+98h+var_18]
0x180028797  xor     rcx, rsp; StackCookie
0x18002879a  call    __security_check_cookie
0x18002879f  add     rsp, 98h
0x1800287a6  retn
```
