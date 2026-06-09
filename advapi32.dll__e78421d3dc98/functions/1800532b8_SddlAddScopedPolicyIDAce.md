# SddlAddScopedPolicyIDAce

- ea: `0x1800532b8`
- end: `0x180053403`
- name: `SddlAddScopedPolicyIDAce`
- size: `331`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, PSID Sid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18001b480`

## callees

- `0x1800532b8`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18005337a`
- `ntdll!RtlLengthSid` at `0x1800533b6`
- `ntdll!RtlLengthSid` at `0x18005337a`
- `ntdll!RtlLengthSid` at `0x1800533b6`
- `ntdll!RtlValidSid` at `0x1800532fa`
- `ntdll!RtlValidSid` at `0x1800532fa`
- `ntdll!RtlCopySid` at `0x1800533c5`
- `ntdll!RtlCopySid` at `0x1800533c5`
- `ntdll!RtlValidAcl` at `0x180053357`
- `ntdll!RtlValidAcl` at `0x180053357`
- `ntdll!RtlFirstFreeAce` at `0x18005336d`
- `ntdll!RtlFirstFreeAce` at `0x18005336d`

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
0x1800532b8  mov     rax, rsp
0x1800532bb  mov     [rax+10h], rbx
0x1800532bf  mov     [rax+18h], rbp
0x1800532c3  push    rsi
0x1800532c4  push    rdi
0x1800532c5  push    r14
0x1800532c7  sub     rsp, 30h
0x1800532cb  mov     qword ptr [rax-28h], 0
0x1800532d3  mov     ebx, r9d
0x1800532d6  mov     dword ptr [rax+8], 0
0x1800532dd  mov     r14d, r8d
0x1800532e0  mov     word ptr [rax+0Ch], 1100h
0x1800532e6  mov     rdi, rcx
0x1800532e9  test    rcx, rcx
0x1800532ec  jz      loc_1800533EB
0x1800532f2  mov     rsi, [rsp+48h+Sid]
0x1800532f7  mov     rcx, rsi; Sid
0x1800532fa  call    cs:__imp_RtlValidSid
0x180053300  test    al, al
0x180053302  jnz     short loc_18005330E
0x180053304  mov     eax, 0C0000078h
0x180053309  jmp     loc_1800533F0
0x18005330e  mov     ecx, [rsi+2]
0x180053311  sub     ecx, [rsp+48h+arg_0]
0x180053315  jnz     short loc_180053322
0x180053317  movzx   ecx, word ptr [rsi+6]
0x18005331b  movzx   eax, [rsp+48h+arg_4]
0x180053320  sub     ecx, eax
0x180053322  test    ecx, ecx
0x180053324  jnz     loc_1800533E4
0x18005332a  cmp     byte ptr [rdi], 4
0x18005332d  ja      loc_1800533DD
0x180053333  movzx   eax, byte ptr [rdi]
0x180053336  lea     ebp, [rcx+2]
0x180053339  cmp     [rdi], bpl
0x18005333c  cmova   ebp, eax
0x18005333f  test    r14d, 0FFFFFFE0h
0x180053346  jnz     loc_1800533E4
0x18005334c  test    ebx, ebx
0x18005334e  jnz     loc_1800533E4
0x180053354  mov     rcx, rdi; Acl
0x180053357  call    cs:__imp_RtlValidAcl
0x18005335d  test    al, al
0x18005335f  jz      loc_1800533EB
0x180053365  lea     rdx, [rsp+48h+Ace]; Ace
0x18005336a  mov     rcx, rdi; Acl
0x18005336d  call    cs:__imp_RtlFirstFreeAce
0x180053373  test    al, al
0x180053375  jz      short loc_1800533EB
0x180053377  mov     rcx, rsi; Sid
0x18005337a  call    cs:__imp_RtlLengthSid
0x180053380  mov     rbx, [rsp+48h+Ace]
0x180053385  test    rbx, rbx
0x180053388  jz      short loc_1800533D6
0x18005338a  movzx   ecx, word ptr [rdi+2]
0x18005338e  add     ax, 8
0x180053392  movzx   edx, ax
0x180053395  add     rcx, rdi
0x180053398  lea     rax, [rbx+rdx]
0x18005339c  cmp     rax, rcx
0x18005339f  ja      short loc_1800533D6
0x1800533a1  mov     rcx, rsi; Sid
0x1800533a4  mov     [rbx+1], r14b
0x1800533a8  mov     byte ptr [rbx], 13h
0x1800533ab  mov     [rbx+2], dx
0x1800533af  mov     dword ptr [rbx+4], 0
0x1800533b6  call    cs:__imp_RtlLengthSid
0x1800533bc  mov     r8, rsi; SourceSid
0x1800533bf  lea     rdx, [rbx+8]; DestinationSid
0x1800533c3  mov     ecx, eax; DestinationSidLength
0x1800533c5  call    cs:__imp_RtlCopySid
0x1800533cb  inc     word ptr [rdi+4]
0x1800533cf  xor     eax, eax
0x1800533d1  mov     [rdi], bpl
0x1800533d4  jmp     short loc_1800533F0
0x1800533d6  mov     eax, 0C0000099h
0x1800533db  jmp     short loc_1800533F0
0x1800533dd  mov     eax, 0C0000059h
0x1800533e2  jmp     short loc_1800533F0
0x1800533e4  mov     eax, 0C000000Dh
0x1800533e9  jmp     short loc_1800533F0
0x1800533eb  mov     eax, 0C0000077h
0x1800533f0  mov     rbx, [rsp+48h+arg_8]
0x1800533f5  mov     rbp, [rsp+48h+arg_10]
0x1800533fa  add     rsp, 30h
0x1800533fe  pop     r14
0x180053400  pop     rdi
0x180053401  pop     rsi
0x180053402  retn
```
