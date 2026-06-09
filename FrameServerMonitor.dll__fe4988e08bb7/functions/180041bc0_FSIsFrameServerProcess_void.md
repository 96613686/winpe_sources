# FSIsFrameServerProcess(void *)

- ea: `0x180041bc0`
- end: `0x180041c9a`
- name: `?FSIsFrameServerProcess@@YA_NPEAX@Z`
- size: `218`
- prototype: `bool __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002bcc0`

## callees

- `0x1800019f0`
- `0x18003f624`
- `0x180041bc0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180041c5d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180041c5d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180041c48`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180041c48`

## pseudocode

```c
bool __fastcall FSIsFrameServerProcess(HANDLE TokenHandle)
{
  bool v2; // bl
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  v2 = AllocateAndInitializeSid(
         &pIdentifierAuthority,
         6u,
         0x50u,
         0xE967CCF4,
         0x7D6A138Du,
         0xB5A1A4F6,
         0x6BFBC5BAu,
         0x2E2D1C23u,
         0,
         0,
         &SidToCheck)
    && CheckTokenMembership(TokenHandle, SidToCheck, &IsMember)
    && IsMember != 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SidToCheck);
  return v2;
}

```

## disassembly

```asm
0x180041bc0  mov     [rsp-8+arg_8], rbx
0x180041bc5  push    rbp
0x180041bc6  mov     rbp, rsp
0x180041bc9  sub     rsp, 80h
0x180041bd0  mov     rax, cs:__security_cookie
0x180041bd7  xor     rax, rsp
0x180041bda  mov     [rbp+var_8], rax
0x180041bde  lea     rax, [rbp+SidToCheck]
0x180041be2  mov     [rbp+IsMember], 0
0x180041be9  mov     [rsp+80h+pSid], rax; pSid
0x180041bee  mov     rbx, rcx
0x180041bf1  mov     [rsp+80h+nSubAuthority7], 0; nSubAuthority7
0x180041bf9  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180041bfd  mov     [rsp+80h+nSubAuthority6], 0; nSubAuthority6
0x180041c05  mov     r9d, 0E967CCF4h; nSubAuthority1
0x180041c0b  mov     [rsp+80h+nSubAuthority5], 2E2D1C23h; nSubAuthority5
0x180041c13  mov     r8d, 50h ; 'P'; nSubAuthority0
0x180041c19  mov     [rsp+80h+nSubAuthority4], 6BFBC5BAh; nSubAuthority4
0x180041c21  mov     dl, 6; nSubAuthorityCount
0x180041c23  mov     [rsp+80h+nSubAuthority3], 0B5A1A4F6h; nSubAuthority3
0x180041c2b  mov     [rsp+80h+nSubAuthority2], 7D6A138Dh; nSubAuthority2
0x180041c33  mov     dword ptr [rbp+pIdentifierAuthority.Value], 0
0x180041c3a  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180041c40  mov     [rbp+SidToCheck], 0
0x180041c48  call    cs:__imp_AllocateAndInitializeSid
0x180041c4e  test    eax, eax
0x180041c50  jz      short loc_180041C70
0x180041c52  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180041c56  lea     r8, [rbp+IsMember]; IsMember
0x180041c5a  mov     rcx, rbx; TokenHandle
0x180041c5d  call    cs:__imp_CheckTokenMembership
0x180041c63  test    eax, eax
0x180041c65  jz      short loc_180041C70
0x180041c67  cmp     [rbp+IsMember], 0
0x180041c6b  setnz   bl
0x180041c6e  jmp     short loc_180041C72
0x180041c70  xor     bl, bl
0x180041c72  lea     rcx, [rbp+SidToCheck]
0x180041c76  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180041c7b  mov     al, bl
0x180041c7d  mov     rcx, [rbp+var_8]
0x180041c81  xor     rcx, rsp; StackCookie
0x180041c84  call    __security_check_cookie
0x180041c89  mov     rbx, [rsp+80h+arg_8]
0x180041c91  add     rsp, 80h
0x180041c98  pop     rbp
0x180041c99  retn
```
