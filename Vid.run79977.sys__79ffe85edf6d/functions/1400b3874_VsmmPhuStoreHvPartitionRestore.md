# VsmmPhuStoreHvPartitionRestore

- ea: `0x1400b3874`
- end: `0x1400b4160`
- name: `VsmmPhuStoreHvPartitionRestore`
- size: `2284`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14008e464`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140022610`
- `0x14002f724`
- `0x14009fb08`
- `0x1400af05c`
- `0x1400b3874`
- `0x1400b7550`

## import_xrefs

- `winhvr!WinHvGetPartitionProperty` at `0x1400b3ed8`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b3ed8`
- `winhvr!WinHvCreatePartition` at `0x1400b3f50`
- `winhvr!WinHvCreatePartition` at `0x1400b3f50`
- `winhvr!WinHvSetInterceptRoutine` at `0x1400b40fb`
- `winhvr!WinHvSetInterceptRoutine` at `0x1400b40fb`
- `winhvr!WinHvSetLowMemoryPolicyRoutine` at `0x1400b4118`
- `winhvr!WinHvSetLowMemoryPolicyRoutine` at `0x1400b4118`

## pseudocode

```c
__int64 __fastcall VsmmPhuStoreHvPartitionRestore(__int64 a1, int *a2, __int128 *a3)
{
  __int128 v3; // xmm1
  int v4; // eax
  __int128 v8; // xmm0
  unsigned __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned __int64 v14; // r15
  __int64 v15; // rcx
  unsigned int v16; // r14d
  __int64 v17; // r9
  __int64 v18; // r8
  int v19; // eax
  const GUID *v20; // r8
  int PartitionProperty; // eax
  int Partition; // eax
  __int64 v23; // rdx
  int v24; // r11d
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+78h] [rbp-88h] BYREF
  int v33; // [rsp+7Ch] [rbp-84h] BYREF
  int v34; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+84h] [rbp-7Ch] BYREF
  int v36; // [rsp+88h] [rbp-78h] BYREF
  int v37; // [rsp+8Ch] [rbp-74h] BYREF
  int v38; // [rsp+90h] [rbp-70h] BYREF
  int v39; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  __int128 Buf2; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v42; // [rsp+B0h] [rbp-50h]
  __int128 v43; // [rsp+C0h] [rbp-40h]
  __int64 v44; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v45; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v46; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v47; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v48; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v49; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h] BYREF
  __int64 v51; // [rsp+108h] [rbp+8h] BYREF
  __int64 v52; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v53; // [rsp+118h] [rbp+18h] BYREF
  __int128 v54; // [rsp+120h] [rbp+20h] BYREF
  __int128 v55; // [rsp+130h] [rbp+30h] BYREF
  __int64 v56; // [rsp+140h] [rbp+40h]
  struct _EVENT_DATA_DESCRIPTOR v57[2]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v58[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v59[16]; // [rsp+180h] [rbp+80h] BYREF
  int *v60; // [rsp+190h] [rbp+90h]
  __int64 v61; // [rsp+198h] [rbp+98h]
  int *v62; // [rsp+1A0h] [rbp+A0h]
  __int64 v63; // [rsp+1A8h] [rbp+A8h]
  __int64 *v64; // [rsp+1B0h] [rbp+B0h]
  __int64 v65; // [rsp+1B8h] [rbp+B8h]
  __int64 *v66; // [rsp+1C0h] [rbp+C0h]
  __int64 v67; // [rsp+1C8h] [rbp+C8h]
  int *v68; // [rsp+1D0h] [rbp+D0h]
  __int64 v69; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 *v70; // [rsp+1E0h] [rbp+E0h]
  __int64 v71; // [rsp+1E8h] [rbp+E8h]
  __int64 *v72; // [rsp+1F0h] [rbp+F0h]
  __int64 v73; // [rsp+1F8h] [rbp+F8h]
  __int64 *v74; // [rsp+200h] [rbp+100h]
  __int64 v75; // [rsp+208h] [rbp+108h]
  unsigned __int64 *v76; // [rsp+210h] [rbp+110h]
  __int64 v77; // [rsp+218h] [rbp+118h]
  __int64 *v78; // [rsp+220h] [rbp+120h]
  __int64 v79; // [rsp+228h] [rbp+128h]
  __int64 *v80; // [rsp+230h] [rbp+130h]
  __int64 v81; // [rsp+238h] [rbp+138h]
  int *v82; // [rsp+240h] [rbp+140h]
  __int64 v83; // [rsp+248h] [rbp+148h]
  int *v84; // [rsp+250h] [rbp+150h]
  __int64 v85; // [rsp+258h] [rbp+158h]
  __int64 *v86; // [rsp+260h] [rbp+160h]
  __int64 v87; // [rsp+268h] [rbp+168h]
  __int64 *v88; // [rsp+270h] [rbp+170h]
  __int64 v89; // [rsp+278h] [rbp+178h]
  int *v90; // [rsp+280h] [rbp+180h]
  __int64 v91; // [rsp+288h] [rbp+188h]
  int *v92; // [rsp+290h] [rbp+190h]
  __int64 v93; // [rsp+298h] [rbp+198h]
  __int64 *v94; // [rsp+2A0h] [rbp+1A0h]
  __int64 v95; // [rsp+2A8h] [rbp+1A8h]
  unsigned __int64 *v96; // [rsp+2B0h] [rbp+1B0h]
  __int64 v97; // [rsp+2B8h] [rbp+1B8h]
  unsigned __int64 *v98; // [rsp+2C0h] [rbp+1C0h]
  __int64 v99; // [rsp+2C8h] [rbp+1C8h]
  __int64 *v100; // [rsp+2D0h] [rbp+1D0h]
  __int64 v101; // [rsp+2D8h] [rbp+1D8h]
  __int128 *v102; // [rsp+2E0h] [rbp+1E0h]
  __int64 v103; // [rsp+2E8h] [rbp+1E8h]
  char *v104; // [rsp+2F0h] [rbp+1F0h]
  __int64 v105; // [rsp+2F8h] [rbp+1F8h]
  __int64 *v106; // [rsp+300h] [rbp+200h]
  __int64 v107; // [rsp+308h] [rbp+208h]
  __int64 *v108; // [rsp+310h] [rbp+210h]
  __int64 v109; // [rsp+318h] [rbp+218h]
  __int64 *v110; // [rsp+320h] [rbp+220h]
  __int64 v111; // [rsp+328h] [rbp+228h]

  v3 = a3[1];
  v56 = 0;
  v4 = *a2;
  v55 = 0;
  v28 = 0;
  v8 = *a3;
  v42 = v3;
  Buf2 = v8;
  v43 = a3[2];
  if ( (*(_QWORD *)&v4 & 0x800000LL) != 0 )
    v9 = v8 | 0x800000;
  else
    v9 = v8 & 0xFFFFFFFFFF7FFFFFuLL;
  v10 = (unsigned int)a2[3];
  v11 = (unsigned int)a2[9];
  v12 = 0;
  v13 = v10 | (v11 << 32);
  *(_QWORD *)&Buf2 = v9;
  v14 = HIDWORD(*((_QWORD *)&Buf2 + 1)) | ((unsigned __int64)DWORD1(v43) << 32);
  do
  {
    v15 = qword_140040890[v12];
    if ( (v13 & v15) != (v14 & v15) )
    {
      if ( (v13 & v15) != 0 )
        v14 |= v15;
      else
        v14 &= ~v15;
    }
    ++v12;
  }
  while ( v12 != 9 );
  v16 = -1070137295;
  if ( v14 != (HIDWORD(*((_QWORD *)&Buf2 + 1)) | ((unsigned __int64)DWORD1(v43) << 32))
    && (unsigned int)dword_140065110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v58, "VsmmPhuStoreHvPartitionRestore");
    tlgCreate1Sz_char(v59, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    v30 = v17;
    v60 = &v26;
    v29 = v18;
    v62 = &v27;
    v26 = 3542;
    v64 = (__int64 *)(a1 + 656);
    v61 = 4;
    v66 = &v69;
    v68 = *(int **)(a1 + 128);
    v69 = *(unsigned __int16 *)(a1 + 120);
    v31 = *(_QWORD *)(a1 + 648);
    v70 = &v31;
    v72 = &v30;
    v74 = &v29;
    v76 = &v40;
    v27 = -1070137295;
    v63 = 4;
    v65 = 16;
    v67 = 2;
    v71 = 8;
    v73 = 8;
    v75 = 8;
    v40 = v14;
    v77 = 8;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, byte_1400500F6, 0, 0, 0xDu, v57);
  }
  v19 = *(_DWORD *)(a1 + 32);
  DWORD1(v43) = HIDWORD(v14);
  HIDWORD(Buf2) = v14;
  if ( (v19 & 0x1E0) != 0 )
  {
    if ( (*a2 & 0x800LL) != 0 )
      v9 |= 0x800u;
    else
      v9 &= ~0x800uLL;
    *(_QWORD *)&Buf2 = v9;
  }
  if ( (*(_BYTE *)(a1 + 16) & 0x20) != 0 )
  {
    if ( (*a2 & 0x10000000) != 0 )
      v9 |= 0x10000000u;
    else
      v9 &= ~0x10000000uLL;
    *(_QWORD *)&Buf2 = v9;
  }
  if ( memcmp(a2, &Buf2, 0x30u) )
  {
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v58, "VsmmPhuStoreHvPartitionRestore");
      tlgCreate1Sz_char(v59, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      v27 = 3618;
      v60 = &v27;
      v62 = &v26;
      v45 = *(_QWORD *)a2;
      v64 = &v45;
      v32 = a2[2];
      v66 = (__int64 *)&v32;
      v33 = a2[3];
      v68 = &v33;
      v46 = *((_QWORD *)a2 + 2);
      v70 = &v46;
      v47 = *((_QWORD *)a2 + 3);
      v72 = &v47;
      v34 = a2[8];
      v74 = (__int64 *)&v34;
      v35 = a2[9];
      v76 = (unsigned __int64 *)&v35;
      v48 = *((_QWORD *)a2 + 5);
      v78 = &v48;
      v49 = *(_QWORD *)a3;
      v80 = &v49;
      v36 = *((_DWORD *)a3 + 2);
      v82 = &v36;
      v37 = *((_DWORD *)a3 + 3);
      v84 = &v37;
      v50 = *((_QWORD *)a3 + 2);
      v86 = &v50;
      v51 = *((_QWORD *)a3 + 3);
      v88 = &v51;
      v38 = *((_DWORD *)a3 + 8);
      v90 = &v38;
      v39 = *((_DWORD *)a3 + 9);
      v61 = 4;
      v26 = -1070137295;
      v63 = 4;
      v65 = 8;
      v67 = 4;
      v69 = 4;
      v71 = 8;
      v73 = 8;
      v75 = 4;
      v77 = 4;
      v79 = 8;
      v81 = 8;
      v83 = 4;
      v85 = 4;
      v87 = 8;
      v89 = 8;
      v91 = 4;
      v92 = &v39;
      v52 = *((_QWORD *)a3 + 5);
      v94 = &v52;
      v96 = &v53;
      LODWORD(v40) = DWORD2(Buf2);
      v98 = &v40;
      v100 = &v29;
      v54 = v42;
      v102 = &v54;
      v104 = (char *)&v54 + 8;
      LODWORD(v30) = v43;
      v106 = &v30;
      v108 = &v31;
      v44 = *((_QWORD *)&v43 + 1);
      v110 = &v44;
      v93 = 4;
      v95 = 8;
      v53 = v9;
      v97 = 8;
      v99 = 4;
      LODWORD(v29) = v14;
      v101 = 4;
      v103 = 8;
      v105 = 8;
      v107 = 4;
      LODWORD(v31) = HIDWORD(v14);
      v109 = 4;
      v111 = 8;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, byte_14004FD82, v20, 0, 0x1Eu, v57);
    }
    return v16;
  }
  v28 = 0;
  PartitionProperty = WinHvGetPartitionProperty(*((_QWORD *)a2 + 7), 327701, &v28);
  v16 = PartitionProperty;
  if ( PartitionProperty < 0 )
  {
    if ( PartitionProperty != -1070268386 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreHvPartitionRestore",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        3641,
        (unsigned int)PartitionProperty);
      return v16;
    }
    v28 = 0;
    goto LABEL_31;
  }
  if ( !v28 )
  {
LABEL_31:
    VsmmPhuStorepCreationPropertiesDeserialize(a2, &v55);
    Partition = WinHvCreatePartition(*(_QWORD *)a2, 4, 0x80000000LL, (unsigned int)a2[2]);
    v16 = Partition;
    if ( Partition >= 0 )
    {
      *(_QWORD *)(a1 + 648) = *((_QWORD *)a2 + 7);
      *(_BYTE *)(a1 + 3221) = (*((_BYTE *)a2 + 49) & 4) != 0;
      *(_BYTE *)(a1 + 8761) = *((_BYTE *)a2 + 49) & 1;
      *(_BYTE *)(a1 + 8762) = (*((_BYTE *)a2 + 49) & 2) != 0;
      *(_QWORD *)(a1 + 8768) = *((_QWORD *)a2 + 13);
      VsmmVsmSetPartitionConfig(a1, v23, a2 + 16);
      WinHvSetInterceptRoutine(*(_QWORD *)(a1 + 648), VidInterceptIsrCallback, a1);
      WinHvSetLowMemoryPolicyRoutine(*(_QWORD *)(a1 + 648), VidHvMemLowMemPolicyCallback, a1);
      *((_BYTE *)a2 + 48) = 0;
      v16 = 0;
      *(_BYTE *)(a1 + 8760) = 1;
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreHvPartitionRestore",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        3684,
        (unsigned int)Partition);
    }
    return v16;
  }
  while ( !(unsigned int)VsmmPartitionAttachDevice(a1) )
  {
    if ( !--v28 )
      goto LABEL_31;
  }
  v16 = -1073741637;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v58, "VsmmPhuStoreHvPartitionRestore");
    tlgCreate1Sz_char(v59, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v31) = 3656;
    v60 = (int *)&v31;
    v61 = 4;
    v62 = (int *)&v30;
    LODWORD(v30) = -1073741637;
    v64 = &v29;
    v63 = 4;
    LODWORD(v29) = v24;
    v65 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, byte_1400500A8, 0, 0, 7u, v57);
  }
  return v16;
}

