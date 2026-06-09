# AfdReceive

- ea: `0x140022470`
- end: `0x140022d3b`
- name: `AfdReceive`
- size: `2251`
- prototype: `NTSTATUS __fastcall(PIRP Irp, __int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`
- `0x140020500`

## callees

- `0x140008064`
- `0x140008210`
- `0x140014460`
- `0x140022214`
- `0x140022470`
- `0x140022d50`
- `0x14002fd7c`
- `0x140032bf4`
- `0x1400445d8`
- `0x140072840`
- `0x140072870`
- `0x140093b7c`
- `0x140093bcc`
- `0x140093d14`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14002269b`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14002296d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14002269b`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14002296d`
- `ntoskrnl!IofCompleteRequest` at `0x14007828b`
- `ntoskrnl!IofCompleteRequest` at `0x14007828b`
- `ntoskrnl!IofCallDriver` at `0x140022b6b`
- `ntoskrnl!IofCallDriver` at `0x140022b6b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022b01`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140077bc5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140077cc5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140077e3a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14007801f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140078181`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022b01`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140077bc5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140077cc5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140077e3a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14007801f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140078181`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140077ca8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140077ca8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022d29`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022d29`
- `ntoskrnl!ExAllocatePool2` at `0x140077c1e`
- `ntoskrnl!ExAllocatePool2` at `0x140077c1e`
- `ntoskrnl!IoIs32bitProcess` at `0x140022596`
- `ntoskrnl!IoIs32bitProcess` at `0x140022596`

## pseudocode

