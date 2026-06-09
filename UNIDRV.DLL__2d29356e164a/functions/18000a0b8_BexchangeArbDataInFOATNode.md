# BexchangeArbDataInFOATNode

- ea: `0x18000a0b8`
- end: `0x18000a2d0`
- name: `BexchangeArbDataInFOATNode`
- size: `536`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x18000cdcc`
- `0x18004165c`
- `0x180041eec`
- `0x1800715e0`

## callees

- `0x180007220`
- `0x18000a0b8`
- `0x18000a97c`
- `0x18000aef4`
- `0x18000c39c`
- `0x180072a54`
- `0x180074580`

## string_xrefs

- `0x18000a1aa`: `Internal error.  BexchangeArbDataInFOATNode should never create a branchless node.`

## pseudocode

```c
__int64 __fastcall BexchangeArbDataInFOATNode(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        void *a5,
        const void *a6,
        _DWORD *a7,
        signed int a8,
        __int64 a9)
{
  _QWORD *v9; // rdi
  size_t v10; // r12
  __int64 v12; // rcx
  int v13; // r10d
  __int64 v14; // rcx
  __int64 v16; // rbp
  signed int *v17; // rsi
  signed int v18; // ecx
  int v19; // r8d
  __int64 v20; // r14
  __int64 v21; // rsi
  void *v22; // rcx
  const void *v23; // rdx

  v9 = (_QWORD *)a9;
  v10 = a4;
  v12 = 396LL * a1;
  if ( a8 )
    v13 = *(_DWORD *)(a9 + 272);
  else
    v13 = 0;
  v14 = *(_QWORD *)((a8 != 0 ? 0x18 : 0) + a9 + 264) + v12;
  if ( !v14 )
  {
    WriteDbgTraceErrorGpd(
      "BexchangeArbDataInFOATNode",
      "Internal error.  BexchangeArbDataInFOATNode found no FEATURE_OPTIONS structs.");
    return 0;
  }
  v16 = *(_QWORD *)(a9 + 72);
  v17 = (signed int *)(v14 + a3);
  v18 = *v17;
  a8 = v18;
  if ( v18 == 0x7FFFFFFF )
  {
    if ( a6 )
    {
      if ( !(unsigned int)BcreateEndNode(v17, v13 + a1, a2, a9)
        || !(unsigned int)BwriteToHeap(
                            (_DWORD *)(v16 + 4 * ((unsigned int)*v17 + 4LL * (unsigned int)*v17 + 3)),
                            a6,
                            v10,
                            4u,
                            (__int64)v9) )
      {
        return 0;
      }
      *(_DWORD *)(v16 + 20LL * (unsigned int)*v17 + 16) = 1;
    }
    goto LABEL_23;
  }
  if ( v18 < 0 )
  {
    WriteDbgTraceErrorGpd(
      "BexchangeArbDataInFOATNode",
      "Internal error.  BexchangeArbDataInFOATNode should never create a branchless node.");
    return 0;
  }
  v19 = v13 + a1;
  if ( !a6 )
  {
    if ( !(unsigned int)BfindMatchingNode(v18, (unsigned int)&a8, v19, a2, a9) )
    {
LABEL_23:
      *a7 = 0;
      return 1;
    }
    v22 = a5;
    if ( !a5 )
    {
LABEL_27:
      *a7 = 1;
      return 1;
    }
    v23 = (const void *)(*v9 + *(unsigned int *)(v16 + 20LL * (unsigned int)a8 + 12));
LABEL_26:
    memcpy_0(v22, v23, v10);
    goto LABEL_27;
  }
  if ( !(unsigned int)BfindOrCreateMatchingNode(v18, (unsigned int *)&a8, v19, a2, a9) )
    return 0;
  v20 = 5LL * (unsigned int)a8;
  v21 = 20LL * (unsigned int)a8;
  if ( *(_DWORD *)(v16 + v21 + 16) == 1 )
  {
    if ( a5 )
      memcpy_0(a5, (const void *)(*v9 + *(unsigned int *)(v21 + v16 + 12)), v10);
    v22 = (void *)(*v9 + *(unsigned int *)(v21 + v16 + 12));
    v23 = a6;
    goto LABEL_26;
  }
  if ( !(unsigned int)BwriteToHeap((_DWORD *)(v21 + v16 + 12), a6, v10, 4u, (__int64)v9) )
    return 0;
  *(_DWORD *)(v16 + 4 * v20 + 16) = 1;
  *a7 = 0;
  return 1;
}

