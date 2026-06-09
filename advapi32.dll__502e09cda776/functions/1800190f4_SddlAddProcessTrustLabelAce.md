# SddlAddProcessTrustLabelAce

- ea: `0x1800190f4`
- end: `0x180019264`
- name: `SddlAddProcessTrustLabelAce`
- size: `368`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180019ed0`

## callees

- `0x1800190f4`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800191cd`
- `ntdll!RtlLengthSid` at `0x18001920c`
- `ntdll!RtlLengthSid` at `0x1800191cd`
- `ntdll!RtlLengthSid` at `0x18001920c`
- `ntdll!RtlValidSid` at `0x180019144`
- `ntdll!RtlValidSid` at `0x180019144`
- `ntdll!RtlCopySid` at `0x180019221`
- `ntdll!RtlCopySid` at `0x180019221`
- `ntdll!RtlValidAcl` at `0x18001912d`
- `ntdll!RtlValidAcl` at `0x18001912d`
- `ntdll!RtlFirstFreeAce` at `0x1800191b6`
- `ntdll!RtlFirstFreeAce` at `0x1800191b6`

## pseudocode

```c
__int64 __fastcall SddlAddProcessTrustLabelAce(PACL Acl, __int64 a2, int a3, __int64 a4, int a5, int a6)
{
  __int64 result; // rax
  int v10; // ecx
  BYTE AclRevision; // bp
  int v12; // r14d
  __int16 v13; // ax
  PACE v14; // rbx
  __int64 v15; // rdx
  ULONG v16; // eax
  PACE Ace; // [rsp+68h] [rbp+20h] BYREF

  Ace = 0;
  if ( !Acl || !RtlValidAcl(Acl) )
    return 3221225591LL;
  if ( !RtlValidSid((PSID)a4) )
    return 3221225592LL;
  v10 = *(_DWORD *)(a4 + 2);
  if ( !v10 )
    v10 = *(unsigned __int16 *)(a4 + 6) - 4864;
  if ( v10 )
    return 3221225485LL;
  if ( Acl->AclRevision > 4u )
    return 3221225561LL;
  AclRevision = 2;
  if ( Acl->AclRevision > 2u )
    AclRevision = Acl->AclRevision;
  if ( (a3 & 0xFFFFFFE0) != 0 )
    return 3221225485LL;
  v12 = a6;
  if ( (a6 & 0xFF000000) != 0 )
    return 3221225485LL;
  if ( !RtlFirstFreeAce(Acl, &Ace) )
    return 3221225591LL;
  v13 = RtlLengthSid((PSID)a4);
  v14 = Ace;
  if ( !Ace )
    return 3221225625LL;
  v15 = (unsigned __int16)(v13 + 8);
  if ( (char *)Ace + v15 > (char *)Acl + Acl->AclSize )
    return 3221225625LL;
  Ace->Header.AceFlags = a3;
  v14->Header.AceType = 20;
  v14->Header.AceSize = v15;
  v14->AccessMask = v12;
  v16 = RtlLengthSid((PSID)a4);
  RtlCopySid(v16, &v14[1], (PSID)a4);
  ++Acl->AceCount;
  result = 0;
  Acl->AclRevision = AclRevision;
  return result;
}

```

## disassembly

