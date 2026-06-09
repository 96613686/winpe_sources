# AfdFreeQueuedConnections

- ea: `0x140033898`
- end: `0x140033bd6`
- name: `AfdFreeQueuedConnections`
- size: `830`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140014934`
- `0x140020970`
- `0x14002e9c0`
- `0x14004cc40`

## callees

- `0x1400044fc`
- `0x1400049b0`
- `0x14001c708`
- `0x14002dc3c`
- `0x14002fd20`
- `0x140033898`
- `0x14004dd24`
- `0x140058aa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400339b1`
- `ntoskrnl!KfRaiseIrql` at `0x1400339b1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033a36`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033a6a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033a8e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033a36`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033a6a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033a8e`
- `ntoskrnl!KeLowerIrql` at `0x140033a79`
- `ntoskrnl!KeLowerIrql` at `0x140033a9d`
- `ntoskrnl!KeLowerIrql` at `0x140033a79`
- `ntoskrnl!KeLowerIrql` at `0x140033a9d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140033afa`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140033afa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400339c7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140033a51`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400339c7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140033a51`
- `ntoskrnl!IofCompleteRequest` at `0x140033b0f`
- `ntoskrnl!IofCompleteRequest` at `0x140033b0f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033a26`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033aeb`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033a26`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033aeb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400338f1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140033968`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400339a3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400338f1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140033968`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400339a3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400338ca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003391a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140033991`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400338ca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003391a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140033991`

## pseudocode

```c
__int64 __fastcall AfdFreeQueuedConnections(__int64 a1)
{
  KSPIN_LOCK *v1; // r14
  const signed __int32 *UnacceptedConnection; // rdi
  _QWORD **v4; // rsi
  _QWORD *v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rdx
  __int64 v8; // rdi
  KIRQL v9; // r15
  _QWORD **v10; // rsi
  _QWORD *v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  ULONG_PTR v14; // rdi
  PSLIST_ENTRY i; // rax
  PIRP v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rcx
  PSLIST_ENTRY FreeConnection; // rax
  __int64 result; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-20h] BYREF
  KIRQL Irql; // [rsp+70h] [rbp+30h] BYREF
  PIRP Irp; // [rsp+78h] [rbp+38h] BYREF

  v1 = (KSPIN_LOCK *)(a1 + 56);
  Irp = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
  while ( *(_WORD *)a1 == 0xAFD4 )
  {
    UnacceptedConnection = (const signed __int32 *)AfdGetUnacceptedConnection(a1);
    if ( !UnacceptedConnection )
      break;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( _bittest(UnacceptedConnection + 1, 0x1Du) )
      AfdSanAbortConnection(UnacceptedConnection);
    else
      AfdAbortConnection((__int64)UnacceptedConnection);
    KeAcquireInStackQueuedSpinLock(v1, &LockHandle);
  }
  v4 = (_QWORD **)(a1 + 112);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    v6 = *v5;
    if ( *(_QWORD **)(*v5 + 8LL) != v5 || (v7 = (_QWORD *)v5[1], (_QWORD *)*v7 != v5) )
