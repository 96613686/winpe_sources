# FlightSettingsAPICommon::IsLocalSystem(bool *)

- ea: `0x18008aaf0`
- end: `0x18008ac27`
- name: `?IsLocalSystem@FlightSettingsAPICommon@@SAJPEA_N@Z`
- size: `311`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180089dfc`
- `0x18008a81c`
- `0x18008ac30`
- `0x180090a00`
- `0x1800b2e58`
- `0x1800b53f8`
- `0x1800b8614`
- `0x1800ba770`
- `0x1800c3380`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x18008aaf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008abc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008abc0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18008abb6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18008abb6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18008ab7f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18008ab7f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008abe2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008abfe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008abe2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008abfe`

## string_xrefs

- `0x18008ab2b`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`

## pseudocode

```c
__int64 __fastcall FlightSettingsAPICommon::IsLocalSystem(bool *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  signed int LastError; // eax
  signed int v6; // eax
  PSID v7; // rcx
  DWORD nSubAuthority2; // [rsp+20h] [rbp-60h]
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 217;
    goto LABEL_3;
  }
  IsMember = 0;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (v2 & 0x80000000) == 0 )
      return v2;
    v3 = 232;
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
0x18008aaf0  mov     [rsp-8+arg_8], rbx
0x18008aaf5  mov     [rsp-8+arg_10], rdi
0x18008aafa  push    rbp
0x18008aafb  mov     rbp, rsp
0x18008aafe  sub     rsp, 80h
0x18008ab05  mov     rax, cs:__security_cookie
0x18008ab0c  xor     rax, rsp
0x18008ab0f  mov     [rbp+var_8], rax
0x18008ab13  xor     edi, edi
0x18008ab15  mov     rbx, rcx
0x18008ab18  test    rcx, rcx
0x18008ab1b  jnz     short loc_18008AB41
0x18008ab1d  mov     ebx, 80070057h
0x18008ab22  mov     edx, 0D9h; void *
0x18008ab27  mov     rcx, [rbp+8]; this
0x18008ab2b  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x18008ab32  mov     r9d, ebx; char *
0x18008ab35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ab3a  mov     eax, ebx
0x18008ab3c  jmp     loc_18008AC06
0x18008ab41  lea     rax, [rbp+SidToCheck]
0x18008ab45  mov     [rbp+IsMember], edi
0x18008ab48  mov     [rsp+80h+pSid], rax; pSid
0x18008ab4d  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18008ab51  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18008ab55  xor     r9d, r9d; nSubAuthority1
0x18008ab58  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x18008ab5c  mov     dl, 1; nSubAuthorityCount
0x18008ab5e  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18008ab62  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x18008ab66  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18008ab6a  lea     r8d, [r9+12h]; nSubAuthority0
0x18008ab6e  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x18008ab72  mov     [rbp+SidToCheck], rdi
0x18008ab76  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x18008ab79  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18008ab7f  call    cs:__imp_AllocateAndInitializeSid
0x18008ab85  test    eax, eax
0x18008ab87  jnz     short loc_18008ABAC
0x18008ab89  call    cs:__imp_GetLastError
0x18008ab8f  mov     ebx, eax
0x18008ab91  test    eax, eax
0x18008ab93  jle     short loc_18008AB9E
0x18008ab95  movzx   ebx, ax
0x18008ab98  or      ebx, 80070000h
0x18008ab9e  test    ebx, ebx
0x18008aba0  jns     short loc_18008AB3A
0x18008aba2  mov     edx, 0E8h
0x18008aba7  jmp     loc_18008AB27
0x18008abac  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18008abb0  lea     r8, [rbp+IsMember]; IsMember
0x18008abb4  xor     ecx, ecx; TokenHandle
0x18008abb6  call    cs:__imp_CheckTokenMembership
0x18008abbc  test    eax, eax
0x18008abbe  jnz     short loc_18008ABED
0x18008abc0  call    cs:__imp_GetLastError
0x18008abc6  mov     ebx, eax
0x18008abc8  test    eax, eax
0x18008abca  jle     short loc_18008ABD5
0x18008abcc  movzx   ebx, ax
0x18008abcf  or      ebx, 80070000h
0x18008abd5  mov     rcx, [rbp+SidToCheck]; pSid
0x18008abd9  test    rcx, rcx
0x18008abdc  jz      loc_18008AB3A
0x18008abe2  call    cs:__imp_FreeSid
0x18008abe8  jmp     loc_18008AB3A
0x18008abed  cmp     [rbp+IsMember], edi
0x18008abf0  mov     rcx, [rbp+SidToCheck]; pSid
0x18008abf4  setnz   al
0x18008abf7  mov     [rbx], al
0x18008abf9  test    rcx, rcx
0x18008abfc  jz      short loc_18008AC04
0x18008abfe  call    cs:__imp_FreeSid
0x18008ac04  xor     eax, eax
0x18008ac06  mov     rcx, [rbp+var_8]
0x18008ac0a  xor     rcx, rsp; StackCookie
0x18008ac0d  call    __security_check_cookie
0x18008ac12  lea     r11, [rsp+80h+var_s0]
0x18008ac1a  mov     rbx, [r11+18h]
0x18008ac1e  mov     rdi, [r11+20h]
0x18008ac22  mov     rsp, r11
0x18008ac25  pop     rbp
0x18008ac26  retn
```
