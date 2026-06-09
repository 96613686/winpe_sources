# AclHasSIDCheckAndSetAccess(_ACL *,void *,ulong,ulong,ulong,bool *)

- ea: `0x18002040c`
- end: `0x1800204a6`
- name: `?AclHasSIDCheckAndSetAccess@@YA_NPEAU_ACL@@PEAXKKKPEA_N@Z`
- size: `154`
- prototype: `char __fastcall(PACL pAcl, PSID pSid2, int, __int64, unsigned int, bool *pAce)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020730`

## callees

- `0x18002040c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002045f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002045f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180020444`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180020444`

## pseudocode

```c
char __fastcall AclHasSIDCheckAndSetAccess(PACL pAcl, PSID pSid2, int a3, __int64 a4, unsigned int a5, bool *pAce)
{
  bool *v6; // rsi
  WORD v10; // bx
  int v11; // ecx
  bool *v12; // rcx

  v6 = pAce;
  v10 = 0;
  *pAce = 0;
  while ( 1 )
  {
    if ( v10 >= pAcl->AceCount )
      return 0;
    pAce = 0;
    if ( GetAce(pAcl, v10, (LPVOID *)&pAce) )
    {
      if ( !*pAce && EqualSid(pAce + 8, pSid2) )
        break;
    }
    ++v10;
  }
  v11 = a3 | *((_DWORD *)pAce + 1);
  if ( *((_DWORD *)pAce + 1) != v11 )
  {
    *((_DWORD *)pAce + 1) = v11;
    v12 = pAce;
    *v6 = 1;
    v12[1] &= ~0x10u;
    pAce[1] |= 3u;
  }
  return 1;
}

```

## disassembly

```asm
0x18002040c  push    rbx
0x18002040e  push    rbp
0x18002040f  push    rsi
0x180020410  push    rdi
0x180020411  push    r14
0x180020413  sub     rsp, 20h
0x180020417  mov     rsi, [rsp+48h+pAce]
0x18002041c  mov     ebp, r8d
0x18002041f  mov     r14, rdx
0x180020422  mov     rdi, rcx
0x180020425  xor     ebx, ebx
0x180020427  mov     byte ptr [rsi], 0
0x18002042a  cmp     bx, [rdi+4]
0x18002042e  jnb     short loc_180020499
0x180020430  movzx   edx, bx; dwAceIndex
0x180020433  lea     r8, [rsp+48h+pAce]; pAce
0x180020438  mov     rcx, rdi; pAcl
0x18002043b  mov     [rsp+48h+pAce], 0
0x180020444  call    cs:__imp_GetAce
0x18002044a  test    eax, eax
0x18002044c  jz      short loc_180020469
0x18002044e  mov     rcx, [rsp+48h+pAce]
0x180020453  cmp     byte ptr [rcx], 0
0x180020456  jnz     short loc_180020469
0x180020458  add     rcx, 8; pSid1
0x18002045c  mov     rdx, r14; pSid2
0x18002045f  call    cs:__imp_EqualSid
0x180020465  test    eax, eax
0x180020467  jnz     short loc_18002046E
0x180020469  inc     bx
0x18002046c  jmp     short loc_18002042A
0x18002046e  mov     rdx, [rsp+48h+pAce]
0x180020473  mov     ecx, [rdx+4]
0x180020476  or      ecx, ebp
0x180020478  cmp     [rdx+4], ecx
0x18002047b  jz      short loc_180020495
0x18002047d  mov     [rdx+4], ecx
0x180020480  mov     rcx, [rsp+48h+pAce]
0x180020485  mov     byte ptr [rsi], 1
0x180020488  and     byte ptr [rcx+1], 0EFh
0x18002048c  mov     rcx, [rsp+48h+pAce]
0x180020491  or      byte ptr [rcx+1], 3
0x180020495  mov     al, 1
0x180020497  jmp     short loc_18002049B
0x180020499  xor     al, al
0x18002049b  add     rsp, 20h
0x18002049f  pop     r14
0x1800204a1  pop     rdi
0x1800204a2  pop     rsi
0x1800204a3  pop     rbp
0x1800204a4  pop     rbx
0x1800204a5  retn
```
