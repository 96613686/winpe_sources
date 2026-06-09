# CNgscbToken::CheckIsTokenMember(WELL_KNOWN_SID_TYPE,bool *)

- ea: `0x18002858c`
- end: `0x1800286e6`
- name: `?CheckIsTokenMember@CNgscbToken@@AEBAJW4WELL_KNOWN_SID_TYPE@@PEA_N@Z`
- size: `346`
- prototype: `__int64 __fastcall(HANDLE *this, enum WELL_KNOWN_SID_TYPE, bool *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180056bcc`
- `0x18006a200`
- `0x180071170`

## callees

- `0x18002858c`
- `0x180034070`
- `0x180034d28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028605`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028605`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286b8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800285f5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800285f5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180028691`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180028691`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180028675`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180028675`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028643`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028643`

## pseudocode

```c
__int64 __fastcall CNgscbToken::CheckIsTokenMember(HANDLE *this, enum WELL_KNOWN_SID_TYPE a2, bool *a3)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  HANDLE v8; // rcx
  int TokenInformation; // [rsp+30h] [rbp-39h] BYREF
  WINBOOL IsMember; // [rsp+34h] [rbp-35h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-31h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-2Dh] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-29h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-19h] BYREF

  TokenHandle = 0;
  IsMember = 0;
  TokenInformation = 1;
  ReturnLength = 0;
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( CreateWellKnownSid(a2, 0, pSid, &cbSid)
    && GetTokenInformation(*this, TokenType, &TokenInformation, 4u, &ReturnLength) )
  {
    v8 = *this;
    if ( TokenInformation != 2 )
    {
      if ( !DuplicateTokenEx(v8, 0, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
        goto LABEL_2;
      v8 = TokenHandle;
    }
    if ( CheckTokenMembership(v8, pSid, &IsMember) )
    {
      v7 = 0;
      *a3 = IsMember != 0;
      goto LABEL_10;
    }
  }
LABEL_2:
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v7;
}

```

## disassembly

```asm
0x18002858c  mov     [rsp-8+arg_18], rbx
0x180028591  push    rbp
0x180028592  push    rsi
0x180028593  push    rdi
0x180028594  lea     rbp, [rsp-47h]
0x180028599  sub     rsp, 0B0h
0x1800285a0  mov     rax, cs:__security_cookie
0x1800285a7  xor     rax, rsp
0x1800285aa  mov     [rbp+57h+var_20], rax
0x1800285ae  mov     ebx, edx
0x1800285b0  mov     [rbp+57h+TokenHandle], 0
0x1800285b8  xor     edx, edx; Val
0x1800285ba  mov     [rbp+57h+IsMember], 0
0x1800285c1  mov     rsi, r8
0x1800285c4  mov     [rbp+57h+TokenInformation], 1
0x1800285cb  mov     rdi, rcx
0x1800285ce  mov     [rbp+57h+var_84], 0
0x1800285d5  lea     rcx, [rbp+57h+pSid]; void *
0x1800285d9  lea     r8d, [rdx+44h]; Size
0x1800285dd  call    memset_0
0x1800285e2  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800285e6  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800285ed  lea     r8, [rbp+57h+pSid]; pSid
0x1800285f1  xor     edx, edx; DomainSid
0x1800285f3  mov     ecx, ebx; WellKnownSidType
0x1800285f5  call    cs:__imp_CreateWellKnownSid
0x1800285fc  nop     dword ptr [rax+rax+00h]
0x180028601  test    eax, eax
0x180028603  jnz     short loc_180028629
0x180028605  call    cs:__imp_GetLastError
0x18002860c  nop     dword ptr [rax+rax+00h]
0x180028611  mov     ebx, eax
0x180028613  test    eax, eax
0x180028615  jle     loc_1800286AF
0x18002861b  movzx   ebx, ax
0x18002861e  or      ebx, 80070000h
0x180028624  jmp     loc_1800286AF
0x180028629  mov     rcx, [rdi]; TokenHandle
0x18002862c  lea     rax, [rbp+57h+var_84]
0x180028630  mov     r9d, 4; TokenInformationLength
0x180028636  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18002863b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002863f  lea     edx, [r9+4]; TokenInformationClass
0x180028643  call    cs:__imp_GetTokenInformation
0x18002864a  nop     dword ptr [rax+rax+00h]
0x18002864f  test    eax, eax
0x180028651  jz      short loc_180028605
0x180028653  mov     rcx, [rdi]; hExistingToken
0x180028656  mov     r9d, 2; ImpersonationLevel
0x18002865c  cmp     [rbp+57h+TokenInformation], r9d
0x180028660  jz      short loc_180028689
0x180028662  lea     rax, [rbp+57h+TokenHandle]
0x180028666  xor     r8d, r8d; lpTokenAttributes
0x180028669  mov     [rsp+0C0h+phNewToken], rax; phNewToken
0x18002866e  xor     edx, edx; dwDesiredAccess
0x180028670  mov     dword ptr [rsp+0C0h+ReturnLength], r9d; TokenType
0x180028675  call    cs:__imp_DuplicateTokenEx
0x18002867c  nop     dword ptr [rax+rax+00h]
0x180028681  test    eax, eax
0x180028683  jz      short loc_180028605
0x180028685  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180028689  lea     r8, [rbp+57h+IsMember]; IsMember
0x18002868d  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180028691  call    cs:__imp_CheckTokenMembership
0x180028698  nop     dword ptr [rax+rax+00h]
0x18002869d  test    eax, eax
0x18002869f  jz      loc_180028605
0x1800286a5  xor     ebx, ebx
0x1800286a7  cmp     [rbp+57h+IsMember], ebx
0x1800286aa  setnz   cl
0x1800286ad  mov     [rsi], cl
0x1800286af  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800286b3  test    rcx, rcx
0x1800286b6  jz      short loc_1800286C4
0x1800286b8  call    cs:__imp_CloseHandle
0x1800286bf  nop     dword ptr [rax+rax+00h]
0x1800286c4  mov     eax, ebx
0x1800286c6  mov     rcx, [rbp+57h+var_20]
0x1800286ca  xor     rcx, rsp; StackCookie
0x1800286cd  call    __security_check_cookie
0x1800286d2  mov     rbx, [rsp+0C0h+arg_18]
0x1800286da  add     rsp, 0B0h
0x1800286e1  pop     rdi
0x1800286e2  pop     rsi
0x1800286e3  pop     rbp
0x1800286e4  retn
```