```c
NTSTATUS __fastcall AfdReceive(PIRP Irp, __int64 a2)
{
  unsigned __int64 v4; // rbx
  char v5; // al
  unsigned int v6; // r14d
  unsigned int v7; // r15d
  int v8; // r12d
  BOOLEAN v10; // al
  unsigned int v11; // ecx
  KPROCESSOR_MODE RequestorMode; // cl
  void *v13; // rdx
  int v14; // ecx
  NTSTATUS v15; // edi
  _WORD *v16; // r14
  KPROCESSOR_MODE v17; // cl
  void *v18; // rdx
  int v19; // ecx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int *v21; // r8
  struct _IO_STACK_LOCATION *v22; // rcx
  unsigned __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rdx
  _WORD *Pool2; // rcx
  __int16 v27; // r14
  __int64 v28; // rdx
  unsigned int *v29; // r8
  __int16 v30; // r14
  unsigned int v31; // r10d
  bool v32; // r11
  IRP *v33; // r9
  char v34; // r13
  bool v35; // cl
  __int64 v36; // rcx
  __int64 v37; // rcx
  unsigned int v38; // r14d
  __int64 *v39; // rax
  __int64 *v40; // r10
  int v41; // edx
  __int64 v42; // rcx
  unsigned int v43; // ecx
  __int64 *v44; // rax
  __int16 v45; // r11
  int v46; // edx
  __int64 v47; // rcx
  unsigned int v48; // ecx
  int v49; // [rsp+20h] [rbp-C8h]
  PMDL MdlAddress; // [rsp+28h] [rbp-C0h]
  int v51; // [rsp+30h] [rbp-B8h]
  int v52; // [rsp+38h] [rbp-B0h]
  int v53; // [rsp+38h] [rbp-B0h]
  PIRP v54; // [rsp+40h] [rbp-A8h]
  PIRP v55; // [rsp+40h] [rbp-A8h]
  bool v56; // [rsp+50h] [rbp-98h]
  int v57; // [rsp+54h] [rbp-94h]
  NTSTATUS v58; // [rsp+54h] [rbp-94h]
  int v59; // [rsp+54h] [rbp-94h]
  NTSTATUS v60; // [rsp+54h] [rbp-94h]
  bool v61; // [rsp+58h] [rbp-90h]
  unsigned int v62; // [rsp+5Ch] [rbp-8Ch] BYREF
  PVOID P; // [rsp+60h] [rbp-88h]
  unsigned __int64 v64; // [rsp+68h] [rbp-80h]
  unsigned int *v65; // [rsp+70h] [rbp-78h]
  PIRP v66; // [rsp+78h] [rbp-70h]
  __int64 v67; // [rsp+80h] [rbp-68h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-60h] BYREF
  __int128 v69; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-38h]

  v66 = Irp;
  memset(&LockHandle, 0, sizeof(LockHandle));
  P = 0;
  LODWORD(v67) = 0;
  v4 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  if ( (*(_BYTE *)(v4 + 7) & 0x10) != 0 )
  {
    v15 = -1073741816;
    v54 = Irp;
    v52 = -1073741816;
    v51 = 0;
    MdlAddress = 0;
    v49 = 0;
    v23 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
    v24 = 4164;
    goto LABEL_71;
  }
  v5 = *(_BYTE *)(v4 + 2);
  if ( v5 != 4 && (*(_WORD *)v4 != 0xAFD1 || v5 != 3) )
  {
    v15 = -1073741811;
    if ( *(_WORD *)v4 != 0xAFD1 )
      v15 = -1073741504;
    v54 = Irp;
    v52 = v15;
    v51 = 0;
    MdlAddress = 0;
    v49 = 0;
    v23 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
    v24 = 4000;
    goto LABEL_71;
  }
  if ( (*(_DWORD *)(v4 + 8) & 0x40000) != 0 )
  {
    v15 = -1073741509;
    v54 = Irp;
    v52 = -1073741509;
    v51 = 0;
    MdlAddress = 0;
    v49 = 0;
    v23 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
    v24 = 4001;
    goto LABEL_71;
  }
  if ( (*(_DWORD *)(v4 + 8) & 0x20000) != 0 )
  {
    v15 = -1073741648;
    v54 = Irp;
    v52 = -1073741648;
    v51 = 0;
    MdlAddress = 0;
    v49 = 0;
    v23 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
    v24 = 4002;
    goto LABEL_71;
  }
  v65 = *(unsigned int **)(*(_QWORD *)(a2 + 48) + 24LL);
  if ( *(_BYTE *)a2 != 14 )
  {
    v6 = 32;
    v64 = 0x2000000002LL;
    v7 = *(_DWORD *)(a2 + 8);
    v62 = v7;
    v8 = 1;
    LODWORD(v67) = 1;
    goto LABEL_7;
  }
  v10 = IoIs32bitProcess(Irp);
  v11 = *(_DWORD *)(a2 + 16);
  v69 = 0;
  if ( !v10 )
  {
    v70 = 0;
    if ( v11 >= 0x18 )
    {
      RequestorMode = Irp->RequestorMode;
      if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      v13 = *(void **)(a2 + 32);
      if ( RequestorMode )
        RtlCopyFromUser(&v69, v13, 0x18u);
      else
        RtlCopyVolatileMemory(&v69, v13, 0x18u);
      v6 = v70;
      v64 = __PAIR64__(v70, HIDWORD(v69));
      v8 = DWORD2(v69);
      v67 = *((_QWORD *)&v69 + 1);
      if ( (v70 & 0x60) != 96 && (v70 & 0x60) != 0 )
      {
        if ( (v70 & 0x40) != 0
          && ((*(_DWORD *)(v4 + 8) & 0x100) == 0 && (*(_DWORD *)(v4 + 16) & 0x100) == 0
           || (*(_DWORD *)(v4 + 8) & 0x80u) != 0) )
        {
          v14 = -1073741637;
          if ( (*(_DWORD *)(v4 + 8) & 0x80u) != 0 )
            v14 = -1073741811;
          v58 = v14;
          AFDETW_TRACERECV(0, 4009, v4, 0, 0, 0, 0, v14, (__int64)Irp, 1);
          v15 = v58;
          v16 = P;
          goto LABEL_66;
        }
        v62 = 0;
        v57 = AfdAllocateMdlChain((__int64)Irp, (_QWORD *)v69, DWORD2(v69), IoWriteAccess, &v62);
        if ( v57 >= 0 )
          goto LABEL_30;
        AFDETW_TRACERECV(0, 4010, v4, 0, 0, 0, 0, v57, (__int64)Irp, 1);
        v15 = v57;
        v16 = P;
      }
      else
      {
        AFDETW_TRACERECV(0, 4008, v4, 0, 0, 0, 0, -1073741811, (__int64)Irp, 1);
        v15 = -1073741811;
        v16 = P;
      }
LABEL_66:
      if ( v16 )
        ExFreePoolWithTag(v16, 0x49646641u);
      Irp->IoStatus.Information = 0;
      Irp->IoStatus.Status = v15;
      IofCompleteRequest(Irp, AfdPriorityBoost);
      return v15;
    }
    v15 = -1073741811;
    v54 = Irp;
    v52 = -1073741811;
    v51 = 0;
    MdlAddress = 0;
    v49 = 0;
    v23 = v4;
    v24 = 4012;
LABEL_71:
    AFDETW_TRACERECV(0, v24, v23, 0, v49, (__int64)MdlAddress, v51, v52, (__int64)v54, 1);
LABEL_72:
    v16 = P;
    goto LABEL_66;
  }
  if ( v11 < 0x10 )
  {
    v15 = -1073741811;
    v54 = Irp;
    v52 = -1073741811;
    v51 = 0;
    MdlAddress = 0;
    v49 = 0;
    v23 = v4;
    v24 = 4007;
    goto LABEL_71;
  }
  v17 = Irp->RequestorMode;
  if ( v17 && (*(_BYTE *)(a2 + 32) & 3) != 0 )
    ExRaiseDatatypeMisalignment();
  v18 = *(void **)(a2 + 32);
  if ( v17 )
    RtlCopyFromUser(&v69, v18, 0x10u);
  else
    RtlCopyVolatileMemory(&v69, v18, 0x10u);
  v6 = HIDWORD(v69);
  v64 = *((_QWORD *)&v69 + 1);
  v8 = DWORD1(v69);
  v67 = *(_QWORD *)((char *)&v69 + 4);
  if ( (BYTE12(v69) & 0x60) == 96 || (BYTE12(v69) & 0x60) == 0 )
  {
    AFDETW_TRACERECV(0, 4003, v4, 0, 0, 0, 0, -1073741811, (__int64)Irp, 1);
    v15 = -1073741811;
    v16 = P;
    goto LABEL_66;
  }
  if ( (BYTE12(v69) & 0x40) != 0
    && ((*(_DWORD *)(v4 + 8) & 0x100) == 0 && (*(_DWORD *)(v4 + 16) & 0x100) == 0 || (*(_DWORD *)(v4 + 8) & 0x80u) != 0) )
  {
    v19 = -1073741637;
    if ( (*(_DWORD *)(v4 + 8) & 0x80u) != 0 )
      v19 = -1073741811;
    v60 = v19;
    AFDETW_TRACERECV(0, 4004, v4, 0, 0, 0, 0, v19, (__int64)Irp, 1);
    v15 = v60;
    v16 = P;
    goto LABEL_66;
  }
  v62 = 0;
  v59 = AfdAllocateMdlChain32((__int64)Irp, (ULONG *)(unsigned int)v69, DWORD1(v69), IoWriteAccess, &v62);
  if ( v59 < 0 )
  {
    AFDETW_TRACERECV(0, 4005, v4, 0, 0, 0, 0, v59, (__int64)Irp, 1);
    v15 = v59;
    v16 = P;
    goto LABEL_66;
  }
LABEL_30:
  if ( *(_WORD *)v4 == 6909 )
  {
    *(_BYTE *)a2 = 3;
    *(_DWORD *)(a2 + 8) = v62;
    return AfdSanRedirectRequest(Irp);
  }
  v7 = v62;
LABEL_7:
  if ( *(_WORD *)v4 == 0xAFD1 )
  {
    *(_QWORD *)&v69 = 0;
    HIDWORD(v70) = 0;
    if ( (v6 & 0x4000) == 0 )
    {
      LOWORD(v70) = v6;
      WORD1(v70) = HIWORD(v64);
      *((_QWORD *)&v69 + 1) = __PAIR64__(v64, v8);
      *(_DWORD *)(a2 + 16) = v7;
      *(_QWORD *)(a2 + 32) = &v69;
      return AfdReceiveDatagram(Irp);
    }
    v15 = -1073741637;
    v54 = Irp;
    v52 = -1073741637;
    v51 = v7;
    MdlAddress = Irp->MdlAddress;
    v49 = v8;
    v23 = v4;
    v24 = 4015;
    goto LABEL_71;
  }
  if ( (*(_DWORD *)(v4 + 8) & 0x100) != 0 || (*(_DWORD *)(v4 + 16) & 0x200) == 0 )
    return AfdBReceive((__int64)Irp, a2, v6, v64, v7, v8);
  AFDETW_TRACERECV(0, 4014, v4, 0, v8, (__int64)Irp->MdlAddress, v7, 0, (__int64)Irp, 1);
  if ( (v6 & 0x4000) != 0 )
  {
    v15 = -1073741637;
    v55 = Irp;
    v53 = -1073741637;
    v25 = 4016;
LABEL_77:
    AFDETW_TRACERECV(1, v25, v4, 0, v8, (__int64)Irp->MdlAddress, v7, v53, (__int64)v55, 1);
    goto LABEL_72;
  }
  Pool2 = (_WORD *)ExAllocatePool2(97, 40, 1231316545);
  P = Pool2;
  Pool2[16] = v6;
  if ( (*(_DWORD *)(v4 + 8) & 0x80u) != 0 )
    Pool2[16] |= 0x60u;
  v27 = Pool2[16];
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 56), &LockHandle);
  v28 = *(unsigned int *)(v4 + 8);
  if ( (v28 & 0x800) != 0 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v15 = -1073741536;
    v55 = Irp;
    v53 = -1073741536;
    v25 = 4018;
    goto LABEL_77;
  }
  if ( (*(_WORD *)v4 & 0xAFD2) != 0xAFD2 || (v29 = *(unsigned int **)(v4 + 192), (v65 = v29) == 0) )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v15 = -1073741504;
    v55 = Irp;
    v53 = -1073741504;
    v25 = 4019;
    goto LABEL_77;
  }
  v30 = v27 & 0x80;
  LOWORD(v62) = v30;
  v31 = v29[1];
  if ( (v31 & 1) != 0 )
  {
    v32 = *((_QWORD *)v29 + 7) > *((_QWORD *)v29 + 8) + *((_QWORD *)v29 + 9) || *((_BYTE *)v29 + 105);
    v33 = (IRP *)(v29 + 24);
  }
  else
  {
    v33 = (IRP *)(v29 + 24);
    v66 = (PIRP)(v29 + 24);
    if ( *((_WORD *)v29 + 48) )
    {
      v32 = 1;
      goto LABEL_94;
    }
    v32 = 0;
  }
  v66 = v33;
LABEL_94:
  v56 = v32;
  if ( (v31 & 1) != 0 )
    v61 = *((_QWORD *)v29 + 10) > *(_QWORD *)&v33->Type + *((_QWORD *)v29 + 11);
  else
    v61 = *((_WORD *)v29 + 49) != 0;
  v34 = v64;
  if ( (v28 & 0x80u) == 0LL )
  {
    v40 = (__int64 *)"PEEK";
  }
  else
  {
    v35 = (v28 & 0x10) != 0;
    if ( v35 && (v64 & 2) == 0 && !v32 && !v61 && (v31 & 0x110) == 0 )
    {
      if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
      {
        WPP_SF_lll(v31 & 1, 10, v29, v29[14], v29[16], v29[18]);
        if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
          WPP_SF_lll(v36, 11, v65, v65[20], v65[22], *(_DWORD *)&v66->Type);
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v15 = -1073741661;
      v55 = Irp;
      v53 = -1073741661;
      v25 = 4020;
      goto LABEL_77;
    }
    v37 = *(unsigned __int8 *)(v4 + 4);
    LOBYTE(v37) = ((v28 & 0x10) != 0) & ((unsigned __int8)v37 >> 4);
    if ( (v37 & 1) != 0 )
    {
      v38 = v29[14] - v29[18] - v29[16];
      v37 = v29[20] - v29[22] - *(_DWORD *)&v33->Type;
      HIDWORD(v64) = v29[20] - v29[22] - *(_DWORD *)&v33->Type;
      if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
      {
        WPP_SF_Ll(v37, v28, v29, v38, v37);
        v29 = v65;
        v37 = HIDWORD(v64);
        v33 = v66;
        v32 = v56;
      }
      if ( v61 && v38 > (unsigned int)v37 || !v32 )
        v38 = v37;
      if ( v7 > v38 )
        v7 = v38;
      v30 = v62;
    }
    if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
    {
      v39 = (__int64 *)"PEEK";
      if ( !v30 )
        v39 = &qword_14007DC38;
      WPP_SF_qlllls(
        (unsigned int)&qword_14007DC38,
        13,
        (_DWORD)v29,
        (_DWORD)v29,
        v7,
        v29[14],
        v29[16],
        v29[18],
        (__int64)v39);
      v29 = v65;
      v33 = v66;
      v32 = v56;
    }
    v40 = (__int64 *)"PEEK";
    if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
    {
      WPP_SF_lll(v37, 14, v29, v29[20], v29[22], *(_DWORD *)&v33->Type);
      v29 = v65;
      v40 = (__int64 *)"PEEK";
      v32 = v56;
    }
    if ( !v30 )
    {
      *((_QWORD *)v29 + 9) += v7;
      *((_QWORD *)v29 + 12) += v7;
    }
  }
  v41 = *(_DWORD *)(v4 + 8);
  v42 = 5;
  v16 = P;
  if ( (*((_WORD *)P + 16) & 0x20) != 0 && (v41 & 0x80u) == 0 )
  {
    LOBYTE(v42) = (v41 & 0x10) != 0;
    if ( ((unsigned __int8)v42 & ((v34 & 2) == 0)) != 0 && !v32 && (v29[1] & 0x110) == 0 )
    {
      if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
        WPP_SF_lll(v42, 15, v29, v29[14], v29[16], v29[18]);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v15 = -1073741661;
      AFDETW_TRACERECV(1, 4021, v4, 0, v8, (__int64)Irp->MdlAddress, v7, -1073741661, (__int64)Irp, 1);
      goto LABEL_66;
    }
    v43 = *(unsigned __int8 *)(v4 + 4);
    LOBYTE(v43) = ((v41 & 0x10) != 0) & ((unsigned __int8)v43 >> 4);
    if ( (v43 & 1) != 0 )
    {
      v43 = v29[14] - v29[18] - v29[16];
      if ( v7 > v43 )
        v7 = v29[14] - v29[18] - v29[16];
    }
    if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
    {
      v44 = (__int64 *)"PEEK";
      if ( !(_WORD)v62 )
        v44 = &qword_14007DC38;
      WPP_SF_qlllls(v43, 16, (_DWORD)v29, (_DWORD)v29, v7, v29[14], v29[16], v29[18], (__int64)v44);
      v29 = v65;
      v40 = (__int64 *)"PEEK";
    }
    v45 = v62;
    if ( !(_WORD)v62 )
      *((_QWORD *)v29 + 9) += v7;
  }
  else
  {
    v45 = v62;
  }
  v46 = *(_DWORD *)(v4 + 8);
  v47 = 6;
  if ( (v16[16] & 0x40) != 0 && (v46 & 0x80u) == 0 )
  {
    LOBYTE(v47) = (v46 & 0x10) != 0;
    if ( ((unsigned __int8)v47 & ((v34 & 2) == 0)) != 0 && !v61 && (v29[1] & 0x110) == 0 )
    {
      if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
        WPP_SF_lll(v47, 17, v29, v29[20], v29[22], v29[24]);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v15 = -1073741661;
      AFDETW_TRACERECV(1, 4022, v4, 0, v8, (__int64)Irp->MdlAddress, v7, -1073741661, (__int64)Irp, 1);
      goto LABEL_66;
    }
    v48 = *(unsigned __int8 *)(v4 + 4);
    LOBYTE(v48) = ((v46 & 0x10) != 0) & ((unsigned __int8)v48 >> 4);
    if ( (v48 & 1) == 0 )
      goto LABEL_156;
    if ( (v29[1] & 1) != 0 )
    {
      if ( *((_QWORD *)v29 + 10) <= *((_QWORD *)v29 + 11) + *((_QWORD *)v29 + 12) )
        goto LABEL_156;
    }
    else if ( !*((_WORD *)v29 + 49) )
    {
LABEL_156:
      if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
      {
        if ( !v45 )
          v40 = &qword_14007DC38;
        WPP_SF_qlllls(v48, 18, (_DWORD)v29, (_DWORD)v29, v7, v29[20], v29[22], v29[24], (__int64)v40);
        v29 = v65;
        v45 = v62;
      }
      if ( !v45 )
        *((_QWORD *)v29 + 12) += v7;
      goto LABEL_53;
    }
    v48 = v29[20] - v29[24] - v29[22];
    if ( v7 > v48 )
      v7 = v29[20] - v29[24] - v29[22];
    goto LABEL_156;
  }
LABEL_53:
  if ( _InterlockedIncrement64((volatile signed __int64 *)v29 + 6) <= 1 )
    __fastfail(0xEu);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)AfdRestartReceive;
  v21 = v65;
  CurrentStackLocation[-1].Context = v65;
  CurrentStackLocation[-1].Control = -32;
  v22 = Irp->Tail.Overlay.CurrentStackLocation;
  *(_WORD *)&v22[-1].MajorFunction = 2063;
  v22[-1].DeviceObject = (PDEVICE_OBJECT)*((_QWORD *)v21 + 3);
  v22[-1].FileObject = (PFILE_OBJECT)*((_QWORD *)v21 + 2);
  *(&v22[-1].Parameters.Read.Length + 1) = (unsigned __int16)v16[16];
  v22[-1].Parameters.Read.Length = v7;
  *(_QWORD *)(a2 + 32) = v16;
  *(_DWORD *)(a2 + 8) = v7;
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 248));
  return IofCallDriver(*((PDEVICE_OBJECT *)v21 + 3), Irp);
}

```

