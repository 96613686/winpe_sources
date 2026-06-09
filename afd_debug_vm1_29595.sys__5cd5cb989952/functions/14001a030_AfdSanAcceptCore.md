# AfdSanAcceptCore

- ea: `0x14001a030`
- end: `0x14001a706`
- name: `AfdSanAcceptCore`
- size: `1750`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140019810`
- `0x14003606c`
- `0x140036dcc`

## callees

- `0x14000f390`
- `0x1400137a0`
- `0x14001a030`
- `0x14001b0d0`
- `0x14001b800`
- `0x14002fd7c`
- `0x14003f7f8`
- `0x14005d760`
- `0x140072870`
- `0x140072880`
- `0x140092008`
- `0x14009220c`
- `0x140092254`
- `0x14009304c`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x14001a67c`
- `ntoskrnl!ObCloseHandle` at `0x14001a67c`
- `ntoskrnl!KeAttachProcess` at `0x14001a1af`
- `ntoskrnl!KeAttachProcess` at `0x14001a4ed`
- `ntoskrnl!KeAttachProcess` at `0x14001a666`
- `ntoskrnl!KeAttachProcess` at `0x14001a1af`
- `ntoskrnl!KeAttachProcess` at `0x14001a4ed`
- `ntoskrnl!KeAttachProcess` at `0x14001a666`
- `ntoskrnl!KeDetachProcess` at `0x14001a1fa`
- `ntoskrnl!KeDetachProcess` at `0x14001a61d`
- `ntoskrnl!KeDetachProcess` at `0x14001a688`
- `ntoskrnl!KeDetachProcess` at `0x14001a1fa`
- `ntoskrnl!KeDetachProcess` at `0x14001a61d`
- `ntoskrnl!KeDetachProcess` at `0x14001a688`
- `ntoskrnl!IoThreadToProcess` at `0x14001a16a`
- `ntoskrnl!IoThreadToProcess` at `0x14001a17c`
- `ntoskrnl!IoThreadToProcess` at `0x14001a198`
- `ntoskrnl!IoThreadToProcess` at `0x14001a16a`
- `ntoskrnl!IoThreadToProcess` at `0x14001a17c`
- `ntoskrnl!IoThreadToProcess` at `0x14001a198`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001a1ec`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001a1ec`
- `ntoskrnl!MmMapLockedPages` at `0x14001a352`
- `ntoskrnl!MmMapLockedPages` at `0x14001a392`
- `ntoskrnl!MmMapLockedPages` at `0x14001a3f4`
- `ntoskrnl!MmMapLockedPages` at `0x14001a45e`
- `ntoskrnl!MmMapLockedPages` at `0x14001a352`
- `ntoskrnl!MmMapLockedPages` at `0x14001a392`
- `ntoskrnl!MmMapLockedPages` at `0x14001a3f4`
- `ntoskrnl!MmMapLockedPages` at `0x14001a45e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001a6e4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001a6e4`
- `ntoskrnl!IofCompleteRequest` at `0x14001a12b`
- `ntoskrnl!IofCompleteRequest` at `0x14001a632`
- `ntoskrnl!IofCompleteRequest` at `0x14001a6a9`
- `ntoskrnl!IofCompleteRequest` at `0x14001a12b`
- `ntoskrnl!IofCompleteRequest` at `0x14001a632`
- `ntoskrnl!IofCompleteRequest` at `0x14001a6a9`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001a6d1`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001a6d1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001a4d9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001a652`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001a4d9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001a652`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001a245`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001a245`
- `ntoskrnl!IoFileObjectType` at `0x14001a1cd`
- `ntoskrnl!IoIs32bitProcess` at `0x14001a4fd`
- `ntoskrnl!IoIs32bitProcess` at `0x14001a4fd`

## pseudocode

```c
__int64 __fastcall AfdSanAcceptCore(__int64 a1, char *a2, __int64 a3, struct _KLOCK_QUEUE_HANDLE *a4)
{
  __int64 v8; // rbx
  __int64 v9; // r14
  struct _KTHREAD *v11; // rbx
  struct _KPROCESS *v12; // rdi
  struct _KPROCESS *v13; // r12
  NTSTATUS v14; // ebx
  __int64 v15; // rdi
  struct _KLOCK_QUEUE_HANDLE *v16; // rbx
  _DWORD *v17; // r13
  _QWORD *v18; // rdx
  unsigned int v19; // ebx
  int v20; // eax
  unsigned __int16 v21; // bx
  __int64 v22; // rcx
  char *v23; // rdx
  __int64 v24; // rcx
  char *v25; // r9
  __int64 v26; // rbx
  unsigned int v27; // eax
  __int64 v28; // rcx
  char *v29; // r9
  size_t v30; // r8
  unsigned __int16 v31; // r8
  unsigned __int16 *v32; // r9
  __int64 v33; // rcx
  char *v34; // rdx
  char *v35; // r15
  __int64 v36; // rdx
  unsigned __int64 v37; // rax
  unsigned __int16 v38; // dx
  unsigned __int16 v39; // di
  __int64 v40; // rbx
  BOOLEAN v41; // cl
  __int64 v42; // rax
  __int64 v43; // rdx
  char v44; // r8
  __int64 v45; // r9
  _DWORD *v46; // rdi
  int v47; // eax
  unsigned __int16 v48; // dx
  __int64 v49; // rbx
  __int64 v50; // [rsp+40h] [rbp-68h]
  __int64 v51; // [rsp+50h] [rbp-58h]
  unsigned __int16 *v52; // [rsp+50h] [rbp-58h]
  __int64 v53; // [rsp+B0h] [rbp+8h]
  unsigned int v54; // [rsp+B0h] [rbp+8h]
  char *Irql; // [rsp+B8h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+C0h] [rbp+18h] BYREF
  PKLOCK_QUEUE_HANDLE LockHandle; // [rsp+C8h] [rbp+20h]

  LockHandle = a4;
  Irql = a2;
  Handle = 0;
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 184) + 48LL) + 24LL);
  v53 = *((_QWORD *)a2 + 3);
  v9 = *(_QWORD *)(a3 + 40);
  *(_QWORD *)(a3 + 40) = 0;
  *(_DWORD *)(v8 + 72) &= ~0x80u;
  if ( (xmmword_1400875E0 & 0x20) != 0 )
    WPP_SF_qD(1029, 51, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v8, *(_DWORD *)(v8 + 72));
  if ( *(_QWORD *)(v8 + 96) == v8 + 96 )
    AfdNotifySockEventsChangedUnderLock(v8, 0, 128);
  else
    AfdIndicateEventSelectEvent(v8, 128, 0);
  *(_QWORD *)(a3 + 8) = 0;
  *(_DWORD *)(a3 + 4) &= ~0x20000000u;
  if ( !_InterlockedExchange64((volatile __int64 *)(v9 + 104), 0) )
  {
    AfdNotifySockIndicateEventsUnlock(v8, a4, 0);
    AfdSanReleaseConnection(v8, a3, 0);
    AfdDereferenceEndpoint(v8);
    *(_DWORD *)(v9 + 48) = -1073741536;
LABEL_8:
    *(_QWORD *)(v9 + 56) = 0;
    IofCompleteRequest((PIRP)v9, AfdPriorityBoost);
    return 3221225788LL;
  }
  AfdNotifySockIndicateEventsUnlock(v8, a4, 0);
  AfdSanReleaseConnection(v8, a3, 0);
  AfdDereferenceEndpoint(v8);
  v11 = *(struct _KTHREAD **)(a1 + 152);
  v12 = IoThreadToProcess(*(PETHREAD *)(v9 + 152));
  if ( IoThreadToProcess(v11) == v12 )
  {
    Handle = *(HANDLE *)(a1 + 144);
    v13 = 0;
  }
  else
  {
    v13 = IoThreadToProcess(*(PETHREAD *)(v9 + 152));
    KeAttachProcess(v13);
    v14 = ObOpenObjectByPointer(a2, 0x40u, 0, 0x2000000u, (POBJECT_TYPE)IoFileObjectType, 1, &Handle);
    KeDetachProcess();
    if ( v14 < 0 )
    {
      *(_DWORD *)(v9 + 48) = -1073741816;
      goto LABEL_8;
    }
  }
  v15 = v53;
  v16 = LockHandle;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v53 + 56), LockHandle);
  _InterlockedExchange64((volatile __int64 *)(a1 + 104), (__int64)&AfdSanCancelAccept);
  if ( (*(_DWORD *)(v53 + 8) & 0x800) != 0 || *(_BYTE *)(a1 + 68) )
  {
    *(_QWORD *)(a1 + 168) = 0;
    KeReleaseInStackQueuedSpinLock(v16);
    if ( v13 )
    {
      KeAttachProcess(v13);
      ObCloseHandle(Handle, 1);
      KeDetachProcess();
    }
    *(_DWORD *)(v9 + 48) = -1073741536;
    *(_QWORD *)(v9 + 56) = 0;
    IofCompleteRequest((PIRP)v9, AfdPriorityBoost);
    if ( !_InterlockedExchange64((volatile __int64 *)(a1 + 104), 0) )
    {
      LOBYTE(Irql) = 0;
      IoAcquireCancelSpinLock((PKIRQL)&Irql);
      IoReleaseCancelSpinLock((KIRQL)Irql);
    }
    return 3221225760LL;
  }
  else
  {
    *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
    v17 = *(_DWORD **)(a1 + 184);
    v54 = v17[2];
    v50 = *(_QWORD *)(v9 + 24);
    *(_QWORD *)(v15 + 360) = 0;
    AfdSanInitEndpoint(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 184) + 48LL) + 24LL), Irql, *(_QWORD *)(v50 + 8));
    if ( v13 )
      *(_BYTE *)(v15 + 160) = 1;
    v18 = *(_QWORD **)(v15 + 136);
    if ( *v18 != v15 + 128 )
      __fastfail(3u);
    *(_QWORD *)(a1 + 168) = v15 + 128;
    *(_QWORD *)(a1 + 176) = v18;
    *v18 = a1 + 168;
    *(_QWORD *)(v15 + 136) = a1 + 168;
    v19 = v17[4];
    if ( v19 >= 0xC )
    {
      v20 = *(unsigned __int16 *)(v50 + 20);
      if ( *(_BYTE *)(v15 + 188) )
      {
        if ( (unsigned __int64)v19 - 2 >= (unsigned __int16)(v20 + 2) )
          v21 = v20 + 2;
        else
          v21 = v19 - 2;
        v22 = *(_QWORD *)(a1 + 8);
        if ( (*(_BYTE *)(v22 + 10) & 5) != 0 )
          v23 = *(char **)(v22 + 24);
        else
          v23 = (char *)MmMapLockedPages((PMDL)v22, 0);
        v51 = (unsigned int)v17[2];
        Irql = &v23[v17[4] + v17[6]];
        v24 = *(_QWORD *)(a1 + 8);
        if ( (*(_BYTE *)(v24 + 10) & 5) != 0 )
          v25 = *(char **)(v24 + 24);
        else
          v25 = (char *)MmMapLockedPages((PMDL)v24, 0);
        RtlMoveVolatileMemory(&v25[v17[6] + v17[2]], (const void *)(v50 + 22), v21);
        *(_WORD *)&Irql[v51 - 2] = v21;
        v26 = v50;
      }
      else
      {
        v27 = v20 + 8;
        if ( v19 >= v27 )
          v19 = v27;
        v28 = *(_QWORD *)(a1 + 8);
        if ( (*(_BYTE *)(v28 + 10) & 5) != 0 )
          v29 = *(char **)(v28 + 24);
        else
          v29 = (char *)MmMapLockedPages((PMDL)v28, 0);
        v30 = v19;
        v26 = v50;
        RtlMoveVolatileMemory(&v29[v17[6] + v17[2]], (const void *)(v50 + 16), v30);
      }
      if ( v17[6] >= 6u )
      {
        v31 = *((_WORD *)v17 + 12);
        LOWORD(Irql) = v31;
        v32 = (unsigned __int16 *)(v26 + *(unsigned __int16 *)(v26 + 20) + 24LL);
        v52 = v32;
        v33 = *(_QWORD *)(a1 + 8);
        if ( (*(_BYTE *)(v33 + 10) & 5) != 0 )
        {
          v34 = *(char **)(v33 + 24);
        }
        else
        {
          v34 = (char *)MmMapLockedPages((PMDL)v33, 0);
          v32 = v52;
          v31 = (unsigned __int16)Irql;
        }
        v35 = &v34[v17[2]];
        v36 = *v32;
        if ( *(_BYTE *)(v15 + 188) )
        {
          v37 = v36 + 2;
          v38 = v36 + 2;
          if ( v37 >= (unsigned __int64)v31 - 2 )
            v38 = v31 - 2;
          v39 = v38;
          v40 = (unsigned int)v17[6];
          RtlMoveVolatileMemory(v35, v32 + 1, v38);
          *(_WORD *)&v35[v40 - 2] = v39;
        }
        else
        {
          *(_DWORD *)v35 = 0;
          *((_DWORD *)v35 + 1) = 1;
          v47 = v36 + 4;
          v48 = v36 + 4;
          if ( v47 >= v31 - 8 )
            v48 = v31 - 8;
          RtlMoveVolatileMemory(v35 + 8, v32, v48);
        }
      }
    }
    KeReleaseInStackQueuedSpinLock(LockHandle);
    if ( v13 )
      KeAttachProcess(v13);
    v41 = IoIs32bitProcess((PIRP)v9);
    v42 = *(_QWORD *)(v9 + 8);
    v43 = *(_QWORD *)(v42 + 32);
    v44 = *(_BYTE *)(v9 + 64);
    v45 = *(unsigned int *)(v42 + 44);
    if ( v41 )
    {
      v46 = (_DWORD *)(v43 + v45);
      if ( v44 )
        RtlCopyToUser(v46, (void *)(int)Handle, 4u);
      else
        RtlCopyVolatileMemory(v46, (const void *)(int)Handle, 4u);
      if ( *(_BYTE *)(v9 + 64) )
        RtlWriteULongToUser(v46 + 1, v54);
      else
        v46[1] = v54;
      *(_QWORD *)(v9 + 56) = 8;
    }
    else
    {
      v49 = v43 + v45;
      if ( v44 )
        RtlWriteULong64ToUser(v49, Handle);
      else
        *(_QWORD *)v49 = Handle;
      if ( *(_BYTE *)(v9 + 64) )
        RtlWriteULongToUser(v49 + 8, v54);
      else
        *(_DWORD *)(v49 + 8) = v54;
      *(_QWORD *)(v9 + 56) = 16;
    }
    *(_DWORD *)(v9 + 48) = v13 != 0 ? 0x105 : 0;
    if ( v13 )
      KeDetachProcess();
    IofCompleteRequest((PIRP)v9, AfdPriorityBoost);
    return 259;
  }
}

