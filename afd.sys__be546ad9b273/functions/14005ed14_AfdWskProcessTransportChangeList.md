# AfdWskProcessTransportChangeList

- ea: `0x14005ed14`
- end: `0x14005eed5`
- name: `AfdWskProcessTransportChangeList`
- size: `449`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14005de50`
- `0x14005e090`

## callees

- `0x14005ed14`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005ee36`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005ee36`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005edd3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005edd3`
- `ntoskrnl!IofCompleteRequest` at `0x14005eeaa`
- `ntoskrnl!IofCompleteRequest` at `0x14005eeaa`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005ed5b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005ed5b`
- `NDIS!NdisReleaseRWLock` at `0x14005ee59`
- `NDIS!NdisReleaseRWLock` at `0x14005ee59`

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
0x14005ed14  mov     [rsp-18h+arg_8], rbx
0x14005ed19  mov     [rsp-18h+arg_10], rsi
0x14005ed1e  push    rbp
0x14005ed1f  push    rdi
0x14005ed20  push    r15
0x14005ed22  mov     rbp, rsp
0x14005ed25  sub     rsp, 50h
0x14005ed29  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005ed30  lea     rdx, [rbp+LockState]; LockState
0x14005ed34  xor     eax, eax
0x14005ed36  xorps   xmm0, xmm0
0x14005ed39  mov     word ptr [rbp+LockState.OldIrql], ax
0x14005ed3d  xor     r8d, r8d; Flags
0x14005ed40  mov     [rbp+LockState.Flags], al
0x14005ed43  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14005ed47  lea     rax, [rbp+var_30]
0x14005ed4b  mov     [rbp+var_28], rax
0x14005ed4f  lea     rax, [rbp+var_30]
0x14005ed53  mov     [rbp+var_30], rax
0x14005ed57  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14005ed5b  call    cs:__imp_NdisAcquireRWLockWrite
0x14005ed62  nop     dword ptr [rax+rax+00h]
0x14005ed67  mov     rbx, cs:AfdWskTransportListChangeReqList
0x14005ed6e  lea     r15, AfdWskTransportListChangeReqList
0x14005ed75  cmp     rbx, r15
0x14005ed78  jz      loc_14005EE4E
0x14005ed7e  mov     rcx, [rbx+18h]
0x14005ed82  xor     eax, eax
0x14005ed84  mov     rsi, [rbx]
0x14005ed87  xchg    rax, [rcx+68h]
0x14005ed8b  test    rax, rax
0x14005ed8e  jz      loc_14005EE42
0x14005ed94  mov     rdx, [rbx]
0x14005ed97  cmp     [rdx+8], rbx
0x14005ed9b  jnz     loc_14005EEB8
0x14005eda1  mov     r8, [rbx+8]
0x14005eda5  cmp     [r8], rbx
0x14005eda8  jnz     loc_14005EEB8
0x14005edae  mov     rdi, [rcx+0B8h]
0x14005edb5  mov     rcx, [rbx+10h]
0x14005edb9  add     rdi, 8
0x14005edbd  mov     [r8], rdx
0x14005edc0  add     rcx, 18h; SpinLock
0x14005edc4  mov     [rdx+8], r8
0x14005edc8  lea     rdx, [rbp+LockHandle]; LockHandle
0x14005edcc  mov     qword ptr [rbx], 0
0x14005edd3  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005edda  nop     dword ptr [rax+rax+00h]
0x14005eddf  mov     rcx, [rdi]
0x14005ede2  test    rcx, rcx
0x14005ede5  jz      short loc_14005EE2A
0x14005ede7  cmp     [rcx+8], rdi
0x14005edeb  jnz     loc_14005EEB8
0x14005edf1  mov     rax, [rdi+8]
0x14005edf5  cmp     [rax], rdi
0x14005edf8  jnz     loc_14005EEB8
0x14005edfe  mov     [rax], rcx
0x14005ee01  mov     [rcx+8], rax
0x14005ee05  lea     rcx, [rbp+var_30]
0x14005ee09  mov     rax, [rbp+var_28]
0x14005ee0d  cmp     [rax], rcx
0x14005ee10  jnz     loc_14005EEB8
0x14005ee16  mov     [rbx+8], rax
0x14005ee1a  lea     rcx, [rbp+var_30]
0x14005ee1e  mov     [rbx], rcx
0x14005ee21  mov     [rax], rbx
0x14005ee24  mov     [rbp+var_28], rbx
0x14005ee28  jmp     short loc_14005EE32
0x14005ee2a  mov     qword ptr [rdi+8], 0
0x14005ee32  lea     rcx, [rbp+LockHandle]; LockHandle
0x14005ee36  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005ee3d  nop     dword ptr [rax+rax+00h]
0x14005ee42  mov     rbx, rsi
0x14005ee45  cmp     rsi, r15
0x14005ee48  jnz     loc_14005ED7E
0x14005ee4e  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005ee55  lea     rdx, [rbp+LockState]; LockState
0x14005ee59  call    cs:__imp_NdisReleaseRWLock
0x14005ee60  nop     dword ptr [rax+rax+00h]
0x14005ee65  mov     rcx, [rbp+var_30]
0x14005ee69  lea     rax, [rbp+var_30]
0x14005ee6d  cmp     rcx, rax
0x14005ee70  jz      short loc_14005EEBF
0x14005ee72  lea     rax, [rbp+var_30]
0x14005ee76  cmp     [rcx+8], rax
0x14005ee7a  jnz     short loc_14005EEB8
0x14005ee7c  mov     rax, [rcx]
0x14005ee7f  cmp     [rax+8], rcx
0x14005ee83  jnz     short loc_14005EEB8
0x14005ee85  mov     [rbp+var_30], rax
0x14005ee89  lea     rdx, [rbp+var_30]
0x14005ee8d  mov     [rax+8], rdx
0x14005ee91  mov     rcx, [rcx+18h]; Irp
0x14005ee95  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14005ee9b  mov     dword ptr [rcx+30h], 0
0x14005eea2  mov     qword ptr [rcx+38h], 0
0x14005eeaa  call    cs:__imp_IofCompleteRequest
0x14005eeb1  nop     dword ptr [rax+rax+00h]
0x14005eeb6  jmp     short loc_14005EE65
0x14005eeb8  mov     ecx, 3
0x14005eebd  int     29h; Win8: RtlFailFast(ecx)
0x14005eebf  lea     r11, [rsp+50h+var_s0]
0x14005eec4  mov     rbx, [r11+28h]
0x14005eec8  mov     rsi, [r11+30h]
0x14005eecc  mov     rsp, r11
0x14005eecf  pop     r15
0x14005eed1  pop     rdi
0x14005eed2  pop     rbp
0x14005eed3  retn
```
