# BaddBranchToTree

- ea: `0x18000a460`
- end: `0x18000a824`
- name: `BaddBranchToTree`
- size: `964`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000a2d8`
- `0x18000b3c0`

## callees

- `0x180007220`
- `0x18000a460`
- `0x18000a82c`
- `0x18000a97c`
- `0x18000c39c`
- `0x18004485c`
- `0x180045500`
- `0x1800729e0`

## string_xrefs

- `0x18000a5ea`: `syntax error: attempt to truncate existing attribute tree.`

## pseudocode

```c
_BOOL8 __fastcall BaddBranchToTree(__int64 a1, unsigned int *a2, __int64 a3)
{
  __int64 v3; // rsi
  unsigned int v4; // r13d
  unsigned int v6; // r8d
  __int64 i; // rax
  __int64 v10; // r9
  __int64 v11; // rdx
  unsigned int v12; // ecx
  __int64 v13; // rdi
  int v14; // eax
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // r14d
  __int64 v19; // rcx
  __int64 v20; // r15
  __int64 v21; // r15
  __int64 v22; // r15
  int v23; // eax
  unsigned int v24; // r13d
  __int64 v25; // rcx
  int v26; // eax
  unsigned int v27; // r14d
  __int64 v28; // r15
  unsigned int v29; // [rsp+30h] [rbp-10h]
  unsigned int v30; // [rsp+90h] [rbp+50h] BYREF
  int v31; // [rsp+98h] [rbp+58h]

  v3 = *(_QWORD *)(a3 + 72);
  v4 = 0;
  v29 = 0;
  v6 = -1;
  v30 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v31 = i;
    if ( (unsigned int)i >= *(_DWORD *)(a3 + 612) )
      break;
    v10 = *(_QWORD *)(a3 + 600);
    v11 = (unsigned int)i;
    v12 = *(_DWORD *)(v10 + 8 * i);
    if ( v12 == 2 )
      goto LABEL_4;
    if ( v12 - 4 <= 2 )
    {
      LODWORD(i) = v31;
LABEL_4:
      v4 = *(_DWORD *)(v10 + 8 * v11 + 4);
      v29 = v4;
      continue;
    }
    if ( v12 <= 0xB && (v17 = 2696, _bittest(&v17, v12)) )
    {
      v18 = *(_DWORD *)(v10 + 8 * v11 + 4);
    }
    else
    {
      if ( ((v12 - 8) & 0xFFFFFFF9) != 0 || v12 == 14 )
        goto LABEL_25;
      v18 = -1;
    }
    if ( v6 == -1 )
    {
      v19 = *a2;
      if ( (_DWORD)v19 == 0x7FFFFFFF )
      {
        if ( !(unsigned int)BcreateEndNode(&v30, v4, v18, a3) )
          return 0;
        v6 = v30;
        *a2 = v30;
      }
      else if ( (int)v19 < 0 )
      {
        if ( !(unsigned int)BcreateGlobalInitializerNode(&v30, v19 & 0x7FFFFFFF, a3) )
          return 0;
        v21 = v30;
        *a2 = v30;
        if ( !(unsigned int)BcreateEndNode(&v30, v4, v18, a3) )
          return 0;
        v6 = v30;
        *(_DWORD *)(v3 + 20 * v21 + 8) = v30;
      }
      else
      {
        v20 = 5 * v19;
        v30 = *a2;
        if ( *(_DWORD *)(v3 + 20 * v19) != -1 )
          goto LABEL_23;
        LODWORD(v19) = *(_DWORD *)(v3 + 20 * v19 + 8);
        if ( (_DWORD)v19 != -1 )
          goto LABEL_40;
        if ( !(unsigned int)BcreateEndNode(&v30, v4, v18, a3) )
          return 0;
        v6 = v30;
        *(_DWORD *)(v3 + 4 * v20 + 8) = v30;
      }
    }
    else
    {
      v22 = 5LL * v6;
      v23 = *(_DWORD *)(v3 + 20LL * v6 + 16);
      if ( !v23 )
      {
        LODWORD(v19) = *(_DWORD *)(v3 + 20LL * v6 + 12);
LABEL_40:
        v30 = v19;
LABEL_23:
        if ( !(unsigned int)BfindOrCreateMatchingNode(v19, &v30, v4, v18, a3) )
        {
          vIdentifySource(a1, a3);
          return 0;
        }
        v6 = v30;
        goto LABEL_25;
      }
      v24 = -1;
      if ( v23 != 1 )
        goto LABEL_46;
      if ( !(unsigned int)BcreateEndNode(&v30, v29, 0xFFFFFFFFLL, a3) )
        return 0;
      v6 = v30;
      v24 = v30;
      v25 = 5LL * v30;
      *(_DWORD *)(v3 + 4 * v25 + 16) = 1;
      *(_DWORD *)(v3 + 4 * v25 + 12) = *(_DWORD *)(v3 + 4 * v22 + 12);
      if ( v6 == -1 || v18 != -1 )
      {
LABEL_46:
        if ( !(unsigned int)BcreateEndNode(&v30, v29, v18, a3) )
          return 0;
        v6 = v30;
        *(_DWORD *)(v3 + 20LL * v30 + 8) = v24;
      }
      v4 = v29;
      *(_DWORD *)(v3 + 4 * v22 + 16) = 0;
      *(_DWORD *)(v3 + 4 * v22 + 12) = v6;
    }
LABEL_25:
    LODWORD(i) = v31;
  }
  if ( v6 == -1 )
  {
    v16 = *a2;
    if ( (_DWORD)v16 == 0x7FFFFFFF )
    {
      if ( (unsigned int)BaddValueToHeap(a2, a1, 0, a3) )
      {
        *a2 |= 0x80000000;
        return 1;
      }
      *a2 = 0x7FFFFFFF;
      return 0;
    }
    if ( (int)v16 >= 0 )
    {
      if ( *(_DWORD *)(v3 + 20 * v16) != -1 )
      {
        if ( !(unsigned int)BcreateGlobalInitializerNode(&v30, 0, a3) )
          return 0;
        v27 = v30;
        v28 = 5LL * v30;
        if ( !(unsigned int)BaddValueToHeap(v3 + 4 * (v28 + 3), a1, 0, a3) )
        {
          BreturnElementFromMasterTable(3, v27, a3);
          return 0;
        }
        *(_DWORD *)(v3 + 4 * v28 + 8) = *a2;
        *a2 = v27;
        return 1;
      }
      v26 = BaddValueToHeap(v3 + 4 * (5 * v16 + 3), a1, 1, a3);
    }
    else
    {
      *a2 = v16 & 0x7FFFFFFF;
      v26 = BaddValueToHeap(a2, a1, 1, a3);
      *a2 |= 0x80000000;
    }
    return v26 != 0;
  }
  v13 = 5LL * v6;
  v14 = *(_DWORD *)(v3 + 20LL * v6 + 16);
  if ( !v14 )
  {
    vIdentifySource(a1, a3);
    WriteDbgTraceErrorGpd("BaddBranchToTree", "syntax error: attempt to truncate existing attribute tree.");
    return 0;
  }
  if ( (unsigned int)BaddValueToHeap(v3 + 12 + 20LL * v6, a1, v14 == 1, a3) )
  {
    *(_DWORD *)(v3 + 4 * v13 + 16) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a460  mov     [rsp-38h+arg_0], rbx
0x18000a465  push    rbp
0x18000a466  push    rsi
0x18000a467  push    rdi
0x18000a468  push    r12
0x18000a46a  push    r13
0x18000a46c  push    r14
0x18000a46e  push    r15
0x18000a470  mov     rbp, rsp
0x18000a473  sub     rsp, 40h
0x18000a477  mov     rsi, [r8+48h]
0x18000a47b  xor     r13d, r13d
0x18000a47e  mov     rbx, r8
0x18000a481  mov     [rbp+var_10], r13d
0x18000a485  or      r8d, 0FFFFFFFFh
0x18000a489  mov     [rbp+arg_10], r13d
0x18000a48d  xor     eax, eax
0x18000a48f  mov     rdi, rdx
0x18000a492  mov     r12, rcx
0x18000a495  mov     [rbp+arg_18], eax
0x18000a498  cmp     eax, [rbx+264h]
0x18000a49e  jnb     short loc_18000A4C3
0x18000a4a0  mov     r9, [rbx+258h]
0x18000a4a7  mov     edx, eax
0x18000a4a9  mov     ecx, [r9+rax*8]
0x18000a4ad  cmp     ecx, 2
0x18000a4b0  jnz     loc_18000A552
0x18000a4b6  mov     r13d, [r9+rdx*8+4]
0x18000a4bb  mov     [rbp+var_10], r13d
0x18000a4bf  inc     eax
0x18000a4c1  jmp     short loc_18000A495
0x18000a4c3  cmp     r8d, 0FFFFFFFFh
0x18000a4c7  jz      short loc_18000A50C
0x18000a4c9  mov     eax, r8d
0x18000a4cc  lea     rdi, [rax+rax*4]
0x18000a4d0  mov     eax, [rsi+rdi*4+10h]
0x18000a4d4  test    eax, eax
0x18000a4d6  jz      loc_18000A5DF
0x18000a4dc  xor     r8d, r8d
0x18000a4df  lea     rcx, [rsi+0Ch]
0x18000a4e3  cmp     eax, 1
0x18000a4e6  lea     rcx, [rcx+rdi*4]
0x18000a4ea  mov     r9, rbx
0x18000a4ed  mov     rdx, r12
0x18000a4f0  setz    r8b
0x18000a4f4  call    BaddValueToHeap
0x18000a4f9  test    eax, eax
0x18000a4fb  jz      short loc_18000A538
0x18000a4fd  mov     dword ptr [rsi+rdi*4+10h], 1
0x18000a505  mov     eax, 1
0x18000a50a  jmp     short loc_18000A53A
0x18000a50c  mov     eax, [rdi]
0x18000a50e  cmp     eax, 7FFFFFFFh
0x18000a513  jnz     loc_18000A776
0x18000a519  mov     r9, rbx
0x18000a51c  xor     r8d, r8d
0x18000a51f  mov     rdx, r12
0x18000a522  mov     rcx, rdi
0x18000a525  call    BaddValueToHeap
0x18000a52a  test    eax, eax
0x18000a52c  jnz     loc_18000A76D
0x18000a532  mov     dword ptr [rdi], 7FFFFFFFh
0x18000a538  xor     eax, eax
0x18000a53a  mov     rbx, [rsp+40h+arg_0]
0x18000a542  add     rsp, 40h
0x18000a546  pop     r15
0x18000a548  pop     r14
0x18000a54a  pop     r13
0x18000a54c  pop     r12
0x18000a54e  pop     rdi
0x18000a54f  pop     rsi
0x18000a550  pop     rbp
0x18000a551  retn
0x18000a552  lea     eax, [rcx-4]
0x18000a555  cmp     eax, 2
0x18000a558  jbe     loc_18000A765
0x18000a55e  cmp     ecx, 0Bh
0x18000a561  ja      loc_18000A602
0x18000a567  mov     eax, 0A88h
0x18000a56c  bt      eax, ecx
0x18000a56f  jnb     loc_18000A602
0x18000a575  mov     r14d, [r9+rdx*8+4]
0x18000a57a  cmp     r8d, 0FFFFFFFFh
0x18000a57e  jnz     loc_18000A6CC
0x18000a584  mov     ecx, [rdi]
0x18000a586  cmp     ecx, 7FFFFFFFh
0x18000a58c  jz      loc_18000A61A
0x18000a592  test    ecx, ecx
0x18000a594  js      loc_18000A63D
0x18000a59a  lea     r15, [rcx+rcx*4]
0x18000a59e  mov     [rbp+arg_10], ecx
0x18000a5a1  cmp     [rsi+r15*4], r8d
0x18000a5a5  jz      loc_18000A68A
0x18000a5ab  mov     r9d, r14d
0x18000a5ae  mov     [rsp+40h+var_20], rbx
0x18000a5b3  mov     r8d, r13d
0x18000a5b6  lea     rdx, [rbp+arg_10]
0x18000a5ba  call    BfindOrCreateMatchingNode
0x18000a5bf  test    eax, eax
0x18000a5c1  jz      short loc_18000A5CF
0x18000a5c3  mov     r8d, [rbp+arg_10]
0x18000a5c7  mov     eax, [rbp+arg_18]
0x18000a5ca  jmp     loc_18000A4BF
0x18000a5cf  mov     rdx, rbx
0x18000a5d2  mov     rcx, r12
0x18000a5d5  call    vIdentifySource
0x18000a5da  jmp     loc_18000A538
0x18000a5df  mov     rdx, rbx
0x18000a5e2  mov     rcx, r12
0x18000a5e5  call    vIdentifySource
0x18000a5ea  lea     rdx, aSyntaxErrorAtt; "syntax error: attempt to truncate exist"...
0x18000a5f1  lea     rcx, aBaddbranchtotr; "BaddBranchToTree"
0x18000a5f8  call    WriteDbgTraceErrorGpd
0x18000a5fd  jmp     loc_18000A538
0x18000a602  lea     eax, [rcx-8]
0x18000a605  test    eax, 0FFFFFFF9h
0x18000a60a  jnz     short loc_18000A5C7
0x18000a60c  cmp     ecx, 0Eh
0x18000a60f  jz      short loc_18000A5C7
0x18000a611  or      r14d, 0FFFFFFFFh
0x18000a615  jmp     loc_18000A57A
0x18000a61a  mov     r9, rbx
0x18000a61d  lea     rcx, [rbp+arg_10]
0x18000a621  mov     r8d, r14d
0x18000a624  mov     edx, r13d
0x18000a627  call    BcreateEndNode
0x18000a62c  test    eax, eax
0x18000a62e  jz      loc_18000A538
0x18000a634  mov     r8d, [rbp+arg_10]
0x18000a638  mov     [rdi], r8d
0x18000a63b  jmp     short loc_18000A5C7
0x18000a63d  btr     ecx, 1Fh
0x18000a641  mov     r8, rbx
0x18000a644  mov     edx, ecx
0x18000a646  lea     rcx, [rbp+arg_10]
0x18000a64a  call    BcreateGlobalInitializerNode
0x18000a64f  test    eax, eax
0x18000a651  jz      loc_18000A538
0x18000a657  mov     r15d, [rbp+arg_10]
0x18000a65b  lea     rcx, [rbp+arg_10]
0x18000a65f  mov     r9, rbx
0x18000a662  mov     [rdi], r15d
0x18000a665  mov     r8d, r14d
0x18000a668  mov     edx, r13d
0x18000a66b  call    BcreateEndNode
0x18000a670  test    eax, eax
0x18000a672  jz      loc_18000A538
0x18000a678  mov     r8d, [rbp+arg_10]
0x18000a67c  lea     rcx, [r15+r15*4]
0x18000a680  mov     [rsi+rcx*4+8], r8d
0x18000a685  jmp     loc_18000A5C7
0x18000a68a  lea     rcx, [rcx+rcx*4]
0x18000a68e  mov     ecx, [rsi+rcx*4+8]
0x18000a692  cmp     ecx, 0FFFFFFFFh
0x18000a695  jnz     short loc_18000A6C4
0x18000a697  mov     r9, rbx
0x18000a69a  lea     rcx, [rbp+arg_10]
0x18000a69e  mov     r8d, r14d
0x18000a6a1  mov     edx, r13d
0x18000a6a4  call    BcreateEndNode
0x18000a6a9  test    eax, eax
0x18000a6ab  jz      loc_18000A538
0x18000a6b1  mov     r8d, [rbp+arg_10]
0x18000a6b5  mov     [rsi+r15*4+8], r8d
0x18000a6ba  jmp     loc_18000A5C7
0x18000a6bf  mov     ecx, [rsi+r15*4+0Ch]
0x18000a6c4  mov     [rbp+arg_10], ecx
0x18000a6c7  jmp     loc_18000A5AB
0x18000a6cc  mov     eax, r8d
0x18000a6cf  lea     r15, [rax+rax*4]
0x18000a6d3  mov     eax, [rsi+r15*4+10h]
0x18000a6d8  test    eax, eax
0x18000a6da  jz      short loc_18000A6BF
0x18000a6dc  or      r13d, 0FFFFFFFFh
0x18000a6e0  cmp     eax, 1
0x18000a6e3  jnz     short loc_18000A727
0x18000a6e5  mov     edx, [rbp+var_10]
0x18000a6e8  lea     rcx, [rbp+arg_10]
0x18000a6ec  mov     r9, rbx
0x18000a6ef  or      r8d, r13d
0x18000a6f2  call    BcreateEndNode
0x18000a6f7  test    eax, eax
0x18000a6f9  jz      loc_18000A538
0x18000a6ff  mov     r8d, [rbp+arg_10]
0x18000a703  mov     r13d, r8d
0x18000a706  lea     rcx, [r8+r8*4]
0x18000a70a  mov     dword ptr [rsi+rcx*4+10h], 1
0x18000a712  mov     eax, [rsi+r15*4+0Ch]
0x18000a717  mov     [rsi+rcx*4+0Ch], eax
0x18000a71b  cmp     r8d, 0FFFFFFFFh
0x18000a71f  jz      short loc_18000A727
0x18000a721  cmp     r14d, 0FFFFFFFFh
0x18000a725  jz      short loc_18000A74E
0x18000a727  mov     edx, [rbp+var_10]
0x18000a72a  lea     rcx, [rbp+arg_10]
0x18000a72e  mov     r9, rbx
0x18000a731  mov     r8d, r14d
0x18000a734  call    BcreateEndNode
0x18000a739  test    eax, eax
0x18000a73b  jz      loc_18000A538
0x18000a741  mov     r8d, [rbp+arg_10]
0x18000a745  lea     rcx, [r8+r8*4]
0x18000a749  mov     [rsi+rcx*4+8], r13d
0x18000a74e  mov     r13d, [rbp+var_10]
0x18000a752  mov     dword ptr [rsi+r15*4+10h], 0
0x18000a75b  mov     [rsi+r15*4+0Ch], r8d
0x18000a760  jmp     loc_18000A5C7
0x18000a765  mov     eax, [rbp+arg_18]
0x18000a768  jmp     loc_18000A4B6
0x18000a76d  bts     dword ptr [rdi], 1Fh
0x18000a771  jmp     loc_18000A505
0x18000a776  test    eax, eax
0x18000a778  jns     short loc_18000A79A
0x18000a77a  btr     eax, 1Fh
0x18000a77e  mov     r9, rbx
0x18000a781  mov     r8d, 1
0x18000a787  mov     [rdi], eax
0x18000a789  mov     rdx, r12
0x18000a78c  mov     rcx, rdi
0x18000a78f  call    BaddValueToHeap
0x18000a794  bts     dword ptr [rdi], 1Fh
0x18000a798  jmp     short loc_18000A7BD
0x18000a79a  lea     rcx, [rax+rax*4]
0x18000a79e  cmp     dword ptr [rsi+rcx*4], 0FFFFFFFFh
0x18000a7a2  jnz     short loc_18000A7CA
0x18000a7a4  add     rcx, 3
0x18000a7a8  mov     r9, rbx
0x18000a7ab  mov     r8d, 1
0x18000a7b1  mov     rdx, r12
0x18000a7b4  lea     rcx, [rsi+rcx*4]
0x18000a7b8  call    BaddValueToHeap
0x18000a7bd  test    eax, eax
0x18000a7bf  jz      loc_18000A538
0x18000a7c5  jmp     loc_18000A505
0x18000a7ca  mov     r8, rbx
0x18000a7cd  lea     rcx, [rbp+arg_10]
0x18000a7d1  xor     edx, edx
0x18000a7d3  call    BcreateGlobalInitializerNode
0x18000a7d8  test    eax, eax
0x18000a7da  jz      loc_18000A538
0x18000a7e0  mov     r14d, [rbp+arg_10]
0x18000a7e4  mov     r9, rbx
0x18000a7e7  xor     r8d, r8d
0x18000a7ea  mov     rdx, r12
0x18000a7ed  lea     r15, [r14+r14*4]
0x18000a7f1  lea     rcx, [r15+3]
0x18000a7f5  lea     rcx, [rsi+rcx*4]
0x18000a7f9  call    BaddValueToHeap
0x18000a7fe  test    eax, eax
0x18000a800  jnz     short loc_18000A815
0x18000a802  mov     r8, rbx
0x18000a805  lea     ecx, [rax+3]
0x18000a808  mov     edx, r14d
0x18000a80b  call    BreturnElementFromMasterTable
0x18000a810  jmp     loc_18000A538
0x18000a815  mov     ecx, [rdi]
0x18000a817  mov     [rsi+r15*4+8], ecx
0x18000a81c  mov     [rdi], r14d
0x18000a81f  jmp     loc_18000A505
```
