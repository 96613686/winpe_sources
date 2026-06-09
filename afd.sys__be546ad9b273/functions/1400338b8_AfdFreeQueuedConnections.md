# AfdFreeQueuedConnections

- ea: `0x1400338b8`
- end: `0x140033bf6`
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
- `0x14004cce0`

## callees

- `0x1400044fc`
- `0x1400049b0`
- `0x14001c708`
- `0x14002dc3c`
- `0x14002fd40`
- `0x1400338b8`
- `0x14004ddc4`
- `0x140058c48`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400339d1`
- `ntoskrnl!KfRaiseIrql` at `0x1400339d1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033a56`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033a8a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033aae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033a56`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033a8a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140033aae`
- `ntoskrnl!KeLowerIrql` at `0x140033a99`
- `ntoskrnl!KeLowerIrql` at `0x140033abd`
- `ntoskrnl!KeLowerIrql` at `0x140033a99`
- `ntoskrnl!KeLowerIrql` at `0x140033abd`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140033b1a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140033b1a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400339e7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140033a71`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400339e7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140033a71`
- `ntoskrnl!IofCompleteRequest` at `0x140033b2f`
- `ntoskrnl!IofCompleteRequest` at `0x140033b2f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033a46`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033b0b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033a46`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033b0b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140033911`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140033988`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400339c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140033911`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140033988`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400339c3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400338ea`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003393a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400339b1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400338ea`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003393a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400339b1`

## pseudocode

```c
__int64 __fastcall AfdFreeQueuedConnections(__int64 a1)
{
  KSPIN_LOCK *v1; // r14
  __int64 UnacceptedConnection; // rdi
  _QWORD **v4; // rsi
  _QWORD *v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rdx
  const signed __int32 *v8; // rdi
  KIRQL v9; // r15
  _QWORD **v10; // rsi
  _QWORD *v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  ULONG_PTR v14; // rdi
  __int64 i; // rax
  __int64 v16; // rdx
  PIRP v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  __int64 FreeConnection; // rax
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
    UnacceptedConnection = AfdGetUnacceptedConnection(a1);
    if ( !UnacceptedConnection )
      break;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( _bittest((const signed __int32 *)(UnacceptedConnection + 4), 0x1Du) )
      AfdSanAbortConnection(UnacceptedConnection);
    else
      AfdAbortConnection(UnacceptedConnection);
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
    v8 = (const signed __int32 *)(v5 - 22);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    if ( v5 == (_QWORD *)176 )
      break;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( _bittest(v8 + 1, 0x1Du) )
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
    for ( i = AfdGetFreeConnection(a1, 0, &Irp); ; i = AfdGetFreeConnection(a1, 0, &Irp) )
    {
      v19 = i;
      if ( !i )
        break;
      v17 = Irp;
      if ( Irp )
      {
        AfdCleanupSuperAccept((__int64)Irp, -1073741536);
        if ( v17->Cancel )
        {
          Irql = 0;
          IoAcquireCancelSpinLock(&Irql);
          IoReleaseCancelSpinLock(Irql);
        }
        IofCompleteRequest(v17, AfdPriorityBoost);
      }
      v18 = _InterlockedDecrement64((volatile signed __int64 *)(v19 + 48));
      if ( v18 <= 0 )
      {
        if ( v18 )
          __fastfail(0xEu);
        AfdCloseConnection(v19);
      }
    }
    if ( (*(_DWORD *)(a1 + 8) & 0x400000) != 0 )
    {
      while ( 1 )
      {
        LOBYTE(v16) = 1;
        FreeConnection = AfdGetFreeConnection(a1, v16, &Irp);
        if ( !FreeConnection )
          break;
        v20 = _InterlockedDecrement64((volatile signed __int64 *)(FreeConnection + 48));
        if ( v20 <= 0 )
        {
          if ( v20 )
            __fastfail(0xEu);
          AfdCloseConnection(FreeConnection);
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
0x1400338b8  mov     [rsp-28h+arg_10], rbx
0x1400338bd  push    rbp
0x1400338be  push    rsi
0x1400338bf  push    rdi
0x1400338c0  push    r14
0x1400338c2  push    r15
0x1400338c4  mov     rbp, rsp
0x1400338c7  sub     rsp, 40h
0x1400338cb  xor     eax, eax
0x1400338cd  lea     r14, [rcx+38h]
0x1400338d1  mov     rbx, rcx
0x1400338d4  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400338d8  xorps   xmm0, xmm0
0x1400338db  mov     [rbp+Irp], rax
0x1400338df  mov     rcx, r14; SpinLock
0x1400338e2  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400338e6  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400338ea  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400338f1  nop     dword ptr [rax+rax+00h]
0x1400338f6  mov     esi, 0AFD4h
0x1400338fb  jmp     short loc_140033946
0x1400338fd  mov     rcx, rbx
0x140033900  call    AfdGetUnacceptedConnection
0x140033905  mov     rdi, rax
0x140033908  test    rax, rax
0x14003390b  jz      short loc_14003394B
0x14003390d  lea     rcx, [rbp+LockHandle]; LockHandle
0x140033911  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140033918  nop     dword ptr [rax+rax+00h]
0x14003391d  bt      dword ptr [rdi+4], 1Dh
0x140033922  mov     rcx, rdi
0x140033925  jnb     short loc_14003392E
0x140033927  call    AfdSanAbortConnection
0x14003392c  jmp     short loc_140033933
0x14003392e  call    AfdAbortConnection
0x140033933  lea     rdx, [rbp+LockHandle]; LockHandle
0x140033937  mov     rcx, r14; SpinLock
0x14003393a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140033941  nop     dword ptr [rax+rax+00h]
0x140033946  cmp     [rbx], si
0x140033949  jz      short loc_1400338FD
0x14003394b  lea     rsi, [rbx+70h]
0x14003394f  mov     rax, [rsi]
0x140033952  cmp     rax, rsi
0x140033955  jz      short loc_1400339BF
0x140033957  mov     rcx, [rax]
0x14003395a  cmp     [rcx+8], rax
0x14003395e  jnz     loc_140033A7F
0x140033964  mov     rdx, [rax+8]
0x140033968  cmp     [rdx], rax
0x14003396b  jnz     loc_140033A7F
0x140033971  lea     rdi, [rax-0B0h]
0x140033978  mov     [rdx], rcx
0x14003397b  mov     [rcx+8], rdx
0x14003397f  test    rdi, rdi
0x140033982  jz      short loc_1400339BF
0x140033984  lea     rcx, [rbp+LockHandle]; LockHandle
0x140033988  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003398f  nop     dword ptr [rax+rax+00h]
0x140033994  bt      dword ptr [rdi+4], 1Dh
0x140033999  mov     rcx, rdi
0x14003399c  jnb     short loc_1400339A5
0x14003399e  call    AfdSanAbortConnection
0x1400339a3  jmp     short loc_1400339AA
0x1400339a5  call    AfdAbortConnection
0x1400339aa  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400339ae  mov     rcx, r14; SpinLock
0x1400339b1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400339b8  nop     dword ptr [rax+rax+00h]
0x1400339bd  jmp     short loc_14003394F
0x1400339bf  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400339c3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400339ca  nop     dword ptr [rax+rax+00h]
0x1400339cf  mov     cl, 2; NewIrql
0x1400339d1  call    cs:__imp_KfRaiseIrql
0x1400339d8  nop     dword ptr [rax+rax+00h]
0x1400339dd  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400339e1  mov     rcx, r14; SpinLock
0x1400339e4  mov     r15b, al
0x1400339e7  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400339ee  nop     dword ptr [rax+rax+00h]
0x1400339f3  mov     ecx, [rbx+8]
0x1400339f6  test    cl, 2
0x1400339f9  jz      loc_140033AAA
0x1400339ff  mov     ecx, [rbx+8]
0x140033a02  bt      ecx, 8
0x140033a06  jb      loc_140033AAA
0x140033a0c  lea     rsi, [rbx+90h]
0x140033a13  mov     rax, [rsi]
0x140033a16  cmp     rax, rsi
0x140033a19  jz      short loc_140033A86
0x140033a1b  mov     rcx, [rax]
0x140033a1e  cmp     [rcx+8], rax
0x140033a22  jnz     short loc_140033A7F
0x140033a24  mov     rdx, [rax+8]
0x140033a28  cmp     [rdx], rax
0x140033a2b  jnz     short loc_140033A7F
0x140033a2d  mov     [rdx], rcx
0x140033a30  xor     edi, edi
0x140033a32  mov     [rcx+8], rdx
0x140033a36  xchg    rdi, [rax-88h]
0x140033a3d  test    rdi, rdi
0x140033a40  jz      short loc_140033A13
0x140033a42  lea     rcx, [rdi+45h]; Irql
0x140033a46  call    cs:__imp_IoAcquireCancelSpinLock
0x140033a4d  nop     dword ptr [rax+rax+00h]
0x140033a52  lea     rcx, [rbp+LockHandle]; LockHandle
0x140033a56  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140033a5d  nop     dword ptr [rax+rax+00h]
0x140033a62  mov     rcx, rdi; BugCheckParameter1
0x140033a65  call    AfdCancelIrp
0x140033a6a  lea     rdx, [rbp+LockHandle]; LockHandle
0x140033a6e  mov     rcx, r14; SpinLock
0x140033a71  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140033a78  nop     dword ptr [rax+rax+00h]
0x140033a7d  jmp     short loc_140033A13
0x140033a7f  mov     ecx, 3
0x140033a84  int     29h; Win8: RtlFailFast(ecx)
0x140033a86  lea     rcx, [rbp+LockHandle]; LockHandle
0x140033a8a  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140033a91  nop     dword ptr [rax+rax+00h]
0x140033a96  mov     cl, r15b; NewIrql
0x140033a99  call    cs:__imp_KeLowerIrql
0x140033aa0  nop     dword ptr [rax+rax+00h]
0x140033aa5  jmp     loc_140033BB7
0x140033aaa  lea     rcx, [rbp+LockHandle]; LockHandle
0x140033aae  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140033ab5  nop     dword ptr [rax+rax+00h]
0x140033aba  mov     cl, r15b; NewIrql
0x140033abd  call    cs:__imp_KeLowerIrql
0x140033ac4  nop     dword ptr [rax+rax+00h]
0x140033ac9  mov     eax, [rbx+8]
0x140033acc  lea     r8, [rbp+Irp]
0x140033ad0  xor     edx, edx
0x140033ad2  mov     rcx, rbx
0x140033ad5  call    AfdGetFreeConnection
0x140033ada  or      r14, 0FFFFFFFFFFFFFFFFh
0x140033ade  lea     r15d, [r14+0Fh]
0x140033ae2  jmp     loc_140033B6B
0x140033ae7  mov     rsi, [rbp+Irp]
0x140033aeb  test    rsi, rsi
0x140033aee  jz      short loc_140033B3B
0x140033af0  mov     edx, 0C0000120h
0x140033af5  mov     rcx, rsi
0x140033af8  call    AfdCleanupSuperAccept
0x140033afd  cmp     byte ptr [rsi+44h], 0
0x140033b01  jz      short loc_140033B26
0x140033b03  lea     rcx, [rbp+Irql]; Irql
0x140033b07  mov     [rbp+Irql], 0
0x140033b0b  call    cs:__imp_IoAcquireCancelSpinLock
0x140033b12  nop     dword ptr [rax+rax+00h]
0x140033b17  mov     cl, [rbp+Irql]; Irql
0x140033b1a  call    cs:__imp_IoReleaseCancelSpinLock
0x140033b21  nop     dword ptr [rax+rax+00h]
0x140033b26  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140033b2c  mov     rcx, rsi; Irp
0x140033b2f  call    cs:__imp_IofCompleteRequest
0x140033b36  nop     dword ptr [rax+rax+00h]
0x140033b3b  mov     rax, r14
0x140033b3e  lock xadd [rdi+30h], rax
0x140033b44  add     rax, r14
0x140033b47  test    rax, rax
0x140033b4a  jg      short loc_140033B5D
0x140033b4c  jnz     short loc_140033B58
0x140033b4e  mov     rcx, rdi
0x140033b51  call    AfdCloseConnection
0x140033b56  jmp     short loc_140033B5D
0x140033b58  mov     rcx, r15
0x140033b5b  int     29h; Win8: RtlFailFast(ecx)
0x140033b5d  lea     r8, [rbp+Irp]
0x140033b61  xor     edx, edx
0x140033b63  mov     rcx, rbx
0x140033b66  call    AfdGetFreeConnection
0x140033b6b  mov     rdi, rax
0x140033b6e  test    rax, rax
0x140033b71  jnz     loc_140033AE7
0x140033b77  mov     eax, [rbx+8]
0x140033b7a  bt      eax, 16h
0x140033b7e  jb      short loc_140033BA4
0x140033b80  jmp     short loc_140033BB7
0x140033b82  mov     rcx, r14
0x140033b85  lock xadd [rax+30h], rcx
0x140033b8b  add     rcx, r14
0x140033b8e  test    rcx, rcx
0x140033b91  jg      short loc_140033BA4
0x140033b93  jnz     short loc_140033B9F
0x140033b95  mov     rcx, rax
0x140033b98  call    AfdCloseConnection
0x140033b9d  jmp     short loc_140033BA4
0x140033b9f  mov     rcx, r15
0x140033ba2  int     29h; Win8: RtlFailFast(ecx)
0x140033ba4  lea     r8, [rbp+Irp]
0x140033ba8  mov     dl, 1
0x140033baa  mov     rcx, rbx
0x140033bad  call    AfdGetFreeConnection
0x140033bb2  test    rax, rax
0x140033bb5  jnz     short loc_140033B82
0x140033bb7  mov     eax, [rbx+8]
0x140033bba  bt      eax, 8
0x140033bbe  jb      short loc_140033BE1
0x140033bc0  mov     dword ptr [rbx+0B0h], 0
0x140033bca  mov     eax, [rbx+8]
0x140033bcd  bt      eax, 16h
0x140033bd1  jnb     short loc_140033BE1
0x140033bd3  mov     rax, [rbx+118h]
0x140033bda  mov     dword ptr [rax+30h], 0
0x140033be1  mov     rbx, [rsp+40h+arg_10]
0x140033be9  add     rsp, 40h
0x140033bed  pop     r15
0x140033bef  pop     r14
0x140033bf1  pop     rdi
0x140033bf2  pop     rsi
0x140033bf3  pop     rbp
0x140033bf4  retn
```
