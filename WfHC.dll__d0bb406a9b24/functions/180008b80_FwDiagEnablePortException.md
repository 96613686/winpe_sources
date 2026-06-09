# FwDiagEnablePortException

- ea: `0x180008b80`
- end: `0x180008e3e`
- name: `FwDiagEnablePortException`
- size: `702`
- prototype: `__int64 __fastcall(__int16, __int16, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009580`

## callees

- `0x180008b80`
- `0x180009a50`

## import_xrefs

- `FirewallAPI!FWOpenPolicyStore` at `0x180008bf4`
- `FirewallAPI!FWOpenPolicyStore` at `0x180008bf4`
- `FirewallAPI!FWSetFirewallRule` at `0x180008de1`
- `FirewallAPI!FWSetFirewallRule` at `0x180008de1`
- `FirewallAPI!FWQueryFirewallRules` at `0x180008c79`
- `FirewallAPI!FWQueryFirewallRules` at `0x180008c79`
- `FirewallAPI!FWFreeFirewallRules` at `0x180008e0a`
- `FirewallAPI!FWFreeFirewallRules` at `0x180008e0a`
- `FirewallAPI!FWClosePolicyStore` at `0x180008e19`
- `FirewallAPI!FWClosePolicyStore` at `0x180008e19`

## pseudocode

```c
__int64 __fastcall FwDiagEnablePortException(__int16 a1, __int16 a2, int a3, int a4, int a5)
{
  unsigned int v9; // r14d
  __int64 *v10; // rbx
  __int64 *v11; // r8
  __int64 v12; // rax
  unsigned int v13; // r9d
  __int16 *v14; // rax
  int v15; // ecx
  __int16 v16; // dx
  int v17; // r10d
  unsigned int *v18; // rax
  unsigned int v19; // r8d
  __int16 *v20; // rax
  int v21; // ecx
  __int16 v22; // dx
  int v23; // eax
  int v24; // eax
  int v26; // [rsp+30h] [rbp-61h] BYREF
  int v27; // [rsp+34h] [rbp-5Dh]
  __int64 v28; // [rsp+38h] [rbp-59h] BYREF
  __int64 *v29; // [rsp+40h] [rbp-51h] BYREF
  __int128 v30; // [rsp+48h] [rbp-49h] BYREF
  __int64 v31; // [rsp+58h] [rbp-39h]
  __int128 v32; // [rsp+60h] [rbp-31h] BYREF
  __int128 v33; // [rsp+70h] [rbp-21h] BYREF
  __int128 v34; // [rsp+80h] [rbp-11h]
  __int128 v35; // [rsp+90h] [rbp-1h]

  v28 = 0;
  v31 = 0;
  v29 = 0;
  v26 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v30 = 0;
  v9 = FWOpenPolicyStore(545, 0, 2, 2, 0, &v28);
  if ( v9 )
    goto LABEL_42;
  *(_QWORD *)&v33 = 5;
  DWORD2(v33) = 2;
  LOWORD(v34) = a2;
  *((_QWORD *)&v32 + 1) = &v33;
  LODWORD(v35) = 2;
  v27 = 1;
  DWORD1(v30) = 1;
  *((_QWORD *)&v34 + 1) = 7 - (unsigned int)(a4 != 0);
  *((_QWORD *)&v30 + 1) = &v32;
  WORD4(v35) = a1;
  LODWORD(v32) = 2;
  LODWORD(v31) = 0x10000;
  LOWORD(v30) = 545;
  v9 = FWQueryFirewallRules(v28, &v30, 0, &v26, &v29);
  if ( v9 )
  {
LABEL_42:
    v10 = v29;
  }
  else
  {
    v10 = v29;
    if ( v26 && v29 )
    {
      v11 = v29;
      while ( 1 )
      {
        if ( *((_DWORD *)v11 + 11) == 2 - (a4 != 0) )
        {
          if ( *((_DWORD *)v11 + 72) == 3 )
          {
            if ( !a5 )
              goto LABEL_20;
          }
          else if ( a5 )
          {
            goto LABEL_20;
          }
          v12 = 8;
          if ( !a4 )
            v12 = 11;
          v13 = v11[v12];
          if ( v13 )
          {
            v14 = (__int16 *)v11[v12 + 1];
            v15 = 0;
            v16 = *v14;
            while ( v16 != v14[1] || v16 != a1 )
            {
              if ( ++v15 >= v13 )
                goto LABEL_20;
            }
            if ( (a3 & (_DWORD)v11[5]) != 0 )
              break;
          }
        }
LABEL_20:
        v11 = (__int64 *)*v11;
        if ( !v11 )
        {
          v17 = 0;
          v27 = 0;
          goto LABEL_22;
        }
      }
      v17 = 1;
      while ( 1 )
      {
LABEL_22:
        if ( *((_DWORD *)v10 + 11) == 2 - (a4 != 0) )
        {
          if ( *((_DWORD *)v10 + 72) == 3 )
          {
            if ( !a5 )
              goto LABEL_41;
          }
          else if ( a5 )
          {
            goto LABEL_41;
          }
          v18 = (unsigned int *)(v10 + 8);
          if ( !a4 )
            v18 = (unsigned int *)(v10 + 11);
          v19 = *v18;
          if ( *v18 )
          {
            v20 = (__int16 *)*((_QWORD *)v18 + 1);
            v21 = 0;
            v22 = *v20;
            while ( v22 != v20[1] || v22 != a1 )
            {
              if ( ++v21 >= v19 )
                goto LABEL_41;
            }
            v23 = *((_DWORD *)v10 + 10);
            if ( (v23 & a3) != 0 || !v17 )
            {
              v24 = a3 | v23;
              *((_DWORD *)v10 + 10) = v24;
              if ( (v24 & ~a3) != 0 )
              {
                v9 = FwDiagSplitRule(v28, v10);
                if ( v9 )
                  goto LABEL_42;
              }
              *((_WORD *)v10 + 146) |= 1u;
              *((_DWORD *)v10 + 72) = 3;
              v9 = FWSetFirewallRule(v28, v10);
              if ( v9 )
                goto LABEL_42;
            }
          }
        }
LABEL_41:
        v10 = (__int64 *)*v10;
        v17 = v27;
        if ( !v10 )
          goto LABEL_42;
      }
    }
    v9 = 87;
  }
  if ( v10 )
    FWFreeFirewallRules(v10);
  if ( v28 )
    FWClosePolicyStore();
  return v9;
}

```

