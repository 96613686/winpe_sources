# FwDiagUpdateProgramExceptionSubnet

- ea: `0x180009e10`
- end: `0x180009fa6`
- name: `FwDiagUpdateProgramExceptionSubnet`
- size: `406`
- prototype: `__int64 __fastcall(LPCWSTR lpString2, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180009940`

## callees

- `0x180009a50`
- `0x180009e10`
- `0x18000a1e0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009f20`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009f20`
- `FirewallAPI!FWOpenPolicyStore` at `0x180009e85`
- `FirewallAPI!FWOpenPolicyStore` at `0x180009e85`
- `FirewallAPI!FWQueryFirewallRules` at `0x180009eed`
- `FirewallAPI!FWQueryFirewallRules` at `0x180009eed`
- `FirewallAPI!FWFreeFirewallRules` at `0x180009f74`
- `FirewallAPI!FWFreeFirewallRules` at `0x180009f74`
- `FirewallAPI!FWClosePolicyStore` at `0x180009f83`
- `FirewallAPI!FWClosePolicyStore` at `0x180009f83`

## pseudocode

```c
__int64 __fastcall FwDiagUpdateProgramExceptionSubnet(LPCWSTR lpString2, int a2, int a3, __int64 a4)
{
  int v7; // r14d
  unsigned int updated; // edi
  __int64 *v9; // rbx
  int v10; // r8d
  __int64 v12; // [rsp+30h] [rbp-39h] BYREF
  __int64 *v13; // [rsp+38h] [rbp-31h] BYREF
  __int128 v14; // [rsp+40h] [rbp-29h] BYREF
  __int128 v15; // [rsp+50h] [rbp-19h] BYREF
  LPCWSTR v16; // [rsp+60h] [rbp-9h]
  __int128 v17; // [rsp+68h] [rbp-1h] BYREF
  __int64 v18; // [rsp+78h] [rbp+Fh]
  int v19; // [rsp+E0h] [rbp+77h] BYREF

  v16 = 0;
  v18 = 0;
  v12 = 0;
  v13 = 0;
  v19 = 0;
  v7 = 2 - (a3 != 0);
  v15 = 0;
  v14 = 0;
  v17 = 0;
  updated = FWOpenPolicyStore(545, 0, 2, 2, 0, &v12);
  if ( updated )
    goto LABEL_11;
  *((_QWORD *)&v14 + 1) = &v15;
  *(_QWORD *)&v15 = 4;
  *((_QWORD *)&v17 + 1) = &v14;
  v16 = lpString2;
  DWORD2(v15) = 5;
  LODWORD(v14) = 1;
  DWORD1(v17) = 1;
  LODWORD(v18) = 0x10000;
  LOWORD(v17) = 545;
  updated = FWQueryFirewallRules(v12, &v17, 4, &v19, &v13);
  if ( updated )
  {
LABEL_11:
    v9 = v13;
    goto LABEL_12;
  }
  v9 = v13;
  if ( v19 && v13 )
  {
    do
    {
      if ( *((_DWORD *)v9 + 11) == v7 && !lstrcmpiW((LPCWSTR)v9[34], lpString2) )
      {
        *((_DWORD *)v9 + 10) |= a2;
        v10 = v9[5] & ~a2;
        if ( v10 )
        {
          updated = FwDiagSplitRule(v12, (__int128 *)v9, v10);
          if ( updated )
            break;
        }
        updated = FwDiagUpdateRuleSubnet(v12, v9, a4);
        if ( updated )
          break;
      }
      v9 = (__int64 *)*v9;
    }
    while ( v9 );
    goto LABEL_11;
  }
  updated = 87;
LABEL_12:
  if ( v9 )
    FWFreeFirewallRules(v9);
  if ( v12 )
    FWClosePolicyStore();
  return updated;
}

