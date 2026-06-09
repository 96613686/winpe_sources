# VsmmMemTrackerpRemoveMemory

- ea: `0x1400a61d4`
- end: `0x1400a66f5`
- name: `VsmmMemTrackerpRemoveMemory`
- size: `1313`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400a58a0`
- `0x1400a66fc`
- `0x1400a67c4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x140007170`
- `0x1400071a4`
- `0x140007dbc`
- `0x14000a010`
- `0x140021c60`
- `0x1400a5f04`
- `0x1400a61d4`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400a64f5`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400a64f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a6509`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a6509`
- `HAL!KeQueryPerformanceCounter` at `0x1400a624a`
- `HAL!KeQueryPerformanceCounter` at `0x1400a669d`
- `HAL!KeQueryPerformanceCounter` at `0x1400a624a`
- `HAL!KeQueryPerformanceCounter` at `0x1400a669d`

## string_xrefs

- `0x1400a6334`: `VsmmMemTrackerpRemoveMemory`
- `0x1400a6540`: `VsmmMemTrackerpRemoveMemory`
- `0x1400a659c`: `VsmmMemTrackerpRemoveMemory`

## pseudocode

```c
unsigned __int64 __fastcall VsmmMemTrackerpRemoveMemory(
        __int64 a1,
        int a2,
        int a3,
        char a4,
        char a5,
        unsigned __int64 a6)
{
  unsigned __int64 v6; // r14
  __int64 v7; // r15
  __int64 v8; // rdx
  unsigned __int64 v9; // rbx
  int v10; // esi
  int v11; // eax
  signed __int64 v12; // r8
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r15
  __int64 v15; // rdi
  char v16; // cl
  signed __int64 v17; // rsi
  bool v18; // zf
  signed __int64 v19; // rax
  unsigned __int64 *v20; // rdi
  unsigned __int64 v21; // rbx
  int v22; // esi
  int v23; // eax
  unsigned __int64 v24; // rax
  void *v25; // rdx
  unsigned __int64 result; // rax
  char v27; // [rsp+30h] [rbp-D0h] BYREF
  char v28; // [rsp+31h] [rbp-CFh] BYREF
  char v29; // [rsp+32h] [rbp-CEh] BYREF
  char v30; // [rsp+33h] [rbp-CDh] BYREF
  char v31; // [rsp+34h] [rbp-CCh]
  int v32; // [rsp+38h] [rbp-C8h] BYREF
  int v33; // [rsp+3Ch] [rbp-C4h]
  int v34; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v38[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v39; // [rsp+68h] [rbp-98h]
  char v40; // [rsp+69h] [rbp-97h]
  __int16 v41; // [rsp+6Ah] [rbp-96h]
  __int128 v42; // [rsp+70h] [rbp-90h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v44[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v45[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v46[16]; // [rsp+C0h] [rbp-40h] BYREF
  int *v47; // [rsp+D0h] [rbp-30h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  __int64 v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h]
  char *v51; // [rsp+F0h] [rbp-10h]
  __int64 v52; // [rsp+F8h] [rbp-8h]
  char *v53; // [rsp+100h] [rbp+0h]
  __int64 v54; // [rsp+108h] [rbp+8h]
  char *v55; // [rsp+110h] [rbp+10h]
  __int64 v56; // [rsp+118h] [rbp+18h]
  char *v57; // [rsp+120h] [rbp+20h]
  __int64 v58; // [rsp+128h] [rbp+28h]
  unsigned __int64 *v59; // [rsp+130h] [rbp+30h]
  __int64 v60; // [rsp+138h] [rbp+38h]

  v36 = a1;
  v6 = a1 + 11920;
  PerformanceFrequency.QuadPart = 0;
  v41 = 0;
  v7 = a1;
  v39 = a5;
  v31 = a4;
  v34 = a3;
  v33 = a2;
  v42 = 0;
  v35 = a1 + 11920;
  v38[0] = a2;
  v38[1] = a3;
  v40 = a4;
  *(LARGE_INTEGER *)&v42 = KeQueryPerformanceCounter(0);
  VidPushLockAcquireShared(v6, v8);
  if ( *(_BYTE *)(v7 + 11948) )
    goto LABEL_54;
  v9 = *(_QWORD *)(v6 + 8);
  if ( (*(_BYTE *)(v6 + 16) & 1) != 0 )
  {
    if ( v9 )
      v9 ^= v6 + 8;
    else
      v9 = 0;
  }
  v10 = *(_BYTE *)(v6 + 16) & 1;
  if ( !v9 )
    goto LABEL_58;
  do
  {
    v11 = VsmmMemTrackerpCompareTreeNodes(v38, v9, 0);
    v12 = 0;
    if ( v11 >= 0 )
    {
      if ( v11 <= 0 )
        break;
      v13 = *(_QWORD *)(v9 + 8);
    }
    else
    {
      v13 = *(_QWORD *)v9;
    }
    if ( v10 && v13 )
      v9 ^= v13;
    else
      v9 = v13;
  }
  while ( v9 );
  if ( !v9 )
  {
LABEL_58:
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_54;
    tlgCreate1Sz_char(v45, "VsmmMemTrackerpRemoveMemory");
    tlgCreate1Sz_char(v46, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtracker.c");
    v32 = 1150;
    v25 = &unk_14004B9A4;
    goto LABEL_53;
  }
  v14 = *(_QWORD *)(v9 + 40);
  v15 = v36;
  v16 = 0;
  do
  {
    if ( a6 <= v14 )
    {
      v17 = v14 - a6;
    }
    else
    {
      if ( !v16 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v45, "VsmmMemTrackerpRemoveMemory");
          tlgCreate1Sz_char(v46, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtracker.c");
          v32 = 1186;
          v47 = &v32;
          v48 = 4;
          v49 = v15 + 656;
          v27 = v33;
          v50 = 16;
          v51 = &v27;
          v28 = v34;
          v53 = &v28;
          v29 = v31;
          v55 = &v29;
          v30 = a5;
          v57 = &v30;
          v59 = &v37;
          v52 = 1;
          v54 = 1;
          v56 = 1;
          v58 = 1;
          v37 = a6;
          v60 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004BA37, 0, 0, 11, v44);
          v12 = 0;
        }
        v16 = 1;
      }
      v17 = v12;
    }
    v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 40), v17, v14);
    v18 = v14 == v19;
    v14 = v19;
  }
  while ( !v18 );
  v6 = v35;
  VidPushLockRelease(v35);
  v20 = (unsigned __int64 *)(v6 + 8);
  if ( !v17 )
  {
    VidPushLockAcquireExclusive(v6);
    v7 = v36;
    if ( *(_BYTE *)(v36 + 11948) )
      goto LABEL_54;
    if ( (*(_BYTE *)(v6 + 16) & 1) != 0 )
    {
      if ( *v20 )
        v21 = *v20 ^ (unsigned __int64)v20;
      else
        v21 = 0;
    }
    else
    {
      v21 = *v20;
    }
    v22 = *(_BYTE *)(v6 + 16) & 1;
    if ( v21 )
    {
      do
      {
        v23 = VsmmMemTrackerpCompareTreeNodes(v38, v21, 0);
        if ( v23 >= 0 )
        {
          if ( v23 <= 0 )
            break;
          v24 = *(_QWORD *)(v21 + 8);
        }
        else
        {
          v24 = *(_QWORD *)v21;
        }
        if ( v22 && v24 )
          v21 ^= v24;
        else
          v21 = v24;
      }
      while ( v21 );
      if ( v21 )
      {
        if ( !*(_QWORD *)(v21 + 40) )
        {
          RtlRbRemoveNode(v6 + 8, v21);
          ExFreePoolWithTag((PVOID)v21, 0x744D6456u);
          --*(_DWORD *)(v6 + 24);
        }
        goto LABEL_54;
      }
    }
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
LABEL_54:
      VidPushLockRelease(v6);
      goto LABEL_55;
    }
    tlgCreate1Sz_char(v45, "VsmmMemTrackerpRemoveMemory");
    tlgCreate1Sz_char(v46, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtracker.c");
    v32 = 1266;
    v25 = &unk_14004BACA;
LABEL_53:
    v50 = 16;
    v47 = &v32;
    v48 = 4;
    v49 = v7 + 656;
    v30 = v33;
    v51 = &v30;
    v29 = v34;
    v53 = &v29;
    v28 = v31;
    v55 = &v28;
    v27 = a5;
    v57 = &v27;
    v35 = a6;
    v59 = &v35;
    v52 = 1;
    v54 = 1;
    v56 = 1;
    v58 = 1;
    v60 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v25, 0, 0, 11, v44);
    goto LABEL_54;
  }
LABEL_55:
  *((LARGE_INTEGER *)&v42 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
  result = 1000000LL * (*((_QWORD *)&v42 + 1) - (_QWORD)v42) / PerformanceFrequency.QuadPart;
  _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v36 + 1528) + 2328LL), result);
  return result;
}

```

