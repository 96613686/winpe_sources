# SddlAddAccessFilterAce

- ea: `0x18005eb44`
- end: `0x18005ed8f`
- name: `SddlAddAccessFilterAce`
- size: `587`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, int, int, void *Src, __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180019ed0`

## callees

- `0x18005eb44`
- `0x180072042`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18005ecb0`
- `ntdll!RtlLengthSid` at `0x18005ed0c`
- `ntdll!RtlLengthSid` at `0x18005ed34`
- `ntdll!RtlLengthSid` at `0x18005ecb0`
- `ntdll!RtlLengthSid` at `0x18005ed0c`
- `ntdll!RtlLengthSid` at `0x18005ed34`
- `ntdll!RtlValidSid` at `0x18005ebd5`
- `ntdll!RtlValidSid` at `0x18005ebd5`
- `ntdll!RtlCopySid` at `0x18005ed21`
- `ntdll!RtlCopySid` at `0x18005ed21`
- `ntdll!RtlValidAcl` at `0x18005eb8d`
- `ntdll!RtlValidAcl` at `0x18005eb8d`
- `ntdll!RtlFirstFreeAce` at `0x18005ec8f`
- `ntdll!RtlFirstFreeAce` at `0x18005ec8f`

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
0x18005eb44  mov     [rsp-38h+arg_8], rbx
0x18005eb49  mov     [rsp-38h+arg_10], r8d
0x18005eb4e  push    rbp
0x18005eb4f  push    rsi
0x18005eb50  push    rdi
0x18005eb51  push    r12
0x18005eb53  push    r13
0x18005eb55  push    r14
0x18005eb57  push    r15
0x18005eb59  mov     rbp, rsp
0x18005eb5c  sub     rsp, 30h
0x18005eb60  xor     r14d, r14d
0x18005eb63  mov     [rbp+arg_1C], 100h
0x18005eb69  mov     [rbp+Ace], r14
0x18005eb6d  mov     rdi, r9
0x18005eb70  mov     [rbp+arg_18], r14d
0x18005eb74  mov     ebx, r8d
0x18005eb77  mov     [rbp+arg_0], r14d
0x18005eb7b  mov     rsi, rcx
0x18005eb7e  mov     [rbp+arg_4], 1300h
0x18005eb84  test    rcx, rcx
0x18005eb87  jz      loc_18005ED74
0x18005eb8d  call    cs:__imp_RtlValidAcl
0x18005eb94  nop     dword ptr [rax+rax+00h]
0x18005eb99  test    al, al
0x18005eb9b  jz      loc_18005ED74
0x18005eba1  mov     r12, [rbp+Src]
0x18005eba5  test    r12, r12
0x18005eba8  jz      loc_18005ED6D
0x18005ebae  movzx   eax, [rbp+arg_38]
0x18005ebb2  mov     ecx, 0FFF8h
0x18005ebb7  sub     ax, 6
0x18005ebbb  cmp     ax, cx
0x18005ebbe  ja      loc_18005ED6D
0x18005ebc4  cmp     dword ptr [r12], 78747261h
0x18005ebcc  jnz     loc_18005ED6D
0x18005ebd2  mov     rcx, rdi; Sid
0x18005ebd5  call    cs:__imp_RtlValidSid
0x18005ebdc  nop     dword ptr [rax+rax+00h]
0x18005ebe1  test    al, al
0x18005ebe3  jnz     short loc_18005EBEF
0x18005ebe5  mov     eax, 0C0000078h
0x18005ebea  jmp     loc_18005ED79
0x18005ebef  mov     r15d, 2
0x18005ebf5  test    bl, 40h
0x18005ebf8  jz      short loc_18005EC2A
0x18005ebfa  cmp     [rdi+1], r15b
0x18005ebfe  jnz     loc_18005ED6D
0x18005ec04  mov     ecx, [rdi+2]
0x18005ec07  sub     ecx, [rbp+arg_0]
0x18005ec0a  jnz     short loc_18005EC16
0x18005ec0c  movzx   ecx, word ptr [rdi+6]
0x18005ec10  movzx   eax, [rbp+arg_4]
0x18005ec14  sub     ecx, eax
0x18005ec16  test    ecx, ecx
0x18005ec18  jnz     loc_18005ED6D
0x18005ec1e  cmp     [rdi+8], r14d
0x18005ec22  jnz     short loc_18005EC58
0x18005ec24  cmp     [rdi+0Ch], r14d
0x18005ec28  jmp     short loc_18005EC52
0x18005ec2a  mov     ecx, [rdi+2]
0x18005ec2d  sub     ecx, [rbp+arg_18]
0x18005ec30  jnz     short loc_18005EC3C
0x18005ec32  movzx   ecx, word ptr [rdi+6]
0x18005ec36  movzx   eax, [rbp+arg_1C]
0x18005ec3a  sub     ecx, eax
0x18005ec3c  test    ecx, ecx
0x18005ec3e  jnz     loc_18005ED6D
0x18005ec44  cmp     byte ptr [rdi+1], 1
0x18005ec48  jnz     loc_18005ED6D
0x18005ec4e  cmp     [rdi+8], r14d
0x18005ec52  jnz     loc_18005ED6D
0x18005ec58  cmp     byte ptr [rsi], 4
0x18005ec5b  ja      loc_18005ED66
0x18005ec61  cmp     [rsi], r15b
0x18005ec64  movzx   eax, byte ptr [rsi]
0x18005ec67  cmova   r15d, eax
0x18005ec6b  test    ebx, 0FFFFFFA0h
0x18005ec71  jnz     loc_18005ED6D
0x18005ec77  mov     r13d, [rbp+arg_28]
0x18005ec7b  test    r13d, 0FF000000h
0x18005ec82  jnz     loc_18005ED6D
0x18005ec88  lea     rdx, [rbp+Ace]; Ace
0x18005ec8c  mov     rcx, rsi; Acl
0x18005ec8f  call    cs:__imp_RtlFirstFreeAce
0x18005ec96  nop     dword ptr [rax+rax+00h]
0x18005ec9b  test    al, al
0x18005ec9d  jz      loc_18005ED74
0x18005eca3  movzx   ebx, [rbp+arg_38]
0x18005eca7  mov     rcx, rdi; Sid
0x18005ecaa  add     ebx, 3
0x18005ecad  and     ebx, 0FFFFFFFCh
0x18005ecb0  call    cs:__imp_RtlLengthSid
0x18005ecb7  nop     dword ptr [rax+rax+00h]
0x18005ecbc  lea     edx, [rbx+8]
0x18005ecbf  add     edx, eax
0x18005ecc1  cmp     edx, ebx
0x18005ecc3  jnb     short loc_18005ECCF
0x18005ecc5  mov     eax, 216h
0x18005ecca  jmp     loc_18005ED79
0x18005eccf  cmp     edx, 0FFFFh
0x18005ecd5  ja      loc_18005ED6D
0x18005ecdb  mov     r14, [rbp+Ace]
0x18005ecdf  test    r14, r14
0x18005ece2  jz      short loc_18005ED5F
0x18005ece4  movzx   ecx, word ptr [rsi+2]
0x18005ece8  mov     eax, edx
0x18005ecea  add     rcx, rsi
0x18005eced  add     rax, r14
0x18005ecf0  cmp     rax, rcx
0x18005ecf3  ja      short loc_18005ED5F
0x18005ecf5  mov     eax, [rbp+arg_10]
0x18005ecf8  mov     rcx, rdi; Sid
0x18005ecfb  mov     [r14+1], al
0x18005ecff  mov     byte ptr [r14], 15h
0x18005ed03  mov     [r14+2], dx
0x18005ed08  mov     [r14+4], r13d
0x18005ed0c  call    cs:__imp_RtlLengthSid
0x18005ed13  nop     dword ptr [rax+rax+00h]
0x18005ed18  mov     r8, rdi; SourceSid
0x18005ed1b  lea     rdx, [r14+8]; DestinationSid
0x18005ed1f  mov     ecx, eax; DestinationSidLength
0x18005ed21  call    cs:__imp_RtlCopySid
0x18005ed28  nop     dword ptr [rax+rax+00h]
0x18005ed2d  movzx   ebx, [rbp+arg_38]
0x18005ed31  mov     rcx, rdi; Sid
0x18005ed34  call    cs:__imp_RtlLengthSid
0x18005ed3b  nop     dword ptr [rax+rax+00h]
0x18005ed40  mov     ecx, eax
0x18005ed42  mov     r8d, ebx; Size
0x18005ed45  add     rcx, 8
0x18005ed49  mov     rdx, r12; Src
0x18005ed4c  add     rcx, r14; void *
0x18005ed4f  call    memcpy_0
0x18005ed54  inc     word ptr [rsi+4]
0x18005ed58  xor     eax, eax
0x18005ed5a  mov     [rsi], r15b
0x18005ed5d  jmp     short loc_18005ED79
0x18005ed5f  mov     eax, 0C0000099h
0x18005ed64  jmp     short loc_18005ED79
0x18005ed66  mov     eax, 0C0000059h
0x18005ed6b  jmp     short loc_18005ED79
0x18005ed6d  mov     eax, 0C000000Dh
0x18005ed72  jmp     short loc_18005ED79
0x18005ed74  mov     eax, 0C0000077h
0x18005ed79  mov     rbx, [rsp+30h+arg_8]
0x18005ed7e  add     rsp, 30h
0x18005ed82  pop     r15
0x18005ed84  pop     r14
0x18005ed86  pop     r13
0x18005ed88  pop     r12
0x18005ed8a  pop     rdi
0x18005ed8b  pop     rsi
0x18005ed8c  pop     rbp
0x18005ed8d  retn
```
