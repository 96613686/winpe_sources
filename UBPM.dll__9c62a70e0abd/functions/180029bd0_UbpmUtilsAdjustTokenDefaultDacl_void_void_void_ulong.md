# UbpmUtilsAdjustTokenDefaultDacl(void *,void *,void * *,ulong)

- ea: `0x180029bd0`
- end: `0x180029dda`
- name: `?UbpmUtilsAdjustTokenDefaultDacl@@YAKPEAX0PEAPEAXK@Z`
- size: `522`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, PSID pSid, void **, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f284`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x180029bd0`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029dae`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029dae`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180029c4c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180029c4c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180029cdd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180029d00`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180029d2e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180029cdd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180029d00`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180029d2e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180029cb7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180029cb7`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180029d5a`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180029d5a`
- `ntdll!RtlLengthSid` at `0x180029c63`
- `ntdll!RtlLengthSid` at `0x180029c79`
- `ntdll!RtlLengthSid` at `0x180029c8b`
- `ntdll!RtlLengthSid` at `0x180029c63`
- `ntdll!RtlLengthSid` at `0x180029c79`
- `ntdll!RtlLengthSid` at `0x180029c8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029dc1`

## pseudocode

```c
__int64 __fastcall UbpmUtilsAdjustTokenDefaultDacl(HANDLE TokenHandle, PSID pSid, void **a3, unsigned int a4)
{
  ULONG v8; // ebx
  ULONG v9; // ebx
  ULONG v10; // ebx
  struct _ACL *v11; // rax
  struct _ACL *v12; // rdi
  unsigned int i; // ebx
  DWORD LastError; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  PSID Sid; // [rsp+60h] [rbp-9h] BYREF
  struct _ACL *TokenInformation; // [rsp+68h] [rbp-1h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+7h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 768;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  Sid = 0;
  TokenInformation = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &Sid) )
  {
    v12 = 0;
LABEL_14:
    LastError = GetLastError();
    goto LABEL_11;
  }
  v8 = a4 * (RtlLengthSid(*a3) + 12);
  v9 = RtlLengthSid(pSid) + v8;
  v10 = RtlLengthSid(Sid) + v9;
  v11 = (struct _ACL *)UbpmAlloc(v10 + 32);
  v12 = v11;
  if ( !v11
    || !InitializeAcl(v11, v10 + 32, 2u)
    || !AddAccessAllowedAce(v12, 2u, 0x10000000u, pSid)
    || !AddAccessAllowedAce(v12, 2u, 0x20000u, Sid) )
  {
    goto LABEL_14;
  }
  for ( i = 0; i < a4; ++i )
  {
    if ( !AddAccessAllowedAce(v12, 2u, 0x10000000u, a3[i]) )
      goto LABEL_14;
  }
  TokenInformation = v12;
  LastError = 0;
  if ( !SetTokenInformation(TokenHandle, TokenDefaultDacl, &TokenInformation, 8u) )
  {
    LastError = GetLastError();
    if ( LastError == 1344 )
      LastError = 0;
  }
LABEL_11:
  UBPM_MIDL_user_free(v12, v15, v16, v17);
  if ( Sid )
    FreeSid(Sid);
  return LastError;
}

