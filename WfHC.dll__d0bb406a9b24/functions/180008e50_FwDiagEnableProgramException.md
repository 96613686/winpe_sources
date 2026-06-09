# FwDiagEnableProgramException

- ea: `0x180008e50`
- end: `0x18000908c`
- name: `FwDiagEnableProgramException`
- size: `572`
- prototype: `__int64 __fastcall(LPCWSTR lpString2, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009620`

## callees

- `0x180008e50`
- `0x180009a50`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008f83`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008fe3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008f83`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008fe3`
- `FirewallAPI!FWOpenPolicyStore` at `0x180008ec0`
- `FirewallAPI!FWOpenPolicyStore` at `0x180008ec0`
- `FirewallAPI!FWSetFirewallRule` at `0x180009036`
- `FirewallAPI!FWSetFirewallRule` at `0x180009036`
- `FirewallAPI!FWQueryFirewallRules` at `0x180008f27`
- `FirewallAPI!FWQueryFirewallRules` at `0x180008f27`
- `FirewallAPI!FWFreeFirewallRules` at `0x18000905a`
- `FirewallAPI!FWFreeFirewallRules` at `0x18000905a`
- `FirewallAPI!FWClosePolicyStore` at `0x180009069`
- `FirewallAPI!FWClosePolicyStore` at `0x180009069`

## pseudocode

```c
__int64 __fastcall FwDiagEnableProgramException(LPCWSTR lpString2, int a2, int a3, int a4)
{
  unsigned int v8; // edi
  __int64 *v9; // rbx
  __int64 *v10; // rbx
  bool v11; // cf
  int v12; // r13d
  int v13; // r15d
  int v14; // eax
  int v15; // eax
  __int64 *v17; // [rsp+30h] [rbp-49h] BYREF
  int v18; // [rsp+38h] [rbp-41h] BYREF
  int v19; // [rsp+3Ch] [rbp-3Dh]
  __int64 v20; // [rsp+40h] [rbp-39h] BYREF
  __int128 v21; // [rsp+48h] [rbp-31h] BYREF
  LPCWSTR v22; // [rsp+58h] [rbp-21h]
  __int128 v23; // [rsp+60h] [rbp-19h] BYREF
  __int64 v24; // [rsp+70h] [rbp-9h]
  __int128 v25; // [rsp+78h] [rbp-1h] BYREF

  v22 = 0;
  v24 = 0;
  v20 = 0;
  v17 = 0;
  v18 = 0;
  v21 = 0;
  v25 = 0;
  v23 = 0;
  v8 = FWOpenPolicyStore(545, 0, 2, 2, 0, &v20);
  if ( v8 )
    goto LABEL_30;
  *((_QWORD *)&v25 + 1) = &v21;
  *(_QWORD *)&v21 = 4;
  *((_QWORD *)&v23 + 1) = &v25;
  v22 = lpString2;
  DWORD2(v21) = 5;
  LODWORD(v25) = 1;
  DWORD1(v23) = 1;
  LODWORD(v24) = 0x10000;
  LOWORD(v23) = 545;
  v8 = FWQueryFirewallRules(v20, &v23, 4, &v18, &v17);
  if ( v8 )
  {
LABEL_30:
    v9 = v17;
    goto LABEL_31;
  }
  v9 = v17;
  if ( !v18 || !v17 )
  {
    v8 = 87;
LABEL_31:
    if ( v9 )
      FWFreeFirewallRules(v9);
    goto LABEL_33;
  }
  v19 = 0;
  while ( 1 )
  {
    if ( *((_DWORD *)v9 + 11) != 2 - (a3 != 0) )
      goto LABEL_13;
    if ( *((_DWORD *)v9 + 72) == 3 )
      break;
    if ( !a4 )
      goto LABEL_11;
LABEL_13:
    v9 = (__int64 *)*v9;
    if ( !v9 )
      goto LABEL_16;
  }
  if ( !a4 )
    goto LABEL_13;
LABEL_11:
  if ( lstrcmpiW((LPCWSTR)v9[34], lpString2) || (a2 & (_DWORD)v9[5]) == 0 )
    goto LABEL_13;
  v19 = 1;
LABEL_16:
  v10 = v17;
  if ( v17 )
  {
    v11 = a3 != 0;
    v12 = v19;
    v13 = 2 - v11;
    while ( 1 )
    {
      if ( *((_DWORD *)v10 + 11) == v13 )
      {
        if ( *((_DWORD *)v10 + 72) == 3 )
        {
          if ( !a4 )
            goto LABEL_29;
        }
        else if ( a4 )
        {
          goto LABEL_29;
        }
        if ( !lstrcmpiW((LPCWSTR)v10[34], lpString2) )
        {
          v14 = *((_DWORD *)v10 + 10);
          if ( (v14 & a2) != 0 || !v12 )
          {
            v15 = a2 | v14;
            *((_DWORD *)v10 + 10) = v15;
            if ( (v15 & ~a2) != 0 )
            {
              v8 = FwDiagSplitRule(v20, v10);
              if ( v8 )
                goto LABEL_30;
            }
            *((_WORD *)v10 + 146) |= 1u;
            *((_DWORD *)v10 + 72) = 3;
            v8 = FWSetFirewallRule(v20, v10);
            if ( v8 )
              goto LABEL_30;
          }
        }
      }
LABEL_29:
      v10 = (__int64 *)*v10;
      if ( !v10 )
        goto LABEL_30;
    }
  }
LABEL_33:
  if ( v20 )
    FWClosePolicyStore();
  return v8;
}

