# FwDiagUpdatePortExceptionSubnet

- ea: `0x180009c20`
- end: `0x180009e0a`
- name: `FwDiagUpdatePortExceptionSubnet`
- size: `490`
- prototype: `__int64 __fastcall(__int16, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800098b0`

## callees

- `0x180009a50`
- `0x180009c20`
- `0x18000a1e0`

## import_xrefs

- `FirewallAPI!FWOpenPolicyStore` at `0x180009c9d`
- `FirewallAPI!FWOpenPolicyStore` at `0x180009c9d`
- `FirewallAPI!FWQueryFirewallRules` at `0x180009d0a`
- `FirewallAPI!FWQueryFirewallRules` at `0x180009d0a`
- `FirewallAPI!FWFreeFirewallRules` at `0x180009dd8`
- `FirewallAPI!FWFreeFirewallRules` at `0x180009dd8`
- `FirewallAPI!FWClosePolicyStore` at `0x180009de7`
- `FirewallAPI!FWClosePolicyStore` at `0x180009de7`

## pseudocode

```c
__int64 __fastcall FwDiagUpdatePortExceptionSubnet(__int16 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  int v8; // r15d
  unsigned int updated; // edi
  __int64 *v10; // rbx
  __int64 v11; // r12
  __int64 v12; // rax
  unsigned int v13; // r8d
  __int16 *v14; // rax
  int v15; // ecx
  __int16 v16; // dx
  int v17; // r8d
  __int64 v19; // [rsp+30h] [rbp-41h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-39h] BYREF
  __int128 v21; // [rsp+40h] [rbp-31h] BYREF
  __int128 v22; // [rsp+50h] [rbp-21h] BYREF
  __int64 v23; // [rsp+60h] [rbp-11h]
  __int128 v24; // [rsp+68h] [rbp-9h] BYREF
  __int64 v25; // [rsp+78h] [rbp+7h]
  int v26; // [rsp+D8h] [rbp+67h] BYREF

  v23 = 0;
  v25 = 0;
  v19 = 0;
  v20 = 0;
  v26 = 0;
  v8 = 2 - (a4 != 0);
  v22 = 0;
  v21 = 0;
  v24 = 0;
  updated = FWOpenPolicyStore(545, 0, 2, 2, 0, &v19);
  if ( updated )
    goto LABEL_19;
  DWORD2(v22) = 2;
  LOWORD(v23) = a1;
  *((_QWORD *)&v21 + 1) = &v22;
  LODWORD(v21) = 1;
  *(_QWORD *)&v22 = 7 - (unsigned int)(a4 != 0);
  *((_QWORD *)&v24 + 1) = &v21;
  DWORD1(v24) = 1;
  LODWORD(v25) = 0x10000;
  LOWORD(v24) = 545;
  updated = FWQueryFirewallRules(v19, &v24, 0, &v26, &v20);
  if ( updated )
  {
LABEL_19:
    v10 = v20;
    goto LABEL_20;
  }
  v10 = v20;
  if ( v26 && v20 )
  {
    v11 = a5;
    while ( 1 )
    {
      if ( *((_DWORD *)v10 + 11) == v8 )
      {
        v12 = 8;
        if ( !a4 )
          v12 = 11;
        v13 = v10[v12];
        if ( v13 )
        {
          v14 = (__int16 *)v10[v12 + 1];
          v15 = 0;
          v16 = *v14;
          while ( v16 != v14[1] || v16 != a1 )
          {
            if ( ++v15 >= v13 )
              goto LABEL_18;
          }
          *((_DWORD *)v10 + 10) |= a3;
          v17 = v10[5] & ~a3;
          if ( v17 )
          {
            updated = FwDiagSplitRule(v19, (__int128 *)v10, v17);
            if ( updated )
              goto LABEL_19;
          }
          updated = FwDiagUpdateRuleSubnet(v19, v10, v11);
          if ( updated )
            goto LABEL_19;
        }
      }
LABEL_18:
      v10 = (__int64 *)*v10;
      if ( !v10 )
        goto LABEL_19;
    }
  }
  updated = 87;
LABEL_20:
  if ( v10 )
    FWFreeFirewallRules(v10);
  if ( v19 )
    FWClosePolicyStore();
  return updated;
}

```

