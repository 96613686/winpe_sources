# SddlAddAccessFilterAce

- ea: `0x180053090`
- end: `0x1800532b0`
- name: `SddlAddAccessFilterAce`
- size: `544`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, int, int, void *Src, __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001b480`

## callees

- `0x180053090`
- `0x180065042`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800531ea`
- `ntdll!RtlLengthSid` at `0x180053240`
- `ntdll!RtlLengthSid` at `0x18005325c`
- `ntdll!RtlLengthSid` at `0x1800531ea`
- `ntdll!RtlLengthSid` at `0x180053240`
- `ntdll!RtlLengthSid` at `0x18005325c`
- `ntdll!RtlValidSid` at `0x18005311b`
- `ntdll!RtlValidSid` at `0x18005311b`
- `ntdll!RtlCopySid` at `0x18005324f`
- `ntdll!RtlCopySid` at `0x18005324f`
- `ntdll!RtlValidAcl` at `0x1800530d9`
- `ntdll!RtlValidAcl` at `0x1800530d9`
- `ntdll!RtlFirstFreeAce` at `0x1800531cf`
- `ntdll!RtlFirstFreeAce` at `0x1800531cf`

## pseudocode

```c
__int64 __fastcall SddlAddAccessFilterAce(
        PACL Acl,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        ACCESS_MASK a6,
        _DWORD *Src,
        unsigned __int16 a8)
{
  __int64 result; // rax
  BYTE AclRevision; // r15
  int v13; // ecx
  bool v14; // zf
  int v15; // ecx
  unsigned int v16; // ebx
  ULONG v17; // edx
  PACE v18; // r14
  ULONG v19; // eax
  ULONG v20; // eax
  PACE Ace; // [rsp+20h] [rbp-10h] BYREF
  BYTE v22; // [rsp+80h] [rbp+50h]

  v22 = a3;
  Ace = 0;
  if ( !Acl || !RtlValidAcl(Acl) )
    return 3221225591LL;
  if ( !Src || (unsigned __int16)(a8 - 6) > 0xFFF8u || *Src != 2020897377 )
    return 3221225485LL;
  if ( !RtlValidSid((PSID)a4) )
    return 3221225592LL;
  AclRevision = 2;
  if ( (a3 & 0x40) != 0 )
  {
    if ( *(_BYTE *)(a4 + 1) != 2 )
      return 3221225485LL;
    v13 = *(_DWORD *)(a4 + 2);
    if ( !v13 )
      v13 = *(unsigned __int16 *)(a4 + 6) - 4864;
    if ( v13 )
      return 3221225485LL;
    if ( *(_DWORD *)(a4 + 8) )
      goto LABEL_21;
    v14 = *(_DWORD *)(a4 + 12) == 0;
  }
  else
  {
    v15 = *(_DWORD *)(a4 + 2);
    if ( !v15 )
      v15 = *(unsigned __int16 *)(a4 + 6) - 256;
    if ( v15 || *(_BYTE *)(a4 + 1) != 1 )
      return 3221225485LL;
    v14 = *(_DWORD *)(a4 + 8) == 0;
  }
  if ( !v14 )
    return 3221225485LL;
LABEL_21:
  if ( Acl->AclRevision > 4u )
    return 3221225561LL;
  if ( Acl->AclRevision > 2u )
    AclRevision = Acl->AclRevision;
  if ( (a3 & 0xFFFFFFA0) != 0 || (a6 & 0xFF000000) != 0 )
    return 3221225485LL;
  if ( !RtlFirstFreeAce(Acl, &Ace) )
    return 3221225591LL;
  v16 = (a8 + 3) & 0xFFFFFFFC;
  v17 = RtlLengthSid((PSID)a4) + v16 + 8;
  if ( v17 < v16 )
    return 534;
  if ( v17 > 0xFFFF )
    return 3221225485LL;
  v18 = Ace;
  if ( !Ace || (char *)Ace + v17 > (char *)Acl + Acl->AclSize )
    return 3221225625LL;
  Ace->Header.AceFlags = v22;
  v18->Header.AceType = 21;
  v18->Header.AceSize = v17;
  v18->AccessMask = a6;
  v19 = RtlLengthSid((PSID)a4);
  RtlCopySid(v19, &v18[1], (PSID)a4);
  v20 = RtlLengthSid((PSID)a4);
  memcpy_0((char *)&v18[1] + v20, Src, a8);
  ++Acl->AceCount;
  result = 0;
  Acl->AclRevision = AclRevision;
  return result;
}

```

