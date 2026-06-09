# AfdTLSuperConnectComplete

- ea: `0x140010eb0`
- end: `0x140011226`
- name: `AfdTLSuperConnectComplete`
- size: `886`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14003ae30`

## callees

- `0x140010670`
- `0x140010eb0`
- `0x140011670`
- `0x140012610`
- `0x140012a88`
- `0x14001b938`
- `0x14001c708`
- `0x14001ebf4`
- `0x1400931f0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400110af`
- `ntoskrnl!IofCompleteRequest` at `0x1400110af`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010f5d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010fda`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001102d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400110cd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011150`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400111db`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010f5d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010fda`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001102d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400110cd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011150`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400111db`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140010f22`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140010faa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140010f22`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140010faa`

## pseudocode

```c
void __fastcall AfdTLSuperConnectComplete(unsigned int *Entry, int a2, __int64 a3, __int64 a4)
{
  IRP *v4; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PVOID FsContext; // rbx
  __int64 v10; // rdi
  int v11; // ecx
  volatile signed __int64 *v12; // r12
  unsigned int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // r13d
  int v17; // eax
  signed __int64 v18; // rax
  bool v19; // cc
  signed __int64 v20; // rax
  signed __int64 v21; // r15
  signed __int64 v22; // r15
  signed __int64 v23; // rax
  signed __int64 v24; // rax
  int v25; // eax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-68h] BYREF

  v4 = (IRP *)*((_QWORD *)Entry + 6);
  memset(&LockHandle, 0, sizeof(LockHandle));
  CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
  FsContext = CurrentStackLocation->FileObject->FsContext;
  v10 = *((_QWORD *)FsContext + 24);
  if ( (xmmword_1400875E0 & 0x80u) != 0LL )
    WPP_SF_Dq(
      1031,
      20,
      WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids,
      (unsigned int)a2,
      CurrentStackLocation->FileObject->FsContext);
  if ( Entry[16] )
    *((_QWORD *)Entry + 6) = v10;
  v4->IoStatus.Status = a2;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)FsContext + 7, &LockHandle);
  if ( a2 < 0 )
  {
    *(_WORD *)FsContext = -20528;
    v12 = (volatile signed __int64 *)(v10 + 48);
    v15 = *(_DWORD *)(v10 + 4);
    *(_QWORD *)(v10 + 24) = 0;
    v16 = v15 & 0x80;
    *(_DWORD *)(v10 + 4) = v15 & 0xFFFFFFF7;
    *((_QWORD *)FsContext + 24) = 0;
    v17 = *(_DWORD *)(v10 + 4);
    if ( (v17 & 0x1000) != 0 )
    {
      *(_DWORD *)(v10 + 4) = v17 & 0xFFFFEFFF;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v18 = _InterlockedExchangeAdd64(v12, 0xFFFFFFFFFFFFFFFFuLL);
      v19 = v18 <= 1;
      v20 = v18 - 1;
      if ( v19 )
      {
        if ( v20 )
          __fastfail(0xEu);
        AfdCloseConnection(v10);
      }
    }
    else
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( v16 )
    {
      AfdCommonRestartAbort(v10, (unsigned int)a2);
    }
    else
    {
      v23 = _InterlockedExchangeAdd64(v12, 0xFFFFFFFFFFFFFFFFuLL);
      v19 = v23 <= 1;
      v24 = v23 - 1;
      if ( v19 )
      {
        if ( v24 )
          __fastfail(0xEu);
        AfdCloseConnection(v10);
      }
    }
    AfdFinishConnect(FsContext);
    goto LABEL_17;
  }
  *(_DWORD *)(v10 + 4) &= ~8u;
  v11 = *(_DWORD *)(v10 + 4);
  *(_QWORD *)(v10 + 16) = a3;
  *(_QWORD *)(v10 + 24) = a4;
  if ( (*((_BYTE *)FsContext + 7) & 0x10) == 0 || (v11 & 0x200000) != 0 || AfdDynamicSendBufferDisabled )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    *((_BYTE *)FsContext + 2) = 4;
    *(_QWORD *)(v10 + 40) = MEMORY[0xFFFFF78000000008];
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    *((_BYTE *)FsContext + 2) = 4;
    *(_QWORD *)(v10 + 40) = MEMORY[0xFFFFF78000000008];
    AfdCheckISBEvents(v10, (unsigned int)AfdTLSockOptEnable);
  }
  v12 = (volatile signed __int64 *)(v10 + 48);
  AfdFinishConnect(FsContext);
  v13 = Entry[16];
  if ( !v13 || *(_DWORD *)(v10 + 120) == v13 )
  {
LABEL_17:
    if ( !Entry[16] )
      AfdReturnBuffer((unsigned __int16 *)Entry, *((PEPROCESS *)FsContext + 6));
    goto LABEL_19;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)FsContext + 7, &LockHandle);
  v14 = *(_DWORD *)(v10 + 4);
  if ( (v14 & 0x100010) != 0 )
  {
    v4->IoStatus.Status = -((v14 & 0x100000) != 0) - 1073741508;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_17;
  }
  *(_DWORD *)(v10 + 120) += Entry[16];
  ++*(_DWORD *)(v10 + 124);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  *(_DWORD *)(*((_QWORD *)Entry + 7) + 40LL) = Entry[16];
  v4->IoStatus.Information = Entry[16];
  if ( _InterlockedIncrement64(v12) <= 1 )
    __fastfail(0xEu);
  v25 = AfdTLStartBufferedVcSend(v10, *((_QWORD *)Entry + 7), Entry[16], 0, Entry);
  if ( v25 < 0 )
  {
    v4->IoStatus.Status = v25;
    v4->IoStatus.Information = 0;
  }
LABEL_19:
  if ( (unsigned __int8)AfdTLCompleteRequest(v4) )
  {
    v21 = _InterlockedExchangeAdd64(v12, 0xFFFFFFFFFFFFFFFFuLL);
    v19 = v21 <= 1;
    v22 = v21 - 1;
    if ( v19 )
    {
      if ( v22 )
        __fastfail(0xEu);
      AfdCloseConnection(v10);
    }
    IofCompleteRequest(v4, AfdPriorityBoost);
  }
}

```

