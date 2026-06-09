# NtfsProcessRepairQueue

- ea: `0x14004dd00`
- end: `0x14004e142`
- name: `NtfsProcessRepairQueue`
- size: `1090`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400054e8`
- `0x14002b4a0`
- `0x14004161c`
- `0x14004dd00`
- `0x14004e1fc`
- `0x1400592c0`
- `0x1400ec79c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14004de2e`
- `ntoskrnl!KeSetEvent` at `0x14004de54`
- `ntoskrnl!KeSetEvent` at `0x14004dff3`
- `ntoskrnl!KeSetEvent` at `0x14004e00e`
- `ntoskrnl!KeSetEvent` at `0x14004e04a`
- `ntoskrnl!KeSetEvent` at `0x14004e0b0`
- `ntoskrnl!KeSetEvent` at `0x14004e0d4`
- `ntoskrnl!KeSetEvent` at `0x14004de2e`
- `ntoskrnl!KeSetEvent` at `0x14004de54`
- `ntoskrnl!KeSetEvent` at `0x14004dff3`
- `ntoskrnl!KeSetEvent` at `0x14004e00e`
- `ntoskrnl!KeSetEvent` at `0x14004e04a`
- `ntoskrnl!KeSetEvent` at `0x14004e0b0`
- `ntoskrnl!KeSetEvent` at `0x14004e0d4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004dd2a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004dd2a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e109`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e109`
- `ntoskrnl!IoSetActivityIdThread` at `0x14004deff`
- `ntoskrnl!IoSetActivityIdThread` at `0x14004deff`
- `ntoskrnl!IoClearActivityIdThread` at `0x14004e07a`
- `ntoskrnl!IoClearActivityIdThread` at `0x14004e07a`
- `ntoskrnl!RtlFindMessage` at `0x14004dd78`
- `ntoskrnl!RtlFindMessage` at `0x14004dd78`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004ddd2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004de95`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004ddd2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004de95`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004de66`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004df65`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004dfc7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e0f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004de66`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004df65`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004dfc7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e0f8`
- `ntoskrnl!KeClearEvent` at `0x14004de08`
- `ntoskrnl!KeClearEvent` at `0x14004de08`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004de86`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004df89`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004de86`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004df89`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14004ddaf`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14004ddaf`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14004dd96`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14004dd96`

## pseudocode

```c
void __fastcall NtfsProcessRepairQueue(char *StartContext)
{
  KIRQL v2; // r15
  int v3; // eax
  __int64 *v4; // rdi
  int v5; // esi
  _QWORD *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 *v11; // rcx
  __int64 **v12; // rax
  int v13; // eax
  int MessageResourceEntry; // [rsp+20h] [rbp-40h]
  PMESSAGE_RESOURCE_ENTRY v15; // [rsp+30h] [rbp-30h] BYREF
  __int128 v16; // [rsp+38h] [rbp-28h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h]

  KeEnterCriticalRegion();
  *((_QWORD *)StartContext + 691) = KeGetCurrentThread();
  if ( !byte_140095C55 )
  {
    v15 = 0;
    byte_140095C55 = RtlFindMessage(DriverObject->DriverStart, 0xBu, 0, 0x61B0u, &v15) >= 0;
  }
  KeAcquireGuardedMutex(&NtfsRepairEventCounterMutex);
  ++NtfsRepairThreadCount;
  KeReleaseGuardedMutex(&NtfsRepairEventCounterMutex);
  while ( 1 )
  {
    v17 = 0;
    v16 = 0;
    v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)StartContext + 692);
    if ( *((_DWORD *)StartContext + 1390) )
      goto LABEL_12;
    *((_DWORD *)StartContext + 1391) |= 0x800u;
    v15 = (PMESSAGE_RESOURCE_ENTRY)-600000000LL;
    KeClearEvent((PRKEVENT)StartContext + 232);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 1398, 0, 0) )
      KeSetEvent((PRKEVENT)(StartContext + 5600), 0, 0);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 1406, 0, 0) )
      KeSetEvent((PRKEVENT)(StartContext + 5632), 0, 0);
    do
    {
      KeReleaseSpinLock((PKSPIN_LOCK)StartContext + 692, v2);
      KeWaitForSingleObject(StartContext + 5568, Executive, 0, 0, (PLARGE_INTEGER)&v15);
      v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)StartContext + 692);
      v3 = *((_DWORD *)StartContext + 1391);
    }
    while ( (v3 & 4) != 0 );
    if ( !*((_DWORD *)StartContext + 1390) )
      break;
    *((_DWORD *)StartContext + 1391) = v3 & 0xFFFFF7FF;
