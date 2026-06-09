# DcaUtil::CheckTokenMembershipSubAuthority0(void *,ulong,bool *)

- ea: `0x1800a5914`
- end: `0x1800a5a00`
- name: `?CheckTokenMembershipSubAuthority0@DcaUtil@@YAJPEAXKPEA_N@Z`
- size: `236`
- prototype: `__int64 __fastcall(DcaUtil *__hidden this, void *, unsigned int, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004fe40`
- `0x1800a7488`

## callees

- `0x180007964`
- `0x18005cee0`
- `0x1800a5914`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800a597a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800a597a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800a59d9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800a59d9`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800a59aa`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800a59aa`

## string_xrefs

- `0x1800a5988`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a59b8`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall DcaUtil::CheckTokenMembershipSubAuthority0(DcaUtil *this, void *a2, bool *a3, bool *a4)
{
  const char *v6; // r9
  const char *v8; // r9
  unsigned int LastError; // ebx
  int v10; // [rsp+60h] [rbp-20h] BYREF
  PSID pSid; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *a3 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x35,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
             v6);
  v10 = 0;
  if ( (unsigned int)CheckTokenMembershipEx(this, pSid, 0, &v10) )
  {
    *a3 = v10 != 0;
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x41,
                  (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
                  v8);
  }
  FreeSid(pSid);
  return LastError;
}

```

## disassembly

```asm
0x1800a5914  mov     [rsp-18h+arg_8], rbx
0x1800a5919  push    rbp
0x1800a591a  push    rsi
0x1800a591b  push    rdi
0x1800a591c  mov     rbp, rsp
0x1800a591f  sub     rsp, 80h
0x1800a5926  mov     rax, cs:__security_cookie
0x1800a592d  xor     rax, rsp
0x1800a5930  mov     [rbp+var_8], rax
0x1800a5934  xor     esi, esi
0x1800a5936  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800a593c  lea     rax, [rbp+var_18]
0x1800a5940  mov     [r8], sil
0x1800a5943  mov     [rsp+80h+pSid], rax; pSid
0x1800a5948  mov     rbx, r8
0x1800a594b  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x1800a594f  mov     rdi, rcx
0x1800a5952  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x1800a5956  lea     r8d, [rsi+12h]; nSubAuthority0
0x1800a595a  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x1800a595e  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800a5962  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x1800a5966  xor     r9d, r9d; nSubAuthority1
0x1800a5969  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x1800a596d  mov     dl, 1; nSubAuthorityCount
0x1800a596f  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x1800a5973  mov     dword ptr [rbp+pIdentifierAuthority.Value], esi
0x1800a5976  mov     [rbp+var_18], rsi
0x1800a597a  call    cs:__imp_AllocateAndInitializeSid
0x1800a5980  test    eax, eax
0x1800a5982  jnz     short loc_1800A5999
0x1800a5984  mov     rcx, [rbp+18h]; this
0x1800a5988  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a598f  lea     edx, [rsi+35h]; void *
0x1800a5992  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a5997  jmp     short loc_1800A59E1
0x1800a5999  mov     rdx, [rbp+var_18]
0x1800a599d  lea     r9, [rbp+var_20]
0x1800a59a1  xor     r8d, r8d
0x1800a59a4  mov     [rbp+var_20], esi
0x1800a59a7  mov     rcx, rdi
0x1800a59aa  call    cs:__imp_CheckTokenMembershipEx
0x1800a59b0  test    eax, eax
0x1800a59b2  jnz     short loc_1800A59CB
0x1800a59b4  mov     rcx, [rbp+18h]; this
0x1800a59b8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a59bf  lea     edx, [rax+41h]; void *
0x1800a59c2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a59c7  mov     ebx, eax
0x1800a59c9  jmp     short loc_1800A59D5
0x1800a59cb  cmp     [rbp+var_20], esi
0x1800a59ce  setnz   al
0x1800a59d1  mov     [rbx], al
0x1800a59d3  mov     ebx, esi
0x1800a59d5  mov     rcx, [rbp+var_18]; pSid
0x1800a59d9  call    cs:__imp_FreeSid
0x1800a59df  mov     eax, ebx
0x1800a59e1  mov     rcx, [rbp+var_8]
0x1800a59e5  xor     rcx, rsp; StackCookie
0x1800a59e8  call    __security_check_cookie
0x1800a59ed  mov     rbx, [rsp+80h+arg_8]
0x1800a59f5  add     rsp, 80h
0x1800a59fc  pop     rdi
0x1800a59fd  pop     rsi
0x1800a59fe  pop     rbp
0x1800a59ff  retn
```
