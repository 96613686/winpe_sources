# FSIsAdmin(void *)

- ea: `0x180029c24`
- end: `0x180029cb0`
- name: `?FSIsAdmin@@YA_NPEAX@Z`
- size: `140`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007d914`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180029c24`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180029c6c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180029c6c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029c82`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029c82`

## pseudocode

```c
bool __fastcall FSIsAdmin(void *a1)
{
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  IsMember = 0;
  return CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid)
      && CheckTokenMembership(0, pSid, &IsMember)
      && IsMember != 0;
}

```

## disassembly

```asm
0x180029c24  sub     rsp, 98h
0x180029c2b  mov     rax, cs:__security_cookie
0x180029c32  xor     rax, rsp
0x180029c35  mov     [rsp+98h+var_18], rax
0x180029c3d  xor     edx, edx; Val
0x180029c3f  lea     rcx, [rsp+98h+pSid]; void *
0x180029c44  lea     r8d, [rdx+44h]; Size
0x180029c48  call    memset_0
0x180029c4d  xor     edx, edx; DomainSid
0x180029c4f  mov     [rsp+98h+cbSid], 44h ; 'D'
0x180029c57  lea     r9, [rsp+98h+cbSid]; cbSid
0x180029c5c  mov     [rsp+98h+IsMember], 0
0x180029c64  lea     r8, [rsp+98h+pSid]; pSid
0x180029c69  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180029c6c  call    cs:__imp_CreateWellKnownSid
0x180029c72  test    eax, eax
0x180029c74  jz      short loc_180029C96
0x180029c76  lea     r8, [rsp+98h+IsMember]; IsMember
0x180029c7b  xor     ecx, ecx; TokenHandle
0x180029c7d  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x180029c82  call    cs:__imp_CheckTokenMembership
0x180029c88  test    eax, eax
0x180029c8a  jz      short loc_180029C96
0x180029c8c  cmp     [rsp+98h+IsMember], 0
0x180029c91  setnz   al
0x180029c94  jmp     short loc_180029C98
0x180029c96  xor     al, al
0x180029c98  mov     rcx, [rsp+98h+var_18]
0x180029ca0  xor     rcx, rsp; StackCookie
0x180029ca3  call    __security_check_cookie
0x180029ca8  add     rsp, 98h
0x180029caf  retn
```
