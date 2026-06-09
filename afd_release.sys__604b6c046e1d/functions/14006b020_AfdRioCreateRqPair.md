# AfdRioCreateRqPair

- ea: `0x14006b020`
- end: `0x14006b956`
- name: `AfdRioCreateRqPair`
- size: `2358`
- prototype: `__int64 __fastcall(_WORD *, void *, unsigned int, KPROCESSOR_MODE)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1400064f0`

## callees

- `0x140006b4c`
- `0x140006d68`
- `0x14000f390`
- `0x14002fd5c`
- `0x1400329c4`
- `0x1400336e0`
- `0x14004031c`
- `0x1400445b8`
- `0x140069f94`
- `0x14006b020`
- `0x14006c300`
- `0x1400726a0`
- `0x1400726d0`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14006b120`
- `ntoskrnl!ExRaiseStatus` at `0x14006b1fe`
- `ntoskrnl!ExRaiseStatus` at `0x14006b293`
- `ntoskrnl!ExRaiseStatus` at `0x14006b306`
- `ntoskrnl!ExRaiseStatus` at `0x14006b389`
- `ntoskrnl!ExRaiseStatus` at `0x14006b3fe`
- `ntoskrnl!ExRaiseStatus` at `0x14006b447`
- `ntoskrnl!ExRaiseStatus` at `0x14006b458`
- `ntoskrnl!ExRaiseStatus` at `0x14006b469`
- `ntoskrnl!ExRaiseStatus` at `0x14006b47a`
- `ntoskrnl!ExRaiseStatus` at `0x14006b120`
- `ntoskrnl!ExRaiseStatus` at `0x14006b1fe`
- `ntoskrnl!ExRaiseStatus` at `0x14006b293`
- `ntoskrnl!ExRaiseStatus` at `0x14006b306`
- `ntoskrnl!ExRaiseStatus` at `0x14006b389`
- `ntoskrnl!ExRaiseStatus` at `0x14006b3fe`
- `ntoskrnl!ExRaiseStatus` at `0x14006b447`
- `ntoskrnl!ExRaiseStatus` at `0x14006b458`
- `ntoskrnl!ExRaiseStatus` at `0x14006b469`
- `ntoskrnl!ExRaiseStatus` at `0x14006b47a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006b2e0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006b3d8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006b2e0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006b3d8`
- `ntoskrnl!IoFreeMdl` at `0x14006b8f7`
- `ntoskrnl!IoFreeMdl` at `0x14006b924`
- `ntoskrnl!IoFreeMdl` at `0x14006b8f7`
- `ntoskrnl!IoFreeMdl` at `0x14006b924`
- `ntoskrnl!MmUnlockPages` at `0x14006b8e8`
- `ntoskrnl!MmUnlockPages` at `0x14006b915`
- `ntoskrnl!MmUnlockPages` at `0x14006b8e8`
- `ntoskrnl!MmUnlockPages` at `0x14006b915`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006b2a8`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006b39e`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006b2a8`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006b39e`
- `ntoskrnl!IoAllocateMdl` at `0x14006b272`
- `ntoskrnl!IoAllocateMdl` at `0x14006b368`
- `ntoskrnl!IoAllocateMdl` at `0x14006b272`
- `ntoskrnl!IoAllocateMdl` at `0x14006b368`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006b148`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006b148`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b6ae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b708`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b77f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b795`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b7b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b6ae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b708`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b77f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b795`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b7b0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b67d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b6d7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b730`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b67d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b6d7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b730`
- `ntoskrnl!IoIs32bitProcess` at `0x14006b0fe`
- `ntoskrnl!IoIs32bitProcess` at `0x14006b0fe`

## pseudocode

```c
__int64 __fastcall AfdRioCreateRqPair(_WORD *a1, void *a2, unsigned int a3, KPROCESSOR_MODE a4)
{
  unsigned int v7; // ebx
  unsigned int v8; // esi
  ULONG v9; // edx
  void *v10; // r10
  struct _MDL *Mdl; // rax
  struct _MDL *v12; // r13
  _BYTE *MappedSystemVa; // rax
  ULONG v14; // edx
  void *v15; // r10
  struct _MDL *v16; // rax
  struct _MDL *v17; // r12
  __int64 v18; // rdx
  _BYTE *v19; // rax
  __int64 v20; // r14
  int v21; // esi
  __int64 RioState; // rax
  __int64 v23; // rcx
  _BYTE *v24; // rax
  _BYTE *v25; // rax
  __int64 v26; // rax
  KSPIN_LOCK *v27; // rcx
  __int64 v28; // rcx
  unsigned int v29; // edx
  __int64 v30; // rcx
  unsigned int v31; // edx
  KSPIN_LOCK *v32; // rbx
  __int64 v34; // rcx
  __int64 v35; // rcx
  signed __int32 v36[8]; // [rsp+0h] [rbp-208h] BYREF
  BOOLEAN v37; // [rsp+70h] [rbp-198h]
  KPROCESSOR_MODE v38; // [rsp+71h] [rbp-197h]
  BOOLEAN v39; // [rsp+72h] [rbp-196h]
  KPROCESSOR_MODE v40; // [rsp+78h] [rbp-190h]
  bool v41; // [rsp+80h] [rbp-188h]
  unsigned int v42; // [rsp+84h] [rbp-184h]
  int v43; // [rsp+88h] [rbp-180h]
  int v44; // [rsp+8Ch] [rbp-17Ch]
  int v45; // [rsp+90h] [rbp-178h]
  int v46; // [rsp+94h] [rbp-174h]
  KSPIN_LOCK *v47; // [rsp+98h] [rbp-170h]
  int v48; // [rsp+A0h] [rbp-168h]
  int v49; // [rsp+A4h] [rbp-164h]
  __int64 v50; // [rsp+A8h] [rbp-160h] BYREF
  _BYTE *v51; // [rsp+B0h] [rbp-158h]
  _BYTE *v52; // [rsp+B8h] [rbp-150h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C0h] [rbp-148h] BYREF
  __int64 v54; // [rsp+D8h] [rbp-130h]
  __int64 v55; // [rsp+E0h] [rbp-128h]
  __int64 v56; // [rsp+E8h] [rbp-120h]
  _WORD *v57; // [rsp+F0h] [rbp-118h]
  __int64 v58; // [rsp+F8h] [rbp-110h]
  __int64 v59; // [rsp+100h] [rbp-108h]
  __int128 v60; // [rsp+108h] [rbp-100h]
  __int128 v61; // [rsp+118h] [rbp-F0h]
  __int128 v62; // [rsp+128h] [rbp-E0h]
  unsigned __int64 v63; // [rsp+138h] [rbp-D0h]
  __int128 v64; // [rsp+140h] [rbp-C8h]
  __int128 v65; // [rsp+150h] [rbp-B8h]
  __int128 v66; // [rsp+160h] [rbp-A8h]
  unsigned __int64 v67; // [rsp+170h] [rbp-98h]
  _WORD *v68; // [rsp+178h] [rbp-90h]
  _QWORD v69[8]; // [rsp+180h] [rbp-88h] BYREF

  v38 = a4;
  v57 = a1;
  v68 = a1;
  v47 = (KSPIN_LOCK *)a1;
  v40 = a4;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v50 = 0;
  v54 = 0;
  v55 = 0;
  v43 = -1073741568;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v41 = *a1 != 0xAFD1;
  v37 = IoIs32bitProcess(0);
  v39 = v37;
  if ( a3 < 0x40 )
    ExRaiseStatus(-1073741811);
  memset(v69, 0, sizeof(v69));
  if ( a4 )
  {
    if ( ((unsigned __int8)a2 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(v69, a2, 0x40u);
  }
  else
  {
    RtlCopyVolatileMemory(v69, a2, 0x40u);
  }
  v48 = HIDWORD(v69[4]);
  v67 = __PAIR64__(v69[4], HIDWORD(v69[4]));
  v49 = v69[2];
  v63 = __PAIR64__(HIDWORD(v69[1]), v69[2]);
  v7 = v69[4];
  v44 = v69[4];
  v8 = HIDWORD(v69[1]);
  v42 = HIDWORD(v69[1]);
  if ( !HIDWORD(v69[1]) || !LODWORD(v69[4]) )
    ExRaiseStatus(-1073741811);
  if ( HIDWORD(v69[1]) == 1 && LODWORD(v69[4]) == 1 )
    ExRaiseStatus(-1073741811);
  if ( HIDWORD(v69[1]) > 0x4924924 || LODWORD(v69[4]) > 0x4924924 )
    ExRaiseStatus(-1073741811);
  v45 = v69[1];
  LODWORD(v64) = v69[1];
  v58 = v69[5];
  *(_QWORD *)&v66 = v69[5];
  if ( !v69[5] || !(unsigned __int8)AfdRioCheckRqBufferSize(LODWORD(v69[4])) )
    ExRaiseStatus(-1073741811);
  Mdl = IoAllocateMdl(v10, v9, 0, 1u, 0);
  v12 = Mdl;
  *(_QWORD *)&v65 = Mdl;
  if ( !Mdl )
    ExRaiseStatus(-1073741801);
  MmProbeAndLockPages(Mdl, a4, IoWriteAccess);
  BYTE8(v65) = 1;
  if ( (v12->MdlFlags & 5) != 0 )
    MappedSystemVa = v12->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v12, 0, MmCached, 0, 0, 0x40000010u);
  v51 = MappedSystemVa;
  *((_QWORD *)&v66 + 1) = MappedSystemVa;
  if ( !MappedSystemVa )
    ExRaiseStatus(-1073741670);
  v46 = HIDWORD(v69[0]);
  LODWORD(v60) = HIDWORD(v69[0]);
  v59 = v69[3];
  *(_QWORD *)&v62 = v69[3];
  if ( !v69[3] || !(unsigned __int8)AfdRioCheckRqBufferSize(v8) )
    ExRaiseStatus(-1073741811);
  v16 = IoAllocateMdl(v15, v14, 0, 1u, 0);
  v17 = v16;
  *(_QWORD *)&v61 = v16;
  if ( !v16 )
    ExRaiseStatus(-1073741801);
  MmProbeAndLockPages(v16, a4, IoWriteAccess);
  BYTE8(v61) = 1;
  if ( (v17->MdlFlags & 5) != 0 )
    v19 = v17->MappedSystemVa;
  else
    v19 = MmMapLockedPagesSpecifyCache(v17, 0, MmCached, 0, 0, 0x40000010u);
  v52 = v19;
  *((_QWORD *)&v62 + 1) = v19;
  if ( !v19 )
    ExRaiseStatus(-1073741670);
  v54 = v69[6];
  v56 = v69[7];
  v55 = v69[7];
  v43 = 0;
  LOBYTE(v18) = v38;
  v20 = 0;
  v21 = AfdRioReferenceRegDomainByHandle(v69[6], v18, &v50);
  if ( v21 < 0 )
    goto LABEL_55;
  RioState = AfdRioAllocateRioState(v42, v7);
  v20 = RioState;
  if ( !RioState )
  {
    v21 = -1073741801;
LABEL_55:
    LODWORD(v32) = (_DWORD)v47;
    goto LABEL_56;
  }
  v23 = v50;
  *(_QWORD *)RioState = v50;
  *(_QWORD *)(RioState + 48) = v17;
  *(_DWORD *)(RioState + 64) = v42;
  v24 = v52;
  *(_QWORD *)(v20 + 56) = v52;
  v24[8] = 1;
  *(_WORD *)(v20 + 104) = 0;
  *(_QWORD *)(v20 + 120) = v12;
  *(_DWORD *)(v20 + 136) = v7;
  v25 = v51;
  *(_QWORD *)(v20 + 128) = v51;
  v25[8] = 0;
  *(_QWORD *)(v20 + 24) = v56;
  *(_BYTE *)(v20 + 152) = (v41 | *(_BYTE *)(v20 + 152) & 0xFE) ^ ((v41 | *(_BYTE *)(v20 + 152) & 0xFE) ^ (4 * v37)) & 4;
  *(_QWORD *)(v20 + 40) = AfdRioFindAndReferenceCq(v23);
  v26 = AfdRioFindAndReferenceCq(v50);
  *(_QWORD *)(v20 + 112) = v26;
  v27 = *(KSPIN_LOCK **)(v20 + 40);
  if ( !v27 || !v26 )
  {
    v21 = -1073741811;
    goto LABEL_55;
  }
  KeAcquireInStackQueuedSpinLock(v27, &LockHandle);
  v28 = *(_QWORD *)(v20 + 40);
  v29 = v42 - 1 + *(_DWORD *)(v28 + 32);
  if ( v29 < v42 - 1
    || v29 >= *(_DWORD *)(v28 + 28)
    || (*(_DWORD *)(v28 + 32) = v29,
        KeReleaseInStackQueuedSpinLock(&LockHandle),
        BYTE9(v61) = 1,
        KeAcquireInStackQueuedSpinLock(*(PKSPIN_LOCK *)(v20 + 112), &LockHandle),
        v30 = *(_QWORD *)(v20 + 112),
        v31 = v44 - 1 + *(_DWORD *)(v30 + 32),
        v31 < v44 - 1)
    || v31 >= *(_DWORD *)(v30 + 28) )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v21 = -1073741618;
    goto LABEL_55;
  }
  *(_DWORD *)(v30 + 32) = v31;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  BYTE9(v65) = 1;
  v32 = v47;
  KeAcquireInStackQueuedSpinLock(v47 + 7, &LockHandle);
  if ( (v47[1] & 0x800) != 0 || v47[10] )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v21 = -1073741436;
  }
  else
  {
    if ( *v57 == 0xAFD2 )
    {
      *(_BYTE *)(*(_QWORD *)(v20 + 128) + 8LL) = 1;
      *(_BYTE *)(v20 + 144) = 1;
    }
    _InterlockedOr(v36, 0);
    v32[10] = v20;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
LABEL_56:
  AFDETW_RIO_TRACE_RQ_CREATE(
    (_DWORD)v32,
    v20,
    v50,
    v42 - 1,
    v59,
    (char)v52,
    v49,
    v44 - 1,
    v58,
    (char)v51,
    v48,
    v46,
    v45,
    v21);
  if ( v21 < 0 )
  {
    if ( v20 )
    {
      *(_BYTE *)(v20 + 152) &= ~2u;
      if ( !BYTE9(v61) )
      {
        v34 = *(_QWORD *)(v20 + 40);
        if ( v34 )
        {
          AfdRioDereferenceCqInline(v34);
          *(_QWORD *)(v20 + 40) = 0;
        }
      }
      if ( !BYTE9(v65) )
      {
        v35 = *(_QWORD *)(v20 + 112);
        if ( v35 )
        {
          AfdRioDereferenceCqInline(v35);
          *(_QWORD *)(v20 + 112) = 0;
        }
      }
      AfdRioCleanupRioState((PVOID)v20);
    }
    else if ( v50 )
    {
      AfdDereferenceEndpoint(v50);
    }
    if ( v17 )
    {
      if ( BYTE8(v61) )
        MmUnlockPages(v17);
      IoFreeMdl(v17);
    }
    if ( v12 )
    {
      if ( BYTE8(v65) )
        MmUnlockPages(v12);
      IoFreeMdl(v12);
    }
    return (unsigned int)v21;
  }
  else
  {
    *(_BYTE *)(v20 + 152) |= 2u;
    return 0;
  }
}

