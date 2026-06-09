# SddlAddScopedPolicyIDAce

- ea: `0x18005ed98`
- end: `0x18005ef0c`
- name: `SddlAddScopedPolicyIDAce`
- size: `372`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, PSID Sid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180019ed0`

## callees

- `0x18005ed98`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18005ee70`
- `ntdll!RtlLengthSid` at `0x18005eeb2`
- `ntdll!RtlLengthSid` at `0x18005ee70`
- `ntdll!RtlLengthSid` at `0x18005eeb2`
- `ntdll!RtlValidSid` at `0x18005edda`
- `ntdll!RtlValidSid` at `0x18005edda`
- `ntdll!RtlCopySid` at `0x18005eec7`
- `ntdll!RtlCopySid` at `0x18005eec7`
- `ntdll!RtlValidAcl` at `0x18005ee3d`
- `ntdll!RtlValidAcl` at `0x18005ee3d`
- `ntdll!RtlFirstFreeAce` at `0x18005ee59`
- `ntdll!RtlFirstFreeAce` at `0x18005ee59`

## pseudocode

```c
__int64 __fastcall SddlAddScopedPolicyIDAce(PACL Acl, __int64 a2, int a3, int a4, char *Sid)
{
  __int64 result; // rax
  int v9; // ecx
  BYTE AclRevision; // bp
  __int16 v11; // ax
  PACE v12; // rbx
  __int64 v13; // rdx
  ULONG v14; // eax
  PACE Ace; // [rsp+20h] [rbp-28h] BYREF

  Ace = 0;
  if ( !Acl )
    return 3221225591LL;
  if ( !RtlValidSid(Sid) )
    return 3221225592LL;
  v9 = *(_DWORD *)(Sid + 2);
  if ( !v9 )
    v9 = *((unsigned __int16 *)Sid + 3) - 4352;
  if ( v9 )
    return 3221225485LL;
  if ( Acl->AclRevision > 4u )
    return 3221225561LL;
  AclRevision = 2;
  if ( Acl->AclRevision > 2u )
    AclRevision = Acl->AclRevision;
  if ( (a3 & 0xFFFFFFE0) != 0 || a4 )
    return 3221225485LL;
  if ( !RtlValidAcl(Acl) || !RtlFirstFreeAce(Acl, &Ace) )
    return 3221225591LL;
  v11 = RtlLengthSid(Sid);
  v12 = Ace;
  if ( !Ace )
    return 3221225625LL;
  v13 = (unsigned __int16)(v11 + 8);
  if ( (char *)Ace + v13 > (char *)Acl + Acl->AclSize )
    return 3221225625LL;
  Ace->Header.AceFlags = a3;
  v12->Header.AceType = 19;
  v12->Header.AceSize = v13;
  v12->AccessMask = 0;
  v14 = RtlLengthSid(Sid);
  RtlCopySid(v14, &v12[1], Sid);
  ++Acl->AceCount;
  result = 0;
  Acl->AclRevision = AclRevision;
  return result;
}

```

## disassembly

