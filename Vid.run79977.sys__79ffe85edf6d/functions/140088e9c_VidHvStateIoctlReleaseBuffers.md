# VidHvStateIoctlReleaseBuffers

- ea: `0x140088e9c`
- end: `0x140089b8d`
- name: `VidHvStateIoctlReleaseBuffers`
- size: `3313`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1400321a4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140011518`
- `0x140021c16`
- `0x140021c60`
- `0x140024e18`
- `0x1400305c0`
- `0x140030960`
- `0x140030990`
- `0x1400309d0`
- `0x140088e9c`
- `0x14008acfc`
- `0x14008ad14`
- `0x14008ad30`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400891e1`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140089809`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400891e1`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140089809`
- `ntoskrnl!RtlRbRemoveNode` at `0x140089151`
- `ntoskrnl!RtlRbRemoveNode` at `0x14008977b`
- `ntoskrnl!RtlRbRemoveNode` at `0x140089151`
- `ntoskrnl!RtlRbRemoveNode` at `0x14008977b`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140089021`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140089021`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400899eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400899eb`
- `ntoskrnl!ExAllocatePool2` at `0x140088fc7`
- `ntoskrnl!ExAllocatePool2` at `0x140088fc7`
- `winhvr!WinHvReleaseStateTransferBuffers` at `0x1400890f3`
- `winhvr!WinHvReleaseStateTransferBuffers` at `0x140089522`
- `winhvr!WinHvReleaseStateTransferBuffers` at `0x1400890f3`
- `winhvr!WinHvReleaseStateTransferBuffers` at `0x140089522`

## pseudocode

