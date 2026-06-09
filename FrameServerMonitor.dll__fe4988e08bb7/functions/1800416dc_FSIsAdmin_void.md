# FSIsAdmin(void *)

- ea: `0x1800416dc`
- end: `0x18004176f`
- name: `?FSIsAdmin@@YA_NPEAX@Z`
- size: `147`
- prototype: `bool __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002bcc0`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x1800416dc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180041729`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180041729`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180041740`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180041740`

## pseudocode

```c
bool __fastcall FSIsAdmin(HANDLE TokenHandle)
{
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  IsMember = 0;
  return CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid)
      && CheckTokenMembership(TokenHandle, pSid, &IsMember)
      && IsMember != 0;
}

```

## disassembly

```asm
0x1800416dc  push    rbx
0x1800416de  sub     rsp, 90h
0x1800416e5  mov     rax, cs:__security_cookie
0x1800416ec  xor     rax, rsp
0x1800416ef  mov     [rsp+98h+var_18], rax
0x1800416f7  xor     edx, edx; Val
0x1800416f9  mov     rbx, rcx
0x1800416fc  lea     rcx, [rsp+98h+pSid]; void *
0x180041701  lea     r8d, [rdx+44h]; Size
0x180041705  call    memset_0
0x18004170a  xor     edx, edx; DomainSid
0x18004170c  mov     [rsp+98h+cbSid], 44h ; 'D'
0x180041714  lea     r9, [rsp+98h+cbSid]; cbSid
0x180041719  mov     [rsp+98h+IsMember], 0
0x180041721  lea     r8, [rsp+98h+pSid]; pSid
0x180041726  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180041729  call    cs:__imp_CreateWellKnownSid
0x18004172f  test    eax, eax
0x180041731  jz      short loc_180041754
0x180041733  lea     r8, [rsp+98h+IsMember]; IsMember
0x180041738  mov     rcx, rbx; TokenHandle
0x18004173b  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x180041740  call    cs:__imp_CheckTokenMembership
0x180041746  test    eax, eax
0x180041748  jz      short loc_180041754
0x18004174a  cmp     [rsp+98h+IsMember], 0
0x18004174f  setnz   al
0x180041752  jmp     short loc_180041756
0x180041754  xor     al, al
0x180041756  mov     rcx, [rsp+98h+var_18]
0x18004175e  xor     rcx, rsp; StackCookie
0x180041761  call    __security_check_cookie
0x180041766  add     rsp, 90h
0x18004176d  pop     rbx
0x18004176e  retn
```
