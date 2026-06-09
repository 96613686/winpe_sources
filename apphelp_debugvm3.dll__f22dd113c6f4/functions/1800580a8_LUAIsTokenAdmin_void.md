# _LUAIsTokenAdmin(void *)

- ea: `0x1800580a8`
- end: `0x180058143`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `155`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005823c`
- `0x18005834c`

## callees

- `0x1800580a8`
- `0x1800591b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058121`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800580fd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800580fd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180058116`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180058116`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800580dc`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800580dc`

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
0x1800580a8  sub     rsp, 98h
0x1800580af  mov     rax, cs:__security_cookie
0x1800580b6  xor     rax, rsp
0x1800580b9  mov     [rsp+98h+var_18], rax
0x1800580c1  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800580c6  mov     [rsp+98h+IsMember], 0
0x1800580ce  mov     edx, 1; ImpersonationLevel
0x1800580d3  mov     [rsp+98h+DuplicateTokenHandle], 0
0x1800580dc  call    cs:__imp_DuplicateToken
0x1800580e2  test    eax, eax
0x1800580e4  jz      short loc_180058127
0x1800580e6  xor     edx, edx; DomainSid
0x1800580e8  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800580f0  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800580f5  lea     r8, [rsp+98h+pSid]; pSid
0x1800580fa  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800580fd  call    cs:__imp_CreateWellKnownSid
0x180058103  test    eax, eax
0x180058105  jz      short loc_18005811C
0x180058107  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x18005810c  lea     r8, [rsp+98h+IsMember]; IsMember
0x180058111  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x180058116  call    cs:__imp_CheckTokenMembership
0x18005811c  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x180058121  call    cs:__imp_CloseHandle
0x180058127  mov     eax, [rsp+98h+IsMember]
0x18005812b  mov     rcx, [rsp+98h+var_18]
0x180058133  xor     rcx, rsp; StackCookie
0x180058136  call    __security_check_cookie
0x18005813b  add     rsp, 98h
0x180058142  retn
```
