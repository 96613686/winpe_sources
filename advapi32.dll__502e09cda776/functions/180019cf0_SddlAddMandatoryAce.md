# SddlAddMandatoryAce

- ea: `0x180019cf0`
- end: `0x180019e64`
- name: `SddlAddMandatoryAce`
- size: `372`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180019ed0`

## callees

- `0x180019cf0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180019dc6`
- `ntdll!RtlLengthSid` at `0x180019e05`
- `ntdll!RtlLengthSid` at `0x180019dc6`
- `ntdll!RtlLengthSid` at `0x180019e05`
- `ntdll!RtlValidSid` at `0x180019d2c`
- `ntdll!RtlValidSid` at `0x180019d2c`
- `ntdll!RtlCopySid` at `0x180019e1a`
- `ntdll!RtlCopySid` at `0x180019e1a`
- `ntdll!RtlValidAcl` at `0x180019d93`
- `ntdll!RtlValidAcl` at `0x180019d93`
- `ntdll!RtlFirstFreeAce` at `0x180019daf`
- `ntdll!RtlFirstFreeAce` at `0x180019daf`

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
0x180019cf0  mov     rax, rsp
0x180019cf3  mov     [rax+10h], rbx
0x180019cf7  push    rbp
0x180019cf8  push    rsi
0x180019cf9  push    rdi
0x180019cfa  push    r14
0x180019cfc  push    r15
0x180019cfe  sub     rsp, 20h
0x180019d02  mov     qword ptr [rax+20h], 0
0x180019d0a  mov     rsi, r9
0x180019d0d  mov     dword ptr [rax+8], 0
0x180019d14  mov     r15d, r8d
0x180019d17  mov     word ptr [rax+0Ch], 1000h
0x180019d1d  mov     rdi, rcx
0x180019d20  test    rcx, rcx
0x180019d23  jz      loc_180019E48
0x180019d29  mov     rcx, r9; Sid
0x180019d2c  call    cs:__imp_RtlValidSid
0x180019d33  nop     dword ptr [rax+rax+00h]
0x180019d38  test    al, al
0x180019d3a  jz      loc_180019E56
0x180019d40  mov     ecx, [rsi+2]
0x180019d43  sub     ecx, [rsp+48h+arg_0]
0x180019d47  jnz     short loc_180019D54
0x180019d49  movzx   ecx, word ptr [rsi+6]
0x180019d4d  movzx   eax, [rsp+48h+arg_4]
0x180019d52  sub     ecx, eax
0x180019d54  test    ecx, ecx
0x180019d56  jnz     loc_180019E41
0x180019d5c  cmp     byte ptr [rdi], 4
0x180019d5f  ja      loc_180019E5D
0x180019d65  movzx   eax, byte ptr [rdi]
0x180019d68  lea     ebp, [rcx+2]
0x180019d6b  cmp     [rdi], bpl
0x180019d6e  cmova   ebp, eax
0x180019d71  test    r15d, 0FFFFFFE0h
0x180019d78  jnz     loc_180019E41
0x180019d7e  mov     r14d, [rsp+48h+arg_28]
0x180019d83  test    r14d, 0FFFFFFF8h
0x180019d8a  jnz     loc_180019E41
0x180019d90  mov     rcx, rdi; Acl
0x180019d93  call    cs:__imp_RtlValidAcl
0x180019d9a  nop     dword ptr [rax+rax+00h]
0x180019d9f  test    al, al
0x180019da1  jz      loc_180019E48
0x180019da7  lea     rdx, [rsp+48h+Ace]; Ace
0x180019dac  mov     rcx, rdi; Acl
0x180019daf  call    cs:__imp_RtlFirstFreeAce
0x180019db6  nop     dword ptr [rax+rax+00h]
0x180019dbb  test    al, al
0x180019dbd  jz      loc_180019E48
0x180019dc3  mov     rcx, rsi; Sid
0x180019dc6  call    cs:__imp_RtlLengthSid
0x180019dcd  nop     dword ptr [rax+rax+00h]
0x180019dd2  mov     rbx, [rsp+48h+Ace]
0x180019dd7  test    rbx, rbx
0x180019dda  jz      short loc_180019E4F
0x180019ddc  movzx   ecx, word ptr [rdi+2]
0x180019de0  add     ax, 8
0x180019de4  movzx   edx, ax
0x180019de7  add     rcx, rdi
0x180019dea  lea     rax, [rbx+rdx]
0x180019dee  cmp     rax, rcx
0x180019df1  ja      short loc_180019E4F
0x180019df3  mov     rcx, rsi; Sid
0x180019df6  mov     [rbx+1], r15b
0x180019dfa  mov     byte ptr [rbx], 11h
0x180019dfd  mov     [rbx+2], dx
0x180019e01  mov     [rbx+4], r14d
0x180019e05  call    cs:__imp_RtlLengthSid
0x180019e0c  nop     dword ptr [rax+rax+00h]
0x180019e11  mov     r8, rsi; SourceSid
0x180019e14  lea     rdx, [rbx+8]; DestinationSid
0x180019e18  mov     ecx, eax; DestinationSidLength
0x180019e1a  call    cs:__imp_RtlCopySid
0x180019e21  nop     dword ptr [rax+rax+00h]
0x180019e26  inc     word ptr [rdi+4]
0x180019e2a  xor     eax, eax
0x180019e2c  mov     [rdi], bpl
0x180019e2f  mov     rbx, [rsp+48h+arg_8]
0x180019e34  add     rsp, 20h
0x180019e38  pop     r15
0x180019e3a  pop     r14
0x180019e3c  pop     rdi
0x180019e3d  pop     rsi
0x180019e3e  pop     rbp
0x180019e3f  retn
0x180019e41  mov     eax, 0C000000Dh
0x180019e46  jmp     short loc_180019E2F
0x180019e48  mov     eax, 0C0000077h
0x180019e4d  jmp     short loc_180019E2F
0x180019e4f  mov     eax, 0C0000099h
0x180019e54  jmp     short loc_180019E2F
0x180019e56  mov     eax, 0C0000078h
0x180019e5b  jmp     short loc_180019E2F
0x180019e5d  mov     eax, 0C0000059h
0x180019e62  jmp     short loc_180019E2F
```