```

## disassembly

```asm
0x180009e10  push    rbp
0x180009e12  push    rbx
0x180009e13  push    rsi
0x180009e14  push    rdi
0x180009e15  push    r12
0x180009e17  push    r13
0x180009e19  push    r14
0x180009e1b  push    r15
0x180009e1d  lea     rbp, [rsp-1Fh]
0x180009e22  sub     rsp, 88h
0x180009e29  xor     ebx, ebx
0x180009e2b  xor     eax, eax
0x180009e2d  neg     r8d
0x180009e30  mov     [rbp+57h+var_60], rax
0x180009e34  xorps   xmm0, xmm0
0x180009e37  mov     [rbp+57h+var_48], rax
0x180009e3b  sbb     r14d, r14d
0x180009e3e  mov     [rbp+57h+var_90], rbx
0x180009e42  mov     r12, r9
0x180009e45  mov     [rbp+57h+var_88], rbx
0x180009e49  lea     rax, [rbp+57h+var_90]
0x180009e4d  mov     [rbp+57h+arg_10], ebx
0x180009e50  mov     r9d, 2
0x180009e56  mov     [rsp+0C0h+var_98], rax
0x180009e5b  mov     esi, edx
0x180009e5d  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180009e61  mov     r15, rcx
0x180009e64  xorps   xmm1, xmm1
0x180009e67  mov     r13d, 221h
0x180009e6d  xor     edx, edx
0x180009e6f  mov     ecx, r13d
0x180009e72  mov     r8d, r9d
0x180009e75  add     r14d, 2
0x180009e79  movups  [rbp+57h+var_70], xmm0
0x180009e7d  movups  [rbp+57h+var_80], xmm0
0x180009e81  movups  [rbp+57h+var_58], xmm1
0x180009e85  call    cs:__imp_FWOpenPolicyStore
0x180009e8b  mov     edi, eax
0x180009e8d  test    eax, eax
0x180009e8f  jnz     loc_180009F68
0x180009e95  mov     rcx, [rbp+57h+var_90]
0x180009e99  lea     rax, [rbp+57h+var_70]
0x180009e9d  mov     qword ptr [rbp+57h+var_80+8], rax
0x180009ea1  lea     r9, [rbp+57h+arg_10]
0x180009ea5  lea     rax, [rbp+57h+var_80]
0x180009ea9  mov     qword ptr [rbp+57h+var_70], 4
0x180009eb1  mov     qword ptr [rbp+57h+var_58+8], rax
0x180009eb5  lea     rdx, [rbp+57h+var_58]
0x180009eb9  lea     rax, [rbp+57h+var_88]
0x180009ebd  mov     [rbp+57h+var_60], r15
0x180009ec1  mov     r8d, 4
0x180009ec7  mov     [rsp+0C0h+var_A0], rax
0x180009ecc  mov     dword ptr [rbp+57h+var_70+8], 5
0x180009ed3  mov     dword ptr [rbp+57h+var_80], 1
0x180009eda  mov     dword ptr [rbp+57h+var_58+4], 1
0x180009ee1  mov     dword ptr [rbp+57h+var_48], 10000h
0x180009ee8  mov     word ptr [rbp+57h+var_58], r13w
0x180009eed  call    cs:__imp_FWQueryFirewallRules
0x180009ef3  mov     edi, eax
0x180009ef5  test    eax, eax
0x180009ef7  jnz     short loc_180009F68
0x180009ef9  mov     rbx, [rbp+57h+var_88]
0x180009efd  cmp     [rbp+57h+arg_10], eax
0x180009f00  jz      loc_180009F9F
0x180009f06  test    rbx, rbx
0x180009f09  jz      loc_180009F9F
0x180009f0f  nop
0x180009f10  cmp     [rbx+2Ch], r14d
0x180009f14  jnz     short loc_180009F60
0x180009f16  mov     rcx, [rbx+110h]; lpString1
0x180009f1d  mov     rdx, r15; lpString2
0x180009f20  call    cs:__imp_lstrcmpiW
0x180009f26  test    eax, eax
0x180009f28  jnz     short loc_180009F60
0x180009f2a  or      [rbx+28h], esi
0x180009f2d  mov     r8d, esi
0x180009f30  not     r8d
0x180009f33  and     r8d, [rbx+28h]
0x180009f37  jz      short loc_180009F4B
0x180009f39  mov     rcx, [rbp+57h+var_90]
0x180009f3d  mov     rdx, rbx
0x180009f40  call    FwDiagSplitRule
0x180009f45  mov     edi, eax
0x180009f47  test    eax, eax
0x180009f49  jnz     short loc_180009F68
0x180009f4b  mov     rcx, [rbp+57h+var_90]
0x180009f4f  mov     r8, r12
0x180009f52  mov     rdx, rbx
0x180009f55  call    FwDiagUpdateRuleSubnet
0x180009f5a  mov     edi, eax
0x180009f5c  test    eax, eax
0x180009f5e  jnz     short loc_180009F68
0x180009f60  mov     rbx, [rbx]
0x180009f63  test    rbx, rbx
0x180009f66  jnz     short loc_180009F10
0x180009f68  mov     rbx, [rbp+57h+var_88]
0x180009f6c  test    rbx, rbx
0x180009f6f  jz      short loc_180009F7A
0x180009f71  mov     rcx, rbx
0x180009f74  call    cs:__imp_FWFreeFirewallRules
0x180009f7a  mov     rcx, [rbp+57h+var_90]
0x180009f7e  test    rcx, rcx
0x180009f81  jz      short loc_180009F89
0x180009f83  call    cs:__imp_FWClosePolicyStore
0x180009f89  mov     eax, edi
0x180009f8b  add     rsp, 88h
0x180009f92  pop     r15
0x180009f94  pop     r14
0x180009f96  pop     r13
0x180009f98  pop     r12
0x180009f9a  pop     rdi
0x180009f9b  pop     rsi
0x180009f9c  pop     rbx
0x180009f9d  pop     rbp
0x180009f9e  retn
0x180009f9f  mov     edi, 57h ; 'W'
0x180009fa4  jmp     short loc_180009F6C
```
