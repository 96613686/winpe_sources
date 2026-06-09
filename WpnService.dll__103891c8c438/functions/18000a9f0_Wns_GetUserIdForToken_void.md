# Wns::GetUserIdForToken(void *)

- ea: `0x18000a9f0`
- end: `0x18000abb7`
- name: `?GetUserIdForToken@Wns@@YA_KPEAX@Z`
- size: `455`
- prototype: `unsigned __int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800226b0`

## callees

- `0x18000a9f0`
- `0x18000aee0`
- `0x180026200`
- `0x180026d3c`
- `0x180031da0`
- `0x180031dc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaf3`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18000aad1`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18000aad1`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000aab9`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000aab9`
- `ntdll!RtlInitializeSidEx` at `0x18000aa52`
- `ntdll!RtlInitializeSidEx` at `0x18000aa52`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000aa6b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000ab0e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000aa6b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000ab0e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000ab44`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000ab44`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000ab5c`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000ab5c`

## pseudocode

```c
unsigned __int64 __fastcall Wns::GetUserIdForToken(HANDLE TokenHandle, void *a2)
{
  int v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  bool v7; // di
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int v10; // r8d
  const char *v11; // r9
  unsigned int v12; // r8d
  const char *v13; // r9
  unsigned int v14; // r8d
  const char *v15; // r9
  WINBOOL IsMember; // [rsp+20h] [rbp-19h] BYREF
  int v17; // [rsp+24h] [rbp-15h] BYREF
  DWORD cbSid; // [rsp+28h] [rbp-11h] BYREF
  __int16 v19; // [rsp+2Ch] [rbp-Dh]
  _OWORD SidToCheck[4]; // [rsp+30h] [rbp-9h] BYREF
  int v21; // [rsp+70h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v19 = 1280;
  v21 = 0;
  cbSid = 0;
  IsMember = 0;
  memset(SidToCheck, 0, sizeof(SidToCheck));
  v3 = RtlInitializeSidEx(SidToCheck, &cbSid, 1, 18);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, v4, v5, (const char *)(unsigned int)v3, IsMember);
  if ( !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
  {
    if ( GetLastError() != 1309 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x69, v8, v9);
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6B, v10, v11);
  }
  if ( IsMember )
    return 0;
  IsMember = 0;
  RtlGetDeviceFamilyInfoEnum(0, &IsMember, 0);
  v7 = (unsigned int)(IsMember - 7) <= 1;
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() || v7 )
  {
    cbSid = 68;
    v17 = 0;
    if ( !CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, SidToCheck, &cbSid) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x93, v12, v13);
    if ( !(unsigned int)CheckTokenMembershipEx(TokenHandle, SidToCheck, 0, &v17) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x95, v14, v15);
    if ( v17 == 1 )
      return 0;
  }
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
    return 0;
  else
    return GetUserIdForContext(TokenHandle);
}

```

## disassembly

