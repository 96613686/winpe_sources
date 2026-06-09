# FSIsFSMonitorProcess(void *)

- ea: `0x180029d78`
- end: `0x180029e35`
- name: `?FSIsFSMonitorProcess@@YA_NPEAX@Z`
- size: `189`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007d914`

## callees

- `0x180003e20`
- `0x180026f0c`
- `0x180029d78`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180029de9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180029de9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029dfd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029dfd`

## pseudocode

```c
bool __fastcall FSIsFSMonitorProcess(void *a1)
{
  bool v1; // bl
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  v1 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(
         &pIdentifierAuthority,
         6u,
         0x50u,
         0xA320C60B,
         0x8E5BF9Du,
         0xA3D9D00D,
         0xE67373FA,
         0xC7213178,
         0,
         0,
         &SidToCheck)
    && CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v1 = IsMember != 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SidToCheck);
  return v1;
}

```

## disassembly

```asm
0x180029d78  mov     [rsp-8+arg_0], rbx
0x180029d7d  push    rbp
0x180029d7e  mov     rbp, rsp
0x180029d81  sub     rsp, 80h
0x180029d88  mov     rax, cs:__security_cookie
0x180029d8f  xor     rax, rsp
0x180029d92  mov     [rbp+var_8], rax
0x180029d96  xor     ebx, ebx
0x180029d98  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180029d9e  lea     rax, [rbp+SidToCheck]
0x180029da2  mov     [rbp+IsMember], ebx
0x180029da5  mov     [rsp+80h+pSid], rax; pSid
0x180029daa  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180029dae  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x180029db2  mov     r9d, 0A320C60Bh; nSubAuthority1
0x180029db8  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x180029dbc  lea     r8d, [rbx+50h]; nSubAuthority0
0x180029dc0  mov     [rsp+80h+nSubAuthority5], 0C7213178h; nSubAuthority5
0x180029dc8  mov     dl, 6; nSubAuthorityCount
0x180029dca  mov     [rsp+80h+nSubAuthority4], 0E67373FAh; nSubAuthority4
0x180029dd2  mov     [rsp+80h+nSubAuthority3], 0A3D9D00Dh; nSubAuthority3
0x180029dda  mov     [rsp+80h+nSubAuthority2], 8E5BF9Dh; nSubAuthority2
0x180029de2  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x180029de5  mov     [rbp+SidToCheck], rbx
0x180029de9  call    cs:__imp_AllocateAndInitializeSid
0x180029def  test    eax, eax
0x180029df1  jz      short loc_180029E0D
0x180029df3  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180029df7  lea     r8, [rbp+IsMember]; IsMember
0x180029dfb  xor     ecx, ecx; TokenHandle
0x180029dfd  call    cs:__imp_CheckTokenMembership
0x180029e03  test    eax, eax
0x180029e05  jz      short loc_180029E0D
0x180029e07  cmp     [rbp+IsMember], ebx
0x180029e0a  setnz   bl
0x180029e0d  lea     rcx, [rbp+SidToCheck]
0x180029e11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180029e16  mov     al, bl
0x180029e18  mov     rcx, [rbp+var_8]
0x180029e1c  xor     rcx, rsp; StackCookie
0x180029e1f  call    __security_check_cookie
0x180029e24  mov     rbx, [rsp+80h+arg_0]
0x180029e2c  add     rsp, 80h
0x180029e33  pop     rbp
0x180029e34  retn
```
