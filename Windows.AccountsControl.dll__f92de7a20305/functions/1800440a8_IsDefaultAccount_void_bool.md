# IsDefaultAccount(void *,bool &)

- ea: `0x1800440a8`
- end: `0x18004415e`
- name: `?IsDefaultAccount@@YAJPEAXAEA_N@Z`
- size: `182`
- prototype: `__int64 __fastcall(void *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800183c0`

## callees

- `0x180006e8c`
- `0x1800440a8`
- `0x180069730`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800440ef`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800440ef`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180044122`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180044122`

## pseudocode

```c
__int64 __fastcall IsDefaultAccount(void *a1, bool *a2)
{
  const char *v4; // r9
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *a2 = 0;
  v7 = 0;
  cbSid[0] = 68;
  if ( !CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, pSid, cbSid) )
  {
    v5 = 95;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\utilities.cpp",
             v4);
  }
  if ( !(unsigned int)CheckTokenMembershipEx(a1, pSid, 0, &v7) )
  {
    v5 = 96;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\utilities.cpp",
             v4);
  }
  *a2 = v7 == 1;
  return 0;
}

```

## disassembly

```asm
0x1800440a8  mov     [rsp+arg_10], rbx
0x1800440ad  push    rdi
0x1800440ae  sub     rsp, 90h
0x1800440b5  mov     rax, cs:__security_cookie
0x1800440bc  xor     rax, rsp
0x1800440bf  mov     [rsp+98h+var_18], rax
0x1800440c7  mov     rbx, rdx
0x1800440ca  mov     byte ptr [rdx], 0
0x1800440cd  xor     edx, edx; DomainSid
0x1800440cf  mov     [rsp+98h+var_78], 0
0x1800440d7  mov     rdi, rcx
0x1800440da  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800440e2  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800440e7  lea     r8, [rsp+98h+pSid]; pSid
0x1800440ec  lea     ecx, [rdx+6Fh]; WellKnownSidType
0x1800440ef  call    cs:__imp_CreateWellKnownSid
0x1800440f5  test    eax, eax
0x1800440f7  jnz     short loc_180044112
0x1800440f9  lea     edx, [rax+5Fh]; void *
0x1800440fc  mov     rcx, [rsp+98h]; this
0x180044104  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004410b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180044110  jmp     short loc_18004413D
0x180044112  lea     r9, [rsp+98h+var_78]
0x180044117  xor     r8d, r8d
0x18004411a  lea     rdx, [rsp+98h+pSid]
0x18004411f  mov     rcx, rdi
0x180044122  call    cs:__imp_CheckTokenMembershipEx
0x180044128  test    eax, eax
0x18004412a  jnz     short loc_180044131
0x18004412c  lea     edx, [rax+60h]
0x18004412f  jmp     short loc_1800440FC
0x180044131  cmp     [rsp+98h+var_78], 1
0x180044136  setz    al
0x180044139  mov     [rbx], al
0x18004413b  xor     eax, eax
0x18004413d  mov     rcx, [rsp+98h+var_18]
0x180044145  xor     rcx, rsp; StackCookie
0x180044148  call    __security_check_cookie
0x18004414d  mov     rbx, [rsp+98h+arg_10]
0x180044155  add     rsp, 90h
0x18004415c  pop     rdi
0x18004415d  retn
```