```asm
0x18000a9f0  mov     [rsp-8+arg_10], rbx
0x18000a9f5  mov     [rsp-8+arg_18], rsi
0x18000a9fa  push    rbp
0x18000a9fb  lea     rbp, [rsp-57h]
0x18000aa00  sub     rsp, 90h
0x18000aa07  mov     rax, cs:__security_cookie
0x18000aa0e  xor     rax, rsp
0x18000aa11  mov     [rbp+57h+var_10], rax
0x18000aa15  xorps   xmm0, xmm0
0x18000aa18  mov     [rbp+57h+var_64], 500h
0x18000aa1e  xor     eax, eax
0x18000aa20  lea     rdx, [rbp+57h+cbSid]
0x18000aa24  mov     rbx, rcx
0x18000aa27  mov     [rbp+57h+var_20], eax
0x18000aa2a  xor     esi, esi
0x18000aa2c  mov     [rbp+57h+cbSid], eax
0x18000aa2f  lea     rcx, [rbp+57h+SidToCheck]
0x18000aa33  mov     [rbp+57h+IsMember], esi
0x18000aa36  mov     r9d, 12h
0x18000aa3c  mov     r8d, 1
0x18000aa42  movups  [rbp+57h+SidToCheck], xmm0
0x18000aa46  movups  [rbp+57h+var_50], xmm0
0x18000aa4a  movups  [rbp+57h+var_40], xmm0
0x18000aa4e  movups  [rbp+57h+var_30], xmm0
0x18000aa52  call    cs:__imp_RtlInitializeSidEx
0x18000aa58  test    eax, eax
0x18000aa5a  js      loc_18000AB84
0x18000aa60  lea     r8, [rbp+57h+IsMember]; IsMember
0x18000aa64  mov     rcx, rbx; TokenHandle
0x18000aa67  lea     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18000aa6b  call    cs:__imp_CheckTokenMembership
0x18000aa71  test    eax, eax
0x18000aa73  jz      short loc_18000AAF3
0x18000aa75  mov     [rsp+90h+arg_8], rdi
0x18000aa7d  cmp     [rbp+57h+IsMember], esi
0x18000aa80  jz      short loc_18000AAAD
0x18000aa82  xor     eax, eax
0x18000aa84  mov     rdi, [rsp+90h+arg_8]
0x18000aa8c  mov     rcx, [rbp+57h+var_10]
0x18000aa90  xor     rcx, rsp; StackCookie
0x18000aa93  call    __security_check_cookie
0x18000aa98  lea     r11, [rsp+90h+var_s0]
0x18000aaa0  mov     rbx, [r11+20h]
0x18000aaa4  mov     rsi, [r11+28h]
0x18000aaa8  mov     rsp, r11
0x18000aaab  pop     rbp
0x18000aaac  retn
0x18000aaad  xor     r8d, r8d
0x18000aab0  mov     [rbp+57h+IsMember], esi
0x18000aab3  lea     rdx, [rbp+57h+IsMember]
0x18000aab7  xor     ecx, ecx
0x18000aab9  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000aabf  mov     eax, [rbp+57h+IsMember]
0x18000aac2  add     eax, 0FFFFFFF9h
0x18000aac5  cmp     eax, 1
0x18000aac8  ja      loc_18000ABA0
0x18000aace  mov     dil, 1
0x18000aad1  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18000aad7  test    al, al
0x18000aad9  jnz     short loc_18000AB2B
0x18000aadb  test    dil, dil
0x18000aade  jnz     short loc_18000AB2B
0x18000aae0  call    IsUMgrQueryUserContextPresent
0x18000aae5  test    al, al
0x18000aae7  jz      short loc_18000AA82
0x18000aae9  mov     rcx, rbx; void *
0x18000aaec  call    ?GetUserIdForContext@@YA_KPEAX@Z; GetUserIdForContext(void *)
0x18000aaf1  jmp     short loc_18000AA84
0x18000aaf3  call    cs:__imp_GetLastError
0x18000aaf9  cmp     eax, 51Dh
0x18000aafe  jnz     loc_18000AB91
0x18000ab04  lea     r8, [rbp+57h+IsMember]; IsMember
0x18000ab08  xor     ecx, ecx; TokenHandle
0x18000ab0a  lea     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18000ab0e  call    cs:__imp_CheckTokenMembership
0x18000ab14  test    eax, eax
0x18000ab16  jnz     loc_18000AA75
0x18000ab1c  mov     rcx, [rbp+5Fh]; this
0x18000ab20  mov     edx, 6Bh ; 'k'; void *
0x18000ab25  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000ab2b  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000ab2f  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000ab36  lea     r8, [rbp+57h+SidToCheck]; pSid
0x18000ab3a  mov     [rbp+57h+var_6C], esi
0x18000ab3d  xor     edx, edx; DomainSid
0x18000ab3f  mov     ecx, 6Fh ; 'o'; WellKnownSidType
0x18000ab44  call    cs:__imp_CreateWellKnownSid
0x18000ab4a  test    eax, eax
0x18000ab4c  jz      short loc_18000AB75
0x18000ab4e  lea     r9, [rbp+57h+var_6C]
0x18000ab52  xor     r8d, r8d
0x18000ab55  lea     rdx, [rbp+57h+SidToCheck]
0x18000ab59  mov     rcx, rbx
0x18000ab5c  call    cs:__imp_CheckTokenMembershipEx
0x18000ab62  test    eax, eax
0x18000ab64  jnz     short loc_18000ABA8
0x18000ab66  mov     rcx, [rbp+5Fh]; this
0x18000ab6a  mov     edx, 95h; void *
0x18000ab6f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000ab75  mov     rcx, [rbp+5Fh]; this
0x18000ab79  mov     edx, 93h; void *
0x18000ab7e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000ab84  mov     rcx, [rbp+5Fh]; this
0x18000ab88  mov     r9d, eax; char *
0x18000ab8b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18000ab91  mov     rcx, [rbp+5Fh]; this
0x18000ab95  mov     edx, 69h ; 'i'; void *
0x18000ab9a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000aba0  xor     dil, dil
0x18000aba3  jmp     loc_18000AAD1
0x18000aba8  cmp     [rbp+57h+var_6C], 1
0x18000abac  jz      loc_18000AA82
0x18000abb2  jmp     loc_18000AAE0
```
