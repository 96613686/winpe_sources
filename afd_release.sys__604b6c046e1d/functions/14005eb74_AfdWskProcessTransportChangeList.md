# AfdWskProcessTransportChangeList

- ea: `0x14005eb74`
- end: `0x14005ed35`
- name: `AfdWskProcessTransportChangeList`
- size: `449`
- prototype: `__int64 **()`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14005dcb0`
- `0x14005def0`

## callees

- `0x14005eb74`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005ec96`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005ec96`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005ec33`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005ec33`
- `ntoskrnl!IofCompleteRequest` at `0x14005ed0a`
- `ntoskrnl!IofCompleteRequest` at `0x14005ed0a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005ebbb`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005ebbb`
- `NDIS!NdisReleaseRWLock` at `0x14005ecb9`
- `NDIS!NdisReleaseRWLock` at `0x14005ecb9`

## pseudocode

```c
__int64 **AfdWskProcessTransportChangeList()
{
  __int64 *v0; // rbx
  __int64 v1; // rcx
  __int64 *v2; // rsi
  __int64 *v3; // rdx
  __int64 **v4; // r8
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 *v7; // rdi
  __int64 v8; // rcx
  __int64 **v9; // rax
  __int64 **v10; // rax
  __int64 *v11; // rcx
  __int64 **result; // rax
  __int64 *v13; // rax
  IRP *v14; // rcx
  CCHAR v15; // dl
  __int64 *v16; // [rsp+20h] [rbp-30h] BYREF
  __int64 *v17; // [rsp+28h] [rbp-28h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-20h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+70h] [rbp+20h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v17 = (__int64 *)&v16;
  v16 = (__int64 *)&v16;
  memset(&LockHandle, 0, sizeof(LockHandle));
  NdisAcquireRWLockWrite(AfdTlTransportLock, &LockState, 0);
  v0 = (__int64 *)AfdWskTransportListChangeReqList;
  if ( (__int64 *)AfdWskTransportListChangeReqList != &AfdWskTransportListChangeReqList )
  {
    do
    {
      v1 = v0[3];
      v2 = (__int64 *)*v0;
      if ( _InterlockedExchange64((volatile __int64 *)(v1 + 104), 0) )
      {
        v3 = (__int64 *)*v0;
        if ( *(__int64 **)(*v0 + 8) != v0 || (v4 = (__int64 **)v0[1], *v4 != v0) )
LABEL_18:
          __fastfail(3u);
        v5 = *(_QWORD *)(v1 + 184);
        v6 = v0[2];
        v7 = (__int64 *)(v5 + 8);
        *v4 = v3;
        v3[1] = (__int64)v4;
        *v0 = 0;
        KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v6 + 24), &LockHandle);
        v8 = *v7;
        if ( *v7 )
        {
          if ( *(__int64 **)(v8 + 8) != v7 )
            goto LABEL_18;
          v9 = (__int64 **)v7[1];
          if ( *v9 != v7 )
            goto LABEL_18;
          *v9 = (__int64 *)v8;
          *(_QWORD *)(v8 + 8) = v9;
          v10 = (__int64 **)v17;
          if ( (__int64 **)*v17 != &v16 )
            goto LABEL_18;
          v0[1] = (__int64)v17;
          *v0 = (__int64)&v16;
          *v10 = v0;
          v17 = v0;
        }
        else
        {
          v7[1] = 0;
        }
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      }
      v0 = v2;
    }
    while ( v2 != &AfdWskTransportListChangeReqList );
  }
  NdisReleaseRWLock(AfdTlTransportLock, &LockState);
  while ( 1 )
  {
    v11 = v16;
    result = &v16;
    if ( v16 == (__int64 *)&v16 )
      return result;
    if ( (__int64 **)v16[1] != &v16 )
      goto LABEL_18;
    v13 = (__int64 *)*v16;
    if ( *(__int64 **)(*v16 + 8) != v16 )
      goto LABEL_18;
    v16 = (__int64 *)*v16;
    v13[1] = (__int64)&v16;
    v14 = (IRP *)v11[3];
    v15 = AfdPriorityBoost;
    v14->IoStatus.Status = 0;
    v14->IoStatus.Information = 0;
    IofCompleteRequest(v14, v15);
  }
}

```

## disassembly

