# VidTdxIoctlPartitionCreateScanOutputBuffer

- ea: `0x14007c150`
- end: `0x14007c5fa`
- name: `VidTdxIoctlPartitionCreateScanOutputBuffer`
- size: `1194`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x140035708`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140021e00`
- `0x140024850`
- `0x1400248b8`
- `0x140024e18`
- `0x140030990`
- `0x1400309d0`
- `0x14007b388`
- `0x14007c150`
- `0x1400f1ea0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14007c30d`
- `ntoskrnl!ExAllocatePool2` at `0x14007c30d`
- `winhvr!WinHvCreateTdScanOutputBuffer` at `0x14007c36d`
- `winhvr!WinHvCreateTdScanOutputBuffer` at `0x14007c36d`

## string_xrefs

- `0x14007c1c5`: `VidTdxIoctlPartitionCreateScanOutputBuffer`

## pseudocode

```c
__int64 __fastcall VidTdxIoctlPartitionCreateScanOutputBuffer(__int64 a1, unsigned __int8 a2, _QWORD *a3)
{
  _QWORD *v3; // rdi
  __int64 v4; // r13
  __int64 v6; // r12
  __int64 *v7; // r14
  int v8; // ecx
  __int64 v9; // rdx
  unsigned int v10; // edx
  __int64 *v11; // rcx
  __int64 v12; // r8
  int TdScanOutputBuffer; // ebx
  char v14; // r12
  _QWORD *Pool2; // rax
  _QWORD *v16; // rdi
  int v17; // r8d
  bool v18; // zf
  unsigned int v19; // edx
  __int64 *v20; // rcx
  unsigned int v21; // edx
  __int64 *v22; // rcx
  char v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v28[10]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v29[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v30[32]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v31[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v32; // [rsp+100h] [rbp+0h] BYREF
  __int64 v33; // [rsp+108h] [rbp+8h]
  __int64 *v34; // [rsp+110h] [rbp+10h]
  __int64 v35; // [rsp+118h] [rbp+18h]
  __int64 *v36; // [rsp+120h] [rbp+20h]
  __int64 v37; // [rsp+128h] [rbp+28h] BYREF
  __int64 *v38; // [rsp+130h] [rbp+30h]
  __int64 v39; // [rsp+138h] [rbp+38h] BYREF
  __int64 *v40; // [rsp+140h] [rbp+40h]
  __int64 v41; // [rsp+148h] [rbp+48h]
  __int64 *v42; // [rsp+150h] [rbp+50h]
  __int64 v43; // [rsp+158h] [rbp+58h]

  v26 = a3;
  v3 = a3;
  v4 = a2;
  memset(v29, 0, 24);
  memset(v28, 0, sizeof(v28));
  v6 = -1;
  v25 = -1;
  VidTraceActivityInitialize(v28);
  v7 = (__int64 *)(a1 + 648);
  v28[7] = *(_QWORD *)(a1 + 648);
  v8 = a1 + 656;
  v9 = a1 + 120;
  v28[0] = "VidTdxIoctlPartitionCreateScanOutputBuffer";
  v28[6] = a1 + 656;
  v28[8] = a1 + 120;
  if ( (unsigned int)dword_140065110 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v31, v28[0]);
      v32 = v28[6];
      v33 = 16;
      v10 = *(unsigned __int16 *)v28[8];
      v11 = *(__int64 **)(v28[8] + 8LL);
      v34 = &v37;
      v27 = v28[7];
      v38 = &v27;
      v40 = (__int64 *)&v24;
      v36 = v11;
      v37 = v10;
      v39 = v12;
      v35 = 2;
      v24 = v4;
      v41 = 1;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140045F28, &v28[4], &v28[2], v12, v30);
    }
    v9 = a1 + 120;
    v8 = a1 + 656;
  }
  LOBYTE(v28[9]) = 1;
  if ( (unsigned __int8)v4 >= *(_BYTE *)(a1 + 2040) )
  {
    TdScanOutputBuffer = -1073741811;
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidTdxIoctlPartitionCreateScanOutputBuffer",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
      438,
      v8,
      v9,
      *v7,
      -1073741811);
    goto LABEL_18;
  }
  v14 = 0;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 112, 1917084758);
  v16 = Pool2;
  if ( !Pool2 )
  {
    TdScanOutputBuffer = -1073741670;
    v17 = 451;
    goto LABEL_13;
  }
  *Pool2 = 0;
  memset(Pool2 + 4, 0, 0x48u);
  v16[10] = v16 + 9;
  v16[9] = v16 + 9;
  v16[1] = -1;
  v16[13] = 0;
  TdScanOutputBuffer = WinHvCreateTdScanOutputBuffer(*v7, *(unsigned __int8 *)(v4 + a1 + 2041), v29);
  if ( TdScanOutputBuffer < 0 )
  {
    v17 = 475;
    goto LABEL_13;
  }
  v6 = *(_QWORD *)&v29[0];
  v16[1] = *(_QWORD *)&v29[0];
  v25 = v6;
  *((_OWORD *)v16 + 1) = *(_OWORD *)((char *)v29 + 8);
  VidLockAcquireExclusive(a1 + 12800);
  TdScanOutputBuffer = VidHandleTableAllocateEntry(a1 + 12768, v16, v26);
  if ( TdScanOutputBuffer < 0 )
  {
    v14 = 1;
    v17 = 493;
LABEL_13:
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidTdxIoctlPartitionCreateScanOutputBuffer",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
      v17,
      a1 + 656,
      a1 + 120,
      *v7,
      TdScanOutputBuffer);
    if ( v16 )
      VidTdxScanOutputBufferTeardown(a1, v16);
    v18 = v14 == 0;
    v6 = v25;
    if ( v18 )
      goto LABEL_17;
  }
  VidLockRelease(a1 + 12800);
LABEL_17:
  v3 = v26;
LABEL_18:
  if ( LOBYTE(v28[9]) )
  {
    if ( TdScanOutputBuffer < 0 )
    {
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        v31[0] = &v25;
        LODWORD(v25) = TdScanOutputBuffer;
        v31[1] = 4;
        tlgCreate1Sz_char(&v32, v28[0]);
        v34 = (__int64 *)v28[6];
        v35 = 16;
        v21 = *(unsigned __int16 *)v28[8];
        v22 = *(__int64 **)(v28[8] + 8LL);
        v36 = &v39;
        v27 = v28[7];
        v40 = &v27;
        v38 = v22;
        v39 = v21;
        v37 = 2;
        v41 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140045E38, &v28[4], 0, 8, v30);
      }
    }
    else if ( (unsigned int)dword_140065110 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v31, v28[0]);
      v32 = v28[6];
      v33 = 16;
      v19 = *(unsigned __int16 *)v28[8];
      v20 = *(__int64 **)(v28[8] + 8LL);
      v34 = &v37;
      v27 = v28[7];
      v38 = &v27;
      v26 = (_QWORD *)*v3;
      v40 = (__int64 *)&v26;
      v42 = &v25;
      v37 = v19;
      v35 = 2;
      v36 = v20;
      v39 = 8;
      v41 = 8;
      v25 = v6;
      v43 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140045E9F, &v28[4], 0, 9, v30);
    }
    VidTraceActivityTeardown(v28);
  }
  return (unsigned int)TdScanOutputBuffer;
}

```

