# AfdRioCreateRqPair

- ea: `0x14006b1c0`
- end: `0x14006baf6`
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
- `0x14002fd7c`
- `0x1400329e4`
- `0x140033700`
- `0x14004033c`
- `0x1400445d8`
- `0x14006a134`
- `0x14006b1c0`
- `0x14006c4a0`
- `0x140072840`
- `0x140072870`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14006b2c0`
- `ntoskrnl!ExRaiseStatus` at `0x14006b39e`
- `ntoskrnl!ExRaiseStatus` at `0x14006b433`
- `ntoskrnl!ExRaiseStatus` at `0x14006b4a6`
- `ntoskrnl!ExRaiseStatus` at `0x14006b529`
- `ntoskrnl!ExRaiseStatus` at `0x14006b59e`
- `ntoskrnl!ExRaiseStatus` at `0x14006b5e7`
- `ntoskrnl!ExRaiseStatus` at `0x14006b5f8`
- `ntoskrnl!ExRaiseStatus` at `0x14006b609`
- `ntoskrnl!ExRaiseStatus` at `0x14006b61a`
- `ntoskrnl!ExRaiseStatus` at `0x14006b2c0`
- `ntoskrnl!ExRaiseStatus` at `0x14006b39e`
- `ntoskrnl!ExRaiseStatus` at `0x14006b433`
- `ntoskrnl!ExRaiseStatus` at `0x14006b4a6`
- `ntoskrnl!ExRaiseStatus` at `0x14006b529`
- `ntoskrnl!ExRaiseStatus` at `0x14006b59e`
- `ntoskrnl!ExRaiseStatus` at `0x14006b5e7`
- `ntoskrnl!ExRaiseStatus` at `0x14006b5f8`
- `ntoskrnl!ExRaiseStatus` at `0x14006b609`
- `ntoskrnl!ExRaiseStatus` at `0x14006b61a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006b480`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006b578`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006b480`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006b578`
- `ntoskrnl!IoFreeMdl` at `0x14006ba97`
- `ntoskrnl!IoFreeMdl` at `0x14006bac4`
- `ntoskrnl!IoFreeMdl` at `0x14006ba97`
- `ntoskrnl!IoFreeMdl` at `0x14006bac4`
- `ntoskrnl!MmUnlockPages` at `0x14006ba88`
- `ntoskrnl!MmUnlockPages` at `0x14006bab5`
- `ntoskrnl!MmUnlockPages` at `0x14006ba88`
- `ntoskrnl!MmUnlockPages` at `0x14006bab5`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006b448`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006b53e`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006b448`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006b53e`
- `ntoskrnl!IoAllocateMdl` at `0x14006b412`
- `ntoskrnl!IoAllocateMdl` at `0x14006b508`
- `ntoskrnl!IoAllocateMdl` at `0x14006b412`
- `ntoskrnl!IoAllocateMdl` at `0x14006b508`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006b2e8`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006b2e8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b84e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b8a8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b91f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b935`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b950`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b84e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b8a8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b91f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b935`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b950`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b81d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b877`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b8d0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b81d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b877`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006b8d0`
- `ntoskrnl!IoIs32bitProcess` at `0x14006b29e`
- `ntoskrnl!IoIs32bitProcess` at `0x14006b29e`

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
0x14006b1c0  mov     r11, rsp
0x14006b1c3  push    rbx
0x14006b1c4  push    rsi
0x14006b1c5  push    rdi
0x14006b1c6  push    r12
0x14006b1c8  push    r13
0x14006b1ca  push    r14
0x14006b1cc  push    r15
0x14006b1ce  sub     rsp, 1D0h
0x14006b1d5  mov     rax, cs:__security_cookie
0x14006b1dc  xor     rax, rsp
0x14006b1df  mov     [rsp+208h+var_48], rax
0x14006b1e7  mov     r14b, r9b
0x14006b1ea  mov     [rsp+208h+var_197], r9b
0x14006b1ef  mov     esi, r8d
0x14006b1f2  mov     rbx, rdx
0x14006b1f5  mov     rax, rcx
0x14006b1f8  mov     [rsp+208h+var_118], rcx
0x14006b200  mov     [rsp+208h+var_90], rcx
0x14006b208  mov     [rsp+208h+var_170], rcx
0x14006b210  mov     [rsp+208h+var_190], r9b
0x14006b215  xorps   xmm0, xmm0
0x14006b218  xor     ecx, ecx
0x14006b21a  movups  [rsp+208h+var_100], xmm0
0x14006b222  movups  [rsp+208h+var_F0], xmm0
0x14006b22a  movups  [rsp+208h+var_E0], xmm0
0x14006b232  mov     [r11-0D0h], rcx
0x14006b239  xorps   xmm1, xmm1
0x14006b23c  movups  [rsp+208h+var_C8], xmm1
0x14006b244  movups  [rsp+208h+var_B8], xmm1
0x14006b24c  movups  [rsp+208h+var_A8], xmm1
0x14006b254  mov     [r11-98h], rcx
0x14006b25b  xor     edi, edi
0x14006b25d  mov     [r11-160h], rdi
0x14006b264  mov     [r11-130h], rdi
0x14006b26b  mov     [r11-128h], rdi
0x14006b272  mov     [rsp+208h+var_180], 0C0000100h
0x14006b27d  movups  xmmword ptr [rsp+208h+LockHandle.LockQueue.Next], xmm0
0x14006b285  mov     [r11-138h], rcx
0x14006b28c  mov     ecx, 0AFD1h
0x14006b291  cmp     [rax], cx
0x14006b294  setnz   [rsp+208h+var_188]
0x14006b29c  xor     ecx, ecx; Irp
0x14006b29e  call    cs:__imp_IoIs32bitProcess
0x14006b2a5  nop     dword ptr [rax+rax+00h]
0x14006b2aa  mov     [rsp+208h+var_198], al
0x14006b2ae  mov     [rsp+208h+var_196], al
0x14006b2b2  lea     r15d, [rdi+40h]
0x14006b2b6  cmp     esi, r15d
0x14006b2b9  jnb     short loc_14006B2CC
0x14006b2bb  mov     ecx, 0C000000Dh; Status
0x14006b2c0  call    cs:__imp_ExRaiseStatus
0x14006b2cc  mov     r8, r15; Size
0x14006b2cf  xor     edx, edx; Val
0x14006b2d1  lea     rcx, [rsp+208h+var_88]; void *
0x14006b2d9  call    memset
0x14006b2de  test    r14b, r14b
0x14006b2e1  jz      short loc_14006B30F
0x14006b2e3  test    bl, 3
0x14006b2e6  jz      short loc_14006B2F5
0x14006b2e8  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14006b2ef  nop     dword ptr [rax+rax+00h]
0x14006b2f4  int     3; Trap to Debugger
0x14006b2f5  test    r14b, r14b
0x14006b2f8  jz      short loc_14006B30F
0x14006b2fa  mov     r8, r15; Size
0x14006b2fd  mov     rdx, rbx; Src
0x14006b300  lea     rcx, [rsp+208h+var_88]; void *
0x14006b308  call    RtlCopyFromUser
0x14006b30d  jmp     short loc_14006B322
0x14006b30f  mov     r8, r15; Size
0x14006b312  mov     rdx, rbx; Src
0x14006b315  lea     rcx, [rsp+208h+var_88]; void *
0x14006b31d  call    RtlCopyVolatileMemory
0x14006b322  mov     edx, [rsp+208h+var_64]
0x14006b329  mov     [rsp+208h+var_168], edx
0x14006b330  mov     [rsp+208h+var_98], edx
0x14006b337  mov     r12d, [rsp+208h+var_78]
0x14006b33f  mov     [rsp+208h+var_164], r12d
0x14006b347  mov     [rsp+208h+var_D0], r12d
0x14006b34f  mov     ebx, [rsp+208h+var_68]
0x14006b356  mov     [rsp+208h+var_17C], ebx
0x14006b35d  mov     [rsp+208h+var_94], ebx
0x14006b364  mov     esi, [rsp+208h+var_7C]
0x14006b36b  mov     [rsp+208h+var_184], esi
0x14006b372  mov     [rsp+208h+var_CC], esi
0x14006b379  test    esi, esi
0x14006b37b  jz      loc_14006B615
0x14006b381  test    ebx, ebx
0x14006b383  jz      loc_14006B615
0x14006b389  mov     r15d, 1
0x14006b38f  cmp     esi, r15d
0x14006b392  jnz     short loc_14006B3AA
0x14006b394  cmp     ebx, r15d
0x14006b397  jnz     short loc_14006B3AA
0x14006b399  mov     ecx, 0C000000Dh; Status
0x14006b39e  call    cs:__imp_ExRaiseStatus
0x14006b3aa  mov     eax, 4924924h
0x14006b3af  cmp     esi, eax
0x14006b3b1  ja      loc_14006B604
0x14006b3b7  cmp     ebx, eax
0x14006b3b9  ja      loc_14006B604
0x14006b3bf  mov     eax, [rsp+208h+var_80]
0x14006b3c6  mov     [rsp+208h+var_178], eax
0x14006b3cd  mov     dword ptr [rsp+208h+var_C8], eax
0x14006b3d4  mov     r10, [rsp+208h+var_60]
0x14006b3dc  mov     [rsp+208h+var_110], r10
0x14006b3e4  mov     qword ptr [rsp+208h+var_A8], r10
0x14006b3ec  test    r10, r10
0x14006b3ef  jz      loc_14006B5F3
0x14006b3f5  mov     ecx, ebx
0x14006b3f7  call    AfdRioCheckRqBufferSize
0x14006b3fc  test    al, al
0x14006b3fe  jz      loc_14006B5F3
0x14006b404  mov     [rsp+208h+Irp], rdi; Irp
0x14006b409  mov     r9b, r15b; ChargeQuota
0x14006b40c  xor     r8d, r8d; SecondaryBuffer
0x14006b40f  mov     rcx, r10; VirtualAddress
0x14006b412  call    cs:__imp_IoAllocateMdl
0x14006b419  nop     dword ptr [rax+rax+00h]
0x14006b41e  mov     r13, rax
0x14006b421  mov     qword ptr [rsp+208h+var_B8], rax
0x14006b429  test    rax, rax
0x14006b42c  jnz     short loc_14006B43F
0x14006b42e  mov     ecx, 0C0000017h; Status
0x14006b433  call    cs:__imp_ExRaiseStatus
0x14006b43f  mov     r8d, r15d; Operation
0x14006b442  mov     dl, r14b; AccessMode
0x14006b445  mov     rcx, r13; MemoryDescriptorList
0x14006b448  call    cs:__imp_MmProbeAndLockPages
0x14006b44f  nop     dword ptr [rax+rax+00h]
0x14006b454  mov     byte ptr [rsp+208h+var_B8+8], r15b
0x14006b45c  test    byte ptr [r13+0Ah], 5
0x14006b461  jz      short loc_14006B469
0x14006b463  mov     rax, [r13+18h]
0x14006b467  jmp     short loc_14006B48C
0x14006b469  mov     [rsp+208h+Priority], 40000010h; Priority
0x14006b471  mov     dword ptr [rsp+208h+Irp], edi; BugCheckOnFailure
0x14006b475  xor     r9d, r9d; RequestedAddress
0x14006b478  mov     r8d, r15d; CacheType
0x14006b47b  xor     edx, edx; AccessMode
0x14006b47d  mov     rcx, r13; MemoryDescriptorList
0x14006b480  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006b487  nop     dword ptr [rax+rax+00h]
0x14006b48c  mov     [rsp+208h+var_158], rax
0x14006b494  mov     qword ptr [rsp+208h+var_A8+8], rax
0x14006b49c  test    rax, rax
0x14006b49f  jnz     short loc_14006B4B2
0x14006b4a1  mov     ecx, 0C000009Ah; Status
0x14006b4a6  call    cs:__imp_ExRaiseStatus
0x14006b4b2  mov     eax, [rsp+208h+var_84]
0x14006b4b9  mov     [rsp+208h+var_174], eax
0x14006b4c0  mov     dword ptr [rsp+208h+var_100], eax
0x14006b4c7  mov     r10, [rsp+208h+var_70]
0x14006b4cf  mov     [rsp+208h+var_108], r10
0x14006b4d7  mov     qword ptr [rsp+208h+var_E0], r10
0x14006b4df  test    r10, r10
0x14006b4e2  jz      loc_14006B5E2
0x14006b4e8  mov     edx, r12d
0x14006b4eb  mov     ecx, esi
0x14006b4ed  call    AfdRioCheckRqBufferSize
0x14006b4f2  test    al, al
0x14006b4f4  jz      loc_14006B5E2
0x14006b4fa  mov     [rsp+208h+Irp], rdi; Irp
0x14006b4ff  mov     r9b, r15b; ChargeQuota
0x14006b502  xor     r8d, r8d; SecondaryBuffer
0x14006b505  mov     rcx, r10; VirtualAddress
0x14006b508  call    cs:__imp_IoAllocateMdl
0x14006b50f  nop     dword ptr [rax+rax+00h]
0x14006b514  mov     r12, rax
0x14006b517  mov     qword ptr [rsp+208h+var_F0], rax
0x14006b51f  test    rax, rax
0x14006b522  jnz     short loc_14006B535
0x14006b524  mov     ecx, 0C0000017h; Status
0x14006b529  call    cs:__imp_ExRaiseStatus
0x14006b535  mov     r8d, r15d; Operation
0x14006b538  mov     dl, r14b; AccessMode
0x14006b53b  mov     rcx, r12; MemoryDescriptorList
0x14006b53e  call    cs:__imp_MmProbeAndLockPages
0x14006b545  nop     dword ptr [rax+rax+00h]
0x14006b54a  mov     byte ptr [rsp+208h+var_F0+8], r15b
0x14006b552  test    byte ptr [r12+0Ah], 5
0x14006b558  jz      short loc_14006B561
0x14006b55a  mov     rax, [r12+18h]
0x14006b55f  jmp     short loc_14006B584
0x14006b561  mov     [rsp+208h+Priority], 40000010h; Priority
0x14006b569  mov     dword ptr [rsp+208h+Irp], edi; BugCheckOnFailure
0x14006b56d  xor     r9d, r9d; RequestedAddress
0x14006b570  mov     r8d, r15d; CacheType
0x14006b573  xor     edx, edx; AccessMode
0x14006b575  mov     rcx, r12; MemoryDescriptorList
0x14006b578  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006b57f  nop     dword ptr [rax+rax+00h]
0x14006b584  mov     [rsp+208h+var_150], rax
0x14006b58c  mov     qword ptr [rsp+208h+var_E0+8], rax
0x14006b594  test    rax, rax
0x14006b597  jnz     short loc_14006B5AA
0x14006b599  mov     ecx, 0C000009Ah; Status
0x14006b59e  call    cs:__imp_ExRaiseStatus
0x14006b5aa  mov     rcx, [rsp+208h+var_58]
0x14006b5b2  mov     [rsp+208h+var_130], rcx
0x14006b5ba  mov     rax, [rsp+208h+var_50]
0x14006b5c2  mov     [rsp+208h+var_120], rax
0x14006b5ca  mov     [rsp+208h+var_128], rax
0x14006b5d2  mov     [rsp+208h+var_180], edi
0x14006b5d9  mov     dl, [rsp+208h+var_197]
0x14006b5dd  jmp     loc_14006B705
0x14006b5e2  mov     ecx, 0C000000Dh; Status
0x14006b5e7  call    cs:__imp_ExRaiseStatus
0x14006b5f3  mov     ecx, 0C000000Dh; Status
0x14006b5f8  call    cs:__imp_ExRaiseStatus
0x14006b604  mov     ecx, 0C000000Dh; Status
0x14006b609  call    cs:__imp_ExRaiseStatus
0x14006b615  mov     ecx, 0C000000Dh; Status
0x14006b61a  call    cs:__imp_ExRaiseStatus
0x14006b627  xor     edi, edi
0x14006b629  lea     r15d, [rdi+1]
0x14006b62d  mov     eax, [rsp+208h+var_CC]
0x14006b634  mov     [rsp+208h+var_184], eax
0x14006b63b  mov     eax, [rsp+208h+var_D0]
0x14006b642  mov     [rsp+208h+var_164], eax
0x14006b649  mov     rax, qword ptr [rsp+208h+var_E0+8]
0x14006b651  mov     [rsp+208h+var_150], rax
0x14006b659  mov     rax, qword ptr [rsp+208h+var_E0]
0x14006b661  mov     [rsp+208h+var_108], rax
0x14006b669  mov     r12, qword ptr [rsp+208h+var_F0]
0x14006b671  mov     eax, dword ptr [rsp+208h+var_100]
0x14006b678  mov     [rsp+208h+var_174], eax
0x14006b67f  mov     ebx, [rsp+208h+var_94]
0x14006b686  mov     [rsp+208h+var_17C], ebx
0x14006b68d  mov     eax, [rsp+208h+var_98]
0x14006b694  mov     [rsp+208h+var_168], eax
0x14006b69b  mov     rax, qword ptr [rsp+208h+var_A8+8]
0x14006b6a3  mov     [rsp+208h+var_158], rax
0x14006b6ab  mov     rax, qword ptr [rsp+208h+var_A8]
0x14006b6b3  mov     [rsp+208h+var_110], rax
0x14006b6bb  mov     r13, qword ptr [rsp+208h+var_B8]
0x14006b6c3  mov     eax, dword ptr [rsp+208h+var_C8]
0x14006b6ca  mov     [rsp+208h+var_178], eax
0x14006b6d1  mov     rcx, [rsp+208h+var_130]
0x14006b6d9  mov     rax, [rsp+208h+var_128]
0x14006b6e1  mov     [rsp+208h+var_120], rax
0x14006b6e9  mov     al, [rsp+208h+var_196]
0x14006b6ed  mov     [rsp+208h+var_198], al
0x14006b6f1  mov     dl, [rsp+208h+var_190]
0x14006b6f5  mov     rax, [rsp+208h+var_90]
0x14006b6fd  mov     [rsp+208h+var_118], rax
0x14006b705  mov     r14, rdi
0x14006b708  mov     esi, [rsp+208h+var_180]
0x14006b70f  test    esi, esi
0x14006b711  js      loc_14006B968
0x14006b717  lea     r8, [rsp+208h+var_160]
0x14006b71f  call    AfdRioReferenceRegDomainByHandle
0x14006b724  mov     esi, eax
0x14006b726  test    eax, eax
0x14006b728  js      loc_14006B968
0x14006b72e  mov     edx, ebx
0x14006b730  mov     ecx, [rsp+208h+var_184]
0x14006b737  call    AfdRioAllocateRioState
0x14006b73c  mov     r14, rax
0x14006b73f  test    rax, rax
0x14006b742  jnz     short loc_14006B74E
0x14006b744  mov     esi, 0C0000017h
0x14006b749  jmp     loc_14006B968
0x14006b74e  mov     rcx, [rsp+208h+var_160]
0x14006b756  mov     [rax], rcx
0x14006b759  mov     [rax+30h], r12
0x14006b75d  mov     eax, [rsp+208h+var_184]
0x14006b764  mov     [r14+40h], eax
0x14006b768  mov     rax, [rsp+208h+var_150]
0x14006b770  mov     [r14+38h], rax
0x14006b774  mov     [rax+8], r15b
0x14006b778  mov     word ptr [r14+68h], 0
0x14006b77f  mov     [r14+78h], r13
0x14006b783  mov     [r14+88h], ebx
0x14006b78a  mov     rax, [rsp+208h+var_158]
0x14006b792  mov     [r14+80h], rax
0x14006b799  mov     [rax+8], dil
0x14006b79d  mov     rax, [rsp+208h+var_120]
0x14006b7a5  mov     [r14+18h], rax
0x14006b7a9  mov     al, [r14+98h]
0x14006b7b0  and     al, 0FEh
0x14006b7b2  or      al, [rsp+208h+var_188]
0x14006b7b9  mov     dl, [rsp+208h+var_198]
0x14006b7bd  shl     dl, 2
0x14006b7c0  xor     dl, al
0x14006b7c2  and     dl, 4
0x14006b7c5  xor     dl, al
0x14006b7c7  mov     [r14+98h], dl
0x14006b7ce  mov     edx, [rsp+208h+var_174]
0x14006b7d5  call    AfdRioFindAndReferenceCq
0x14006b7da  mov     [r14+28h], rax
0x14006b7de  mov     edx, [rsp+208h+var_178]
0x14006b7e5  mov     rcx, [rsp+208h+var_160]
0x14006b7ed  call    AfdRioFindAndReferenceCq
0x14006b7f2  mov     [r14+70h], rax
0x14006b7f6  mov     rcx, [r14+28h]; SpinLock
0x14006b7fa  test    rcx, rcx
0x14006b7fd  jz      loc_14006B963
0x14006b803  test    rax, rax
  ... truncated ...
```
