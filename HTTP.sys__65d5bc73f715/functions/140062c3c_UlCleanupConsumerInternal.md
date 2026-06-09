# UlCleanupConsumerInternal

- ea: `0x140062c3c`
- end: `0x1400630ea`
- name: `UlCleanupConsumerInternal`
- size: `1198`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x140062ad0`

## callees

- `0x14000a350`
- `0x140025918`
- `0x140041778`
- `0x140060ddc`
- `0x140060e04`
- `0x14006122c`
- `0x140061d30`
- `0x140062c3c`
- `0x14007109c`
- `0x140071678`
- `0x140071770`
- `0x14009620c`
- `0x1400a031c`
- `0x1400a0968`
- `0x1400a1808`
- `0x1400a19b8`
- `0x1400a38ac`
- `0x1400a9674`
- `0x1400b3d20`
- `0x1400d724c`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c575c`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140062eee`
- `ntoskrnl!IofCompleteRequest` at `0x140062eee`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140062e5b`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140063006`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140062e5b`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140063006`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140062e04`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140062e04`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140062cf4`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140062fe3`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140062cf4`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140062fe3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140062e67`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140062e8f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140063012`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140062e67`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140062e8f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140063012`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140062e83`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140062e83`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140062cd5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140062cd5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062cb9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062ce1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062fd0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062cb9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062ce1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062fd0`

## pseudocode

```c
__int64 __fastcall UlCleanupConsumerInternal(__int64 a1, ULONG_PTR a2, ULONG_PTR a3)
{
  __int64 i; // r14
  __int64 *j; // rax
  void *v8; // r14
  char v9; // r12
  char v10; // bl
  __int64 v11; // r8
  _QWORD *v12; // rcx
  __int64 v13; // rax
  IRP *v14; // rcx
  char v15; // bl
  int v16; // eax
  __int64 result; // rax
  _QWORD v18[2]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v19[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v21[2]; // [rsp+60h] [rbp-10h] BYREF

  v19[0] = v19;
  v19[1] = v19;
  v21[0] = v21;
  v21[1] = v21;
  v18[0] = v18;
  v18[1] = v18;
  v20[0] = v20;
  v20[1] = v20;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 123, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(a2 + 328) + 4144LL, 0);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a2 + 280));
  UlpFlushPendingConsumerIo(a3);
  *(_BYTE *)(a3 + 5) = 1;
  for ( i = 0; (unsigned int)i < (unsigned __int16)UlNumberOfLanes; i = (unsigned int)(i + 1) )
  {
    UlpEnumerateCouplings(
      *(_QWORD *)(*(_QWORD *)(a2 + 264) + 8 * i),
      40,
      (unsigned int)UlpFlushWaitForDisconnects,
      a3,
      (__int64)v18);
    UlpEnumerateCouplings(
      *(_QWORD *)(*(_QWORD *)(a2 + 264) + 8 * i),
      40,
      (unsigned int)UlpFlushCouplingRequests,
      a3,
      (__int64)v21);
  }
  UlpFlushConsumerCallbacks(a3, v20);
  UlpAttemptDetachFromRequestQueue(a3);
  for ( j = *(__int64 **)(a2 + 216); j != (__int64 *)(a2 + 216); j = (__int64 *)*j )
  {
    if ( !*((_BYTE *)j + 96) )
    {
      v8 = 0;
      v9 = 0;
      v10 = 0;
      goto LABEL_13;
    }
  }
  v10 = 1;
  if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_qZ(1046, 124, (unsigned int)WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a2, a2 + 160);
  RtlRemoveEntryHashTable(
    (PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(a2 + 328) + 4152LL),
    (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a2 + 176),
    0);
  *(_BYTE *)(a2 + 338) = 1;
  v9 = UlpAttemptRequestQueueCleanup(a2);
  UlpCleanupRequestQueueCouplings(a2);
  LOBYTE(v11) = 1;
  UlpFlushPendingRequests(a2, v19, v11);
  v8 = *(void **)(a2 + 136);
  *(_QWORD *)(a2 + 136) = 0;
  *(_DWORD *)(a2 + 248) = 4;