LABEL_25:
      __fastfail(3u);
    v8 = (__int64)(v5 - 22);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    if ( v5 == (_QWORD *)176 )
      break;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( _bittest((const signed __int32 *)(v8 + 4), 0x1Du) )
      AfdSanAbortConnection(v8);
    else
      AfdAbortConnection(v8);
    KeAcquireInStackQueuedSpinLock(v1, &LockHandle);
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v9 = KfRaiseIrql(2u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel(v1, &LockHandle);
  if ( (*(_DWORD *)(a1 + 8) & 2) == 0 || (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
  {
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    KeLowerIrql(v9);
    for ( i = AfdGetFreeConnection(a1, 0, (__int64 *)&Irp); ; i = AfdGetFreeConnection(a1, 0, (__int64 *)&Irp) )
    {
      v18 = (__int64)i;
      if ( !i )
        break;
      v16 = Irp;
      if ( Irp )
      {
        AfdCleanupSuperAccept((__int64)Irp, -1073741536);
        if ( v16->Cancel )
        {
          Irql = 0;
          IoAcquireCancelSpinLock(&Irql);
          IoReleaseCancelSpinLock(Irql);
        }
        IofCompleteRequest(v16, AfdPriorityBoost);
      }
      v17 = _InterlockedDecrement64((volatile signed __int64 *)(v18 + 48));
      if ( v17 <= 0 )
      {
        if ( v17 )
          __fastfail(0xEu);
        AfdCloseConnection(v18);
      }
    }
    if ( (*(_DWORD *)(a1 + 8) & 0x400000) != 0 )
    {
      while ( 1 )
      {
        FreeConnection = AfdGetFreeConnection(a1, 1, (__int64 *)&Irp);
        if ( !FreeConnection )
          break;
        v19 = _InterlockedDecrement64((volatile signed __int64 *)&FreeConnection[3]);
        if ( v19 <= 0 )
        {
          if ( v19 )
            __fastfail(0xEu);
          AfdCloseConnection((__int64)FreeConnection);
        }
      }
    }
  }
  else
  {
    v10 = (_QWORD **)(a1 + 144);
    while ( 1 )
    {
      v11 = *v10;
      if ( *v10 == v10 )
        break;
      v12 = *v11;
      if ( *(_QWORD **)(*v11 + 8LL) != v11 )
        goto LABEL_25;
      v13 = (_QWORD *)v11[1];
      if ( (_QWORD *)*v13 != v11 )
        goto LABEL_25;
      *v13 = v12;
      *(_QWORD *)(v12 + 8) = v13;
      v14 = _InterlockedExchange64(v11 - 17, 0);
      if ( v14 )
      {
        IoAcquireCancelSpinLock((PKIRQL)(v14 + 69));
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        AfdCancelIrp(v14);
        KeAcquireInStackQueuedSpinLockAtDpcLevel(v1, &LockHandle);
      }
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    KeLowerIrql(v9);
  }
  result = *(unsigned int *)(a1 + 8);
  if ( (result & 0x100) == 0 )
  {
    *(_DWORD *)(a1 + 176) = 0;
    result = *(unsigned int *)(a1 + 8);
    if ( (result & 0x400000) != 0 )
    {
      result = *(_QWORD *)(a1 + 280);
      *(_DWORD *)(result + 48) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140033898  mov     [rsp-28h+arg_10], rbx
0x14003389d  push    rbp
0x14003389e  push    rsi
0x14003389f  push    rdi
0x1400338a0  push    r14
0x1400338a2  push    r15
0x1400338a4  mov     rbp, rsp
0x1400338a7  sub     rsp, 40h
0x1400338ab  xor     eax, eax
0x1400338ad  lea     r14, [rcx+38h]
0x1400338b1  mov     rbx, rcx
0x1400338b4  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400338b8  xorps   xmm0, xmm0
0x1400338bb  mov     [rbp+Irp], rax
0x1400338bf  mov     rcx, r14; SpinLock
0x1400338c2  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400338c6  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400338ca  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400338d1  nop     dword ptr [rax+rax+00h]
0x1400338d6  mov     esi, 0AFD4h
0x1400338db  jmp     short loc_140033926
0x1400338dd  mov     rcx, rbx
0x1400338e0  call    AfdGetUnacceptedConnection
0x1400338e5  mov     rdi, rax
0x1400338e8  test    rax, rax
0x1400338eb  jz      short loc_14003392B
0x1400338ed  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400338f1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400338f8  nop     dword ptr [rax+rax+00h]
0x1400338fd  bt      dword ptr [rdi+4], 1Dh
0x140033902  mov     rcx, rdi
0x140033905  jnb     short loc_14003390E
0x140033907  call    AfdSanAbortConnection
0x14003390c  jmp     short loc_140033913
0x14003390e  call    AfdAbortConnection
0x140033913  lea     rdx, [rbp+LockHandle]; LockHandle
0x140033917  mov     rcx, r14; SpinLock
0x14003391a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140033921  nop     dword ptr [rax+rax+00h]
0x140033926  cmp     [rbx], si
0x140033929  jz      short loc_1400338DD
0x14003392b  lea     rsi, [rbx+70h]
0x14003392f  mov     rax, [rsi]
0x140033932  cmp     rax, rsi
0x140033935  jz      short loc_14003399F
0x140033937  mov     rcx, [rax]
0x14003393a  cmp     [rcx+8], rax
0x14003393e  jnz     loc_140033A5F
0x140033944  mov     rdx, [rax+8]
0x140033948  cmp     [rdx], rax
0x14003394b  jnz     loc_140033A5F
0x140033951  lea     rdi, [rax-0B0h]
0x140033958  mov     [rdx], rcx
0x14003395b  mov     [rcx+8], rdx
0x14003395f  test    rdi, rdi
0x140033962  jz      short loc_14003399F
0x140033964  lea     rcx, [rbp+LockHandle]; LockHandle
0x140033968  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003396f  nop     dword ptr [rax+rax+00h]
0x140033974  bt      dword ptr [rdi+4], 1Dh
0x140033979  mov     rcx, rdi
0x14003397c  jnb     short loc_140033985
0x14003397e  call    AfdSanAbortConnection
0x140033983  jmp     short loc_14003398A
0x140033985  call    AfdAbortConnection
0x14003398a  lea     rdx, [rbp+LockHandle]; LockHandle
0x14003398e  mov     rcx, r14; SpinLock
0x140033991  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140033998  nop     dword ptr [rax+rax+00h]
0x14003399d  jmp     short loc_14003392F
0x14003399f  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400339a3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400339aa  nop     dword ptr [rax+rax+00h]
0x1400339af  mov     cl, 2; NewIrql
0x1400339b1  call    cs:__imp_KfRaiseIrql
0x1400339b8  nop     dword ptr [rax+rax+00h]
0x1400339bd  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400339c1  mov     rcx, r14; SpinLock
0x1400339c4  mov     r15b, al
0x1400339c7  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400339ce  nop     dword ptr [rax+rax+00h]
0x1400339d3  mov     ecx, [rbx+8]
0x1400339d6  test    cl, 2
0x1400339d9  jz      loc_140033A8A
0x1400339df  mov     ecx, [rbx+8]
0x1400339e2  bt      ecx, 8
0x1400339e6  jb      loc_140033A8A
0x1400339ec  lea     rsi, [rbx+90h]
0x1400339f3  mov     rax, [rsi]
0x1400339f6  cmp     rax, rsi
0x1400339f9  jz      short loc_140033A66
0x1400339fb  mov     rcx, [rax]
0x1400339fe  cmp     [rcx+8], rax
0x140033a02  jnz     short loc_140033A5F
0x140033a04  mov     rdx, [rax+8]
0x140033a08  cmp     [rdx], rax
0x140033a0b  jnz     short loc_140033A5F
0x140033a0d  mov     [rdx], rcx
0x140033a10  xor     edi, edi
0x140033a12  mov     [rcx+8], rdx
0x140033a16  xchg    rdi, [rax-88h]
0x140033a1d  test    rdi, rdi
0x140033a20  jz      short loc_1400339F3
0x140033a22  lea     rcx, [rdi+45h]; Irql
0x140033a26  call    cs:__imp_IoAcquireCancelSpinLock
0x140033a2d  nop     dword ptr [rax+rax+00h]
0x140033a32  lea     rcx, [rbp+LockHandle]; LockHandle
0x140033a36  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140033a3d  nop     dword ptr [rax+rax+00h]
0x140033a42  mov     rcx, rdi; BugCheckParameter1
0x140033a45  call    AfdCancelIrp
0x140033a4a  lea     rdx, [rbp+LockHandle]; LockHandle
0x140033a4e  mov     rcx, r14; SpinLock
0x140033a51  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140033a58  nop     dword ptr [rax+rax+00h]
0x140033a5d  jmp     short loc_1400339F3
0x140033a5f  mov     ecx, 3
0x140033a64  int     29h; Win8: RtlFailFast(ecx)
0x140033a66  lea     rcx, [rbp+LockHandle]; LockHandle
0x140033a6a  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140033a71  nop     dword ptr [rax+rax+00h]
0x140033a76  mov     cl, r15b; NewIrql
0x140033a79  call    cs:__imp_KeLowerIrql
0x140033a80  nop     dword ptr [rax+rax+00h]
0x140033a85  jmp     loc_140033B97
0x140033a8a  lea     rcx, [rbp+LockHandle]; LockHandle
0x140033a8e  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140033a95  nop     dword ptr [rax+rax+00h]
0x140033a9a  mov     cl, r15b; NewIrql
0x140033a9d  call    cs:__imp_KeLowerIrql
0x140033aa4  nop     dword ptr [rax+rax+00h]
0x140033aa9  mov     eax, [rbx+8]
0x140033aac  lea     r8, [rbp+Irp]
0x140033ab0  xor     edx, edx
0x140033ab2  mov     rcx, rbx
0x140033ab5  call    AfdGetFreeConnection
0x140033aba  or      r14, 0FFFFFFFFFFFFFFFFh
0x140033abe  lea     r15d, [r14+0Fh]
0x140033ac2  jmp     loc_140033B4B
0x140033ac7  mov     rsi, [rbp+Irp]
0x140033acb  test    rsi, rsi
0x140033ace  jz      short loc_140033B1B
0x140033ad0  mov     edx, 0C0000120h
0x140033ad5  mov     rcx, rsi
0x140033ad8  call    AfdCleanupSuperAccept
0x140033add  cmp     byte ptr [rsi+44h], 0
0x140033ae1  jz      short loc_140033B06
0x140033ae3  lea     rcx, [rbp+Irql]; Irql
0x140033ae7  mov     [rbp+Irql], 0
0x140033aeb  call    cs:__imp_IoAcquireCancelSpinLock
0x140033af2  nop     dword ptr [rax+rax+00h]
0x140033af7  mov     cl, [rbp+Irql]; Irql
0x140033afa  call    cs:__imp_IoReleaseCancelSpinLock
0x140033b01  nop     dword ptr [rax+rax+00h]
0x140033b06  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140033b0c  mov     rcx, rsi; Irp
0x140033b0f  call    cs:__imp_IofCompleteRequest
0x140033b16  nop     dword ptr [rax+rax+00h]
0x140033b1b  mov     rax, r14
0x140033b1e  lock xadd [rdi+30h], rax
0x140033b24  add     rax, r14
0x140033b27  test    rax, rax
0x140033b2a  jg      short loc_140033B3D
0x140033b2c  jnz     short loc_140033B38
0x140033b2e  mov     rcx, rdi
0x140033b31  call    AfdCloseConnection
0x140033b36  jmp     short loc_140033B3D
0x140033b38  mov     rcx, r15
0x140033b3b  int     29h; Win8: RtlFailFast(ecx)
0x140033b3d  lea     r8, [rbp+Irp]
0x140033b41  xor     edx, edx
0x140033b43  mov     rcx, rbx
0x140033b46  call    AfdGetFreeConnection
0x140033b4b  mov     rdi, rax
0x140033b4e  test    rax, rax
0x140033b51  jnz     loc_140033AC7
0x140033b57  mov     eax, [rbx+8]
0x140033b5a  bt      eax, 16h
0x140033b5e  jb      short loc_140033B84
0x140033b60  jmp     short loc_140033B97
0x140033b62  mov     rcx, r14
0x140033b65  lock xadd [rax+30h], rcx
0x140033b6b  add     rcx, r14
0x140033b6e  test    rcx, rcx
0x140033b71  jg      short loc_140033B84
0x140033b73  jnz     short loc_140033B7F
0x140033b75  mov     rcx, rax
0x140033b78  call    AfdCloseConnection
0x140033b7d  jmp     short loc_140033B84
0x140033b7f  mov     rcx, r15
0x140033b82  int     29h; Win8: RtlFailFast(ecx)
0x140033b84  lea     r8, [rbp+Irp]
0x140033b88  mov     dl, 1
0x140033b8a  mov     rcx, rbx
0x140033b8d  call    AfdGetFreeConnection
0x140033b92  test    rax, rax
0x140033b95  jnz     short loc_140033B62
0x140033b97  mov     eax, [rbx+8]
0x140033b9a  bt      eax, 8
0x140033b9e  jb      short loc_140033BC1
0x140033ba0  mov     dword ptr [rbx+0B0h], 0
0x140033baa  mov     eax, [rbx+8]
0x140033bad  bt      eax, 16h
0x140033bb1  jnb     short loc_140033BC1
0x140033bb3  mov     rax, [rbx+118h]
0x140033bba  mov     dword ptr [rax+30h], 0
0x140033bc1  mov     rbx, [rsp+40h+arg_10]
0x140033bc9  add     rsp, 40h
0x140033bcd  pop     r15
0x140033bcf  pop     r14
0x140033bd1  pop     rdi
0x140033bd2  pop     rsi
0x140033bd3  pop     rbp
0x140033bd4  retn
```
