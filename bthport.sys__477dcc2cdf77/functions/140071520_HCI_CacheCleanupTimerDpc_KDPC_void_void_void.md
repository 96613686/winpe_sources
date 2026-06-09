# HCI_CacheCleanupTimerDpc(_KDPC *,void *,void *,void *)

- ea: `0x140071520`
- end: `0x140071708`
- name: `?HCI_CacheCleanupTimerDpc@@YAXPEAU_KDPC@@PEAX11@Z`
- size: `488`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140005608`
- `0x140005b4c`
- `0x14000abf4`
- `0x1400272a4`
- `0x1400712a0`
- `0x140071520`
- `0x140077810`
- `0x140161a44`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140071603`
- `ntoskrnl!IoAllocateWorkItem` at `0x140071603`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400716ee`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400716ee`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140071644`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140071644`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400715d8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400715d8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400715a8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400715a8`

## pseudocode

```c
void __fastcall HCI_CacheCleanupTimerDpc(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  struct HCI_INTERFACE *p_DeferredRoutine; // rbx
  char v5; // di
  char v6; // dl
  __int16 DeviceType; // ax
  unsigned int CacheCleanupDelay; // ebp
  struct _DEVICE_OBJECT *m_controlDevice; // rcx
  unsigned __int64 v10; // rdx
  struct _IO_WORKITEM *WorkItem; // rsi
  int v12; // edx
  int v13; // r8d
  __int16 v14; // ax

  p_DeferredRoutine = (struct HCI_INTERFACE *)&Dpc[-33].DeferredRoutine;
  v5 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v6 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v6 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v6 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      DeviceType != 0,
      p_DeferredRoutine->IfrLog,
      5,
      2,
      210,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
      p_DeferredRoutine);
  KeAcquireSpinLockAtDpcLevel(&p_DeferredRoutine->HciLock);
  if ( p_DeferredRoutine->CacheCleanupTimerQueued )
  {
    p_DeferredRoutine->CacheCleanupTimerQueued = 0;
    HCI_StartCacheCleanupTimer(p_DeferredRoutine, 1);
  }
  CacheCleanupDelay = p_DeferredRoutine->CacheCleanupDelay;
  KeReleaseSpinLockFromDpcLevel(&p_DeferredRoutine->HciLock);
  if ( (unsigned int)Feature_59215879__private_IsEnabledDeviceUsageNoInline() )
    m_controlDevice = Driver::GetInstance()->m_controlDevice;
  else
    m_controlDevice = p_DeferredRoutine->BtDevice->FunctionalDeviceObject;
  WorkItem = IoAllocateWorkItem(m_controlDevice);
  if ( WorkItem )
  {
    RefObj_AddRefEx(
      &p_DeferredRoutine->RefObj,
      HCI_CacheCleanupWorkItem,
      5793,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciinterface.cpp");
    IoQueueWorkItemEx(WorkItem, HCI_CacheCleanupWorkItem, DelayedWorkQueue, p_DeferredRoutine);
  }
  else
  {
    HCI_CacheCleanup(p_DeferredRoutine, v10, (union _LARGE_INTEGER)(600000000 * CacheCleanupDelay));
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v5 = 0;
  v14 = WPP_GLOBAL_Control->DeviceType;
  if ( v5 || v14 )
  {
    LOBYTE(v12) = v5;
    LOBYTE(v13) = v14 != 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      v13,
      p_DeferredRoutine->IfrLog,
      5,
      2,
      211,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids);
  }
  RefObj_ReleaseEx(
    &p_DeferredRoutine->RefObj,
    HCI_StartCacheCleanupTimer,
    5810,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciinterface.cpp");
  IoReleaseRemoveLockEx(&p_DeferredRoutine->DevExt->RemoveLock, HCI_StartCacheCleanupTimer, 0x20u);
}

```

## disassembly

```asm
0x140071520  push    rbx
0x140071522  push    rbp
0x140071523  push    rsi
0x140071524  push    rdi
0x140071525  push    r12
0x140071527  push    r14
0x140071529  sub     rsp, 58h
0x14007152d  lea     rbx, [rcx-828h]
0x140071534  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007153b  xor     r14d, r14d
0x14007153e  mov     eax, [rcx+2Ch]
0x140071541  lea     edi, [r14+1]
0x140071545  test    al, 2
0x140071547  jz      short loc_140071552
0x140071549  cmp     byte ptr [rcx+29h], 5
0x14007154d  mov     dl, dil
0x140071550  jnb     short loc_140071555
0x140071552  mov     dl, r14b
0x140071555  movzx   eax, word ptr [rcx+48h]
0x140071559  lea     r12, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x140071560  test    ax, ax
0x140071563  setnz   r8b
0x140071567  test    dl, dl
0x140071569  jnz     short loc_140071570
0x14007156b  test    ax, ax
0x14007156e  jz      short loc_14007159E
0x140071570  mov     r9, [rbx+10B0h]
0x140071577  mov     rcx, [rcx+18h]
0x14007157b  mov     [rsp+88h+var_48], rbx
0x140071580  mov     [rsp+88h+var_50], r12
0x140071585  mov     [rsp+88h+var_58], 0D2h
0x14007158c  mov     [rsp+88h+var_60], 2
0x140071594  mov     [rsp+88h+var_68], 5
0x140071599  call    WPP_RECORDER_AND_TRACE_SF_q
0x14007159e  lea     rsi, [rbx+7B0h]
0x1400715a5  mov     rcx, rsi; SpinLock
0x1400715a8  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400715af  nop     dword ptr [rax+rax+00h]
0x1400715b4  cmp     [rbx+8A8h], r14b
0x1400715bb  jz      short loc_1400715CF
0x1400715bd  mov     dl, dil; unsigned __int8
0x1400715c0  mov     [rbx+8A8h], r14b
0x1400715c7  mov     rcx, rbx; struct HCI_INTERFACE *
0x1400715ca  call    ?HCI_StartCacheCleanupTimer@@YAXPEAUHCI_INTERFACE@@E@Z; HCI_StartCacheCleanupTimer(HCI_INTERFACE *,uchar)
0x1400715cf  mov     ebp, [rbx+824h]
0x1400715d5  mov     rcx, rsi; SpinLock
0x1400715d8  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400715df  nop     dword ptr [rax+rax+00h]
0x1400715e4  call    Feature_59215879__private_IsEnabledDeviceUsageNoInline
0x1400715e9  test    eax, eax
0x1400715eb  jz      short loc_1400715F8
0x1400715ed  call    ?GetInstance@Driver@@SAAEAV1@XZ; Driver::GetInstance(void)
0x1400715f2  mov     rcx, [rax+10h]
0x1400715f6  jmp     short loc_140071603
0x1400715f8  mov     rcx, [rbx+4B0h]
0x1400715ff  mov     rcx, [rcx+8]; DeviceObject
0x140071603  call    cs:__imp_IoAllocateWorkItem
0x14007160a  nop     dword ptr [rax+rax+00h]
0x14007160f  mov     rsi, rax
0x140071612  test    rax, rax
0x140071615  jz      short loc_140071652
0x140071617  lea     rcx, [rbx+8]
0x14007161b  mov     r8d, 16A1h
0x140071621  lea     r9, aOnecoreDrivers_38; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140071628  lea     rdx, ?HCI_CacheCleanupWorkItem@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; HCI_CacheCleanupWorkItem(void *,void *,_IO_WORKITEM *)
0x14007162f  call    RefObj_AddRefEx
0x140071634  mov     r9, rbx; Context
0x140071637  lea     rdx, ?HCI_CacheCleanupWorkItem@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x14007163e  mov     r8d, edi; QueueType
0x140071641  mov     rcx, rsi; IoWorkItem
0x140071644  call    cs:__imp_IoQueueWorkItemEx
0x14007164b  nop     dword ptr [rax+rax+00h]
0x140071650  jmp     short loc_140071661
0x140071652  imul    r8d, ebp, 23C34600h; union _LARGE_INTEGER
0x140071659  mov     rcx, rbx; struct HCI_INTERFACE *
0x14007165c  call    ?HCI_CacheCleanup@@YAXPEAUHCI_INTERFACE@@_KT_LARGE_INTEGER@@@Z; HCI_CacheCleanup(HCI_INTERFACE *,unsigned __int64,_LARGE_INTEGER)
0x140071661  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140071668  mov     eax, [rcx+2Ch]
0x14007166b  test    al, 2
0x14007166d  jz      short loc_140071675
0x14007166f  cmp     byte ptr [rcx+29h], 5
0x140071673  jnb     short loc_140071678
0x140071675  mov     dil, r14b
0x140071678  movzx   eax, word ptr [rcx+48h]
0x14007167c  test    ax, ax
0x14007167f  setnz   r8b
0x140071683  test    dil, dil
0x140071686  jnz     short loc_14007168D
0x140071688  test    ax, ax
0x14007168b  jz      short loc_1400716B9
0x14007168d  mov     r9, [rbx+10B0h]
0x140071694  mov     dl, dil
0x140071697  mov     rcx, [rcx+18h]
0x14007169b  mov     [rsp+88h+var_50], r12
0x1400716a0  mov     [rsp+88h+var_58], 0D3h
0x1400716a7  mov     [rsp+88h+var_60], 2
0x1400716af  mov     [rsp+88h+var_68], 5
0x1400716b4  call    WPP_RECORDER_AND_TRACE_SF_
0x1400716b9  lea     rcx, [rbx+8]
0x1400716bd  mov     r8d, 16B2h
0x1400716c3  lea     r9, aOnecoreDrivers_38; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400716ca  lea     rdx, ?HCI_StartCacheCleanupTimer@@YAXPEAUHCI_INTERFACE@@E@Z; HCI_StartCacheCleanupTimer(HCI_INTERFACE *,uchar)
0x1400716d1  call    RefObj_ReleaseEx
0x1400716d6  mov     rcx, [rbx+4A8h]
0x1400716dd  lea     rdx, ?HCI_StartCacheCleanupTimer@@YAXPEAUHCI_INTERFACE@@E@Z; Tag
0x1400716e4  add     rcx, 38h ; '8'; RemoveLock
0x1400716e8  mov     r8d, 20h ; ' '; RemlockSize
0x1400716ee  call    cs:__imp_IoReleaseRemoveLockEx
0x1400716f5  nop     dword ptr [rax+rax+00h]
0x1400716fa  add     rsp, 58h
0x1400716fe  pop     r14
0x140071700  pop     r12
0x140071702  pop     rdi
0x140071703  pop     rsi
0x140071704  pop     rbp
0x140071705  pop     rbx
0x140071706  retn
```
