# _DaclHasAllowAceForAppContainer(_ACL *)

- ea: `0x180024c58`
- end: `0x180024ce9`
- name: `?_DaclHasAllowAceForAppContainer@@YA_NPEAU_ACL@@@Z`
- size: `145`
- prototype: `char __fastcall(PACL pAcl)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024b30`

## callees

- `0x180024c58`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180024ca8`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180024ca8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024cca`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024cca`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180024cb4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180024cb4`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180024c80`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180024c80`

## pseudocode

```c
char __fastcall _DaclHasAllowAceForAppContainer(PACL pAcl)
{
  WORD i; // bx
  int v3; // edx
  char *v4; // rsi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rbp
  LPVOID pAce; // [rsp+50h] [rbp+8h] BYREF

  for ( i = 0; i < pAcl->AceCount; ++i )
  {
    pAce = 0;
    if ( GetAce(pAcl, i, &pAce) )
    {
      if ( *(_BYTE *)pAce <= 0xBu )
      {
        v3 = 2609;
        if ( _bittest(&v3, *(unsigned __int8 *)pAce) )
        {
          v4 = (char *)pAce + 8;
          SidIdentifierAuthority = GetSidIdentifierAuthority((char *)pAce + 8);
          if ( *GetSidSubAuthorityCount(v4) == 8
            && SidIdentifierAuthority->Value[5] == 15
            && *GetSidSubAuthority(v4, 0) == 2 )
          {
            return 1;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180024c58  push    rbx
0x180024c5a  push    rbp
0x180024c5b  push    rsi
0x180024c5c  push    rdi
0x180024c5d  sub     rsp, 28h
0x180024c61  mov     rdi, rcx
0x180024c64  xor     ebx, ebx
0x180024c66  cmp     bx, [rdi+4]
0x180024c6a  jnb     short loc_180024CDE
0x180024c6c  movzx   edx, bx; dwAceIndex
0x180024c6f  lea     r8, [rsp+48h+pAce]; pAce
0x180024c74  mov     rcx, rdi; pAcl
0x180024c77  mov     [rsp+48h+pAce], 0
0x180024c80  call    cs:__imp_GetAce
0x180024c86  test    eax, eax
0x180024c88  jz      short loc_180024CD5
0x180024c8a  mov     rcx, [rsp+48h+pAce]
0x180024c8f  cmp     byte ptr [rcx], 0Bh
0x180024c92  ja      short loc_180024CD5
0x180024c94  movzx   eax, byte ptr [rcx]
0x180024c97  mov     edx, 0A31h
0x180024c9c  bt      edx, eax
0x180024c9f  jnb     short loc_180024CD5
0x180024ca1  lea     rsi, [rcx+8]
0x180024ca5  mov     rcx, rsi; pSid
0x180024ca8  call    cs:__imp_GetSidIdentifierAuthority
0x180024cae  mov     rcx, rsi; pSid
0x180024cb1  mov     rbp, rax
0x180024cb4  call    cs:__imp_GetSidSubAuthorityCount
0x180024cba  cmp     byte ptr [rax], 8
0x180024cbd  jnz     short loc_180024CD5
0x180024cbf  cmp     byte ptr [rbp+5], 0Fh
0x180024cc3  jnz     short loc_180024CD5
0x180024cc5  xor     edx, edx; nSubAuthority
0x180024cc7  mov     rcx, rsi; pSid
0x180024cca  call    cs:__imp_GetSidSubAuthority
0x180024cd0  cmp     dword ptr [rax], 2
0x180024cd3  jz      short loc_180024CDA
0x180024cd5  inc     bx
0x180024cd8  jmp     short loc_180024C66
0x180024cda  mov     al, 1
0x180024cdc  jmp     short loc_180024CE0
0x180024cde  xor     al, al
0x180024ce0  add     rsp, 28h
0x180024ce4  pop     rdi
0x180024ce5  pop     rsi
0x180024ce6  pop     rbp
0x180024ce7  pop     rbx
0x180024ce8  retn
```
