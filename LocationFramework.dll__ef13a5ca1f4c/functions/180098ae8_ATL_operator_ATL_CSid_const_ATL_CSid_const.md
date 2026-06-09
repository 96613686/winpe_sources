# ATL::operator<(ATL::CSid const &,ATL::CSid const &)

- ea: `0x180098ae8`
- end: `0x180098b9e`
- name: `??MATL@@YA_NAEBVCSid@0@0@Z`
- size: `182`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b624`
- `0x180051ddc`
- `0x180051e60`
- `0x1800524fc`
- `0x18005e648`
- `0x1800a37a0`

## callees

- `0x180098ae8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180098afd`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180098b0d`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180098afd`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180098b0d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180098b55`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180098b62`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180098b71`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180098b7e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180098b55`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180098b62`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180098b71`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180098b7e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180098b33`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180098b41`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180098b33`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180098b41`

## pseudocode

```c
char __fastcall ATL::operator<(__int64 a1, __int64 a2)
{
  void *v2; // rbp
  void *v3; // r14
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rdi
  PSID_IDENTIFIER_AUTHORITY v5; // rax
  int i; // edx
  BYTE v7; // r8
  UCHAR j; // di
  DWORD v9; // ebx
  DWORD v10; // ebx

  v2 = (void *)(a1 + 8);
  v3 = (void *)(a2 + 8);
  SidIdentifierAuthority = GetSidIdentifierAuthority((PSID)(a1 + 8));
  v5 = GetSidIdentifierAuthority(v3);
  for ( i = 0; i < 6; ++i )
  {
    v7 = v5->Value[i];
    if ( SidIdentifierAuthority->Value[i] < v7 )
      return 1;
    if ( SidIdentifierAuthority->Value[i] > v7 )
      return 0;
  }
  for ( j = 0; j < *GetSidSubAuthorityCount(v3); ++j )
  {
    if ( *GetSidSubAuthorityCount(v2) == j )
      return 1;
    v9 = *GetSidSubAuthority(v2, j);
    if ( v9 < *GetSidSubAuthority(v3, j) )
      return 1;
    v10 = *GetSidSubAuthority(v2, j);
    if ( v10 > *GetSidSubAuthority(v3, j) )
      return 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180098ae8  push    rbx
0x180098aea  push    rbp
0x180098aeb  push    rsi
0x180098aec  push    rdi
0x180098aed  push    r14
0x180098aef  sub     rsp, 20h
0x180098af3  lea     rbp, [rcx+8]
0x180098af7  mov     r14, rdx
0x180098afa  mov     rcx, rbp; pSid
0x180098afd  call    cs:__imp_GetSidIdentifierAuthority
0x180098b03  add     r14, 8
0x180098b07  mov     rdi, rax
0x180098b0a  mov     rcx, r14; pSid
0x180098b0d  call    cs:__imp_GetSidIdentifierAuthority
0x180098b13  xor     edx, edx
0x180098b15  cmp     edx, 6
0x180098b18  jge     short loc_180098B2D
0x180098b1a  movsxd  rcx, edx
0x180098b1d  mov     r8b, [rcx+rax]
0x180098b21  cmp     [rcx+rdi], r8b
0x180098b25  jb      short loc_180098B8D
0x180098b27  ja      short loc_180098B91
0x180098b29  inc     edx
0x180098b2b  jmp     short loc_180098B15
0x180098b2d  xor     dil, dil
0x180098b30  mov     rcx, r14; pSid
0x180098b33  call    cs:__imp_GetSidSubAuthorityCount
0x180098b39  cmp     dil, [rax]
0x180098b3c  jnb     short loc_180098B91
0x180098b3e  mov     rcx, rbp; pSid
0x180098b41  call    cs:__imp_GetSidSubAuthorityCount
0x180098b47  cmp     [rax], dil
0x180098b4a  jz      short loc_180098B8D
0x180098b4c  movzx   esi, dil
0x180098b50  mov     rcx, rbp; pSid
0x180098b53  mov     edx, esi; nSubAuthority
0x180098b55  call    cs:__imp_GetSidSubAuthority
0x180098b5b  mov     edx, esi; nSubAuthority
0x180098b5d  mov     rcx, r14; pSid
0x180098b60  mov     ebx, [rax]
0x180098b62  call    cs:__imp_GetSidSubAuthority
0x180098b68  cmp     ebx, [rax]
0x180098b6a  jb      short loc_180098B8D
0x180098b6c  mov     edx, esi; nSubAuthority
0x180098b6e  mov     rcx, rbp; pSid
0x180098b71  call    cs:__imp_GetSidSubAuthority
0x180098b77  mov     edx, esi; nSubAuthority
0x180098b79  mov     rcx, r14; pSid
0x180098b7c  mov     ebx, [rax]
0x180098b7e  call    cs:__imp_GetSidSubAuthority
0x180098b84  cmp     ebx, [rax]
0x180098b86  ja      short loc_180098B91
0x180098b88  inc     dil
0x180098b8b  jmp     short loc_180098B30
0x180098b8d  mov     al, 1
0x180098b8f  jmp     short loc_180098B93
0x180098b91  xor     al, al
0x180098b93  add     rsp, 20h
0x180098b97  pop     r14
0x180098b99  pop     rdi
0x180098b9a  pop     rsi
0x180098b9b  pop     rbp
0x180098b9c  pop     rbx
0x180098b9d  retn
```
