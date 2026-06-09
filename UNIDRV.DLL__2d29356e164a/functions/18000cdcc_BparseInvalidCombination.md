# BparseInvalidCombination

- ea: `0x18000cdcc`
- end: `0x18000d0cb`
- name: `BparseInvalidCombination`
- size: `767`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180070d04`

## callees

- `0x180007220`
- `0x18000a0b8`
- `0x18000a97c`
- `0x18000aa88`
- `0x18000b09c`
- `0x18000c39c`
- `0x18000cdcc`

## string_xrefs

- `0x18000d09e`: `Must have at least 2 objects to define an InvalidCombination.`
- `0x18000d0a5`: `BparseInvalidCombination`
- `0x18000cfe1`: `Internal parser error.  BexchangeDataInFOATNode should never create a branchless node.`

## pseudocode

```c
__int64 __fastcall BparseInvalidCombination(int a1, unsigned int a2, _QWORD *a3)
{
  __int64 v3; // r13
  int v4; // r12d
  __int64 v5; // rdi
  __int64 v7; // rbx
  __int64 v8; // r15
  int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 result; // rax
  unsigned int v16; // r14d
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rbx
  int *v24; // r13
  int v25; // ecx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rbx
  unsigned int v29; // eax
  unsigned int v30; // [rsp+50h] [rbp-20h] BYREF
  __int64 v31; // [rsp+58h] [rbp-18h]
  __int64 v32; // [rsp+60h] [rbp-10h]
  __int64 v33; // [rsp+68h] [rbp-8h]
  unsigned int v34; // [rsp+C0h] [rbp+50h] BYREF
  unsigned int v35; // [rsp+C8h] [rbp+58h] BYREF

  v3 = a3[27];
  v4 = 0;
  v5 = a3[21];
  v7 = a2;
  v35 = 0;
  v34 = 0;
  v30 = 0;
  v31 = v3;
  if ( !(unsigned int)BparseList(a1, (unsigned int)&v34, (unsigned int)BparseQualifiedName, 4, (__int64)a3) )
    return 0;
  v8 = v34;
  v9 = 1;
  LODWORD(v10) = v34;
  if ( *(_DWORD *)(v5 + 8LL * v34 + 4) == -1 )
    goto LABEL_34;
  do
  {
    ++v9;
    v10 = *(unsigned int *)(v5 + 8LL * (unsigned int)v10 + 4);
  }
  while ( *(_DWORD *)(v5 + 8 * v10 + 4) != -1 );
  if ( v9 == 1 )
  {
LABEL_34:
    WriteDbgTraceErrorGpd("BparseInvalidCombination", "Must have at least 2 objects to define an InvalidCombination.");
    return 0;
  }
  if ( v9 == 2 )
  {
    v34 = 0;
    v30 = 0;
    if ( !(unsigned int)BallocElementFromMasterTable(8, &v34, a3) )
      return 0;
    v11 = a3[24];
    if ( !(unsigned int)BexchangeArbDataInFOATNode(
                          *(unsigned __int16 *)(v5 + 8 * v8),
                          *(unsigned __int16 *)(v5 + 8 * v8 + 2),
                          136) )
      return 0;
    v12 = v34;
    if ( v35 )
      *(_DWORD *)(v11 + 12LL * v34) = v30;
    else
      *(_DWORD *)(v11 + 12LL * v34) = -1;
    v13 = *(unsigned int *)(v5 + 8 * v8 + 4);
    v14 = 3 * v12;
    result = 1;
    *(_DWORD *)(v11 + 4 * v14 + 4) = *(unsigned __int16 *)(v5 + 8 * v13);
    *(_DWORD *)(v11 + 4 * v14 + 8) = *(unsigned __int16 *)(v5 + 8 * v13 + 2);
    return result;
  }
  v16 = BallocElementFromMasterTable(9, &v30, a3);
  LODWORD(v17) = v30;
  v34 = v30;
  if ( !v16 )
    return 0;
  v18 = v7;
  v33 = v7;
  while ( 1 )
  {
    if ( *(_WORD *)(v5 + 8 * v8 + 2) == 0xFFFF )
      *(_WORD *)(v5 + 8 * v8 + 2) = -1;
    v19 = (unsigned int)v17;
    v20 = *(unsigned __int16 *)(v5 + 8 * v8);
    v19 *= 16;
    v35 = 0;
    v32 = v19;
    *(_DWORD *)(v19 + v3) = v20;
    *(_DWORD *)(v19 + v3 + 4) = *(unsigned __int16 *)(v5 + 8 * v8 + 2);
    v21 = *(unsigned __int16 *)(v5 + 8 * v8);
    v22 = *(unsigned __int16 *)(v5 + 8 * v8 + 2);
    v23 = a3[9];
    v24 = (int *)(v18 + a3[33] + 396 * v21);
    v25 = *v24;
    if ( *v24 == 0x7FFFFFFF )
    {
      if ( !(unsigned int)BcreateEndNode(v24, v21, v22, a3) )
        goto LABEL_26;
      *(_DWORD *)(v23 + 20LL * (unsigned int)*v24 + 12) = v34;
      v26 = 5LL * (unsigned int)*v24;
    }
    else
    {
      if ( v25 < 0 )
      {
        WriteDbgTraceErrorGpd(
          "BexchangeDataInFOATNode",
          "Internal parser error.  BexchangeDataInFOATNode should never create a branchless node.",
          v22);
        goto LABEL_28;
      }
      if ( !(unsigned int)BfindOrCreateMatchingNode(v25, (unsigned int)&v35, v21, v22, (__int64)a3) )
        goto LABEL_26;
      v26 = 5LL * v35;
      if ( *(_DWORD *)(v23 + 20LL * v35 + 16) == 1 )
      {
        v4 = *(_DWORD *)(v23 + 20LL * v35 + 12);
        *(_DWORD *)(v23 + 20LL * v35 + 12) = v34;
LABEL_26:
        if ( v4 != -1 )
          goto LABEL_28;
        goto LABEL_27;
      }
      *(_DWORD *)(v23 + 20LL * v35 + 12) = v34;
    }
    *(_DWORD *)(v23 + 4 * v26 + 16) = 1;
LABEL_27:
    v4 = -1;
LABEL_28:
    v3 = v31;
    v27 = v32;
    *(_DWORD *)(v32 + v31 + 12) = v4;
    v8 = *(unsigned int *)(v5 + 8 * v8 + 4);
    if ( (_DWORD)v8 == -1 )
      break;
    v28 = v27 + v3;
    v29 = BallocElementFromMasterTable(9, v27 + v3 + 8, a3);
    v18 = v33;
    v16 = v29;
    v17 = *(unsigned int *)(v28 + 8);
    v4 = 0;
    v30 = *(_DWORD *)(v28 + 8);
    if ( !v16 )
      goto LABEL_32;
  }
  v17 = v30;
LABEL_32:
  if ( v16 )
  {
    *(_DWORD *)(v3 + 16 * v17 + 8) = -1;
    return v16;
  }
  return 0;
}

