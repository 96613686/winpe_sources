# SddlAddMandatoryAce

- ea: `0x18001b2c0`
- end: `0x18001b40b`
- name: `SddlAddMandatoryAce`
- size: `331`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001b480`

## callees

- `0x18001b2c0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001b380`
- `ntdll!RtlLengthSid` at `0x18001b3b9`
- `ntdll!RtlLengthSid` at `0x18001b380`
- `ntdll!RtlLengthSid` at `0x18001b3b9`
- `ntdll!RtlValidSid` at `0x18001b2fc`
- `ntdll!RtlValidSid` at `0x18001b2fc`
- `ntdll!RtlCopySid` at `0x18001b3c8`
- `ntdll!RtlCopySid` at `0x18001b3c8`
- `ntdll!RtlValidAcl` at `0x18001b35d`
- `ntdll!RtlValidAcl` at `0x18001b35d`
- `ntdll!RtlFirstFreeAce` at `0x18001b373`
- `ntdll!RtlFirstFreeAce` at `0x18001b373`

## pseudocode

```c
__int64 __fastcall SddlAddMandatoryAce(PACL Acl, __int64 a2, int a3, __int64 a4, int a5, int a6)
{
  int v9; // ecx
  BYTE AclRevision; // bp
  int v11; // r14d
  __int16 v12; // ax
  PACE v13; // rbx
  __int64 v14; // rdx
  ULONG v15; // eax
  __int64 result; // rax
  PACE Ace; // [rsp+68h] [rbp+20h] BYREF

  Ace = 0;
  if ( !Acl )
    return 3221225591LL;
  if ( !RtlValidSid((PSID)a4) )
    return 3221225592LL;
  v9 = *(_DWORD *)(a4 + 2);
  if ( !v9 )
    v9 = *(unsigned __int16 *)(a4 + 6) - 4096;
  if ( v9 )
    return 3221225485LL;
  if ( Acl->AclRevision > 4u )
    return 3221225561LL;
  AclRevision = 2;
  if ( Acl->AclRevision > 2u )
    AclRevision = Acl->AclRevision;
  if ( (a3 & 0xFFFFFFE0) != 0 )
    return 3221225485LL;
  v11 = a6;
  if ( (a6 & 0xFFFFFFF8) != 0 )
    return 3221225485LL;
  if ( !RtlValidAcl(Acl) || !RtlFirstFreeAce(Acl, &Ace) )
    return 3221225591LL;
  v12 = RtlLengthSid((PSID)a4);
  v13 = Ace;
  if ( !Ace )
    return 3221225625LL;
  v14 = (unsigned __int16)(v12 + 8);
  if ( (char *)Ace + v14 > (char *)Acl + Acl->AclSize )
    return 3221225625LL;
  Ace->Header.AceFlags = a3;
  v13->Header.AceType = 17;
  v13->Header.AceSize = v14;
  v13->AccessMask = v11;
  v15 = RtlLengthSid((PSID)a4);
  RtlCopySid(v15, &v13[1], (PSID)a4);
  ++Acl->AceCount;
  result = 0;
  Acl->AclRevision = AclRevision;
  return result;
}

