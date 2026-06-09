# AfdDeferAccept

- ea: `0x140044700`
- end: `0x140044971`
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
- `0x14003f7f8`
- `0x140044700`
- `0x140044abc`
- `0x14009304c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140044856`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140044856`
- `ntoskrnl!IofCompleteRequest` at `0x140044790`
- `ntoskrnl!IofCompleteRequest` at `0x1400448aa`
- `ntoskrnl!IofCompleteRequest` at `0x140044790`
- `ntoskrnl!IofCompleteRequest` at `0x1400448aa`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140044847`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140044847`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044772`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004490e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004495e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044772`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004490e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004495e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044750`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044750`

## pseudocode

```c
__int64 __fastcall AfdDeferAccept(PIRP Irp, __int64 a2)
{
  struct _IRP *MasterIrp; // rsi
  __int64 v3; // rax
  __int64 v5; // rbx
  __int64 ReturnedConnection; // rax
  __int64 v7; // rdi
  unsigned int v8; // ebx
  CCHAR v9; // dl
  __int64 v11; // rsi
  int v12; // eax
  CCHAR v13; // dl
  volatile signed __int32 *v14; // rax
  __int64 *v15; // rbx
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
    ReturnedConnection = AfdGetReturnedConnection(v5, *(unsigned int *)&MasterIrp->Type);
    v7 = ReturnedConnection;
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
            AfdNotifySockIndicateEventsUnlock(v5, &LockHandle, 0);
            v12 = -1073741258;
          }
          else
          {
            Irql = 0;
            AfdNotifySockIndicateEventsUnlock(v5, &LockHandle, 0);
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
          AfdNotifySockIndicateEventsUnlock(v5, &LockHandle, 0);
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
        if ( (*(_DWORD *)(ReturnedConnection + 4) & 0x80u) != 0 )
        {
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          AfdAbortConnection(v7);
          v8 = -1073741299;
          goto LABEL_6;
        }
        v15 = (__int64 *)(v5 + 96);
        *(_WORD *)(ReturnedConnection + 2) = 1;
        v16 = *v15;
        if ( *(__int64 **)(*v15 + 8) != v15 )
          __fastfail(3u);
        *(_QWORD *)(ReturnedConnection + 176) = v16;
        *(_QWORD *)(ReturnedConnection + 184) = v15;
        *(_QWORD *)(v16 + 8) = ReturnedConnection + 176;
        *v15 = ReturnedConnection + 176;
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
0x140044700  push    rbp
0x140044702  push    rbx
0x140044703  push    rsi
0x140044704  push    rdi
0x140044705  push    r12
0x140044707  push    r14
0x140044709  mov     rbp, rsp
0x14004470c  sub     rsp, 58h
0x140044710  mov     rsi, [rcx+18h]
0x140044714  xor     eax, eax
0x140044716  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14004471a  xorps   xmm0, xmm0
0x14004471d  mov     rax, [rdx+30h]
0x140044721  mov     r12d, 1
0x140044727  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14004472b  mov     r14, rcx
0x14004472e  mov     rbx, [rax+18h]
0x140044732  mov     qword ptr [rcx+38h], 0
0x14004473a  mov     eax, [rbx+8]
0x14004473d  test    r12b, al
0x140044740  jz      short loc_14004477E
0x140044742  cmp     dword ptr [rdx+10h], 8
0x140044746  jb      short loc_14004477E
0x140044748  lea     rcx, [rbx+38h]; SpinLock
0x14004474c  lea     rdx, [rbp+LockHandle]; LockHandle
0x140044750  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140044757  nop     dword ptr [rax+rax+00h]
0x14004475c  mov     edx, [rsi]
0x14004475e  mov     rcx, rbx
0x140044761  call    AfdGetReturnedConnection
0x140044766  mov     rdi, rax
0x140044769  test    rax, rax
0x14004476c  jnz     short loc_1400447AC
0x14004476e  lea     rcx, [rbp+LockHandle]; LockHandle
0x140044772  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140044779  nop     dword ptr [rax+rax+00h]
0x14004477e  mov     ebx, 0C000000Dh
0x140044783  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140044789  mov     rcx, r14; Irp
0x14004478c  mov     [r14+30h], ebx
0x140044790  call    cs:__imp_IofCompleteRequest
0x140044797  nop     dword ptr [rax+rax+00h]
0x14004479c  mov     eax, ebx
0x14004479e  add     rsp, 58h
0x1400447a2  pop     r14
0x1400447a4  pop     r12
0x1400447a6  pop     rdi
0x1400447a7  pop     rsi
0x1400447a8  pop     rbx
0x1400447a9  pop     rbp
0x1400447aa  retn
0x1400447ac  cmp     byte ptr [rsi+4], 0
0x1400447b0  jz      loc_140044903
0x1400447b6  mov     eax, [rbx+48h]
0x1400447b9  btr     eax, 7
0x1400447bd  mov     [rbx+48h], eax
0x1400447c0  test    byte ptr cs:xmmword_1400875E0, 20h
0x1400447c7  jz      short loc_1400447E9
0x1400447c9  mov     eax, [rbx+48h]
0x1400447cc  lea     r8, WPP_6216d3581a803072be4346b6e903d992_Traceguids
0x1400447d3  mov     edx, 12h
0x1400447d8  mov     [rsp+58h+var_38], eax
0x1400447dc  mov     ecx, 405h
0x1400447e1  mov     r9, rbx
0x1400447e4  call    WPP_SF_qD
0x1400447e9  lea     rax, [rbx+60h]
0x1400447ed  mov     rcx, rbx
0x1400447f0  cmp     [rax], rax
0x1400447f3  jz      short loc_140044804
0x1400447f5  xor     r8d, r8d
0x1400447f8  mov     edx, 80h
0x1400447fd  call    AfdIndicateEventSelectEvent
0x140044802  jmp     short loc_140044811
0x140044804  xor     edx, edx
0x140044806  mov     r8d, 80h
0x14004480c  call    AfdNotifySockEventsChangedUnderLock
0x140044811  xor     r8d, r8d
0x140044814  lea     rdx, [rbp+LockHandle]
0x140044818  test    dword ptr [rdi+4], 20000000h
0x14004481f  mov     rcx, rbx
0x140044822  jz      loc_1400448BB
0x140044828  mov     rsi, [rdi+28h]
0x14004482c  xor     eax, eax
0x14004482e  mov     [rdi+28h], r8
0x140044832  xchg    rax, [rsi+68h]
0x140044836  test    rax, rax
0x140044839  jnz     short loc_140044869
0x14004483b  mov     [rbp+Irql], al
0x14004483e  call    AfdNotifySockIndicateEventsUnlock
0x140044843  lea     rcx, [rbp+Irql]; Irql
0x140044847  call    cs:__imp_IoAcquireCancelSpinLock
0x14004484e  nop     dword ptr [rax+rax+00h]
0x140044853  mov     cl, [rbp+Irql]; Irql
0x140044856  call    cs:__imp_IoReleaseCancelSpinLock
0x14004485d  nop     dword ptr [rax+rax+00h]
0x140044862  mov     eax, 0C0000120h
0x140044867  jmp     short loc_140044873
0x140044869  call    AfdNotifySockIndicateEventsUnlock
0x14004486e  mov     eax, 0C0000236h
0x140044873  mov     [rsi+30h], eax
0x140044876  xor     r8d, r8d
0x140044879  btr     dword ptr [rdi+4], 1Dh
0x14004487e  mov     rdx, rdi
0x140044881  mov     rcx, rbx
0x140044884  mov     qword ptr [rdi+8], 0
0x14004488c  call    AfdSanReleaseConnection
0x140044891  mov     rcx, rbx
0x140044894  call    AfdDereferenceEndpoint
0x140044899  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14004489f  mov     rcx, rsi; Irp
0x1400448a2  mov     qword ptr [rsi+38h], 0
0x1400448aa  call    cs:__imp_IofCompleteRequest
0x1400448b1  nop     dword ptr [rax+rax+00h]
0x1400448b6  jmp     loc_14004496A
0x1400448bb  call    AfdNotifySockIndicateEventsUnlock
0x1400448c0  mov     eax, [rbx+8]
0x1400448c3  bt      eax, 8
0x1400448c7  jb      short loc_1400448F9
0x1400448c9  mov     eax, [rdi+4]
0x1400448cc  test    al, 2
0x1400448ce  jz      short loc_1400448E6
0x1400448d0  mov     eax, [rbx+8]
0x1400448d3  bt      eax, 16h
0x1400448d7  jnb     short loc_1400448E6
0x1400448d9  mov     rax, [rbx+118h]
0x1400448e0  add     rax, 30h ; '0'
0x1400448e4  jmp     short loc_1400448ED
0x1400448e6  lea     rax, [rbx+0B0h]
0x1400448ed  lock add [rax], r12d
0x1400448f1  mov     rcx, rbx
0x1400448f4  call    AfdReplenishListenBacklog
0x1400448f9  mov     rcx, rdi
0x1400448fc  call    AfdAbortConnection
0x140044901  jmp     short loc_14004496A
0x140044903  mov     eax, [rax+4]
0x140044906  test    al, al
0x140044908  jns     short loc_14004492C
0x14004490a  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004490e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140044915  nop     dword ptr [rax+rax+00h]
0x14004491a  mov     rcx, rdi
0x14004491d  call    AfdAbortConnection
0x140044922  mov     ebx, 0C000020Dh
0x140044927  jmp     loc_140044783
0x14004492c  add     rbx, 60h ; '`'
0x140044930  mov     [rdi+2], r12w
0x140044935  mov     rcx, [rbx]
0x140044938  cmp     [rcx+8], rbx
0x14004493c  jz      short loc_140044945
0x14004493e  mov     ecx, 3
0x140044943  int     29h; Win8: RtlFailFast(ecx)
0x140044945  lea     rax, [rdi+0B0h]
0x14004494c  mov     [rax], rcx
0x14004494f  mov     [rax+8], rbx
0x140044953  mov     [rcx+8], rax
0x140044957  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004495b  mov     [rbx], rax
0x14004495e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140044965  nop     dword ptr [rax+rax+00h]
0x14004496a  xor     ebx, ebx
0x14004496c  jmp     loc_140044783
```