## disassembly

```asm
0x180009c20  mov     word ptr [rsp-8+arg_8], dx
0x180009c25  push    rbp
0x180009c26  push    rbx
0x180009c27  push    rsi
0x180009c28  push    rdi
0x180009c29  push    r12
0x180009c2b  push    r13
0x180009c2d  push    r14
0x180009c2f  push    r15
0x180009c31  lea     rbp, [rsp-17h]
0x180009c36  sub     rsp, 88h
0x180009c3d  xor     eax, eax
0x180009c3f  xor     r12d, r12d
0x180009c42  mov     [rbp+4Fh+var_60], rax
0x180009c46  xorps   xmm0, xmm0
0x180009c49  mov     [rbp+4Fh+var_48], rax
0x180009c4d  mov     r13d, r9d
0x180009c50  mov     eax, r9d
0x180009c53  mov     [rbp+4Fh+var_90], r12
0x180009c57  neg     eax
0x180009c59  mov     [rbp+4Fh+var_88], r12
0x180009c5d  lea     rax, [rbp+4Fh+var_90]
0x180009c61  mov     [rbp+4Fh+arg_8], r12d
0x180009c65  sbb     r15d, r15d
0x180009c68  mov     [rsp+0C0h+var_98], rax
0x180009c6d  mov     r9d, 2
0x180009c73  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x180009c78  mov     r14d, r8d
0x180009c7b  movzx   esi, cx
0x180009c7e  xorps   xmm1, xmm1
0x180009c81  mov     ebx, 221h
0x180009c86  xor     edx, edx
0x180009c88  mov     ecx, ebx
0x180009c8a  mov     r8d, r9d
0x180009c8d  add     r15d, 2
0x180009c91  movups  [rbp+4Fh+var_70], xmm0
0x180009c95  movups  [rbp+4Fh+var_80], xmm0
0x180009c99  movups  [rbp+4Fh+var_58], xmm1
0x180009c9d  call    cs:__imp_FWOpenPolicyStore
0x180009ca3  mov     edi, eax
0x180009ca5  test    eax, eax
0x180009ca7  jnz     loc_180009DCC
0x180009cad  mov     eax, r13d
0x180009cb0  mov     dword ptr [rbp+4Fh+var_70+4], r12d
0x180009cb4  neg     eax
0x180009cb6  mov     dword ptr [rbp+4Fh+var_70+8], 2
0x180009cbd  lea     rax, [rbp+4Fh+var_70]
0x180009cc1  mov     word ptr [rbp+4Fh+var_60], si
0x180009cc5  sbb     ecx, ecx
0x180009cc7  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x180009ccb  add     ecx, 7
0x180009cce  mov     dword ptr [rbp+4Fh+var_80], 1
0x180009cd5  lea     rax, [rbp+4Fh+var_80]
0x180009cd9  mov     dword ptr [rbp+4Fh+var_70], ecx
0x180009cdc  mov     rcx, [rbp+4Fh+var_90]
0x180009ce0  lea     r9, [rbp+4Fh+arg_8]
0x180009ce4  mov     qword ptr [rbp+4Fh+var_58+8], rax
0x180009ce8  lea     rdx, [rbp+4Fh+var_58]
0x180009cec  lea     rax, [rbp+4Fh+var_88]
0x180009cf0  mov     dword ptr [rbp+4Fh+var_58+4], 1
0x180009cf7  xor     r8d, r8d
0x180009cfa  mov     [rsp+0C0h+var_A0], rax
0x180009cff  mov     dword ptr [rbp+4Fh+var_48], 10000h
0x180009d06  mov     word ptr [rbp+4Fh+var_58], bx
0x180009d0a  call    cs:__imp_FWQueryFirewallRules
0x180009d10  mov     edi, eax
0x180009d12  test    eax, eax
0x180009d14  jnz     loc_180009DCC
0x180009d1a  mov     rbx, [rbp+4Fh+var_88]
0x180009d1e  cmp     [rbp+4Fh+arg_8], r12d
0x180009d22  jz      loc_180009E03
0x180009d28  test    rbx, rbx
0x180009d2b  jz      loc_180009E03
0x180009d31  mov     r12, [rbp+4Fh+arg_20]
0x180009d35  mov     ecx, 58h ; 'X'
0x180009d3a  nop     word ptr [rax+rax+00h]
0x180009d40  cmp     [rbx+2Ch], r15d
0x180009d44  jnz     short loc_180009DC0
0x180009d46  test    r13d, r13d
0x180009d49  mov     eax, 40h ; '@'
0x180009d4e  cmovz   rax, rcx
0x180009d52  mov     r8d, [rax+rbx]
0x180009d56  test    r8d, r8d
0x180009d59  jz      short loc_180009DC0
0x180009d5b  mov     rax, [rax+rbx+8]
0x180009d60  xor     ecx, ecx
0x180009d62  movzx   r9d, word ptr [rax+2]
0x180009d67  movzx   edx, word ptr [rax]
0x180009d6a  nop     word ptr [rax+rax+00h]
0x180009d70  cmp     dx, r9w
0x180009d74  jnz     short loc_180009D7B
0x180009d76  cmp     dx, si
0x180009d79  jz      short loc_180009D84
0x180009d7b  inc     ecx
0x180009d7d  cmp     ecx, r8d
0x180009d80  jb      short loc_180009D70
0x180009d82  jmp     short loc_180009DBB
0x180009d84  or      [rbx+28h], r14d
0x180009d88  mov     r8d, r14d
0x180009d8b  not     r8d
0x180009d8e  and     r8d, [rbx+28h]
0x180009d92  jz      short loc_180009DA6
0x180009d94  mov     rcx, [rbp+4Fh+var_90]
0x180009d98  mov     rdx, rbx
0x180009d9b  call    FwDiagSplitRule
0x180009da0  mov     edi, eax
0x180009da2  test    eax, eax
0x180009da4  jnz     short loc_180009DCC
0x180009da6  mov     rcx, [rbp+4Fh+var_90]
0x180009daa  mov     r8, r12
0x180009dad  mov     rdx, rbx
0x180009db0  call    FwDiagUpdateRuleSubnet
0x180009db5  mov     edi, eax
0x180009db7  test    eax, eax
0x180009db9  jnz     short loc_180009DCC
0x180009dbb  mov     ecx, 58h ; 'X'
0x180009dc0  mov     rbx, [rbx]
0x180009dc3  test    rbx, rbx
0x180009dc6  jnz     loc_180009D40
0x180009dcc  mov     rbx, [rbp+4Fh+var_88]
0x180009dd0  test    rbx, rbx
0x180009dd3  jz      short loc_180009DDE
0x180009dd5  mov     rcx, rbx
0x180009dd8  call    cs:__imp_FWFreeFirewallRules
0x180009dde  mov     rcx, [rbp+4Fh+var_90]
0x180009de2  test    rcx, rcx
0x180009de5  jz      short loc_180009DED
0x180009de7  call    cs:__imp_FWClosePolicyStore
0x180009ded  mov     eax, edi
0x180009def  add     rsp, 88h
0x180009df6  pop     r15
0x180009df8  pop     r14
0x180009dfa  pop     r13
0x180009dfc  pop     r12
0x180009dfe  pop     rdi
0x180009dff  pop     rsi
0x180009e00  pop     rbx
0x180009e01  pop     rbp
0x180009e02  retn
0x180009e03  mov     edi, 57h ; 'W'
0x180009e08  jmp     short loc_180009DD0
```