```

## disassembly

```asm
0x18000cdcc  mov     [rsp-38h+arg_0], rbx
0x18000cdd1  push    rbp
0x18000cdd2  push    rsi
0x18000cdd3  push    rdi
0x18000cdd4  push    r12
0x18000cdd6  push    r13
0x18000cdd8  push    r14
0x18000cdda  push    r15
0x18000cddc  mov     rbp, rsp
0x18000cddf  sub     rsp, 70h
0x18000cde3  mov     r13, [r8+0D8h]
0x18000cdea  xor     r12d, r12d
0x18000cded  mov     rdi, [r8+0A8h]
0x18000cdf4  mov     rsi, r8
0x18000cdf7  mov     ebx, edx
0x18000cdf9  lea     rdx, [rbp+arg_10]
0x18000cdfd  mov     [rsp+70h+var_50], r8
0x18000ce02  lea     r8, BparseQualifiedName
0x18000ce09  lea     r9d, [r12+4]
0x18000ce0e  mov     [rbp+arg_18], r12d
0x18000ce12  mov     [rbp+arg_10], r12d
0x18000ce16  mov     [rbp+var_20], r12d
0x18000ce1a  mov     [rbp+var_18], r13
0x18000ce1e  call    BparseList
0x18000ce23  test    eax, eax
0x18000ce25  jz      loc_18000D0B1
0x18000ce2b  mov     r15d, [rbp+arg_10]
0x18000ce2f  lea     ecx, [r12+1]
0x18000ce34  or      r8d, 0FFFFFFFFh
0x18000ce38  mov     edx, r15d
0x18000ce3b  cmp     [rdi+r15*8+4], r8d
0x18000ce40  jz      loc_18000D09E
0x18000ce46  mov     eax, edx
0x18000ce48  inc     ecx
0x18000ce4a  mov     edx, [rdi+rax*8+4]
0x18000ce4e  cmp     [rdi+rdx*8+4], r8d
0x18000ce53  jnz     short loc_18000CE46
0x18000ce55  cmp     ecx, 1
0x18000ce58  jz      loc_18000D09E
0x18000ce5e  mov     r8, rsi
0x18000ce61  cmp     ecx, 2
0x18000ce64  jnz     loc_18000CF1F
0x18000ce6a  lea     rdx, [rbp+arg_10]
0x18000ce6e  mov     [rbp+arg_10], r12d
0x18000ce72  mov     ecx, 8
0x18000ce77  mov     [rbp+var_20], r12d
0x18000ce7b  call    BallocElementFromMasterTable
0x18000ce80  test    eax, eax
0x18000ce82  jz      loc_18000D0B1
0x18000ce88  movzx   edx, word ptr [rdi+r15*8+2]
0x18000ce8e  lea     rax, [rbp+arg_18]
0x18000ce92  movzx   ecx, word ptr [rdi+r15*8]
0x18000ce97  mov     r9d, 4
0x18000ce9d  mov     rbx, [rsi+0C0h]
0x18000cea4  mov     r8d, 88h
0x18000ceaa  mov     [rsp+70h+var_30], rsi
0x18000ceaf  mov     [rsp+70h+var_38], r12d
0x18000ceb4  mov     [rsp+70h+var_40], rax
0x18000ceb9  lea     rax, [rbp+arg_10]
0x18000cebd  mov     [rsp+70h+var_48], rax
0x18000cec2  lea     rax, [rbp+var_20]
0x18000cec6  mov     [rsp+70h+var_50], rax
0x18000cecb  call    BexchangeArbDataInFOATNode
0x18000ced0  test    eax, eax
0x18000ced2  jz      loc_18000D0B1
0x18000ced8  mov     r9d, [rbp+arg_10]
0x18000cedc  cmp     [rbp+arg_18], r12d
0x18000cee0  jz      short loc_18000CEEE
0x18000cee2  mov     eax, [rbp+var_20]
0x18000cee5  lea     rcx, [r9+r9*2]
0x18000cee9  mov     [rbx+rcx*4], eax
0x18000ceec  jmp     short loc_18000CEF9
0x18000ceee  lea     rdx, [r9+r9*2]
0x18000cef2  mov     dword ptr [rbx+rdx*4], 0FFFFFFFFh
0x18000cef9  mov     r8d, [rdi+r15*8+4]
0x18000cefe  lea     rdx, [r9+r9*2]
0x18000cf02  mov     eax, 1
0x18000cf07  movzx   ecx, word ptr [rdi+r8*8]
0x18000cf0c  mov     [rbx+rdx*4+4], ecx
0x18000cf10  movzx   ecx, word ptr [rdi+r8*8+2]
0x18000cf16  mov     [rbx+rdx*4+8], ecx
0x18000cf1a  jmp     loc_18000D0B3
0x18000cf1f  lea     rdx, [rbp+var_20]
0x18000cf23  mov     ecx, 9
0x18000cf28  call    BallocElementFromMasterTable
0x18000cf2d  mov     r14d, eax
0x18000cf30  mov     eax, [rbp+var_20]
0x18000cf33  mov     [rbp+arg_10], eax
0x18000cf36  mov     [rbp+var_20], eax
0x18000cf39  test    r14d, r14d
0x18000cf3c  jz      loc_18000D0B1
0x18000cf42  mov     r9, rbx
0x18000cf45  mov     [rbp+var_8], rbx
0x18000cf49  mov     ecx, 0FFFFh
0x18000cf4e  cmp     [rdi+r15*8+2], cx
0x18000cf54  jnz     short loc_18000CF5C
0x18000cf56  mov     [rdi+r15*8+2], cx
0x18000cf5c  mov     ecx, eax
0x18000cf5e  movzx   eax, word ptr [rdi+r15*8]
0x18000cf63  shl     rcx, 4
0x18000cf67  mov     [rbp+arg_18], 0
0x18000cf6e  mov     [rbp+var_10], rcx
0x18000cf72  mov     [rcx+r13], eax
0x18000cf76  movzx   eax, word ptr [rdi+r15*8+2]
0x18000cf7c  mov     [rcx+r13+4], eax
0x18000cf81  movzx   edx, word ptr [rdi+r15*8]
0x18000cf86  movzx   r8d, word ptr [rdi+r15*8+2]
0x18000cf8c  mov     rbx, [rsi+48h]
0x18000cf90  imul    r13, rdx, 18Ch
0x18000cf97  add     r13, [rsi+108h]
0x18000cf9e  add     r13, r9
0x18000cfa1  mov     ecx, [r13+0]
0x18000cfa5  cmp     ecx, 7FFFFFFFh
0x18000cfab  jnz     short loc_18000CFDD
0x18000cfad  mov     r9, rsi
0x18000cfb0  mov     rcx, r13
0x18000cfb3  call    BcreateEndNode
0x18000cfb8  test    eax, eax
0x18000cfba  jz      short loc_18000D02E
0x18000cfbc  mov     eax, [r13+0]
0x18000cfc0  lea     rcx, [rax+rax*4]
0x18000cfc4  mov     eax, [rbp+arg_10]
0x18000cfc7  mov     [rbx+rcx*4+0Ch], eax
0x18000cfcb  mov     eax, [r13+0]
0x18000cfcf  lea     rcx, [rax+rax*4]
0x18000cfd3  mov     dword ptr [rbx+rcx*4+10h], 1
0x18000cfdb  jmp     short loc_18000D034
0x18000cfdd  test    ecx, ecx
0x18000cfdf  jns     short loc_18000CFF6
0x18000cfe1  lea     rdx, aInternalParser; "Internal parser error.  BexchangeDataIn"...
0x18000cfe8  lea     rcx, aBexchangedatai; "BexchangeDataInFOATNode"
0x18000cfef  call    WriteDbgTraceErrorGpd
0x18000cff4  jmp     short loc_18000D038
0x18000cff6  mov     r9d, r8d
0x18000cff9  mov     [rsp+70h+var_50], rsi
0x18000cffe  mov     r8d, edx
0x18000d001  lea     rdx, [rbp+arg_18]
0x18000d005  call    BfindOrCreateMatchingNode
0x18000d00a  test    eax, eax
0x18000d00c  jz      short loc_18000D02E
0x18000d00e  mov     eax, [rbp+arg_18]
0x18000d011  lea     rcx, [rax+rax*4]
0x18000d015  mov     eax, [rbp+arg_10]
0x18000d018  cmp     dword ptr [rbx+rcx*4+10h], 1
0x18000d01d  jz      short loc_18000D025
0x18000d01f  mov     [rbx+rcx*4+0Ch], eax
0x18000d023  jmp     short loc_18000CFD3
0x18000d025  mov     r12d, [rbx+rcx*4+0Ch]
0x18000d02a  mov     [rbx+rcx*4+0Ch], eax
0x18000d02e  cmp     r12d, 0FFFFFFFFh
0x18000d032  jnz     short loc_18000D038
0x18000d034  or      r12d, 0FFFFFFFFh
0x18000d038  mov     r13, [rbp+var_18]
0x18000d03c  mov     rax, [rbp+var_10]
0x18000d040  mov     [rax+r13+0Ch], r12d
0x18000d045  mov     r15d, [rdi+r15*8+4]
0x18000d04a  cmp     r15d, 0FFFFFFFFh
0x18000d04e  jz      short loc_18000D085
0x18000d050  lea     rbx, [rax+r13]
0x18000d054  mov     r8, rsi
0x18000d057  lea     rdx, [rbx+8]
0x18000d05b  mov     ecx, 9
0x18000d060  call    BallocElementFromMasterTable
0x18000d065  mov     r9, [rbp+var_8]
0x18000d069  mov     r14d, eax
0x18000d06c  mov     eax, [rbx+8]
0x18000d06f  xor     r12d, r12d
0x18000d072  mov     [rbp+var_20], eax
0x18000d075  mov     ecx, 0FFFFh
0x18000d07a  test    r14d, r14d
0x18000d07d  jnz     loc_18000CF4E
0x18000d083  jmp     short loc_18000D088
0x18000d085  mov     eax, [rbp+var_20]
0x18000d088  test    r14d, r14d
0x18000d08b  jz      short loc_18000D0B1
0x18000d08d  add     rax, rax
0x18000d090  mov     dword ptr [r13+rax*8+8], 0FFFFFFFFh
0x18000d099  mov     eax, r14d
0x18000d09c  jmp     short loc_18000D0B3
0x18000d09e  lea     rdx, aMustHaveAtLeas_0; "Must have at least 2 objects to define "...
0x18000d0a5  lea     rcx, aBparseinvalidc; "BparseInvalidCombination"
0x18000d0ac  call    WriteDbgTraceErrorGpd
0x18000d0b1  xor     eax, eax
0x18000d0b3  mov     rbx, [rsp+70h+arg_0]
0x18000d0bb  add     rsp, 70h
0x18000d0bf  pop     r15
0x18000d0c1  pop     r14
0x18000d0c3  pop     r13
0x18000d0c5  pop     r12
0x18000d0c7  pop     rdi
0x18000d0c8  pop     rsi
0x18000d0c9  pop     rbp
0x18000d0ca  retn
```