## disassembly

```asm
0x140022470  mov     r11, rsp
0x140022473  mov     [r11+18h], rbx
0x140022477  mov     [r11+20h], rsi
0x14002247b  push    rdi
0x14002247c  push    r12
0x14002247e  push    r13
0x140022480  push    r14
0x140022482  push    r15
0x140022484  sub     rsp, 0C0h
0x14002248b  mov     rax, cs:__security_cookie
0x140022492  xor     rax, rsp
0x140022495  mov     [rsp+0E8h+var_30], rax
0x14002249d  mov     rdi, rdx
0x1400224a0  mov     rsi, rcx
0x1400224a3  mov     [rsp+0E8h+var_70], rcx
0x1400224a8  xorps   xmm0, xmm0
0x1400224ab  xor     eax, eax
0x1400224ad  movups  xmmword ptr [r11-60h], xmm0
0x1400224b2  mov     [r11-50h], rax
0x1400224b6  mov     [rsp+0E8h+P], rax
0x1400224bb  mov     [r11-68h], eax
0x1400224bf  mov     rbx, [rdx+30h]
0x1400224c3  mov     rbx, [rbx+18h]
0x1400224c7  test    byte ptr [rbx+7], 10h
0x1400224cb  jnz     loc_140022B7C
0x1400224d1  movzx   eax, byte ptr [rbx+2]
0x1400224d5  mov     r13d, 0AFD1h
0x1400224db  cmp     al, 4
0x1400224dd  jnz     loc_140022BAC
0x1400224e3  mov     eax, [rbx+8]
0x1400224e6  shr     eax, 10h
0x1400224e9  test    al, 4
0x1400224eb  jnz     loc_140022BC6
0x1400224f1  test    al, 2
0x1400224f3  jnz     loc_140022C02
0x1400224f9  mov     [rsp+0E8h+var_78], rbx
0x1400224fe  cmp     byte ptr [rdx], 0Eh
0x140022501  jz      loc_140022593
0x140022507  mov     r14d, 20h ; ' '
0x14002250d  mov     dword ptr [rsp+0E8h+var_80+4], r14d
0x140022512  mov     dword ptr [rsp+0E8h+var_80], 2
0x14002251a  mov     r15d, [rdx+8]
0x14002251e  mov     [rsp+0E8h+var_8C], r15d
0x140022523  mov     r12d, 1
0x140022529  mov     dword ptr [rsp+0E8h+var_68], r12d
0x140022531  cmp     [rbx], r13w
0x140022535  jz      loc_140022827
0x14002253b  mov     eax, [rbx+8]
0x14002253e  bt      eax, 8
0x140022542  jnb     loc_140077B56
0x140022548  mov     [rsp+0E8h+var_C0], r12d; int
0x14002254d  mov     [rsp+0E8h+var_C8], r15d; int
0x140022552  mov     r9d, dword ptr [rsp+0E8h+var_80]
0x140022557  mov     r8d, r14d
0x14002255a  mov     rdx, rdi
0x14002255d  mov     rcx, rsi; Irp
0x140022560  call    AfdBReceive
0x140022565  mov     rcx, [rsp+0E8h+var_30]
0x14002256d  xor     rcx, rsp; StackCookie
0x140022570  call    __security_check_cookie
0x140022575  lea     r11, [rsp+0E8h+var_28]
0x14002257d  mov     rbx, [r11+40h]
0x140022581  mov     rsi, [r11+48h]
0x140022585  mov     rsp, r11
0x140022588  pop     r15
0x14002258a  pop     r14
0x14002258c  pop     r13
0x14002258e  pop     r12
0x140022590  pop     rdi
0x140022591  retn
0x140022593  mov     rcx, rsi; Irp
0x140022596  call    cs:__imp_IoIs32bitProcess
0x14002259d  nop     dword ptr [rax+rax+00h]
0x1400225a2  mov     ecx, [rdi+10h]
0x1400225a5  xorps   xmm0, xmm0
0x1400225a8  movups  [rsp+0E8h+var_48], xmm0
0x1400225b0  test    al, al
0x1400225b2  jnz     loc_140022894
0x1400225b8  xor     eax, eax
0x1400225ba  mov     [rsp+0E8h+var_38], rax
0x1400225c2  cmp     ecx, 18h
0x1400225c5  jb      loc_140022C96
0x1400225cb  mov     [rsp+0E8h+var_94], eax
0x1400225cf  movzx   ecx, byte ptr [rsi+40h]
0x1400225d3  test    cl, cl
0x1400225d5  jz      short loc_1400225E1
0x1400225d7  test    byte ptr [rdi+20h], 3
0x1400225db  jnz     loc_14002269B
0x1400225e1  mov     rdx, [rdi+20h]; Src
0x1400225e5  mov     r8d, 18h; Size
0x1400225eb  test    cl, cl
0x1400225ed  lea     rcx, [rsp+0E8h+var_48]; void *
0x1400225f5  jz      loc_140022691
0x1400225fb  call    RtlCopyFromUser
0x140022600  mov     r14, [rsp+0E8h+var_38]
0x140022608  mov     dword ptr [rsp+0E8h+var_80+4], r14d
0x14002260d  mov     r15d, dword ptr [rsp+0E8h+var_48+0Ch]
0x140022615  mov     dword ptr [rsp+0E8h+var_80], r15d
0x14002261a  mov     dword ptr [rsp+0E8h+var_68+4], r15d
0x140022622  mov     rdx, qword ptr [rsp+0E8h+var_48]
0x14002262a  mov     r12d, dword ptr [rsp+0E8h+var_48+8]
0x140022632  mov     dword ptr [rsp+0E8h+var_68], r12d
0x14002263a  mov     eax, r14d
0x14002263d  and     eax, 60h
0x140022640  cmp     eax, 60h ; '`'
0x140022643  setnz   cl
0x140022646  test    eax, eax
0x140022648  setnz   al
0x14002264b  test    al, cl
0x14002264d  jz      loc_14002276D
0x140022653  test    r14b, 40h
0x140022657  jnz     short loc_1400226A8
0x140022659  mov     [rsp+0E8h+var_8C], 0
0x140022661  lea     rax, [rsp+0E8h+var_8C]
0x140022666  mov     qword ptr [rsp+0E8h+var_C8], rax
0x14002266b  mov     r9d, 1
0x140022671  mov     r8d, r12d
0x140022674  mov     rcx, rsi
0x140022677  call    AfdAllocateMdlChain
0x14002267c  mov     [rsp+0E8h+var_94], eax
0x140022680  mov     eax, [rsp+0E8h+var_94]
0x140022684  test    eax, eax
0x140022686  js      loc_140022722
0x14002268c  jmp     loc_14002280F
0x140022691  call    RtlCopyVolatileMemory
0x140022696  jmp     loc_140022600
0x14002269b  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400226a2  nop     dword ptr [rax+rax+00h]
0x1400226a7  int     3; Trap to Debugger
0x1400226a8  mov     eax, [rbx+8]
0x1400226ab  bt      eax, 8
0x1400226af  jb      short loc_1400226BA
0x1400226b1  test    dword ptr [rbx+10h], 100h
0x1400226b8  jz      short loc_1400226C1
0x1400226ba  mov     eax, [rbx+8]
0x1400226bd  test    al, al
0x1400226bf  jns     short loc_140022659
0x1400226c1  mov     eax, [rbx+8]
0x1400226c4  test    al, 80h
0x1400226c6  mov     ecx, 0C00000BBh
0x1400226cb  mov     eax, 0C000000Dh
0x1400226d0  cmovnz  ecx, eax
0x1400226d3  mov     [rsp+0E8h+var_94], ecx
0x1400226d7  mov     [rsp+0E8h+var_A0], 1
0x1400226dc  mov     [rsp+0E8h+var_A8], rsi
0x1400226e1  mov     eax, [rsp+0E8h+var_94]
0x1400226e5  mov     [rsp+0E8h+var_B0], eax
0x1400226e9  mov     [rsp+0E8h+var_B8], 0
0x1400226f1  mov     qword ptr [rsp+0E8h+var_C0], 0
0x1400226fa  mov     [rsp+0E8h+var_C8], 0
0x140022702  xor     r9d, r9d
0x140022705  mov     r8, rbx
0x140022708  mov     edx, 0FA9h
0x14002270d  xor     ecx, ecx
0x14002270f  call    AFDETW_TRACERECV
0x140022714  mov     edi, [rsp+0E8h+var_94]
0x140022718  mov     r14, [rsp+0E8h+P]
0x14002271d  jmp     loc_140022D18
0x140022722  mov     [rsp+0E8h+var_A0], 1
0x140022727  mov     [rsp+0E8h+var_A8], rsi
0x14002272c  mov     eax, [rsp+0E8h+var_94]
0x140022730  mov     [rsp+0E8h+var_B0], eax
0x140022734  mov     [rsp+0E8h+var_B8], 0
0x14002273c  mov     qword ptr [rsp+0E8h+var_C0], 0
0x140022745  mov     [rsp+0E8h+var_C8], 0
0x14002274d  xor     r9d, r9d
0x140022750  mov     r8, rbx
0x140022753  mov     edx, 0FAAh
0x140022758  xor     ecx, ecx
0x14002275a  call    AFDETW_TRACERECV
0x14002275f  mov     edi, [rsp+0E8h+var_94]
0x140022763  mov     r14, [rsp+0E8h+P]
0x140022768  jmp     loc_140022D18
0x14002276d  mov     eax, 0C000000Dh
0x140022772  mov     [rsp+0E8h+var_94], eax
0x140022776  mov     [rsp+0E8h+var_A0], 1
0x14002277b  mov     [rsp+0E8h+var_A8], rsi
0x140022780  mov     eax, [rsp+0E8h+var_94]
0x140022784  mov     [rsp+0E8h+var_B0], eax
0x140022788  mov     [rsp+0E8h+var_B8], 0
0x140022790  mov     qword ptr [rsp+0E8h+var_C0], 0
0x140022799  mov     [rsp+0E8h+var_C8], 0
0x1400227a1  xor     r9d, r9d
0x1400227a4  mov     r8, rbx
0x1400227a7  mov     edx, 0FA8h
0x1400227ac  xor     ecx, ecx
0x1400227ae  call    AFDETW_TRACERECV
0x1400227b3  mov     edi, [rsp+0E8h+var_94]
0x1400227b7  mov     r14, [rsp+0E8h+P]
0x1400227bc  jmp     loc_140022D18
0x1400227c1  mov     [rsp+0E8h+var_A0], 1
0x1400227c6  mov     rsi, [rsp+0E8h+var_70]
0x1400227cb  mov     [rsp+0E8h+var_A8], rsi
0x1400227d0  mov     edi, [rsp+0E8h+var_94]
0x1400227d4  mov     [rsp+0E8h+var_B0], edi
0x1400227d8  mov     [rsp+0E8h+var_B8], 0
0x1400227e0  mov     qword ptr [rsp+0E8h+var_C0], 0
0x1400227e9  mov     [rsp+0E8h+var_C8], 0
0x1400227f1  xor     r9d, r9d
0x1400227f4  mov     r8, [rsp+0E8h+var_78]
0x1400227f9  mov     edx, 0FABh
0x1400227fe  xor     ecx, ecx
0x140022800  call    AFDETW_TRACERECV
0x140022805  mov     r14, [rsp+0E8h+P]
0x14002280a  jmp     loc_140022D18
0x14002280f  mov     eax, 1AFDh
0x140022814  cmp     [rbx], ax
0x140022817  jz      loc_140022C7C
0x14002281d  mov     r15d, [rsp+0E8h+var_8C]
0x140022822  jmp     loc_140022531
0x140022827  mov     qword ptr [rsp+0E8h+var_48], 0
0x140022833  mov     dword ptr [rsp+0E8h+var_38+4], 0
0x14002283e  bt      r14d, 0Eh
0x140022843  jb      loc_140022CD4
0x140022849  mov     word ptr [rsp+0E8h+var_38], r14w
0x140022852  movzx   eax, word ptr [rsp+0E8h+var_80+6]
0x140022857  mov     word ptr [rsp+0E8h+var_38+2], ax
0x14002285f  mov     r13d, dword ptr [rsp+0E8h+var_80]
0x140022864  mov     dword ptr [rsp+0E8h+var_48+0Ch], r13d
0x14002286c  mov     dword ptr [rsp+0E8h+var_48+8], r12d
0x140022874  mov     [rdi+10h], r15d
0x140022878  lea     rax, [rsp+0E8h+var_48]
0x140022880  mov     [rdi+20h], rax
0x140022884  mov     rdx, rdi
0x140022887  mov     rcx, rsi; Irp
0x14002288a  call    AfdReceiveDatagram
0x14002288f  jmp     loc_140022565
0x140022894  cmp     ecx, 10h
0x140022897  jb      loc_140022C3E
0x14002289d  mov     [rsp+0E8h+var_94], 0
0x1400228a5  movzx   ecx, byte ptr [rsi+40h]
0x1400228a9  test    cl, cl
0x1400228ab  jz      short loc_1400228B7
0x1400228ad  test    byte ptr [rdi+20h], 3
0x1400228b1  jnz     loc_14002296D
0x1400228b7  mov     rdx, [rdi+20h]; Src
0x1400228bb  mov     r8d, 10h; Size
0x1400228c1  test    cl, cl
0x1400228c3  lea     rcx, [rsp+0E8h+var_48]; void *
0x1400228cb  jz      loc_140022963
0x1400228d1  call    RtlCopyFromUser
0x1400228d6  mov     r14d, dword ptr [rsp+0E8h+var_48+0Ch]
0x1400228de  mov     dword ptr [rsp+0E8h+var_80+4], r14d
0x1400228e3  mov     eax, dword ptr [rsp+0E8h+var_48+8]
0x1400228ea  mov     dword ptr [rsp+0E8h+var_80], eax
0x1400228ee  mov     dword ptr [rsp+0E8h+var_68+4], eax
0x1400228f5  mov     edx, dword ptr [rsp+0E8h+var_48]
0x1400228fc  mov     r12d, dword ptr [rsp+0E8h+var_48+4]
0x140022904  mov     dword ptr [rsp+0E8h+var_68], r12d
0x14002290c  mov     eax, r14d
0x14002290f  and     eax, 60h
0x140022912  cmp     eax, 60h ; '`'
0x140022915  setnz   cl
0x140022918  test    eax, eax
0x14002291a  setnz   al
0x14002291d  test    al, cl
0x14002291f  jz      loc_140022A3F
0x140022925  test    r14b, 40h
0x140022929  jnz     short loc_14002297A
0x14002292b  mov     [rsp+0E8h+var_8C], 0
0x140022933  lea     rax, [rsp+0E8h+var_8C]
0x140022938  mov     qword ptr [rsp+0E8h+var_C8], rax
0x14002293d  mov     r9d, 1
0x140022943  mov     r8d, r12d
0x140022946  mov     rcx, rsi
0x140022949  call    AfdAllocateMdlChain32
0x14002294e  mov     [rsp+0E8h+var_94], eax
0x140022952  mov     eax, [rsp+0E8h+var_94]
0x140022956  test    eax, eax
0x140022958  js      loc_1400229F4
0x14002295e  jmp     loc_14002280F
0x140022963  call    RtlCopyVolatileMemory
0x140022968  jmp     loc_1400228D6
0x14002296d  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140022974  nop     dword ptr [rax+rax+00h]
0x140022979  int     3; Trap to Debugger
0x14002297a  mov     eax, [rbx+8]
0x14002297d  bt      eax, 8
0x140022981  jb      short loc_14002298C
0x140022983  test    dword ptr [rbx+10h], 100h
0x14002298a  jz      short loc_140022993
0x14002298c  mov     eax, [rbx+8]
0x14002298f  test    al, al
0x140022991  jns     short loc_14002292B
0x140022993  mov     eax, [rbx+8]
0x140022996  test    al, 80h
0x140022998  mov     ecx, 0C00000BBh
0x14002299d  mov     eax, 0C000000Dh
0x1400229a2  cmovnz  ecx, eax
0x1400229a5  mov     [rsp+0E8h+var_94], ecx
0x1400229a9  mov     [rsp+0E8h+var_A0], 1
0x1400229ae  mov     [rsp+0E8h+var_A8], rsi
0x1400229b3  mov     eax, [rsp+0E8h+var_94]
0x1400229b7  mov     [rsp+0E8h+var_B0], eax
0x1400229bb  mov     [rsp+0E8h+var_B8], 0
0x1400229c3  mov     qword ptr [rsp+0E8h+var_C0], 0
0x1400229cc  mov     [rsp+0E8h+var_C8], 0
0x1400229d4  xor     r9d, r9d
0x1400229d7  mov     r8, rbx
0x1400229da  mov     edx, 0FA4h
  ... truncated ...
```