## disassembly

```asm
0x14007c150  mov     [rsp-8+arg_18], rbx
0x14007c155  push    rbp
0x14007c156  push    rsi
0x14007c157  push    rdi
0x14007c158  push    r12
0x14007c15a  push    r13
0x14007c15c  push    r14
0x14007c15e  push    r15
0x14007c160  lea     rbp, [rsp-70h]
0x14007c165  sub     rsp, 170h
0x14007c16c  mov     rax, cs:__security_cookie
0x14007c173  xor     rax, rsp
0x14007c176  mov     [rbp+0A0h+var_40], rax
0x14007c17a  xor     eax, eax
0x14007c17c  mov     [rsp+1A0h+var_150], r8
0x14007c181  mov     rdi, r8
0x14007c184  movzx   r13d, dl
0x14007c188  mov     rsi, rcx
0x14007c18b  mov     [rbp+0A0h+var_E0], rax
0x14007c18f  xorps   xmm0, xmm0
0x14007c192  lea     rcx, [rsp+1A0h+var_140]; void *
0x14007c197  lea     r8d, [rax+50h]; Size
0x14007c19b  xor     edx, edx; Val
0x14007c19d  movups  [rbp+0A0h+var_F0], xmm0
0x14007c1a1  call    memset
0x14007c1a6  or      r12, 0FFFFFFFFFFFFFFFFh
0x14007c1aa  lea     rcx, [rsp+1A0h+var_140]
0x14007c1af  mov     [rsp+1A0h+var_158], r12
0x14007c1b4  call    VidTraceActivityInitialize
0x14007c1b9  lea     r14, [rsi+288h]
0x14007c1c0  xor     ebx, ebx
0x14007c1c2  mov     rax, [r14]
0x14007c1c5  lea     r15, aVidtdxioctlpar_25; "VidTdxIoctlPartitionCreateScanOutputBuf"...
0x14007c1cc  mov     [rbp+0A0h+var_108], rax
0x14007c1d0  lea     rcx, [rsi+290h]
0x14007c1d7  mov     eax, cs:dword_140065110
0x14007c1dd  lea     rdx, [rsi+78h]
0x14007c1e1  mov     [rsp+1A0h+var_140], r15
0x14007c1e6  lea     r8d, [r12+9]
0x14007c1eb  mov     [rbp+0A0h+var_110], rcx
0x14007c1ef  mov     [rbp+0A0h+var_100], rdx
0x14007c1f3  cmp     eax, 5
0x14007c1f6  jbe     loc_14007C2B9
0x14007c1fc  mov     edx, 100h
0x14007c201  lea     rcx, dword_140065110
0x14007c208  call    _tlgKeywordOn
0x14007c20d  test    al, al
0x14007c20f  jz      loc_14007C2AE
0x14007c215  mov     rdx, [rsp+1A0h+var_140]
0x14007c21a  lea     rcx, [rbp+0A0h+var_B0]
0x14007c21e  call    _tlgCreate1Sz_char
0x14007c223  mov     rax, [rbp+0A0h+var_100]
0x14007c227  lea     r9, [rsp+1A0h+var_130]
0x14007c22c  mov     rcx, [rbp+0A0h+var_110]
0x14007c230  mov     [rbp+0A0h+var_A0], rcx
0x14007c234  mov     [rbp+0A0h+var_98], 10h
0x14007c23c  movzx   edx, word ptr [rax]
0x14007c23f  mov     rcx, [rax+8]
0x14007c243  lea     rax, [rbp+0A0h+var_78]
0x14007c247  mov     [rbp+0A0h+var_90], rax
0x14007c24b  mov     rax, [rbp+0A0h+var_108]
0x14007c24f  mov     [rsp+1A0h+var_148], rax
0x14007c254  lea     rax, [rsp+1A0h+var_148]
0x14007c259  mov     [rbp+0A0h+var_70], rax
0x14007c25d  lea     rax, [rsp+1A0h+var_160]
0x14007c262  mov     [rbp+0A0h+var_60], rax
0x14007c266  lea     rax, [rbp+0A0h+var_D0]
0x14007c26a  mov     [rsp+1A0h+var_178], rax
0x14007c26f  mov     dword ptr [rsp+1A0h+var_180], r8d
0x14007c274  mov     [rbp+0A0h+var_80], rcx
0x14007c278  lea     rcx, dword_140065110
0x14007c27f  mov     dword ptr [rbp+0A0h+var_78], edx
0x14007c282  lea     rdx, unk_140045F28
0x14007c289  mov     [rbp+0A0h+var_68], r8
0x14007c28d  lea     r8, [rbp+0A0h+var_120]
0x14007c291  mov     [rbp+0A0h+var_88], 2
0x14007c299  mov     dword ptr [rbp+0A0h+var_78+4], ebx
0x14007c29c  mov     [rsp+1A0h+var_160], r13b
0x14007c2a1  mov     [rbp+0A0h+var_58], 1
0x14007c2a9  call    _tlgWriteTransfer_EtwWriteTransfer
0x14007c2ae  lea     rdx, [rsi+78h]
0x14007c2b2  lea     rcx, [rsi+290h]
0x14007c2b9  mov     [rbp+0A0h+var_F8], 1
0x14007c2bd  cmp     r13b, [rsi+7F8h]
0x14007c2c4  jb      short loc_14007C2FC
0x14007c2c6  mov     ebx, 0C000000Dh
0x14007c2cb  mov     rax, [r14]
0x14007c2ce  mov     r9, rcx
0x14007c2d1  mov     [rsp+1A0h+var_170], ebx
0x14007c2d5  mov     r8d, 1B6h
0x14007c2db  mov     [rsp+1A0h+var_178], rax
0x14007c2e0  mov     rcx, r15
0x14007c2e3  mov     [rsp+1A0h+var_180], rdx
0x14007c2e8  lea     rdx, aOnecoreVmVidSy_21; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007c2ef  call    VidTracePartitionErrorInternal0
0x14007c2f4  xor     r13d, r13d
0x14007c2f7  jmp     loc_14007C425
0x14007c2fc  mov     edx, 70h ; 'p'
0x14007c301  mov     r8d, 72446456h
0x14007c307  mov     r12b, bl
0x14007c30a  lea     ecx, [rdx-30h]
0x14007c30d  call    cs:__imp_ExAllocatePool2
0x14007c314  nop     dword ptr [rax+rax+00h]
0x14007c319  mov     rdi, rax
0x14007c31c  test    rax, rax
0x14007c31f  jnz     short loc_14007C334
0x14007c321  mov     ebx, 0C000009Ah
0x14007c326  mov     r8d, 1C3h
0x14007c32c  xor     r13d, r13d
0x14007c32f  jmp     loc_14007C3CF
0x14007c334  xor     edx, edx; Val
0x14007c336  mov     [rax], rbx
0x14007c339  lea     rcx, [rax+20h]; void *
0x14007c33d  lea     r8d, [rdx+48h]; Size
0x14007c341  call    memset
0x14007c346  lea     rax, [rdi+48h]
0x14007c34a  mov     [rax+8], rax
0x14007c34e  lea     r8, [rbp+0A0h+var_F0]
0x14007c352  mov     [rax], rax
0x14007c355  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x14007c35d  mov     [rdi+68h], rbx
0x14007c361  movzx   edx, byte ptr [r13+rsi+7F9h]
0x14007c36a  mov     rcx, [r14]
0x14007c36d  call    cs:__imp_WinHvCreateTdScanOutputBuffer
0x14007c374  nop     dword ptr [rax+rax+00h]
0x14007c379  xor     r13d, r13d
0x14007c37c  mov     ebx, eax
0x14007c37e  test    eax, eax
0x14007c380  jns     short loc_14007C38A
0x14007c382  mov     r8d, 1DBh
0x14007c388  jmp     short loc_14007C3CF
0x14007c38a  mov     r12, qword ptr [rbp+0A0h+var_F0]
0x14007c38e  lea     rcx, [rsi+3200h]
0x14007c395  mov     [rdi+8], r12
0x14007c399  movups  xmm0, [rbp+0A0h+var_F0+8]
0x14007c39d  mov     [rsp+1A0h+var_158], r12
0x14007c3a2  movdqu  xmmword ptr [rdi+10h], xmm0
0x14007c3a7  call    VidLockAcquireExclusive
0x14007c3ac  mov     r8, [rsp+1A0h+var_150]
0x14007c3b1  lea     rcx, [rsi+31E0h]
0x14007c3b8  mov     rdx, rdi
0x14007c3bb  call    VidHandleTableAllocateEntry
0x14007c3c0  mov     ebx, eax
0x14007c3c2  test    eax, eax
0x14007c3c4  jns     short loc_14007C414
0x14007c3c6  mov     r12b, 1
0x14007c3c9  mov     r8d, 1EDh
0x14007c3cf  lea     rdx, aOnecoreVmVidSy_21; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007c3d6  mov     rax, [r14]
0x14007c3d9  lea     r9, [rsi+290h]
0x14007c3e0  mov     [rsp+1A0h+var_170], ebx
0x14007c3e4  mov     rcx, r15
0x14007c3e7  mov     [rsp+1A0h+var_178], rax
0x14007c3ec  lea     rax, [rsi+78h]
0x14007c3f0  mov     [rsp+1A0h+var_180], rax
0x14007c3f5  call    VidTracePartitionErrorInternal0
0x14007c3fa  test    rdi, rdi
0x14007c3fd  jz      short loc_14007C40A
0x14007c3ff  mov     rdx, rdi
0x14007c402  mov     rcx, rsi
0x14007c405  call    VidTdxScanOutputBufferTeardown
0x14007c40a  test    r12b, r12b
0x14007c40d  mov     r12, [rsp+1A0h+var_158]
0x14007c412  jz      short loc_14007C420
0x14007c414  lea     rcx, [rsi+3200h]
0x14007c41b  call    VidLockRelease
0x14007c420  mov     rdi, [rsp+1A0h+var_150]
0x14007c425  cmp     [rbp+0A0h+var_F8], r13b
0x14007c429  jz      loc_14007C5D0
0x14007c42f  mov     eax, cs:dword_140065110
0x14007c435  test    ebx, ebx
0x14007c437  js      loc_14007C509
0x14007c43d  cmp     eax, 5
0x14007c440  jbe     loc_14007C5C6
0x14007c446  mov     edx, 100h
0x14007c44b  lea     rcx, dword_140065110
0x14007c452  call    _tlgKeywordOn
0x14007c457  test    al, al
0x14007c459  jz      loc_14007C5C6
0x14007c45f  mov     rdx, [rsp+1A0h+var_140]
0x14007c464  lea     rcx, [rbp+0A0h+var_B0]
0x14007c468  call    _tlgCreate1Sz_char
0x14007c46d  mov     rax, [rbp+0A0h+var_100]
0x14007c471  mov     rcx, [rbp+0A0h+var_110]
0x14007c475  mov     [rbp+0A0h+var_A0], rcx
0x14007c479  mov     [rbp+0A0h+var_98], 10h
0x14007c481  movzx   edx, word ptr [rax]
0x14007c484  mov     rcx, [rax+8]
0x14007c488  lea     rax, [rbp+0A0h+var_78]
0x14007c48c  mov     [rbp+0A0h+var_90], rax
0x14007c490  mov     rax, [rbp+0A0h+var_108]
0x14007c494  mov     [rsp+1A0h+var_148], rax
0x14007c499  lea     rax, [rsp+1A0h+var_148]
0x14007c49e  mov     [rbp+0A0h+var_70], rax
0x14007c4a2  mov     rax, [rdi]
0x14007c4a5  mov     [rsp+1A0h+var_150], rax
0x14007c4aa  lea     rax, [rsp+1A0h+var_150]
0x14007c4af  mov     [rbp+0A0h+var_60], rax
0x14007c4b3  lea     rax, [rsp+1A0h+var_158]
0x14007c4b8  mov     [rbp+0A0h+var_50], rax
0x14007c4bc  lea     rax, [rbp+0A0h+var_D0]
0x14007c4c0  mov     [rsp+1A0h+var_178], rax
0x14007c4c5  mov     dword ptr [rbp+0A0h+var_78], edx
0x14007c4c8  lea     rdx, unk_140045E9F
0x14007c4cf  mov     dword ptr [rsp+1A0h+var_180], 9
0x14007c4d7  mov     [rbp+0A0h+var_88], 2
0x14007c4df  mov     [rbp+0A0h+var_80], rcx
0x14007c4e3  mov     dword ptr [rbp+0A0h+var_78+4], r13d
0x14007c4e7  mov     [rbp+0A0h+var_68], 8
0x14007c4ef  mov     [rbp+0A0h+var_58], 8
0x14007c4f7  mov     [rsp+1A0h+var_158], r12
0x14007c4fc  mov     [rbp+0A0h+var_48], 8
0x14007c504  jmp     loc_14007C5B3
0x14007c509  cmp     eax, 2
0x14007c50c  jbe     loc_14007C5C6
0x14007c512  mov     edx, 100h
0x14007c517  lea     rcx, dword_140065110
0x14007c51e  call    _tlgKeywordOn
0x14007c523  test    al, al
0x14007c525  jz      loc_14007C5C6
0x14007c52b  mov     rdx, [rsp+1A0h+var_140]
0x14007c530  lea     rax, [rsp+1A0h+var_158]
0x14007c535  lea     rcx, [rbp+0A0h+var_A0]
0x14007c539  mov     [rbp+0A0h+var_B0], rax
0x14007c53d  mov     dword ptr [rsp+1A0h+var_158], ebx
0x14007c541  mov     [rbp+0A0h+var_A8], 4
0x14007c549  call    _tlgCreate1Sz_char
0x14007c54e  mov     rax, [rbp+0A0h+var_100]
0x14007c552  mov     rcx, [rbp+0A0h+var_110]
0x14007c556  mov     [rbp+0A0h+var_90], rcx
0x14007c55a  mov     [rbp+0A0h+var_88], 10h
0x14007c562  movzx   edx, word ptr [rax]
0x14007c565  mov     rcx, [rax+8]
0x14007c569  lea     rax, [rbp+0A0h+var_68]
0x14007c56d  mov     [rbp+0A0h+var_80], rax
0x14007c571  mov     rax, [rbp+0A0h+var_108]
0x14007c575  mov     [rsp+1A0h+var_148], rax
0x14007c57a  lea     rax, [rsp+1A0h+var_148]
0x14007c57f  mov     [rbp+0A0h+var_60], rax
0x14007c583  lea     rax, [rbp+0A0h+var_D0]
0x14007c587  mov     [rbp+0A0h+var_70], rcx
0x14007c58b  mov     ecx, 8
0x14007c590  mov     [rsp+1A0h+var_178], rax
0x14007c595  mov     dword ptr [rbp+0A0h+var_68], edx
0x14007c598  lea     rdx, unk_140045E38
0x14007c59f  mov     dword ptr [rsp+1A0h+var_180], ecx
0x14007c5a3  mov     [rbp+0A0h+var_78], 2
0x14007c5ab  mov     dword ptr [rbp+0A0h+var_68+4], r13d
0x14007c5af  mov     [rbp+0A0h+var_58], rcx
0x14007c5b3  xor     r9d, r9d
0x14007c5b6  lea     r8, [rbp+0A0h+var_120]
0x14007c5ba  lea     rcx, dword_140065110
0x14007c5c1  call    _tlgWriteTransfer_EtwWriteTransfer
0x14007c5c6  lea     rcx, [rsp+1A0h+var_140]
0x14007c5cb  call    VidTraceActivityTeardown
0x14007c5d0  mov     eax, ebx
0x14007c5d2  mov     rcx, [rbp+0A0h+var_40]
0x14007c5d6  xor     rcx, rsp; StackCookie
0x14007c5d9  call    __security_check_cookie
0x14007c5de  mov     rbx, [rsp+1A0h+arg_18]
0x14007c5e6  add     rsp, 170h
0x14007c5ed  pop     r15
0x14007c5ef  pop     r14
0x14007c5f1  pop     r13
0x14007c5f3  pop     r12
0x14007c5f5  pop     rdi
0x14007c5f6  pop     rsi
0x14007c5f7  pop     rbp
0x14007c5f8  retn
```
