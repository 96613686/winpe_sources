# AfdReceiveDatagramEventCommonHandler

- ea: `0x14000d7f0`
- end: `0x14000dc88`
- name: `AfdReceiveDatagramEventCommonHandler`
- size: `1176`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, int, void *, int, int, ULONG SourceBytesToCopy, ULONG *, PVOID SourceBuffer, char, int, __int64, __int64 *, PIRP Irp, struct _KLOCK_QUEUE_HANDLE *LockHandle)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000d5f0`
- `0x140053600`

## callees

- `0x140008fb0`
- `0x14000d7f0`
- `0x14000f450`
- `0x1400137a0`
- `0x140013dc0`
- `0x14001b800`
- `0x14002c160`
- `0x14002fb34`
- `0x140031f88`
- `0x140036cc4`
- `0x14003e410`
- `0x140050c84`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140075a4c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140075a4c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140075a88`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140075a88`
- `ntoskrnl!IofCompleteRequest` at `0x14000d95b`
- `ntoskrnl!IofCompleteRequest` at `0x140075b0b`
- `ntoskrnl!IofCompleteRequest` at `0x14000d95b`
- `ntoskrnl!IofCompleteRequest` at `0x140075b0b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000d899`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000dae1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000db86`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075920`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075a75`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075b24`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000d899`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000dae1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000db86`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075920`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075a75`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075b24`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000dac2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000db66`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000dac2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000db66`

## pseudocode