LABEL_12:
    v4 = (__int64 *)*((_QWORD *)StartContext + 693);
    v5 = 0;
    v6 = (_QWORD *)v4[22];
    if ( v6 )
    {
      *((_QWORD *)&v16 + 1) = *v6;
      v17 = v6[1];
      *(_QWORD *)&v16 = (char *)&v16 + 8;
    }
    else
    {
      *(_QWORD *)&v16 = 0;
    }
    v8 = IoSetActivityIdThread(v16);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
    {
      MessageResourceEntry = 8;
      McTemplateK0pq_EtwWriteTransfer(v7, WORKITEM_START, v16);
    }
    while ( 1 )
    {
      v9 = v4[6];
      if ( !v9 || (unsigned __int8)NtfsSetCancelRoutine(v9, 0, 0, 0, MessageResourceEntry) )
        break;
      _InterlockedIncrement((volatile signed __int32 *)&xmmword_140094D10);
      if ( *((_DWORD *)StartContext + 1390) <= (unsigned int)++v5 )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)StartContext + 692, v2);
        KeWaitForSingleObject(StartContext + 5568, Executive, 0, 0, 0);
        goto LABEL_32;
      }
      v4 = (__int64 *)*v4;
    }
    v11 = (__int64 *)*v4;
    if ( *(__int64 **)(*v4 + 8) != v4 || (v12 = (__int64 **)v4[1], *v12 != v4) )
      __fastfail(3u);
    *v12 = v11;
    v11[1] = (__int64)v12;
    --*((_DWORD *)StartContext + 1390);
    KeReleaseSpinLock((PKSPIN_LOCK)StartContext + 692, v2);
    if ( v5 != -1 )
    {
      NtfsRepairItem(StartContext, v4);
      v13 = *((_DWORD *)v4 + 4);
      if ( (v13 & 1) != 0 )
      {
        KeSetEvent((PRKEVENT)v4 + 1, 0, 0);
      }
      else if ( (v13 & 2) == 0
             || (KeSetEvent((PRKEVENT)v4 + 1, 0, 0),
                 !_InterlockedCompareExchange((volatile signed __int32 *)v4 + 5, 0, 1)) )
      {
        NtfsFreeRepairItem(v4);
      }
      v10 = 0;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 1398, 0, 0) )
        KeSetEvent((PRKEVENT)(StartContext + 5600), 0, 0);
    }
