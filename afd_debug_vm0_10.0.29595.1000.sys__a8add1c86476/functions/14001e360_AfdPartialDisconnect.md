# AfdPartialDisconnect

- ea: `0x14001e360`
- end: `0x14001e7cb`
- name: `AfdPartialDisconnect`
- size: `1131`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000fcd0`
- `0x140013030`
- `0x14001c708`
- `0x14001ceb0`
- `0x14001db90`
- `0x14001e360`
- `0x14001e7e0`
- `0x14001e86c`
- `0x14002fd7c`
- `0x14003338c`
- `0x1400445d8`
- `0x140072840`
- `0x140072870`
- `0x140072c80`
- `0x140093008`
- `0x1400930cc`
- `0x14009352c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140077121`
- `ntoskrnl!KeInitializeEvent` at `0x14007729c`
- `ntoskrnl!KeInitializeEvent` at `0x140077121`
- `ntoskrnl!KeInitializeEvent` at `0x14007729c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140077224`
- `ntoskrnl!KeWaitForSingleObject` at `0x140077224`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140077184`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140077184`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14001e45b`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14001e481`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14001e45b`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14001e481`
- `ntoskrnl!IofCallDriver` at `0x1400771f8`
- `ntoskrnl!IofCallDriver` at `0x1400771f8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001e5af`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001e647`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140076fb4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14007707d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140077274`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400772c5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001e5af`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001e647`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140076fb4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14007707d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140077274`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400772c5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001e542`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001e6d1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007725c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400772ad`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001e542`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001e6d1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007725c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400772ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077068`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077068`
- `ntoskrnl!IoIs32bitProcess` at `0x14001e3d5`
- `ntoskrnl!IoIs32bitProcess` at `0x14001e3d5`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007700e`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007700e`
- `NDIS!NdisReleaseRWLock` at `0x14007703b`
- `NDIS!NdisReleaseRWLock` at `0x14007703b`

## pseudocode

```c
__int64 __fastcall AfdPartialDisconnect(
        __int64 a1,
        __int64 a2,
        char a3,
        void *a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8)
{
  unsigned int v10; // r13d
  __int64 v11; // rdi
  __int64 ConnectionReferenceFromEndpoint; // rbx
  int v13; // eax
  BOOL v14; // ecx
  char v15; // r15
  int v16; // eax
  int v17; // edi
  signed __int64 v18; // rax
  bool v19; // cc
  signed __int64 v20; // rax
  char v22; // al
  void *v23; // r14
  unsigned int v24; // ebx
  struct _FILE_OBJECT *v25; // r14
  struct _DEVICE_OBJECT *v26; // rbx
  __int64 v27; // rax
  PIRP v28; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v30; // rdx
  NTSTATUS v31; // eax
  KSPIN_LOCK *v32; // rcx
  int v33; // eax
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp-E8h] BYREF
  int v35; // [rsp+54h] [rbp-E4h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+58h] [rbp-E0h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp-C8h] BYREF
  _DWORD v38[20]; // [rsp+90h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+E0h] [rbp-58h] BYREF
  ULONG_PTR Information; // [rsp+E8h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  LODWORD(Information) = 0;
  v39 = 0;
  *a8 = 0;
  v10 = 0;
  v35 = 0;
  v11 = *(_QWORD *)(a1 + 24);
  if ( a5 < 0x10 )
    return 3221225485LL;
  if ( IoIs32bitProcess(0) )
  {
    LODWORD(IoStatusBlock.Information) = 0;
    IoStatusBlock.Pointer = 0;
    if ( a3 && ((unsigned __int8)a4 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    if ( a3 )
      RtlCopyFromUser(&IoStatusBlock, a4, 0x10u);
    else
      RtlCopyVolatileMemory(&IoStatusBlock, a4, 0x10u);
    LODWORD(v39) = IoStatusBlock.Status;
    Information = IoStatusBlock.Information;
  }
  else
  {
    if ( a3 && ((unsigned __int8)a4 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    if ( a3 )
      RtlCopyFromUser(&v39, a4, 0x10u);
    else
      RtlCopyVolatileMemory(&v39, a4, 0x10u);
  }
  if ( (xmmword_1400875E0 & 0x80u) != 0LL )
    WPP_SF_qdd(1031, 10, WPP_56506c8bf8c7385db6ea71daa1f57f8f_Traceguids, v11, v39, HIWORD(*(_DWORD *)(v11 + 8)) & 0xF);
  if ( *(_WORD *)v11 != 0xAFD1 )
  {
    if ( (*(_WORD *)v11 & 0xAFD2) == 0xAFD2
      && (*(_DWORD *)(v11 + 8) & 1) == 0
      && (*(_BYTE *)(v11 + 6) & 1) == 0
      && *(_BYTE *)(v11 + 2) == 4 )
    {
      ConnectionReferenceFromEndpoint = AfdGetConnectionReferenceFromEndpoint(v11);
      if ( ConnectionReferenceFromEndpoint )
      {
        if ( (v39 & 4) != 0 )
        {
          if ( (xmmword_1400875E0 & 0x80u) != 0LL )
            WPP_SF_q(1031, 11, WPP_56506c8bf8c7385db6ea71daa1f57f8f_Traceguids, v11);
          AFDETW_TRACEABORT(2, 8003, v11, 2);
          v33 = AfdBeginAbort(ConnectionReferenceFromEndpoint);
          v17 = 0;
          if ( v33 != 259 )
            v17 = v33;
          goto LABEL_45;
        }
        if ( (v39 & 2) == 0 || (*(_DWORD *)(v11 + 8) & 0x20000) != 0 )
        {
LABEL_42:
          if ( (v39 & 1) != 0 && (*(_DWORD *)(v11 + 8) & 0x10000) == 0 )
          {
            v17 = AfdBeginDisconnect(v11, &Information);
            if ( v17 < 0 )
              goto LABEL_45;
          }
          goto LABEL_50;
        }
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v11 + 56), &LockHandle);
        if ( (*(_DWORD *)(ConnectionReferenceFromEndpoint + 4) & 1) != 0 )
        {
          if ( *(_QWORD *)(ConnectionReferenceFromEndpoint + 56) <= *(_QWORD *)(ConnectionReferenceFromEndpoint + 64)
                                                                  + *(_QWORD *)(ConnectionReferenceFromEndpoint + 72)
            && !*(_BYTE *)(ConnectionReferenceFromEndpoint + 105) )
          {
LABEL_32:
            if ( (*(_DWORD *)(ConnectionReferenceFromEndpoint + 4) & 1) != 0 )
            {
              v14 = *(_QWORD *)(ConnectionReferenceFromEndpoint + 80) > *(_QWORD *)(ConnectionReferenceFromEndpoint + 88)
                                                                      + *(_QWORD *)(ConnectionReferenceFromEndpoint + 96);
            }
            else
            {
              if ( *(_WORD *)(ConnectionReferenceFromEndpoint + 98) )
                goto LABEL_47;
              v14 = 0;
            }
            if ( !v14 )
            {
              v15 = 0;
              if ( (xmmword_1400875E0 & 0x80u) != 0LL )
                WPP_SF_q(1031, 13, WPP_56506c8bf8c7385db6ea71daa1f57f8f_Traceguids, v11);
              v16 = *(_DWORD *)(v11 + 8);
              if ( (v16 & 0x20000) == 0 )
              {
                *(_DWORD *)(v11 + 8) = v16 | 0x20000;
                v15 = 1;
              }
              KeReleaseInStackQueuedSpinLock(&LockHandle);
              if ( v15 )
                AfdDisconnectReceive(ConnectionReferenceFromEndpoint);
              goto LABEL_42;
            }
LABEL_47:
            if ( (xmmword_1400875E0 & 0x80u) != 0LL )
              WPP_SF_qq(1031, 12, WPP_56506c8bf8c7385db6ea71daa1f57f8f_Traceguids, v11, ConnectionReferenceFromEndpoint);
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            AFDETW_TRACEABORT(2, 8004, v11, 3);
            AfdBeginAbort(ConnectionReferenceFromEndpoint);
LABEL_50:
            v17 = 0;
LABEL_45:
            v18 = _InterlockedExchangeAdd64(
                    (volatile signed __int64 *)(ConnectionReferenceFromEndpoint + 48),
                    0xFFFFFFFFFFFFFFFFuLL);
            v19 = v18 <= 1;
            v20 = v18 - 1;
            if ( v19 )
            {
              if ( v20 )
                __fastfail(0xEu);
              AfdCloseConnection(ConnectionReferenceFromEndpoint);
            }
            return (unsigned int)v17;
          }
          v13 = 1;
        }
        else
        {
          if ( *(_WORD *)(ConnectionReferenceFromEndpoint + 96) )
            goto LABEL_47;
          v13 = 0;
        }
        if ( v13 )
          goto LABEL_47;
        goto LABEL_32;
      }
    }
    return 3221225485LL;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v11 + 56), &LockHandle);
  v22 = v39;
  if ( (v39 & 4) != 0 )
  {
    *(_DWORD *)(v11 + 8) |= 0x70000u;
    v22 = v39;
  }
  if ( (v22 & 2) != 0 )
  {
    *(_DWORD *)(v11 + 8) |= 0x20000u;
    v22 = v39;
  }
  if ( (v22 & 1) != 0 )
    *(_DWORD *)(v11 + 8) |= 0x10000u;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 368), 3, 0) )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    return 3221225485LL;
  }
  if ( (v39 & 8) != 0 && *(_BYTE *)(v11 + 2) == 4 )
  {
    v23 = *(void **)(v11 + 184);
    if ( v23 )
    {
      *(_WORD *)&LockState.OldIrql = 0;
      LockState.Flags = 0;
      v24 = *(_DWORD *)(v11 + 176);
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v11 + 168), &LockState, 1u);
      *(_QWORD *)(v11 + 184) = 0;
      *(_DWORD *)(v11 + 176) = 0;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v11 + 168), &LockState);
      if ( v24 > (unsigned int)AfdStandardAddressLength )
        ExFreePoolWithTag(v23, 0x52646641u);
      else
        PplFreeToLookasideList((__int64)PplAddressPool, v23);
    }
    *(_BYTE *)(v11 + 2) = 3;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( (*(_DWORD *)(v11 + 8) & 0x100) != 0 )
    {
      memset(v38, 0, sizeof(v38));
      v38[5] = 65533;
      v38[6] = 28;
      v10 = AfdTLIoControl(*(_QWORD *)(*(_QWORD *)(v11 + 24) + 8LL), *(_QWORD *)(v11 + 16), v38, v11);
    }
    else if ( (*(_DWORD *)(v11 + 16) & 0x8000) != 0 )
    {
      memset(&Event, 0, sizeof(Event));
      IoStatusBlock = 0;
      v25 = *(struct _FILE_OBJECT **)(v11 + 24);
      v26 = *(struct _DEVICE_OBJECT **)(v11 + 40);
      KeInitializeEvent(&Event, SynchronizationEvent, 0);
      if ( (*(_DWORD *)(v11 + 8) & 0x400000) != 0 && (*(_DWORD *)(v11 + 192) & 0x20) != 0 )
      {
        v27 = *(_QWORD *)(v11 + 280);
        v26 = *(struct _DEVICE_OBJECT **)(v27 + 16);
        v25 = *(struct _FILE_OBJECT **)(v27 + 8);
      }
      while ( 1 )
      {
        v28 = IoBuildDeviceIoControlRequest(3u, v26, 0, 0, 0, 0, 1u, &Event, &IoStatusBlock);
        if ( !v28 )
          break;
        CurrentStackLocation = v28->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].CompletionRoutine = 0;
        CurrentStackLocation[-1].Context = 0;
        CurrentStackLocation[-1].Control = 0;
        v30 = v28->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&v30[-1].MajorFunction = 1551;
        v30[-1].DeviceObject = v26;
        v30[-1].FileObject = v25;
        v30[-1].Parameters.WMI.ProviderId = (-(__int64)((v39 & 4) != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 4;
        v30[-1].Parameters.QueryDirectory.FileName = 0;
        v30[-1].Parameters.Read.ByteOffset.QuadPart = 0;
        v30[-1].Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)&Information;
        v31 = IofCallDriver(v26, v28);
        v10 = v31;
        if ( v31 == 259 )
        {
          v31 = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          v10 = v31;
        }
        if ( (*(_DWORD *)(v11 + 8) & 0x400000) == 0 || v31 < 0 )
          goto LABEL_91;
        v32 = (KSPIN_LOCK *)(v11 + 56);
        if ( (*(_DWORD *)(v11 + 192) & 0x20) == 0 )
        {
          KeAcquireInStackQueuedSpinLock(v32, &LockHandle);
          *(_DWORD *)(v11 + 192) &= ~0x40u;
          goto LABEL_90;
        }
        KeAcquireInStackQueuedSpinLock(v32, &LockHandle);
        *(_DWORD *)(v11 + 192) &= ~0x20u;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( (*(_DWORD *)(v11 + 192) & 0x40) == 0 )
          goto LABEL_91;
        v25 = *(struct _FILE_OBJECT **)(v11 + 24);
        v26 = *(struct _DEVICE_OBJECT **)(v11 + 40);
        KeInitializeEvent(&Event, SynchronizationEvent, 0);
      }
      v10 = -1073741670;
    }
  }
  else
  {
LABEL_90:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
LABEL_91:
  _InterlockedExchange((volatile __int32 *)(v11 + 368), 0);
  return v10;
}