```c
__int64 __fastcall AfdReceiveDatagramEventCommonHandler(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        void *a5,
        int a6,
        int a7,
        ULONG SourceBytesToCopy,
        ULONG *a9,
        PVOID SourceBuffer,
        char a11,
        int a12,
        __int64 a13,
        __int64 *a14,
        PIRP Irp,
        struct _KLOCK_QUEUE_HANDLE *LockHandle)
{
  _QWORD **v20; // rdx
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  __int64 v23; // rsi
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v28; // rcx
  _QWORD *v29; // r13
  __int64 v30; // rcx
  _QWORD **v31; // rcx
  _QWORD *v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rbx
  __int64 v41; // r14
  __int64 v42; // r12
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rcx
  int v50[2]; // [rsp+20h] [rbp-A8h]
  int v51[2]; // [rsp+20h] [rbp-A8h]
  void *Src; // [rsp+28h] [rbp-A0h]
  size_t v53; // [rsp+40h] [rbp-88h]
  struct _KLOCK_QUEUE_HANDLE v54; // [rsp+70h] [rbp-58h] BYREF
  int v56; // [rsp+E8h] [rbp+20h]
  IRP *Irpa; // [rsp+140h] [rbp+78h]

  v56 = a4;
  if ( !LOBYTE(Irp->Type) )
  {
    LOBYTE(Irp->Type) = 1;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), LockHandle);
    a4 = v56;
  }
  if ( *(_BYTE *)(a1 + 2) == 4 && (*(_DWORD *)(a1 + 8) & 0x100) == 0 && (*(_DWORD *)(a1 + 192) & 0x10) == 0 )
  {
    if ( !AfdAreTransportAddressesEqual(*(_QWORD *)(a1 + 184), *(_DWORD *)(a1 + 176), (__int64)a3, a2, 1) )
    {
      *(_DWORD *)(a1 + 192) |= 0x1000u;
      LOBYTE(Irp->Type) = 0;
      KeReleaseInStackQueuedSpinLock(LockHandle);
      v50[0] = SourceBytesToCopy;
      AFDETW_TRACEDATAGRAM_DROP(v39, 10000, (_WORD *)a1, SourceBuffer, *(_QWORD *)v50, a3, 1);
      *a9 = SourceBytesToCopy;
      return 0;
    }
    a4 = v56;
  }
  v20 = (_QWORD **)(a1 + 96);
  while ( 1 )
  {
    v21 = *v20;
    if ( *v20 == v20 )
      break;
    if ( (_QWORD **)v21[1] != v20 || (v22 = (_QWORD *)*v21, *(_QWORD **)(*v21 + 8LL) != v21) )
LABEL_31:
      __fastfail(3u);
    *v20 = v22;
    v23 = (__int64)(v21 - 21);
    v22[1] = v20;
    if ( _InterlockedExchange64(v21 - 8, 0) )
    {
      LOBYTE(Irp->Type) = 0;
      KeReleaseInStackQueuedSpinLock(LockHandle);
      if ( a7 == SourceBytesToCopy || !*(_QWORD *)(v23 + 8) )
      {
        v50[0] = SourceBytesToCopy;
        *a9 = SourceBytesToCopy;
        AFDETW_TRACEDATA_INDICATION(v24, 9001, a1, SourceBuffer, *(_QWORD *)v50, a3);
        AFDETW_TRACEBUFFER(v25, 0, (__int64)SourceBuffer, a13);
        AFDETW_TRACEBUFFER(v26, v23, (__int64)SourceBuffer, 0);
        AfdSetupReceiveDatagramIrp((PIRP)v23, SourceBuffer, SourceBytesToCopy, v56, a3, a2, a6, a11, a12);
        IofCompleteRequest((PIRP)v23, AfdPriorityBoost);
        return 0;
      }
      v40 = *(_QWORD *)(v23 + 184);
      v41 = *(_QWORD *)(a1 + 24);
      v42 = *(_QWORD *)(a1 + 40);
      v50[0] = SourceBytesToCopy;
      AFDETW_TRACEDATA_INDICATION(v24, 8003, a1, 0, *(_QWORD *)v50, a3);
      AFDETW_TRACEBUFFER(v43, 0, *(_QWORD *)(v23 + 8), a13);
      AFDETW_TRACEBUFFER(v44, v23, *(_QWORD *)(v23 + 8), 0);
      *(_DWORD *)(v40 + 8) = AfdSetupReceiveDatagramIrp((PIRP)v23, 0, SourceBytesToCopy, v56, a3, a2, a6, 0, 0);
      if ( (*(_DWORD *)(a1 + 8) & 0x400000) != 0 )
      {
        if ( (unsigned __int8)AfdTdi_IsTA6V4Mapped(a3, a2) )
        {
          v45 = *(_QWORD *)(a1 + 280);
          v41 = *(_QWORD *)(v45 + 8);
          v42 = *(_QWORD *)(v45 + 16);
        }
      }
      v37 = *(_QWORD *)(v23 + 184);
      *(_QWORD *)(v37 - 16) = AfdRestartReceiveDatagramWithUserIrp;
      *(_QWORD *)(v37 - 8) = a1;
      *(_BYTE *)(v37 - 69) = -32;
      v38 = *(_QWORD *)(v23 + 184);
      *(_WORD *)(v38 - 72) = 2575;
      *(_QWORD *)(v38 - 32) = v42;
      *(_QWORD *)(v38 - 24) = v41;
      *(_DWORD *)(v38 - 64) = SourceBytesToCopy;
      *(_QWORD *)(v38 - 56) = 0;
      *(_QWORD *)(v38 - 48) = 0;
      *(_DWORD *)(v38 - 40) = 0;
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 248));
      --*(_BYTE *)(v23 + 67);
      *(_QWORD *)(v23 + 184) -= 72LL;
      *a14 = v23;
      *a9 = 0;
      if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 64)) <= 1 )
        goto LABEL_35;
      return 3221225494LL;
    }
    *v21 = 0;
  }
  LODWORD(v53) = SourceBytesToCopy;
  v29 = (_QWORD *)AfdBufferReceiveDatagram(a1, a2, a3, a4, a5, (__int64)Src, a6, a7, v53, a9, SourceBuffer, a11, a12);
  if ( !v29 )
  {
    LOBYTE(Irp->Type) = 0;
    KeReleaseInStackQueuedSpinLock(LockHandle);
    return 0;
  }
  v51[0] = SourceBytesToCopy;
  AFDETW_TRACEDATA_INDICATION(v28, 8004, a1, SourceBuffer, *(_QWORD *)v51, a3);
  AFDETW_TRACEBUFFER(v30, 0, v29[7], a13);
  if ( a7 != SourceBytesToCopy )
  {
    LOBYTE(Irp->Type) = 0;
    KeReleaseInStackQueuedSpinLock(LockHandle);
    v29[6] = a1;
    if ( (*(_DWORD *)(a1 + 8) & 0x400000) != 0 && (unsigned __int8)AfdTdi_IsTA6V4Mapped(a3, a2) )
    {
      v46 = *(_QWORD *)(v29[13] + 184LL);
      *(_QWORD *)(v46 - 16) = &AfdRestartBufferReceiveDatagram;
      *(_QWORD *)(v46 - 8) = v29;
      *(_BYTE *)(v46 - 69) = -32;
      v47 = *(_QWORD *)(v29[13] + 184LL);
      *(_WORD *)(v47 - 72) = 2575;
      *(_QWORD *)(v47 - 32) = *(_QWORD *)(*(_QWORD *)(a1 + 280) + 16LL);
      *(_QWORD *)(v47 - 24) = *(_QWORD *)(*(_QWORD *)(a1 + 280) + 8LL);
      *(_DWORD *)(v47 - 64) = SourceBytesToCopy;
      *(_QWORD *)(v47 - 56) = 0;
      *(_QWORD *)(v47 - 48) = 0;
      *(_DWORD *)(v47 - 40) = 0;
    }
    else
    {
      v48 = *(_QWORD *)(v29[13] + 184LL);
      *(_QWORD *)(v48 - 16) = &AfdRestartBufferReceiveDatagram;
      *(_QWORD *)(v48 - 8) = v29;
      *(_BYTE *)(v48 - 69) = -32;
      v49 = *(_QWORD *)(v29[13] + 184LL);
      *(_WORD *)(v49 - 72) = 2575;
      *(_QWORD *)(v49 - 32) = *(_QWORD *)(a1 + 40);
      *(_QWORD *)(v49 - 24) = *(_QWORD *)(a1 + 24);
      *(_DWORD *)(v49 - 64) = SourceBytesToCopy;
      *(_QWORD *)(v49 - 56) = 0;
      *(_QWORD *)(v49 - 48) = 0;
      *(_DWORD *)(v49 - 40) = 0;
    }
    v36 = v29[13];
    --*(_BYTE *)(v36 + 67);
    *(_QWORD *)(v36 + 184) -= 72LL;
    *a14 = v29[13];
    *a9 = 0;
    if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 64)) <= 1 )
LABEL_35:
      __fastfail(0xEu);
    return 3221225494LL;
  }
  v31 = (_QWORD **)(a1 + 112);
  while ( 1 )
  {
    v32 = *v31;
    if ( *v31 == v31 )
      break;
    if ( (_QWORD **)v32[1] != v31 )
      goto LABEL_31;
    v35 = (_QWORD *)*v32;
    if ( *(_QWORD **)(*v32 + 8LL) != v32 )
      goto LABEL_31;
    *v31 = v35;
    v35[1] = v31;
    Irpa = (IRP *)(v32 - 21);
    if ( _InterlockedExchange64(v32 - 8, 0) )
      goto LABEL_17;
    *v32 = 0;
  }
  Irpa = 0;
LABEL_17:
  v33 = *(_QWORD *)(a1 + 384);
  if ( v33 )
    *(_WORD *)(v33 + 100) |= 1u;
  AfdIndicateEventSelectEvent(a1, 1, 0);
  if ( AfdIndicatePollEvent(a1, 1u, 0, LockHandle) )
  {
    memset(&v54, 0, sizeof(v54));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &v54);
    if ( *(_QWORD *)(a1 + 384) && ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 392)) )
    {
      AfdNotifyPostEvents(a1, &v54, 0);
      KeReleaseInStackQueuedSpinLock(&v54);
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 392));
    }
    else
    {
      KeReleaseInStackQueuedSpinLock(&v54);
    }
  }
  else
  {
    AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)a1, LockHandle, 0);
  }
  LOBYTE(Irp->Type) = 0;
  if ( Irpa )
  {
    AFDETW_TRACEBUFFER(v34, (__int64)Irpa, v29[7], 0);
    AfdSetupReceiveDatagramIrp(Irpa, SourceBuffer, SourceBytesToCopy, v56, a3, a2, a6, a11, a12);
    IofCompleteRequest(Irpa, AfdPriorityBoost);
  }
  *a9 = SourceBytesToCopy;
  return 0;
}

```