```

## disassembly

```asm
0x14001a030  mov     rax, rsp
0x14001a033  mov     [rax+20h], r9
0x14001a037  mov     [rax+10h], rdx
0x14001a03b  push    rbx
0x14001a03c  push    rsi
0x14001a03d  push    rdi
0x14001a03e  push    r12
0x14001a040  push    r13
0x14001a042  push    r14
0x14001a044  push    r15
0x14001a046  sub     rsp, 70h
0x14001a04a  mov     r12, r9
0x14001a04d  mov     rdi, r8
0x14001a050  mov     r13, rdx
0x14001a053  mov     r15, rcx
0x14001a056  xor     esi, esi
0x14001a058  mov     [rax+18h], rsi
0x14001a05c  mov     rax, [rcx+0B8h]
0x14001a063  mov     r10, [rax+30h]
0x14001a067  mov     rbx, [r10+18h]
0x14001a06b  mov     rax, [rdx+18h]
0x14001a06f  mov     [rsp+0A8h+arg_0], rax
0x14001a077  mov     r14, [r8+28h]
0x14001a07b  mov     [rsp+0A8h+var_48], r14
0x14001a080  mov     [r8+28h], rsi
0x14001a084  mov     eax, [rbx+48h]
0x14001a087  btr     eax, 7
0x14001a08b  mov     [rbx+48h], eax
0x14001a08e  test    byte ptr cs:xmmword_1400875E0, 20h
0x14001a095  jz      short loc_14001A0B5
0x14001a097  lea     edx, [rsi+33h]
0x14001a09a  mov     ecx, 405h
0x14001a09f  mov     eax, [rbx+48h]
0x14001a0a2  mov     dword ptr [rsp+0A8h+ObjectType], eax
0x14001a0a6  mov     r9, rbx
0x14001a0a9  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14001a0b0  call    WPP_SF_qD
0x14001a0b5  lea     rax, [rbx+60h]
0x14001a0b9  mov     rcx, rbx
0x14001a0bc  cmp     [rax], rax
0x14001a0bf  jz      short loc_14001A0D0
0x14001a0c1  xor     r8d, r8d
0x14001a0c4  mov     edx, 80h
0x14001a0c9  call    AfdIndicateEventSelectEvent
0x14001a0ce  jmp     short loc_14001A0DD
0x14001a0d0  xor     edx, edx
0x14001a0d2  mov     r8d, 80h
0x14001a0d8  call    AfdNotifySockEventsChangedUnderLock
0x14001a0dd  mov     [rdi+8], rsi
0x14001a0e1  btr     dword ptr [rdi+4], 1Dh
0x14001a0e6  mov     rax, rsi
0x14001a0e9  xchg    rax, [r14+68h]
0x14001a0ed  xor     r8d, r8d
0x14001a0f0  mov     rdx, r12
0x14001a0f3  mov     rcx, rbx
0x14001a0f6  test    rax, rax
0x14001a0f9  jnz     short loc_14001A141
0x14001a0fb  call    AfdNotifySockIndicateEventsUnlock
0x14001a100  xor     r8d, r8d
0x14001a103  mov     rdx, rdi
0x14001a106  mov     rcx, rbx
0x14001a109  call    AfdSanReleaseConnection
0x14001a10e  mov     rcx, rbx
0x14001a111  call    AfdDereferenceEndpoint
0x14001a116  mov     dword ptr [r14+30h], 0C0000120h
0x14001a11e  mov     [r14+38h], rsi
0x14001a122  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14001a128  mov     rcx, r14; Irp
0x14001a12b  call    cs:__imp_IofCompleteRequest
0x14001a132  nop     dword ptr [rax+rax+00h]
0x14001a137  mov     eax, 0C000013Ch
0x14001a13c  jmp     loc_14001A6F5
0x14001a141  call    AfdNotifySockIndicateEventsUnlock
0x14001a146  xor     r8d, r8d
0x14001a149  mov     rdx, rdi
0x14001a14c  mov     rcx, rbx
0x14001a14f  call    AfdSanReleaseConnection
0x14001a154  mov     rcx, rbx
0x14001a157  call    AfdDereferenceEndpoint
0x14001a15c  mov     rcx, [r14+98h]; Thread
0x14001a163  mov     rbx, [r15+98h]
0x14001a16a  call    cs:__imp_IoThreadToProcess
0x14001a171  nop     dword ptr [rax+rax+00h]
0x14001a176  mov     rdi, rax
0x14001a179  mov     rcx, rbx; Thread
0x14001a17c  call    cs:__imp_IoThreadToProcess
0x14001a183  nop     dword ptr [rax+rax+00h]
0x14001a188  cmp     rax, rdi
0x14001a18b  jz      loc_14001A217
0x14001a191  mov     rcx, [r14+98h]; Thread
0x14001a198  call    cs:__imp_IoThreadToProcess
0x14001a19f  nop     dword ptr [rax+rax+00h]
0x14001a1a4  mov     r12, rax
0x14001a1a7  mov     [rsp+0A8h+var_60], rax
0x14001a1ac  mov     rcx, rax; Process
0x14001a1af  call    cs:__imp_KeAttachProcess
0x14001a1b6  nop     dword ptr [rax+rax+00h]
0x14001a1bb  lea     rax, [rsp+0A8h+arg_10]
0x14001a1c3  mov     [rsp+0A8h+Handle], rax; Handle
0x14001a1c8  mov     [rsp+0A8h+AccessMode], 1; AccessMode
0x14001a1cd  mov     rax, cs:__imp_IoFileObjectType
0x14001a1d4  mov     rcx, [rax]
0x14001a1d7  mov     [rsp+0A8h+ObjectType], rcx; ObjectType
0x14001a1dc  mov     r9d, 2000000h; DesiredAccess
0x14001a1e2  xor     r8d, r8d; PassedAccessState
0x14001a1e5  lea     edx, [r8+40h]; HandleAttributes
0x14001a1e9  mov     rcx, r13; Object
0x14001a1ec  call    cs:__imp_ObOpenObjectByPointer
0x14001a1f3  nop     dword ptr [rax+rax+00h]
0x14001a1f8  mov     ebx, eax
0x14001a1fa  call    cs:__imp_KeDetachProcess
0x14001a201  nop     dword ptr [rax+rax+00h]
0x14001a206  test    ebx, ebx
0x14001a208  jns     short loc_14001A22E
0x14001a20a  mov     dword ptr [r14+30h], 0C0000008h
0x14001a212  jmp     loc_14001A11E
0x14001a217  mov     rax, [r15+90h]
0x14001a21e  mov     [rsp+0A8h+arg_10], rax
0x14001a226  mov     r12, rsi
0x14001a229  mov     [rsp+0A8h+var_60], rsi
0x14001a22e  mov     rdi, [rsp+0A8h+arg_0]
0x14001a236  lea     rcx, [rdi+38h]; SpinLock
0x14001a23a  mov     rbx, [rsp+0A8h+LockHandle]
0x14001a242  mov     rdx, rbx; LockHandle
0x14001a245  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001a24c  nop     dword ptr [rax+rax+00h]
0x14001a251  lea     rax, AfdSanCancelAccept
0x14001a258  xchg    rax, [r15+68h]
0x14001a25c  test    dword ptr [rdi+8], 800h
0x14001a263  jnz     loc_14001A648
0x14001a269  cmp     [r15+44h], sil
0x14001a26d  jnz     loc_14001A648
0x14001a273  mov     rax, [r15+0B8h]
0x14001a27a  or      byte ptr [rax+3], 1
0x14001a27e  mov     r13, [r15+0B8h]
0x14001a285  mov     eax, [r13+8]
0x14001a289  mov     dword ptr [rsp+0A8h+arg_0], eax
0x14001a290  mov     rdx, [r14+18h]
0x14001a294  mov     [rsp+0A8h+var_68], rdx
0x14001a299  mov     [rdi+168h], rsi
0x14001a2a0  mov     rax, [r14+0B8h]
0x14001a2a7  mov     rcx, [rax+30h]
0x14001a2ab  mov     r8, [rdx+8]
0x14001a2af  mov     rdx, [rsp+0A8h+Irql]
0x14001a2b7  mov     rcx, [rcx+18h]
0x14001a2bb  call    AfdSanInitEndpoint
0x14001a2c0  test    r12, r12
0x14001a2c3  jz      short loc_14001A2CC
0x14001a2c5  mov     byte ptr [rdi+0A0h], 1
0x14001a2cc  lea     rcx, [rdi+80h]
0x14001a2d3  mov     rdx, [rcx+8]
0x14001a2d7  cmp     [rdx], rcx
0x14001a2da  jz      short loc_14001A2E3
0x14001a2dc  mov     ecx, 3
0x14001a2e1  int     29h; Win8: RtlFailFast(ecx)
0x14001a2e3  mov     [rsp+0A8h+var_50], r14
0x14001a2e8  lea     rax, [r15+0A8h]
0x14001a2ef  mov     [rax], rcx
0x14001a2f2  mov     [rax+8], rdx
0x14001a2f6  mov     [rdx], rax
0x14001a2f9  mov     [rcx+8], rax
0x14001a2fd  mov     ebx, [r13+10h]
0x14001a301  cmp     ebx, 0Ch
0x14001a304  jb      loc_14001A4CC
0x14001a30a  mov     rax, [rsp+0A8h+var_68]
0x14001a30f  movzx   eax, word ptr [rax+14h]
0x14001a313  cmp     [rdi+0BCh], sil
0x14001a31a  jz      loc_14001A3DA
0x14001a320  mov     r8d, 2
0x14001a326  add     ax, r8w
0x14001a32a  movzx   edx, ax
0x14001a32d  mov     ecx, ebx
0x14001a32f  sub     rcx, r8
0x14001a332  cmp     rcx, rdx
0x14001a335  jnb     short loc_14001A33D
0x14001a337  sub     bx, r8w
0x14001a33b  jmp     short loc_14001A340
0x14001a33d  movzx   ebx, dx
0x14001a340  mov     rcx, [r15+8]; MemoryDescriptorList
0x14001a344  test    byte ptr [rcx+0Ah], 5
0x14001a348  jz      short loc_14001A350
0x14001a34a  mov     rdx, [rcx+18h]
0x14001a34e  jmp     short loc_14001A361
0x14001a350  xor     edx, edx; AccessMode
0x14001a352  call    cs:__imp_MmMapLockedPages
0x14001a359  nop     dword ptr [rax+rax+00h]
0x14001a35e  mov     rdx, rax
0x14001a361  mov     eax, [r13+18h]
0x14001a365  mov     ecx, [r13+10h]
0x14001a369  add     rcx, rdx
0x14001a36c  mov     edx, [r13+8]
0x14001a370  mov     [rsp+0A8h+var_58], rdx
0x14001a375  add     rcx, rax
0x14001a378  mov     [rsp+0A8h+Irql], rcx
0x14001a380  mov     rcx, [r15+8]; MemoryDescriptorList
0x14001a384  test    byte ptr [rcx+0Ah], 5
0x14001a388  jz      short loc_14001A390
0x14001a38a  mov     r9, [rcx+18h]
0x14001a38e  jmp     short loc_14001A3A1
0x14001a390  xor     edx, edx; AccessMode
0x14001a392  call    cs:__imp_MmMapLockedPages
0x14001a399  nop     dword ptr [rax+rax+00h]
0x14001a39e  mov     r9, rax
0x14001a3a1  movzx   r8d, bx; Size
0x14001a3a5  mov     rdx, [rsp+0A8h+var_68]
0x14001a3aa  add     rdx, 16h; Src
0x14001a3ae  mov     eax, [r13+18h]
0x14001a3b2  mov     ecx, [r13+8]
0x14001a3b6  add     rax, r9
0x14001a3b9  add     rcx, rax; void *
0x14001a3bc  call    RtlMoveVolatileMemory
0x14001a3c1  mov     rax, [rsp+0A8h+Irql]
0x14001a3c9  mov     rcx, [rsp+0A8h+var_58]
0x14001a3ce  mov     [rcx+rax-2], bx
0x14001a3d3  mov     rbx, [rsp+0A8h+var_68]
0x14001a3d8  jmp     short loc_14001A422
0x14001a3da  add     eax, 8
0x14001a3dd  cmp     ebx, eax
0x14001a3df  cmovnb  ebx, eax
0x14001a3e2  mov     rcx, [r15+8]; MemoryDescriptorList
0x14001a3e6  test    byte ptr [rcx+0Ah], 5
0x14001a3ea  jz      short loc_14001A3F2
0x14001a3ec  mov     r9, [rcx+18h]
0x14001a3f0  jmp     short loc_14001A403
0x14001a3f2  xor     edx, edx; AccessMode
0x14001a3f4  call    cs:__imp_MmMapLockedPages
0x14001a3fb  nop     dword ptr [rax+rax+00h]
0x14001a400  mov     r9, rax
0x14001a403  mov     r8d, ebx; Size
0x14001a406  mov     rbx, [rsp+0A8h+var_68]
0x14001a40b  lea     rdx, [rbx+10h]; Src
0x14001a40f  mov     eax, [r13+18h]
0x14001a413  mov     ecx, [r13+8]
0x14001a417  add     rax, r9
0x14001a41a  add     rcx, rax; void *
0x14001a41d  call    RtlMoveVolatileMemory
0x14001a422  cmp     dword ptr [r13+18h], 6
0x14001a427  jb      loc_14001A4CC
0x14001a42d  movzx   r8d, word ptr [r13+18h]
0x14001a432  mov     word ptr [rsp+0A8h+Irql], r8w
0x14001a43b  movzx   r9d, word ptr [rbx+14h]
0x14001a440  add     r9, 18h
0x14001a444  add     r9, rbx
0x14001a447  mov     [rsp+0A8h+var_58], r9
0x14001a44c  mov     rcx, [r15+8]; MemoryDescriptorList
0x14001a450  test    byte ptr [rcx+0Ah], 5
0x14001a454  jz      short loc_14001A45C
0x14001a456  mov     rdx, [rcx+18h]
0x14001a45a  jmp     short loc_14001A47B
0x14001a45c  xor     edx, edx; AccessMode
0x14001a45e  call    cs:__imp_MmMapLockedPages
0x14001a465  nop     dword ptr [rax+rax+00h]
0x14001a46a  mov     rdx, rax
0x14001a46d  mov     r9, [rsp+0A8h+var_58]
0x14001a472  movzx   r8d, word ptr [rsp+0A8h+Irql]
0x14001a47b  mov     r15d, [r13+8]
0x14001a47f  add     r15, rdx
0x14001a482  movzx   edx, word ptr [r9]
0x14001a486  cmp     [rdi+0BCh], sil
0x14001a48d  jz      loc_14001A541
0x14001a493  movzx   ecx, r8w
0x14001a497  add     rcx, 0FFFFFFFFFFFFFFFEh
0x14001a49b  mov     r8d, 2
0x14001a4a1  lea     rax, [r8+rdx]
0x14001a4a5  add     dx, r8w
0x14001a4a9  cmp     rax, rcx
0x14001a4ac  cmovnb  dx, cx
0x14001a4b0  movzx   edi, dx
0x14001a4b3  mov     ebx, [r13+18h]
0x14001a4b7  mov     r8d, edi; Size
0x14001a4ba  lea     rdx, [r9+2]; Src
0x14001a4be  mov     rcx, r15; void *
0x14001a4c1  call    RtlMoveVolatileMemory
0x14001a4c6  mov     [rbx+r15-2], di
0x14001a4cc  mov     ebx, 4
0x14001a4d1  mov     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14001a4d9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001a4e0  nop     dword ptr [rax+rax+00h]
0x14001a4e5  test    r12, r12
0x14001a4e8  jz      short loc_14001A4FA
0x14001a4ea  mov     rcx, r12; Process
0x14001a4ed  call    cs:__imp_KeAttachProcess
0x14001a4f4  nop     dword ptr [rax+rax+00h]
0x14001a4f9  nop
0x14001a4fa  mov     rcx, r14; Irp
0x14001a4fd  call    cs:__imp_IoIs32bitProcess
0x14001a504  nop     dword ptr [rax+rax+00h]
0x14001a509  mov     cl, al
0x14001a50b  mov     rax, [r14+8]
0x14001a50f  mov     rdx, [rax+20h]
0x14001a513  mov     r8b, [r14+40h]
0x14001a517  mov     r9d, [rax+2Ch]
0x14001a51b  test    cl, cl
0x14001a51d  jz      loc_14001A5AA
0x14001a523  lea     rdi, [rdx+r9]
0x14001a527  movsxd  rdx, dword ptr [rsp+0A8h+arg_10]; Src
0x14001a52f  mov     rcx, rdi; void *
0x14001a532  test    r8b, r8b
0x14001a535  mov     r8, rbx; Size
0x14001a538  jz      short loc_14001A579
  ... truncated ...
```
