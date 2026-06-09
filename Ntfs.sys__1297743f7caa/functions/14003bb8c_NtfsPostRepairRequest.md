# NtfsPostRepairRequest

- ea: `0x14003bb8c`
- end: `0x14003c17e`
- name: `NtfsPostRepairRequest`
- size: `1522`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140029d80`
- `0x1400e724c`
- `0x140213920`

## callees

- `0x1400054e8`
- `0x140007ea0`
- `0x14002b4a0`
- `0x14003bb8c`
- `0x14004161c`
- `0x1400416d4`
- `0x1400419f8`
- `0x14004e280`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14003be63`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003be63`
- `ntoskrnl!KeSetEvent` at `0x14003bfc9`
- `ntoskrnl!KeSetEvent` at `0x14003bfc9`
- `ntoskrnl!ZwClose` at `0x14003bd9a`
- `ntoskrnl!ZwClose` at `0x14003bd9a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bcf0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bda9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bdd6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003be2c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bcf0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bda9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bdd6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003be2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003bd2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003be02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003bfa8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003bd2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003be02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003bfa8`
- `ntoskrnl!PsCreateSystemThread` at `0x14003bd7b`
- `ntoskrnl!PsCreateSystemThread` at `0x14003bd7b`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003beb9`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003beb9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003bc1d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003bff2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003bc1d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003bff2`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003bbe8`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003bbe8`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003be19`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003c0a9`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003be19`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003c0a9`

## pseudocode

```c
__int64 __fastcall NtfsPostRepairRequest(__int64 a1, _QWORD *a2)
{
  char v2; // r12
  NTSTATUS v5; // r15d
  unsigned __int64 v6; // rbx
  __int64 StartContext; // r14
  PIRP TopLevelIrp; // rsi
  __int64 v9; // rax
  struct _LIST_ENTRY *Flink; // rcx
  __int64 v11; // rcx
  int v12; // eax
  KIRQL v13; // al
  int v14; // esi
  int v15; // eax
  unsigned __int64 v16; // rsi
  int ActivityIdIrp; // eax
  __int64 v18; // rcx
  _OWORD *ActivityIdThread; // rax
  unsigned __int64 *v20; // rdx
  __int64 v21; // rcx
  char v22; // al
  int v23; // eax
  _OWORD *v24; // rax
  __int64 TopLevelIrpContext; // r14
  __int64 v26; // rsi
  unsigned __int64 v27; // rsi
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rcx
  int Timeout; // [rsp+20h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v35; // [rsp+C0h] [rbp+50h]
  int v36; // [rsp+C8h] [rbp+58h]

  v2 = 0;
  v35 = *(_DWORD *)(a1 + 24);
  v36 = 0;
  v5 = 0;
  v6 = *(_QWORD *)(a1 + 384) & 0xFFFFFFFFFFFFFFFCuLL;
  memset(&ObjectAttributes, 0, 44);
  if ( v35 == -1073741774 )
    *(_DWORD *)(v6 + 16) |= 4u;
  StartContext = *(_QWORD *)(a1 + 104);
  *(_DWORD *)(a1 + 24) = 0;
  TopLevelIrp = IoGetTopLevelIrp();
  if ( byte_140095C54 && !byte_140095C55 )
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  if ( (unsigned __int8)NtfsRepairIsTopLevelRequest(a1) )
  {
    v9 = *(_QWORD *)(a1 + 384);
    if ( v9 )
    {
      if ( (v9 & 3) == 0 )
      {
        if ( a2 && byte_140095C55 )
        {
          *(_DWORD *)(v6 + 16) |= 1u;
          v2 = 1;
          *(_DWORD *)(v6 + 20) = 0;
        }
        goto LABEL_24;
      }
      if ( (v9 & 2) != 0 && a2 && byte_140095C55 )
        goto LABEL_58;
    }
LABEL_73:
    TopLevelIrpContext = NtfsRepairGetTopLevelIrpContext(a1);
    v26 = *(_QWORD *)(TopLevelIrpContext + 384);
    if ( (v26 & 2) != 0 )
    {
      v27 = v26 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v27 + 20), 0, 1) )
        NtfsFreeRepairItem((PVOID)v27);
      *(_QWORD *)(TopLevelIrpContext + 384) = v27 | 1;
    }
    v28 = *(_QWORD *)(a1 + 384);
    if ( v28 && (v28 & 3) == 0 )
    {
      v29 = v6 | 1;
      *(_QWORD *)(a1 + 384) = 0;
      if ( (v5 & 2) != 0 && !(unsigned __int8)NtfsRepairIsTopLevelRequest(a1) )
        v29 |= 2uLL;
      *(_QWORD *)(TopLevelIrpContext + 384) = v29;
    }
    return v35;
  }
  if ( _bittest((const signed __int32 *)(*(_QWORD *)(a1 + 144) + 12LL), 0x14u)
    && LOBYTE(TopLevelIrp->Type)
    && (!HIBYTE(TopLevelIrp->Type)
     || (Flink = TopLevelIrp->AssociatedIrp.MasterIrp->ThreadListEntry.Flink, (HIDWORD(Flink->Flink) & 0x200) == 0)
     || _bittest((const signed __int32 *)&Flink->Blink + 1, 0x14u)) )
  {
    *(_DWORD *)(v6 + 16) |= 2u;
    *(_DWORD *)(v6 + 20) = 1;
  }
  else if ( (unsigned __int8)NtfsRepairIsTopLevelNtfs(a1) && (*(_BYTE *)(a1 + 384) & 1) != 0 )
  {
    goto LABEL_73;
  }