```

## disassembly

```asm
0x180008e50  push    rbp
0x180008e52  push    rbx
0x180008e53  push    rsi
0x180008e54  push    rdi
0x180008e55  push    r12
0x180008e57  push    r13
0x180008e59  push    r14
0x180008e5b  push    r15
0x180008e5d  lea     rbp, [rsp-1Fh]
0x180008e62  sub     rsp, 98h
0x180008e69  xor     eax, eax
0x180008e6b  xor     r15d, r15d
0x180008e6e  xorps   xmm0, xmm0
0x180008e71  mov     [rbp+57h+var_78], rax
0x180008e75  mov     [rbp+57h+var_60], rax
0x180008e79  mov     esi, r9d
0x180008e7c  lea     rax, [rbp+57h+var_90]
0x180008e80  mov     [rbp+57h+var_90], r15
0x180008e84  mov     r9d, 2
0x180008e8a  mov     [rsp+0D0h+var_A8], rax
0x180008e8f  mov     r13d, r8d
0x180008e92  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x180008e97  mov     r14d, edx
0x180008e9a  mov     [rbp+57h+var_A0], r15
0x180008e9e  mov     r12, rcx
0x180008ea1  mov     [rbp+57h+var_98], r15d
0x180008ea5  xorps   xmm1, xmm1
0x180008ea8  mov     ebx, 221h
0x180008ead  mov     ecx, ebx
0x180008eaf  xor     edx, edx
0x180008eb1  mov     r8d, r9d
0x180008eb4  movups  [rbp+57h+var_88], xmm0
0x180008eb8  movups  [rbp+57h+var_58], xmm0
0x180008ebc  movups  [rbp+57h+var_70], xmm1
0x180008ec0  call    cs:__imp_FWOpenPolicyStore
0x180008ec6  mov     edi, eax
0x180008ec8  test    eax, eax
0x180008eca  jnz     loc_18000904E
0x180008ed0  mov     rcx, [rbp+57h+var_90]
0x180008ed4  lea     rax, [rbp+57h+var_88]
0x180008ed8  mov     qword ptr [rbp+57h+var_58+8], rax
0x180008edc  lea     r9, [rbp+57h+var_98]
0x180008ee0  lea     rax, [rbp+57h+var_58]
0x180008ee4  mov     qword ptr [rbp+57h+var_88], 4
0x180008eec  mov     qword ptr [rbp+57h+var_70+8], rax
0x180008ef0  lea     rdx, [rbp+57h+var_70]
0x180008ef4  lea     rax, [rbp+57h+var_A0]
0x180008ef8  mov     [rbp+57h+var_78], r12
0x180008efc  mov     r8d, 4
0x180008f02  mov     [rsp+0D0h+var_B0], rax
0x180008f07  mov     dword ptr [rbp+57h+var_88+8], 5
0x180008f0e  mov     dword ptr [rbp+57h+var_58], 1
0x180008f15  mov     dword ptr [rbp+57h+var_70+4], 1
0x180008f1c  mov     dword ptr [rbp+57h+var_60], 10000h
0x180008f23  mov     word ptr [rbp+57h+var_70], bx
0x180008f27  call    cs:__imp_FWQueryFirewallRules
0x180008f2d  mov     edi, eax
0x180008f2f  test    eax, eax
0x180008f31  jnz     loc_18000904E
0x180008f37  mov     rbx, [rbp+57h+var_A0]
0x180008f3b  cmp     [rbp+57h+var_98], r15d
0x180008f3f  jz      loc_180009085
0x180008f45  test    rbx, rbx
0x180008f48  jz      loc_180009085
0x180008f4e  mov     [rbp+57h+var_94], r15d
0x180008f52  mov     eax, r13d
0x180008f55  neg     eax
0x180008f57  sbb     r15d, r15d
0x180008f5a  add     r15d, 2
0x180008f5e  xchg    ax, ax
0x180008f60  cmp     [rbx+2Ch], r15d
0x180008f64  jnz     short loc_180008F93
0x180008f66  cmp     dword ptr [rbx+120h], 3
0x180008f6d  jz      short loc_180008F75
0x180008f6f  test    esi, esi
0x180008f71  jz      short loc_180008F79
0x180008f73  jmp     short loc_180008F93
0x180008f75  test    esi, esi
0x180008f77  jz      short loc_180008F93
0x180008f79  mov     rcx, [rbx+110h]; lpString1
0x180008f80  mov     rdx, r12; lpString2
0x180008f83  call    cs:__imp_lstrcmpiW
0x180008f89  test    eax, eax
0x180008f8b  jnz     short loc_180008F93
0x180008f8d  test    [rbx+28h], r14d
0x180008f91  ja      short loc_180008F9D
0x180008f93  mov     rbx, [rbx]
0x180008f96  test    rbx, rbx
0x180008f99  jnz     short loc_180008F60
0x180008f9b  jmp     short loc_180008FA4
0x180008f9d  mov     [rbp+57h+var_94], 1
0x180008fa4  mov     rbx, [rbp+57h+var_A0]
0x180008fa8  test    rbx, rbx
0x180008fab  jz      loc_180009060
0x180008fb1  neg     r13d
0x180008fb4  mov     r13d, [rbp+57h+var_94]
0x180008fb8  sbb     r15d, r15d
0x180008fbb  add     r15d, 2
0x180008fbf  nop
0x180008fc0  cmp     [rbx+2Ch], r15d
0x180008fc4  jnz     short loc_180009042
0x180008fc6  cmp     dword ptr [rbx+120h], 3
0x180008fcd  jz      short loc_180008FD5
0x180008fcf  test    esi, esi
0x180008fd1  jz      short loc_180008FD9
0x180008fd3  jmp     short loc_180009042
0x180008fd5  test    esi, esi
0x180008fd7  jz      short loc_180009042
0x180008fd9  mov     rcx, [rbx+110h]; lpString1
0x180008fe0  mov     rdx, r12; lpString2
0x180008fe3  call    cs:__imp_lstrcmpiW
0x180008fe9  test    eax, eax
0x180008feb  jnz     short loc_180009042
0x180008fed  mov     eax, [rbx+28h]
0x180008ff0  test    r14d, eax
0x180008ff3  jnz     short loc_180008FFA
0x180008ff5  test    r13d, r13d
0x180008ff8  jnz     short loc_180009042
0x180008ffa  or      eax, r14d
0x180008ffd  mov     r8d, r14d
0x180009000  not     r8d
0x180009003  mov     [rbx+28h], eax
0x180009006  and     r8d, eax
0x180009009  jz      short loc_18000901D
0x18000900b  mov     rcx, [rbp+57h+var_90]
0x18000900f  mov     rdx, rbx
0x180009012  call    FwDiagSplitRule
0x180009017  mov     edi, eax
0x180009019  test    eax, eax
0x18000901b  jnz     short loc_18000904E
0x18000901d  or      word ptr [rbx+124h], 1
0x180009025  mov     rdx, rbx
0x180009028  mov     dword ptr [rbx+120h], 3
0x180009032  mov     rcx, [rbp+57h+var_90]
0x180009036  call    cs:__imp_FWSetFirewallRule
0x18000903c  mov     edi, eax
0x18000903e  test    eax, eax
0x180009040  jnz     short loc_18000904E
0x180009042  mov     rbx, [rbx]
0x180009045  test    rbx, rbx
0x180009048  jnz     loc_180008FC0
0x18000904e  mov     rbx, [rbp+57h+var_A0]
0x180009052  test    rbx, rbx
0x180009055  jz      short loc_180009060
0x180009057  mov     rcx, rbx
0x18000905a  call    cs:__imp_FWFreeFirewallRules
0x180009060  mov     rcx, [rbp+57h+var_90]
0x180009064  test    rcx, rcx
0x180009067  jz      short loc_18000906F
0x180009069  call    cs:__imp_FWClosePolicyStore
0x18000906f  mov     eax, edi
0x180009071  add     rsp, 98h
0x180009078  pop     r15
0x18000907a  pop     r14
0x18000907c  pop     r13
0x18000907e  pop     r12
0x180009080  pop     rdi
0x180009081  pop     rsi
0x180009082  pop     rbx
0x180009083  pop     rbp
0x180009084  retn
0x180009085  mov     edi, 57h ; 'W'
0x18000908a  jmp     short loc_180009052
```