```asm
0x1800190f4  mov     rax, rsp
0x1800190f7  mov     [rax+10h], rbx
0x1800190fb  push    rbp
0x1800190fc  push    rsi
0x1800190fd  push    rdi
0x1800190fe  push    r14
0x180019100  push    r15
0x180019102  sub     rsp, 20h
0x180019106  mov     qword ptr [rax+20h], 0
0x18001910e  mov     rsi, r9
0x180019111  mov     dword ptr [rax+8], 0
0x180019118  mov     r15d, r8d
0x18001911b  mov     word ptr [rax+0Ch], 1300h
0x180019121  mov     rdi, rcx
0x180019124  test    rcx, rcx
0x180019127  jz      loc_18001924D
0x18001912d  call    cs:__imp_RtlValidAcl
0x180019134  nop     dword ptr [rax+rax+00h]
0x180019139  test    al, al
0x18001913b  jz      loc_18001924D
0x180019141  mov     rcx, rsi; Sid
0x180019144  call    cs:__imp_RtlValidSid
0x18001914b  nop     dword ptr [rax+rax+00h]
0x180019150  test    al, al
0x180019152  jnz     short loc_18001915E
0x180019154  mov     eax, 0C0000078h
0x180019159  jmp     loc_180019252
0x18001915e  mov     ecx, [rsi+2]
0x180019161  sub     ecx, [rsp+48h+arg_0]
0x180019165  jnz     short loc_180019172
0x180019167  movzx   ecx, word ptr [rsi+6]
0x18001916b  movzx   eax, [rsp+48h+arg_4]
0x180019170  sub     ecx, eax
0x180019172  test    ecx, ecx
0x180019174  jnz     loc_180019246
0x18001917a  cmp     byte ptr [rdi], 4
0x18001917d  ja      loc_18001923F
0x180019183  movzx   eax, byte ptr [rdi]
0x180019186  lea     ebp, [rcx+2]
0x180019189  cmp     [rdi], bpl
0x18001918c  cmova   ebp, eax
0x18001918f  test    r15d, 0FFFFFFE0h
0x180019196  jnz     loc_180019246
0x18001919c  mov     r14d, [rsp+48h+arg_28]
0x1800191a1  test    r14d, 0FF000000h
0x1800191a8  jnz     loc_180019246
0x1800191ae  lea     rdx, [rsp+48h+Ace]; Ace
0x1800191b3  mov     rcx, rdi; Acl
0x1800191b6  call    cs:__imp_RtlFirstFreeAce
0x1800191bd  nop     dword ptr [rax+rax+00h]
0x1800191c2  test    al, al
0x1800191c4  jz      loc_18001924D
0x1800191ca  mov     rcx, rsi; Sid
0x1800191cd  call    cs:__imp_RtlLengthSid
0x1800191d4  nop     dword ptr [rax+rax+00h]
0x1800191d9  mov     rbx, [rsp+48h+Ace]
0x1800191de  test    rbx, rbx
0x1800191e1  jz      short loc_180019238
0x1800191e3  movzx   ecx, word ptr [rdi+2]
0x1800191e7  add     ax, 8
0x1800191eb  movzx   edx, ax
0x1800191ee  add     rcx, rdi
0x1800191f1  lea     rax, [rbx+rdx]
0x1800191f5  cmp     rax, rcx
0x1800191f8  ja      short loc_180019238
0x1800191fa  mov     rcx, rsi; Sid
0x1800191fd  mov     [rbx+1], r15b
0x180019201  mov     byte ptr [rbx], 14h
0x180019204  mov     [rbx+2], dx
0x180019208  mov     [rbx+4], r14d
0x18001920c  call    cs:__imp_RtlLengthSid
0x180019213  nop     dword ptr [rax+rax+00h]
0x180019218  mov     r8, rsi; SourceSid
0x18001921b  lea     rdx, [rbx+8]; DestinationSid
0x18001921f  mov     ecx, eax; DestinationSidLength
0x180019221  call    cs:__imp_RtlCopySid
0x180019228  nop     dword ptr [rax+rax+00h]
0x18001922d  inc     word ptr [rdi+4]
0x180019231  xor     eax, eax
0x180019233  mov     [rdi], bpl
0x180019236  jmp     short loc_180019252
0x180019238  mov     eax, 0C0000099h
0x18001923d  jmp     short loc_180019252
0x18001923f  mov     eax, 0C0000059h
0x180019244  jmp     short loc_180019252
0x180019246  mov     eax, 0C000000Dh
0x18001924b  jmp     short loc_180019252
0x18001924d  mov     eax, 0C0000077h
0x180019252  mov     rbx, [rsp+48h+arg_8]
0x180019257  add     rsp, 20h
0x18001925b  pop     r15
0x18001925d  pop     r14
0x18001925f  pop     rdi
0x180019260  pop     rsi
0x180019261  pop     rbp
0x180019262  retn
```
