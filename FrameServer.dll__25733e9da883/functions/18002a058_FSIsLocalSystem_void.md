# FSIsLocalSystem(void *)

- ea: `0x18002a058`
- end: `0x18002a0e4`
- name: `?FSIsLocalSystem@@YA_NPEAX@Z`
- size: `140`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007d914`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x18002a058`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002a0a0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002a0a0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002a0b6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002a0b6`

## pseudocode

```c
bool __fastcall FSIsLocalSystem(void *a1)
{
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  IsMember = 0;
  return CreateWellKnownSid(WinLocalSystemSid, 0, pSid, cbSid)
      && CheckTokenMembership(0, pSid, &IsMember)
      && IsMember != 0;
}

```

## disassembly

```asm
0x18002a058  sub     rsp, 98h
0x18002a05f  mov     rax, cs:__security_cookie
0x18002a066  xor     rax, rsp
0x18002a069  mov     [rsp+98h+var_18], rax
0x18002a071  xor     edx, edx; Val
0x18002a073  lea     rcx, [rsp+98h+pSid]; void *
0x18002a078  lea     r8d, [rdx+44h]; Size
0x18002a07c  call    memset_0
0x18002a081  xor     edx, edx; DomainSid
0x18002a083  mov     [rsp+98h+cbSid], 44h ; 'D'
0x18002a08b  lea     r9, [rsp+98h+cbSid]; cbSid
0x18002a090  mov     [rsp+98h+IsMember], 0
0x18002a098  lea     r8, [rsp+98h+pSid]; pSid
0x18002a09d  lea     ecx, [rdx+16h]; WellKnownSidType
0x18002a0a0  call    cs:__imp_CreateWellKnownSid
0x18002a0a6  test    eax, eax
0x18002a0a8  jz      short loc_18002A0CA
0x18002a0aa  lea     r8, [rsp+98h+IsMember]; IsMember
0x18002a0af  xor     ecx, ecx; TokenHandle
0x18002a0b1  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x18002a0b6  call    cs:__imp_CheckTokenMembership
0x18002a0bc  test    eax, eax
0x18002a0be  jz      short loc_18002A0CA
0x18002a0c0  cmp     [rsp+98h+IsMember], 0
0x18002a0c5  setnz   al
0x18002a0c8  jmp     short loc_18002A0CC
0x18002a0ca  xor     al, al
0x18002a0cc  mov     rcx, [rsp+98h+var_18]
0x18002a0d4  xor     rcx, rsp; StackCookie
0x18002a0d7  call    __security_check_cookie
0x18002a0dc  add     rsp, 98h
0x18002a0e3  retn
```