## disassembly

```asm
0x180053090  mov     [rsp-38h+arg_8], rbx
0x180053095  mov     [rsp-38h+arg_10], r8d
0x18005309a  push    rbp
0x18005309b  push    rsi
0x18005309c  push    rdi
0x18005309d  push    r12
0x18005309f  push    r13
0x1800530a1  push    r14
0x1800530a3  push    r15
0x1800530a5  mov     rbp, rsp
0x1800530a8  sub     rsp, 30h
0x1800530ac  xor     r14d, r14d
0x1800530af  mov     [rbp+arg_1C], 100h
0x1800530b5  mov     [rbp+Ace], r14
0x1800530b9  mov     rdi, r9
0x1800530bc  mov     [rbp+arg_18], r14d
0x1800530c0  mov     ebx, r8d
0x1800530c3  mov     [rbp+arg_0], r14d
0x1800530c7  mov     rsi, rcx
0x1800530ca  mov     [rbp+arg_4], 1300h
0x1800530d0  test    rcx, rcx
0x1800530d3  jz      loc_180053296
0x1800530d9  call    cs:__imp_RtlValidAcl
0x1800530df  test    al, al
0x1800530e1  jz      loc_180053296
0x1800530e7  mov     r12, [rbp+Src]
0x1800530eb  test    r12, r12
0x1800530ee  jz      loc_18005328F
0x1800530f4  movzx   eax, [rbp+arg_38]
0x1800530f8  mov     ecx, 0FFF8h
0x1800530fd  sub     ax, 6
0x180053101  cmp     ax, cx
0x180053104  ja      loc_18005328F
0x18005310a  cmp     dword ptr [r12], 78747261h
0x180053112  jnz     loc_18005328F
0x180053118  mov     rcx, rdi; Sid
0x18005311b  call    cs:__imp_RtlValidSid
0x180053121  test    al, al
0x180053123  jnz     short loc_18005312F
0x180053125  mov     eax, 0C0000078h
0x18005312a  jmp     loc_18005329B
0x18005312f  mov     r15d, 2
0x180053135  test    bl, 40h
0x180053138  jz      short loc_18005316A
0x18005313a  cmp     [rdi+1], r15b
0x18005313e  jnz     loc_18005328F
0x180053144  mov     ecx, [rdi+2]
0x180053147  sub     ecx, [rbp+arg_0]
0x18005314a  jnz     short loc_180053156
0x18005314c  movzx   ecx, word ptr [rdi+6]
0x180053150  movzx   eax, [rbp+arg_4]
0x180053154  sub     ecx, eax
0x180053156  test    ecx, ecx
0x180053158  jnz     loc_18005328F
0x18005315e  cmp     [rdi+8], r14d
0x180053162  jnz     short loc_180053198
0x180053164  cmp     [rdi+0Ch], r14d
0x180053168  jmp     short loc_180053192
0x18005316a  mov     ecx, [rdi+2]
0x18005316d  sub     ecx, [rbp+arg_18]
0x180053170  jnz     short loc_18005317C
0x180053172  movzx   ecx, word ptr [rdi+6]
0x180053176  movzx   eax, [rbp+arg_1C]
0x18005317a  sub     ecx, eax
0x18005317c  test    ecx, ecx
0x18005317e  jnz     loc_18005328F
0x180053184  cmp     byte ptr [rdi+1], 1
0x180053188  jnz     loc_18005328F
0x18005318e  cmp     [rdi+8], r14d
0x180053192  jnz     loc_18005328F
0x180053198  cmp     byte ptr [rsi], 4
0x18005319b  ja      loc_180053288
0x1800531a1  cmp     [rsi], r15b
0x1800531a4  movzx   eax, byte ptr [rsi]
0x1800531a7  cmova   r15d, eax
0x1800531ab  test    ebx, 0FFFFFFA0h
0x1800531b1  jnz     loc_18005328F
0x1800531b7  mov     r13d, [rbp+arg_28]
0x1800531bb  test    r13d, 0FF000000h
0x1800531c2  jnz     loc_18005328F
0x1800531c8  lea     rdx, [rbp+Ace]; Ace
0x1800531cc  mov     rcx, rsi; Acl
0x1800531cf  call    cs:__imp_RtlFirstFreeAce
0x1800531d5  test    al, al
0x1800531d7  jz      loc_180053296
0x1800531dd  movzx   ebx, [rbp+arg_38]
0x1800531e1  mov     rcx, rdi; Sid
0x1800531e4  add     ebx, 3
0x1800531e7  and     ebx, 0FFFFFFFCh
0x1800531ea  call    cs:__imp_RtlLengthSid
0x1800531f0  lea     edx, [rbx+8]
0x1800531f3  add     edx, eax
0x1800531f5  cmp     edx, ebx
0x1800531f7  jnb     short loc_180053203
0x1800531f9  mov     eax, 216h
0x1800531fe  jmp     loc_18005329B
0x180053203  cmp     edx, 0FFFFh
0x180053209  ja      loc_18005328F
0x18005320f  mov     r14, [rbp+Ace]
0x180053213  test    r14, r14
0x180053216  jz      short loc_180053281
0x180053218  movzx   ecx, word ptr [rsi+2]
0x18005321c  mov     eax, edx
0x18005321e  add     rcx, rsi
0x180053221  add     rax, r14
0x180053224  cmp     rax, rcx
0x180053227  ja      short loc_180053281
0x180053229  mov     eax, [rbp+arg_10]
0x18005322c  mov     rcx, rdi; Sid
0x18005322f  mov     [r14+1], al
0x180053233  mov     byte ptr [r14], 15h
0x180053237  mov     [r14+2], dx
0x18005323c  mov     [r14+4], r13d
0x180053240  call    cs:__imp_RtlLengthSid
0x180053246  mov     r8, rdi; SourceSid
0x180053249  lea     rdx, [r14+8]; DestinationSid
0x18005324d  mov     ecx, eax; DestinationSidLength
0x18005324f  call    cs:__imp_RtlCopySid
0x180053255  movzx   ebx, [rbp+arg_38]
0x180053259  mov     rcx, rdi; Sid
0x18005325c  call    cs:__imp_RtlLengthSid
0x180053262  mov     ecx, eax
0x180053264  mov     r8d, ebx; Size
0x180053267  add     rcx, 8
0x18005326b  mov     rdx, r12; Src
0x18005326e  add     rcx, r14; void *
0x180053271  call    memcpy_0
0x180053276  inc     word ptr [rsi+4]
0x18005327a  xor     eax, eax
0x18005327c  mov     [rsi], r15b
0x18005327f  jmp     short loc_18005329B
0x180053281  mov     eax, 0C0000099h
0x180053286  jmp     short loc_18005329B
0x180053288  mov     eax, 0C0000059h
0x18005328d  jmp     short loc_18005329B
0x18005328f  mov     eax, 0C000000Dh
0x180053294  jmp     short loc_18005329B
0x180053296  mov     eax, 0C0000077h
0x18005329b  mov     rbx, [rsp+30h+arg_8]
0x1800532a0  add     rsp, 30h
0x1800532a4  pop     r15
0x1800532a6  pop     r14
0x1800532a8  pop     r13
0x1800532aa  pop     r12
0x1800532ac  pop     rdi
0x1800532ad  pop     rsi
0x1800532ae  pop     rbp
0x1800532af  retn
```