```

## disassembly

```asm
0x18000a0b8  push    rbp
0x18000a0ba  push    rsi
0x18000a0bb  push    rdi
0x18000a0bc  push    r12
0x18000a0be  push    r14
0x18000a0c0  sub     rsp, 30h
0x18000a0c4  mov     eax, [rsp+58h+arg_38]
0x18000a0cb  mov     r11d, edx
0x18000a0ce  mov     rdi, [rsp+58h+arg_40]
0x18000a0d6  mov     r12d, r9d
0x18000a0d9  mov     r9d, ecx
0x18000a0dc  imul    rcx, r9, 18Ch
0x18000a0e3  test    eax, eax
0x18000a0e5  jz      short loc_18000A0F0
0x18000a0e7  mov     r10d, [rdi+110h]
0x18000a0ee  jmp     short loc_18000A0F3
0x18000a0f0  xor     r10d, r10d
0x18000a0f3  neg     eax
0x18000a0f5  sbb     rax, rax
0x18000a0f8  and     eax, 18h
0x18000a0fb  add     rcx, [rax+rdi+108h]
0x18000a103  jnz     short loc_18000A11F
0x18000a105  lea     rdx, aInternalErrorB_1; "Internal error.  BexchangeArbDataInFOAT"...
0x18000a10c  lea     rcx, aBexchangearbda; "BexchangeArbDataInFOATNode"
0x18000a113  call    WriteDbgTraceErrorGpd
0x18000a118  xor     eax, eax
0x18000a11a  jmp     loc_18000A2C4
0x18000a11f  mov     rbp, [rdi+48h]
0x18000a123  mov     esi, r8d
0x18000a126  add     rsi, rcx
0x18000a129  mov     ecx, [rsi]
0x18000a12b  mov     [rsp+58h+arg_38], ecx
0x18000a132  cmp     ecx, 7FFFFFFFh
0x18000a138  jnz     short loc_18000A1A6
0x18000a13a  mov     r14, [rsp+58h+arg_28]
0x18000a142  test    r14, r14
0x18000a145  jz      loc_18000A27A
0x18000a14b  lea     edx, [r10+r9]
0x18000a14f  mov     r8d, r11d
0x18000a152  mov     r9, rdi
0x18000a155  mov     rcx, rsi
0x18000a158  call    BcreateEndNode
0x18000a15d  test    eax, eax
0x18000a15f  jz      short loc_18000A118
0x18000a161  mov     eax, [rsi]
0x18000a163  mov     r9d, 4
0x18000a169  mov     r8d, r12d
0x18000a16c  mov     [rsp+58h+var_38], rdi
0x18000a171  mov     rdx, r14
0x18000a174  lea     rcx, ds:3[rax*4]
0x18000a17c  add     rcx, rax
0x18000a17f  lea     rcx, ds:0[rcx*4]
0x18000a187  add     rcx, rbp
0x18000a18a  call    BwriteToHeap
0x18000a18f  test    eax, eax
0x18000a191  jz      short loc_18000A118
0x18000a193  mov     eax, [rsi]
0x18000a195  lea     rcx, [rax+rax*4]
0x18000a199  mov     dword ptr [rbp+rcx*4+10h], 1
0x18000a1a1  jmp     loc_18000A27A
0x18000a1a6  test    ecx, ecx
0x18000a1a8  jns     short loc_18000A1B6
0x18000a1aa  lea     rdx, aInternalErrorB_2; "Internal error.  BexchangeArbDataInFOAT"...
0x18000a1b1  jmp     loc_18000A10C
0x18000a1b6  cmp     [rsp+58h+arg_28], 0
0x18000a1bf  lea     r8d, [r10+r9]
0x18000a1c3  mov     r9d, r11d
0x18000a1c6  mov     [rsp+58h+var_38], rdi
0x18000a1cb  lea     rdx, [rsp+58h+arg_38]
0x18000a1d3  jz      loc_18000A271
0x18000a1d9  call    BfindOrCreateMatchingNode
0x18000a1de  test    eax, eax
0x18000a1e0  jz      loc_18000A118
0x18000a1e6  mov     eax, [rsp+58h+arg_38]
0x18000a1ed  lea     r14, [rax+rax*4]
0x18000a1f1  cmp     dword ptr [rbp+r14*4+10h], 1
0x18000a1f7  lea     rsi, ds:0[r14*4]
0x18000a1ff  jz      short loc_18000A244
0x18000a201  mov     rdx, [rsp+58h+arg_28]
0x18000a209  lea     rcx, [rbp+0Ch]
0x18000a20d  add     rcx, rsi
0x18000a210  mov     [rsp+58h+var_38], rdi
0x18000a215  mov     r9d, 4
0x18000a21b  mov     r8d, r12d
0x18000a21e  call    BwriteToHeap
0x18000a223  test    eax, eax
0x18000a225  jz      loc_18000A118
0x18000a22b  mov     rcx, [rsp+58h+arg_30]
0x18000a233  mov     dword ptr [rbp+r14*4+10h], 1
0x18000a23c  mov     dword ptr [rcx], 0
0x18000a242  jmp     short loc_18000A2BF
0x18000a244  mov     rcx, [rsp+58h+arg_20]; void *
0x18000a24c  test    rcx, rcx
0x18000a24f  jz      short loc_18000A260
0x18000a251  mov     edx, [rsi+rbp+0Ch]
0x18000a255  mov     r8, r12; Size
0x18000a258  add     rdx, [rdi]; Src
0x18000a25b  call    memcpy_0
0x18000a260  mov     ecx, [rsi+rbp+0Ch]
0x18000a264  add     rcx, [rdi]
0x18000a267  mov     rdx, [rsp+58h+arg_28]
0x18000a26f  jmp     short loc_18000A2A9
0x18000a271  call    BfindMatchingNode
0x18000a276  test    eax, eax
0x18000a278  jnz     short loc_18000A28A
0x18000a27a  mov     rax, [rsp+58h+arg_30]
0x18000a282  mov     dword ptr [rax], 0
0x18000a288  jmp     short loc_18000A2BF
0x18000a28a  mov     rcx, [rsp+58h+arg_20]; void *
0x18000a292  test    rcx, rcx
0x18000a295  jz      short loc_18000A2B1
0x18000a297  mov     eax, [rsp+58h+arg_38]
0x18000a29e  lea     rdx, [rax+rax*4]
0x18000a2a2  mov     edx, [rbp+rdx*4+0Ch]
0x18000a2a6  add     rdx, [rdi]; Src
0x18000a2a9  mov     r8, r12; Size
0x18000a2ac  call    memcpy_0
0x18000a2b1  mov     rax, [rsp+58h+arg_30]
0x18000a2b9  mov     dword ptr [rax], 1
0x18000a2bf  mov     eax, 1
0x18000a2c4  add     rsp, 30h
0x18000a2c8  pop     r14
0x18000a2ca  pop     r12
0x18000a2cc  pop     rdi
0x18000a2cd  pop     rsi
0x18000a2ce  pop     rbp
0x18000a2cf  retn
```