```

## disassembly

```asm
0x1400b3874  mov     [rsp-8+arg_10], rbx
0x1400b3879  push    rbp
0x1400b387a  push    rsi
0x1400b387b  push    rdi
0x1400b387c  push    r12
0x1400b387e  push    r13
0x1400b3880  push    r14
0x1400b3882  push    r15
0x1400b3884  lea     rbp, [rsp-240h]
0x1400b388c  sub     rsp, 340h
0x1400b3893  mov     rax, cs:__security_cookie
0x1400b389a  xor     rax, rsp
0x1400b389d  mov     [rbp+270h+var_40], rax
0x1400b38a4  movups  xmm1, xmmword ptr [r8+10h]
0x1400b38a9  xor     eax, eax
0x1400b38ab  xor     r13d, r13d
0x1400b38ae  xorps   xmm0, xmm0
0x1400b38b1  mov     [rbp+270h+var_230], rax
0x1400b38b5  mov     eax, [rdx]
0x1400b38b7  mov     rsi, rcx
0x1400b38ba  movups  [rbp+270h+var_240], xmm0
0x1400b38be  mov     ecx, 800000h
0x1400b38c3  mov     r12, r8
0x1400b38c6  mov     [rsp+370h+var_318], r13
0x1400b38cb  mov     rdi, rdx
0x1400b38ce  movups  xmm0, xmmword ptr [r8]
0x1400b38d2  movups  [rbp+270h+var_2C0], xmm1
0x1400b38d6  movups  [rbp+270h+Buf2], xmm0
0x1400b38da  mov     rbx, qword ptr [rbp+270h+Buf2]
0x1400b38de  movups  xmm0, xmmword ptr [r8+20h]
0x1400b38e3  movups  [rbp+270h+var_2B0], xmm0
0x1400b38e7  test    rcx, rax
0x1400b38ea  jz      short loc_1400B38F1
0x1400b38ec  or      rbx, rcx
0x1400b38ef  jmp     short loc_1400B38F6
0x1400b38f1  btr     rbx, 17h
0x1400b38f6  mov     eax, [rdx+0Ch]
0x1400b38f9  mov     r9d, [rdx+24h]
0x1400b38fd  mov     rdx, r13
0x1400b3900  mov     r8d, dword ptr [rbp+270h+var_2B0+4]
0x1400b3904  shl     r9, 20h
0x1400b3908  or      r9, rax
0x1400b390b  shl     r8, 20h
0x1400b390f  mov     rax, qword ptr [rbp+270h+Buf2+8]
0x1400b3913  shr     rax, 20h
0x1400b3917  or      r8, rax
0x1400b391a  mov     qword ptr [rbp+270h+Buf2], rbx
0x1400b391e  mov     r15, r8
0x1400b3921  lea     rcx, qword_140040890
0x1400b3928  mov     rcx, [rcx+rdx*8]
0x1400b392c  mov     r10, rcx
0x1400b392f  mov     rax, rcx
0x1400b3932  and     r10, r9
0x1400b3935  and     rax, r15
0x1400b3938  cmp     r10, rax
0x1400b393b  jz      short loc_1400B394D
0x1400b393d  test    r10, r10
0x1400b3940  jz      short loc_1400B3947
0x1400b3942  or      r15, rcx
0x1400b3945  jmp     short loc_1400B394D
0x1400b3947  not     rcx
0x1400b394a  and     r15, rcx
0x1400b394d  inc     rdx
0x1400b3950  cmp     rdx, 9
0x1400b3954  jnz     short loc_1400B3921
0x1400b3956  mov     r14d, 0C0370031h
0x1400b395c  cmp     r15, r8
0x1400b395f  jz      loc_1400B3ADB
0x1400b3965  mov     eax, cs:dword_140065110
0x1400b396b  cmp     eax, 2
0x1400b396e  jbe     loc_1400B3ADB
0x1400b3974  mov     edx, 100h
0x1400b3979  lea     rcx, dword_140065110
0x1400b3980  call    _tlgKeywordOn
0x1400b3985  test    al, al
0x1400b3987  jz      loc_1400B3ADB
0x1400b398d  lea     rdx, aVsmmphustorehv_0; "VsmmPhuStoreHvPartitionRestore"
0x1400b3994  lea     rcx, [rbp+270h+var_200]
0x1400b3998  call    _tlgCreate1Sz_char
0x1400b399d  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b39a4  lea     rcx, [rbp+270h+var_1F0]
0x1400b39ab  call    _tlgCreate1Sz_char
0x1400b39b0  lea     rax, [rsp+370h+var_320]
0x1400b39b5  mov     [rsp+370h+var_308], r9
0x1400b39ba  mov     [rbp+270h+var_1E0], rax
0x1400b39c1  lea     rdx, byte_1400500F6
0x1400b39c8  lea     rax, [rsp+370h+var_31C]
0x1400b39cd  mov     [rsp+370h+var_310], r8
0x1400b39d2  mov     [rbp+270h+var_1D0], rax
0x1400b39d9  lea     rcx, dword_140065110
0x1400b39e0  lea     rax, [rsi+290h]
0x1400b39e7  mov     [rsp+370h+var_320], 0DD6h
0x1400b39ef  mov     [rbp+270h+var_1C0], rax
0x1400b39f6  xor     r9d, r9d
0x1400b39f9  lea     rax, [rbp+270h+var_198]
0x1400b3a00  mov     [rbp+270h+var_1D8], 4
0x1400b3a0b  mov     [rbp+270h+var_1B0], rax
0x1400b3a12  xor     r8d, r8d
0x1400b3a15  mov     rax, [rsi+80h]
0x1400b3a1c  mov     [rbp+270h+var_1A0], rax
0x1400b3a23  movzx   eax, word ptr [rsi+78h]
0x1400b3a27  mov     dword ptr [rbp+270h+var_198], eax
0x1400b3a2d  mov     rax, [rsi+288h]
0x1400b3a34  mov     [rsp+370h+var_300], rax
0x1400b3a39  lea     rax, [rsp+370h+var_300]
0x1400b3a3e  mov     [rbp+270h+var_190], rax
0x1400b3a45  lea     rax, [rsp+370h+var_308]
0x1400b3a4a  mov     [rbp+270h+var_180], rax
0x1400b3a51  lea     rax, [rsp+370h+var_310]
0x1400b3a56  mov     [rbp+270h+var_170], rax
0x1400b3a5d  lea     rax, [rbp+270h+var_2D8]
0x1400b3a61  mov     [rbp+270h+var_160], rax
0x1400b3a68  lea     rax, [rbp+270h+var_220]
0x1400b3a6c  mov     [rsp+370h+var_348], rax
0x1400b3a71  mov     dword ptr [rsp+370h+var_350], 0Dh
0x1400b3a79  mov     [rsp+370h+var_31C], r14d
0x1400b3a7e  mov     [rbp+270h+var_1C8], 4
0x1400b3a89  mov     [rbp+270h+var_1B8], 10h
0x1400b3a94  mov     [rbp+270h+var_1A8], 2
0x1400b3a9f  mov     dword ptr [rbp+270h+var_198+4], r13d
0x1400b3aa6  mov     [rbp+270h+var_188], 8
0x1400b3ab1  mov     [rbp+270h+var_178], 8
0x1400b3abc  mov     [rbp+270h+var_168], 8
0x1400b3ac7  mov     [rbp+270h+var_2D8], r15
0x1400b3acb  mov     [rbp+270h+var_158], 8
0x1400b3ad6  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b3adb  mov     eax, [rsi+20h]
0x1400b3ade  mov     r13, r15
0x1400b3ae1  shr     r13, 20h
0x1400b3ae5  mov     dword ptr [rbp+270h+Buf2+0Ch], r15d
0x1400b3ae9  mov     dword ptr [rbp+270h+var_2B0+4], r13d
0x1400b3aed  test    rax, 1E0h
0x1400b3af3  jz      short loc_1400B3B0F
0x1400b3af5  mov     eax, [rdi]
0x1400b3af7  mov     ecx, 800h
0x1400b3afc  test    rcx, rax
0x1400b3aff  jz      short loc_1400B3B06
0x1400b3b01  or      rbx, rcx
0x1400b3b04  jmp     short loc_1400B3B0B
0x1400b3b06  btr     rbx, 0Bh
0x1400b3b0b  mov     qword ptr [rbp+270h+Buf2], rbx
0x1400b3b0f  test    byte ptr [rsi+10h], 20h
0x1400b3b13  jz      short loc_1400B3B2F
0x1400b3b15  mov     eax, [rdi]
0x1400b3b17  mov     ecx, 10000000h
0x1400b3b1c  test    rcx, rax
0x1400b3b1f  jz      short loc_1400B3B26
0x1400b3b21  or      rbx, rcx
0x1400b3b24  jmp     short loc_1400B3B2B
0x1400b3b26  btr     rbx, 1Ch
0x1400b3b2b  mov     qword ptr [rbp+270h+Buf2], rbx
0x1400b3b2f  mov     r8d, 30h ; '0'; Size
0x1400b3b35  lea     rdx, [rbp+270h+Buf2]; Buf2
0x1400b3b39  mov     rcx, rdi; Buf1
0x1400b3b3c  call    memcmp
0x1400b3b41  xor     r8d, r8d
0x1400b3b44  test    eax, eax
0x1400b3b46  jz      loc_1400B3EC2
0x1400b3b4c  mov     eax, cs:dword_140065110
0x1400b3b52  cmp     eax, 2
0x1400b3b55  jbe     loc_1400B4132
0x1400b3b5b  mov     edx, 100h
0x1400b3b60  lea     rcx, dword_140065110
0x1400b3b67  call    _tlgKeywordOn
0x1400b3b6c  test    al, al
0x1400b3b6e  jz      loc_1400B4132
0x1400b3b74  lea     rdx, aVsmmphustorehv_0; "VsmmPhuStoreHvPartitionRestore"
0x1400b3b7b  lea     rcx, [rbp+270h+var_200]
0x1400b3b7f  call    _tlgCreate1Sz_char
0x1400b3b84  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b3b8b  lea     rcx, [rbp+270h+var_1F0]
0x1400b3b92  call    _tlgCreate1Sz_char
0x1400b3b97  lea     rax, [rsp+370h+var_31C]
0x1400b3b9c  mov     [rsp+370h+var_31C], 0E22h
0x1400b3ba4  mov     [rbp+270h+var_1E0], rax
0x1400b3bab  lea     rax, [rsp+370h+var_320]
0x1400b3bb0  mov     [rbp+270h+var_1D0], rax
0x1400b3bb7  mov     rax, [rdi]
0x1400b3bba  mov     [rbp+270h+var_298], rax
0x1400b3bbe  lea     rax, [rbp+270h+var_298]
0x1400b3bc2  mov     [rbp+270h+var_1C0], rax
0x1400b3bc9  mov     eax, [rdi+8]
0x1400b3bcc  mov     [rsp+370h+var_2F8], eax
0x1400b3bd0  lea     rax, [rsp+370h+var_2F8]
0x1400b3bd5  mov     [rbp+270h+var_1B0], rax
0x1400b3bdc  mov     eax, [rdi+0Ch]
0x1400b3bdf  mov     [rsp+370h+var_2F4], eax
0x1400b3be3  lea     rax, [rsp+370h+var_2F4]
0x1400b3be8  mov     [rbp+270h+var_1A0], rax
0x1400b3bef  mov     rax, [rdi+10h]
0x1400b3bf3  mov     [rbp+270h+var_290], rax
0x1400b3bf7  lea     rax, [rbp+270h+var_290]
0x1400b3bfb  mov     [rbp+270h+var_190], rax
0x1400b3c02  mov     rax, [rdi+18h]
0x1400b3c06  mov     [rbp+270h+var_288], rax
0x1400b3c0a  lea     rax, [rbp+270h+var_288]
0x1400b3c0e  mov     [rbp+270h+var_180], rax
0x1400b3c15  mov     eax, [rdi+20h]
0x1400b3c18  mov     [rbp+270h+var_2F0], eax
0x1400b3c1b  lea     rax, [rbp+270h+var_2F0]
0x1400b3c1f  mov     [rbp+270h+var_170], rax
0x1400b3c26  mov     eax, [rdi+24h]
0x1400b3c29  mov     [rbp+270h+var_2EC], eax
0x1400b3c2c  lea     rax, [rbp+270h+var_2EC]
0x1400b3c30  mov     [rbp+270h+var_160], rax
0x1400b3c37  mov     rax, [rdi+28h]
0x1400b3c3b  mov     [rbp+270h+var_280], rax
0x1400b3c3f  lea     rax, [rbp+270h+var_280]
0x1400b3c43  mov     [rbp+270h+var_150], rax
0x1400b3c4a  mov     rax, [r12]
0x1400b3c4e  mov     [rbp+270h+var_278], rax
0x1400b3c52  lea     rax, [rbp+270h+var_278]
0x1400b3c56  mov     [rbp+270h+var_140], rax
0x1400b3c5d  mov     eax, [r12+8]
0x1400b3c62  mov     [rbp+270h+var_2E8], eax
0x1400b3c65  lea     rax, [rbp+270h+var_2E8]
0x1400b3c69  mov     [rbp+270h+var_130], rax
0x1400b3c70  mov     eax, [r12+0Ch]
0x1400b3c75  mov     [rbp+270h+var_2E4], eax
0x1400b3c78  lea     rax, [rbp+270h+var_2E4]
0x1400b3c7c  mov     [rbp+270h+var_120], rax
0x1400b3c83  mov     rax, [r12+10h]
0x1400b3c88  mov     [rbp+270h+var_270], rax
0x1400b3c8c  lea     rax, [rbp+270h+var_270]
0x1400b3c90  mov     [rbp+270h+var_110], rax
0x1400b3c97  mov     rax, [r12+18h]
0x1400b3c9c  mov     [rbp+270h+var_268], rax
0x1400b3ca0  lea     rax, [rbp+270h+var_268]
0x1400b3ca4  mov     [rbp+270h+var_100], rax
0x1400b3cab  mov     eax, [r12+20h]
0x1400b3cb0  mov     [rbp+270h+var_2E0], eax
0x1400b3cb3  lea     rax, [rbp+270h+var_2E0]
0x1400b3cb7  mov     [rbp+270h+var_F0], rax
0x1400b3cbe  mov     eax, [r12+24h]
0x1400b3cc3  mov     [rbp+270h+var_2DC], eax
0x1400b3cc6  lea     rax, [rbp+270h+var_2DC]
0x1400b3cca  mov     [rbp+270h+var_1D8], 4
0x1400b3cd5  mov     [rsp+370h+var_320], r14d
0x1400b3cda  mov     [rbp+270h+var_1C8], 4
0x1400b3ce5  mov     [rbp+270h+var_1B8], 8
0x1400b3cf0  mov     [rbp+270h+var_1A8], 4
0x1400b3cfb  mov     [rbp+270h+var_198], 4
0x1400b3d06  mov     [rbp+270h+var_188], 8
0x1400b3d11  mov     [rbp+270h+var_178], 8
0x1400b3d1c  mov     [rbp+270h+var_168], 4
0x1400b3d27  mov     [rbp+270h+var_158], 4
0x1400b3d32  mov     [rbp+270h+var_148], 8
0x1400b3d3d  mov     [rbp+270h+var_138], 8
0x1400b3d48  mov     [rbp+270h+var_128], 4
0x1400b3d53  mov     [rbp+270h+var_118], 4
0x1400b3d5e  mov     [rbp+270h+var_108], 8
0x1400b3d69  mov     [rbp+270h+var_F8], 8
0x1400b3d74  mov     [rbp+270h+var_E8], 4
0x1400b3d7f  mov     [rbp+270h+var_E0], rax
0x1400b3d86  lea     rdx, byte_14004FD82
0x1400b3d8d  mov     rax, [r12+28h]
0x1400b3d92  xor     r9d, r9d
0x1400b3d95  mov     [rbp+270h+var_260], rax
0x1400b3d99  lea     rax, [rbp+270h+var_260]
0x1400b3d9d  mov     [rbp+270h+var_D0], rax
0x1400b3da4  lea     rax, [rbp+270h+var_258]
0x1400b3da8  mov     [rbp+270h+var_C0], rax
0x1400b3daf  mov     eax, dword ptr [rbp+270h+Buf2+8]
0x1400b3db2  mov     dword ptr [rbp+270h+var_2D8], eax
0x1400b3db5  lea     rax, [rbp+270h+var_2D8]
0x1400b3db9  mov     [rbp+270h+var_B0], rax
0x1400b3dc0  lea     rax, [rsp+370h+var_310]
0x1400b3dc5  mov     [rbp+270h+var_A0], rax
0x1400b3dcc  mov     rax, qword ptr [rbp+270h+var_2C0]
0x1400b3dd0  mov     qword ptr [rbp+270h+var_250], rax
0x1400b3dd4  lea     rax, [rbp+270h+var_250]
0x1400b3dd8  mov     [rbp+270h+var_90], rax
0x1400b3ddf  mov     rax, qword ptr [rbp+270h+var_2C0+8]
0x1400b3de3  mov     qword ptr [rbp+270h+var_250+8], rax
0x1400b3de7  lea     rax, [rbp+270h+var_250+8]
0x1400b3deb  mov     [rbp+270h+var_80], rax
0x1400b3df2  mov     eax, dword ptr [rbp+270h+var_2B0]
0x1400b3df5  mov     dword ptr [rsp+370h+var_308], eax
0x1400b3df9  lea     rax, [rsp+370h+var_308]
0x1400b3dfe  mov     [rbp+270h+var_70], rax
0x1400b3e05  lea     rax, [rsp+370h+var_300]
0x1400b3e0a  mov     [rbp+270h+var_60], rax
0x1400b3e11  mov     rax, qword ptr [rbp+270h+var_2B0+8]
0x1400b3e15  mov     [rbp+270h+var_2A0], rax
0x1400b3e19  lea     rax, [rbp+270h+var_2A0]
0x1400b3e1d  mov     [rbp+270h+var_50], rax
0x1400b3e24  lea     rax, [rbp+270h+var_220]
0x1400b3e28  mov     [rsp+370h+var_348], rax
0x1400b3e2d  mov     dword ptr [rsp+370h+var_350], 1Eh
0x1400b3e35  mov     [rbp+270h+var_D8], 4
0x1400b3e40  mov     [rbp+270h+var_C8], 8
0x1400b3e4b  mov     [rbp+270h+var_258], rbx
0x1400b3e4f  mov     [rbp+270h+var_B8], 8
0x1400b3e5a  mov     [rbp+270h+var_A8], 4
0x1400b3e65  mov     dword ptr [rsp+370h+var_310], r15d
0x1400b3e6a  mov     [rbp+270h+var_98], 4
0x1400b3e75  mov     [rbp+270h+var_88], 8
0x1400b3e80  mov     [rbp+270h+var_78], 8
0x1400b3e8b  mov     [rbp+270h+var_68], 4
0x1400b3e96  mov     dword ptr [rsp+370h+var_300], r13d
  ... truncated ...
```
