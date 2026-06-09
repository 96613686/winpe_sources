# _LUAIsTokenAdmin(void *)

- ea: `0x18007aafc`
- end: `0x18007abb0`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `180`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007acb4`

## callees

- `0x180034070`
- `0x18007aafc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ab87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ab87`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007ab57`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007ab57`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007ab76`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007ab76`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007ab30`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007ab30`

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
0x18007aafc  sub     rsp, 98h
0x18007ab03  mov     rax, cs:__security_cookie
0x18007ab0a  xor     rax, rsp
0x18007ab0d  mov     [rsp+98h+var_18], rax
0x18007ab15  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18007ab1a  mov     [rsp+98h+IsMember], 0
0x18007ab22  mov     edx, 1; ImpersonationLevel
0x18007ab27  mov     [rsp+98h+DuplicateTokenHandle], 0
0x18007ab30  call    cs:__imp_DuplicateToken
0x18007ab37  nop     dword ptr [rax+rax+00h]
0x18007ab3c  test    eax, eax
0x18007ab3e  jz      short loc_18007AB93
0x18007ab40  xor     edx, edx; DomainSid
0x18007ab42  mov     [rsp+98h+cbSid], 44h ; 'D'
0x18007ab4a  lea     r9, [rsp+98h+cbSid]; cbSid
0x18007ab4f  lea     r8, [rsp+98h+pSid]; pSid
0x18007ab54  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18007ab57  call    cs:__imp_CreateWellKnownSid
0x18007ab5e  nop     dword ptr [rax+rax+00h]
0x18007ab63  test    eax, eax
0x18007ab65  jz      short loc_18007AB82
0x18007ab67  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x18007ab6c  lea     r8, [rsp+98h+IsMember]; IsMember
0x18007ab71  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x18007ab76  call    cs:__imp_CheckTokenMembership
0x18007ab7d  nop     dword ptr [rax+rax+00h]
0x18007ab82  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x18007ab87  call    cs:__imp_CloseHandle
0x18007ab8e  nop     dword ptr [rax+rax+00h]
0x18007ab93  mov     eax, [rsp+98h+IsMember]
0x18007ab97  mov     rcx, [rsp+98h+var_18]
0x18007ab9f  xor     rcx, rsp; StackCookie
0x18007aba2  call    __security_check_cookie
0x18007aba7  add     rsp, 98h
0x18007abae  retn
```
