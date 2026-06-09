# AfdRestartAccept

- ea: `0x14002d8d0`
- end: `0x14002dc34`
- name: `AfdRestartAccept`
- size: `868`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140003d20`

## callees

- `0x140004c10`
- `0x14000f450`
- `0x1400137a0`
- `0x14001b0d0`
- `0x14001b800`
- `0x14001c708`
- `0x14001d524`
- `0x14001db90`
- `0x14002d8d0`
- `0x14002dc3c`
- `0x14003606c`
- `0x140036dcc`
- `0x1400930cc`
- `0x1400934d8`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14002d9b3`
- `ntoskrnl!IoFreeIrp` at `0x14002d9b3`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002db02`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002db02`
- `ntoskrnl!IofCompleteRequest` at `0x14002db2d`
- `ntoskrnl!IofCompleteRequest` at `0x14002dbfd`
- `ntoskrnl!IofCompleteRequest` at `0x14002db2d`
- `ntoskrnl!IofCompleteRequest` at `0x14002dbfd`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002daf3`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002daf3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002d9ee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002d9ee`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002d9d5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002db41`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002d9d5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002db41`

## pseudocode

```c
__int64 __fastcall AfdRestartAccept(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // rbx
  signed __int64 v6; // rax
  bool v7; // cc
  signed __int64 v8; // rax
  _QWORD *v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // rsi
  _QWORD *v13; // rdx
  __int64 v14; // rcx
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  IRP *v16; // rcx
  struct _LIST_ENTRY *v17; // r8
  struct _LIST_ENTRY *Blink; // rdx
  __int128 v20; // [rsp+30h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-20h] BYREF
  KIRQL Irql; // [rsp+90h] [rbp+30h] BYREF

  v3 = *(_QWORD *)(a3 + 8);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v20 = 0;
  if ( (*(_DWORD *)(v3 + 8) & 0x100) != 0 )
  {
    if ( (BYTE1(xmmword_1400875E0) & 2) != 0 )
      WPP_SF_Dqq(
        1033,
        23,
        WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids,
        0,
        v3,
        a3,
        v20,
        *((_QWORD *)&v20 + 1),
        LockHandle.LockQueue.Next,
        LockHandle.LockQueue.Lock,
        *(_QWORD *)&LockHandle.OldIrql);
  }
  else
  {
    if ( (BYTE1(xmmword_1400875E0) & 2) != 0 )
      WPP_SF_Dqq(
        1033,
        24,
        WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids,
        (unsigned int)a2->IoStatus.Status,
        v3,
        a3,
        v20,
        *((_QWORD *)&v20 + 1),
        LockHandle.LockQueue.Next,
        LockHandle.LockQueue.Lock,
        *(_QWORD *)&LockHandle.OldIrql);
    _InterlockedDecrement((volatile signed __int32 *)(v3 + 180));
    if ( a2->IoStatus.Status < 0 )
    {
      AFDETW_TRACEABORT(2, 8029, v3, 9);
      AfdCommonDisconnectEventHandler(a3, 0, 0, 0, 0, 1);
    }
    IoFreeIrp(a2);
  }
  *(_QWORD *)(a3 + 40) = MEMORY[0xFFFFF78000000008];
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 56), &LockHandle);
  if ( (*(_DWORD *)(v3 + 8) & 0x800) != 0 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    AfdAbortConnection(a3);
  }
  else
  {
    *((_QWORD *)&v20 + 1) = &v20;
    *(_QWORD *)&v20 = &v20;
    while ( !AfdServiceSuperAccept(v3, a3, &LockHandle, (__int64)&v20) )
    {
      v9 = (_QWORD *)(v3 + 128);
      v10 = *(_QWORD **)(v3 + 128);
      if ( v10 == (_QWORD *)(v3 + 128) )
      {
        v13 = *(_QWORD **)(v3 + 104);
        if ( *v13 == v3 + 96 )
        {
          *(_QWORD *)(a3 + 176) = v3 + 96;
          *(_QWORD *)(a3 + 184) = v13;
          *v13 = a3 + 176;
          *(_QWORD *)(v3 + 104) = a3 + 176;
          AfdIndicateEventSelectEvent(v3, 128, 0);
          AfdNotifySockEventsChangedUnderLock(v3, 128, 0);
          if ( (unsigned __int8)AfdIndicatePollEvent(v14, 128, 0, &LockHandle) )
            p_LockHandle = 0;
          else
            p_LockHandle = &LockHandle;
          AfdNotifySockIndicateEventsUnlock(v3, p_LockHandle, 0);
          break;
        }
LABEL_34:
        __fastfail(3u);
      }
      if ( (_QWORD *)v10[1] != v9 )
        goto LABEL_34;
      v11 = *v10;
      if ( *(_QWORD **)(*v10 + 8LL) != v10 )
        goto LABEL_34;
      *v9 = v11;
      v12 = v10 - 21;
      *(_QWORD *)(v11 + 8) = v9;
      *v10 = 0;
      if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
        WPP_SF_q(1032, 25, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, v10 - 21);
      if ( (int)AfdServiceWaitForListen((PIRP)v12) >= 0 )
        break;
      AfdNotifySockIndicateEventsUnlock(v3, &LockHandle, 0);
      if ( !_InterlockedExchange64(v12 + 13, 0) )
      {
        Irql = 0;
        IoAcquireCancelSpinLock(&Irql);
        IoReleaseCancelSpinLock(Irql);
      }
      AFDETW_TRACEWAITLISTEN(1, 6225, v3, *((unsigned int *)v12 + 12));
      IofCompleteRequest((PIRP)v12, AfdPriorityBoost);
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 56), &LockHandle);
    }
    while ( (__int128 *)v20 != &v20 )
    {
      v16 = (IRP *)(v20 - 168);
      v17 = *(struct _LIST_ENTRY **)v20;
      if ( *(_QWORD *)(*(_QWORD *)v20 + 8LL) != (_QWORD)v20 )
        goto LABEL_34;
      Blink = v16->Tail.Overlay.ListEntry.Blink;
      if ( Blink->Flink != (struct _LIST_ENTRY *)v20 )
        goto LABEL_34;
      Blink->Flink = v17;
      v17->Blink = Blink;
      IofCompleteRequest(v16, AfdPriorityBoost);
    }
  }
  v6 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a3 + 48), 0xFFFFFFFFFFFFFFFFuLL);
  v7 = v6 <= 1;
  v8 = v6 - 1;
  if ( v7 )
  {
    if ( v8 )
      __fastfail(0xEu);
    AfdCloseConnection(a3);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14002d8d0  mov     r11, rsp
0x14002d8d3  mov     [r11+8], rbx
0x14002d8d7  mov     [r11+10h], rsi
0x14002d8db  push    rbp
0x14002d8dc  push    rdi
0x14002d8dd  push    r14
0x14002d8df  mov     rbp, rsp
0x14002d8e2  sub     rsp, 60h
0x14002d8e6  mov     rbx, [r8+8]
0x14002d8ea  xor     eax, eax
0x14002d8ec  xorps   xmm0, xmm0
0x14002d8ef  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14002d8f3  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14002d8f7  mov     rdi, r8
0x14002d8fa  mov     r14, rdx
0x14002d8fd  movups  [rbp+var_30], xmm0
0x14002d901  mov     eax, [rbx+8]
0x14002d904  bt      eax, 8
0x14002d908  jnb     short loc_14002D93D
0x14002d90a  test    byte ptr cs:xmmword_1400875E0+1, 2
0x14002d911  jz      loc_14002D9BF
0x14002d917  mov     [r11-50h], r8
0x14002d91b  mov     edx, 17h
0x14002d920  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14002d927  mov     [r11-58h], rbx
0x14002d92b  mov     ecx, 409h
0x14002d930  xor     r9d, r9d
0x14002d933  call    WPP_SF_Dqq
0x14002d938  jmp     loc_14002D9BF
0x14002d93d  test    byte ptr cs:xmmword_1400875E0+1, 2
0x14002d944  jz      short loc_14002D96A
0x14002d946  mov     r9d, [r14+30h]
0x14002d94a  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14002d951  mov     edx, 18h
0x14002d956  mov     [rsp+60h+var_38], rdi
0x14002d95b  mov     ecx, 409h
0x14002d960  mov     [rsp+60h+var_40], rbx
0x14002d965  call    WPP_SF_Dqq
0x14002d96a  lock dec dword ptr [rbx+0B4h]
0x14002d971  cmp     dword ptr [r14+30h], 0
0x14002d976  jge     short loc_14002D9B0
0x14002d978  mov     r9d, 9
0x14002d97e  mov     r8, rbx
0x14002d981  mov     edx, 1F5Dh
0x14002d986  lea     ecx, [r9-7]
0x14002d98a  call    AFDETW_TRACEABORT
0x14002d98f  xor     r9d, r9d
0x14002d992  mov     dword ptr [rsp+60h+var_38], 1
0x14002d99a  xor     r8d, r8d
0x14002d99d  mov     [rsp+60h+var_40], 0
0x14002d9a6  xor     edx, edx
0x14002d9a8  mov     rcx, rdi
0x14002d9ab  call    AfdCommonDisconnectEventHandler
0x14002d9b0  mov     rcx, r14; Irp
0x14002d9b3  call    cs:__imp_IoFreeIrp
0x14002d9ba  nop     dword ptr [rax+rax+00h]
0x14002d9bf  mov     rax, ds:0FFFFF78000000008h
0x14002d9c9  lea     rdx, [rbp+LockHandle]; LockHandle
0x14002d9cd  lea     rcx, [rbx+38h]; SpinLock
0x14002d9d1  mov     [rdi+28h], rax
0x14002d9d5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002d9dc  nop     dword ptr [rax+rax+00h]
0x14002d9e1  test    dword ptr [rbx+8], 800h
0x14002d9e8  jz      short loc_14002DA2C
0x14002d9ea  lea     rcx, [rbp+LockHandle]; LockHandle
0x14002d9ee  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002d9f5  nop     dword ptr [rax+rax+00h]
0x14002d9fa  mov     rcx, rdi
0x14002d9fd  call    AfdAbortConnection
0x14002da02  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002da06  lock xadd [rdi+30h], rax
0x14002da0c  sub     rax, 1
0x14002da10  jg      loc_14002DC19
0x14002da16  test    rax, rax
0x14002da19  jnz     loc_14002DC12
0x14002da1f  mov     rcx, rdi
0x14002da22  call    AfdCloseConnection
0x14002da27  jmp     loc_14002DC19
0x14002da2c  lea     rax, [rbp+var_30]
0x14002da30  mov     qword ptr [rbp+var_30+8], rax
0x14002da34  lea     rax, [rbp+var_30]
0x14002da38  mov     qword ptr [rbp+var_30], rax
0x14002da3c  lea     r9, [rbp+var_30]
0x14002da40  mov     rdx, rdi
0x14002da43  lea     r8, [rbp+LockHandle]
0x14002da47  mov     rcx, rbx
0x14002da4a  call    AfdServiceSuperAccept
0x14002da4f  test    al, al
0x14002da51  jnz     loc_14002DBBC
0x14002da57  lea     rcx, [rbx+80h]
0x14002da5e  mov     rax, [rcx]
0x14002da61  cmp     rax, rcx
0x14002da64  jz      loc_14002DB52
0x14002da6a  cmp     [rax+8], rcx
0x14002da6e  jnz     loc_14002DC0B
0x14002da74  mov     rdx, [rax]
0x14002da77  cmp     [rdx+8], rax
0x14002da7b  jnz     loc_14002DC0B
0x14002da81  mov     [rcx], rdx
0x14002da84  lea     rsi, [rax-0A8h]
0x14002da8b  mov     [rdx+8], rcx
0x14002da8f  mov     qword ptr [rax], 0
0x14002da96  test    byte ptr cs:xmmword_1400875E0+1, 1
0x14002da9d  jz      short loc_14002DAB8
0x14002da9f  mov     edx, 19h
0x14002daa4  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14002daab  mov     ecx, 408h
0x14002dab0  mov     r9, rsi
0x14002dab3  call    WPP_SF_q
0x14002dab8  xor     r9d, r9d
0x14002dabb  lea     r8, [rbp+LockHandle]
0x14002dabf  mov     rdx, rdi
0x14002dac2  mov     rcx, rsi; Irp
0x14002dac5  call    AfdServiceWaitForListen
0x14002daca  test    eax, eax
0x14002dacc  jns     loc_14002DBBC
0x14002dad2  xor     r8d, r8d
0x14002dad5  lea     rdx, [rbp+LockHandle]
0x14002dad9  mov     rcx, rbx
0x14002dadc  call    AfdNotifySockIndicateEventsUnlock
0x14002dae1  xor     eax, eax
0x14002dae3  xchg    rax, [rsi+68h]
0x14002dae7  test    rax, rax
0x14002daea  jnz     short loc_14002DB0E
0x14002daec  lea     rcx, [rbp+Irql]; Irql
0x14002daf0  mov     [rbp+Irql], al
0x14002daf3  call    cs:__imp_IoAcquireCancelSpinLock
0x14002dafa  nop     dword ptr [rax+rax+00h]
0x14002daff  mov     cl, [rbp+Irql]; Irql
0x14002db02  call    cs:__imp_IoReleaseCancelSpinLock
0x14002db09  nop     dword ptr [rax+rax+00h]
0x14002db0e  mov     r9d, [rsi+30h]
0x14002db12  mov     r8, rbx
0x14002db15  mov     edx, 1851h
0x14002db1a  mov     ecx, 1
0x14002db1f  call    AFDETW_TRACEWAITLISTEN
0x14002db24  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14002db2a  mov     rcx, rsi; Irp
0x14002db2d  call    cs:__imp_IofCompleteRequest
0x14002db34  nop     dword ptr [rax+rax+00h]
0x14002db39  lea     rdx, [rbp+LockHandle]; LockHandle
0x14002db3d  lea     rcx, [rbx+38h]; SpinLock
0x14002db41  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002db48  nop     dword ptr [rax+rax+00h]
0x14002db4d  jmp     loc_14002DA3C
0x14002db52  lea     rcx, [rbx+60h]
0x14002db56  mov     rdx, [rcx+8]
0x14002db5a  cmp     [rdx], rcx
0x14002db5d  jnz     loc_14002DC0B
0x14002db63  lea     rax, [rdi+0B0h]
0x14002db6a  mov     esi, 80h
0x14002db6f  mov     [rax], rcx
0x14002db72  xor     r8d, r8d
0x14002db75  mov     [rax+8], rdx
0x14002db79  mov     [rdx], rax
0x14002db7c  mov     edx, esi
0x14002db7e  mov     [rcx+8], rax
0x14002db82  mov     rcx, rbx
0x14002db85  call    AfdIndicateEventSelectEvent
0x14002db8a  xor     r8d, r8d
0x14002db8d  mov     edx, esi
0x14002db8f  mov     rcx, rbx
0x14002db92  call    AfdNotifySockEventsChangedUnderLock
0x14002db97  xor     r8d, r8d
0x14002db9a  lea     r9, [rbp+LockHandle]
0x14002db9e  mov     edx, esi
0x14002dba0  call    AfdIndicatePollEvent
0x14002dba5  xor     r8d, r8d
0x14002dba8  mov     rcx, rbx
0x14002dbab  test    al, al
0x14002dbad  jnz     short loc_14002DBB5
0x14002dbaf  lea     rdx, [rbp+LockHandle]
0x14002dbb3  jmp     short loc_14002DBB7
0x14002dbb5  xor     edx, edx
0x14002dbb7  call    AfdNotifySockIndicateEventsUnlock
0x14002dbbc  mov     rcx, qword ptr [rbp+var_30]
0x14002dbc0  lea     rax, [rbp+var_30]
0x14002dbc4  cmp     rcx, rax
0x14002dbc7  jz      loc_14002DA02
0x14002dbcd  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14002dbd4  lea     rax, [rcx+0A8h]
0x14002dbdb  mov     r8, [rax]
0x14002dbde  cmp     [r8+8], rax
0x14002dbe2  jnz     short loc_14002DC0B
0x14002dbe4  mov     rdx, [rcx+0B0h]
0x14002dbeb  cmp     [rdx], rax
0x14002dbee  jnz     short loc_14002DC0B
0x14002dbf0  mov     [rdx], r8
0x14002dbf3  mov     [r8+8], rdx
0x14002dbf7  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14002dbfd  call    cs:__imp_IofCompleteRequest
0x14002dc04  nop     dword ptr [rax+rax+00h]
0x14002dc09  jmp     short loc_14002DBBC
0x14002dc0b  mov     ecx, 3
0x14002dc10  int     29h; Win8: RtlFailFast(ecx)
0x14002dc12  mov     ecx, 0Eh
0x14002dc17  int     29h; Win8: RtlFailFast(ecx)
0x14002dc19  lea     r11, [rsp+60h+var_s0]
0x14002dc1e  mov     eax, 0C0000016h
0x14002dc23  mov     rbx, [r11+20h]
0x14002dc27  mov     rsi, [r11+28h]
0x14002dc2b  mov     rsp, r11
0x14002dc2e  pop     r14
0x14002dc30  pop     rdi
0x14002dc31  pop     rbp
0x14002dc32  retn
```
