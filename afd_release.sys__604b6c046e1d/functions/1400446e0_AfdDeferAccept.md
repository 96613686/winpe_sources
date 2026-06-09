# AfdDeferAccept

- ea: `0x1400446e0`
- end: `0x140044951`
- name: `AfdDeferAccept`
- size: `625`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14000f390`
- `0x1400137a0`
- `0x140019fe4`
- `0x14001b0d0`
- `0x14001b800`
- `0x14002dc3c`
- `0x14003f7d8`
- `0x1400446e0`
- `0x140044a9c`
- `0x14009304c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140044836`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140044836`
- `ntoskrnl!IofCompleteRequest` at `0x140044770`
- `ntoskrnl!IofCompleteRequest` at `0x14004488a`
- `ntoskrnl!IofCompleteRequest` at `0x140044770`
- `ntoskrnl!IofCompleteRequest` at `0x14004488a`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140044827`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140044827`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044752`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400448ee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004493e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044752`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400448ee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004493e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044730`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044730`

## pseudocode

```c
__int64 __fastcall AfdDeferAccept(PIRP Irp, __int64 a2)
{
  struct _IRP *MasterIrp; // rsi
  __int64 v3; // rax
  __int64 v5; // rbx
  _QWORD *ReturnedConnection; // rax
  __int64 v7; // rdi
  unsigned int v8; // ebx
  CCHAR v9; // dl
  __int64 v11; // rsi
  int v12; // eax
  CCHAR v13; // dl
  volatile signed __int32 *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF
  KIRQL Irql; // [rsp+90h] [rbp+38h] BYREF

  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  v3 = *(_QWORD *)(a2 + 48);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = *(_QWORD *)(v3 + 24);
  Irp->IoStatus.Information = 0;
  if ( (*(_DWORD *)(v5 + 8) & 1) != 0 && *(_DWORD *)(a2 + 16) >= 8u )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
    ReturnedConnection = AfdGetReturnedConnection(v5, *(_DWORD *)&MasterIrp->Type);
    v7 = (__int64)ReturnedConnection;
    if ( ReturnedConnection )
    {
      if ( *((_BYTE *)&MasterIrp->Size + 2) )
      {
        *(_DWORD *)(v5 + 72) &= ~0x80u;
        if ( (xmmword_1400875E0 & 0x20) != 0 )
          WPP_SF_qD(1029, 18, WPP_6216d3581a803072be4346b6e903d992_Traceguids, v5, *(_DWORD *)(v5 + 72));
        if ( *(_QWORD *)(v5 + 96) == v5 + 96 )
          AfdNotifySockEventsChangedUnderLock(v5, 0, 128);
        else
          AfdIndicateEventSelectEvent(v5, 128, 0);
        if ( (*(_DWORD *)(v7 + 4) & 0x20000000) != 0 )
        {
          v11 = *(_QWORD *)(v7 + 40);
          *(_QWORD *)(v7 + 40) = 0;
          if ( _InterlockedExchange64((volatile __int64 *)(v11 + 104), 0) )
          {
            AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v5, &LockHandle, 0);
            v12 = -1073741258;
          }
          else
          {
            Irql = 0;
            AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v5, &LockHandle, 0);
            IoAcquireCancelSpinLock(&Irql);
            IoReleaseCancelSpinLock(Irql);
            v12 = -1073741536;
          }
          *(_DWORD *)(v11 + 48) = v12;
          *(_DWORD *)(v7 + 4) &= ~0x20000000u;
          *(_QWORD *)(v7 + 8) = 0;
          AfdSanReleaseConnection(v5, v7, 0);
          AfdDereferenceEndpoint(v5);
          v13 = AfdPriorityBoost;
          *(_QWORD *)(v11 + 56) = 0;
          IofCompleteRequest((PIRP)v11, v13);
        }
        else
        {
          AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v5, &LockHandle, 0);
          if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
          {
            if ( (*(_DWORD *)(v7 + 4) & 2) != 0 && (*(_DWORD *)(v5 + 8) & 0x400000) != 0 )
              v14 = (volatile signed __int32 *)(*(_QWORD *)(v5 + 280) + 48LL);
            else
              v14 = (volatile signed __int32 *)(v5 + 176);
            _InterlockedAdd(v14, 1u);
            AfdReplenishListenBacklog(v5);
          }
          AfdAbortConnection(v7);
        }
      }
      else
      {
        if ( (*((_DWORD *)ReturnedConnection + 1) & 0x80u) != 0 )
        {
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          AfdAbortConnection(v7);
          v8 = -1073741299;
          goto LABEL_6;
        }
        v15 = v5 + 96;
        *((_WORD *)ReturnedConnection + 1) = 1;
        v16 = *(_QWORD *)v15;
        if ( *(_QWORD *)(*(_QWORD *)v15 + 8LL) != v15 )
          __fastfail(3u);
        ReturnedConnection[22] = v16;
        ReturnedConnection[23] = v15;
        *(_QWORD *)(v16 + 8) = ReturnedConnection + 22;
        *(_QWORD *)v15 = ReturnedConnection + 22;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      v8 = 0;
      goto LABEL_6;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  v8 = -1073741811;
LABEL_6:
  v9 = AfdPriorityBoost;
  Irp->IoStatus.Status = v8;
  IofCompleteRequest(Irp, v9);
  return v8;
}

```

