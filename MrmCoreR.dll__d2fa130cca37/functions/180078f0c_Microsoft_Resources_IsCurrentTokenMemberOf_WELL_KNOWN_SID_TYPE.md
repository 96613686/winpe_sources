# Microsoft::Resources::IsCurrentTokenMemberOf(WELL_KNOWN_SID_TYPE)

- ea: `0x180078f0c`
- end: `0x180078f85`
- name: `?IsCurrentTokenMemberOf@Resources@Microsoft@@YA_NW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `121`
- prototype: `bool __fastcall(Microsoft::Resources *__hidden this, enum WELL_KNOWN_SID_TYPE)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007e84`

## callees

- `0x180078f0c`
- `0x1800862f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180078f57`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180078f57`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180078f39`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180078f39`

## pseudocode

```c
bool __fastcall Microsoft::Resources::IsCurrentTokenMemberOf(Microsoft::Resources *this, enum WELL_KNOWN_SID_TYPE a2)
{
  bool result; // al
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  cbSid[0] = 68;
  result = CreateWellKnownSid((WELL_KNOWN_SID_TYPE)this, 0, pSid, cbSid)
        && (IsMember = 0, CheckTokenMembership(0, pSid, &IsMember))
        && IsMember != 0;
  return result;
}

```

## disassembly

```asm
0x180078f0c  sub     rsp, 98h
0x180078f13  mov     rax, cs:__security_cookie
0x180078f1a  xor     rax, rsp
0x180078f1d  mov     [rsp+98h+var_18], rax
0x180078f25  lea     r9, [rsp+98h+cbSid]; cbSid
0x180078f2a  mov     [rsp+98h+cbSid], 44h ; 'D'
0x180078f32  lea     r8, [rsp+98h+pSid]; pSid
0x180078f37  xor     edx, edx; DomainSid
0x180078f39  call    cs:__imp_CreateWellKnownSid
0x180078f3f  test    eax, eax
0x180078f41  jz      short loc_180078F61
0x180078f43  lea     r8, [rsp+98h+IsMember]; IsMember
0x180078f48  mov     [rsp+98h+IsMember], 0
0x180078f50  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x180078f55  xor     ecx, ecx; TokenHandle
0x180078f57  call    cs:__imp_CheckTokenMembership
0x180078f5d  test    eax, eax
0x180078f5f  jnz     short loc_180078F7B
0x180078f61  xor     al, al
0x180078f63  mov     rcx, [rsp+98h+var_18]
0x180078f6b  xor     rcx, rsp; StackCookie
0x180078f6e  call    __security_check_cookie
0x180078f73  add     rsp, 98h
0x180078f7a  retn
0x180078f7b  cmp     [rsp+98h+IsMember], 0
0x180078f80  setnz   al
0x180078f83  jmp     short loc_180078F63
```
