# FSIsLocalSystem(void *)

- ea: `0x180041ca0`
- end: `0x180041d33`
- name: `?FSIsLocalSystem@@YA_NPEAX@Z`
- size: `147`
- prototype: `bool __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002bcc0`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180041ca0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180041ced`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180041ced`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180041d04`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180041d04`

## pseudocode

```c
bool __fastcall FSIsLocalSystem(HANDLE TokenHandle)
{
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  IsMember = 0;
  return CreateWellKnownSid(WinLocalSystemSid, 0, pSid, cbSid)
      && CheckTokenMembership(TokenHandle, pSid, &IsMember)
      && IsMember != 0;
}

```

## disassembly

```asm
0x180041ca0  push    rbx
0x180041ca2  sub     rsp, 90h
0x180041ca9  mov     rax, cs:__security_cookie
0x180041cb0  xor     rax, rsp
0x180041cb3  mov     [rsp+98h+var_18], rax
0x180041cbb  xor     edx, edx; Val
0x180041cbd  mov     rbx, rcx
0x180041cc0  lea     rcx, [rsp+98h+pSid]; void *
0x180041cc5  lea     r8d, [rdx+44h]; Size
0x180041cc9  call    memset_0
0x180041cce  xor     edx, edx; DomainSid
0x180041cd0  mov     [rsp+98h+cbSid], 44h ; 'D'
0x180041cd8  lea     r9, [rsp+98h+cbSid]; cbSid
0x180041cdd  mov     [rsp+98h+IsMember], 0
0x180041ce5  lea     r8, [rsp+98h+pSid]; pSid
0x180041cea  lea     ecx, [rdx+16h]; WellKnownSidType
0x180041ced  call    cs:__imp_CreateWellKnownSid
0x180041cf3  test    eax, eax
0x180041cf5  jz      short loc_180041D18
0x180041cf7  lea     r8, [rsp+98h+IsMember]; IsMember
0x180041cfc  mov     rcx, rbx; TokenHandle
0x180041cff  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x180041d04  call    cs:__imp_CheckTokenMembership
0x180041d0a  test    eax, eax
0x180041d0c  jz      short loc_180041D18
0x180041d0e  cmp     [rsp+98h+IsMember], 0
0x180041d13  setnz   al
0x180041d16  jmp     short loc_180041D1A
0x180041d18  xor     al, al
0x180041d1a  mov     rcx, [rsp+98h+var_18]
0x180041d22  xor     rcx, rsp; StackCookie
0x180041d25  call    __security_check_cookie
0x180041d2a  add     rsp, 90h
0x180041d31  pop     rbx
0x180041d32  retn
```