LABEL_24:
  LOBYTE(v11) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(StartContext + 5536));
  LOBYTE(ThreadHandle) = v11;
  v12 = *(_DWORD *)(StartContext + 5564);
  if ( (v12 & 1) != 0 )
  {
    if ( (v12 & 0x400) != 0 )
    {
      v5 = -1073741823;
      goto LABEL_56;
    }
    goto LABEL_33;
  }
  if ( (v12 & 4) != 0 )
  {
    v14 = 20;
    while ( 1 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(StartContext + 5536), v11);
      KeDelayExecutionThread(0, 0, &NtfsShortDelay);
      LOBYTE(v11) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(StartContext + 5536));
      LOBYTE(ThreadHandle) = v11;
      v15 = *(_DWORD *)(StartContext + 5564);
      if ( (v15 & 1) != 0 )
        goto LABEL_33;
      if ( (v15 & 4) == 0 )
      {
        v5 = -1073741823;
        if ( NtfsStatusDebugFlags )
        {
          NtfsStatusTraceAndDebugInternal(0, 3221225473LL, 3016004);
          LOBYTE(v11) = (_BYTE)ThreadHandle;
        }
        goto LABEL_39;
      }
      if ( !--v14 )
        goto LABEL_33;
    }
  }
  ThreadHandle = 0;
  *(_DWORD *)(StartContext + 5564) = v12 | 4;
  KeReleaseSpinLock((PKSPIN_LOCK)(StartContext + 5536), v11);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = PsCreateSystemThread(
         &ThreadHandle,
         0x1FFFFFu,
         &ObjectAttributes,
         0,
         0,
         NtfsProcessRepairQueue,
         (PVOID)StartContext);
  if ( v5 < 0 )
  {
    v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(StartContext + 5536));
    *(_DWORD *)(StartContext + 5564) &= ~4u;
    LOBYTE(v11) = v13;
    LOBYTE(ThreadHandle) = v13;
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(StartContext + 260));
    ZwClose(ThreadHandle);
    LOBYTE(v11) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(StartContext + 5536));
    LOBYTE(ThreadHandle) = v11;
    *(_DWORD *)(StartContext + 5564) = *(_DWORD *)(StartContext + 5564) & 0xFFFFFFFA | 1;
  }