## disassembly

```asm
0x1400446e0  push    rbp
0x1400446e2  push    rbx
0x1400446e3  push    rsi
0x1400446e4  push    rdi
0x1400446e5  push    r12
0x1400446e7  push    r14
0x1400446e9  mov     rbp, rsp
0x1400446ec  sub     rsp, 58h
0x1400446f0  mov     rsi, [rcx+18h]
0x1400446f4  xor     eax, eax
0x1400446f6  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400446fa  xorps   xmm0, xmm0
0x1400446fd  mov     rax, [rdx+30h]
0x140044701  mov     r12d, 1
0x140044707  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14004470b  mov     r14, rcx
0x14004470e  mov     rbx, [rax+18h]
0x140044712  mov     qword ptr [rcx+38h], 0
0x14004471a  mov     eax, [rbx+8]
0x14004471d  test    r12b, al
0x140044720  jz      short loc_14004475E
0x140044722  cmp     dword ptr [rdx+10h], 8
0x140044726  jb      short loc_14004475E
0x140044728  lea     rcx, [rbx+38h]; SpinLock
0x14004472c  lea     rdx, [rbp+LockHandle]; LockHandle
0x140044730  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140044737  nop     dword ptr [rax+rax+00h]
0x14004473c  mov     edx, [rsi]
0x14004473e  mov     rcx, rbx
0x140044741  call    AfdGetReturnedConnection
0x140044746  mov     rdi, rax
0x140044749  test    rax, rax
0x14004474c  jnz     short loc_14004478C
0x14004474e  lea     rcx, [rbp+LockHandle]; LockHandle
0x140044752  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140044759  nop     dword ptr [rax+rax+00h]
0x14004475e  mov     ebx, 0C000000Dh
0x140044763  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140044769  mov     rcx, r14; Irp
0x14004476c  mov     [r14+30h], ebx
0x140044770  call    cs:__imp_IofCompleteRequest
0x140044777  nop     dword ptr [rax+rax+00h]
0x14004477c  mov     eax, ebx
0x14004477e  add     rsp, 58h
0x140044782  pop     r14
0x140044784  pop     r12
0x140044786  pop     rdi
0x140044787  pop     rsi
0x140044788  pop     rbx
0x140044789  pop     rbp
0x14004478a  retn
0x14004478c  cmp     byte ptr [rsi+4], 0
0x140044790  jz      loc_1400448E3
0x140044796  mov     eax, [rbx+48h]
0x140044799  btr     eax, 7
0x14004479d  mov     [rbx+48h], eax
0x1400447a0  test    byte ptr cs:xmmword_1400875E0, 20h
0x1400447a7  jz      short loc_1400447C9
0x1400447a9  mov     eax, [rbx+48h]
0x1400447ac  lea     r8, WPP_6216d3581a803072be4346b6e903d992_Traceguids
0x1400447b3  mov     edx, 12h
0x1400447b8  mov     [rsp+58h+var_38], eax
0x1400447bc  mov     ecx, 405h
0x1400447c1  mov     r9, rbx
0x1400447c4  call    WPP_SF_qD
0x1400447c9  lea     rax, [rbx+60h]
0x1400447cd  mov     rcx, rbx
0x1400447d0  cmp     [rax], rax
0x1400447d3  jz      short loc_1400447E4
0x1400447d5  xor     r8d, r8d
0x1400447d8  mov     edx, 80h
0x1400447dd  call    AfdIndicateEventSelectEvent
0x1400447e2  jmp     short loc_1400447F1
0x1400447e4  xor     edx, edx
0x1400447e6  mov     r8d, 80h
0x1400447ec  call    AfdNotifySockEventsChangedUnderLock
0x1400447f1  xor     r8d, r8d
0x1400447f4  lea     rdx, [rbp+LockHandle]
0x1400447f8  test    dword ptr [rdi+4], 20000000h
0x1400447ff  mov     rcx, rbx
0x140044802  jz      loc_14004489B
0x140044808  mov     rsi, [rdi+28h]
0x14004480c  xor     eax, eax
0x14004480e  mov     [rdi+28h], r8
0x140044812  xchg    rax, [rsi+68h]
0x140044816  test    rax, rax
0x140044819  jnz     short loc_140044849
0x14004481b  mov     [rbp+Irql], al
0x14004481e  call    AfdNotifySockIndicateEventsUnlock
0x140044823  lea     rcx, [rbp+Irql]; Irql
0x140044827  call    cs:__imp_IoAcquireCancelSpinLock
0x14004482e  nop     dword ptr [rax+rax+00h]
0x140044833  mov     cl, [rbp+Irql]; Irql
0x140044836  call    cs:__imp_IoReleaseCancelSpinLock
0x14004483d  nop     dword ptr [rax+rax+00h]
0x140044842  mov     eax, 0C0000120h
0x140044847  jmp     short loc_140044853
0x140044849  call    AfdNotifySockIndicateEventsUnlock
0x14004484e  mov     eax, 0C0000236h
0x140044853  mov     [rsi+30h], eax
0x140044856  xor     r8d, r8d
0x140044859  btr     dword ptr [rdi+4], 1Dh
0x14004485e  mov     rdx, rdi
0x140044861  mov     rcx, rbx
0x140044864  mov     qword ptr [rdi+8], 0
0x14004486c  call    AfdSanReleaseConnection
0x140044871  mov     rcx, rbx
0x140044874  call    AfdDereferenceEndpoint
0x140044879  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14004487f  mov     rcx, rsi; Irp
0x140044882  mov     qword ptr [rsi+38h], 0
0x14004488a  call    cs:__imp_IofCompleteRequest
0x140044891  nop     dword ptr [rax+rax+00h]
0x140044896  jmp     loc_14004494A
0x14004489b  call    AfdNotifySockIndicateEventsUnlock
0x1400448a0  mov     eax, [rbx+8]
0x1400448a3  bt      eax, 8
0x1400448a7  jb      short loc_1400448D9
0x1400448a9  mov     eax, [rdi+4]
0x1400448ac  test    al, 2
0x1400448ae  jz      short loc_1400448C6
0x1400448b0  mov     eax, [rbx+8]
0x1400448b3  bt      eax, 16h
0x1400448b7  jnb     short loc_1400448C6
0x1400448b9  mov     rax, [rbx+118h]
0x1400448c0  add     rax, 30h ; '0'
0x1400448c4  jmp     short loc_1400448CD
0x1400448c6  lea     rax, [rbx+0B0h]
0x1400448cd  lock add [rax], r12d
0x1400448d1  mov     rcx, rbx
0x1400448d4  call    AfdReplenishListenBacklog
0x1400448d9  mov     rcx, rdi
0x1400448dc  call    AfdAbortConnection
0x1400448e1  jmp     short loc_14004494A
0x1400448e3  mov     eax, [rax+4]
0x1400448e6  test    al, al
0x1400448e8  jns     short loc_14004490C
0x1400448ea  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400448ee  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400448f5  nop     dword ptr [rax+rax+00h]
0x1400448fa  mov     rcx, rdi
0x1400448fd  call    AfdAbortConnection
0x140044902  mov     ebx, 0C000020Dh
0x140044907  jmp     loc_140044763
0x14004490c  add     rbx, 60h ; '`'
0x140044910  mov     [rdi+2], r12w
0x140044915  mov     rcx, [rbx]
0x140044918  cmp     [rcx+8], rbx
0x14004491c  jz      short loc_140044925
0x14004491e  mov     ecx, 3
0x140044923  int     29h; Win8: RtlFailFast(ecx)
0x140044925  lea     rax, [rdi+0B0h]
0x14004492c  mov     [rax], rcx
0x14004492f  mov     [rax+8], rbx
0x140044933  mov     [rcx+8], rax
0x140044937  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004493b  mov     [rbx], rax
0x14004493e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140044945  nop     dword ptr [rax+rax+00h]
0x14004494a  xor     ebx, ebx
0x14004494c  jmp     loc_140044763
```
