# GetPublisherIdentityForSid(void *,ushort * *)

- ea: `0x18013753c`
- end: `0x180137658`
- name: `?GetPublisherIdentityForSid@@YAKPEAXPEAPEAG@Z`
- size: `284`
- prototype: `unsigned int __fastcall(PSID pSid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180137660`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x1800180e4`
- `0x18013753c`

## import_xrefs

- `ADVAPI32!GetSidIdentifierAuthority` at `0x180137583`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x1801375e0`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x180137583`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x1801375e0`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180137577`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180137577`
- `ADVAPI32!IsValidSid` at `0x180137560`
- `ADVAPI32!IsValidSid` at `0x180137560`
- `ADVAPI32!GetSidSubAuthority` at `0x180137611`
- `ADVAPI32!GetSidSubAuthority` at `0x180137611`

## pseudocode

```c
__int64 __fastcall GetPublisherIdentityForSid(PSID pSid, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rdi
  unsigned int v5; // ebx
  DWORD v6; // ebx
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v8; // ecx
  DWORD v9; // ebp
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // rax
  PSID_IDENTIFIER_AUTHORITY v12; // rax
  int v13; // eax
  DWORD i; // ebx
  __int64 v16; // [rsp+20h] [rbp-48h]

  v4 = 0;
  if ( !IsValidSid(pSid) )
    goto LABEL_2;
  v6 = *GetSidSubAuthorityCount(pSid);
  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  v8 = *(_DWORD *)SidIdentifierAuthority->Value;
  if ( !*(_DWORD *)SidIdentifierAuthority->Value )
    v8 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - 1280;
  if ( v8 )
  {
LABEL_2:
    v5 = 1008;
  }
  else
  {
    v9 = v6;
    v10 = 11 * v6 + 15;
    v11 = 2 * v10;
    if ( !is_mul_ok(v10, 2u) )
      v11 = -1;
    v4 = (unsigned __int16 *)operator new[](v11, (const struct std::nothrow_t *)std::nothrow);
    if ( v4 )
    {
      v12 = GetSidIdentifierAuthority(pSid);
      v13 = StringCchPrintfW(v4, 11 * v6 + 15, L"S-1-%u", v12->Value[5]);
      if ( v13 >= 0 )
      {
        for ( i = 0; i < v9; ++i )
        {
          LODWORD(v16) = *GetSidSubAuthority(pSid, i);
          v13 = StringCchPrintfW(v4, v10, L"%s-%u", v4, v16);
          if ( v13 < 0 )
            goto LABEL_11;
        }
        *a2 = v4;
        v4 = 0;
        v5 = 0;
      }
      else
      {
LABEL_11:
        v5 = (unsigned __int16)v13;
      }
    }
    else
    {
      v5 = 8;
    }
  }
  operator delete(v4);
  return v5;
}

```

## disassembly

```asm
0x18013753c  mov     rax, rsp
0x18013753f  push    rbx
0x180137540  push    rbp
0x180137541  push    rsi
0x180137542  push    rdi
0x180137543  push    r14
0x180137545  push    r15
0x180137547  sub     rsp, 38h
0x18013754b  mov     r15, rdx
0x18013754e  mov     dword ptr [rax+18h], 0
0x180137555  mov     rsi, rcx
0x180137558  mov     word ptr [rax+1Ch], 500h
0x18013755e  xor     edi, edi
0x180137560  call    cs:__imp_IsValidSid
0x180137566  test    eax, eax
0x180137568  jnz     short loc_180137574
0x18013756a  mov     ebx, 3F0h
0x18013756f  jmp     loc_180137641
0x180137574  mov     rcx, rsi; pSid
0x180137577  call    cs:__imp_GetSidSubAuthorityCount
0x18013757d  mov     rcx, rsi; pSid
0x180137580  movzx   ebx, byte ptr [rax]
0x180137583  call    cs:__imp_GetSidIdentifierAuthority
0x180137589  mov     ecx, [rax]
0x18013758b  sub     ecx, [rsp+68h+arg_10]
0x180137592  jnz     short loc_1801375A2
0x180137594  movzx   ecx, word ptr [rax+4]
0x180137598  movzx   eax, [rsp+68h+arg_14]
0x1801375a0  sub     ecx, eax
0x1801375a2  test    ecx, ecx
0x1801375a4  jnz     short loc_18013756A
0x1801375a6  lea     eax, [rcx+2]
0x1801375a9  imul    r14d, ebx, 0Bh
0x1801375ad  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1801375b4  mov     ebp, ebx
0x1801375b6  add     r14d, 0Fh
0x1801375ba  mul     r14
0x1801375bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801375c4  cmovb   rax, rcx
0x1801375c8  mov     rcx, rax; unsigned __int64
0x1801375cb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801375d0  mov     rdi, rax
0x1801375d3  test    rax, rax
0x1801375d6  jnz     short loc_1801375DD
0x1801375d8  lea     ebx, [rax+8]
0x1801375db  jmp     short loc_180137641
0x1801375dd  mov     rcx, rsi; pSid
0x1801375e0  call    cs:__imp_GetSidIdentifierAuthority
0x1801375e6  lea     r8, aS1U; "S-1-%u"
0x1801375ed  mov     rdx, r14; unsigned __int64
0x1801375f0  mov     rcx, rdi; unsigned __int16 *
0x1801375f3  movzx   r9d, byte ptr [rax+5]
0x1801375f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801375fd  test    eax, eax
0x1801375ff  jns     short loc_180137606
0x180137601  movzx   ebx, ax
0x180137604  jmp     short loc_180137641
0x180137606  xor     ebx, ebx
0x180137608  cmp     ebx, ebp
0x18013760a  jnb     short loc_18013763A
0x18013760c  mov     edx, ebx; nSubAuthority
0x18013760e  mov     rcx, rsi; pSid
0x180137611  call    cs:__imp_GetSidSubAuthority
0x180137617  mov     r9, rdi
0x18013761a  lea     r8, aSU; "%s-%u"
0x180137621  mov     rdx, r14; unsigned __int64
0x180137624  mov     ecx, [rax]
0x180137626  mov     dword ptr [rsp+68h+var_48], ecx
0x18013762a  mov     rcx, rdi; unsigned __int16 *
0x18013762d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180137632  test    eax, eax
0x180137634  js      short loc_180137601
0x180137636  inc     ebx
0x180137638  jmp     short loc_180137608
0x18013763a  mov     [r15], rdi
0x18013763d  xor     edi, edi
0x18013763f  xor     ebx, ebx
0x180137641  mov     rcx, rdi; Block
0x180137644  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180137649  mov     eax, ebx
0x18013764b  add     rsp, 38h
0x18013764f  pop     r15
0x180137651  pop     r14
0x180137653  pop     rdi
0x180137654  pop     rsi
0x180137655  pop     rbp
0x180137656  pop     rbx
0x180137657  retn
```