```

## disassembly

```asm
0x180029bd0  push    rbp
0x180029bd2  push    rbx
0x180029bd3  push    rsi
0x180029bd4  push    rdi
0x180029bd5  push    r12
0x180029bd7  push    r13
0x180029bd9  push    r14
0x180029bdb  push    r15
0x180029bdd  lea     rbp, [rsp-1Fh]
0x180029be2  sub     rsp, 88h
0x180029be9  mov     rax, cs:__security_cookie
0x180029bf0  xor     rax, rsp
0x180029bf3  mov     [rbp+57h+var_48], rax
0x180029bf7  xor     r13d, r13d
0x180029bfa  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 300h
0x180029c00  lea     rax, [rbp+57h+Sid]
0x180029c04  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x180029c08  mov     [rsp+0C0h+pSid], rax; pSid
0x180029c0d  mov     r14d, r9d
0x180029c10  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x180029c15  mov     r15, r8
0x180029c18  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x180029c1d  lea     r8d, [r13+4]; nSubAuthority0
0x180029c21  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x180029c26  mov     rsi, rdx
0x180029c29  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x180029c2e  mov     r12, rcx
0x180029c31  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x180029c36  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180029c3a  xor     r9d, r9d; nSubAuthority1
0x180029c3d  mov     [rsp+0C0h+nSubAuthority2], r13d; nSubAuthority2
0x180029c42  mov     dl, 1; nSubAuthorityCount
0x180029c44  mov     [rbp+57h+Sid], r13
0x180029c48  mov     [rbp+57h+TokenInformation], r13
0x180029c4c  call    cs:__imp_AllocateAndInitializeSid
0x180029c53  nop     dword ptr [rax+rax+00h]
0x180029c58  test    eax, eax
0x180029c5a  jz      loc_180029DBC
0x180029c60  mov     rcx, [r15]; Sid
0x180029c63  call    cs:__imp_RtlLengthSid
0x180029c6a  nop     dword ptr [rax+rax+00h]
0x180029c6f  mov     rcx, rsi; Sid
0x180029c72  lea     ebx, [rax+0Ch]
0x180029c75  imul    ebx, r14d
0x180029c79  call    cs:__imp_RtlLengthSid
0x180029c80  nop     dword ptr [rax+rax+00h]
0x180029c85  mov     rcx, [rbp+57h+Sid]; Sid
0x180029c89  add     ebx, eax
0x180029c8b  call    cs:__imp_RtlLengthSid
0x180029c92  nop     dword ptr [rax+rax+00h]
0x180029c97  add     ebx, eax
0x180029c99  lea     ecx, [rbx+20h]; Size
0x180029c9c  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180029ca1  mov     rdi, rax
0x180029ca4  test    rax, rax
0x180029ca7  jz      loc_180029D9E
0x180029cad  lea     r8d, [r13+2]; dwAclRevision
0x180029cb1  mov     rcx, rax; pAcl
0x180029cb4  lea     edx, [rbx+20h]; nAclLength
0x180029cb7  call    cs:__imp_InitializeAcl
0x180029cbe  nop     dword ptr [rax+rax+00h]
0x180029cc3  test    eax, eax
0x180029cc5  jz      loc_180029D9E
0x180029ccb  mov     r9, rsi; pSid
0x180029cce  mov     r8d, 10000000h; AccessMask
0x180029cd4  lea     esi, [r13+2]
0x180029cd8  mov     rcx, rdi; pAcl
0x180029cdb  mov     edx, esi; dwAceRevision
0x180029cdd  call    cs:__imp_AddAccessAllowedAce
0x180029ce4  nop     dword ptr [rax+rax+00h]
0x180029ce9  test    eax, eax
0x180029ceb  jz      loc_180029D9E
0x180029cf1  mov     r9, [rbp+57h+Sid]; pSid
0x180029cf5  mov     r8d, 20000h; AccessMask
0x180029cfb  mov     edx, esi; dwAceRevision
0x180029cfd  mov     rcx, rdi; pAcl
0x180029d00  call    cs:__imp_AddAccessAllowedAce
0x180029d07  nop     dword ptr [rax+rax+00h]
0x180029d0c  test    eax, eax
0x180029d0e  jz      loc_180029D9E
0x180029d14  mov     ebx, r13d
0x180029d17  cmp     ebx, r14d
0x180029d1a  jnb     short loc_180029D42
0x180029d1c  mov     r9d, ebx
0x180029d1f  mov     r8d, 10000000h; AccessMask
0x180029d25  mov     edx, esi; dwAceRevision
0x180029d27  mov     rcx, rdi; pAcl
0x180029d2a  mov     r9, [r15+r9*8]; pSid
0x180029d2e  call    cs:__imp_AddAccessAllowedAce
0x180029d35  nop     dword ptr [rax+rax+00h]
0x180029d3a  test    eax, eax
0x180029d3c  jz      short loc_180029D9E
0x180029d3e  inc     ebx
0x180029d40  jmp     short loc_180029D17
0x180029d42  mov     r9d, 8; TokenInformationLength
0x180029d48  mov     [rbp+57h+TokenInformation], rdi
0x180029d4c  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180029d50  mov     rcx, r12; TokenHandle
0x180029d53  mov     ebx, r13d
0x180029d56  lea     edx, [r9-2]; TokenInformationClass
0x180029d5a  call    cs:__imp_SetTokenInformation
0x180029d61  nop     dword ptr [rax+rax+00h]
0x180029d66  test    eax, eax
0x180029d68  jz      short loc_180029DC1
0x180029d6a  mov     rcx, rdi
0x180029d6d  call    UBPM_MIDL_user_free
0x180029d72  mov     rcx, [rbp+57h+Sid]; pSid
0x180029d76  test    rcx, rcx
0x180029d79  jnz     short loc_180029DAE
0x180029d7b  mov     eax, ebx
0x180029d7d  mov     rcx, [rbp+57h+var_48]
0x180029d81  xor     rcx, rsp; StackCookie
0x180029d84  call    __security_check_cookie
0x180029d89  add     rsp, 88h
0x180029d90  pop     r15
0x180029d92  pop     r14
0x180029d94  pop     r13
0x180029d96  pop     r12
0x180029d98  pop     rdi
0x180029d99  pop     rsi
0x180029d9a  pop     rbx
0x180029d9b  pop     rbp
0x180029d9c  retn
0x180029d9e  call    cs:__imp_GetLastError
0x180029da5  nop     dword ptr [rax+rax+00h]
0x180029daa  mov     ebx, eax
0x180029dac  jmp     short loc_180029D6A
0x180029dae  call    cs:__imp_FreeSid
0x180029db5  nop     dword ptr [rax+rax+00h]
0x180029dba  jmp     short loc_180029D7B
0x180029dbc  mov     rdi, r13
0x180029dbf  jmp     short loc_180029D9E
0x180029dc1  call    cs:__imp_GetLastError
0x180029dc8  nop     dword ptr [rax+rax+00h]
0x180029dcd  cmp     eax, 540h
0x180029dd2  mov     ebx, eax
0x180029dd4  cmovz   ebx, r13d
0x180029dd8  jmp     short loc_180029D6A
```