```

## disassembly

```asm
0x14006b020  mov     r11, rsp
0x14006b023  push    rbx
0x14006b024  push    rsi
0x14006b025  push    rdi
0x14006b026  push    r12
0x14006b028  push    r13
0x14006b02a  push    r14
0x14006b02c  push    r15
0x14006b02e  sub     rsp, 1D0h
0x14006b035  mov     rax, cs:__security_cookie
0x14006b03c  xor     rax, rsp
0x14006b03f  mov     [rsp+208h+var_48], rax
0x14006b047  mov     r14b, r9b
0x14006b04a  mov     [rsp+208h+var_197], r9b
0x14006b04f  mov     esi, r8d
0x14006b052  mov     rbx, rdx
0x14006b055  mov     rax, rcx
0x14006b058  mov     [rsp+208h+var_118], rcx
0x14006b060  mov     [rsp+208h+var_90], rcx
0x14006b068  mov     [rsp+208h+var_170], rcx
0x14006b070  mov     [rsp+208h+var_190], r9b
0x14006b075  xorps   xmm0, xmm0
0x14006b078  xor     ecx, ecx
0x14006b07a  movups  [rsp+208h+var_100], xmm0
0x14006b082  movups  [rsp+208h+var_F0], xmm0
0x14006b08a  movups  [rsp+208h+var_E0], xmm0
0x14006b092  mov     [r11-0D0h], rcx
0x14006b099  xorps   xmm1, xmm1
0x14006b09c  movups  [rsp+208h+var_C8], xmm1
0x14006b0a4  movups  [rsp+208h+var_B8], xmm1
0x14006b0ac  movups  [rsp+208h+var_A8], xmm1
0x14006b0b4  mov     [r11-98h], rcx
0x14006b0bb  xor     edi, edi
0x14006b0bd  mov     [r11-160h], rdi
0x14006b0c4  mov     [r11-130h], rdi
0x14006b0cb  mov     [r11-128h], rdi
0x14006b0d2  mov     [rsp+208h+var_180], 0C0000100h
0x14006b0dd  movups  xmmword ptr [rsp+208h+LockHandle.LockQueue.Next], xmm0
0x14006b0e5  mov     [r11-138h], rcx
0x14006b0ec  mov     ecx, 0AFD1h
0x14006b0f1  cmp     [rax], cx
0x14006b0f4  setnz   [rsp+208h+var_188]
0x14006b0fc  xor     ecx, ecx; Irp
0x14006b0fe  call    cs:__imp_IoIs32bitProcess
0x14006b105  nop     dword ptr [rax+rax+00h]
0x14006b10a  mov     [rsp+208h+var_198], al
0x14006b10e  mov     [rsp+208h+var_196], al
0x14006b112  lea     r15d, [rdi+40h]
0x14006b116  cmp     esi, r15d
0x14006b119  jnb     short loc_14006B12C
0x14006b11b  mov     ecx, 0C000000Dh; Status
0x14006b120  call    cs:__imp_ExRaiseStatus
0x14006b12c  mov     r8, r15; Size
0x14006b12f  xor     edx, edx; Val
0x14006b131  lea     rcx, [rsp+208h+var_88]; void *
0x14006b139  call    memset
0x14006b13e  test    r14b, r14b
0x14006b141  jz      short loc_14006B16F
0x14006b143  test    bl, 3
0x14006b146  jz      short loc_14006B155
0x14006b148  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14006b14f  nop     dword ptr [rax+rax+00h]
0x14006b154  int     3; Trap to Debugger
0x14006b155  test    r14b, r14b
0x14006b158  jz      short loc_14006B16F
0x14006b15a  mov     r8, r15; Size
0x14006b15d  mov     rdx, rbx; Src
0x14006b160  lea     rcx, [rsp+208h+var_88]; void *
0x14006b168  call    RtlCopyFromUser
0x14006b16d  jmp     short loc_14006B182
0x14006b16f  mov     r8, r15; Size
0x14006b172  mov     rdx, rbx; Src
0x14006b175  lea     rcx, [rsp+208h+var_88]; void *
0x14006b17d  call    RtlCopyVolatileMemory
0x14006b182  mov     edx, [rsp+208h+var_64]
0x14006b189  mov     [rsp+208h+var_168], edx
0x14006b190  mov     [rsp+208h+var_98], edx
0x14006b197  mov     r12d, [rsp+208h+var_78]
0x14006b19f  mov     [rsp+208h+var_164], r12d
0x14006b1a7  mov     [rsp+208h+var_D0], r12d
0x14006b1af  mov     ebx, [rsp+208h+var_68]
0x14006b1b6  mov     [rsp+208h+var_17C], ebx
0x14006b1bd  mov     [rsp+208h+var_94], ebx
0x14006b1c4  mov     esi, [rsp+208h+var_7C]
0x14006b1cb  mov     [rsp+208h+var_184], esi
0x14006b1d2  mov     [rsp+208h+var_CC], esi
0x14006b1d9  test    esi, esi
0x14006b1db  jz      loc_14006B475
0x14006b1e1  test    ebx, ebx
0x14006b1e3  jz      loc_14006B475
0x14006b1e9  mov     r15d, 1
0x14006b1ef  cmp     esi, r15d
0x14006b1f2  jnz     short loc_14006B20A
0x14006b1f4  cmp     ebx, r15d
0x14006b1f7  jnz     short loc_14006B20A
0x14006b1f9  mov     ecx, 0C000000Dh; Status
0x14006b1fe  call    cs:__imp_ExRaiseStatus
0x14006b20a  mov     eax, 4924924h
0x14006b20f  cmp     esi, eax
0x14006b211  ja      loc_14006B464
0x14006b217  cmp     ebx, eax
0x14006b219  ja      loc_14006B464
0x14006b21f  mov     eax, [rsp+208h+var_80]
0x14006b226  mov     [rsp+208h+var_178], eax
0x14006b22d  mov     dword ptr [rsp+208h+var_C8], eax
0x14006b234  mov     r10, [rsp+208h+var_60]
0x14006b23c  mov     [rsp+208h+var_110], r10
0x14006b244  mov     qword ptr [rsp+208h+var_A8], r10
0x14006b24c  test    r10, r10
0x14006b24f  jz      loc_14006B453
0x14006b255  mov     ecx, ebx
0x14006b257  call    AfdRioCheckRqBufferSize
0x14006b25c  test    al, al
0x14006b25e  jz      loc_14006B453
0x14006b264  mov     [rsp+208h+Irp], rdi; Irp
0x14006b269  mov     r9b, r15b; ChargeQuota
0x14006b26c  xor     r8d, r8d; SecondaryBuffer
0x14006b26f  mov     rcx, r10; VirtualAddress
0x14006b272  call    cs:__imp_IoAllocateMdl
0x14006b279  nop     dword ptr [rax+rax+00h]
0x14006b27e  mov     r13, rax
0x14006b281  mov     qword ptr [rsp+208h+var_B8], rax
0x14006b289  test    rax, rax
0x14006b28c  jnz     short loc_14006B29F
0x14006b28e  mov     ecx, 0C0000017h; Status
0x14006b293  call    cs:__imp_ExRaiseStatus
0x14006b29f  mov     r8d, r15d; Operation
0x14006b2a2  mov     dl, r14b; AccessMode
0x14006b2a5  mov     rcx, r13; MemoryDescriptorList
0x14006b2a8  call    cs:__imp_MmProbeAndLockPages
0x14006b2af  nop     dword ptr [rax+rax+00h]
0x14006b2b4  mov     byte ptr [rsp+208h+var_B8+8], r15b
0x14006b2bc  test    byte ptr [r13+0Ah], 5
0x14006b2c1  jz      short loc_14006B2C9
0x14006b2c3  mov     rax, [r13+18h]
0x14006b2c7  jmp     short loc_14006B2EC
0x14006b2c9  mov     [rsp+208h+Priority], 40000010h; Priority
0x14006b2d1  mov     dword ptr [rsp+208h+Irp], edi; BugCheckOnFailure
0x14006b2d5  xor     r9d, r9d; RequestedAddress
0x14006b2d8  mov     r8d, r15d; CacheType
0x14006b2db  xor     edx, edx; AccessMode
0x14006b2dd  mov     rcx, r13; MemoryDescriptorList
0x14006b2e0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006b2e7  nop     dword ptr [rax+rax+00h]
0x14006b2ec  mov     [rsp+208h+var_158], rax
0x14006b2f4  mov     qword ptr [rsp+208h+var_A8+8], rax
0x14006b2fc  test    rax, rax
0x14006b2ff  jnz     short loc_14006B312
0x14006b301  mov     ecx, 0C000009Ah; Status
0x14006b306  call    cs:__imp_ExRaiseStatus
0x14006b312  mov     eax, [rsp+208h+var_84]
0x14006b319  mov     [rsp+208h+var_174], eax
0x14006b320  mov     dword ptr [rsp+208h+var_100], eax
0x14006b327  mov     r10, [rsp+208h+var_70]
0x14006b32f  mov     [rsp+208h+var_108], r10
0x14006b337  mov     qword ptr [rsp+208h+var_E0], r10
0x14006b33f  test    r10, r10
0x14006b342  jz      loc_14006B442
0x14006b348  mov     edx, r12d
0x14006b34b  mov     ecx, esi
0x14006b34d  call    AfdRioCheckRqBufferSize
0x14006b352  test    al, al
0x14006b354  jz      loc_14006B442
0x14006b35a  mov     [rsp+208h+Irp], rdi; Irp
0x14006b35f  mov     r9b, r15b; ChargeQuota
0x14006b362  xor     r8d, r8d; SecondaryBuffer
0x14006b365  mov     rcx, r10; VirtualAddress
0x14006b368  call    cs:__imp_IoAllocateMdl
0x14006b36f  nop     dword ptr [rax+rax+00h]
0x14006b374  mov     r12, rax
0x14006b377  mov     qword ptr [rsp+208h+var_F0], rax
0x14006b37f  test    rax, rax
0x14006b382  jnz     short loc_14006B395
0x14006b384  mov     ecx, 0C0000017h; Status
0x14006b389  call    cs:__imp_ExRaiseStatus
0x14006b395  mov     r8d, r15d; Operation
0x14006b398  mov     dl, r14b; AccessMode
0x14006b39b  mov     rcx, r12; MemoryDescriptorList
0x14006b39e  call    cs:__imp_MmProbeAndLockPages
0x14006b3a5  nop     dword ptr [rax+rax+00h]
0x14006b3aa  mov     byte ptr [rsp+208h+var_F0+8], r15b
0x14006b3b2  test    byte ptr [r12+0Ah], 5
0x14006b3b8  jz      short loc_14006B3C1
0x14006b3ba  mov     rax, [r12+18h]
0x14006b3bf  jmp     short loc_14006B3E4
0x14006b3c1  mov     [rsp+208h+Priority], 40000010h; Priority
0x14006b3c9  mov     dword ptr [rsp+208h+Irp], edi; BugCheckOnFailure
0x14006b3cd  xor     r9d, r9d; RequestedAddress
0x14006b3d0  mov     r8d, r15d; CacheType
0x14006b3d3  xor     edx, edx; AccessMode
0x14006b3d5  mov     rcx, r12; MemoryDescriptorList
0x14006b3d8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006b3df  nop     dword ptr [rax+rax+00h]
0x14006b3e4  mov     [rsp+208h+var_150], rax
0x14006b3ec  mov     qword ptr [rsp+208h+var_E0+8], rax
0x14006b3f4  test    rax, rax
0x14006b3f7  jnz     short loc_14006B40A
0x14006b3f9  mov     ecx, 0C000009Ah; Status
0x14006b3fe  call    cs:__imp_ExRaiseStatus
0x14006b40a  mov     rcx, [rsp+208h+var_58]
0x14006b412  mov     [rsp+208h+var_130], rcx
0x14006b41a  mov     rax, [rsp+208h+var_50]
0x14006b422  mov     [rsp+208h+var_120], rax
0x14006b42a  mov     [rsp+208h+var_128], rax
0x14006b432  mov     [rsp+208h+var_180], edi
0x14006b439  mov     dl, [rsp+208h+var_197]
0x14006b43d  jmp     loc_14006B565
0x14006b442  mov     ecx, 0C000000Dh; Status
0x14006b447  call    cs:__imp_ExRaiseStatus
0x14006b453  mov     ecx, 0C000000Dh; Status
0x14006b458  call    cs:__imp_ExRaiseStatus
0x14006b464  mov     ecx, 0C000000Dh; Status
0x14006b469  call    cs:__imp_ExRaiseStatus
0x14006b475  mov     ecx, 0C000000Dh; Status
0x14006b47a  call    cs:__imp_ExRaiseStatus
0x14006b487  xor     edi, edi
0x14006b489  lea     r15d, [rdi+1]
0x14006b48d  mov     eax, [rsp+208h+var_CC]
0x14006b494  mov     [rsp+208h+var_184], eax
0x14006b49b  mov     eax, [rsp+208h+var_D0]
0x14006b4a2  mov     [rsp+208h+var_164], eax
0x14006b4a9  mov     rax, qword ptr [rsp+208h+var_E0+8]
0x14006b4b1  mov     [rsp+208h+var_150], rax
0x14006b4b9  mov     rax, qword ptr [rsp+208h+var_E0]
0x14006b4c1  mov     [rsp+208h+var_108], rax
0x14006b4c9  mov     r12, qword ptr [rsp+208h+var_F0]
0x14006b4d1  mov     eax, dword ptr [rsp+208h+var_100]
0x14006b4d8  mov     [rsp+208h+var_174], eax
0x14006b4df  mov     ebx, [rsp+208h+var_94]
0x14006b4e6  mov     [rsp+208h+var_17C], ebx
0x14006b4ed  mov     eax, [rsp+208h+var_98]
0x14006b4f4  mov     [rsp+208h+var_168], eax
0x14006b4fb  mov     rax, qword ptr [rsp+208h+var_A8+8]
0x14006b503  mov     [rsp+208h+var_158], rax
0x14006b50b  mov     rax, qword ptr [rsp+208h+var_A8]
0x14006b513  mov     [rsp+208h+var_110], rax
0x14006b51b  mov     r13, qword ptr [rsp+208h+var_B8]
0x14006b523  mov     eax, dword ptr [rsp+208h+var_C8]
0x14006b52a  mov     [rsp+208h+var_178], eax
0x14006b531  mov     rcx, [rsp+208h+var_130]
0x14006b539  mov     rax, [rsp+208h+var_128]
0x14006b541  mov     [rsp+208h+var_120], rax
0x14006b549  mov     al, [rsp+208h+var_196]
0x14006b54d  mov     [rsp+208h+var_198], al
0x14006b551  mov     dl, [rsp+208h+var_190]
0x14006b555  mov     rax, [rsp+208h+var_90]
0x14006b55d  mov     [rsp+208h+var_118], rax
0x14006b565  mov     r14, rdi
0x14006b568  mov     esi, [rsp+208h+var_180]
0x14006b56f  test    esi, esi
0x14006b571  js      loc_14006B7C8
0x14006b577  lea     r8, [rsp+208h+var_160]
0x14006b57f  call    AfdRioReferenceRegDomainByHandle
0x14006b584  mov     esi, eax
0x14006b586  test    eax, eax
0x14006b588  js      loc_14006B7C8
0x14006b58e  mov     edx, ebx
0x14006b590  mov     ecx, [rsp+208h+var_184]
0x14006b597  call    AfdRioAllocateRioState
0x14006b59c  mov     r14, rax
0x14006b59f  test    rax, rax
0x14006b5a2  jnz     short loc_14006B5AE
0x14006b5a4  mov     esi, 0C0000017h
0x14006b5a9  jmp     loc_14006B7C8
0x14006b5ae  mov     rcx, [rsp+208h+var_160]
0x14006b5b6  mov     [rax], rcx
0x14006b5b9  mov     [rax+30h], r12
0x14006b5bd  mov     eax, [rsp+208h+var_184]
0x14006b5c4  mov     [r14+40h], eax
0x14006b5c8  mov     rax, [rsp+208h+var_150]
0x14006b5d0  mov     [r14+38h], rax
0x14006b5d4  mov     [rax+8], r15b
0x14006b5d8  mov     word ptr [r14+68h], 0
0x14006b5df  mov     [r14+78h], r13
0x14006b5e3  mov     [r14+88h], ebx
0x14006b5ea  mov     rax, [rsp+208h+var_158]
0x14006b5f2  mov     [r14+80h], rax
0x14006b5f9  mov     [rax+8], dil
0x14006b5fd  mov     rax, [rsp+208h+var_120]
0x14006b605  mov     [r14+18h], rax
0x14006b609  mov     al, [r14+98h]
0x14006b610  and     al, 0FEh
0x14006b612  or      al, [rsp+208h+var_188]
0x14006b619  mov     dl, [rsp+208h+var_198]
0x14006b61d  shl     dl, 2
0x14006b620  xor     dl, al
0x14006b622  and     dl, 4
0x14006b625  xor     dl, al
0x14006b627  mov     [r14+98h], dl
0x14006b62e  mov     edx, [rsp+208h+var_174]
0x14006b635  call    AfdRioFindAndReferenceCq
0x14006b63a  mov     [r14+28h], rax
0x14006b63e  mov     edx, [rsp+208h+var_178]
0x14006b645  mov     rcx, [rsp+208h+var_160]
0x14006b64d  call    AfdRioFindAndReferenceCq
0x14006b652  mov     [r14+70h], rax
0x14006b656  mov     rcx, [r14+28h]; SpinLock
0x14006b65a  test    rcx, rcx
0x14006b65d  jz      loc_14006B7C3
0x14006b663  test    rax, rax
  ... truncated ...
```