```

## disassembly

```asm
0x14001e360  mov     r11, rsp
0x14001e363  mov     [r11+10h], rbx
0x14001e367  mov     [r11+18h], rsi
0x14001e36b  push    rdi
0x14001e36c  push    r12
0x14001e36e  push    r13
0x14001e370  push    r14
0x14001e372  push    r15
0x14001e374  sub     rsp, 110h
0x14001e37b  mov     rax, cs:__security_cookie
0x14001e382  xor     rax, rsp
0x14001e385  mov     [rsp+138h+var_38], rax
0x14001e38d  mov     rbx, r9
0x14001e390  mov     sil, r8b
0x14001e393  mov     rax, [rsp+138h+arg_38]
0x14001e39b  xorps   xmm0, xmm0
0x14001e39e  xor     edx, edx
0x14001e3a0  movups  xmmword ptr [rsp+138h+LockHandle.LockQueue.Next], xmm0
0x14001e3a5  mov     qword ptr [rsp+138h+LockHandle.OldIrql], rdx
0x14001e3aa  mov     [r11-54h], rdx
0x14001e3ae  mov     [r11-58h], rdx
0x14001e3b2  mov     [rax], rdx
0x14001e3b5  xor     r13d, r13d
0x14001e3b8  mov     [rsp+138h+var_E4], r13d
0x14001e3bd  mov     rdi, [rcx+18h]
0x14001e3c1  lea     r14d, [rdx+10h]
0x14001e3c5  cmp     [rsp+138h+arg_20], r14d
0x14001e3cd  jb      loc_14001E675
0x14001e3d3  xor     ecx, ecx; Irp
0x14001e3d5  call    cs:__imp_IoIs32bitProcess
0x14001e3dc  nop     dword ptr [rax+rax+00h]
0x14001e3e1  lea     r15d, [r13+3]
0x14001e3e5  test    al, al
0x14001e3e7  jnz     short loc_14001E468
0x14001e3e9  test    sil, sil
0x14001e3ec  jnz     short loc_14001E456
0x14001e3ee  mov     r8, r14; Size
0x14001e3f1  mov     rdx, rbx; Src
0x14001e3f4  lea     rcx, [rsp+138h+var_58]; void *
0x14001e3fc  test    sil, sil
0x14001e3ff  jz      short loc_14001E40B
0x14001e401  call    RtlCopyFromUser
0x14001e406  jmp     loc_14001E48E
0x14001e40b  call    RtlCopyVolatileMemory
0x14001e410  jmp     short loc_14001E48E
0x14001e412  test    r15b, bl
0x14001e415  jnz     short loc_14001E481
0x14001e417  mov     r8, r14; Size
0x14001e41a  mov     rdx, rbx; Src
0x14001e41d  lea     rcx, [rsp+138h+var_48]; void *
0x14001e425  test    sil, sil
0x14001e428  jz      short loc_14001E44F
0x14001e42a  call    RtlCopyFromUser
0x14001e42f  mov     eax, dword ptr [rsp+138h+var_48]
0x14001e436  mov     dword ptr [rsp+138h+var_58], eax
0x14001e43d  mov     rax, [rsp+138h+var_48.Information]
0x14001e445  mov     [rsp+138h+var_50], rax
0x14001e44d  jmp     short loc_14001E48E
0x14001e44f  call    RtlCopyVolatileMemory
0x14001e454  jmp     short loc_14001E42F
0x14001e456  test    r15b, bl
0x14001e459  jz      short loc_14001E3EE
0x14001e45b  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14001e462  nop     dword ptr [rax+rax+00h]
0x14001e467  int     3; Trap to Debugger
0x14001e468  xor     eax, eax
0x14001e46a  mov     qword ptr [rsp+138h+var_48+4], rax
0x14001e472  mov     qword ptr [rsp+138h+var_48], rax
0x14001e47a  test    sil, sil
0x14001e47d  jz      short loc_14001E417
0x14001e47f  jmp     short loc_14001E412
0x14001e481  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14001e488  nop     dword ptr [rax+rax+00h]
0x14001e48d  int     3; Trap to Debugger
0x14001e48e  jmp     short loc_14001E499
0x14001e490  mov     eax, [rsp+138h+var_E4]
0x14001e494  jmp     loc_14001E606
0x14001e499  mov     al, byte ptr cs:xmmword_1400875E0
0x14001e49f  mov     r12d, 407h
0x14001e4a5  test    al, al
0x14001e4a7  js      loc_14001E691
0x14001e4ad  movzx   eax, word ptr [rdi]
0x14001e4b0  mov     ecx, 0AFD1h
0x14001e4b5  cmp     ax, cx
0x14001e4b8  jz      loc_14001E6C5
0x14001e4be  mov     ecx, 0AFD2h
0x14001e4c3  and     ax, cx
0x14001e4c6  cmp     ax, cx
0x14001e4c9  jnz     loc_14001E675
0x14001e4cf  mov     eax, [rdi+8]
0x14001e4d2  mov     esi, 1
0x14001e4d7  test    sil, al
0x14001e4da  jnz     loc_14001E675
0x14001e4e0  test    [rdi+6], sil
0x14001e4e4  jnz     loc_14001E675
0x14001e4ea  cmp     byte ptr [rdi+2], 4
0x14001e4ee  jnz     loc_14001E675
0x14001e4f4  mov     rcx, rdi
0x14001e4f7  call    AfdGetConnectionReferenceFromEndpoint
0x14001e4fc  mov     rbx, rax
0x14001e4ff  xor     r13d, r13d
0x14001e502  test    rax, rax
0x14001e505  jz      loc_14001E675
0x14001e50b  test    byte ptr [rsp+138h+var_58], 4
0x14001e513  jnz     loc_14001E703
0x14001e519  test    byte ptr [rsp+138h+var_58], 2
0x14001e521  jz      loc_14001E5C4
0x14001e527  mov     eax, [rdi+8]
0x14001e52a  mov     r14d, 20000h
0x14001e530  test    r14d, eax
0x14001e533  jnz     loc_14001E5C4
0x14001e539  lea     rcx, [rdi+38h]; SpinLock
0x14001e53d  lea     rdx, [rsp+138h+LockHandle]; LockHandle
0x14001e542  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001e549  nop     dword ptr [rax+rax+00h]
0x14001e54e  mov     ecx, [rbx+4]
0x14001e551  and     ecx, esi
0x14001e553  jnz     loc_14001E72E
0x14001e559  cmp     [rbx+60h], r13w
0x14001e55e  jnz     loc_14001E634
0x14001e564  mov     eax, r13d
0x14001e567  test    eax, eax
0x14001e569  jnz     loc_14001E634
0x14001e56f  test    ecx, ecx
0x14001e571  jnz     loc_14001E74F
0x14001e577  cmp     [rbx+62h], r13w
0x14001e57c  jnz     loc_14001E634
0x14001e582  mov     ecx, r13d
0x14001e585  test    ecx, ecx
0x14001e587  jnz     loc_14001E634
0x14001e58d  mov     r15b, r13b
0x14001e590  mov     al, byte ptr cs:xmmword_1400875E0
0x14001e596  test    al, al
0x14001e598  js      loc_14001E766
0x14001e59e  mov     eax, [rdi+8]
0x14001e5a1  test    r14d, eax
0x14001e5a4  jz      loc_14001E782
0x14001e5aa  lea     rcx, [rsp+138h+LockHandle]; LockHandle
0x14001e5af  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001e5b6  nop     dword ptr [rax+rax+00h]
0x14001e5bb  test    r15b, r15b
0x14001e5be  jnz     loc_14001E790
0x14001e5c4  test    byte ptr [rsp+138h+var_58], sil
0x14001e5cc  jz      loc_14001E670
0x14001e5d2  mov     eax, [rdi+8]
0x14001e5d5  bt      eax, 10h
0x14001e5d9  jb      loc_14001E670
0x14001e5df  lea     rdx, [rsp+138h+var_50]
0x14001e5e7  mov     rcx, rdi
0x14001e5ea  call    AfdBeginDisconnect
0x14001e5ef  mov     edi, eax
0x14001e5f1  test    eax, eax
0x14001e5f3  jns     short loc_14001E670
0x14001e5f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001e5f9  lock xadd [rbx+30h], rax
0x14001e5ff  sub     rax, rsi
0x14001e602  jle     short loc_14001E67C
0x14001e604  mov     eax, edi
0x14001e606  mov     rcx, [rsp+138h+var_38]
0x14001e60e  xor     rcx, rsp; StackCookie
0x14001e611  call    __security_check_cookie
0x14001e616  lea     r11, [rsp+138h+var_28]
0x14001e61e  mov     rbx, [r11+38h]
0x14001e622  mov     rsi, [r11+40h]
0x14001e626  mov     rsp, r11
0x14001e629  pop     r15
0x14001e62b  pop     r14
0x14001e62d  pop     r13
0x14001e62f  pop     r12
0x14001e631  pop     rdi
0x14001e632  retn
0x14001e634  mov     al, byte ptr cs:xmmword_1400875E0
0x14001e63a  test    al, al
0x14001e63c  js      loc_14001E79D
0x14001e642  lea     rcx, [rsp+138h+LockHandle]; LockHandle
0x14001e647  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001e64e  nop     dword ptr [rax+rax+00h]
0x14001e653  mov     r9d, r15d
0x14001e656  mov     r8, rdi
0x14001e659  mov     edx, 1F44h
0x14001e65e  mov     ecx, 2
0x14001e663  call    AFDETW_TRACEABORT
0x14001e668  mov     rcx, rbx
0x14001e66b  call    AfdBeginAbort
0x14001e670  mov     edi, r13d
0x14001e673  jmp     short loc_14001E5F5
0x14001e675  mov     eax, 0C000000Dh
0x14001e67a  jmp     short loc_14001E606
0x14001e67c  test    rax, rax
0x14001e67f  jz      loc_14001E7BE
0x14001e685  mov     ecx, 0Eh
0x14001e68a  int     29h; Win8: RtlFailFast(ecx)
0x14001e68c  jmp     loc_14001E604
0x14001e691  mov     eax, [rdi+8]
0x14001e694  shr     eax, 10h
0x14001e697  and     eax, 0Fh
0x14001e69a  mov     edx, 0Ah
0x14001e69f  mov     ecx, r12d
0x14001e6a2  mov     [rsp+138h+OutputBufferLength], eax
0x14001e6a6  mov     eax, dword ptr [rsp+138h+var_58]
0x14001e6ad  mov     dword ptr [rsp+138h+OutputBuffer], eax
0x14001e6b1  mov     r9, rdi
0x14001e6b4  lea     r8, WPP_56506c8bf8c7385db6ea71daa1f57f8f_Traceguids
0x14001e6bb  call    WPP_SF_qdd
0x14001e6c0  jmp     loc_14001E4AD
0x14001e6c5  lea     r12, [rdi+38h]
0x14001e6c9  lea     rdx, [rsp+138h+LockHandle]; LockHandle
0x14001e6ce  mov     rcx, r12; SpinLock
0x14001e6d1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001e6d8  nop     dword ptr [rax+rax+00h]
0x14001e6dd  mov     eax, dword ptr [rsp+138h+var_58]
0x14001e6e4  test    al, 4
0x14001e6e6  jz      loc_140076F74
0x14001e6ec  mov     eax, [rdi+8]
0x14001e6ef  or      eax, 70000h
0x14001e6f4  mov     [rdi+8], eax
0x14001e6f7  mov     eax, dword ptr [rsp+138h+var_58]
0x14001e6fe  jmp     loc_140076F74
0x14001e703  mov     dl, byte ptr cs:xmmword_1400875E0
0x14001e709  test    dl, dl
0x14001e70b  jns     loc_1400772E9
0x14001e711  mov     edx, 0Bh
0x14001e716  mov     ecx, r12d
0x14001e719  mov     r9, rdi
0x14001e71c  lea     r8, WPP_56506c8bf8c7385db6ea71daa1f57f8f_Traceguids
0x14001e723  call    WPP_SF_q
0x14001e728  nop
0x14001e729  jmp     loc_1400772E9
0x14001e72e  mov     rax, [rbx+48h]
0x14001e732  add     rax, [rbx+40h]
0x14001e736  cmp     [rbx+38h], rax
0x14001e73a  jg      loc_140077317
0x14001e740  cmp     [rbx+69h], r13b
0x14001e744  jz      loc_14001E56F
0x14001e74a  jmp     loc_140077317
0x14001e74f  mov     rax, [rbx+60h]
0x14001e753  add     rax, [rbx+58h]
0x14001e757  mov     ecx, r13d
0x14001e75a  cmp     [rbx+50h], rax
0x14001e75e  setnle  cl
0x14001e761  jmp     loc_14001E585
0x14001e766  mov     edx, 0Dh
0x14001e76b  mov     ecx, r12d
0x14001e76e  mov     r9, rdi
0x14001e771  lea     r8, WPP_56506c8bf8c7385db6ea71daa1f57f8f_Traceguids
0x14001e778  call    WPP_SF_q
0x14001e77d  jmp     loc_14001E59E
0x14001e782  or      eax, r14d
0x14001e785  mov     [rdi+8], eax
0x14001e788  mov     r15b, sil
0x14001e78b  jmp     loc_14001E5AA
0x14001e790  mov     rcx, rbx
0x14001e793  call    AfdDisconnectReceive
0x14001e798  jmp     loc_14001E5C4
0x14001e79d  mov     edx, 0Ch
0x14001e7a2  mov     ecx, r12d
0x14001e7a5  mov     [rsp+138h+OutputBuffer], rbx
0x14001e7aa  mov     r9, rdi
0x14001e7ad  lea     r8, WPP_56506c8bf8c7385db6ea71daa1f57f8f_Traceguids
0x14001e7b4  call    WPP_SF_qq
0x14001e7b9  jmp     loc_14001E642
0x14001e7be  mov     rcx, rbx
0x14001e7c1  call    AfdCloseConnection
0x14001e7c6  jmp     loc_14001E604
0x140073740  push    rbp
0x140073742  sub     rsp, 50h
0x140073746  mov     rbp, rdx
0x140073749  mov     r8, rcx
0x14007374c  lea     r9, [rbp+54h]
0x140073750  mov     edx, 8Fh
0x140073755  lea     rcx, aMinioSocketsWi_8; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x14007375c  call    AfdExceptionFilter
0x140073761  nop
0x140073762  add     rsp, 50h
0x140073766  pop     rbp
0x140073767  retn
0x140076f74  test    al, 2
0x140076f76  jz      short loc_140076F8E
0x140076f78  mov     eax, [rdi+8]
0x140076f7b  mov     r14d, 20000h
0x140076f81  or      eax, r14d
0x140076f84  mov     [rdi+8], eax
0x140076f87  mov     eax, dword ptr [rsp+138h+var_58]
0x140076f8e  mov     esi, 1
0x140076f93  test    sil, al
0x140076f96  jz      short loc_140076FA2
0x140076f98  mov     eax, [rdi+8]
0x140076f9b  bts     eax, 10h
0x140076f9f  mov     [rdi+8], eax
0x140076fa2  xor     eax, eax
0x140076fa4  lock cmpxchg [rdi+170h], r15d
0x140076fad  jz      short loc_140076FC6
0x140076faf  lea     rcx, [rsp+138h+LockHandle]; LockHandle
0x140076fb4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140076fbb  nop     dword ptr [rax+rax+00h]
0x140076fc0  nop
0x140076fc1  jmp     loc_14001E675
0x140076fc6  test    byte ptr [rsp+138h+var_58], 8
0x140076fce  jz      loc_1400772C0
0x140076fd4  cmp     byte ptr [rdi+2], 4
  ... truncated ...
```
