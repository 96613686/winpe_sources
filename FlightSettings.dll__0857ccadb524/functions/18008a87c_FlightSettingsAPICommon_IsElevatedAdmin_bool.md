# FlightSettingsAPICommon::IsElevatedAdmin(bool *)

- ea: `0x18008a87c`
- end: `0x18008a9b8`
- name: `?IsElevatedAdmin@FlightSettingsAPICommon@@CAJPEA_N@Z`
- size: `316`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008ac30`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x18008a87c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a91a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a91a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a951`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18008a947`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18008a947`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18008a910`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18008a910`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008a973`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008a98f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008a973`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008a98f`

## string_xrefs

- `0x18008a8b7`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`

## pseudocode

```c
__int64 __fastcall FlightSettingsAPICommon::IsElevatedAdmin(bool *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  signed int LastError; // eax
  signed int v6; // eax
  PSID v7; // rcx
  DWORD nSubAuthority2; // [rsp+20h] [rbp-60h]
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 171;
    goto LABEL_3;
  }
  IsMember = 0;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (v2 & 0x80000000) == 0 )
      return v2;
    v3 = 186;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
      (const char *)v2,
      nSubAuthority2);
    return v2;
  }
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v6 = GetLastError();
    v2 = v6;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    if ( SidToCheck )
      FreeSid(SidToCheck);
    return v2;
  }
  v7 = SidToCheck;
  *a1 = IsMember != 0;
  if ( v7 )
    FreeSid(v7);
  return 0;
}

```

## disassembly

```asm
0x18008a87c  mov     [rsp-8+arg_8], rbx
0x18008a881  mov     [rsp-8+arg_10], rdi
0x18008a886  push    rbp
0x18008a887  mov     rbp, rsp
0x18008a88a  sub     rsp, 80h
0x18008a891  mov     rax, cs:__security_cookie
0x18008a898  xor     rax, rsp
0x18008a89b  mov     [rbp+var_8], rax
0x18008a89f  xor     edi, edi
0x18008a8a1  mov     rbx, rcx
0x18008a8a4  test    rcx, rcx
0x18008a8a7  jnz     short loc_18008A8CD
0x18008a8a9  mov     ebx, 80070057h
0x18008a8ae  mov     edx, 0ABh; void *
0x18008a8b3  mov     rcx, [rbp+8]; this
0x18008a8b7  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x18008a8be  mov     r9d, ebx; char *
0x18008a8c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a8c6  mov     eax, ebx
0x18008a8c8  jmp     loc_18008A997
0x18008a8cd  lea     rax, [rbp+SidToCheck]
0x18008a8d1  mov     [rbp+IsMember], edi
0x18008a8d4  mov     [rsp+80h+pSid], rax; pSid
0x18008a8d9  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18008a8dd  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18008a8e1  mov     r9d, 220h; nSubAuthority1
0x18008a8e7  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x18008a8eb  mov     r8d, 20h ; ' '; nSubAuthority0
0x18008a8f1  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18008a8f5  mov     dl, 2; nSubAuthorityCount
0x18008a8f7  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x18008a8fb  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18008a8ff  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x18008a903  mov     [rbp+SidToCheck], rdi
0x18008a907  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x18008a90a  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18008a910  call    cs:__imp_AllocateAndInitializeSid
0x18008a916  test    eax, eax
0x18008a918  jnz     short loc_18008A93D
0x18008a91a  call    cs:__imp_GetLastError
0x18008a920  mov     ebx, eax
0x18008a922  test    eax, eax
0x18008a924  jle     short loc_18008A92F
0x18008a926  movzx   ebx, ax
0x18008a929  or      ebx, 80070000h
0x18008a92f  test    ebx, ebx
0x18008a931  jns     short loc_18008A8C6
0x18008a933  mov     edx, 0BAh
0x18008a938  jmp     loc_18008A8B3
0x18008a93d  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18008a941  lea     r8, [rbp+IsMember]; IsMember
0x18008a945  xor     ecx, ecx; TokenHandle
0x18008a947  call    cs:__imp_CheckTokenMembership
0x18008a94d  test    eax, eax
0x18008a94f  jnz     short loc_18008A97E
0x18008a951  call    cs:__imp_GetLastError
0x18008a957  mov     ebx, eax
0x18008a959  test    eax, eax
0x18008a95b  jle     short loc_18008A966
0x18008a95d  movzx   ebx, ax
0x18008a960  or      ebx, 80070000h
0x18008a966  mov     rcx, [rbp+SidToCheck]; pSid
0x18008a96a  test    rcx, rcx
0x18008a96d  jz      loc_18008A8C6
0x18008a973  call    cs:__imp_FreeSid
0x18008a979  jmp     loc_18008A8C6
0x18008a97e  cmp     [rbp+IsMember], edi
0x18008a981  mov     rcx, [rbp+SidToCheck]; pSid
0x18008a985  setnz   al
0x18008a988  mov     [rbx], al
0x18008a98a  test    rcx, rcx
0x18008a98d  jz      short loc_18008A995
0x18008a98f  call    cs:__imp_FreeSid
0x18008a995  xor     eax, eax
0x18008a997  mov     rcx, [rbp+var_8]
0x18008a99b  xor     rcx, rsp; StackCookie
0x18008a99e  call    __security_check_cookie
0x18008a9a3  lea     r11, [rsp+80h+var_s0]
0x18008a9ab  mov     rbx, [r11+18h]
0x18008a9af  mov     rdi, [r11+20h]
0x18008a9b3  mov     rsp, r11
0x18008a9b6  pop     rbp
0x18008a9b7  retn
```