```c
__int64 __fastcall VidHvStateIoctlReleaseBuffers(__int64 a1, void *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  __int64 v7; // r12
  int v8; // r14d
  int v9; // r8d
  unsigned int v10; // r15d
  size_t v11; // rdi
  _QWORD *Pool2; // rax
  _QWORD *v13; // r13
  __int64 v14; // rax
  __int64 v15; // r12
  __int64 v16; // r13
  __int64 v17; // rdi
  int v18; // r14d
  int v19; // eax
  __int64 v20; // rax
  __int64 *v21; // rax
  __int64 *v22; // rcx
  __int64 *v23; // r13
  __int64 v24; // r8
  __int64 v25; // r15
  unsigned __int64 v26; // r14
  int v27; // r12d
  unsigned __int64 v28; // rax
  __int64 **v29; // rcx
  void *v30; // rdx
  int v31; // r8d
  __int64 *v32; // rax
  __int64 v33; // rcx
  __int64 *v34; // r13
  __int64 v35; // r8
  __int64 v36; // r15
  unsigned __int64 v37; // rdi
  int v38; // r12d
  unsigned __int64 v39; // rax
  _DWORD *v40; // r13
  int v42; // [rsp+20h] [rbp-1178h]
  int v43; // [rsp+30h] [rbp-1168h]
  char v44; // [rsp+40h] [rbp-1158h]
  unsigned int v45; // [rsp+44h] [rbp-1154h] BYREF
  __int64 v46; // [rsp+48h] [rbp-1150h] BYREF
  __int64 v47; // [rsp+50h] [rbp-1148h] BYREF
  __int64 v48; // [rsp+58h] [rbp-1140h] BYREF
  __int64 *v49; // [rsp+60h] [rbp-1138h] BYREF
  __int64 **v50; // [rsp+68h] [rbp-1130h]
  __int64 v51; // [rsp+70h] [rbp-1128h]
  __int64 v52; // [rsp+78h] [rbp-1120h] BYREF
  __int64 v53; // [rsp+80h] [rbp-1118h] BYREF
  PVOID P; // [rsp+88h] [rbp-1110h]
  _QWORD v55[2]; // [rsp+90h] [rbp-1108h] BYREF
  _BYTE v56[32]; // [rsp+A0h] [rbp-10F8h] BYREF
  _BYTE v57[16]; // [rsp+C0h] [rbp-10D8h] BYREF
  _BYTE v58[16]; // [rsp+D0h] [rbp-10C8h] BYREF
  __int64 *v59; // [rsp+E0h] [rbp-10B8h]
  __int64 v60; // [rsp+E8h] [rbp-10B0h]
  __int64 *v61; // [rsp+F0h] [rbp-10A8h]
  __int64 v62; // [rsp+F8h] [rbp-10A0h]
  __int64 v63; // [rsp+100h] [rbp-1098h]
  __int64 v64; // [rsp+108h] [rbp-1090h]
  int *v65; // [rsp+110h] [rbp-1088h]
  __int64 v66; // [rsp+118h] [rbp-1080h]
  __int64 v67; // [rsp+120h] [rbp-1078h]
  int v68; // [rsp+128h] [rbp-1070h] BYREF
  int v69; // [rsp+12Ch] [rbp-106Ch]
  __int64 *v70; // [rsp+130h] [rbp-1068h]
  __int64 v71; // [rsp+138h] [rbp-1060h]
  unsigned int *v72; // [rsp+140h] [rbp-1058h]
  __int64 v73; // [rsp+148h] [rbp-1050h]
  _DWORD *v74; // [rsp+150h] [rbp-1048h]
  __int64 v75; // [rsp+158h] [rbp-1040h]
  _DWORD v76[1020]; // [rsp+160h] [rbp-1038h] BYREF

  v4 = (unsigned int)a3;
  v45 = a3;
  v52 = a1;
  LODWORD(v47) = a3;
  v55[0] = 0;
  P = 0;
  v50 = &v49;
  v49 = (__int64 *)&v49;
  v53 = a1 + 12624;
  if ( !(unsigned __int8)VidOpCtrlStart(a1 + 12624, a2, a3, a4) )
  {
    v44 = 0;
    v7 = 0;
    v51 = 0;
    v8 = -1073741436;
    v43 = -1073741436;
    v9 = 516;
LABEL_3:
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidHvStateIoctlReleaseBuffers",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidhvstate.c",
      v9,
      a1 + 656,
      a1 + 120,
      *(_QWORD *)(a1 + 648),
      v43);
    goto LABEL_72;
  }
  v7 = *(_QWORD *)(a1 + 12720);
  v51 = v7;
  v46 = v7;
  VidLockAcquireExclusive(v7);
  v44 = 1;
  LOBYTE(v48) = 1;
  if ( (unsigned int)v4 > *(_DWORD *)(v7 + 32) )
  {
    v8 = -1073741811;
    v43 = -1073741811;
    v9 = 529;
    goto LABEL_3;
  }
  v10 = 0;
  v11 = 8 * v4;
  Pool2 = (_QWORD *)ExAllocatePool2(256, v11, 1917084758);
  v13 = Pool2;
  P = Pool2;
  v55[1] = Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidHvStateIoctlReleaseBuffers",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidhvstate.c",
      541,
      a1 + 656,
      a1 + 120,
      *(_QWORD *)(a1 + 648),
      -1073741670);
    goto LABEL_72;
  }
  if ( v11 && ((unsigned __int8)a2 & 7) != 0 )
    ExRaiseDatatypeMisalignment();
  RtlCopyFromUser(Pool2, a2, v11);
  v14 = 0;
  LODWORD(v48) = 0;
  if ( !v45 )
    goto LABEL_65;
  v15 = v7 + 64;
  v46 = v15;
  while ( 1 )
  {
    v16 = v13[v14];
    v47 = v16;
    v17 = *(_QWORD *)v15;
    if ( (*(_BYTE *)(v15 + 8) & 1) != 0 )
    {
      if ( v17 )
        v17 ^= v15;
      else
        v17 = 0;
    }
    v18 = *(_BYTE *)(v15 + 8) & 1;
    if ( !v17 )
      goto LABEL_58;
    do
    {
      v19 = VidHvStatepCompareBuffersByMappedAddress(&v47, v17);
      if ( v19 >= 0 )
      {
        if ( v19 <= 0 )
          break;
        v20 = *(_QWORD *)(v17 + 8);
      }
      else
      {
        v20 = *(_QWORD *)v17;
      }
      if ( v18 && v20 )
        v17 ^= v20;
      else
        v17 = v20;
    }
    while ( v17 );
    if ( !v17 )
    {
LABEL_58:
      v8 = -1073741811;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_62;
      tlgCreate1Sz_char(v57, "VidHvStateIoctlReleaseBuffers");
      tlgCreate1Sz_char(v58, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
      LODWORD(v47) = 574;
      v59 = &v47;
      LODWORD(v46) = v31;
      v61 = &v46;
      v63 = a1 + 656;
      v65 = &v68;
      v67 = *(_QWORD *)(a1 + 128);
      v68 = *(unsigned __int16 *)(a1 + 120);
      v52 = *(_QWORD *)(a1 + 648);
      v70 = &v52;
      v48 = v16;
      v72 = (unsigned int *)&v48;
      v73 = 8;
      v42 = 11;
      v30 = &unk_14004734B;
      goto LABEL_61;
    }
    if ( v10 == 1020 )
    {
      v8 = WinHvReleaseStateTransferBuffers(*(_QWORD *)(a1 + 648), 1020, v76, v55);
      if ( v8 >= 0 )
      {
        while ( 1 )
        {
          v21 = v49;
          if ( v49 == (__int64 *)&v49 )
            break;
          if ( (__int64 **)v49[1] != &v49 )
            goto LABEL_93;
          v22 = (__int64 *)*v49;
          if ( *(__int64 **)(*v49 + 8) != v49 )
            goto LABEL_93;
          v49 = (__int64 *)*v49;
          v22[1] = (__int64)&v49;
          v23 = v21 - 3;
          RtlRbRemoveNode(v15, v21 - 3);
          v25 = v51 + 16;
          v26 = *(_QWORD *)(v51 + 16);
          if ( (*(_BYTE *)(v51 + 24) & 1) != 0 )
          {
            if ( v26 )
              v26 ^= v25;
            else
              v26 = 0;
          }
          v27 = *(_BYTE *)(v51 + 24) & 1;
          LOBYTE(v24) = 0;
          if ( v26 )
          {
            while ( 1 )
            {
              if ( (int)VidHvStatepCompareBuffersById(v23 + 5, v26, v24) < 0 )
              {
                v28 = *(_QWORD *)v26;
                if ( v27 )
                {
                  if ( !v28 )
                    goto LABEL_49;
                  v28 ^= v26;
                }
                if ( !v28 )
                {
LABEL_49:
                  LOBYTE(v24) = 0;
                  break;
                }
              }
              else
              {
                v28 = *(_QWORD *)(v26 + 8);
                if ( v27 )
                {
                  if ( !v28 )
                    goto LABEL_43;
                  v28 ^= v26;
                }
                if ( !v28 )
                {
LABEL_43:
                  LOBYTE(v24) = 1;
                  break;
                }
              }
              v26 = v28;
            }
          }
          RtlRbInsertNodeEx(v25, v26, v24, v23);
          *((_DWORD *)v23 + 32) &= 0xFFFFFFFC;
          v15 = v46;
        }
        v10 = 0;
        goto LABEL_52;
      }
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
LABEL_62:
        VidHvStatepDebugState(a1);
        goto LABEL_63;
      }
      tlgCreate1Sz_char(v57, "VidHvStateIoctlReleaseBuffers");
      tlgCreate1Sz_char(v58, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
      LODWORD(v46) = 604;
      v59 = &v46;
      LODWORD(v47) = v8;
      v61 = &v47;
      v63 = a1 + 656;
      v65 = &v68;
      v67 = *(_QWORD *)(a1 + 128);
      v68 = *(unsigned __int16 *)(a1 + 120);
      v52 = *(_QWORD *)(a1 + 648);
      v70 = &v52;
      LOWORD(v48) = 1020;
      v72 = (unsigned int *)&v48;
      v73 = 2;
      v74 = v76;
      v75 = 4080;
      v42 = 12;
      v30 = &unk_1400473C8;
LABEL_61:
      v62 = 4;
      v60 = 4;
      v71 = 8;
      v69 = 0;
      v66 = 2;
      v64 = 16;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v30, 0, 0, v42, v56);
      goto LABEL_62;
    }
LABEL_52:
    v76[v10] = *(_DWORD *)(v17 + 40);
    v29 = v50;
    if ( *v50 != (__int64 *)&v49 )
LABEL_93:
      __fastfail(3u);
    ++v10;
    *(_QWORD *)(v17 + 24) = &v49;
    *(_QWORD *)(v17 + 32) = v29;
    *v29 = (__int64 *)(v17 + 24);
    v50 = (__int64 **)(v17 + 24);
    v14 = (unsigned int)(v48 + 1);
    LODWORD(v48) = v14;
    if ( (unsigned int)v14 >= v45 )
      break;
    v13 = P;
  }
  v7 = v51;
LABEL_65:
  if ( v10 && (v8 = WinHvReleaseStateTransferBuffers(*(_QWORD *)(a1 + 648), v10, v76, v55), v8 < 0) )
  {
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v57, "VidHvStateIoctlReleaseBuffers");
      tlgCreate1Sz_char(v58, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
      LODWORD(v47) = 654;
      v59 = &v47;
      v60 = 4;
      LODWORD(v46) = v8;
      v61 = &v46;
      v62 = 4;
      v63 = a1 + 656;
      v64 = 16;
      v65 = &v68;
      v66 = 2;
      v67 = *(_QWORD *)(a1 + 128);
      v68 = *(unsigned __int16 *)(a1 + 120);
      v69 = 0;
      v52 = *(_QWORD *)(a1 + 648);
      v70 = &v52;
      v71 = 8;
      LOWORD(v48) = v10;
      v72 = (unsigned int *)&v48;
      v73 = 2;
      v74 = v76;
      v75 = 4 * (unsigned int)(unsigned __int16)v10;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_1400472D2, 0, 0, 12, v56);
    }
    VidHvStatepDebugState(a1);
  }
  else
  {
    v8 = 0;
  }
LABEL_72:
  while ( 1 )
  {
    v32 = v49;
    if ( v49 == (__int64 *)&v49 )
      break;
    if ( (__int64 **)v49[1] != &v49 )
      goto LABEL_93;
    v33 = *v49;
    if ( *(__int64 **)(*v49 + 8) != v49 )
      goto LABEL_93;
    v49 = (__int64 *)*v49;
    *(_QWORD *)(v33 + 8) = &v49;
    v34 = v32 - 3;
    RtlRbRemoveNode(v7 + 64, v32 - 3);
    v36 = v7 + 16;
    v37 = *(_QWORD *)(v7 + 16);
    if ( (*(_BYTE *)(v7 + 24) & 1) != 0 )
    {
      if ( v37 )
        v37 ^= v36;
      else
        v37 = 0;
    }
    v38 = *(_BYTE *)(v7 + 24) & 1;
    LOBYTE(v35) = 0;
    if ( v37 )
    {
      while ( 1 )
      {
        if ( (int)VidHvStatepCompareBuffersById(v34 + 5, v37, v35) < 0 )
        {
          v39 = *(_QWORD *)v37;
          if ( v38 )
          {
            if ( !v39 )
              goto LABEL_91;
            v39 ^= v37;
          }
          if ( !v39 )
          {
LABEL_91:
            LOBYTE(v35) = 0;
            break;
          }
        }
        else
        {
          v39 = *(_QWORD *)(v37 + 8);
          if ( v38 )
          {
            if ( !v39 )
              goto LABEL_85;
            v39 ^= v37;
          }
          if ( !v39 )
          {
LABEL_85:
            LOBYTE(v35) = 1;
            break;
          }
        }
        v37 = v39;
      }
    }
    RtlRbInsertNodeEx(v36, v37, v35, v34);
    *((_DWORD *)v34 + 32) &= 0xFFFFFFFC;
LABEL_63:
    v7 = v51;
  }
  if ( v44 )
  {
    VidLockRelease(v7);
    VidOpCtrlFinish(v53);
  }
  v40 = P;
  if ( P )
  {
    if ( v8 < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v57, "VidHvStateIoctlReleaseBuffers");
      tlgCreate1Sz_char(v58, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
      LODWORD(v47) = 703;
      v59 = &v47;
      v60 = 4;
      LODWORD(v46) = v8;
      v61 = &v46;
      v62 = 4;
      v63 = a1 + 656;
      v64 = 16;
      v65 = &v68;
      v66 = 2;
      v67 = *(_QWORD *)(a1 + 128);
      v68 = *(unsigned __int16 *)(a1 + 120);
      v69 = 0;
      v53 = *(_QWORD *)(a1 + 648);
      v70 = &v53;
      v71 = 8;
      LOWORD(v48) = v45;
      v72 = (unsigned int *)&v48;
      v73 = 2;
      v74 = v40;
      v75 = 8 * (unsigned int)(unsigned __int16)v45;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_1400471DD, 0, 0, 12, v56);
    }
    ExFreePoolWithTag(v40, 0x72446456u);
  }
  else if ( v8 < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v57, "VidHvStateIoctlReleaseBuffers");
    tlgCreate1Sz_char(v58, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
    LODWORD(v47) = 712;
    v59 = &v47;
    v60 = 4;
    LODWORD(v46) = v8;
    v61 = &v46;
    v62 = 4;
    v63 = a1 + 656;
    v64 = 16;
    v65 = &v68;
    v66 = 2;
    v67 = *(_QWORD *)(a1 + 128);
    v68 = *(unsigned __int16 *)(a1 + 120);
    v69 = 0;
    v53 = *(_QWORD *)(a1 + 648);
    v70 = &v53;
    v71 = 8;
    v72 = &v45;
    v73 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140047257, 0, 0, 11, v56);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140088e9c  push    rbx
0x140088e9e  push    rsi
0x140088e9f  push    rdi
0x140088ea0  push    r12
0x140088ea2  push    r13
0x140088ea4  push    r14
0x140088ea6  push    r15
0x140088ea8  mov     eax, 1160h
0x140088ead  call    __chkstk_0
0x140088eb2  sub     rsp, rax
0x140088eb5  mov     rax, cs:__security_cookie
0x140088ebc  xor     rax, rsp
0x140088ebf  mov     [rsp+1198h+var_48], rax
0x140088ec7  mov     edi, r8d
0x140088eca  mov     [rsp+1198h+var_1154], edi
0x140088ece  mov     r14, rdx
0x140088ed1  mov     rsi, rcx
0x140088ed4  mov     [rsp+1198h+var_1120], rcx
0x140088ed9  mov     dword ptr [rsp+1198h+var_1148], edi
0x140088edd  xor     ebx, ebx
0x140088edf  mov     [rsp+1198h+var_1108], rbx
0x140088ee7  mov     [rsp+1198h+P], rbx
0x140088eef  lea     rcx, [rsp+1198h+var_1138]
0x140088ef4  mov     [rsp+1198h+var_1130], rcx
0x140088ef9  lea     rax, [rsp+1198h+var_1138]
0x140088efe  mov     [rsp+1198h+var_1138], rax
0x140088f03  lea     r13, [rsi+3150h]
0x140088f0a  mov     [rsp+1198h+var_1118], r13
0x140088f12  mov     rcx, r13
0x140088f15  call    VidOpCtrlStart
0x140088f1a  test    al, al
0x140088f1c  jnz     short loc_140088F6F
0x140088f1e  mov     [rsp+1198h+var_1158], bl
0x140088f22  mov     r12d, ebx
0x140088f25  mov     [rsp+1198h+var_1128], rbx
0x140088f2a  mov     r14d, 0C0000184h
0x140088f30  mov     [rsp+1198h+var_1168], r14d
0x140088f35  mov     r8d, 204h
0x140088f3b  mov     rax, [rsi+288h]
0x140088f42  mov     [rsp+1198h+var_1170], rax
0x140088f47  lea     rcx, [rsi+78h]
0x140088f4b  mov     [rsp+1198h+var_1178], rcx
0x140088f50  lea     r9, [rsi+290h]
0x140088f57  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x140088f5e  lea     rcx, aVidhvstateioct; "VidHvStateIoctlReleaseBuffers"
0x140088f65  call    VidTracePartitionErrorInternal0
0x140088f6a  jmp     loc_140089732
0x140088f6f  mov     r12, [rsi+31B0h]
0x140088f76  mov     [rsp+1198h+var_1128], r12
0x140088f7b  mov     [rsp+1198h+var_1150], r12
0x140088f80  mov     rcx, r12
0x140088f83  call    VidLockAcquireExclusive
0x140088f88  mov     r15b, 1
0x140088f8b  mov     [rsp+1198h+var_1158], r15b
0x140088f90  mov     byte ptr [rsp+1198h+var_1140], r15b
0x140088f95  cmp     edi, [r12+20h]
0x140088f9a  jbe     short loc_140088FB2
0x140088f9c  mov     r8d, 0C000000Dh
0x140088fa2  mov     r14d, r8d
0x140088fa5  mov     [rsp+1198h+var_1168], r8d
0x140088faa  mov     r8d, 211h
0x140088fb0  jmp     short loc_140088F3B
0x140088fb2  mov     r15d, ebx
0x140088fb5  shl     rdi, 3
0x140088fb9  mov     r8d, 72446456h
0x140088fbf  mov     rdx, rdi
0x140088fc2  mov     ecx, 100h
0x140088fc7  call    cs:__imp_ExAllocatePool2
0x140088fce  nop     dword ptr [rax+rax+00h]
0x140088fd3  mov     r13, rax
0x140088fd6  mov     [rsp+1198h+P], rax
0x140088fde  mov     [rsp+1198h+var_1100], rax
0x140088fe6  test    rax, rax
0x140088fe9  jnz     short loc_140089016
0x140088feb  mov     r14d, 0C000009Ah
0x140088ff1  lea     rdx, [rsi+78h]
0x140088ff5  mov     [rsp+1198h+var_1168], r14d
0x140088ffa  mov     rcx, [rsi+288h]
0x140089001  mov     [rsp+1198h+var_1170], rcx
0x140089006  mov     [rsp+1198h+var_1178], rdx
0x14008900b  mov     r8d, 21Dh
0x140089011  jmp     loc_140088F50
0x140089016  test    rdi, rdi
0x140089019  jz      short loc_14008902D
0x14008901b  test    r14b, 7
0x14008901f  jz      short loc_14008902D
0x140089021  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140089028  nop     dword ptr [rax+rax+00h]
0x14008902d  mov     r8, rdi; Size
0x140089030  mov     rdx, r14; Src
0x140089033  mov     rcx, rax; void *
0x140089036  call    RtlCopyFromUser
0x14008903b  nop
0x14008903c  mov     eax, ebx
0x14008903e  mov     dword ptr [rsp+1198h+var_1140], eax
0x140089042  cmp     [rsp+1198h+var_1154], ebx
0x140089046  jbe     loc_1400894FF
0x14008904c  add     r12, 40h ; '@'
0x140089050  mov     [rsp+1198h+var_1150], r12
0x140089055  mov     ecx, 3FCh
0x14008905a  mov     r13, [r13+rax*8+0]
0x14008905f  mov     [rsp+1198h+var_1148], r13
0x140089064  mov     rdi, [r12]
0x140089068  test    byte ptr [r12+8], 1
0x14008906e  jz      short loc_14008907D
0x140089070  test    rdi, rdi
0x140089073  jz      short loc_14008907A
0x140089075  xor     rdi, r12
0x140089078  jmp     short loc_14008907D
0x14008907a  mov     rdi, rbx
0x14008907d  movzx   r14d, byte ptr [r12+8]
0x140089083  and     r14d, 1
0x140089087  test    rdi, rdi
0x14008908a  jz      loc_140089387
0x140089090  mov     rdx, rdi
0x140089093  lea     rcx, [rsp+1198h+var_1148]
0x140089098  call    VidHvStatepCompareBuffersByMappedAddress
0x14008909d  test    eax, eax
0x14008909f  jns     short loc_1400890A6
0x1400890a1  mov     rax, [rdi]
0x1400890a4  jmp     short loc_1400890AC
0x1400890a6  jle     short loc_1400890C3
0x1400890a8  mov     rax, [rdi+8]
0x1400890ac  test    r14d, r14d
0x1400890af  jz      short loc_1400890BB
0x1400890b1  test    rax, rax
0x1400890b4  jz      short loc_1400890BB
0x1400890b6  xor     rdi, rax
0x1400890b9  jmp     short loc_1400890BE
0x1400890bb  mov     rdi, rax
0x1400890be  test    rdi, rdi
0x1400890c1  jnz     short loc_140089090
0x1400890c3  mov     ecx, 3FCh
0x1400890c8  test    rdi, rdi
0x1400890cb  jz      loc_140089387
0x1400890d1  cmp     r15d, ecx
0x1400890d4  jnz     loc_140089202
0x1400890da  lea     r9, [rsp+1198h+var_1108]
0x1400890e2  lea     r8, [rsp+1198h+var_1038]
0x1400890ea  mov     edx, ecx
0x1400890ec  mov     rcx, [rsi+288h]
0x1400890f3  call    cs:__imp_WinHvReleaseStateTransferBuffers
0x1400890fa  nop     dword ptr [rax+rax+00h]
0x1400890ff  mov     r14d, eax
0x140089102  test    eax, eax
0x140089104  js      loc_14008925E
0x14008910a  mov     rax, [rsp+1198h+var_1138]
0x14008910f  lea     rcx, [rsp+1198h+var_1138]
0x140089114  cmp     rax, rcx
0x140089117  jz      loc_1400891FF
0x14008911d  lea     rcx, [rsp+1198h+var_1138]
0x140089122  cmp     [rax+8], rcx
0x140089126  jnz     loc_140089822
0x14008912c  mov     rcx, [rax]
0x14008912f  cmp     [rcx+8], rax
0x140089133  jnz     loc_140089822
0x140089139  mov     [rsp+1198h+var_1138], rcx
0x14008913e  lea     rdx, [rsp+1198h+var_1138]
0x140089143  mov     [rcx+8], rdx
0x140089147  lea     r13, [rax-18h]
0x14008914b  mov     rdx, r13
0x14008914e  mov     rcx, r12
0x140089151  call    cs:__imp_RtlRbRemoveNode
0x140089158  nop     dword ptr [rax+rax+00h]
0x14008915d  mov     rax, [rsp+1198h+var_1128]
0x140089162  lea     r15, [rax+10h]
0x140089166  mov     r14, [r15]
0x140089169  test    byte ptr [rax+18h], 1
0x14008916d  jz      short loc_14008917C
0x14008916f  test    r14, r14
0x140089172  jz      short loc_140089179
0x140089174  xor     r14, r15
0x140089177  jmp     short loc_14008917C
0x140089179  mov     r14, rbx
0x14008917c  movzx   r12d, byte ptr [r15+8]
0x140089181  and     r12d, 1
0x140089185  mov     r8b, bl
0x140089188  test    r14, r14
0x14008918b  jz      short loc_1400891D8
0x14008918d  lea     rax, [r13+28h]
0x140089191  mov     rdx, r14
0x140089194  mov     rcx, rax
0x140089197  call    VidHvStatepCompareBuffersById
0x14008919c  test    eax, eax
0x14008919e  js      short loc_1400891BB
0x1400891a0  mov     rax, [r14+8]
0x1400891a4  test    r12d, r12d
0x1400891a7  jz      short loc_1400891B1
0x1400891a9  test    rax, rax
0x1400891ac  jz      short loc_1400891B6
0x1400891ae  xor     rax, r14
0x1400891b1  test    rax, rax
0x1400891b4  jnz     short loc_1400891D0
0x1400891b6  mov     r8b, 1
0x1400891b9  jmp     short loc_1400891D8
0x1400891bb  mov     rax, [r14]
0x1400891be  test    r12d, r12d
0x1400891c1  jz      short loc_1400891CB
0x1400891c3  test    rax, rax
0x1400891c6  jz      short loc_1400891D5
0x1400891c8  xor     rax, r14
0x1400891cb  test    rax, rax
0x1400891ce  jz      short loc_1400891D5
0x1400891d0  mov     r14, rax
0x1400891d3  jmp     short loc_14008918D
0x1400891d5  mov     r8b, bl
0x1400891d8  mov     r9, r13
0x1400891db  mov     rdx, r14
0x1400891de  mov     rcx, r15
0x1400891e1  call    cs:__imp_RtlRbInsertNodeEx
0x1400891e8  nop     dword ptr [rax+rax+00h]
0x1400891ed  and     dword ptr [r13+80h], 0FFFFFFFCh
0x1400891f5  mov     r12, [rsp+1198h+var_1150]
0x1400891fa  jmp     loc_14008910A
0x1400891ff  mov     r15d, ebx
0x140089202  mov     ecx, r15d
0x140089205  mov     eax, [rdi+28h]
0x140089208  mov     [rsp+rcx*4+1198h+var_1038], eax
0x14008920f  mov     rcx, [rsp+1198h+var_1130]
0x140089214  lea     rax, [rsp+1198h+var_1138]
0x140089219  cmp     [rcx], rax
0x14008921c  jnz     loc_140089822
0x140089222  inc     r15d
0x140089225  lea     rax, [rdi+18h]
0x140089229  lea     rdx, [rsp+1198h+var_1138]
0x14008922e  mov     [rax], rdx
0x140089231  mov     [rax+8], rcx
0x140089235  mov     [rcx], rax
0x140089238  mov     [rsp+1198h+var_1130], rax
0x14008923d  mov     eax, dword ptr [rsp+1198h+var_1140]
0x140089241  inc     eax
0x140089243  mov     dword ptr [rsp+1198h+var_1140], eax
0x140089247  cmp     eax, [rsp+1198h+var_1154]
0x14008924b  jnb     loc_1400894FA
0x140089251  mov     r13, [rsp+1198h+P]
0x140089259  jmp     loc_140089055
0x14008925e  mov     eax, cs:dword_140065110
0x140089264  cmp     eax, 2
0x140089267  jbe     loc_1400894E8
0x14008926d  mov     edx, 100h
0x140089272  lea     rcx, dword_140065110
0x140089279  call    _tlgKeywordOn
0x14008927e  test    al, al
0x140089280  jz      loc_1400894E8
0x140089286  lea     rdx, aVidhvstateioct; "VidHvStateIoctlReleaseBuffers"
0x14008928d  lea     rcx, [rsp+1198h+var_10D8]
0x140089295  call    _tlgCreate1Sz_char
0x14008929a  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x1400892a1  lea     rcx, [rsp+1198h+var_10C8]
0x1400892a9  call    _tlgCreate1Sz_char
0x1400892ae  mov     dword ptr [rsp+1198h+var_1150], 25Ch
0x1400892b6  lea     rax, [rsp+1198h+var_1150]
0x1400892bb  mov     [rsp+1198h+var_10B8], rax
0x1400892c3  mov     dword ptr [rsp+1198h+var_1148], r14d
0x1400892c8  lea     rax, [rsp+1198h+var_1148]
0x1400892cd  mov     [rsp+1198h+var_10A8], rax
0x1400892d5  lea     rax, [rsi+290h]
0x1400892dc  mov     [rsp+1198h+var_1098], rax
0x1400892e4  lea     rax, [rsp+1198h+var_1070]
0x1400892ec  mov     [rsp+1198h+var_1088], rax
0x1400892f4  mov     rax, [rsi+80h]
0x1400892fb  mov     [rsp+1198h+var_1078], rax
0x140089303  movzx   eax, word ptr [rsi+78h]
0x140089307  mov     [rsp+1198h+var_1070], eax
0x14008930e  mov     rax, [rsi+288h]
0x140089315  mov     [rsp+1198h+var_1120], rax
0x14008931a  lea     rax, [rsp+1198h+var_1120]
0x14008931f  mov     [rsp+1198h+var_1068], rax
0x140089327  mov     eax, 3FCh
0x14008932c  mov     word ptr [rsp+1198h+var_1140], ax
0x140089331  lea     rax, [rsp+1198h+var_1140]
0x140089336  mov     [rsp+1198h+var_1058], rax
0x14008933e  mov     [rsp+1198h+var_1050], 2
0x14008934a  lea     rax, [rsp+1198h+var_1038]
0x140089352  mov     [rsp+1198h+var_1048], rax
0x14008935a  mov     [rsp+1198h+var_1040], 0FF0h
0x140089366  lea     rax, [rsp+1198h+var_10F8]
0x14008936e  mov     [rsp+1198h+var_1170], rax
0x140089373  mov     dword ptr [rsp+1198h+var_1178], 0Ch
0x14008937b  lea     rdx, unk_1400473C8
0x140089382  jmp     loc_140089493
0x140089387  mov     r8d, 0C000000Dh
0x14008938d  mov     r14d, r8d
0x140089390  mov     eax, cs:dword_140065110
0x140089396  cmp     eax, 2
0x140089399  jbe     loc_1400894E8
0x14008939f  mov     edx, 100h
0x1400893a4  lea     rcx, dword_140065110
0x1400893ab  call    _tlgKeywordOn
0x1400893b0  test    al, al
0x1400893b2  jz      loc_1400894E8
0x1400893b8  lea     rdx, aVidhvstateioct; "VidHvStateIoctlReleaseBuffers"
0x1400893bf  lea     rcx, [rsp+1198h+var_10D8]
0x1400893c7  call    _tlgCreate1Sz_char
0x1400893cc  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x1400893d3  lea     rcx, [rsp+1198h+var_10C8]
0x1400893db  call    _tlgCreate1Sz_char
0x1400893e0  mov     dword ptr [rsp+1198h+var_1148], 23Eh
0x1400893e8  lea     rax, [rsp+1198h+var_1148]
0x1400893ed  mov     [rsp+1198h+var_10B8], rax
  ... truncated ...
```
