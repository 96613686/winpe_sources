# BaddBranchToTree

- ea: `0x18000a45c`
- end: `0x18000a821`
- name: `BaddBranchToTree`
- size: `965`
- prototype: `_BOOL8 __fastcall(__int64, unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000a2d0`
- `0x18000b3d0`

## callees

- `0x180007150`
- `0x18000a45c`
- `0x18000a828`
- `0x18000a97c`
- `0x18000c390`
- `0x180045aa4`
- `0x1800466f8`
- `0x180074a6c`

## string_xrefs

- `0x18000a5e7`: `syntax error: attempt to truncate existing attribute tree.`

## pseudocode

```c
_BOOL8 __fastcall BaddBranchToTree(unsigned int *a1, unsigned int *a2, __int64 a3)
{
  __int64 v3; // rsi
  int v4; // r13d
  __int64 v6; // r8
  __int64 i; // rax
  __int64 v10; // r9
  __int64 v11; // rdx
  unsigned int v12; // ecx
  __int64 v13; // rdi
  int v14; // eax
  __int64 v16; // rax
  int v17; // eax
  int v18; // r14d
  __int64 v19; // rcx
  __int64 v20; // r15
  __int64 v21; // r8
  __int64 v22; // r15
  __int64 v23; // r15
  int v24; // eax
  unsigned int v25; // r13d
  __int64 v26; // rcx
  int v27; // eax
  int v28; // r14d
  __int64 v29; // r15
  int v30; // [rsp+30h] [rbp-10h]
  unsigned int v31; // [rsp+90h] [rbp+50h] BYREF
  int v32; // [rsp+98h] [rbp+58h]

  v3 = *(_QWORD *)(a3 + 72);
  v4 = 0;
  v30 = 0;
  v6 = 0xFFFFFFFFLL;
  v31 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v32 = i;
    if ( (unsigned int)i >= *(_DWORD *)(a3 + 612) )
      break;
    v10 = *(_QWORD *)(a3 + 600);
    v11 = (unsigned int)i;
    v12 = *(_DWORD *)(v10 + 8 * i);
    if ( v12 == 2 )
      goto LABEL_4;
    if ( v12 - 4 <= 2 )
    {
      LODWORD(i) = v32;
LABEL_4:
      v4 = *(_DWORD *)(v10 + 8 * v11 + 4);
      v30 = v4;
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
    if ( (_DWORD)v6 == -1 )
    {
      v19 = *a2;
      if ( (_DWORD)v19 == 0x7FFFFFFF )
      {
        if ( !(unsigned int)BcreateEndNode(&v31, v4, v18, a3) )
          return 0;
        v6 = v31;
        *a2 = v31;
      }
      else if ( (int)v19 < 0 )
      {
        if ( !(unsigned int)BcreateGlobalInitializerNode(&v31, v19 & 0x7FFFFFFF, a3) )
          return 0;
        v22 = v31;
        *a2 = v31;
        if ( !(unsigned int)BcreateEndNode(&v31, v4, v18, a3) )
          return 0;
        v6 = v31;
        *(_DWORD *)(v3 + 20 * v22 + 8) = v31;
      }
      else
      {
        v20 = 5 * v19;
        v31 = *a2;
        if ( *(_DWORD *)(v3 + 20 * v19) != -1 )
          goto LABEL_23;
        LODWORD(v19) = *(_DWORD *)(v3 + 20 * v19 + 8);
        if ( (_DWORD)v19 != -1 )
          goto LABEL_40;
        if ( !(unsigned int)BcreateEndNode(&v31, v4, v18, a3) )
          return 0;
        v6 = v31;
        *(_DWORD *)(v3 + 4 * v20 + 8) = v31;
      }
    }
    else
    {
      v23 = 5LL * (unsigned int)v6;
      v24 = *(_DWORD *)(v3 + 20LL * (unsigned int)v6 + 16);
      if ( !v24 )
      {
        LODWORD(v19) = *(_DWORD *)(v3 + 20LL * (unsigned int)v6 + 12);
LABEL_40:
        v31 = v19;
LABEL_23:
        if ( !(unsigned int)BfindOrCreateMatchingNode(v19, &v31, v4, v18, a3) )
        {
          vIdentifySource(a1, a3, v21);
          return 0;
        }
        v6 = v31;
        goto LABEL_25;
      }
      v25 = -1;
      if ( v24 != 1 )
        goto LABEL_46;
      if ( !(unsigned int)BcreateEndNode(&v31, v30, -1, a3) )
        return 0;
      v6 = v31;
      v25 = v31;
      v26 = 5LL * v31;
      *(_DWORD *)(v3 + 4 * v26 + 16) = 1;
      *(_DWORD *)(v3 + 4 * v26 + 12) = *(_DWORD *)(v3 + 4 * v23 + 12);
      if ( (_DWORD)v6 == -1 || v18 != -1 )
      {
LABEL_46:
        if ( !(unsigned int)BcreateEndNode(&v31, v30, v18, a3) )
          return 0;
        v6 = v31;
        *(_DWORD *)(v3 + 20LL * v31 + 8) = v25;
      }
      v4 = v30;
      *(_DWORD *)(v3 + 4 * v23 + 16) = 0;
      *(_DWORD *)(v3 + 4 * v23 + 12) = v6;
    }
LABEL_25:
    LODWORD(i) = v32;
  }
  if ( (_DWORD)v6 == -1 )
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
        if ( !(unsigned int)BcreateGlobalInitializerNode(&v31, 0, a3) )
          return 0;
        v28 = v31;
        v29 = 5LL * v31;
        if ( !(unsigned int)BaddValueToHeap((unsigned int *)(v3 + 4 * (v29 + 3)), a1, 0, a3) )
        {
          BreturnElementFromMasterTable(3, v28, (_DWORD *)a3);
          return 0;
        }
        *(_DWORD *)(v3 + 4 * v29 + 8) = *a2;
        *a2 = v28;
        return 1;
      }
      v27 = BaddValueToHeap((unsigned int *)(v3 + 4 * (5 * v16 + 3)), a1, 1, a3);
    }
    else
    {
      *a2 = v16 & 0x7FFFFFFF;
      v27 = BaddValueToHeap(a2, a1, 1, a3);
      *a2 |= 0x80000000;
    }
    return v27 != 0;
  }
  v13 = 5LL * (unsigned int)v6;
  v14 = *(_DWORD *)(v3 + 20LL * (unsigned int)v6 + 16);
  if ( !v14 )
  {
    vIdentifySource(a1, a3, v6);
    WriteDbgTraceErrorGpd((__int64)"BaddBranchToTree", "syntax error: attempt to truncate existing attribute tree.");
    return 0;
  }
  if ( (unsigned int)BaddValueToHeap((unsigned int *)(v3 + 12 + 20LL * (unsigned int)v6), a1, v14 == 1, a3) )
  {
    *(_DWORD *)(v3 + 4 * v13 + 16) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a45c  mov     [rsp-38h+arg_0], rbx
0x18000a461  push    rbp
0x18000a462  push    rsi
0x18000a463  push    rdi
0x18000a464  push    r12
0x18000a466  push    r13
0x18000a468  push    r14
0x18000a46a  push    r15
0x18000a46c  mov     rbp, rsp
0x18000a46f  sub     rsp, 40h
0x18000a473  mov     rsi, [r8+48h]
0x18000a477  xor     r13d, r13d
0x18000a47a  mov     rbx, r8
0x18000a47d  mov     [rbp+var_10], r13d
0x18000a481  or      r8d, 0FFFFFFFFh
0x18000a485  mov     [rbp+arg_10], r13d
0x18000a489  xor     eax, eax
0x18000a48b  mov     rdi, rdx
0x18000a48e  mov     r12, rcx
0x18000a491  mov     [rbp+arg_18], eax
0x18000a494  cmp     eax, [rbx+264h]
0x18000a49a  jnb     short loc_18000A4BF
0x18000a49c  mov     r9, [rbx+258h]
0x18000a4a3  mov     edx, eax
0x18000a4a5  mov     ecx, [r9+rax*8]
0x18000a4a9  cmp     ecx, 2
0x18000a4ac  jnz     loc_18000A54F
0x18000a4b2  mov     r13d, [r9+rdx*8+4]
0x18000a4b7  mov     [rbp+var_10], r13d
0x18000a4bb  inc     eax
0x18000a4bd  jmp     short loc_18000A491
0x18000a4bf  cmp     r8d, 0FFFFFFFFh
0x18000a4c3  jz      short loc_18000A508
0x18000a4c5  mov     eax, r8d
0x18000a4c8  lea     rdi, [rax+rax*4]
0x18000a4cc  mov     eax, [rsi+rdi*4+10h]
0x18000a4d0  test    eax, eax
0x18000a4d2  jz      loc_18000A5DC
0x18000a4d8  xor     r8d, r8d
0x18000a4db  lea     rcx, [rsi+0Ch]
0x18000a4df  cmp     eax, 1
0x18000a4e2  lea     rcx, [rcx+rdi*4]
0x18000a4e6  mov     r9, rbx
0x18000a4e9  mov     rdx, r12
0x18000a4ec  setz    r8b
0x18000a4f0  call    BaddValueToHeap
0x18000a4f5  test    eax, eax
0x18000a4f7  jz      short loc_18000A534
0x18000a4f9  mov     dword ptr [rsi+rdi*4+10h], 1
0x18000a501  mov     eax, 1
0x18000a506  jmp     short loc_18000A536
0x18000a508  mov     eax, [rdi]
0x18000a50a  cmp     eax, 7FFFFFFFh
0x18000a50f  jnz     loc_18000A773
0x18000a515  mov     r9, rbx
0x18000a518  xor     r8d, r8d
0x18000a51b  mov     rdx, r12
0x18000a51e  mov     rcx, rdi
0x18000a521  call    BaddValueToHeap
0x18000a526  test    eax, eax
0x18000a528  jnz     loc_18000A76A
0x18000a52e  mov     dword ptr [rdi], 7FFFFFFFh
0x18000a534  xor     eax, eax
0x18000a536  mov     rbx, [rsp+40h+arg_0]
0x18000a53e  add     rsp, 40h
0x18000a542  pop     r15
0x18000a544  pop     r14
0x18000a546  pop     r13
0x18000a548  pop     r12
0x18000a54a  pop     rdi
0x18000a54b  pop     rsi
0x18000a54c  pop     rbp
0x18000a54d  retn
0x18000a54f  lea     eax, [rcx-4]
0x18000a552  cmp     eax, 2
0x18000a555  jbe     loc_18000A762
0x18000a55b  cmp     ecx, 0Bh
0x18000a55e  ja      loc_18000A5FF
0x18000a564  mov     eax, 0A88h
0x18000a569  bt      eax, ecx
0x18000a56c  jnb     loc_18000A5FF
0x18000a572  mov     r14d, [r9+rdx*8+4]
0x18000a577  cmp     r8d, 0FFFFFFFFh
0x18000a57b  jnz     loc_18000A6C9
0x18000a581  mov     ecx, [rdi]
0x18000a583  cmp     ecx, 7FFFFFFFh
0x18000a589  jz      loc_18000A617
0x18000a58f  test    ecx, ecx
0x18000a591  js      loc_18000A63A
0x18000a597  lea     r15, [rcx+rcx*4]
0x18000a59b  mov     [rbp+arg_10], ecx
0x18000a59e  cmp     [rsi+r15*4], r8d
0x18000a5a2  jz      loc_18000A687
0x18000a5a8  mov     r9d, r14d
0x18000a5ab  mov     [rsp+40h+var_20], rbx
0x18000a5b0  mov     r8d, r13d
0x18000a5b3  lea     rdx, [rbp+arg_10]
0x18000a5b7  call    BfindOrCreateMatchingNode
0x18000a5bc  test    eax, eax
0x18000a5be  jz      short loc_18000A5CC
0x18000a5c0  mov     r8d, [rbp+arg_10]
0x18000a5c4  mov     eax, [rbp+arg_18]
0x18000a5c7  jmp     loc_18000A4BB
0x18000a5cc  mov     rdx, rbx
0x18000a5cf  mov     rcx, r12
0x18000a5d2  call    vIdentifySource
0x18000a5d7  jmp     loc_18000A534
0x18000a5dc  mov     rdx, rbx
0x18000a5df  mov     rcx, r12
0x18000a5e2  call    vIdentifySource
0x18000a5e7  lea     rdx, aSyntaxErrorAtt; "syntax error: attempt to truncate exist"...
0x18000a5ee  lea     rcx, aBaddbranchtotr; "BaddBranchToTree"
0x18000a5f5  call    WriteDbgTraceErrorGpd
0x18000a5fa  jmp     loc_18000A534
0x18000a5ff  lea     eax, [rcx-8]
0x18000a602  test    eax, 0FFFFFFF9h
0x18000a607  jnz     short loc_18000A5C4
0x18000a609  cmp     ecx, 0Eh
0x18000a60c  jz      short loc_18000A5C4
0x18000a60e  or      r14d, 0FFFFFFFFh
0x18000a612  jmp     loc_18000A577
0x18000a617  mov     r9, rbx
0x18000a61a  lea     rcx, [rbp+arg_10]
0x18000a61e  mov     r8d, r14d
0x18000a621  mov     edx, r13d
0x18000a624  call    BcreateEndNode
0x18000a629  test    eax, eax
0x18000a62b  jz      loc_18000A534
0x18000a631  mov     r8d, [rbp+arg_10]
0x18000a635  mov     [rdi], r8d
0x18000a638  jmp     short loc_18000A5C4
0x18000a63a  btr     ecx, 1Fh
0x18000a63e  mov     r8, rbx
0x18000a641  mov     edx, ecx
0x18000a643  lea     rcx, [rbp+arg_10]
0x18000a647  call    BcreateGlobalInitializerNode
0x18000a64c  test    eax, eax
0x18000a64e  jz      loc_18000A534
0x18000a654  mov     r15d, [rbp+arg_10]
0x18000a658  lea     rcx, [rbp+arg_10]
0x18000a65c  mov     r9, rbx
0x18000a65f  mov     [rdi], r15d
0x18000a662  mov     r8d, r14d
0x18000a665  mov     edx, r13d
0x18000a668  call    BcreateEndNode
0x18000a66d  test    eax, eax
0x18000a66f  jz      loc_18000A534
0x18000a675  mov     r8d, [rbp+arg_10]
0x18000a679  lea     rcx, [r15+r15*4]
0x18000a67d  mov     [rsi+rcx*4+8], r8d
0x18000a682  jmp     loc_18000A5C4
0x18000a687  lea     rcx, [rcx+rcx*4]
0x18000a68b  mov     ecx, [rsi+rcx*4+8]
0x18000a68f  cmp     ecx, 0FFFFFFFFh
0x18000a692  jnz     short loc_18000A6C1
0x18000a694  mov     r9, rbx
0x18000a697  lea     rcx, [rbp+arg_10]
0x18000a69b  mov     r8d, r14d
0x18000a69e  mov     edx, r13d
0x18000a6a1  call    BcreateEndNode
0x18000a6a6  test    eax, eax
0x18000a6a8  jz      loc_18000A534
0x18000a6ae  mov     r8d, [rbp+arg_10]
0x18000a6b2  mov     [rsi+r15*4+8], r8d
0x18000a6b7  jmp     loc_18000A5C4
0x18000a6bc  mov     ecx, [rsi+r15*4+0Ch]
0x18000a6c1  mov     [rbp+arg_10], ecx
0x18000a6c4  jmp     loc_18000A5A8
0x18000a6c9  mov     eax, r8d
0x18000a6cc  lea     r15, [rax+rax*4]
0x18000a6d0  mov     eax, [rsi+r15*4+10h]
0x18000a6d5  test    eax, eax
0x18000a6d7  jz      short loc_18000A6BC
0x18000a6d9  or      r13d, 0FFFFFFFFh
0x18000a6dd  cmp     eax, 1
0x18000a6e0  jnz     short loc_18000A724
0x18000a6e2  mov     edx, [rbp+var_10]
0x18000a6e5  lea     rcx, [rbp+arg_10]
0x18000a6e9  mov     r9, rbx
0x18000a6ec  or      r8d, r13d
0x18000a6ef  call    BcreateEndNode
0x18000a6f4  test    eax, eax
0x18000a6f6  jz      loc_18000A534
0x18000a6fc  mov     r8d, [rbp+arg_10]
0x18000a700  mov     r13d, r8d
0x18000a703  lea     rcx, [r8+r8*4]
0x18000a707  mov     dword ptr [rsi+rcx*4+10h], 1
0x18000a70f  mov     eax, [rsi+r15*4+0Ch]
0x18000a714  mov     [rsi+rcx*4+0Ch], eax
0x18000a718  cmp     r8d, 0FFFFFFFFh
0x18000a71c  jz      short loc_18000A724
0x18000a71e  cmp     r14d, 0FFFFFFFFh
0x18000a722  jz      short loc_18000A74B
0x18000a724  mov     edx, [rbp+var_10]
0x18000a727  lea     rcx, [rbp+arg_10]
0x18000a72b  mov     r9, rbx
0x18000a72e  mov     r8d, r14d
0x18000a731  call    BcreateEndNode
0x18000a736  test    eax, eax
0x18000a738  jz      loc_18000A534
0x18000a73e  mov     r8d, [rbp+arg_10]
0x18000a742  lea     rcx, [r8+r8*4]
0x18000a746  mov     [rsi+rcx*4+8], r13d
0x18000a74b  mov     r13d, [rbp+var_10]
0x18000a74f  mov     dword ptr [rsi+r15*4+10h], 0
0x18000a758  mov     [rsi+r15*4+0Ch], r8d
0x18000a75d  jmp     loc_18000A5C4
0x18000a762  mov     eax, [rbp+arg_18]
0x18000a765  jmp     loc_18000A4B2
0x18000a76a  bts     dword ptr [rdi], 1Fh
0x18000a76e  jmp     loc_18000A501
0x18000a773  test    eax, eax
0x18000a775  jns     short loc_18000A797
0x18000a777  btr     eax, 1Fh
0x18000a77b  mov     r9, rbx
0x18000a77e  mov     r8d, 1
0x18000a784  mov     [rdi], eax
0x18000a786  mov     rdx, r12
0x18000a789  mov     rcx, rdi
0x18000a78c  call    BaddValueToHeap
0x18000a791  bts     dword ptr [rdi], 1Fh
0x18000a795  jmp     short loc_18000A7BA
0x18000a797  lea     rcx, [rax+rax*4]
0x18000a79b  cmp     dword ptr [rsi+rcx*4], 0FFFFFFFFh
0x18000a79f  jnz     short loc_18000A7C7
0x18000a7a1  add     rcx, 3
0x18000a7a5  mov     r9, rbx
0x18000a7a8  mov     r8d, 1
0x18000a7ae  mov     rdx, r12
0x18000a7b1  lea     rcx, [rsi+rcx*4]
0x18000a7b5  call    BaddValueToHeap
0x18000a7ba  test    eax, eax
0x18000a7bc  jz      loc_18000A534
0x18000a7c2  jmp     loc_18000A501
0x18000a7c7  mov     r8, rbx
0x18000a7ca  lea     rcx, [rbp+arg_10]
0x18000a7ce  xor     edx, edx
0x18000a7d0  call    BcreateGlobalInitializerNode
0x18000a7d5  test    eax, eax
0x18000a7d7  jz      loc_18000A534
0x18000a7dd  mov     r14d, [rbp+arg_10]
0x18000a7e1  mov     r9, rbx
0x18000a7e4  xor     r8d, r8d
0x18000a7e7  mov     rdx, r12
0x18000a7ea  lea     r15, [r14+r14*4]
0x18000a7ee  lea     rcx, [r15+3]
0x18000a7f2  lea     rcx, [rsi+rcx*4]
0x18000a7f6  call    BaddValueToHeap
0x18000a7fb  test    eax, eax
0x18000a7fd  jnz     short loc_18000A812
0x18000a7ff  mov     r8, rbx
0x18000a802  lea     ecx, [rax+3]
0x18000a805  mov     edx, r14d
0x18000a808  call    BreturnElementFromMasterTable
0x18000a80d  jmp     loc_18000A534
0x18000a812  mov     ecx, [rdi]
0x18000a814  mov     [rsi+r15*4+8], ecx
0x18000a819  mov     [rdi], r14d
0x18000a81c  jmp     loc_18000A501
```