LABEL_13:
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a2 + 280));
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*(_QWORD *)(a2 + 328) + 4144LL, 0);
  KeLeaveCriticalRegion();
  while ( 1 )
  {
    v12 = (_QWORD *)v18[0];
    if ( (_QWORD *)v18[0] == v18 )
      break;
    if ( *(_QWORD **)(v18[0] + 8LL) != v18 || (v13 = *(_QWORD *)v18[0], *(_QWORD *)(*(_QWORD *)v18[0] + 8LL) != v18[0]) )
      __fastfail(3u);
    v18[0] = *(_QWORD *)v18[0];
    *(_QWORD *)(v13 + 8) = v18;
    *v12 = 0;
    v12[1] = 0;
    v14 = (IRP *)(v12 - 21);
    v14->IoStatus.Status = -1073741536;
    v14->IoStatus.Information = 0;
    IofCompleteRequest(v14, 0);
  }
  *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
  *(_DWORD *)(a1 + 48) = 259;
  *(_QWORD *)(a3 + 32) = a1;
  UlpInvokeFlushedConsumerCallbacks(v20);
  UlPurgeZombieConnections(*(_QWORD *)(a3 + 136), UlPurgeConsumer, a3);
  UlFlushCacheByConsumer(a3);
  if ( v10 )
    UlFlushCacheByRequestQueue(*(_QWORD *)(a3 + 136), a2);
  UlpAbortFlushedRequests(v21);
  if ( v10 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_d(1032, 137, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, 4);
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_d(1032, 138, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, 24);
    UlpRejectFlushedRequests(a2, v19, 24, a3);
    v15 = 0;
    if ( v8 )
      UlDeleteAutoServerSession(v8);
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a2 + 280));
    if ( !*(_BYTE *)(a2 + 336) )
    {
      v15 = 1;
      *(_BYTE *)(a2 + 336) = 1;
    }
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a2 + 280));
    KeLeaveCriticalRegion();
    if ( v15 )
      UlPcwDeleteInstance(*(_QWORD *)(a2 + 328), a2, 2);
  }
  else
  {
    UlpRedeliverFlushedRequests(a2, v19, a3);
  }
  if ( v9 )
  {
    v16 = _InterlockedDecrement((volatile signed __int32 *)a2);
    if ( UxDebugCheckRefcount && v16 <= -1 )
      UlBugCheckEx(3u, a2, 1u, v16);
    if ( !v16 )
      UlFreeRequestQueue((PVOID)a2);
  }
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)a3);
  if ( UxDebugCheckRefcount && (int)result <= -1 )
    UlBugCheckEx(3u, a3, 1u, (int)result);
  if ( !(_DWORD)result )
    result = UlConsumerCleanupCompletion(a3);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    return WPP_SF_(1032, 125, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140062c3c  push    rbp
0x140062c3e  push    rbx
0x140062c3f  push    rsi
0x140062c40  push    rdi
0x140062c41  push    r12
0x140062c43  push    r14
0x140062c45  push    r15
0x140062c47  mov     rbp, rsp
0x140062c4a  sub     rsp, 70h
0x140062c4e  lea     rax, [rbp+var_30]
0x140062c52  mov     rsi, r8
0x140062c55  mov     [rbp+var_30], rax
0x140062c59  mov     rdi, rdx
0x140062c5c  lea     rax, [rbp+var_30]
0x140062c60  mov     r15, rcx
0x140062c63  mov     [rbp+var_28], rax
0x140062c67  lea     rax, [rbp+var_10]
0x140062c6b  mov     [rbp+var_10], rax
0x140062c6f  lea     rax, [rbp+var_10]
0x140062c73  mov     [rbp+var_8], rax
0x140062c77  lea     rax, [rbp+var_40]
0x140062c7b  mov     [rbp+var_40], rax
0x140062c7f  lea     rax, [rbp+var_40]
0x140062c83  mov     [rbp+var_38], rax
0x140062c87  lea     rax, [rbp+var_20]
0x140062c8b  mov     [rbp+var_20], rax
0x140062c8f  lea     rax, [rbp+var_20]
0x140062c93  mov     [rbp+var_18], rax
0x140062c97  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140062c9e  jz      short loc_140062CB9
0x140062ca0  mov     edx, 7Bh ; '{'
0x140062ca5  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140062cac  mov     ecx, 408h
0x140062cb1  mov     r9, r15
0x140062cb4  call    WPP_SF_q
0x140062cb9  call    cs:__imp_KeEnterCriticalRegion
0x140062cc0  nop     dword ptr [rax+rax+00h]
0x140062cc5  mov     rcx, [rdi+148h]
0x140062ccc  xor     edx, edx
0x140062cce  add     rcx, 1030h
0x140062cd5  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140062cdc  nop     dword ptr [rax+rax+00h]
0x140062ce1  call    cs:__imp_KeEnterCriticalRegion
0x140062ce8  nop     dword ptr [rax+rax+00h]
0x140062ced  mov     rcx, [rdi+118h]
0x140062cf4  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x140062cfb  nop     dword ptr [rax+rax+00h]
0x140062d00  lea     r8, [rbp+var_30]
0x140062d04  mov     rcx, rsi; BugCheckParameter2
0x140062d07  lea     rdx, [rbp+var_40]
0x140062d0b  call    UlpFlushPendingConsumerIo
0x140062d10  xor     eax, eax
0x140062d12  mov     byte ptr [rsi+5], 1
0x140062d16  xor     r14d, r14d
0x140062d19  cmp     ax, cs:UlNumberOfLanes
0x140062d20  jnb     short loc_140062D81
0x140062d22  lea     r12d, [r14+28h]
0x140062d26  mov     rcx, [rdi+108h]
0x140062d2d  lea     rax, [rbp+var_40]
0x140062d31  mov     r9, rsi
0x140062d34  mov     [rsp+70h+var_50], rax
0x140062d39  lea     r8, UlpFlushWaitForDisconnects
0x140062d40  mov     rdx, r12
0x140062d43  mov     rcx, [rcx+r14*8]
0x140062d47  call    UlpEnumerateCouplings
0x140062d4c  mov     rcx, [rdi+108h]
0x140062d53  lea     rax, [rbp+var_10]
0x140062d57  mov     r9, rsi
0x140062d5a  mov     [rsp+70h+var_50], rax
0x140062d5f  lea     r8, UlpFlushCouplingRequests
0x140062d66  mov     rdx, r12
0x140062d69  mov     rcx, [rcx+r14*8]
0x140062d6d  call    UlpEnumerateCouplings
0x140062d72  movzx   eax, cs:UlNumberOfLanes
0x140062d79  inc     r14d
0x140062d7c  cmp     r14d, eax
0x140062d7f  jb      short loc_140062D26
0x140062d81  lea     rdx, [rbp+var_20]
0x140062d85  mov     rcx, rsi
0x140062d88  call    UlpFlushConsumerCallbacks
0x140062d8d  mov     rcx, rsi
0x140062d90  call    UlpAttemptDetachFromRequestQueue
0x140062d95  lea     rcx, [rdi+0D8h]
0x140062d9c  mov     rax, [rcx]
0x140062d9f  cmp     rax, rcx
0x140062da2  jz      short loc_140062DBC
0x140062da4  cmp     byte ptr [rax+60h], 0
0x140062da8  jz      short loc_140062DAF
0x140062daa  mov     rax, [rax]
0x140062dad  jmp     short loc_140062D9F
0x140062daf  xor     r14d, r14d
0x140062db2  xor     r12b, r12b
0x140062db5  xor     bl, bl
0x140062db7  jmp     loc_140062E54
0x140062dbc  mov     bl, 1
0x140062dbe  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x140062dc5  jz      short loc_140062DEC
0x140062dc7  lea     rax, [rdi+0A0h]
0x140062dce  mov     edx, 7Ch ; '|'
0x140062dd3  mov     ecx, 416h
0x140062dd8  mov     [rsp+70h+var_50], rax
0x140062ddd  mov     r9, rdi
0x140062de0  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140062de7  call    WPP_SF_qZ
0x140062dec  mov     rcx, [rdi+148h]
0x140062df3  lea     rdx, [rdi+0B0h]; Entry
0x140062dfa  add     rcx, 1038h; HashTable
0x140062e01  xor     r8d, r8d; Context
0x140062e04  call    cs:__imp_RtlRemoveEntryHashTable
0x140062e0b  nop     dword ptr [rax+rax+00h]
0x140062e10  mov     rcx, rdi
0x140062e13  mov     [rdi+152h], bl
0x140062e19  call    UlpAttemptRequestQueueCleanup
0x140062e1e  mov     rcx, rdi
0x140062e21  mov     r12b, al
0x140062e24  call    UlpCleanupRequestQueueCouplings
0x140062e29  mov     r8b, bl
0x140062e2c  lea     rdx, [rbp+var_30]
0x140062e30  mov     rcx, rdi
0x140062e33  call    UlpFlushPendingRequests
0x140062e38  mov     r14, [rdi+88h]
0x140062e3f  mov     qword ptr [rdi+88h], 0
0x140062e4a  mov     dword ptr [rdi+0F8h], 4
0x140062e54  mov     rcx, [rdi+118h]
0x140062e5b  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x140062e62  nop     dword ptr [rax+rax+00h]
0x140062e67  call    cs:__imp_KeLeaveCriticalRegion
0x140062e6e  nop     dword ptr [rax+rax+00h]
0x140062e73  mov     rcx, [rdi+148h]
0x140062e7a  xor     edx, edx
0x140062e7c  add     rcx, 1030h
0x140062e83  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140062e8a  nop     dword ptr [rax+rax+00h]
0x140062e8f  call    cs:__imp_KeLeaveCriticalRegion
0x140062e96  nop     dword ptr [rax+rax+00h]
0x140062e9b  mov     rcx, [rbp+var_40]
0x140062e9f  lea     rax, [rbp+var_40]
0x140062ea3  cmp     rcx, rax
0x140062ea6  jz      short loc_140062F03
0x140062ea8  lea     rax, [rbp+var_40]
0x140062eac  cmp     [rcx+8], rax
0x140062eb0  jnz     short loc_140062EFC
0x140062eb2  mov     rax, [rcx]
0x140062eb5  cmp     [rax+8], rcx
0x140062eb9  jnz     short loc_140062EFC
0x140062ebb  mov     [rbp+var_40], rax
0x140062ebf  lea     rdx, [rbp+var_40]
0x140062ec3  mov     [rax+8], rdx
0x140062ec7  xor     edx, edx; PriorityBoost
0x140062ec9  mov     qword ptr [rcx], 0
0x140062ed0  mov     qword ptr [rcx+8], 0
0x140062ed8  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x140062edf  mov     dword ptr [rcx+30h], 0C0000120h
0x140062ee6  mov     qword ptr [rcx+38h], 0
0x140062eee  call    cs:__imp_IofCompleteRequest
0x140062ef5  nop     dword ptr [rax+rax+00h]
0x140062efa  jmp     short loc_140062E9B
0x140062efc  mov     ecx, 3
0x140062f01  int     29h; Win8: RtlFailFast(ecx)
0x140062f03  mov     rax, [r15+0B8h]
0x140062f0a  lea     rcx, [rbp+var_20]
0x140062f0e  or      byte ptr [rax+3], 1
0x140062f12  mov     dword ptr [r15+30h], 103h
0x140062f1a  mov     [rsi+20h], r15
0x140062f1e  call    UlpInvokeFlushedConsumerCallbacks
0x140062f23  mov     rcx, [rsi+88h]
0x140062f2a  lea     rdx, UlPurgeConsumer
0x140062f31  mov     r8, rsi
0x140062f34  call    UlPurgeZombieConnections
0x140062f39  mov     rcx, rsi
0x140062f3c  call    UlFlushCacheByConsumer
0x140062f41  test    bl, bl
0x140062f43  jz      short loc_140062F54
0x140062f45  mov     rcx, [rsi+88h]
0x140062f4c  mov     rdx, rdi
0x140062f4f  call    UlFlushCacheByRequestQueue
0x140062f54  lea     rcx, [rbp+var_10]
0x140062f58  call    UlpAbortFlushedRequests
0x140062f5d  test    bl, bl
0x140062f5f  jz      loc_140063039
0x140062f65  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140062f6c  jz      short loc_140062F8A
0x140062f6e  mov     edx, 89h
0x140062f73  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140062f7a  mov     ecx, 408h
0x140062f7f  mov     r9d, 4
0x140062f85  call    WPP_SF_d
0x140062f8a  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140062f91  mov     ebx, 18h
0x140062f96  jz      short loc_140062FAF
0x140062f98  lea     edx, [rbx+72h]
0x140062f9b  mov     ecx, 408h
0x140062fa0  mov     r9d, ebx
0x140062fa3  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140062faa  call    WPP_SF_d
0x140062faf  mov     r9, rsi
0x140062fb2  lea     rdx, [rbp+var_30]
0x140062fb6  mov     r8d, ebx
0x140062fb9  mov     rcx, rdi
0x140062fbc  call    UlpRejectFlushedRequests
0x140062fc1  xor     bl, bl
0x140062fc3  test    r14, r14
0x140062fc6  jz      short loc_140062FD0
0x140062fc8  mov     rcx, r14
0x140062fcb  call    UlDeleteAutoServerSession
0x140062fd0  call    cs:__imp_KeEnterCriticalRegion
0x140062fd7  nop     dword ptr [rax+rax+00h]
0x140062fdc  mov     rcx, [rdi+118h]
0x140062fe3  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x140062fea  nop     dword ptr [rax+rax+00h]
0x140062fef  cmp     [rdi+150h], bl
0x140062ff5  jnz     short loc_140062FFF
0x140062ff7  mov     bl, 1
0x140062ff9  mov     [rdi+150h], bl
0x140062fff  mov     rcx, [rdi+118h]
0x140063006  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x14006300d  nop     dword ptr [rax+rax+00h]
0x140063012  call    cs:__imp_KeLeaveCriticalRegion
0x140063019  nop     dword ptr [rax+rax+00h]
0x14006301e  test    bl, bl
0x140063020  jz      short loc_140063048
0x140063022  mov     rcx, [rdi+148h]
0x140063029  mov     r8d, 2
0x14006302f  mov     rdx, rdi
0x140063032  call    UlPcwDeleteInstance
0x140063037  jmp     short loc_140063048
0x140063039  mov     r8, rsi
0x14006303c  lea     rdx, [rbp+var_30]
0x140063040  mov     rcx, rdi
0x140063043  call    UlpRedeliverFlushedRequests
0x140063048  or      ebx, 0FFFFFFFFh
0x14006304b  test    r12b, r12b
0x14006304e  jz      short loc_140063084
0x140063050  mov     eax, ebx
0x140063052  lock xadd [rdi], eax
0x140063056  add     eax, ebx
0x140063058  cmp     cs:UxDebugCheckRefcount, 0
0x14006305f  jz      short loc_140063078
0x140063061  cmp     eax, ebx
0x140063063  jg      short loc_140063078
0x140063065  movsxd  r9, eax; BugCheckParameter4
0x140063068  lea     r8d, [rbx+2]; BugCheckParameter3
0x14006306c  mov     rdx, rdi; BugCheckParameter2
0x14006306f  lea     ecx, [rbx+4]; BugCheckParameter1
0x140063072  call    UlBugCheckEx
0x140063078  test    eax, eax
0x14006307a  jnz     short loc_140063084
0x14006307c  mov     rcx, rdi; P
0x14006307f  call    UlFreeRequestQueue
0x140063084  mov     eax, ebx
0x140063086  lock xadd [rsi], eax
0x14006308a  add     eax, ebx
0x14006308c  cmp     cs:UxDebugCheckRefcount, 0
0x140063093  jz      short loc_1400630AF
0x140063095  cmp     eax, ebx
0x140063097  jg      short loc_1400630AF
0x140063099  mov     r8d, 1; BugCheckParameter3
0x14006309f  movsxd  r9, eax; BugCheckParameter4
0x1400630a2  mov     rdx, rsi; BugCheckParameter2
0x1400630a5  lea     ecx, [r8+2]; BugCheckParameter1
0x1400630a9  call    UlBugCheckEx
0x1400630af  test    eax, eax
0x1400630b1  jnz     short loc_1400630BB
0x1400630b3  mov     rcx, rsi
0x1400630b6  call    UlConsumerCleanupCompletion
0x1400630bb  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400630c2  jz      short loc_1400630DA
0x1400630c4  mov     edx, 7Dh ; '}'
0x1400630c9  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400630d0  mov     ecx, 408h
0x1400630d5  call    WPP_SF_
0x1400630da  add     rsp, 70h
0x1400630de  pop     r15
0x1400630e0  pop     r14
0x1400630e2  pop     r12
0x1400630e4  pop     rdi
0x1400630e5  pop     rsi
0x1400630e6  pop     rbx
0x1400630e7  pop     rbp
0x1400630e8  retn
```