## disassembly

```asm
0x1400a61d4  push    rbp
0x1400a61d6  push    rbx
0x1400a61d7  push    rsi
0x1400a61d8  push    rdi
0x1400a61d9  push    r12
0x1400a61db  push    r13
0x1400a61dd  push    r14
0x1400a61df  push    r15
0x1400a61e1  lea     rbp, [rsp-58h]
0x1400a61e6  sub     rsp, 158h
0x1400a61ed  mov     rax, cs:__security_cookie
0x1400a61f4  xor     rax, rsp
0x1400a61f7  mov     [rbp+90h+var_50], rax
0x1400a61fb  xor     eax, eax
0x1400a61fd  mov     [rsp+190h+var_140], rcx
0x1400a6202  lea     r14, [rcx+2E90h]
0x1400a6209  mov     qword ptr [rbp+90h+PerformanceFrequency], rax
0x1400a620d  mov     [rsp+190h+var_126], ax
0x1400a6212  mov     r15, rcx
0x1400a6215  mov     al, [rbp+90h+arg_20]
0x1400a621b  xorps   xmm0, xmm0
0x1400a621e  xor     ecx, ecx; PerformanceFrequency
0x1400a6220  mov     [rsp+190h+var_128], al
0x1400a6224  mov     [rsp+190h+var_15C], r9b
0x1400a6229  mov     [rsp+190h+var_150], r8d
0x1400a622e  mov     [rsp+190h+var_154], edx
0x1400a6232  movups  [rsp+190h+var_120], xmm0
0x1400a6237  mov     [rsp+190h+var_148], r14
0x1400a623c  mov     [rsp+190h+var_130], edx
0x1400a6240  mov     [rsp+190h+var_12C], r8d
0x1400a6245  mov     [rsp+190h+var_127], r9b
0x1400a624a  call    cs:__imp_KeQueryPerformanceCounter
0x1400a6251  nop     dword ptr [rax+rax+00h]
0x1400a6256  mov     rcx, r14
0x1400a6259  mov     qword ptr [rsp+190h+var_120], rax
0x1400a625e  call    VidPushLockAcquireShared
0x1400a6263  mov     al, [r15+2EACh]
0x1400a626a  xor     r8d, r8d
0x1400a626d  test    al, al
0x1400a626f  jnz     loc_1400A6691
0x1400a6275  lea     rdi, [r14+8]
0x1400a6279  mov     rbx, [rdi]
0x1400a627c  lea     r9d, [r8+1]
0x1400a6280  test    [rdi+8], r9b
0x1400a6284  jz      short loc_1400A6293
0x1400a6286  test    rbx, rbx
0x1400a6289  jz      short loc_1400A6290
0x1400a628b  xor     rbx, rdi
0x1400a628e  jmp     short loc_1400A6293
0x1400a6290  mov     rbx, r8
0x1400a6293  movzx   esi, byte ptr [rdi+8]
0x1400a6297  and     esi, r9d
0x1400a629a  test    rbx, rbx
0x1400a629d  jz      loc_1400A6571
0x1400a62a3  mov     rdx, rbx
0x1400a62a6  lea     rcx, [rsp+190h+var_130]
0x1400a62ab  call    VsmmMemTrackerpCompareTreeNodes
0x1400a62b0  xor     r8d, r8d
0x1400a62b3  test    eax, eax
0x1400a62b5  jns     short loc_1400A62BC
0x1400a62b7  mov     rax, [rbx]
0x1400a62ba  jmp     short loc_1400A62C2
0x1400a62bc  jle     short loc_1400A62D8
0x1400a62be  mov     rax, [rbx+8]
0x1400a62c2  test    esi, esi
0x1400a62c4  jz      short loc_1400A62D0
0x1400a62c6  test    rax, rax
0x1400a62c9  jz      short loc_1400A62D0
0x1400a62cb  xor     rbx, rax
0x1400a62ce  jmp     short loc_1400A62D3
0x1400a62d0  mov     rbx, rax
0x1400a62d3  test    rbx, rbx
0x1400a62d6  jnz     short loc_1400A62A3
0x1400a62d8  test    rbx, rbx
0x1400a62db  jz      loc_1400A6571
0x1400a62e1  mov     r15, [rbx+28h]
0x1400a62e5  lea     r12, dword_140065110
0x1400a62ec  mov     rdi, [rsp+190h+var_140]
0x1400a62f1  mov     cl, r8b
0x1400a62f4  mov     r14, [rbp+90h+arg_28]
0x1400a62fb  mov     r13d, 100h
0x1400a6301  cmp     r14, r15
0x1400a6304  jbe     loc_1400A642C
0x1400a630a  test    cl, cl
0x1400a630c  jnz     loc_1400A6427
0x1400a6312  mov     eax, cs:dword_140065110
0x1400a6318  cmp     eax, 2
0x1400a631b  jbe     loc_1400A6425
0x1400a6321  mov     rdx, r13
0x1400a6324  mov     rcx, r12
0x1400a6327  call    _tlgKeywordOn
0x1400a632c  test    al, al
0x1400a632e  jz      loc_1400A6425
0x1400a6334  lea     rdx, aVsmmmemtracker_6; "VsmmMemTrackerpRemoveMemory"
0x1400a633b  lea     rcx, [rbp+90h+var_E0]
0x1400a633f  call    _tlgCreate1Sz_char
0x1400a6344  lea     rdx, aOnecoreVmVidSy_15; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtra"...
0x1400a634b  lea     rcx, [rbp+90h+var_D0]
0x1400a634f  call    _tlgCreate1Sz_char
0x1400a6354  lea     rax, [rsp+190h+var_158]
0x1400a6359  mov     [rsp+190h+var_158], 4A2h
0x1400a6361  mov     [rbp+90h+var_C0], rax
0x1400a6365  lea     rdx, unk_14004BA37
0x1400a636c  lea     rax, [rdi+290h]
0x1400a6373  mov     [rbp+90h+var_B8], 4
0x1400a637b  mov     [rbp+90h+var_B0], rax
0x1400a637f  xor     r9d, r9d
0x1400a6382  mov     eax, [rsp+190h+var_154]
0x1400a6386  xor     r8d, r8d
0x1400a6389  mov     [rsp+190h+var_160], al
0x1400a638d  mov     rcx, r12
0x1400a6390  lea     rax, [rsp+190h+var_160]
0x1400a6395  mov     [rbp+90h+var_A8], 10h
0x1400a639d  mov     [rbp+90h+var_A0], rax
0x1400a63a1  mov     eax, [rsp+190h+var_150]
0x1400a63a5  mov     [rsp+190h+var_15F], al
0x1400a63a9  lea     rax, [rsp+190h+var_15F]
0x1400a63ae  mov     [rbp+90h+var_90], rax
0x1400a63b2  mov     al, [rsp+190h+var_15C]
0x1400a63b6  mov     [rsp+190h+var_15E], al
0x1400a63ba  lea     rax, [rsp+190h+var_15E]
0x1400a63bf  mov     [rbp+90h+var_80], rax
0x1400a63c3  mov     al, [rbp+90h+arg_20]
0x1400a63c9  mov     [rsp+190h+var_15D], al
0x1400a63cd  lea     rax, [rsp+190h+var_15D]
0x1400a63d2  mov     [rbp+90h+var_70], rax
0x1400a63d6  lea     rax, [rsp+190h+var_138]
0x1400a63db  mov     [rbp+90h+var_60], rax
0x1400a63df  lea     rax, [rbp+90h+var_100]
0x1400a63e3  mov     [rsp+190h+var_168], rax
0x1400a63e8  mov     [rsp+190h+var_170], 0Bh
0x1400a63f0  mov     [rbp+90h+var_98], 1
0x1400a63f8  mov     [rbp+90h+var_88], 1
0x1400a6400  mov     [rbp+90h+var_78], 1
0x1400a6408  mov     [rbp+90h+var_68], 1
0x1400a6410  mov     [rsp+190h+var_138], r14
0x1400a6415  mov     [rbp+90h+var_58], 8
0x1400a641d  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a6422  xor     r8d, r8d
0x1400a6425  mov     cl, 1
0x1400a6427  mov     rsi, r8
0x1400a642a  jmp     short loc_1400A6432
0x1400a642c  mov     rsi, r15
0x1400a642f  sub     rsi, r14
0x1400a6432  mov     rax, r15
0x1400a6435  lock cmpxchg [rbx+28h], rsi
0x1400a643b  mov     r15, rax
0x1400a643e  jnz     loc_1400A6301
0x1400a6444  mov     r14, [rsp+190h+var_148]
0x1400a6449  mov     rcx, r14
0x1400a644c  call    VidPushLockRelease
0x1400a6451  lea     rdi, [r14+8]
0x1400a6455  test    rsi, rsi
0x1400a6458  jnz     loc_1400A6699
0x1400a645e  mov     rcx, r14
0x1400a6461  call    VidPushLockAcquireExclusive
0x1400a6466  mov     r15, [rsp+190h+var_140]
0x1400a646b  xor     r8d, r8d
0x1400a646e  mov     al, [r15+2EACh]
0x1400a6475  test    al, al
0x1400a6477  jnz     loc_1400A6691
0x1400a647d  lea     r9d, [r8+1]
0x1400a6481  test    [rdi+8], r9b
0x1400a6485  jz      short loc_1400A649C
0x1400a6487  mov     rax, [rdi]
0x1400a648a  test    rax, rax
0x1400a648d  jz      short loc_1400A6497
0x1400a648f  mov     rbx, rdi
0x1400a6492  xor     rbx, rax
0x1400a6495  jmp     short loc_1400A649F
0x1400a6497  mov     rbx, r8
0x1400a649a  jmp     short loc_1400A649F
0x1400a649c  mov     rbx, [rdi]
0x1400a649f  movzx   esi, byte ptr [rdi+8]
0x1400a64a3  and     esi, r9d
0x1400a64a6  test    rbx, rbx
0x1400a64a9  jz      short loc_1400A651E
0x1400a64ab  mov     rdx, rbx
0x1400a64ae  lea     rcx, [rsp+190h+var_130]
0x1400a64b3  call    VsmmMemTrackerpCompareTreeNodes
0x1400a64b8  xor     r8d, r8d
0x1400a64bb  test    eax, eax
0x1400a64bd  jns     short loc_1400A64C4
0x1400a64bf  mov     rax, [rbx]
0x1400a64c2  jmp     short loc_1400A64CA
0x1400a64c4  jle     short loc_1400A64E0
0x1400a64c6  mov     rax, [rbx+8]
0x1400a64ca  test    esi, esi
0x1400a64cc  jz      short loc_1400A64D8
0x1400a64ce  test    rax, rax
0x1400a64d1  jz      short loc_1400A64D8
0x1400a64d3  xor     rbx, rax
0x1400a64d6  jmp     short loc_1400A64DB
0x1400a64d8  mov     rbx, rax
0x1400a64db  test    rbx, rbx
0x1400a64de  jnz     short loc_1400A64AB
0x1400a64e0  test    rbx, rbx
0x1400a64e3  jz      short loc_1400A651E
0x1400a64e5  cmp     [rbx+28h], r8
0x1400a64e9  jnz     loc_1400A6691
0x1400a64ef  mov     rdx, rbx
0x1400a64f2  mov     rcx, rdi
0x1400a64f5  call    cs:__imp_RtlRbRemoveNode
0x1400a64fc  nop     dword ptr [rax+rax+00h]
0x1400a6501  mov     edx, 744D6456h; Tag
0x1400a6506  mov     rcx, rbx; P
0x1400a6509  call    cs:__imp_ExFreePoolWithTag
0x1400a6510  nop     dword ptr [rax+rax+00h]
0x1400a6515  dec     dword ptr [r14+18h]
0x1400a6519  jmp     loc_1400A6691
0x1400a651e  mov     eax, cs:dword_140065110
0x1400a6524  cmp     eax, 2
0x1400a6527  jbe     loc_1400A6691
0x1400a652d  mov     rdx, r13
0x1400a6530  mov     rcx, r12
0x1400a6533  call    _tlgKeywordOn
0x1400a6538  test    al, al
0x1400a653a  jz      loc_1400A6691
0x1400a6540  lea     rdx, aVsmmmemtracker_6; "VsmmMemTrackerpRemoveMemory"
0x1400a6547  lea     rcx, [rbp+90h+var_E0]
0x1400a654b  call    _tlgCreate1Sz_char
0x1400a6550  lea     rdx, aOnecoreVmVidSy_15; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtra"...
0x1400a6557  lea     rcx, [rbp+90h+var_D0]
0x1400a655b  call    _tlgCreate1Sz_char
0x1400a6560  mov     [rsp+190h+var_158], 4F2h
0x1400a6568  lea     rdx, unk_14004BACA
0x1400a656f  jmp     short loc_1400A65CB
0x1400a6571  mov     eax, cs:dword_140065110
0x1400a6577  cmp     eax, 2
0x1400a657a  jbe     loc_1400A6691
0x1400a6580  lea     r12, dword_140065110
0x1400a6587  mov     edx, 100h
0x1400a658c  mov     rcx, r12
0x1400a658f  call    _tlgKeywordOn
0x1400a6594  test    al, al
0x1400a6596  jz      loc_1400A6691
0x1400a659c  lea     rdx, aVsmmmemtracker_6; "VsmmMemTrackerpRemoveMemory"
0x1400a65a3  lea     rcx, [rbp+90h+var_E0]
0x1400a65a7  call    _tlgCreate1Sz_char
0x1400a65ac  lea     rdx, aOnecoreVmVidSy_15; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemtra"...
0x1400a65b3  lea     rcx, [rbp+90h+var_D0]
0x1400a65b7  call    _tlgCreate1Sz_char
0x1400a65bc  mov     [rsp+190h+var_158], 47Eh
0x1400a65c4  lea     rdx, unk_14004B9A4
0x1400a65cb  lea     rax, [rsp+190h+var_158]
0x1400a65d0  mov     [rbp+90h+var_A8], 10h
0x1400a65d8  mov     [rbp+90h+var_C0], rax
0x1400a65dc  xor     r9d, r9d
0x1400a65df  lea     rax, [r15+290h]
0x1400a65e6  mov     [rbp+90h+var_B8], 4
0x1400a65ee  mov     [rbp+90h+var_B0], rax
0x1400a65f2  xor     r8d, r8d
0x1400a65f5  mov     eax, [rsp+190h+var_154]
0x1400a65f9  mov     rcx, r12
0x1400a65fc  mov     [rsp+190h+var_15D], al
0x1400a6600  lea     rax, [rsp+190h+var_15D]
0x1400a6605  mov     [rbp+90h+var_A0], rax
0x1400a6609  mov     eax, [rsp+190h+var_150]
0x1400a660d  mov     [rsp+190h+var_15E], al
0x1400a6611  lea     rax, [rsp+190h+var_15E]
0x1400a6616  mov     [rbp+90h+var_90], rax
0x1400a661a  mov     al, [rsp+190h+var_15C]
0x1400a661e  mov     [rsp+190h+var_15F], al
0x1400a6622  lea     rax, [rsp+190h+var_15F]
0x1400a6627  mov     [rbp+90h+var_80], rax
0x1400a662b  mov     al, [rbp+90h+arg_20]
0x1400a6631  mov     [rsp+190h+var_160], al
0x1400a6635  lea     rax, [rsp+190h+var_160]
0x1400a663a  mov     [rbp+90h+var_70], rax
0x1400a663e  mov     rax, [rbp+90h+arg_28]
0x1400a6645  mov     [rsp+190h+var_148], rax
0x1400a664a  lea     rax, [rsp+190h+var_148]
0x1400a664f  mov     [rbp+90h+var_60], rax
0x1400a6653  lea     rax, [rbp+90h+var_100]
0x1400a6657  mov     [rsp+190h+var_168], rax
0x1400a665c  mov     [rsp+190h+var_170], 0Bh
0x1400a6664  mov     [rbp+90h+var_98], 1
0x1400a666c  mov     [rbp+90h+var_88], 1
0x1400a6674  mov     [rbp+90h+var_78], 1
0x1400a667c  mov     [rbp+90h+var_68], 1
0x1400a6684  mov     [rbp+90h+var_58], 8
0x1400a668c  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a6691  mov     rcx, r14
0x1400a6694  call    VidPushLockRelease
0x1400a6699  lea     rcx, [rbp+90h+PerformanceFrequency]; PerformanceFrequency
0x1400a669d  call    cs:__imp_KeQueryPerformanceCounter
0x1400a66a4  nop     dword ptr [rax+rax+00h]
0x1400a66a9  mov     rcx, [rsp+190h+var_140]
0x1400a66ae  mov     qword ptr [rsp+190h+var_120+8], rax
0x1400a66b3  sub     rax, qword ptr [rsp+190h+var_120]
0x1400a66b8  imul    rax, 0F4240h
0x1400a66bf  mov     rcx, [rcx+5F8h]
0x1400a66c6  cqo
0x1400a66c8  idiv    qword ptr [rbp+90h+PerformanceFrequency]
0x1400a66cc  lock add [rcx+918h], rax
0x1400a66d4  mov     rcx, [rbp+90h+var_50]
0x1400a66d8  xor     rcx, rsp; StackCookie
0x1400a66db  call    __security_check_cookie
0x1400a66e0  add     rsp, 158h
0x1400a66e7  pop     r15
  ... truncated ...
```
