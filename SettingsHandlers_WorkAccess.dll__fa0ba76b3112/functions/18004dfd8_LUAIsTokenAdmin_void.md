# _LUAIsTokenAdmin(void *)

- ea: `0x18004dfd8`
- end: `0x18004e08c`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `180`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004e190`
- `0x18004e2d4`

## callees

- `0x180002a60`
- `0x18004dfd8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e063`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18004e00c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18004e00c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004e033`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004e033`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004e052`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004e052`

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
0x18004dfd8  sub     rsp, 98h
0x18004dfdf  mov     rax, cs:__security_cookie
0x18004dfe6  xor     rax, rsp
0x18004dfe9  mov     [rsp+98h+var_18], rax
0x18004dff1  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18004dff6  mov     [rsp+98h+IsMember], 0
0x18004dffe  mov     edx, 1; ImpersonationLevel
0x18004e003  mov     [rsp+98h+DuplicateTokenHandle], 0
0x18004e00c  call    cs:__imp_DuplicateToken
0x18004e013  nop     dword ptr [rax+rax+00h]
0x18004e018  test    eax, eax
0x18004e01a  jz      short loc_18004E06F
0x18004e01c  xor     edx, edx; DomainSid
0x18004e01e  mov     [rsp+98h+cbSid], 44h ; 'D'
0x18004e026  lea     r9, [rsp+98h+cbSid]; cbSid
0x18004e02b  lea     r8, [rsp+98h+pSid]; pSid
0x18004e030  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18004e033  call    cs:__imp_CreateWellKnownSid
0x18004e03a  nop     dword ptr [rax+rax+00h]
0x18004e03f  test    eax, eax
0x18004e041  jz      short loc_18004E05E
0x18004e043  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x18004e048  lea     r8, [rsp+98h+IsMember]; IsMember
0x18004e04d  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x18004e052  call    cs:__imp_CheckTokenMembership
0x18004e059  nop     dword ptr [rax+rax+00h]
0x18004e05e  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x18004e063  call    cs:__imp_CloseHandle
0x18004e06a  nop     dword ptr [rax+rax+00h]
0x18004e06f  mov     eax, [rsp+98h+IsMember]
0x18004e073  mov     rcx, [rsp+98h+var_18]
0x18004e07b  xor     rcx, rsp; StackCookie
0x18004e07e  call    __security_check_cookie
0x18004e083  add     rsp, 98h
0x18004e08a  retn
```