```asm
0x14005eb74  mov     [rsp-18h+arg_8], rbx
0x14005eb79  mov     [rsp-18h+arg_10], rsi
0x14005eb7e  push    rbp
0x14005eb7f  push    rdi
0x14005eb80  push    r15
0x14005eb82  mov     rbp, rsp
0x14005eb85  sub     rsp, 50h
0x14005eb89  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005eb90  lea     rdx, [rbp+LockState]; LockState
0x14005eb94  xor     eax, eax
0x14005eb96  xorps   xmm0, xmm0
0x14005eb99  mov     word ptr [rbp+LockState.OldIrql], ax
0x14005eb9d  xor     r8d, r8d; Flags
0x14005eba0  mov     [rbp+LockState.Flags], al
0x14005eba3  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14005eba7  lea     rax, [rbp+var_30]
0x14005ebab  mov     [rbp+var_28], rax
0x14005ebaf  lea     rax, [rbp+var_30]
0x14005ebb3  mov     [rbp+var_30], rax
0x14005ebb7  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14005ebbb  call    cs:__imp_NdisAcquireRWLockWrite
0x14005ebc2  nop     dword ptr [rax+rax+00h]
0x14005ebc7  mov     rbx, cs:AfdWskTransportListChangeReqList
0x14005ebce  lea     r15, AfdWskTransportListChangeReqList
0x14005ebd5  cmp     rbx, r15
0x14005ebd8  jz      loc_14005ECAE
0x14005ebde  mov     rcx, [rbx+18h]
0x14005ebe2  xor     eax, eax
0x14005ebe4  mov     rsi, [rbx]
0x14005ebe7  xchg    rax, [rcx+68h]
0x14005ebeb  test    rax, rax
0x14005ebee  jz      loc_14005ECA2
0x14005ebf4  mov     rdx, [rbx]
0x14005ebf7  cmp     [rdx+8], rbx
0x14005ebfb  jnz     loc_14005ED18
0x14005ec01  mov     r8, [rbx+8]
0x14005ec05  cmp     [r8], rbx
0x14005ec08  jnz     loc_14005ED18
0x14005ec0e  mov     rdi, [rcx+0B8h]
0x14005ec15  mov     rcx, [rbx+10h]
0x14005ec19  add     rdi, 8
0x14005ec1d  mov     [r8], rdx
0x14005ec20  add     rcx, 18h; SpinLock
0x14005ec24  mov     [rdx+8], r8
0x14005ec28  lea     rdx, [rbp+LockHandle]; LockHandle
0x14005ec2c  mov     qword ptr [rbx], 0
0x14005ec33  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005ec3a  nop     dword ptr [rax+rax+00h]
0x14005ec3f  mov     rcx, [rdi]
0x14005ec42  test    rcx, rcx
0x14005ec45  jz      short loc_14005EC8A
0x14005ec47  cmp     [rcx+8], rdi
0x14005ec4b  jnz     loc_14005ED18
0x14005ec51  mov     rax, [rdi+8]
0x14005ec55  cmp     [rax], rdi
0x14005ec58  jnz     loc_14005ED18
0x14005ec5e  mov     [rax], rcx
0x14005ec61  mov     [rcx+8], rax
0x14005ec65  lea     rcx, [rbp+var_30]
0x14005ec69  mov     rax, [rbp+var_28]
0x14005ec6d  cmp     [rax], rcx
0x14005ec70  jnz     loc_14005ED18
0x14005ec76  mov     [rbx+8], rax
0x14005ec7a  lea     rcx, [rbp+var_30]
0x14005ec7e  mov     [rbx], rcx
0x14005ec81  mov     [rax], rbx
0x14005ec84  mov     [rbp+var_28], rbx
0x14005ec88  jmp     short loc_14005EC92
0x14005ec8a  mov     qword ptr [rdi+8], 0
0x14005ec92  lea     rcx, [rbp+LockHandle]; LockHandle
0x14005ec96  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005ec9d  nop     dword ptr [rax+rax+00h]
0x14005eca2  mov     rbx, rsi
0x14005eca5  cmp     rsi, r15
0x14005eca8  jnz     loc_14005EBDE
0x14005ecae  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005ecb5  lea     rdx, [rbp+LockState]; LockState
0x14005ecb9  call    cs:__imp_NdisReleaseRWLock
0x14005ecc0  nop     dword ptr [rax+rax+00h]
0x14005ecc5  mov     rcx, [rbp+var_30]
0x14005ecc9  lea     rax, [rbp+var_30]
0x14005eccd  cmp     rcx, rax
0x14005ecd0  jz      short loc_14005ED1F
0x14005ecd2  lea     rax, [rbp+var_30]
0x14005ecd6  cmp     [rcx+8], rax
0x14005ecda  jnz     short loc_14005ED18
0x14005ecdc  mov     rax, [rcx]
0x14005ecdf  cmp     [rax+8], rcx
0x14005ece3  jnz     short loc_14005ED18
0x14005ece5  mov     [rbp+var_30], rax
0x14005ece9  lea     rdx, [rbp+var_30]
0x14005eced  mov     [rax+8], rdx
0x14005ecf1  mov     rcx, [rcx+18h]; Irp
0x14005ecf5  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14005ecfb  mov     dword ptr [rcx+30h], 0
0x14005ed02  mov     qword ptr [rcx+38h], 0
0x14005ed0a  call    cs:__imp_IofCompleteRequest
0x14005ed11  nop     dword ptr [rax+rax+00h]
0x14005ed16  jmp     short loc_14005ECC5
0x14005ed18  mov     ecx, 3
0x14005ed1d  int     29h; Win8: RtlFailFast(ecx)
0x14005ed1f  lea     r11, [rsp+50h+var_s0]
0x14005ed24  mov     rbx, [r11+28h]
0x14005ed28  mov     rsi, [r11+30h]
0x14005ed2c  mov     rsp, r11
0x14005ed2f  pop     r15
0x14005ed31  pop     rdi
0x14005ed32  pop     rbp
0x14005ed33  retn
```
