# Windows::Internal::AssignedAccess::UserSessionHelper::IsUserDeviceOwner(void *)

- ea: `0x18004f418`
- end: `0x18004f4ce`
- name: `?IsUserDeviceOwner@UserSessionHelper@AssignedAccess@Internal@Windows@@CA_NPEAX@Z`
- size: `182`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004f300`

## callees

- `0x180006640`
- `0x18004f418`
- `0x18004fd00`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004f459`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004f459`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18004f485`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18004f485`

## pseudocode

```c
char __fastcall Windows::Internal::AssignedAccess::UserSessionHelper::IsUserDeviceOwner(void *a1)
{
  char v1; // bl
  unsigned int v3; // r8d
  const char *v4; // r9
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v1 = 0;
  if ( a1 != (void *)-1LL )
  {
    cbSid[0] = 68;
    if ( CreateWellKnownSid(WinAuthenticationAuthorityAssertedSid|WinSelfSid, 0, pSid, cbSid) )
    {
      v7 = 0;
      if ( (unsigned int)CheckTokenMembershipEx(a1, pSid, 1, &v7) )
        return v7 != 0;
      v5 = 170;
    }
    else
    {
      v5 = 167;
    }
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)v5, v3, v4);
  }
  return v1;
}

```

## disassembly

```asm
0x18004f418  mov     [rsp+arg_8], rbx
0x18004f41d  push    rdi
0x18004f41e  sub     rsp, 90h
0x18004f425  mov     rax, cs:__security_cookie
0x18004f42c  xor     rax, rsp
0x18004f42f  mov     [rsp+98h+var_18], rax
0x18004f437  xor     bl, bl
0x18004f439  mov     rdi, rcx
0x18004f43c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004f440  jz      short loc_18004F4AB
0x18004f442  xor     edx, edx; DomainSid
0x18004f444  mov     [rsp+98h+cbSid], 44h ; 'D'
0x18004f44c  lea     r9, [rsp+98h+cbSid]; cbSid
0x18004f451  lea     r8, [rsp+98h+pSid]; pSid
0x18004f456  lea     ecx, [rdx+77h]; WellKnownSidType
0x18004f459  call    cs:__imp_CreateWellKnownSid
0x18004f45f  test    eax, eax
0x18004f461  jnz     short loc_18004F46A
0x18004f463  mov     edx, 0A7h
0x18004f468  jmp     short loc_18004F494
0x18004f46a  lea     r9, [rsp+98h+var_78]
0x18004f46f  mov     [rsp+98h+var_78], 0
0x18004f477  mov     r8d, 1
0x18004f47d  lea     rdx, [rsp+98h+pSid]
0x18004f482  mov     rcx, rdi
0x18004f485  call    cs:__imp_CheckTokenMembershipEx
0x18004f48b  test    eax, eax
0x18004f48d  jnz     short loc_18004F4A3
0x18004f48f  mov     edx, 0AAh; void *
0x18004f494  mov     rcx, [rsp+98h]; this
0x18004f49c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18004f4a1  jmp     short loc_18004F4AB
0x18004f4a3  cmp     [rsp+98h+var_78], 0
0x18004f4a8  setnz   bl
0x18004f4ab  mov     al, bl
0x18004f4ad  mov     rcx, [rsp+98h+var_18]
0x18004f4b5  xor     rcx, rsp; StackCookie
0x18004f4b8  call    __security_check_cookie
0x18004f4bd  mov     rbx, [rsp+98h+arg_8]
0x18004f4c5  add     rsp, 90h
0x18004f4cc  pop     rdi
0x18004f4cd  retn
```
