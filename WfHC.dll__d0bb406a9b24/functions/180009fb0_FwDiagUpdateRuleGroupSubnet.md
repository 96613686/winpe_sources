# FwDiagUpdateRuleGroupSubnet

- ea: `0x180009fb0`
- end: `0x18000a1cc`
- name: `FwDiagUpdateRuleGroupSubnet`
- size: `540`
- prototype: `__int64 __fastcall(PCNZWCH lpString2, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800099d0`

## callees

- `0x180009a50`
- `0x180009fb0`
- `0x18000a1e0`
- `0x18000c5b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000a129`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000a129`
- `FirewallAPI!FWOpenPolicyStore` at `0x18000a03e`
- `FirewallAPI!FWOpenPolicyStore` at `0x18000a03e`
- `FirewallAPI!FWQueryFirewallRules` at `0x18000a0b0`
- `FirewallAPI!FWQueryFirewallRules` at `0x18000a0b0`
- `FirewallAPI!FWFreeFirewallRules` at `0x18000a182`
- `FirewallAPI!FWFreeFirewallRules` at `0x18000a182`
- `FirewallAPI!FWClosePolicyStore` at `0x18000a192`
- `FirewallAPI!FWClosePolicyStore` at `0x18000a192`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18000a0fe`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18000a0fe`

## pseudocode

```c
__int64 __fastcall FwDiagUpdateRuleGroupSubnet(PCNZWCH lpString2, int a2, __int64 a3)
{
  unsigned int updated; // edi
  __int128 *v7; // rbx
  const WCHAR *v8; // rcx
  int v9; // r8d
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  __int128 *v13; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+48h] [rbp-B8h] BYREF
  PCNZWCH v15; // [rsp+58h] [rbp-A8h]
  __int128 v16; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+70h] [rbp-90h]
  __int128 v18; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszOutBuf[1024]; // [rsp+90h] [rbp-70h] BYREF

  v15 = 0;
  v17 = 0;
  v12 = 0;
  v13 = 0;
  v11 = 0;
  v14 = 0;
  v18 = 0;
  v16 = 0;
  updated = FWOpenPolicyStore(545, 0, 2, 2, 0, &v12);
  if ( updated )
    goto LABEL_12;
  *((_QWORD *)&v18 + 1) = &v14;
  *(_QWORD *)&v14 = 8;
  *((_QWORD *)&v16 + 1) = &v18;
  v15 = lpString2;
  DWORD2(v14) = 5;
  LODWORD(v18) = 1;
  DWORD1(v16) = 1;
  LODWORD(v17) = 0x10000;
  LOWORD(v16) = 545;
  updated = FWQueryFirewallRules(v12, &v16, 0, &v11, &v13);
  if ( updated )
  {
LABEL_12:
    v7 = v13;
    goto LABEL_13;
  }
  v7 = v13;
  if ( v11 && v13 )
  {
    do
    {
      v8 = (const WCHAR *)*((_QWORD *)v7 + 39);
      if ( v8 )
      {
        pszOutBuf[0] = 0;
        if ( SHLoadIndirectString(v8, pszOutBuf, 0x400u, 0) >= 0
          && CompareStringW(0x7Fu, 1u, pszOutBuf, -1, lpString2, -1) == 2 )
        {
          v9 = *((_DWORD *)v7 + 10) & ~a2;
          if ( v9 )
          {
            updated = FwDiagSplitRule(v12, v7, v9);
            if ( updated )
              break;
          }
          updated = FwDiagUpdateRuleSubnet(v12, v7, a3);
          if ( updated )
            break;
        }
      }
      v7 = *(__int128 **)v7;
    }
    while ( v7 );
    goto LABEL_12;
  }
  updated = 87;
LABEL_13:
  if ( v7 )
    FWFreeFirewallRules(v7);
  if ( v12 )
    FWClosePolicyStore();
  return updated;
}

