# _anonymous_namespace_::SetACSIDReadOnlyInAcl

- ea: `0x180029b30`
- end: `0x180029c08`
- name: `_anonymous_namespace_::SetACSIDReadOnlyInAcl`
- size: `216`
- prototype: `__int64 __fastcall(PACL pAcl)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029e50`

## callees

- `0x180029b30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180029b89`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180029b89`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180029bc5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180029bc5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180029bb5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180029bb5`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180029b6e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180029b6e`

## pseudocode

```c
char __fastcall anonymous_namespace_::SetACSIDReadOnlyInAcl(PACL pAcl)
{
  char v1; // di
  WORD i; // bx
  char *v4; // rbp
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  LPVOID pAce; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  for ( i = 0; i < pAcl->AceCount; ++i )
  {
    pAce = 0;
    if ( GetAce(pAcl, i, &pAce) )
    {
      if ( !*(_BYTE *)pAce )
      {
        v4 = (char *)pAce + 8;
        SidIdentifierAuthority = GetSidIdentifierAuthority((char *)pAce + 8);
        if ( SidIdentifierAuthority->Value[5] == 15
          && !SidIdentifierAuthority->Value[4]
          && !SidIdentifierAuthority->Value[3]
          && !SidIdentifierAuthority->Value[2]
          && !SidIdentifierAuthority->Value[1]
          && !SidIdentifierAuthority->Value[0]
          && *GetSidSubAuthorityCount(v4) >= 8u
          && *GetSidSubAuthority(v4, 0) - 2 <= 1 )
        {
          v1 = 1;
          *((_DWORD *)pAce + 1) = 0x80000000;
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180029b30  mov     [rsp+arg_8], rbx
0x180029b35  mov     [rsp+arg_10], rbp
0x180029b3a  push    rsi
0x180029b3b  push    rdi
0x180029b3c  push    r15
0x180029b3e  sub     rsp, 20h
0x180029b42  xor     dil, dil
0x180029b45  xor     ebx, ebx
0x180029b47  xor     eax, eax
0x180029b49  mov     rsi, rcx
0x180029b4c  cmp     ax, [rcx+4]
0x180029b50  jnb     loc_180029BF2
0x180029b56  lea     r15d, [rbx+1]
0x180029b5a  movzx   edx, bx; dwAceIndex
0x180029b5d  lea     r8, [rsp+38h+pAce]; pAce
0x180029b62  mov     rcx, rsi; pAcl
0x180029b65  mov     [rsp+38h+pAce], 0
0x180029b6e  call    cs:__imp_GetAce
0x180029b74  test    eax, eax
0x180029b76  jz      short loc_180029BE4
0x180029b78  mov     rax, [rsp+38h+pAce]
0x180029b7d  cmp     byte ptr [rax], 0
0x180029b80  jnz     short loc_180029BE4
0x180029b82  lea     rbp, [rax+8]
0x180029b86  mov     rcx, rbp; pSid
0x180029b89  call    cs:__imp_GetSidIdentifierAuthority
0x180029b8f  cmp     byte ptr [rax+5], 0Fh
0x180029b93  jnz     short loc_180029BE4
0x180029b95  cmp     byte ptr [rax+4], 0
0x180029b99  jnz     short loc_180029BE4
0x180029b9b  cmp     byte ptr [rax+3], 0
0x180029b9f  jnz     short loc_180029BE4
0x180029ba1  cmp     byte ptr [rax+2], 0
0x180029ba5  jnz     short loc_180029BE4
0x180029ba7  cmp     byte ptr [rax+1], 0
0x180029bab  jnz     short loc_180029BE4
0x180029bad  cmp     byte ptr [rax], 0
0x180029bb0  jnz     short loc_180029BE4
0x180029bb2  mov     rcx, rbp; pSid
0x180029bb5  call    cs:__imp_GetSidSubAuthorityCount
0x180029bbb  cmp     byte ptr [rax], 8
0x180029bbe  jb      short loc_180029BE4
0x180029bc0  xor     edx, edx; nSubAuthority
0x180029bc2  mov     rcx, rbp; pSid
0x180029bc5  call    cs:__imp_GetSidSubAuthority
0x180029bcb  mov     ecx, [rax]
0x180029bcd  sub     ecx, 2
0x180029bd0  cmp     ecx, r15d
0x180029bd3  ja      short loc_180029BE4
0x180029bd5  mov     rax, [rsp+38h+pAce]
0x180029bda  mov     dil, r15b
0x180029bdd  mov     dword ptr [rax+4], 80000000h
0x180029be4  add     bx, r15w
0x180029be8  cmp     bx, [rsi+4]
0x180029bec  jb      loc_180029B5A
0x180029bf2  mov     rbx, [rsp+38h+arg_8]
0x180029bf7  mov     al, dil
0x180029bfa  mov     rbp, [rsp+38h+arg_10]
0x180029bff  add     rsp, 20h
0x180029c03  pop     r15
0x180029c05  pop     rdi
0x180029c06  pop     rsi
0x180029c07  retn
```
