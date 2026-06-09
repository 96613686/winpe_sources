# _LUAIsTokenAdmin(void *)

- ea: `0x14006c814`
- end: `0x14006c8ae`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006c9e0`
- `0x14006caf0`

## callees

- `0x140005f30`
- `0x1400062d7`
- `0x14006c814`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14006c88c`
- `KERNEL32!CloseHandle` at `0x14006c88c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14006c848`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14006c848`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14006c869`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14006c869`

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
0x14006c814  sub     rsp, 98h
0x14006c81b  mov     rax, cs:__security_cookie
0x14006c822  xor     rax, rsp
0x14006c825  mov     [rsp+98h+var_18], rax
0x14006c82d  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x14006c832  mov     [rsp+98h+IsMember], 0
0x14006c83a  mov     edx, 1; ImpersonationLevel
0x14006c83f  mov     [rsp+98h+DuplicateTokenHandle], 0
0x14006c848  call    cs:__imp_DuplicateToken
0x14006c84e  test    eax, eax
0x14006c850  jz      short loc_14006C892
0x14006c852  xor     edx, edx; DomainSid
0x14006c854  mov     [rsp+98h+cbSid], 44h ; 'D'
0x14006c85c  lea     r9, [rsp+98h+cbSid]; cbSid
0x14006c861  lea     r8, [rsp+98h+pSid]; pSid
0x14006c866  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x14006c869  call    cs:__imp_CreateWellKnownSid
0x14006c86f  test    eax, eax
0x14006c871  jz      short loc_14006C887
0x14006c873  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x14006c878  lea     r8, [rsp+98h+IsMember]; IsMember
0x14006c87d  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x14006c882  call    CheckTokenMembership_0
0x14006c887  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x14006c88c  call    cs:__imp_CloseHandle
0x14006c892  mov     eax, [rsp+98h+IsMember]
0x14006c896  mov     rcx, [rsp+98h+var_18]
0x14006c89e  xor     rcx, rsp; StackCookie
0x14006c8a1  call    __security_check_cookie
0x14006c8a6  add     rsp, 98h
0x14006c8ad  retn
```