```

## disassembly

```asm
0x180009fb0  mov     [rsp-8+arg_10], rbx
0x180009fb5  mov     [rsp-8+arg_18], rsi
0x180009fba  push    rbp
0x180009fbb  push    rdi
0x180009fbc  push    r12
0x180009fbe  push    r14
0x180009fc0  push    r15
0x180009fc2  lea     rbp, [rsp-7A0h]
0x180009fca  sub     rsp, 8A0h
0x180009fd1  mov     rax, cs:__security_cookie
0x180009fd8  xor     rax, rsp
0x180009fdb  mov     [rbp+7C0h+var_30], rax
0x180009fe2  xor     eax, eax
0x180009fe4  xor     r12d, r12d
0x180009fe7  xorps   xmm0, xmm0
0x180009fea  mov     [rsp+8C0h+var_868], rax
0x180009fef  mov     [rsp+8C0h+var_850], rax
0x180009ff4  mov     r9d, 2
0x180009ffa  lea     rax, [rsp+8C0h+var_888]
0x180009fff  mov     [rsp+8C0h+var_888], r12
0x18000a004  mov     r15, r8
0x18000a007  mov     qword ptr [rsp+8C0h+cchCount2], rax
0x18000a00c  mov     esi, edx
0x18000a00e  mov     dword ptr [rsp+8C0h+lpString2], r12d
0x18000a013  mov     r14, rcx
0x18000a016  mov     [rsp+8C0h+var_880], r12
0x18000a01b  xorps   xmm1, xmm1
0x18000a01e  mov     [rsp+8C0h+var_890], r12d
0x18000a023  mov     ebx, 221h
0x18000a028  xor     edx, edx
0x18000a02a  mov     ecx, ebx
0x18000a02c  mov     r8d, r9d
0x18000a02f  movups  [rsp+8C0h+var_878], xmm0
0x18000a034  movups  [rsp+8C0h+var_848], xmm0
0x18000a039  movups  [rsp+8C0h+var_860], xmm1
0x18000a03e  call    cs:__imp_FWOpenPolicyStore
0x18000a044  mov     edi, eax
0x18000a046  test    eax, eax
0x18000a048  jnz     loc_18000A175
0x18000a04e  mov     rcx, [rsp+8C0h+var_888]
0x18000a053  lea     rax, [rsp+8C0h+var_878]
0x18000a058  mov     qword ptr [rbp+7C0h+var_848+8], rax
0x18000a05c  lea     r9, [rsp+8C0h+var_890]
0x18000a061  lea     rax, [rsp+8C0h+var_848]
0x18000a066  mov     qword ptr [rsp+8C0h+var_878], 8
0x18000a06f  mov     qword ptr [rsp+8C0h+var_860+8], rax
0x18000a074  lea     rdx, [rsp+8C0h+var_860]
0x18000a079  lea     rax, [rsp+8C0h+var_880]
0x18000a07e  mov     [rsp+8C0h+var_868], r14
0x18000a083  xor     r8d, r8d
0x18000a086  mov     [rsp+8C0h+lpString2], rax
0x18000a08b  mov     dword ptr [rsp+8C0h+var_878+8], 5
0x18000a093  mov     dword ptr [rsp+8C0h+var_848], 1
0x18000a09b  mov     dword ptr [rsp+8C0h+var_860+4], 1
0x18000a0a3  mov     dword ptr [rsp+8C0h+var_850], 10000h
0x18000a0ab  mov     word ptr [rsp+8C0h+var_860], bx
0x18000a0b0  call    cs:__imp_FWQueryFirewallRules
0x18000a0b6  mov     edi, eax
0x18000a0b8  test    eax, eax
0x18000a0ba  jnz     loc_18000A175
0x18000a0c0  mov     rbx, [rsp+8C0h+var_880]
0x18000a0c5  cmp     [rsp+8C0h+var_890], r12d
0x18000a0ca  jz      loc_18000A1C5
0x18000a0d0  test    rbx, rbx
0x18000a0d3  jz      loc_18000A1C5
0x18000a0d9  nop     dword ptr [rax+00000000h]
0x18000a0e0  mov     rcx, [rbx+138h]; pszSource
0x18000a0e7  test    rcx, rcx
0x18000a0ea  jz      short loc_18000A169
0x18000a0ec  xor     r9d, r9d; ppvReserved
0x18000a0ef  mov     [rbp+7C0h+pszOutBuf], r12w
0x18000a0f4  mov     r8d, 400h; cchOutBuf
0x18000a0fa  lea     rdx, [rbp+7C0h+pszOutBuf]; pszOutBuf
0x18000a0fe  call    cs:__imp_SHLoadIndirectString
0x18000a104  test    eax, eax
0x18000a106  js      short loc_18000A169
0x18000a108  mov     [rsp+8C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000a110  lea     r8, [rbp+7C0h+pszOutBuf]; lpString1
0x18000a114  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000a11a  mov     [rsp+8C0h+lpString2], r14; lpString2
0x18000a11f  mov     edx, 1; dwCmpFlags
0x18000a124  mov     ecx, 7Fh; Locale
0x18000a129  call    cs:__imp_CompareStringW
0x18000a12f  cmp     eax, 2
0x18000a132  jnz     short loc_18000A169
0x18000a134  mov     r8d, esi
0x18000a137  not     r8d
0x18000a13a  and     r8d, [rbx+28h]
0x18000a13e  jz      short loc_18000A153
0x18000a140  mov     rcx, [rsp+8C0h+var_888]
0x18000a145  mov     rdx, rbx
0x18000a148  call    FwDiagSplitRule
0x18000a14d  mov     edi, eax
0x18000a14f  test    eax, eax
0x18000a151  jnz     short loc_18000A175
0x18000a153  mov     rcx, [rsp+8C0h+var_888]
0x18000a158  mov     r8, r15
0x18000a15b  mov     rdx, rbx
0x18000a15e  call    FwDiagUpdateRuleSubnet
0x18000a163  mov     edi, eax
0x18000a165  test    eax, eax
0x18000a167  jnz     short loc_18000A175
0x18000a169  mov     rbx, [rbx]
0x18000a16c  test    rbx, rbx
0x18000a16f  jnz     loc_18000A0E0
0x18000a175  mov     rbx, [rsp+8C0h+var_880]
0x18000a17a  test    rbx, rbx
0x18000a17d  jz      short loc_18000A188
0x18000a17f  mov     rcx, rbx
0x18000a182  call    cs:__imp_FWFreeFirewallRules
0x18000a188  mov     rcx, [rsp+8C0h+var_888]
0x18000a18d  test    rcx, rcx
0x18000a190  jz      short loc_18000A198
0x18000a192  call    cs:__imp_FWClosePolicyStore
0x18000a198  mov     eax, edi
0x18000a19a  mov     rcx, [rbp+7C0h+var_30]
0x18000a1a1  xor     rcx, rsp; StackCookie
0x18000a1a4  call    __security_check_cookie
0x18000a1a9  lea     r11, [rsp+8C0h+var_20]
0x18000a1b1  mov     rbx, [r11+40h]
0x18000a1b5  mov     rsi, [r11+48h]
0x18000a1b9  mov     rsp, r11
0x18000a1bc  pop     r15
0x18000a1be  pop     r14
0x18000a1c0  pop     r12
0x18000a1c2  pop     rdi
0x18000a1c3  pop     rbp
0x18000a1c4  retn
0x18000a1c5  mov     edi, 57h ; 'W'
0x18000a1ca  jmp     short loc_18000A17A
```