```asm
0x18005ed98  mov     rax, rsp
0x18005ed9b  mov     [rax+10h], rbx
0x18005ed9f  mov     [rax+18h], rbp
0x18005eda3  push    rsi
0x18005eda4  push    rdi
0x18005eda5  push    r14
0x18005eda7  sub     rsp, 30h
0x18005edab  mov     qword ptr [rax-28h], 0
0x18005edb3  mov     ebx, r9d
0x18005edb6  mov     dword ptr [rax+8], 0
0x18005edbd  mov     r14d, r8d
0x18005edc0  mov     word ptr [rax+0Ch], 1100h
0x18005edc6  mov     rdi, rcx
0x18005edc9  test    rcx, rcx
0x18005edcc  jz      loc_18005EEF3
0x18005edd2  mov     rsi, [rsp+48h+Sid]
0x18005edd7  mov     rcx, rsi; Sid
0x18005edda  call    cs:__imp_RtlValidSid
0x18005ede1  nop     dword ptr [rax+rax+00h]
0x18005ede6  test    al, al
0x18005ede8  jnz     short loc_18005EDF4
0x18005edea  mov     eax, 0C0000078h
0x18005edef  jmp     loc_18005EEF8
0x18005edf4  mov     ecx, [rsi+2]
0x18005edf7  sub     ecx, [rsp+48h+arg_0]
0x18005edfb  jnz     short loc_18005EE08
0x18005edfd  movzx   ecx, word ptr [rsi+6]
0x18005ee01  movzx   eax, [rsp+48h+arg_4]
0x18005ee06  sub     ecx, eax
0x18005ee08  test    ecx, ecx
0x18005ee0a  jnz     loc_18005EEEC
0x18005ee10  cmp     byte ptr [rdi], 4
0x18005ee13  ja      loc_18005EEE5
0x18005ee19  movzx   eax, byte ptr [rdi]
0x18005ee1c  lea     ebp, [rcx+2]
0x18005ee1f  cmp     [rdi], bpl
0x18005ee22  cmova   ebp, eax
0x18005ee25  test    r14d, 0FFFFFFE0h
0x18005ee2c  jnz     loc_18005EEEC
0x18005ee32  test    ebx, ebx
0x18005ee34  jnz     loc_18005EEEC
0x18005ee3a  mov     rcx, rdi; Acl
0x18005ee3d  call    cs:__imp_RtlValidAcl
0x18005ee44  nop     dword ptr [rax+rax+00h]
0x18005ee49  test    al, al
0x18005ee4b  jz      loc_18005EEF3
0x18005ee51  lea     rdx, [rsp+48h+Ace]; Ace
0x18005ee56  mov     rcx, rdi; Acl
0x18005ee59  call    cs:__imp_RtlFirstFreeAce
0x18005ee60  nop     dword ptr [rax+rax+00h]
0x18005ee65  test    al, al
0x18005ee67  jz      loc_18005EEF3
0x18005ee6d  mov     rcx, rsi; Sid
0x18005ee70  call    cs:__imp_RtlLengthSid
0x18005ee77  nop     dword ptr [rax+rax+00h]
0x18005ee7c  mov     rbx, [rsp+48h+Ace]
0x18005ee81  test    rbx, rbx
0x18005ee84  jz      short loc_18005EEDE
0x18005ee86  movzx   ecx, word ptr [rdi+2]
0x18005ee8a  add     ax, 8
0x18005ee8e  movzx   edx, ax
0x18005ee91  add     rcx, rdi
0x18005ee94  lea     rax, [rbx+rdx]
0x18005ee98  cmp     rax, rcx
0x18005ee9b  ja      short loc_18005EEDE
0x18005ee9d  mov     rcx, rsi; Sid
0x18005eea0  mov     [rbx+1], r14b
0x18005eea4  mov     byte ptr [rbx], 13h
0x18005eea7  mov     [rbx+2], dx
0x18005eeab  mov     dword ptr [rbx+4], 0
0x18005eeb2  call    cs:__imp_RtlLengthSid
0x18005eeb9  nop     dword ptr [rax+rax+00h]
0x18005eebe  mov     r8, rsi; SourceSid
0x18005eec1  lea     rdx, [rbx+8]; DestinationSid
0x18005eec5  mov     ecx, eax; DestinationSidLength
0x18005eec7  call    cs:__imp_RtlCopySid
0x18005eece  nop     dword ptr [rax+rax+00h]
0x18005eed3  inc     word ptr [rdi+4]
0x18005eed7  xor     eax, eax
0x18005eed9  mov     [rdi], bpl
0x18005eedc  jmp     short loc_18005EEF8
0x18005eede  mov     eax, 0C0000099h
0x18005eee3  jmp     short loc_18005EEF8
0x18005eee5  mov     eax, 0C0000059h
0x18005eeea  jmp     short loc_18005EEF8
0x18005eeec  mov     eax, 0C000000Dh
0x18005eef1  jmp     short loc_18005EEF8
0x18005eef3  mov     eax, 0C0000077h
0x18005eef8  mov     rbx, [rsp+48h+arg_8]
0x18005eefd  mov     rbp, [rsp+48h+arg_10]
0x18005ef02  add     rsp, 30h
0x18005ef06  pop     r14
0x18005ef08  pop     rdi
0x18005ef09  pop     rsi
0x18005ef0a  retn
```
