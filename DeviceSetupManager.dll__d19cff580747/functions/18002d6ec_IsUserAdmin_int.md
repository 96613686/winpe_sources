# IsUserAdmin(int *)

- ea: `0x18002d6ec`
- end: `0x18002d78a`
- name: `?IsUserAdmin@@YAJPEAH@Z`
- size: `158`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d610`

## callees

- `0x18001af70`
- `0x18002d6ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d75f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d75f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002d751`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002d751`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d727`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d727`

## pseudocode

```c
signed int __fastcall IsUserAdmin(PBOOL IsMember)
{
  signed int result; // eax
  bool v3; // sf
  DWORD cbSid[4]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  *IsMember = 0;
  cbSid[0] = 68;
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
    goto LABEL_11;
  result = GetLastError();
  v3 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v3 = result < 0;
  }
  if ( !v3 )
  {
LABEL_11:
    if ( CheckTokenMembership(0, pSid, IsMember) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002d6ec  push    rbx
0x18002d6ee  sub     rsp, 90h
0x18002d6f5  mov     rax, cs:__security_cookie
0x18002d6fc  xor     rax, rsp
0x18002d6ff  mov     [rsp+98h+var_18], rax
0x18002d707  xor     edx, edx; DomainSid
0x18002d709  mov     dword ptr [rcx], 0
0x18002d70f  mov     rbx, rcx
0x18002d712  mov     [rsp+98h+cbSid], 44h ; 'D'
0x18002d71a  lea     r9, [rsp+98h+cbSid]; cbSid
0x18002d71f  lea     r8, [rsp+98h+pSid]; pSid
0x18002d724  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18002d727  call    cs:__imp_CreateWellKnownSid
0x18002d72d  test    eax, eax
0x18002d72f  jnz     short loc_18002D747
0x18002d731  call    cs:__imp_GetLastError
0x18002d737  test    eax, eax
0x18002d739  jle     short loc_18002D745
0x18002d73b  movzx   eax, ax
0x18002d73e  or      eax, 80070000h
0x18002d743  test    eax, eax
0x18002d745  js      short loc_18002D771
0x18002d747  mov     r8, rbx; IsMember
0x18002d74a  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x18002d74f  xor     ecx, ecx; TokenHandle
0x18002d751  call    cs:__imp_CheckTokenMembership
0x18002d757  test    eax, eax
0x18002d759  jz      short loc_18002D75F
0x18002d75b  xor     eax, eax
0x18002d75d  jmp     short loc_18002D771
0x18002d75f  call    cs:__imp_GetLastError
0x18002d765  test    eax, eax
0x18002d767  jle     short loc_18002D771
0x18002d769  movzx   eax, ax
0x18002d76c  or      eax, 80070000h
0x18002d771  mov     rcx, [rsp+98h+var_18]
0x18002d779  xor     rcx, rsp; StackCookie
0x18002d77c  call    __security_check_cookie
0x18002d781  add     rsp, 90h
0x18002d788  pop     rbx
0x18002d789  retn
```
