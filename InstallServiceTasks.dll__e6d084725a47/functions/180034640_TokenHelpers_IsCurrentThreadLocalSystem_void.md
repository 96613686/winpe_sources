# TokenHelpers::IsCurrentThreadLocalSystem(void)

- ea: `0x180034640`
- end: `0x1800346f1`
- name: `?IsCurrentThreadLocalSystem@TokenHelpers@@YA_NXZ`
- size: `177`
- prototype: `bool __fastcall(TokenHelpers *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180016044`
- `0x18002b21c`

## callees

- `0x180003450`
- `0x180019624`
- `0x180034640`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800346ad`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800346ad`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180034670`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180034670`

## string_xrefs

- `0x180034682`: `onecoreuap\enduser\winstore\servicescommon\lib\tokenhelpers.cpp`
- `0x1800346bf`: `onecoreuap\enduser\winstore\servicescommon\lib\tokenhelpers.cpp`

## pseudocode

```c
bool __fastcall TokenHelpers::IsCurrentThreadLocalSystem(TokenHelpers *this)
{
  const char *v1; // r9
  const char *v2; // r9
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  cbSid[0] = 68;
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, cbSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\tokenhelpers.cpp",
      v1);
  IsMember = 0;
  if ( !CheckTokenMembership((HANDLE)0xFFFFFFFFFFFFFFFALL, pSid, &IsMember) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\tokenhelpers.cpp",
      v2);
  return IsMember != 0;
}

```

## disassembly

```asm
0x180034640  sub     rsp, 98h
0x180034647  mov     rax, cs:__security_cookie
0x18003464e  xor     rax, rsp
0x180034651  mov     [rsp+98h+var_18], rax
0x180034659  xor     edx, edx; DomainSid
0x18003465b  mov     [rsp+98h+cbSid], 44h ; 'D'
0x180034663  lea     r9, [rsp+98h+cbSid]; cbSid
0x180034668  lea     r8, [rsp+98h+pSid]; pSid
0x18003466d  lea     ecx, [rdx+16h]; WellKnownSidType
0x180034670  call    cs:__imp_CreateWellKnownSid
0x180034676  test    eax, eax
0x180034678  jnz     short loc_180034694
0x18003467a  mov     rcx, [rsp+98h]; this
0x180034682  lea     r8, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\services"...
0x180034689  mov     edx, 0A8h; void *
0x18003468e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180034694  lea     r8, [rsp+98h+IsMember]; IsMember
0x180034699  mov     [rsp+98h+IsMember], 0
0x1800346a1  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x1800346a6  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800346ad  call    cs:__imp_CheckTokenMembership
0x1800346b3  test    eax, eax
0x1800346b5  jnz     short loc_1800346D1
0x1800346b7  mov     rcx, [rsp+98h]; this
0x1800346bf  lea     r8, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\services"...
0x1800346c6  mov     edx, 0ABh; void *
0x1800346cb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800346d1  cmp     [rsp+98h+IsMember], 0
0x1800346d6  setnz   al
0x1800346d9  mov     rcx, [rsp+98h+var_18]
0x1800346e1  xor     rcx, rsp; StackCookie
0x1800346e4  call    __security_check_cookie
0x1800346e9  add     rsp, 98h
0x1800346f0  retn
```