LABEL_39:
  if ( v5 >= 0 )
  {
LABEL_33:
    if ( a2 )
    {
      v16 = v6 + 184;
      ActivityIdIrp = IoGetActivityIdIrp(a2, v6 + 184);
      v18 = (unsigned int)ActivityIdIrp;
      if ( ActivityIdIrp < 0 )
        v16 = 0;
    }
    else
    {
      ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v11);
      if ( ActivityIdThread )
      {
        v16 = v6 + 184;
        *(_OWORD *)(v6 + 184) = *ActivityIdThread;
      }
      else
      {
        v16 = 0;
      }
    }
    *(_QWORD *)(v6 + 176) = v16;
    if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
    {
      Timeout = 8;
      McTemplateK0pq_EtwWriteTransfer(v18, WORKITEM_QUEUE, *(_QWORD *)(v6 + 176));
    }
    v20 = *(unsigned __int64 **)(StartContext + 5552);
    if ( *v20 != StartContext + 5544 )
      __fastfail(3u);
    *(_QWORD *)v6 = StartContext + 5544;
    *(_QWORD *)(v6 + 8) = v20;
    *v20 = v6;
    *(_QWORD *)(StartContext + 5552) = v6;
    ++*(_DWORD *)(StartContext + 5560);
    if ( v2 )
    {
      v21 = *(_QWORD *)(*(_QWORD *)(a1 + 144) + 112LL);
      *(_QWORD *)(v6 + 48) = v21;
      if ( !(unsigned __int8)NtfsSetCancelRoutine(v21, NtfsCancelRepairRequest, v6, 0, Timeout) )
      {
        *(_DWORD *)(v6 + 16) &= ~1u;
        v2 = 0;
        v22 = NtfsStatusDebugFlags;
        *(_QWORD *)(v6 + 48) = 0;
        if ( v22 )
          NtfsStatusTraceAndDebugInternal(0, 3221225760LL, 3016083);
        v35 = -1073741536;
        _InterlockedIncrement((_DWORD *)&xmmword_140094D00 + 3);
      }
    }
    LOBYTE(v11) = (_BYTE)ThreadHandle;
    v36 = *(_DWORD *)(v6 + 16);
  }
LABEL_56:
  KeReleaseSpinLock((PKSPIN_LOCK)(StartContext + 5536), v11);
  if ( v5 < 0 )
  {
    v30 = *(_QWORD *)(a1 + 384);
    if ( v30 && (v30 & 3) == 0 )
    {
      NtfsFreeRepairItem((PVOID)v6);
      *(_QWORD *)(a1 + 384) = 0;
    }
    return v35;
  }
  KeSetEvent((PRKEVENT)(StartContext + 5568), 0, 0);
  if ( !v2 )
  {
    LOBYTE(v5) = v36;
    goto LABEL_73;
  }
LABEL_58:
  KeWaitForSingleObject((PVOID)(v6 + 24), Executive, 0, 0, 0);
  v23 = *(_DWORD *)(v6 + 16);
  if ( (v23 & 0x10) == 0 )
  {
    if ( (v23 & 0x800) != 0 )
    {
      if ( *(_DWORD *)(a2[23] + 8LL) )
      {
        v24 = (_OWORD *)a2[3];
        *v24 = *(_OWORD *)(v6 + 112);
        v24[1] = *(_OWORD *)(v6 + 128);
        a2[7] = 32;
      }
      v35 = 0;
    }
    else
    {
      v35 = -1073741608;
    }
    *(_QWORD *)(a1 + 384) = 0;
    while ( *(_DWORD *)(v6 + 20) )
      KeDelayExecutionThread(0, 0, &NtfsShortDelay);
    goto LABEL_62;
  }
  _InterlockedIncrement((_DWORD *)&xmmword_140094D10 + 1);
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225760LL, 3016137);
  v35 = -1073741536;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v6 + 20), 0, 1) )
LABEL_62:
    NtfsFreeRepairItem((PVOID)v6);
  return v35;
}

