# BparseInvalidCombination

- ea: `0x18000ce0c`
- end: `0x18000d10c`
- name: `BparseInvalidCombination`
- size: `768`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180072d78`

## callees

- `0x180007150`
- `0x18000a0b0`
- `0x18000a97c`
- `0x18000aa88`
- `0x18000b0ac`
- `0x18000c390`
- `0x18000ce0c`

## string_xrefs

- `0x18000d0de`: `Must have at least 2 objects to define an InvalidCombination.`
- `0x18000d0e5`: `BparseInvalidCombination`
- `0x18000d021`: `Internal parser error.  BexchangeDataInFOATNode should never create a branchless node.`

## pseudocode

```c
__int64 __fastcall BparseInvalidCombination(__int64 a1, unsigned int a2, _QWORD *a3)
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
  unsigned int *v24; // r13
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
  if ( !(unsigned int)BparseList(
                        a1,
                        (int *)&v34,
                        (unsigned int (__fastcall *)(__int128 *, __int64, _QWORD, __int64))BparseQualifiedName,
                        4u,
                        (__int64)a3) )
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
    WriteDbgTraceErrorGpd(
      (__int64)"BparseInvalidCombination",
      "Must have at least 2 objects to define an InvalidCombination.");
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
                          0x88u,
                          4u,
                          &v30,
                          &v34,
                          &v35,
                          0,
                          (__int64)a3) )
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
    v24 = (unsigned int *)(v18 + a3[33] + 396 * v21);
    v25 = *v24;
    if ( *v24 == 0x7FFFFFFF )
    {
      if ( !(unsigned int)BcreateEndNode(v24, v21, v22, (__int64)a3) )
        goto LABEL_26;
      *(_DWORD *)(v23 + 20LL * *v24 + 12) = v34;
      v26 = 5LL * *v24;
    }
    else
    {
      if ( v25 < 0 )
      {
        WriteDbgTraceErrorGpd(
          (__int64)"BexchangeDataInFOATNode",
          "Internal parser error.  BexchangeDataInFOATNode should never create a branchless node.",
          v22);
        goto LABEL_28;
      }
      if ( !(unsigned int)BfindOrCreateMatchingNode(v25, &v35, v21, v22, (__int64)a3) )
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
    v29 = BallocElementFromMasterTable(9, (unsigned int *)(v27 + v3 + 8), a3);
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
0x18000ce0c  mov     [rsp-38h+arg_0], rbx
0x18000ce11  push    rbp
0x18000ce12  push    rsi
0x18000ce13  push    rdi
0x18000ce14  push    r12
0x18000ce16  push    r13
0x18000ce18  push    r14
0x18000ce1a  push    r15
0x18000ce1c  mov     rbp, rsp
0x18000ce1f  sub     rsp, 70h
0x18000ce23  mov     r13, [r8+0D8h]
0x18000ce2a  xor     r12d, r12d
0x18000ce2d  mov     rdi, [r8+0A8h]
0x18000ce34  mov     rsi, r8
0x18000ce37  mov     ebx, edx
0x18000ce39  lea     rdx, [rbp+arg_10]
0x18000ce3d  mov     [rsp+70h+var_50], r8
0x18000ce42  lea     r8, BparseQualifiedName
0x18000ce49  lea     r9d, [r12+4]
0x18000ce4e  mov     [rbp+arg_18], r12d
0x18000ce52  mov     [rbp+arg_10], r12d
0x18000ce56  mov     [rbp+var_20], r12d
0x18000ce5a  mov     [rbp+var_18], r13
0x18000ce5e  call    BparseList
0x18000ce63  test    eax, eax
0x18000ce65  jz      loc_18000D0F1
0x18000ce6b  mov     r15d, [rbp+arg_10]
0x18000ce6f  lea     ecx, [r12+1]
0x18000ce74  or      r8d, 0FFFFFFFFh
0x18000ce78  mov     edx, r15d
0x18000ce7b  cmp     [rdi+r15*8+4], r8d
0x18000ce80  jz      loc_18000D0DE
0x18000ce86  mov     eax, edx
0x18000ce88  inc     ecx
0x18000ce8a  mov     edx, [rdi+rax*8+4]
0x18000ce8e  cmp     [rdi+rdx*8+4], r8d
0x18000ce93  jnz     short loc_18000CE86
0x18000ce95  cmp     ecx, 1
0x18000ce98  jz      loc_18000D0DE
0x18000ce9e  mov     r8, rsi
0x18000cea1  cmp     ecx, 2
0x18000cea4  jnz     loc_18000CF5F
0x18000ceaa  lea     rdx, [rbp+arg_10]
0x18000ceae  mov     [rbp+arg_10], r12d
0x18000ceb2  mov     ecx, 8
0x18000ceb7  mov     [rbp+var_20], r12d
0x18000cebb  call    BallocElementFromMasterTable
0x18000cec0  test    eax, eax
0x18000cec2  jz      loc_18000D0F1
0x18000cec8  movzx   edx, word ptr [rdi+r15*8+2]
0x18000cece  lea     rax, [rbp+arg_18]
0x18000ced2  movzx   ecx, word ptr [rdi+r15*8]
0x18000ced7  mov     r9d, 4
0x18000cedd  mov     rbx, [rsi+0C0h]
0x18000cee4  mov     r8d, 88h
0x18000ceea  mov     [rsp+70h+var_30], rsi
0x18000ceef  mov     [rsp+70h+var_38], r12d
0x18000cef4  mov     [rsp+70h+var_40], rax
0x18000cef9  lea     rax, [rbp+arg_10]
0x18000cefd  mov     [rsp+70h+var_48], rax
0x18000cf02  lea     rax, [rbp+var_20]
0x18000cf06  mov     [rsp+70h+var_50], rax
0x18000cf0b  call    BexchangeArbDataInFOATNode
0x18000cf10  test    eax, eax
0x18000cf12  jz      loc_18000D0F1
0x18000cf18  mov     r9d, [rbp+arg_10]
0x18000cf1c  cmp     [rbp+arg_18], r12d
0x18000cf20  jz      short loc_18000CF2E
0x18000cf22  mov     eax, [rbp+var_20]
0x18000cf25  lea     rcx, [r9+r9*2]
0x18000cf29  mov     [rbx+rcx*4], eax
0x18000cf2c  jmp     short loc_18000CF39
0x18000cf2e  lea     rdx, [r9+r9*2]
0x18000cf32  mov     dword ptr [rbx+rdx*4], 0FFFFFFFFh
0x18000cf39  mov     r8d, [rdi+r15*8+4]
0x18000cf3e  lea     rdx, [r9+r9*2]
0x18000cf42  mov     eax, 1
0x18000cf47  movzx   ecx, word ptr [rdi+r8*8]
0x18000cf4c  mov     [rbx+rdx*4+4], ecx
0x18000cf50  movzx   ecx, word ptr [rdi+r8*8+2]
0x18000cf56  mov     [rbx+rdx*4+8], ecx
0x18000cf5a  jmp     loc_18000D0F3
0x18000cf5f  lea     rdx, [rbp+var_20]
0x18000cf63  mov     ecx, 9
0x18000cf68  call    BallocElementFromMasterTable
0x18000cf6d  mov     r14d, eax
0x18000cf70  mov     eax, [rbp+var_20]
0x18000cf73  mov     [rbp+arg_10], eax
0x18000cf76  mov     [rbp+var_20], eax
0x18000cf79  test    r14d, r14d
0x18000cf7c  jz      loc_18000D0F1
0x18000cf82  mov     r9, rbx
0x18000cf85  mov     [rbp+var_8], rbx
0x18000cf89  mov     ecx, 0FFFFh
0x18000cf8e  cmp     [rdi+r15*8+2], cx
0x18000cf94  jnz     short loc_18000CF9C
0x18000cf96  mov     [rdi+r15*8+2], cx
0x18000cf9c  mov     ecx, eax
0x18000cf9e  movzx   eax, word ptr [rdi+r15*8]
0x18000cfa3  shl     rcx, 4
0x18000cfa7  mov     [rbp+arg_18], 0
0x18000cfae  mov     [rbp+var_10], rcx
0x18000cfb2  mov     [rcx+r13], eax
0x18000cfb6  movzx   eax, word ptr [rdi+r15*8+2]
0x18000cfbc  mov     [rcx+r13+4], eax
0x18000cfc1  movzx   edx, word ptr [rdi+r15*8]
0x18000cfc6  movzx   r8d, word ptr [rdi+r15*8+2]
0x18000cfcc  mov     rbx, [rsi+48h]
0x18000cfd0  imul    r13, rdx, 18Ch
0x18000cfd7  add     r13, [rsi+108h]
0x18000cfde  add     r13, r9
0x18000cfe1  mov     ecx, [r13+0]
0x18000cfe5  cmp     ecx, 7FFFFFFFh
0x18000cfeb  jnz     short loc_18000D01D
0x18000cfed  mov     r9, rsi
0x18000cff0  mov     rcx, r13
0x18000cff3  call    BcreateEndNode
0x18000cff8  test    eax, eax
0x18000cffa  jz      short loc_18000D06E
0x18000cffc  mov     eax, [r13+0]
0x18000d000  lea     rcx, [rax+rax*4]
0x18000d004  mov     eax, [rbp+arg_10]
0x18000d007  mov     [rbx+rcx*4+0Ch], eax
0x18000d00b  mov     eax, [r13+0]
0x18000d00f  lea     rcx, [rax+rax*4]
0x18000d013  mov     dword ptr [rbx+rcx*4+10h], 1
0x18000d01b  jmp     short loc_18000D074
0x18000d01d  test    ecx, ecx
0x18000d01f  jns     short loc_18000D036
0x18000d021  lea     rdx, aInternalParser; "Internal parser error.  BexchangeDataIn"...
0x18000d028  lea     rcx, aBexchangedatai; "BexchangeDataInFOATNode"
0x18000d02f  call    WriteDbgTraceErrorGpd
0x18000d034  jmp     short loc_18000D078
0x18000d036  mov     r9d, r8d
0x18000d039  mov     [rsp+70h+var_50], rsi
0x18000d03e  mov     r8d, edx
0x18000d041  lea     rdx, [rbp+arg_18]
0x18000d045  call    BfindOrCreateMatchingNode
0x18000d04a  test    eax, eax
0x18000d04c  jz      short loc_18000D06E
0x18000d04e  mov     eax, [rbp+arg_18]
0x18000d051  lea     rcx, [rax+rax*4]
0x18000d055  mov     eax, [rbp+arg_10]
0x18000d058  cmp     dword ptr [rbx+rcx*4+10h], 1
0x18000d05d  jz      short loc_18000D065
0x18000d05f  mov     [rbx+rcx*4+0Ch], eax
0x18000d063  jmp     short loc_18000D013
0x18000d065  mov     r12d, [rbx+rcx*4+0Ch]
0x18000d06a  mov     [rbx+rcx*4+0Ch], eax
0x18000d06e  cmp     r12d, 0FFFFFFFFh
0x18000d072  jnz     short loc_18000D078
0x18000d074  or      r12d, 0FFFFFFFFh
0x18000d078  mov     r13, [rbp+var_18]
0x18000d07c  mov     rax, [rbp+var_10]
0x18000d080  mov     [rax+r13+0Ch], r12d
0x18000d085  mov     r15d, [rdi+r15*8+4]
0x18000d08a  cmp     r15d, 0FFFFFFFFh
0x18000d08e  jz      short loc_18000D0C5
0x18000d090  lea     rbx, [rax+r13]
0x18000d094  mov     r8, rsi
0x18000d097  lea     rdx, [rbx+8]
0x18000d09b  mov     ecx, 9
0x18000d0a0  call    BallocElementFromMasterTable
0x18000d0a5  mov     r9, [rbp+var_8]
0x18000d0a9  mov     r14d, eax
0x18000d0ac  mov     eax, [rbx+8]
0x18000d0af  xor     r12d, r12d
0x18000d0b2  mov     [rbp+var_20], eax
0x18000d0b5  mov     ecx, 0FFFFh
0x18000d0ba  test    r14d, r14d
0x18000d0bd  jnz     loc_18000CF8E
0x18000d0c3  jmp     short loc_18000D0C8
0x18000d0c5  mov     eax, [rbp+var_20]
0x18000d0c8  test    r14d, r14d
0x18000d0cb  jz      short loc_18000D0F1
0x18000d0cd  add     rax, rax
0x18000d0d0  mov     dword ptr [r13+rax*8+8], 0FFFFFFFFh
0x18000d0d9  mov     eax, r14d
0x18000d0dc  jmp     short loc_18000D0F3
0x18000d0de  lea     rdx, aMustHaveAtLeas_0; "Must have at least 2 objects to define "...
0x18000d0e5  lea     rcx, aBparseinvalidc; "BparseInvalidCombination"
0x18000d0ec  call    WriteDbgTraceErrorGpd
0x18000d0f1  xor     eax, eax
0x18000d0f3  mov     rbx, [rsp+70h+arg_0]
0x18000d0fb  add     rsp, 70h
0x18000d0ff  pop     r15
0x18000d101  pop     r14
0x18000d103  pop     r13
0x18000d105  pop     r12
0x18000d107  pop     rdi
0x18000d108  pop     rsi
0x18000d109  pop     rbp
0x18000d10a  retn
```