## disassembly

```asm
0x140010eb0  mov     [rsp+arg_10], r8
0x140010eb5  push    rbx
0x140010eb6  push    rbp
0x140010eb7  push    rsi
0x140010eb8  push    rdi
0x140010eb9  push    r12
0x140010ebb  push    r13
0x140010ebd  push    r14
0x140010ebf  push    r15
0x140010ec1  sub     rsp, 58h
0x140010ec5  mov     rbp, [rcx+30h]
0x140010ec9  xor     eax, eax
0x140010ecb  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x140010ed0  xorps   xmm0, xmm0
0x140010ed3  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x140010ed8  mov     r12, r9
0x140010edb  mov     r14d, edx
0x140010ede  mov     rax, [rbp+0B8h]
0x140010ee5  mov     rsi, rcx
0x140010ee8  mov     rbx, [rax+30h]
0x140010eec  mov     rbx, [rbx+18h]
0x140010ef0  mov     rdi, [rbx+0C0h]
0x140010ef7  cmp     byte ptr cs:xmmword_1400875E0, 0
0x140010efe  jl      loc_140011124
0x140010f04  cmp     dword ptr [rsi+40h], 0
0x140010f08  ja      loc_1400111B6
0x140010f0e  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x140010f13  mov     [rbp+30h], r14d
0x140010f17  lea     rcx, [rbx+38h]; SpinLock
0x140010f1b  mov     r15, 0FFFFFFFFFFFFFFFFh
0x140010f22  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140010f29  nop     dword ptr [rax+rax+00h]
0x140010f2e  test    r14d, r14d
0x140010f31  js      loc_140010FEB
0x140010f37  and     dword ptr [rdi+4], 0FFFFFFF7h
0x140010f3b  mov     rax, [rsp+98h+arg_10]
0x140010f43  mov     ecx, [rdi+4]
0x140010f46  mov     [rdi+10h], rax
0x140010f4a  mov     [rdi+18h], r12
0x140010f4e  test    byte ptr [rbx+7], 10h
0x140010f52  jnz     loc_1400111BF
0x140010f58  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140010f5d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140010f64  nop     dword ptr [rax+rax+00h]
0x140010f69  mov     byte ptr [rbx+2], 4
0x140010f6d  mov     rax, ds:0FFFFF78000000008h
0x140010f77  mov     [rdi+28h], rax
0x140010f7b  xor     r8d, r8d
0x140010f7e  lea     r12, [rdi+30h]
0x140010f82  mov     rdx, rbp
0x140010f85  mov     rcx, rbx; Context
0x140010f88  call    AfdFinishConnect
0x140010f8d  mov     eax, [rsi+40h]
0x140010f90  test    eax, eax
0x140010f92  jz      loc_14001106E
0x140010f98  cmp     [rdi+78h], eax
0x140010f9b  jz      loc_14001106E
0x140010fa1  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x140010fa6  lea     rcx, [rbx+38h]; SpinLock
0x140010faa  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140010fb1  nop     dword ptr [rax+rax+00h]
0x140010fb6  mov     eax, [rdi+4]
0x140010fb9  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140010fbe  test    eax, 100010h
0x140010fc3  jz      loc_140011147
0x140010fc9  and     eax, 100000h
0x140010fce  neg     eax
0x140010fd0  sbb     eax, eax
0x140010fd2  add     eax, 0C000013Ch
0x140010fd7  mov     [rbp+30h], eax
0x140010fda  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140010fe1  nop     dword ptr [rax+rax+00h]
0x140010fe6  jmp     loc_14001106E
0x140010feb  mov     word ptr [rbx], 0AFD0h
0x140010ff0  lea     r12, [rdi+30h]
0x140010ff4  mov     eax, [rdi+4]
0x140010ff7  xor     ecx, ecx
0x140010ff9  mov     r13d, eax
0x140010ffc  mov     [rdi+18h], rcx
0x140011000  and     eax, 0FFFFFFF7h
0x140011003  and     r13d, 80h
0x14001100a  mov     [rdi+4], eax
0x14001100d  mov     [rbx+0C0h], rcx
0x140011014  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140011019  mov     eax, [rdi+4]
0x14001101c  bt      eax, 0Ch
0x140011020  jnb     loc_1400110CD
0x140011026  btr     eax, 0Ch
0x14001102a  mov     [rdi+4], eax
0x14001102d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011034  nop     dword ptr [rax+rax+00h]
0x140011039  mov     rax, r15
0x14001103c  lock xadd [r12], rax
0x140011042  sub     rax, 1
0x140011046  jle     loc_140011106
0x14001104c  test    r13d, r13d
0x14001104f  jz      loc_1400110DE
0x140011055  mov     edx, r14d
0x140011058  mov     rcx, rdi
0x14001105b  call    AfdCommonRestartAbort
0x140011060  xor     r8d, r8d
0x140011063  mov     rdx, rbp
0x140011066  mov     rcx, rbx; Context
0x140011069  call    AfdFinishConnect
0x14001106e  cmp     dword ptr [rsi+40h], 0
0x140011072  jnz     short loc_140011080
0x140011074  mov     rdx, [rbx+30h]; Process
0x140011078  mov     rcx, rsi; Entry
0x14001107b  call    AfdReturnBuffer
0x140011080  mov     rcx, rbp
0x140011083  call    AfdTLCompleteRequest
0x140011088  test    al, al
0x14001108a  jz      short loc_1400110BB
0x14001108c  lock xadd [r12], r15
0x140011092  sub     r15, 1
0x140011096  jg      short loc_1400110A5
0x140011098  test    r15, r15
0x14001109b  jnz     short loc_14001111B
0x14001109d  mov     rcx, rdi
0x1400110a0  call    AfdCloseConnection
0x1400110a5  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x1400110ac  mov     rcx, rbp; Irp
0x1400110af  call    cs:__imp_IofCompleteRequest
0x1400110b6  nop     dword ptr [rax+rax+00h]
0x1400110bb  add     rsp, 58h
0x1400110bf  pop     r15
0x1400110c1  pop     r14
0x1400110c3  pop     r13
0x1400110c5  pop     r12
0x1400110c7  pop     rdi
0x1400110c8  pop     rsi
0x1400110c9  pop     rbp
0x1400110ca  pop     rbx
0x1400110cb  retn
0x1400110cd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400110d4  nop     dword ptr [rax+rax+00h]
0x1400110d9  jmp     loc_14001104C
0x1400110de  mov     rax, r15
0x1400110e1  lock xadd [r12], rax
0x1400110e7  sub     rax, 1
0x1400110eb  jg      loc_140011060
0x1400110f1  test    rax, rax
0x1400110f4  jz      loc_140011219
0x1400110fa  mov     ecx, 0Eh
0x1400110ff  int     29h; Win8: RtlFailFast(ecx)
0x140011101  jmp     loc_140011060
0x140011106  test    rax, rax
0x140011109  jz      loc_14001120C
0x14001110f  mov     ecx, 0Eh
0x140011114  int     29h; Win8: RtlFailFast(ecx)
0x140011116  jmp     loc_14001104C
0x14001111b  mov     ecx, 0Eh
0x140011120  int     29h; Win8: RtlFailFast(ecx)
0x140011122  jmp     short loc_1400110A5
0x140011124  mov     edx, 14h
0x140011129  mov     [rsp+98h+Entry], rbx
0x14001112e  mov     ecx, 407h
0x140011133  lea     r8, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids
0x14001113a  mov     r9d, r14d
0x14001113d  call    WPP_SF_Dq
0x140011142  jmp     loc_140010F04
0x140011147  mov     eax, [rsi+40h]
0x14001114a  add     [rdi+78h], eax
0x14001114d  inc     dword ptr [rdi+7Ch]
0x140011150  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011157  nop     dword ptr [rax+rax+00h]
0x14001115c  mov     eax, [rsi+40h]
0x14001115f  mov     rcx, [rsi+38h]
0x140011163  mov     [rcx+28h], eax
0x140011166  mov     eax, [rsi+40h]
0x140011169  mov     [rbp+38h], rax
0x14001116d  mov     eax, 1
0x140011172  lock xadd [r12], rax
0x140011178  inc     rax
0x14001117b  cmp     rax, 1
0x14001117f  jg      short loc_140011188
0x140011181  mov     ecx, 0Eh
0x140011186  int     29h; Win8: RtlFailFast(ecx)
0x140011188  mov     r8d, [rsi+40h]; int
0x14001118c  xor     r9d, r9d; int
0x14001118f  mov     rdx, [rsi+38h]; int
0x140011193  mov     rcx, rdi; int
0x140011196  mov     [rsp+98h+Entry], rsi; Entry
0x14001119b  call    AfdTLStartBufferedVcSend
0x1400111a0  test    eax, eax
0x1400111a2  jns     loc_140011080
0x1400111a8  xor     ecx, ecx
0x1400111aa  mov     [rbp+30h], eax
0x1400111ad  mov     [rbp+38h], rcx
0x1400111b1  jmp     loc_140011080
0x1400111b6  mov     [rsi+30h], rdi
0x1400111ba  jmp     loc_140010F0E
0x1400111bf  bt      ecx, 15h
0x1400111c3  jb      loc_140010F58
0x1400111c9  cmp     cs:AfdDynamicSendBufferDisabled, 0
0x1400111d0  jnz     loc_140010F58
0x1400111d6  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x1400111db  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400111e2  nop     dword ptr [rax+rax+00h]
0x1400111e7  mov     byte ptr [rbx+2], 4
0x1400111eb  mov     rcx, rdi
0x1400111ee  mov     rax, ds:0FFFFF78000000008h
0x1400111f8  mov     [rdi+28h], rax
0x1400111fc  mov     edx, cs:AfdTLSockOptEnable
0x140011202  call    AfdCheckISBEvents
0x140011207  jmp     loc_140010F7B
0x14001120c  mov     rcx, rdi
0x14001120f  call    AfdCloseConnection
0x140011214  jmp     loc_14001104C
0x140011219  mov     rcx, rdi
0x14001121c  call    AfdCloseConnection
0x140011221  jmp     loc_140011060
```