## disassembly

```asm
0x14000d7f0  mov     [rsp+arg_18], r9d
0x14000d7f5  mov     [rsp+arg_8], edx
0x14000d7f9  push    rdi
0x14000d7fa  push    r12
0x14000d7fc  push    r13
0x14000d7fe  push    r14
0x14000d800  push    r15
0x14000d802  sub     rsp, 0A0h
0x14000d809  mov     r14, [rsp+0C8h+Irp]
0x14000d811  mov     r15, r8
0x14000d814  mov     r12, [rsp+0C8h+LockHandle]
0x14000d81c  mov     r13d, edx
0x14000d81f  mov     rdi, rcx
0x14000d822  cmp     byte ptr [r14], 0
0x14000d826  jz      loc_14000DB5B
0x14000d82c  cmp     byte ptr [rdi+2], 4
0x14000d830  mov     [rsp+0C8h+arg_0], rbx
0x14000d838  mov     [rsp+0C8h+var_30], rbp
0x14000d840  jz      loc_1400758D4
0x14000d846  lea     rdx, [rdi+60h]
0x14000d84a  mov     [rsp+0C8h+var_38], rsi
0x14000d852  mov     rax, [rdx]
0x14000d855  cmp     rax, rdx
0x14000d858  jz      loc_14000D99F
0x14000d85e  cmp     [rax+8], rdx
0x14000d862  jnz     loc_14000DB99
0x14000d868  mov     rcx, [rax]
0x14000d86b  cmp     [rcx+8], rax
0x14000d86f  jnz     loc_14000DB99
0x14000d875  mov     [rdx], rcx
0x14000d878  lea     rsi, [rax-0A8h]
0x14000d87f  mov     [rcx+8], rdx
0x14000d883  xor     ecx, ecx
0x14000d885  xchg    rcx, [rsi+68h]
0x14000d889  test    rcx, rcx
0x14000d88c  jz      loc_14000D993
0x14000d892  mov     rcx, r12; LockHandle
0x14000d895  mov     byte ptr [r14], 0
0x14000d899  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000d8a0  nop     dword ptr [rax+rax+00h]
0x14000d8a5  mov     ebp, [rsp+0C8h+SourceBytesToCopy]
0x14000d8ac  cmp     [rsp+0C8h+arg_30], ebp
0x14000d8b3  jnz     loc_140075977
0x14000d8b9  mov     rax, [rsp+0C8h+arg_40]
0x14000d8c1  mov     r8, rdi
0x14000d8c4  mov     rbx, [rsp+0C8h+SourceBuffer]
0x14000d8cc  mov     edx, 2329h
0x14000d8d1  mov     [rsp+0C8h+Src], r15
0x14000d8d6  mov     r9, rbx
0x14000d8d9  mov     [rsp+0C8h+var_A8], ebp
0x14000d8dd  mov     [rax], ebp
0x14000d8df  call    AFDETW_TRACEDATA_INDICATION
0x14000d8e4  mov     r9, [rsp+0C8h+arg_60]
0x14000d8ec  mov     r8, rbx
0x14000d8ef  xor     edx, edx
0x14000d8f1  call    AFDETW_TRACEBUFFER
0x14000d8f6  xor     r9d, r9d
0x14000d8f9  mov     r8, rbx
0x14000d8fc  mov     rdx, rsi
0x14000d8ff  call    AFDETW_TRACEBUFFER
0x14000d904  mov     eax, [rsp+0C8h+arg_58]
0x14000d90b  mov     r8d, ebp; SourceBytesToCopy
0x14000d90e  mov     r9, [rsp+0C8h+arg_20]
0x14000d916  mov     rdx, rbx; SourceBuffer
0x14000d919  mov     [rsp+0C8h+var_80], eax; int
0x14000d91d  mov     rcx, rsi; Irp
0x14000d920  movzx   eax, [rsp+0C8h+arg_50]
0x14000d928  mov     [rsp+0C8h+var_88], al; char
0x14000d92c  mov     eax, [rsp+0C8h+arg_28]
0x14000d933  mov     [rsp+0C8h+var_90], eax; int
0x14000d937  mov     eax, [rsp+0C8h+arg_18]
0x14000d93e  mov     [rsp+0C8h+var_98], r13d; int
0x14000d943  mov     [rsp+0C8h+Src], r15; Src
0x14000d948  mov     [rsp+0C8h+var_A8], eax; int
0x14000d94c  call    AfdSetupReceiveDatagramIrp
0x14000d951  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x14000d958  mov     rcx, rsi; Irp
0x14000d95b  call    cs:__imp_IofCompleteRequest
0x14000d962  nop     dword ptr [rax+rax+00h]
0x14000d967  xor     eax, eax
0x14000d969  mov     rsi, [rsp+0C8h+var_38]
0x14000d971  mov     rbp, [rsp+0C8h+var_30]
0x14000d979  mov     rbx, [rsp+0C8h+arg_0]
0x14000d981  add     rsp, 0A0h
0x14000d988  pop     r15
0x14000d98a  pop     r14
0x14000d98c  pop     r13
0x14000d98e  pop     r12
0x14000d990  pop     rdi
0x14000d991  retn
0x14000d993  mov     qword ptr [rax], 0
0x14000d99a  jmp     loc_14000D852
0x14000d99f  mov     eax, [rsp+0C8h+arg_58]
0x14000d9a6  mov     r8, r15
0x14000d9a9  mov     rsi, [rsp+0C8h+arg_40]
0x14000d9b1  mov     edx, r13d
0x14000d9b4  mov     ebx, [rsp+0C8h+SourceBytesToCopy]
0x14000d9bb  mov     rcx, rdi
0x14000d9be  mov     ebp, [rsp+0C8h+arg_30]
0x14000d9c5  mov     [rsp+0C8h+var_68], eax
0x14000d9c9  movzx   eax, [rsp+0C8h+arg_50]
0x14000d9d1  mov     [rsp+0C8h+var_70], al
0x14000d9d5  mov     rax, [rsp+0C8h+SourceBuffer]
0x14000d9dd  mov     [rsp+0C8h+var_78], rax
0x14000d9e2  mov     eax, [rsp+0C8h+arg_28]
0x14000d9e9  mov     qword ptr [rsp+0C8h+var_80], rsi
0x14000d9ee  mov     dword ptr [rsp+0C8h+var_88], ebx
0x14000d9f2  mov     [rsp+0C8h+var_90], ebp
0x14000d9f6  mov     [rsp+0C8h+var_98], eax
0x14000d9fa  mov     rax, [rsp+0C8h+arg_20]
0x14000da02  mov     qword ptr [rsp+0C8h+var_A8], rax
0x14000da07  call    AfdBufferReceiveDatagram
0x14000da0c  mov     r13, rax
0x14000da0f  test    rax, rax
0x14000da12  jz      loc_14000DB7F
0x14000da18  mov     r9, [rsp+0C8h+SourceBuffer]
0x14000da20  mov     r8, rdi
0x14000da23  mov     [rsp+0C8h+Src], r15
0x14000da28  mov     edx, 1F44h
0x14000da2d  mov     [rsp+0C8h+var_A8], ebx
0x14000da31  call    AFDETW_TRACEDATA_INDICATION
0x14000da36  mov     r9, [rsp+0C8h+arg_60]
0x14000da3e  xor     edx, edx
0x14000da40  mov     r8, [r13+38h]
0x14000da44  call    AFDETW_TRACEBUFFER
0x14000da49  cmp     ebp, ebx
0x14000da4b  jnz     loc_140075B1D
0x14000da51  lea     rcx, [rdi+70h]
0x14000da55  mov     rdx, [rcx]
0x14000da58  cmp     rdx, rcx
0x14000da5b  jnz     loc_14000DB0B
0x14000da61  mov     [rsp+0C8h+Irp], 0
0x14000da6d  mov     rax, [rdi+180h]
0x14000da74  test    rax, rax
0x14000da77  jnz     loc_14000DBA0
0x14000da7d  mov     ebp, 1
0x14000da82  xor     r8d, r8d
0x14000da85  mov     edx, ebp
0x14000da87  mov     rcx, rdi
0x14000da8a  call    AfdIndicateEventSelectEvent
0x14000da8f  mov     r9, r12
0x14000da92  xor     r8d, r8d
0x14000da95  mov     edx, ebp
0x14000da97  mov     rcx, rdi
0x14000da9a  call    AfdIndicatePollEvent
0x14000da9f  test    al, al
0x14000daa1  jz      loc_14000DB4B
0x14000daa7  xorps   xmm0, xmm0
0x14000daaa  lea     rcx, [rdi+38h]; SpinLock
0x14000daae  xor     eax, eax
0x14000dab0  lea     rdx, [rsp+0C8h+var_58]; LockHandle
0x14000dab5  movups  xmmword ptr [rsp+0C8h+var_58.LockQueue.Next], xmm0
0x14000daba  mov     qword ptr [rsp+0C8h+var_58.OldIrql], rax
0x14000dac2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000dac9  nop     dword ptr [rax+rax+00h]
0x14000dace  cmp     qword ptr [rdi+180h], 0
0x14000dad6  jnz     loc_140075A45
0x14000dadc  lea     rcx, [rsp+0C8h+var_58]; LockHandle
0x14000dae1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000dae8  nop     dword ptr [rax+rax+00h]
0x14000daed  mov     rdi, [rsp+0C8h+Irp]
0x14000daf5  mov     byte ptr [r14], 0
0x14000daf9  test    rdi, rdi
0x14000dafc  jnz     loc_140075A9A
0x14000db02  mov     [rsi], ebx
0x14000db04  xor     eax, eax
0x14000db06  jmp     loc_14000D969
0x14000db0b  cmp     [rdx+8], rcx
0x14000db0f  jnz     loc_14000DB99
0x14000db15  mov     rax, [rdx]
0x14000db18  cmp     [rax+8], rdx
0x14000db1c  jnz     short loc_14000DB99
0x14000db1e  mov     [rcx], rax
0x14000db21  lea     r8, [rdx-0A8h]
0x14000db28  mov     [rax+8], rcx
0x14000db2c  xor     eax, eax
0x14000db2e  xchg    rax, [r8+68h]
0x14000db32  mov     [rsp+0C8h+Irp], r8
0x14000db3a  test    rax, rax
0x14000db3d  jnz     loc_14000DA6D
0x14000db43  mov     [rdx], rax
0x14000db46  jmp     loc_14000DA55
0x14000db4b  xor     r8d, r8d
0x14000db4e  mov     rdx, r12
0x14000db51  mov     rcx, rdi
0x14000db54  call    AfdNotifySockIndicateEventsUnlock
0x14000db59  jmp     short loc_14000DAED
0x14000db5b  add     rcx, 38h ; '8'; SpinLock
0x14000db5f  mov     byte ptr [r14], 1
0x14000db63  mov     rdx, r12; LockHandle
0x14000db66  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000db6d  nop     dword ptr [rax+rax+00h]
0x14000db72  mov     r9d, [rsp+0C8h+arg_18]
0x14000db7a  jmp     loc_14000D82C
0x14000db7f  mov     rcx, r12; LockHandle
0x14000db82  mov     byte ptr [r14], 0
0x14000db86  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000db8d  nop     dword ptr [rax+rax+00h]
0x14000db92  xor     eax, eax
0x14000db94  jmp     loc_14000D969
0x14000db99  mov     ecx, 3
0x14000db9e  int     29h; Win8: RtlFailFast(ecx)
0x14000dba0  or      word ptr [rax+64h], 1
0x14000dba5  jmp     loc_14000DA7D
0x14000dbaa  mov     rax, [r13+68h]
0x14000dbae  mov     ebp, 1
0x14000dbb3  dec     byte ptr [rax+43h]
0x14000dbb6  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000dbbe  mov     rcx, [r13+68h]
0x14000dbc2  mov     rax, [rsp+0C8h+arg_68]
0x14000dbca  mov     [rax], rcx
0x14000dbcd  mov     dword ptr [rsi], 0
0x14000dbd3  lock xadd [rdi+40h], rbp
0x14000dbd9  inc     rbp
0x14000dbdc  cmp     rbp, 1
0x14000dbe0  jle     loc_14000DC7C
0x14000dbe6  mov     eax, 0C0000016h
0x14000dbeb  jmp     loc_14000D969
0x14000dbf0  mov     rax, [rsi+0B8h]
0x14000dbf7  lea     rcx, AfdRestartReceiveDatagramWithUserIrp
0x14000dbfe  mov     [rax-10h], rcx
0x14000dc02  mov     [rax-8], rdi
0x14000dc06  mov     byte ptr [rax-45h], 0E0h
0x14000dc0a  mov     rax, [rsi+0B8h]
0x14000dc11  mov     word ptr [rax-48h], 0A0Fh
0x14000dc17  mov     [rax-20h], r12
0x14000dc1b  mov     [rax-18h], r14
0x14000dc1f  mov     [rax-40h], ebp
0x14000dc22  mov     qword ptr [rax-38h], 0
0x14000dc2a  mov     qword ptr [rax-30h], 0
0x14000dc32  mov     dword ptr [rax-28h], 0
0x14000dc39  lock inc dword ptr [rdi+0F8h]
0x14000dc40  dec     byte ptr [rsi+43h]
0x14000dc43  mov     ebp, 1
0x14000dc48  mov     rax, [rsp+0C8h+arg_68]
0x14000dc50  add     qword ptr [rsi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000dc58  mov     [rax], rsi
0x14000dc5b  mov     rax, [rsp+0C8h+arg_40]
0x14000dc63  mov     dword ptr [rax], 0
0x14000dc69  lock xadd [rdi+40h], rbp
0x14000dc6f  inc     rbp
0x14000dc72  cmp     rbp, 1
0x14000dc76  jg      loc_14000DBE6
0x14000dc7c  mov     ecx, 0Eh
0x14000dc81  int     29h; Win8: RtlFailFast(ecx)
0x14000dc83  jmp     loc_14000DBE6
0x1400758d4  mov     eax, [rdi+8]
0x1400758d7  bt      eax, 8
0x1400758db  jb      loc_14000D846
0x1400758e1  mov     eax, [rdi+0C0h]
0x1400758e7  test    al, 10h
0x1400758e9  jnz     loc_14000D846
0x1400758ef  mov     edx, [rdi+0B0h]
0x1400758f5  mov     r9d, r13d
0x1400758f8  mov     rcx, [rdi+0B8h]
0x1400758ff  mov     r8, r15
0x140075902  mov     byte ptr [rsp+0C8h+var_A8], 1
0x140075907  call    AfdAreTransportAddressesEqual
0x14007590c  test    al, al
0x14007590e  jnz     short loc_14007596A
0x140075910  or      dword ptr [rdi+0C0h], 1000h
0x14007591a  mov     rcx, r12; LockHandle
0x14007591d  mov     [r14], al
0x140075920  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140075927  nop     dword ptr [rax+rax+00h]
0x14007592c  mov     r9, [rsp+0C8h+SourceBuffer]
0x140075934  mov     r8, rdi
0x140075937  mov     ebx, [rsp+0C8h+SourceBytesToCopy]
0x14007593e  mov     edx, 2710h
0x140075943  mov     [rsp+0C8h+var_98], 1
0x14007594b  mov     [rsp+0C8h+Src], r15
0x140075950  mov     [rsp+0C8h+var_A8], ebx
0x140075954  call    AFDETW_TRACEDATAGRAM_DROP
0x140075959  mov     rax, [rsp+0C8h+arg_40]
0x140075961  mov     [rax], ebx
0x140075963  xor     eax, eax
0x140075965  jmp     loc_14000D971
0x14007596a  mov     r9d, [rsp+0C8h+arg_18]
0x140075972  jmp     loc_14000D846
0x140075977  cmp     qword ptr [rsi+8], 0
0x14007597c  jz      loc_14000D8B9
0x140075982  mov     rbx, [rsi+0B8h]
0x140075989  xor     r9d, r9d
0x14007598c  mov     r14, [rdi+18h]
0x140075990  mov     r8, rdi
0x140075993  mov     r12, [rdi+28h]
0x140075997  mov     edx, 1F43h
0x14007599c  mov     [rsp+0C8h+Src], r15
0x1400759a1  mov     [rsp+0C8h+var_A8], ebp
0x1400759a5  call    AFDETW_TRACEDATA_INDICATION
0x1400759aa  mov     r9, [rsp+0C8h+arg_60]
0x1400759b2  xor     edx, edx
0x1400759b4  mov     r8, [rsi+8]
0x1400759b8  call    AFDETW_TRACEBUFFER
0x1400759bd  mov     r8, [rsi+8]
0x1400759c1  xor     r9d, r9d
0x1400759c4  mov     rdx, rsi
0x1400759c7  call    AFDETW_TRACEBUFFER
0x1400759cc  mov     eax, [rsp+0C8h+arg_28]
0x1400759d3  mov     r8d, ebp; SourceBytesToCopy
  ... truncated ...
```