```

## disassembly

```asm
0x14003bb8c  mov     [rsp-38h+arg_8], rbx
0x14003bb91  push    rbp
0x14003bb92  push    rsi
0x14003bb93  push    rdi
0x14003bb94  push    r12
0x14003bb96  push    r13
0x14003bb98  push    r14
0x14003bb9a  push    r15
0x14003bb9c  mov     rbp, rsp
0x14003bb9f  sub     rsp, 70h
0x14003bba3  mov     eax, [rcx+18h]
0x14003bba6  xorps   xmm0, xmm0
0x14003bba9  xor     r12d, r12d
0x14003bbac  mov     [rbp+arg_10], eax
0x14003bbaf  mov     rdi, rcx
0x14003bbb2  mov     [rbp+arg_18], r12d
0x14003bbb6  xor     ecx, ecx
0x14003bbb8  mov     r13, rdx
0x14003bbbb  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14003bbbf  mov     r15d, r12d
0x14003bbc2  mov     rbx, [rdi+180h]
0x14003bbc9  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14003bbcd  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003bbd1  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14003bbd5  cmp     eax, 0C0000032h
0x14003bbda  jnz     short loc_14003BBE0
0x14003bbdc  or      dword ptr [rbx+10h], 4
0x14003bbe0  mov     r14, [rdi+68h]
0x14003bbe4  mov     [rdi+18h], r12d
0x14003bbe8  call    cs:__imp_IoGetTopLevelIrp
0x14003bbef  nop     dword ptr [rax+rax+00h]
0x14003bbf4  cmp     cs:byte_140095C54, r12b
0x14003bbfb  mov     rsi, rax
0x14003bbfe  jz      short loc_14003BC29
0x14003bc00  cmp     cs:byte_140095C55, r12b
0x14003bc07  jnz     short loc_14003BC29
0x14003bc09  xor     r9d, r9d; Alertable
0x14003bc0c  mov     [rsp+70h+Timeout], r12; Timeout
0x14003bc11  xor     r8d, r8d; WaitMode
0x14003bc14  lea     rcx, Event; Object
0x14003bc1b  xor     edx, edx; WaitReason
0x14003bc1d  call    cs:__imp_KeWaitForSingleObject
0x14003bc24  nop     dword ptr [rax+rax+00h]
0x14003bc29  mov     rcx, rdi
0x14003bc2c  call    NtfsRepairIsTopLevelRequest
0x14003bc31  test    al, al
0x14003bc33  jz      short loc_14003BC8F
0x14003bc35  mov     rax, [rdi+180h]
0x14003bc3c  test    rax, rax
0x14003bc3f  jz      loc_14003C0C4
0x14003bc45  test    al, 3
0x14003bc47  jnz     short loc_14003BC6C
0x14003bc49  test    r13, r13
0x14003bc4c  jz      loc_14003BCE6
0x14003bc52  cmp     cs:byte_140095C55, r12b
0x14003bc59  jz      loc_14003BCE6
0x14003bc5f  or      dword ptr [rbx+10h], 1
0x14003bc63  mov     r12b, 1
0x14003bc66  mov     [rbx+14h], r15d
0x14003bc6a  jmp     short loc_14003BCE6
0x14003bc6c  test    al, 2
0x14003bc6e  jz      loc_14003C0C4
0x14003bc74  test    r13, r13
0x14003bc77  jz      loc_14003C0C4
0x14003bc7d  cmp     cs:byte_140095C55, r12b
0x14003bc84  jz      loc_14003C0C4
0x14003bc8a  jmp     loc_14003BFE1
0x14003bc8f  mov     rax, [rdi+90h]
0x14003bc96  bt      dword ptr [rax+0Ch], 14h
0x14003bc9b  jnb     short loc_14003BCCD
0x14003bc9d  cmp     [rsi], r12b
0x14003bca0  jz      short loc_14003BCCD
0x14003bca2  cmp     [rsi+1], r12b
0x14003bca6  jz      short loc_14003BCC0
0x14003bca8  mov     rax, [rsi+18h]
0x14003bcac  mov     rcx, [rax+20h]
0x14003bcb0  test    dword ptr [rcx+4], 200h
0x14003bcb7  jz      short loc_14003BCC0
0x14003bcb9  bt      dword ptr [rcx+0Ch], 14h
0x14003bcbe  jnb     short loc_14003BCCD
0x14003bcc0  or      dword ptr [rbx+10h], 2
0x14003bcc4  mov     dword ptr [rbx+14h], 1
0x14003bccb  jmp     short loc_14003BCE6
0x14003bccd  mov     rcx, rdi
0x14003bcd0  call    NtfsRepairIsTopLevelNtfs
0x14003bcd5  test    al, al
0x14003bcd7  jz      short loc_14003BCE6
0x14003bcd9  test    byte ptr [rdi+180h], 1
0x14003bce0  jnz     loc_14003C0C4
0x14003bce6  lea     rsi, [r14+15A0h]
0x14003bced  mov     rcx, rsi; SpinLock
0x14003bcf0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003bcf7  nop     dword ptr [rax+rax+00h]
0x14003bcfc  mov     cl, al
0x14003bcfe  mov     byte ptr [rbp+ThreadHandle], al
0x14003bd01  mov     eax, [r14+15BCh]
0x14003bd08  test    al, 1
0x14003bd0a  jnz     loc_14003BEA8
0x14003bd10  test    al, 4
0x14003bd12  jnz     loc_14003BDF4
0x14003bd18  or      eax, 4
0x14003bd1b  mov     [rbp+ThreadHandle], r15
0x14003bd1f  mov     dl, cl; NewIrql
0x14003bd21  mov     [r14+15BCh], eax
0x14003bd28  mov     rcx, rsi; SpinLock
0x14003bd2b  call    cs:__imp_KeReleaseSpinLock
0x14003bd32  nop     dword ptr [rax+rax+00h]
0x14003bd37  lea     rax, NtfsProcessRepairQueue
0x14003bd3e  mov     [rsp+70h+StartContext], r14; StartContext
0x14003bd43  xorps   xmm0, xmm0
0x14003bd46  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x14003bd4b  xor     r9d, r9d; ProcessHandle
0x14003bd4e  mov     [rsp+70h+Timeout], r15; ClientId
0x14003bd53  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003bd57  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14003bd5e  mov     edx, 1FFFFFh; DesiredAccess
0x14003bd63  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x14003bd67  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14003bd6b  mov     [rbp+ObjectAttributes.Attributes], 200h
0x14003bd72  mov     [rbp+ObjectAttributes.ObjectName], r15
0x14003bd76  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003bd7b  call    cs:__imp_PsCreateSystemThread
0x14003bd82  nop     dword ptr [rax+rax+00h]
0x14003bd87  mov     r15d, eax
0x14003bd8a  test    eax, eax
0x14003bd8c  js      short loc_14003BDD3
0x14003bd8e  lock inc dword ptr [r14+104h]
0x14003bd96  mov     rcx, [rbp+ThreadHandle]; Handle
0x14003bd9a  call    cs:__imp_ZwClose
0x14003bda1  nop     dword ptr [rax+rax+00h]
0x14003bda6  mov     rcx, rsi; SpinLock
0x14003bda9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003bdb0  nop     dword ptr [rax+rax+00h]
0x14003bdb5  mov     cl, al
0x14003bdb7  mov     byte ptr [rbp+ThreadHandle], al
0x14003bdba  mov     eax, [r14+15BCh]
0x14003bdc1  and     eax, 0FFFFFFFBh
0x14003bdc4  or      eax, 1
0x14003bdc7  mov     [r14+15BCh], eax
0x14003bdce  jmp     loc_14003BE9E
0x14003bdd3  mov     rcx, rsi; SpinLock
0x14003bdd6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003bddd  nop     dword ptr [rax+rax+00h]
0x14003bde2  and     dword ptr [r14+15BCh], 0FFFFFFFBh
0x14003bdea  mov     cl, al
0x14003bdec  mov     byte ptr [rbp+ThreadHandle], al
0x14003bdef  jmp     loc_14003BE9E
0x14003bdf4  mov     esi, 14h
0x14003bdf9  mov     dl, cl; NewIrql
0x14003bdfb  lea     rcx, [r14+15A0h]; SpinLock
0x14003be02  call    cs:__imp_KeReleaseSpinLock
0x14003be09  nop     dword ptr [rax+rax+00h]
0x14003be0e  lea     r8, NtfsShortDelay; Interval
0x14003be15  xor     edx, edx; Alertable
0x14003be17  xor     ecx, ecx; WaitMode
0x14003be19  call    cs:__imp_KeDelayExecutionThread
0x14003be20  nop     dword ptr [rax+rax+00h]
0x14003be25  lea     rcx, [r14+15A0h]; SpinLock
0x14003be2c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003be33  nop     dword ptr [rax+rax+00h]
0x14003be38  mov     cl, al
0x14003be3a  mov     byte ptr [rbp+ThreadHandle], al
0x14003be3d  mov     eax, [r14+15BCh]
0x14003be44  test    al, 1
0x14003be46  jnz     short loc_14003BE51
0x14003be48  test    al, 4
0x14003be4a  jz      short loc_14003BE7B
0x14003be4c  add     esi, 0FFFFFFFFh
0x14003be4f  jnz     short loc_14003BDF9
0x14003be51  test    r13, r13
0x14003be54  jz      short loc_14003BEB9
0x14003be56  lea     rsi, [rbx+0B8h]
0x14003be5d  mov     rcx, r13
0x14003be60  mov     rdx, rsi
0x14003be63  call    cs:__imp_IoGetActivityIdIrp
0x14003be6a  nop     dword ptr [rax+rax+00h]
0x14003be6f  mov     ecx, eax
0x14003be71  xor     eax, eax
0x14003be73  test    ecx, ecx
0x14003be75  cmovs   rsi, rax
0x14003be79  jmp     short loc_14003BEDC
0x14003be7b  mov     al, cs:NtfsStatusDebugFlags
0x14003be81  mov     r15d, 0C0000001h
0x14003be87  test    al, al
0x14003be89  jz      short loc_14003BE9E
0x14003be8b  mov     r8d, 2E0544h
0x14003be91  mov     edx, r15d
0x14003be94  xor     ecx, ecx
0x14003be96  call    NtfsStatusTraceAndDebugInternal
0x14003be9b  mov     cl, byte ptr [rbp+ThreadHandle]
0x14003be9e  test    r15d, r15d
0x14003bea1  jns     short loc_14003BE51
0x14003bea3  jmp     loc_14003BF9F
0x14003bea8  bt      eax, 0Ah
0x14003beac  jnb     short loc_14003BE51
0x14003beae  mov     r15d, 0C0000001h
0x14003beb4  jmp     loc_14003BF9F
0x14003beb9  call    cs:__imp_IoGetActivityIdThread
0x14003bec0  nop     dword ptr [rax+rax+00h]
0x14003bec5  test    rax, rax
0x14003bec8  jz      short loc_14003BEDA
0x14003beca  movups  xmm0, xmmword ptr [rax]
0x14003becd  lea     rsi, [rbx+0B8h]
0x14003bed4  movdqu  xmmword ptr [rsi], xmm0
0x14003bed8  jmp     short loc_14003BEDC
0x14003beda  xor     esi, esi
0x14003bedc  mov     [rbx+0B0h], rsi
0x14003bee3  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14003beea  jz      short loc_14003BF07
0x14003beec  mov     r8, [rbx+0B0h]
0x14003bef3  lea     rdx, WORKITEM_QUEUE
0x14003befa  mov     dword ptr [rsp+70h+Timeout], 8
0x14003bf02  call    McTemplateK0pq_EtwWriteTransfer
0x14003bf07  lea     rax, [r14+15A8h]
0x14003bf0e  mov     rdx, [rax+8]
0x14003bf12  cmp     [rdx], rax
0x14003bf15  jz      short loc_14003BF1E
0x14003bf17  mov     ecx, 3
0x14003bf1c  int     29h; Win8: RtlFailFast(ecx)
0x14003bf1e  mov     [rbx], rax
0x14003bf21  mov     [rbx+8], rdx
0x14003bf25  mov     [rdx], rbx
0x14003bf28  mov     [rax+8], rbx
0x14003bf2c  inc     dword ptr [r14+15B8h]
0x14003bf33  test    r12b, r12b
0x14003bf36  jz      short loc_14003BF96
0x14003bf38  mov     rax, [rdi+90h]
0x14003bf3f  lea     rdx, NtfsCancelRepairRequest
0x14003bf46  xor     r9d, r9d
0x14003bf49  mov     r8, rbx
0x14003bf4c  mov     rcx, [rax+70h]
0x14003bf50  mov     [rbx+30h], rcx
0x14003bf54  call    NtfsSetCancelRoutine
0x14003bf59  test    al, al
0x14003bf5b  jnz     short loc_14003BF96
0x14003bf5d  and     dword ptr [rbx+10h], 0FFFFFFFEh
0x14003bf61  xor     r12b, r12b
0x14003bf64  mov     al, cs:NtfsStatusDebugFlags
0x14003bf6a  mov     qword ptr [rbx+30h], 0
0x14003bf72  test    al, al
0x14003bf74  jz      short loc_14003BF88
0x14003bf76  mov     edx, 0C0000120h
0x14003bf7b  xor     ecx, ecx
0x14003bf7d  mov     r8d, 2E0593h
0x14003bf83  call    NtfsStatusTraceAndDebugInternal
0x14003bf88  mov     [rbp+arg_10], 0C0000120h
0x14003bf8f  lock inc dword ptr cs:xmmword_140094D00+0Ch
0x14003bf96  mov     eax, [rbx+10h]
0x14003bf99  mov     cl, byte ptr [rbp+ThreadHandle]
0x14003bf9c  mov     [rbp+arg_18], eax
0x14003bf9f  mov     dl, cl; NewIrql
0x14003bfa1  lea     rcx, [r14+15A0h]; SpinLock
0x14003bfa8  call    cs:__imp_KeReleaseSpinLock
0x14003bfaf  nop     dword ptr [rax+rax+00h]
0x14003bfb4  test    r15d, r15d
0x14003bfb7  js      loc_14003C13E
0x14003bfbd  lea     rcx, [r14+15C0h]; Event
0x14003bfc4  xor     r8d, r8d; Wait
0x14003bfc7  xor     edx, edx; Increment
0x14003bfc9  call    cs:__imp_KeSetEvent
0x14003bfd0  nop     dword ptr [rax+rax+00h]
0x14003bfd5  test    r12b, r12b
0x14003bfd8  jz      loc_14003C0BD
0x14003bfde  xor     r12d, r12d
0x14003bfe1  lea     rcx, [rbx+18h]; Object
0x14003bfe5  mov     [rsp+70h+Timeout], r12; Timeout
0x14003bfea  xor     r9d, r9d; Alertable
0x14003bfed  xor     r8d, r8d; WaitMode
0x14003bff0  xor     edx, edx; WaitReason
0x14003bff2  call    cs:__imp_KeWaitForSingleObject
0x14003bff9  nop     dword ptr [rax+rax+00h]
0x14003bffe  mov     eax, [rbx+10h]
0x14003c001  test    al, 10h
0x14003c003  jz      short loc_14003C051
0x14003c005  lock inc dword ptr cs:xmmword_140094D10+4
0x14003c00c  mov     al, cs:NtfsStatusDebugFlags
0x14003c012  test    al, al
0x14003c014  jz      short loc_14003C028
0x14003c016  mov     edx, 0C0000120h
0x14003c01b  xor     ecx, ecx
0x14003c01d  mov     r8d, 2E05C9h
0x14003c023  call    NtfsStatusTraceAndDebugInternal
0x14003c028  mov     [rbp+arg_10], 0C0000120h
0x14003c02f  mov     edx, r12d
0x14003c032  mov     eax, 1
0x14003c037  lock cmpxchg [rbx+14h], edx
0x14003c03c  test    eax, eax
0x14003c03e  jnz     loc_14003C162
0x14003c044  mov     rcx, rbx; P
0x14003c047  call    NtfsFreeRepairItem
0x14003c04c  jmp     loc_14003C162
0x14003c051  bt      eax, 0Bh
0x14003c055  jnb     short loc_14003C088
0x14003c057  mov     rax, [r13+0B8h]
0x14003c05e  cmp     [rax+8], r12d
0x14003c062  jz      short loc_14003C082
0x14003c064  movups  xmm0, xmmword ptr [rbx+70h]
0x14003c068  mov     rax, [r13+18h]
0x14003c06c  movups  xmmword ptr [rax], xmm0
0x14003c06f  movups  xmm1, xmmword ptr [rbx+80h]
  ... truncated ...
```