```

## disassembly

```asm
0x18001b2c0  mov     rax, rsp
0x18001b2c3  mov     [rax+10h], rbx
0x18001b2c7  push    rbp
0x18001b2c8  push    rsi
0x18001b2c9  push    rdi
0x18001b2ca  push    r14
0x18001b2cc  push    r15
0x18001b2ce  sub     rsp, 20h
0x18001b2d2  mov     qword ptr [rax+20h], 0
0x18001b2da  mov     rsi, r9
0x18001b2dd  mov     dword ptr [rax+8], 0
0x18001b2e4  mov     r15d, r8d
0x18001b2e7  mov     word ptr [rax+0Ch], 1000h
0x18001b2ed  mov     rdi, rcx
0x18001b2f0  test    rcx, rcx
0x18001b2f3  jz      loc_18001B3EF
0x18001b2f9  mov     rcx, r9; Sid
0x18001b2fc  call    cs:__imp_RtlValidSid
0x18001b302  test    al, al
0x18001b304  jz      loc_18001B3FD
0x18001b30a  mov     ecx, [rsi+2]
0x18001b30d  sub     ecx, [rsp+48h+arg_0]
0x18001b311  jnz     short loc_18001B31E
0x18001b313  movzx   ecx, word ptr [rsi+6]
0x18001b317  movzx   eax, [rsp+48h+arg_4]
0x18001b31c  sub     ecx, eax
0x18001b31e  test    ecx, ecx
0x18001b320  jnz     loc_18001B3E8
0x18001b326  cmp     byte ptr [rdi], 4
0x18001b329  ja      loc_18001B404
0x18001b32f  movzx   eax, byte ptr [rdi]
0x18001b332  lea     ebp, [rcx+2]
0x18001b335  cmp     [rdi], bpl
0x18001b338  cmova   ebp, eax
0x18001b33b  test    r15d, 0FFFFFFE0h
0x18001b342  jnz     loc_18001B3E8
0x18001b348  mov     r14d, [rsp+48h+arg_28]
0x18001b34d  test    r14d, 0FFFFFFF8h
0x18001b354  jnz     loc_18001B3E8
0x18001b35a  mov     rcx, rdi; Acl
0x18001b35d  call    cs:__imp_RtlValidAcl
0x18001b363  test    al, al
0x18001b365  jz      loc_18001B3EF
0x18001b36b  lea     rdx, [rsp+48h+Ace]; Ace
0x18001b370  mov     rcx, rdi; Acl
0x18001b373  call    cs:__imp_RtlFirstFreeAce
0x18001b379  test    al, al
0x18001b37b  jz      short loc_18001B3EF
0x18001b37d  mov     rcx, rsi; Sid
0x18001b380  call    cs:__imp_RtlLengthSid
0x18001b386  mov     rbx, [rsp+48h+Ace]
0x18001b38b  test    rbx, rbx
0x18001b38e  jz      short loc_18001B3F6
0x18001b390  movzx   ecx, word ptr [rdi+2]
0x18001b394  add     ax, 8
0x18001b398  movzx   edx, ax
0x18001b39b  add     rcx, rdi
0x18001b39e  lea     rax, [rbx+rdx]
0x18001b3a2  cmp     rax, rcx
0x18001b3a5  ja      short loc_18001B3F6
0x18001b3a7  mov     rcx, rsi; Sid
0x18001b3aa  mov     [rbx+1], r15b
0x18001b3ae  mov     byte ptr [rbx], 11h
0x18001b3b1  mov     [rbx+2], dx
0x18001b3b5  mov     [rbx+4], r14d
0x18001b3b9  call    cs:__imp_RtlLengthSid
0x18001b3bf  mov     r8, rsi; SourceSid
0x18001b3c2  lea     rdx, [rbx+8]; DestinationSid
0x18001b3c6  mov     ecx, eax; DestinationSidLength
0x18001b3c8  call    cs:__imp_RtlCopySid
0x18001b3ce  inc     word ptr [rdi+4]
0x18001b3d2  xor     eax, eax
0x18001b3d4  mov     [rdi], bpl
0x18001b3d7  mov     rbx, [rsp+48h+arg_8]
0x18001b3dc  add     rsp, 20h
0x18001b3e0  pop     r15
0x18001b3e2  pop     r14
0x18001b3e4  pop     rdi
0x18001b3e5  pop     rsi
0x18001b3e6  pop     rbp
0x18001b3e7  retn
0x18001b3e8  mov     eax, 0C000000Dh
0x18001b3ed  jmp     short loc_18001B3D7
0x18001b3ef  mov     eax, 0C0000077h
0x18001b3f4  jmp     short loc_18001B3D7
0x18001b3f6  mov     eax, 0C0000099h
0x18001b3fb  jmp     short loc_18001B3D7
0x18001b3fd  mov     eax, 0C0000078h
0x18001b402  jmp     short loc_18001B3D7
0x18001b404  mov     eax, 0C0000059h
0x18001b409  jmp     short loc_18001B3D7
```