LABEL_32:
    if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
    {
      MessageResourceEntry = 8;
      McTemplateK0pq_EtwWriteTransfer(v10, WORKITEM_COMPLETE, v16);
    }
    IoClearActivityIdThread(v8);
  }
  *((_DWORD *)StartContext + 1391) = v3 & 0xFFFFF7FE;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 1398, 0, 0) )
    KeSetEvent((PRKEVENT)(StartContext + 5600), 0, 0);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 1406, 0, 0) )
    KeSetEvent((PRKEVENT)(StartContext + 5632), 0, 0);
  *((_QWORD *)StartContext + 691) = 0;
  _InterlockedDecrement((volatile signed __int32 *)StartContext + 65);
  KeReleaseSpinLock((PKSPIN_LOCK)StartContext + 692, v2);
  NtfsRepairEndThreadUpdate();
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14004dd00  mov     [rsp-28h+arg_8], rbx
0x14004dd05  mov     [rsp-28h+arg_10], rsi
0x14004dd0a  push    rbp
0x14004dd0b  push    rdi
0x14004dd0c  push    r12
0x14004dd0e  push    r14
0x14004dd10  push    r15
0x14004dd12  mov     rbp, rsp
0x14004dd15  sub     rsp, 60h
0x14004dd19  mov     rax, cs:__security_cookie
0x14004dd20  xor     rax, rsp
0x14004dd23  mov     [rbp+var_10], rax
0x14004dd27  mov     rbx, rcx
0x14004dd2a  call    cs:__imp_KeEnterCriticalRegion
0x14004dd31  nop     dword ptr [rax+rax+00h]
0x14004dd36  mov     rax, gs:188h
0x14004dd3f  mov     [rbx+1598h], rax
0x14004dd46  cmp     cs:byte_140095C55, 0
0x14004dd4d  jnz     short loc_14004DD8F
0x14004dd4f  mov     rcx, cs:DriverObject
0x14004dd56  lea     rax, [rbp+var_30]
0x14004dd5a  xor     r8d, r8d; Language
0x14004dd5d  mov     [rbp+var_30], 0
0x14004dd65  mov     r9d, 61B0h; MessageId
0x14004dd6b  mov     qword ptr [rsp+60h+MessageResourceEntry], rax; MessageResourceEntry
0x14004dd70  mov     rcx, [rcx+18h]; BaseAddress
0x14004dd74  lea     edx, [r8+0Bh]; Type
0x14004dd78  call    cs:__imp_RtlFindMessage
0x14004dd7f  nop     dword ptr [rax+rax+00h]
0x14004dd84  test    eax, eax
0x14004dd86  js      short loc_14004DD8F
0x14004dd88  mov     cs:byte_140095C55, 1
0x14004dd8f  lea     rcx, NtfsRepairEventCounterMutex; Mutex
0x14004dd96  call    cs:__imp_KeAcquireGuardedMutex
0x14004dd9d  nop     dword ptr [rax+rax+00h]
0x14004dda2  inc     cs:NtfsRepairThreadCount
0x14004dda8  lea     rcx, NtfsRepairEventCounterMutex; Mutex
0x14004ddaf  call    cs:__imp_KeReleaseGuardedMutex
0x14004ddb6  nop     dword ptr [rax+rax+00h]
0x14004ddbb  lea     r12, [rbx+15A0h]
0x14004ddc2  xorps   xmm0, xmm0
0x14004ddc5  xor     eax, eax
0x14004ddc7  mov     rcx, r12; SpinLock
0x14004ddca  mov     [rbp+var_18], rax
0x14004ddce  movups  [rbp+var_28], xmm0
0x14004ddd2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004ddd9  nop     dword ptr [rax+rax+00h]
0x14004ddde  cmp     dword ptr [rbx+15B8h], 0
0x14004dde5  mov     r15b, al
0x14004dde8  jnz     loc_14004DEC5
0x14004ddee  bts     dword ptr [rbx+15BCh], 0Bh
0x14004ddf6  lea     rdi, [rbx+15C0h]
0x14004ddfd  mov     rcx, rdi; Event
0x14004de00  mov     [rbp+var_30], 0FFFFFFFFDC3CBA00h
0x14004de08  call    cs:__imp_KeClearEvent
0x14004de0f  nop     dword ptr [rax+rax+00h]
0x14004de14  xor     ecx, ecx
0x14004de16  xor     eax, eax
0x14004de18  lock cmpxchg [rbx+15D8h], ecx
0x14004de20  jz      short loc_14004DE3A
0x14004de22  lea     rcx, [rbx+15E0h]; Event
0x14004de29  xor     r8d, r8d; Wait
0x14004de2c  xor     edx, edx; Increment
0x14004de2e  call    cs:__imp_KeSetEvent
0x14004de35  nop     dword ptr [rax+rax+00h]
0x14004de3a  xor     ecx, ecx
0x14004de3c  xor     eax, eax
0x14004de3e  lock cmpxchg [rbx+15F8h], ecx
0x14004de46  jz      short loc_14004DE60
0x14004de48  lea     rcx, [rbx+1600h]; Event
0x14004de4f  xor     r8d, r8d; Wait
0x14004de52  xor     edx, edx; Increment
0x14004de54  call    cs:__imp_KeSetEvent
0x14004de5b  nop     dword ptr [rax+rax+00h]
0x14004de60  mov     dl, r15b; NewIrql
0x14004de63  mov     rcx, r12; SpinLock
0x14004de66  call    cs:__imp_KeReleaseSpinLock
0x14004de6d  nop     dword ptr [rax+rax+00h]
0x14004de72  lea     rax, [rbp+var_30]
0x14004de76  xor     r9d, r9d; Alertable
0x14004de79  xor     r8d, r8d; WaitMode
0x14004de7c  mov     qword ptr [rsp+60h+MessageResourceEntry], rax; Timeout
0x14004de81  xor     edx, edx; WaitReason
0x14004de83  mov     rcx, rdi; Object
0x14004de86  call    cs:__imp_KeWaitForSingleObject
0x14004de8d  nop     dword ptr [rax+rax+00h]
0x14004de92  mov     rcx, r12; SpinLock
0x14004de95  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004de9c  nop     dword ptr [rax+rax+00h]
0x14004dea1  mov     r15b, al
0x14004dea4  mov     eax, [rbx+15BCh]
0x14004deaa  test    al, 4
0x14004deac  jnz     short loc_14004DE60
0x14004deae  cmp     dword ptr [rbx+15B8h], 0
0x14004deb5  jz      loc_14004E08B
0x14004debb  btr     eax, 0Bh
0x14004debf  mov     [rbx+15BCh], eax
0x14004dec5  mov     rdi, [rbx+15A8h]
0x14004decc  xor     esi, esi
0x14004dece  mov     rcx, [rdi+0B0h]
0x14004ded5  test    rcx, rcx
0x14004ded8  jz      short loc_14004DEF3
0x14004deda  mov     rax, [rcx]
0x14004dedd  mov     qword ptr [rbp+var_28+8], rax
0x14004dee1  mov     rax, [rcx+8]
0x14004dee5  mov     [rbp+var_18], rax
0x14004dee9  lea     rax, [rbp+var_28+8]
0x14004deed  mov     qword ptr [rbp+var_28], rax
0x14004def1  jmp     short loc_14004DEF7
0x14004def3  mov     qword ptr [rbp+var_28], rsi
0x14004def7  mov     rax, qword ptr [rbp+var_28]
0x14004defb  mov     rcx, qword ptr [rbp+var_28]
0x14004deff  call    cs:__imp_IoSetActivityIdThread
0x14004df06  nop     dword ptr [rax+rax+00h]
0x14004df0b  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14004df12  mov     r14, rax
0x14004df15  jz      short loc_14004DF2F
0x14004df17  mov     r8, qword ptr [rbp+var_28]
0x14004df1b  lea     rdx, WORKITEM_START
0x14004df22  mov     [rsp+60h+MessageResourceEntry], 8
0x14004df2a  call    McTemplateK0pq_EtwWriteTransfer
0x14004df2f  mov     rcx, [rdi+30h]
0x14004df33  test    rcx, rcx
0x14004df36  jz      short loc_14004DF9A
0x14004df38  xor     r9d, r9d
0x14004df3b  xor     r8d, r8d
0x14004df3e  xor     edx, edx
0x14004df40  call    NtfsSetCancelRoutine
0x14004df45  test    al, al
0x14004df47  jnz     short loc_14004DF9A
0x14004df49  lock inc dword ptr cs:xmmword_140094D10
0x14004df50  inc     esi
0x14004df52  cmp     [rbx+15B8h], esi
0x14004df58  jbe     short loc_14004DF5F
0x14004df5a  mov     rdi, [rdi]
0x14004df5d  jmp     short loc_14004DF2F
0x14004df5f  mov     dl, r15b; NewIrql
0x14004df62  mov     rcx, r12; SpinLock
0x14004df65  call    cs:__imp_KeReleaseSpinLock
0x14004df6c  nop     dword ptr [rax+rax+00h]
0x14004df71  lea     rcx, [rbx+15C0h]; Object
0x14004df78  mov     qword ptr [rsp+60h+MessageResourceEntry], 0; Timeout
0x14004df81  xor     r9d, r9d; Alertable
0x14004df84  xor     r8d, r8d; WaitMode
0x14004df87  xor     edx, edx; WaitReason
0x14004df89  call    cs:__imp_KeWaitForSingleObject
0x14004df90  nop     dword ptr [rax+rax+00h]
0x14004df95  jmp     loc_14004E056
0x14004df9a  mov     rcx, [rdi]
0x14004df9d  cmp     [rcx+8], rdi
0x14004dfa1  jnz     loc_14004E13B
0x14004dfa7  mov     rax, [rdi+8]
0x14004dfab  cmp     [rax], rdi
0x14004dfae  jnz     loc_14004E13B
0x14004dfb4  mov     [rax], rcx
0x14004dfb7  mov     dl, r15b; NewIrql
0x14004dfba  mov     [rcx+8], rax
0x14004dfbe  mov     rcx, r12; SpinLock
0x14004dfc1  dec     dword ptr [rbx+15B8h]
0x14004dfc7  call    cs:__imp_KeReleaseSpinLock
0x14004dfce  nop     dword ptr [rax+rax+00h]
0x14004dfd3  cmp     esi, 0FFFFFFFFh
0x14004dfd6  jz      short loc_14004E056
0x14004dfd8  mov     rdx, rdi
0x14004dfdb  mov     rcx, rbx
0x14004dfde  call    NtfsRepairItem
0x14004dfe3  mov     eax, [rdi+10h]
0x14004dfe6  test    al, 1
0x14004dfe8  jz      short loc_14004E001
0x14004dfea  lea     rcx, [rdi+18h]; Event
0x14004dfee  xor     r8d, r8d; Wait
0x14004dff1  xor     edx, edx; Increment
0x14004dff3  call    cs:__imp_KeSetEvent
0x14004dffa  nop     dword ptr [rax+rax+00h]
0x14004dfff  jmp     short loc_14004E030
0x14004e001  test    al, 2
0x14004e003  jz      short loc_14004E028
0x14004e005  lea     rcx, [rdi+18h]; Event
0x14004e009  xor     r8d, r8d; Wait
0x14004e00c  xor     edx, edx; Increment
0x14004e00e  call    cs:__imp_KeSetEvent
0x14004e015  nop     dword ptr [rax+rax+00h]
0x14004e01a  xor     edx, edx
0x14004e01c  lea     eax, [rdx+1]
0x14004e01f  lock cmpxchg [rdi+14h], edx
0x14004e024  test    eax, eax
0x14004e026  jnz     short loc_14004E030
0x14004e028  mov     rcx, rdi; P
0x14004e02b  call    NtfsFreeRepairItem
0x14004e030  xor     ecx, ecx
0x14004e032  xor     eax, eax
0x14004e034  lock cmpxchg [rbx+15D8h], ecx
0x14004e03c  jz      short loc_14004E056
0x14004e03e  lea     rcx, [rbx+15E0h]; Event
0x14004e045  xor     r8d, r8d; Wait
0x14004e048  xor     edx, edx; Increment
0x14004e04a  call    cs:__imp_KeSetEvent
0x14004e051  nop     dword ptr [rax+rax+00h]
0x14004e056  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14004e05d  jz      short loc_14004E077
0x14004e05f  mov     r8, qword ptr [rbp+var_28]
0x14004e063  lea     rdx, WORKITEM_COMPLETE
0x14004e06a  mov     [rsp+60h+MessageResourceEntry], 8
0x14004e072  call    McTemplateK0pq_EtwWriteTransfer
0x14004e077  mov     rcx, r14
0x14004e07a  call    cs:__imp_IoClearActivityIdThread
0x14004e081  nop     dword ptr [rax+rax+00h]
0x14004e086  jmp     loc_14004DDC2
0x14004e08b  and     eax, 0FFFFF7FEh
0x14004e090  xor     ecx, ecx
0x14004e092  mov     [rbx+15BCh], eax
0x14004e098  xor     eax, eax
0x14004e09a  lock cmpxchg [rbx+15D8h], ecx
0x14004e0a2  jz      short loc_14004E0BC
0x14004e0a4  lea     rcx, [rbx+15E0h]; Event
0x14004e0ab  xor     r8d, r8d; Wait
0x14004e0ae  xor     edx, edx; Increment
0x14004e0b0  call    cs:__imp_KeSetEvent
0x14004e0b7  nop     dword ptr [rax+rax+00h]
0x14004e0bc  xor     edx, edx; Increment
0x14004e0be  xor     eax, eax
0x14004e0c0  lock cmpxchg [rbx+15F8h], edx
0x14004e0c8  jz      short loc_14004E0E0
0x14004e0ca  lea     rcx, [rbx+1600h]; Event
0x14004e0d1  xor     r8d, r8d; Wait
0x14004e0d4  call    cs:__imp_KeSetEvent
0x14004e0db  nop     dword ptr [rax+rax+00h]
0x14004e0e0  mov     qword ptr [rbx+1598h], 0
0x14004e0eb  mov     dl, r15b; NewIrql
0x14004e0ee  lock dec dword ptr [rbx+104h]
0x14004e0f5  mov     rcx, r12; SpinLock
0x14004e0f8  call    cs:__imp_KeReleaseSpinLock
0x14004e0ff  nop     dword ptr [rax+rax+00h]
0x14004e104  call    NtfsRepairEndThreadUpdate
0x14004e109  call    cs:__imp_KeLeaveCriticalRegion
0x14004e110  nop     dword ptr [rax+rax+00h]
0x14004e115  mov     rcx, [rbp+var_10]
0x14004e119  xor     rcx, rsp; StackCookie
0x14004e11c  call    __security_check_cookie
0x14004e121  lea     r11, [rsp+60h+var_s0]
0x14004e126  mov     rbx, [r11+38h]
0x14004e12a  mov     rsi, [r11+40h]
0x14004e12e  mov     rsp, r11
0x14004e131  pop     r15
0x14004e133  pop     r14
0x14004e135  pop     r12
0x14004e137  pop     rdi
0x14004e138  pop     rbp
0x14004e139  retn
0x14004e13b  mov     ecx, 3
0x14004e140  int     29h; Win8: RtlFailFast(ecx)
```
