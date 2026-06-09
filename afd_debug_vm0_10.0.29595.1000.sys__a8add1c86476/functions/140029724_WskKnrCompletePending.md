# WskKnrCompletePending

- ea: `0x140029724`
- end: `0x140029b10`
- name: `WskKnrCompletePending`
- size: `1004`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140029284`
- `0x1400296e0`

## callees

- `0x140028de0`
- `0x140029724`
- `0x140029b18`
- `0x140029d60`
- `0x140068434`
- `0x140068d08`
- `0x14009304c`
- `0x14009352c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400298dd`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029909`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029986`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400298dd`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029909`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029986`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002978f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002978f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002977d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002977d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400297c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400297c3`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400297b7`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400297b7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140029888`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140029888`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140029875`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140029875`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002983e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002983e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400297d8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400297d8`

## pseudocode

```c
__int64 __fastcall WskKnrCompletePending(PERESOURCE Resource, unsigned __int8 a2)
{
  struct _LIST_ENTRY *Blink; // r14
  POWNER_ENTRY OwnerTable; // rsi
  int v4; // edi
  struct _OWNER_ENTRY::$818A6BB8E639852A52D20A2B257A1D60::$E71B718CD8428E7C8AA4A0868051E710 TableSize; // eax
  struct _OWNER_ENTRY::$818A6BB8E639852A52D20A2B257A1D60::$E71B718CD8428E7C8AA4A0868051E710 v8; // eax
  __int64 v9; // rcx
  POWNER_ENTRY *OwnerThread; // rdx
  __int64 result; // rax
  __int64 v12; // rsi
  void *v13; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-58h] BYREF
  KIRQL Irql; // [rsp+98h] [rbp+10h] BYREF

  Blink = Resource[1].SystemResourcesList.Blink;
  OwnerTable = Resource[1].OwnerTable;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = 0;
  if ( (BYTE3(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_qD(1048, 19, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids, Resource, a2);
  TableSize = (struct _OWNER_ENTRY::$818A6BB8E639852A52D20A2B257A1D60::$E71B718CD8428E7C8AA4A0868051E710)Resource[1].OwnerEntry.TableSize;
  if ( (TableSize == -1073610729 || TableSize == -1073741595)
    && !BYTE2(Resource[1].ActiveEntries)
    && (*(_BYTE *)(&Resource[1].OwnerEntry.8 + 1) & 0x10) == 0 )
  {
    v4 = 1;
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(Resource, 1u);
  if ( a2 )
    WskKnrExtractRpcResults(Resource);
  BYTE1(Resource[1].ActiveEntries) = 1;
  ExReleaseResourceForThreadLite(Resource, (ERESOURCE_THREAD)KeGetCurrentThread());
  KeLeaveCriticalRegion();
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&Blink[1].Blink, &LockHandle);
  v8 = (struct _OWNER_ENTRY::$818A6BB8E639852A52D20A2B257A1D60::$E71B718CD8428E7C8AA4A0868051E710)Resource[1].OwnerEntry.TableSize;
  if ( (v8 == -1073610729 || v8 == -1073741595)
    && !BYTE2(Resource[1].ActiveEntries)
    && (*(_BYTE *)(&Resource[1].OwnerEntry.8 + 1) & 0x10) == 0 )
  {
    v4 = 1;
  }
  if ( (*(_DWORD *)(&Resource[1].OwnerEntry.8 + 1) & 8) != 0 )
  {
    v9 = *(_QWORD *)&OwnerTable[10].0;
    if ( *(POWNER_ENTRY *)(v9 + 8) != (POWNER_ENTRY)&OwnerTable[10].0
      || (OwnerThread = (POWNER_ENTRY *)OwnerTable[11].OwnerThread, *OwnerThread != (POWNER_ENTRY)&OwnerTable[10].0) )
    {
      __fastfail(3u);
    }
    *OwnerThread = (POWNER_ENTRY)v9;
    *(_QWORD *)(v9 + 8) = OwnerThread;
    *((_DWORD *)&Resource[1].OwnerEntry.8 + 1) &= ~8u;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v4 )
  {
    _InterlockedAdd((volatile signed __int32 *)&Resource[1], 1u);
    if ( (BYTE11(xmmword_1400875E0) & 1) != 0 )
      WPP_SF_qdd(
        1304,
        10,
        WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids,
        Resource,
        Resource[1].SystemResourcesList.Flink,
        1,
        LockHandle.LockQueue.Next,
        LockHandle.LockQueue.Lock,
        *(_QWORD *)&LockHandle.OldIrql);
    v13 = *(void **)&Resource[1].NumberOfSharedWaiters;
    if ( v13 )
    {
      WskKnrReleaseRpcBinding(v13, (PKSPIN_LOCK)(Resource[1].CreatorBackTraceIndex + 24));
      *(_QWORD *)&Resource[1].NumberOfSharedWaiters = 0;
    }
    if ( (BYTE11(xmmword_1400875E0) & 1) != 0 )
      WPP_SF_qdd(
        1304,
        11,
        WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids,
        Resource,
        LODWORD(Resource[1].SystemResourcesList.Flink) - 1,
        2,
        LockHandle.LockQueue.Next,
        LockHandle.LockQueue.Lock,
        *(_QWORD *)&LockHandle.OldIrql);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Resource[1], 0xFFFFFFFF) == 1 )
    {
      if ( KeGetCurrentIrql() )
      {
        Resource[1].OwnerEntry.OwnerThread = (ERESOURCE_THREAD)Resource;
        AfdQueueWorkItem(WskKnrDeferredCompleteRequest, &Resource[1].ActiveCount);
      }
      else
      {
        WskKnrCompleteRequest(Resource);
      }
    }
    BYTE2(Resource[1].ActiveEntries) = 1;
    return WskKnrRpcProcessInvoke(Resource);
  }
  else
  {
    Irql = 0;
    if ( _InterlockedExchange64((volatile __int64 *)&OwnerTable[6].0, 0) )
    {
      v12 = *(_QWORD *)(*(_QWORD *)&OwnerTable[11].0 + 24LL);
      if ( (BYTE11(xmmword_1400875E0) & 1) != 0 )
        WPP_SF_qdd(
          1304,
          11,
          WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids,
          v12,
          *(_DWORD *)(v12 + 104) - 1,
          3,
          LockHandle.LockQueue.Next,
          LockHandle.LockQueue.Lock,
          *(_QWORD *)&LockHandle.OldIrql);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 104), 0xFFFFFFFF) == 1 )
      {
        if ( KeGetCurrentIrql() )
        {
          *(_QWORD *)(v12 + 152) = v12;
          AfdQueueWorkItem(WskKnrDeferredCompleteRequest, v12 + 128);
        }
        else
        {
          WskKnrCompleteRequest((PERESOURCE)v12);
        }
      }
    }
    else
    {
      IoAcquireCancelSpinLock(&Irql);
      IoReleaseCancelSpinLock(Irql);
    }
    if ( (BYTE11(xmmword_1400875E0) & 1) != 0 )
      WPP_SF_qdd(
        1304,
        11,
        WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids,
        Resource,
        LODWORD(Resource[1].SystemResourcesList.Flink) - 1,
        2,
        LockHandle.LockQueue.Next,
        LockHandle.LockQueue.Lock,
        *(_QWORD *)&LockHandle.OldIrql);
    result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)&Resource[1]);
    if ( !(_DWORD)result )
    {
      if ( KeGetCurrentIrql() )
      {
        Resource[1].OwnerEntry.OwnerThread = (ERESOURCE_THREAD)Resource;
        return AfdQueueWorkItem(WskKnrDeferredCompleteRequest, &Resource[1].ActiveCount);
      }
      else
      {
        return WskKnrCompleteRequest(Resource);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140029724  push    rbx
0x140029726  push    rbp
0x140029727  push    rsi
0x140029728  push    rdi
0x140029729  push    r14
0x14002972b  push    r15
0x14002972d  sub     rsp, 58h
0x140029731  mov     r14, [rcx+70h]
0x140029735  xor     eax, eax
0x140029737  mov     rsi, [rcx+78h]
0x14002973b  xorps   xmm0, xmm0
0x14002973e  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x140029743  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x140029748  xor     edi, edi
0x14002974a  movzx   ebp, dl
0x14002974d  mov     rbx, rcx
0x140029750  lea     r15d, [rax+1]
0x140029754  test    byte ptr cs:xmmword_1400875E0+3, r15b
0x14002975b  jnz     loc_140029A17
0x140029761  mov     eax, [rbx+0A0h]
0x140029767  cmp     eax, 0C0020017h
0x14002976c  jz      loc_140029A39
0x140029772  cmp     eax, 0C00000E5h
0x140029777  jz      loc_140029A39
0x14002977d  call    cs:__imp_KeEnterCriticalRegion
0x140029784  nop     dword ptr [rax+rax+00h]
0x140029789  mov     dl, r15b; Wait
0x14002978c  mov     rcx, rbx; Resource
0x14002978f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140029796  nop     dword ptr [rax+rax+00h]
0x14002979b  test    bpl, bpl
0x14002979e  jnz     loc_140029A57
0x1400297a4  mov     [rbx+0A9h], r15b
0x1400297ab  mov     rcx, rbx; Resource
0x1400297ae  mov     rdx, gs:188h; ResourceThreadId
0x1400297b7  call    cs:__imp_ExReleaseResourceForThreadLite
0x1400297be  nop     dword ptr [rax+rax+00h]
0x1400297c3  call    cs:__imp_KeLeaveCriticalRegion
0x1400297ca  nop     dword ptr [rax+rax+00h]
0x1400297cf  lea     rcx, [r14+18h]; SpinLock
0x1400297d3  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x1400297d8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400297df  nop     dword ptr [rax+rax+00h]
0x1400297e4  mov     eax, [rbx+0A0h]
0x1400297ea  cmp     eax, 0C0020017h
0x1400297ef  jz      loc_140029A64
0x1400297f5  cmp     eax, 0C00000E5h
0x1400297fa  jz      loc_140029A64
0x140029800  mov     eax, [rbx+0A4h]
0x140029806  test    al, 8
0x140029808  jz      short loc_140029839
0x14002980a  lea     rax, [rsi+0A8h]
0x140029811  mov     rcx, [rax]
0x140029814  cmp     [rcx+8], rax
0x140029818  jnz     loc_140029A82
0x14002981e  mov     rdx, [rax+8]
0x140029822  cmp     [rdx], rax
0x140029825  jnz     loc_140029A82
0x14002982b  mov     [rdx], rcx
0x14002982e  mov     [rcx+8], rdx
0x140029832  and     dword ptr [rbx+0A4h], 0FFFFFFF7h
0x140029839  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14002983e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140029845  nop     dword ptr [rax+rax+00h]
0x14002984a  test    edi, edi
0x14002984c  jnz     loc_1400299B2
0x140029852  xor     eax, eax
0x140029854  mov     [rsp+88h+Irql], dil
0x14002985c  xchg    rax, [rsi+68h]
0x140029860  or      edi, 0FFFFFFFFh
0x140029863  mov     ebp, 518h
0x140029868  test    rax, rax
0x14002986b  jnz     short loc_1400298BA
0x14002986d  lea     rcx, [rsp+88h+Irql]; Irql
0x140029875  call    cs:__imp_IoAcquireCancelSpinLock
0x14002987c  nop     dword ptr [rax+rax+00h]
0x140029881  mov     cl, [rsp+88h+Irql]; Irql
0x140029888  call    cs:__imp_IoReleaseCancelSpinLock
0x14002988f  nop     dword ptr [rax+rax+00h]
0x140029894  test    byte ptr cs:xmmword_1400875E0+0Bh, r15b
0x14002989b  jnz     loc_140029AE3
0x1400298a1  mov     eax, edi
0x1400298a3  lock xadd [rbx+68h], eax
0x1400298a8  add     eax, edi
0x1400298aa  jz      short loc_140029909
0x1400298ac  add     rsp, 58h
0x1400298b0  pop     r15
0x1400298b2  pop     r14
0x1400298b4  pop     rdi
0x1400298b5  pop     rsi
0x1400298b6  pop     rbp
0x1400298b7  pop     rbx
0x1400298b8  retn
0x1400298ba  mov     rax, [rsi+0B8h]
0x1400298c1  mov     rsi, [rax+18h]
0x1400298c5  test    byte ptr cs:xmmword_1400875E0+0Bh, r15b
0x1400298cc  jnz     loc_140029AB6
0x1400298d2  mov     eax, edi
0x1400298d4  lock xadd [rsi+68h], eax
0x1400298d9  add     eax, edi
0x1400298db  jnz     short loc_140029894
0x1400298dd  call    cs:__imp_KeGetCurrentIrql
0x1400298e4  nop     dword ptr [rax+rax+00h]
0x1400298e9  test    al, al
0x1400298eb  jz      short loc_140029942
0x1400298ed  lea     rdx, [rsi+80h]
0x1400298f4  mov     [rsi+98h], rsi
0x1400298fb  lea     rcx, WskKnrDeferredCompleteRequest
0x140029902  call    AfdQueueWorkItem
0x140029907  jmp     short loc_140029894
0x140029909  call    cs:__imp_KeGetCurrentIrql
0x140029910  nop     dword ptr [rax+rax+00h]
0x140029915  test    al, al
0x140029917  jnz     short loc_140029923
0x140029919  mov     rcx, rbx; Resource
0x14002991c  call    WskKnrCompleteRequest
0x140029921  jmp     short loc_1400298AC
0x140029923  lea     rdx, [rbx+80h]
0x14002992a  mov     [rbx+98h], rbx
0x140029931  lea     rcx, WskKnrDeferredCompleteRequest
0x140029938  call    AfdQueueWorkItem
0x14002993d  jmp     loc_1400298AC
0x140029942  mov     rcx, rsi; Resource
0x140029945  call    WskKnrCompleteRequest
0x14002994a  jmp     loc_140029894
0x14002994f  mov     rcx, rbx; Resource
0x140029952  call    WskKnrCompleteRequest
0x140029957  mov     rcx, rbx; Resource
0x14002995a  mov     [rbx+0AAh], r15b
0x140029961  call    WskKnrRpcProcessInvoke
0x140029966  jmp     loc_1400298AC
0x14002996b  test    byte ptr cs:xmmword_1400875E0+0Bh, r15b
0x140029972  jnz     loc_140029A89
0x140029978  or      edi, 0FFFFFFFFh
0x14002997b  mov     eax, edi
0x14002997d  lock xadd [rbx+68h], eax
0x140029982  add     eax, edi
0x140029984  jnz     short loc_140029957
0x140029986  call    cs:__imp_KeGetCurrentIrql
0x14002998d  nop     dword ptr [rax+rax+00h]
0x140029992  test    al, al
0x140029994  jz      short loc_14002994F
0x140029996  lea     rdx, [rbx+80h]
0x14002999d  mov     [rbx+98h], rbx
0x1400299a4  lea     rcx, WskKnrDeferredCompleteRequest
0x1400299ab  call    AfdQueueWorkItem
0x1400299b0  jmp     short loc_140029957
0x1400299b2  lock add [rbx+68h], r15d
0x1400299b7  test    byte ptr cs:xmmword_1400875E0+0Bh, r15b
0x1400299be  mov     ebp, 518h
0x1400299c3  jz      short loc_1400299E7
0x1400299c5  mov     eax, [rbx+68h]
0x1400299c8  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x1400299cf  mov     edx, 0Ah
0x1400299d4  mov     [rsp+88h+var_60], r15d
0x1400299d9  mov     ecx, ebp
0x1400299db  mov     [rsp+88h+var_68], eax
0x1400299df  mov     r9, rbx
0x1400299e2  call    WPP_SF_qdd
0x1400299e7  mov     rcx, [rbx+0B0h]; P
0x1400299ee  test    rcx, rcx
0x1400299f1  jz      loc_14002996B
0x1400299f7  mov     rdx, [rbx+0C0h]
0x1400299fe  add     rdx, 18h; SpinLock
0x140029a02  call    WskKnrReleaseRpcBinding
0x140029a07  mov     qword ptr [rbx+0B0h], 0
0x140029a12  jmp     loc_14002996B
0x140029a17  mov     edx, 13h
0x140029a1c  mov     [rsp+88h+var_68], ebp
0x140029a20  mov     ecx, 418h
0x140029a25  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x140029a2c  mov     r9, rbx
0x140029a2f  call    WPP_SF_qD
0x140029a34  jmp     loc_140029761
0x140029a39  mov     al, [rbx+0AAh]
0x140029a3f  test    al, al
0x140029a41  jnz     loc_14002977D
0x140029a47  test    byte ptr [rbx+0A4h], 10h
0x140029a4e  cmovz   edi, r15d
0x140029a52  jmp     loc_14002977D
0x140029a57  mov     rcx, rbx
0x140029a5a  call    WskKnrExtractRpcResults
0x140029a5f  jmp     loc_1400297A4
0x140029a64  mov     al, [rbx+0AAh]
0x140029a6a  test    al, al
0x140029a6c  jnz     loc_140029800
0x140029a72  test    byte ptr [rbx+0A4h], 10h
0x140029a79  cmovz   edi, r15d
0x140029a7d  jmp     loc_140029800
0x140029a82  mov     ecx, 3
0x140029a87  int     29h; Win8: RtlFailFast(ecx)
0x140029a89  mov     eax, [rbx+68h]
0x140029a8c  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x140029a93  sub     eax, r15d
0x140029a96  mov     [rsp+88h+var_60], 2
0x140029a9e  mov     edx, 0Bh
0x140029aa3  mov     [rsp+88h+var_68], eax
0x140029aa7  mov     ecx, ebp
0x140029aa9  mov     r9, rbx
0x140029aac  call    WPP_SF_qdd
0x140029ab1  jmp     loc_140029978
0x140029ab6  mov     eax, [rsi+68h]
0x140029ab9  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x140029ac0  sub     eax, r15d
0x140029ac3  mov     [rsp+88h+var_60], 3
0x140029acb  mov     edx, 0Bh
0x140029ad0  mov     [rsp+88h+var_68], eax
0x140029ad4  mov     ecx, ebp
0x140029ad6  mov     r9, rsi
0x140029ad9  call    WPP_SF_qdd
0x140029ade  jmp     loc_1400298D2
0x140029ae3  mov     eax, [rbx+68h]
0x140029ae6  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x140029aed  sub     eax, r15d
0x140029af0  mov     [rsp+88h+var_60], 2
0x140029af8  mov     edx, 0Bh
0x140029afd  mov     [rsp+88h+var_68], eax
0x140029b01  mov     ecx, ebp
0x140029b03  mov     r9, rbx
0x140029b06  call    WPP_SF_qdd
0x140029b0b  jmp     loc_1400298A1
```