## disassembly

```asm
0x180008b80  push    rbp
0x180008b82  push    rbx
0x180008b83  push    rsi
0x180008b84  push    rdi
0x180008b85  push    r12
0x180008b87  push    r13
0x180008b89  push    r14
0x180008b8b  push    r15
0x180008b8d  lea     rbp, [rsp-17h]
0x180008b92  sub     rsp, 0A8h
0x180008b99  xorps   xmm0, xmm0
0x180008b9c  xor     r15d, r15d
0x180008b9f  xor     eax, eax
0x180008ba1  mov     [rbp+4Fh+var_A8], r15
0x180008ba5  mov     [rbp+4Fh+var_88], rax
0x180008ba9  mov     r13d, r9d
0x180008bac  lea     rax, [rbp+4Fh+var_A8]
0x180008bb0  mov     [rbp+4Fh+var_A0], r15
0x180008bb4  mov     r9d, 2
0x180008bba  mov     [rsp+0E0h+var_B8], rax
0x180008bbf  mov     r12d, r8d
0x180008bc2  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x180008bc7  movzx   ebx, dx
0x180008bca  mov     [rbp+4Fh+var_B0], r15d
0x180008bce  movzx   edi, cx
0x180008bd1  xorps   xmm1, xmm1
0x180008bd4  mov     esi, 221h
0x180008bd9  xor     edx, edx
0x180008bdb  mov     ecx, esi
0x180008bdd  mov     r8d, r9d
0x180008be0  movups  [rbp+4Fh+var_70], xmm0
0x180008be4  movups  [rbp+4Fh+var_60], xmm0
0x180008be8  movups  [rbp+4Fh+var_50], xmm0
0x180008bec  movups  [rbp+4Fh+var_80], xmm0
0x180008bf0  movups  [rbp+4Fh+var_98], xmm1
0x180008bf4  call    cs:__imp_FWOpenPolicyStore
0x180008bfa  mov     r14d, eax
0x180008bfd  test    eax, eax
0x180008bff  jnz     loc_180008DFE
0x180008c05  mov     eax, r13d
0x180008c08  mov     qword ptr [rbp+4Fh+var_70], 5
0x180008c10  neg     eax
0x180008c12  mov     dword ptr [rbp+4Fh+var_70+8], 2
0x180008c19  lea     rax, [rbp+4Fh+var_70]
0x180008c1d  mov     word ptr [rbp+4Fh+var_60], bx
0x180008c21  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x180008c25  lea     r9, [rbp+4Fh+var_B0]
0x180008c29  sbb     ecx, ecx
0x180008c2b  mov     dword ptr [rbp+4Fh+var_60+0Ch], r15d
0x180008c2f  mov     eax, 1
0x180008c34  mov     dword ptr [rbp+4Fh+var_50], 2
0x180008c3b  mov     [rbp+4Fh+var_AC], eax
0x180008c3e  lea     rdx, [rbp+4Fh+var_98]
0x180008c42  mov     dword ptr [rbp+4Fh+var_98+4], eax
0x180008c45  add     ecx, 7
0x180008c48  lea     rax, [rbp+4Fh+var_80]
0x180008c4c  mov     dword ptr [rbp+4Fh+var_60+8], ecx
0x180008c4f  mov     rcx, [rbp+4Fh+var_A8]
0x180008c53  xor     r8d, r8d
0x180008c56  mov     qword ptr [rbp+4Fh+var_98+8], rax
0x180008c5a  lea     rax, [rbp+4Fh+var_A0]
0x180008c5e  mov     [rsp+0E0h+var_C0], rax
0x180008c63  mov     word ptr [rbp+4Fh+var_50+8], di
0x180008c67  mov     dword ptr [rbp+4Fh+var_80], 2
0x180008c6e  mov     dword ptr [rbp+4Fh+var_88], 10000h
0x180008c75  mov     word ptr [rbp+4Fh+var_98], si
0x180008c79  call    cs:__imp_FWQueryFirewallRules
0x180008c7f  mov     r14d, eax
0x180008c82  test    eax, eax
0x180008c84  jnz     loc_180008DFE
0x180008c8a  mov     rbx, [rbp+4Fh+var_A0]
0x180008c8e  cmp     [rbp+4Fh+var_B0], r15d
0x180008c92  jz      loc_180008E36
0x180008c98  test    rbx, rbx
0x180008c9b  jz      loc_180008E36
0x180008ca1  mov     r15d, [rbp+4Fh+arg_20]
0x180008ca5  mov     eax, r13d
0x180008ca8  neg     eax
0x180008caa  mov     r8, rbx
0x180008cad  mov     esi, 58h ; 'X'
0x180008cb2  sbb     r11d, r11d
0x180008cb5  add     r11d, 2
0x180008cb9  nop     dword ptr [rax+00000000h]
0x180008cc0  cmp     [r8+2Ch], r11d
0x180008cc4  jnz     short loc_180008D1A
0x180008cc6  cmp     dword ptr [r8+120h], 3
0x180008cce  jz      short loc_180008CD7
0x180008cd0  test    r15d, r15d
0x180008cd3  jz      short loc_180008CDC
0x180008cd5  jmp     short loc_180008D1A
0x180008cd7  test    r15d, r15d
0x180008cda  jz      short loc_180008D1A
0x180008cdc  test    r13d, r13d
0x180008cdf  mov     eax, 40h ; '@'
0x180008ce4  cmovz   rax, rsi
0x180008ce8  mov     r9d, [rax+r8]
0x180008cec  test    r9d, r9d
0x180008cef  jz      short loc_180008D1A
0x180008cf1  mov     rax, [rax+r8+8]
0x180008cf6  xor     ecx, ecx
0x180008cf8  movzx   r10d, word ptr [rax+2]
0x180008cfd  movzx   edx, word ptr [rax]
0x180008d00  cmp     dx, r10w
0x180008d04  jnz     short loc_180008D0B
0x180008d06  cmp     dx, di
0x180008d09  jz      short loc_180008D14
0x180008d0b  inc     ecx
0x180008d0d  cmp     ecx, r9d
0x180008d10  jb      short loc_180008D00
0x180008d12  jmp     short loc_180008D1A
0x180008d14  test    [r8+28h], r12d
0x180008d18  ja      short loc_180008D4F
0x180008d1a  mov     r8, [r8]
0x180008d1d  test    r8, r8
0x180008d20  jnz     short loc_180008CC0
0x180008d22  xor     r10d, r10d
0x180008d25  mov     [rbp+4Fh+var_AC], r10d
0x180008d29  mov     eax, r13d
0x180008d2c  neg     eax
0x180008d2e  sbb     esi, esi
0x180008d30  add     esi, 2
0x180008d33  cmp     [rbx+2Ch], esi
0x180008d36  jnz     loc_180008DEE
0x180008d3c  cmp     dword ptr [rbx+120h], 3
0x180008d43  jz      short loc_180008D57
0x180008d45  test    r15d, r15d
0x180008d48  jz      short loc_180008D60
0x180008d4a  jmp     loc_180008DEE
0x180008d4f  mov     r10d, 1
0x180008d55  jmp     short loc_180008D29
0x180008d57  test    r15d, r15d
0x180008d5a  jz      loc_180008DEE
0x180008d60  lea     rax, [rbx+40h]
0x180008d64  test    r13d, r13d
0x180008d67  jnz     short loc_180008D6D
0x180008d69  lea     rax, [rbx+58h]
0x180008d6d  mov     r8d, [rax]
0x180008d70  test    r8d, r8d
0x180008d73  jz      short loc_180008DEE
0x180008d75  mov     rax, [rax+8]
0x180008d79  xor     ecx, ecx
0x180008d7b  movzx   r9d, word ptr [rax+2]
0x180008d80  movzx   edx, word ptr [rax]
0x180008d83  cmp     dx, r9w
0x180008d87  jnz     short loc_180008D8E
0x180008d89  cmp     dx, di
0x180008d8c  jz      short loc_180008D97
0x180008d8e  inc     ecx
0x180008d90  cmp     ecx, r8d
0x180008d93  jb      short loc_180008D83
0x180008d95  jmp     short loc_180008DEE
0x180008d97  mov     eax, [rbx+28h]
0x180008d9a  test    r12d, eax
0x180008d9d  jnz     short loc_180008DA4
0x180008d9f  test    r10d, r10d
0x180008da2  jnz     short loc_180008DEE
0x180008da4  or      eax, r12d
0x180008da7  mov     r8d, r12d
0x180008daa  not     r8d
0x180008dad  mov     [rbx+28h], eax
0x180008db0  and     r8d, eax
0x180008db3  jz      short loc_180008DC8
0x180008db5  mov     rcx, [rbp+4Fh+var_A8]
0x180008db9  mov     rdx, rbx
0x180008dbc  call    FwDiagSplitRule
0x180008dc1  mov     r14d, eax
0x180008dc4  test    eax, eax
0x180008dc6  jnz     short loc_180008DFE
0x180008dc8  or      word ptr [rbx+124h], 1
0x180008dd0  mov     rdx, rbx
0x180008dd3  mov     dword ptr [rbx+120h], 3
0x180008ddd  mov     rcx, [rbp+4Fh+var_A8]
0x180008de1  call    cs:__imp_FWSetFirewallRule
0x180008de7  mov     r14d, eax
0x180008dea  test    eax, eax
0x180008dec  jnz     short loc_180008DFE
0x180008dee  mov     rbx, [rbx]
0x180008df1  mov     r10d, [rbp+4Fh+var_AC]
0x180008df5  test    rbx, rbx
0x180008df8  jnz     loc_180008D33
0x180008dfe  mov     rbx, [rbp+4Fh+var_A0]
0x180008e02  test    rbx, rbx
0x180008e05  jz      short loc_180008E10
0x180008e07  mov     rcx, rbx
0x180008e0a  call    cs:__imp_FWFreeFirewallRules
0x180008e10  mov     rcx, [rbp+4Fh+var_A8]
0x180008e14  test    rcx, rcx
0x180008e17  jz      short loc_180008E1F
0x180008e19  call    cs:__imp_FWClosePolicyStore
0x180008e1f  mov     eax, r14d
0x180008e22  add     rsp, 0A8h
0x180008e29  pop     r15
0x180008e2b  pop     r14
0x180008e2d  pop     r13
0x180008e2f  pop     r12
0x180008e31  pop     rdi
0x180008e32  pop     rsi
0x180008e33  pop     rbx
0x180008e34  pop     rbp
0x180008e35  retn
0x180008e36  mov     r14d, 57h ; 'W'
0x180008e3c  jmp     short loc_180008E02
```
