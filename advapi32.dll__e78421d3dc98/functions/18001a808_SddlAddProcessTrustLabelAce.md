# SddlAddProcessTrustLabelAce

- ea: `0x18001a808`
- end: `0x18001a94b`
- name: `SddlAddProcessTrustLabelAce`
- size: `323`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001b480`

## callees

- `0x18001a808`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001a8c7`
- `ntdll!RtlLengthSid` at `0x18001a900`
- `ntdll!RtlLengthSid` at `0x18001a8c7`
- `ntdll!RtlLengthSid` at `0x18001a900`
- `ntdll!RtlValidSid` at `0x18001a852`
- `ntdll!RtlValidSid` at `0x18001a852`
- `ntdll!RtlCopySid` at `0x18001a90f`
- `ntdll!RtlCopySid` at `0x18001a90f`
- `ntdll!RtlValidAcl` at `0x18001a841`
- `ntdll!RtlValidAcl` at `0x18001a841`
- `ntdll!RtlFirstFreeAce` at `0x18001a8ba`
- `ntdll!RtlFirstFreeAce` at `0x18001a8ba`

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
0x18001a808  mov     rax, rsp
0x18001a80b  mov     [rax+10h], rbx
0x18001a80f  push    rbp
0x18001a810  push    rsi
0x18001a811  push    rdi
0x18001a812  push    r14
0x18001a814  push    r15
0x18001a816  sub     rsp, 20h
0x18001a81a  mov     qword ptr [rax+20h], 0
0x18001a822  mov     rsi, r9
0x18001a825  mov     dword ptr [rax+8], 0
0x18001a82c  mov     r15d, r8d
0x18001a82f  mov     word ptr [rax+0Ch], 1300h
0x18001a835  mov     rdi, rcx
0x18001a838  test    rcx, rcx
0x18001a83b  jz      loc_18001A935
0x18001a841  call    cs:__imp_RtlValidAcl
0x18001a847  test    al, al
0x18001a849  jz      loc_18001A935
0x18001a84f  mov     rcx, rsi; Sid
0x18001a852  call    cs:__imp_RtlValidSid
0x18001a858  test    al, al
0x18001a85a  jnz     short loc_18001A866
0x18001a85c  mov     eax, 0C0000078h
0x18001a861  jmp     loc_18001A93A
0x18001a866  mov     ecx, [rsi+2]
0x18001a869  sub     ecx, [rsp+48h+arg_0]
0x18001a86d  jnz     short loc_18001A87A
0x18001a86f  movzx   ecx, word ptr [rsi+6]
0x18001a873  movzx   eax, [rsp+48h+arg_4]
0x18001a878  sub     ecx, eax
0x18001a87a  test    ecx, ecx
0x18001a87c  jnz     loc_18001A92E
0x18001a882  cmp     byte ptr [rdi], 4
0x18001a885  ja      loc_18001A927
0x18001a88b  movzx   eax, byte ptr [rdi]
0x18001a88e  lea     ebp, [rcx+2]
0x18001a891  cmp     [rdi], bpl
0x18001a894  cmova   ebp, eax
0x18001a897  test    r15d, 0FFFFFFE0h
0x18001a89e  jnz     loc_18001A92E
0x18001a8a4  mov     r14d, [rsp+48h+arg_28]
0x18001a8a9  test    r14d, 0FF000000h
0x18001a8b0  jnz     short loc_18001A92E
0x18001a8b2  lea     rdx, [rsp+48h+Ace]; Ace
0x18001a8b7  mov     rcx, rdi; Acl
0x18001a8ba  call    cs:__imp_RtlFirstFreeAce
0x18001a8c0  test    al, al
0x18001a8c2  jz      short loc_18001A935
0x18001a8c4  mov     rcx, rsi; Sid
0x18001a8c7  call    cs:__imp_RtlLengthSid
0x18001a8cd  mov     rbx, [rsp+48h+Ace]
0x18001a8d2  test    rbx, rbx
0x18001a8d5  jz      short loc_18001A920
0x18001a8d7  movzx   ecx, word ptr [rdi+2]
0x18001a8db  add     ax, 8
0x18001a8df  movzx   edx, ax
0x18001a8e2  add     rcx, rdi
0x18001a8e5  lea     rax, [rbx+rdx]
0x18001a8e9  cmp     rax, rcx
0x18001a8ec  ja      short loc_18001A920
0x18001a8ee  mov     rcx, rsi; Sid
0x18001a8f1  mov     [rbx+1], r15b
0x18001a8f5  mov     byte ptr [rbx], 14h
0x18001a8f8  mov     [rbx+2], dx
0x18001a8fc  mov     [rbx+4], r14d
0x18001a900  call    cs:__imp_RtlLengthSid
0x18001a906  mov     r8, rsi; SourceSid
0x18001a909  lea     rdx, [rbx+8]; DestinationSid
0x18001a90d  mov     ecx, eax; DestinationSidLength
0x18001a90f  call    cs:__imp_RtlCopySid
0x18001a915  inc     word ptr [rdi+4]
0x18001a919  xor     eax, eax
0x18001a91b  mov     [rdi], bpl
0x18001a91e  jmp     short loc_18001A93A
0x18001a920  mov     eax, 0C0000099h
0x18001a925  jmp     short loc_18001A93A
0x18001a927  mov     eax, 0C0000059h
0x18001a92c  jmp     short loc_18001A93A
0x18001a92e  mov     eax, 0C000000Dh
0x18001a933  jmp     short loc_18001A93A
0x18001a935  mov     eax, 0C0000077h
0x18001a93a  mov     rbx, [rsp+48h+arg_8]
0x18001a93f  add     rsp, 20h
0x18001a943  pop     r15
0x18001a945  pop     r14
0x18001a947  pop     rdi
0x18001a948  pop     rsi
0x18001a949  pop     rbp
0x18001a94a  retn
```
