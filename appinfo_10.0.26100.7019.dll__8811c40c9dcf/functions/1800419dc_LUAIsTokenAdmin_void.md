# _LUAIsTokenAdmin(void *)

- ea: `0x1800419dc`
- end: `0x180041a7c`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `160`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017850`

## callees

- `0x18001bc88`
- `0x18001bead`
- `0x1800419dc`
- `0x180042950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180041a2a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180041a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041a53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041a53`

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
  if ( DuplicateToken_0(a1, SecurityIdentification, &DuplicateTokenHandle) )
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
0x1800419dc  sub     rsp, 98h
0x1800419e3  mov     rax, cs:__security_cookie
0x1800419ea  xor     rax, rsp
0x1800419ed  mov     [rsp+98h+var_18], rax
0x1800419f5  and     [rsp+98h+IsMember], 0
0x1800419fa  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800419ff  and     [rsp+98h+DuplicateTokenHandle], 0
0x180041a05  mov     edx, 1; ImpersonationLevel
0x180041a0a  call    DuplicateToken_0
0x180041a0f  test    eax, eax
0x180041a11  jz      short loc_180041A5F
0x180041a13  xor     edx, edx; DomainSid
0x180041a15  mov     [rsp+98h+cbSid], 44h ; 'D'
0x180041a1d  lea     r9, [rsp+98h+cbSid]; cbSid
0x180041a22  lea     r8, [rsp+98h+pSid]; pSid
0x180041a27  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180041a2a  call    cs:__imp_CreateWellKnownSid
0x180041a31  nop     dword ptr [rax+rax+00h]
0x180041a36  test    eax, eax
0x180041a38  jz      short loc_180041A4E
0x180041a3a  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x180041a3f  lea     r8, [rsp+98h+IsMember]; IsMember
0x180041a44  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x180041a49  call    CheckTokenMembership_0
0x180041a4e  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x180041a53  call    cs:__imp_CloseHandle
0x180041a5a  nop     dword ptr [rax+rax+00h]
0x180041a5f  mov     eax, [rsp+98h+IsMember]
0x180041a63  mov     rcx, [rsp+98h+var_18]
0x180041a6b  xor     rcx, rsp; StackCookie
0x180041a6e  call    __security_check_cookie
0x180041a73  add     rsp, 98h
0x180041a7a  retn
```
