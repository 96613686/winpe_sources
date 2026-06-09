# UaspCompleteWorkItem

- ea: `0x140005358`
- end: `0x140005488`
- name: `UaspCompleteWorkItem`
- size: `304`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400062d0`
- `0x140006690`
- `0x140007f80`
- `0x14000a230`
- `0x14000c2e0`

## callees

- `0x140005358`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000542f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000542f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005409`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005409`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400053bc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400053bc`
- `ntoskrnl!IoQueueWorkItem` at `0x140005451`
- `ntoskrnl!IoQueueWorkItem` at `0x140005451`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140005464`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140005464`
- `storport!StorPortNotification` at `0x1400053a4`
- `storport!StorPortNotification` at `0x1400053a4`

## pseudocode

```c
void __fastcall UaspCompleteWorkItem(__int64 *P, int a2)
{
  __int64 v2; // r8
  __int64 v3; // rbx
  _QWORD **v5; // rdx
  PVOID *v6; // rcx
  __int64 v7; // rcx
  PIO_WORKITEM_ROUTINE *v8; // rsi
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v2 = P[1];
  v3 = *P;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( v2 )
  {
    if ( a2 < 0 )
      *(_BYTE *)(v2 + 3) = (a2 == -2147483631) + 4;
    else
      *(_BYTE *)(v2 + 3) = 1;
    StorPortNotification(0, v3, v2);
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 128), &LockHandle);
  v5 = (_QWORD **)P[4];
  if ( v5[1] != P + 4 || (v6 = (PVOID *)P[5], *v6 != P + 4) )
    __fastfail(3u);
  *v6 = v5;
  v5[1] = v6;
  v7 = *(_QWORD *)(v3 + 1352);
  v8 = (PIO_WORKITEM_ROUTINE *)(v7 - 32);
  if ( v7 == v3 + 1352 )
    v8 = 0;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( P == (__int64 *)(v3 + 1304) )
    *(_BYTE *)(v3 + 1296) = 0;
  else
    ExFreePoolWithTag(P, 0);
  if ( v8 )
    IoQueueWorkItem(*(PIO_WORKITEM *)(v3 + 200), v8[3], CriticalWorkQueue, v8);
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v3 + 1288));
}

```

## disassembly

```asm
0x140005358  mov     [rsp+arg_0], rbx
0x14000535d  mov     [rsp+arg_8], rsi
0x140005362  push    rdi
0x140005363  sub     rsp, 40h
0x140005367  mov     r8, [rcx+8]
0x14000536b  xor     eax, eax
0x14000536d  mov     rbx, [rcx]
0x140005370  xorps   xmm0, xmm0
0x140005373  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140005378  mov     rdi, rcx
0x14000537b  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140005380  test    r8, r8
0x140005383  jz      short loc_1400053B0
0x140005385  test    edx, edx
0x140005387  js      short loc_140005390
0x140005389  mov     byte ptr [r8+3], 1
0x14000538e  jmp     short loc_14000539F
0x140005390  cmp     edx, 80000011h
0x140005396  setz    al
0x140005399  add     al, 4
0x14000539b  mov     [r8+3], al
0x14000539f  mov     rdx, rbx
0x1400053a2  xor     ecx, ecx
0x1400053a4  call    cs:__imp_StorPortNotification
0x1400053ab  nop     dword ptr [rax+rax+00h]
0x1400053b0  lea     rcx, [rbx+80h]; SpinLock
0x1400053b7  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x1400053bc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400053c3  nop     dword ptr [rax+rax+00h]
0x1400053c8  lea     rax, [rdi+20h]
0x1400053cc  mov     rdx, [rax]
0x1400053cf  cmp     [rdx+8], rax
0x1400053d3  jnz     loc_140005481
0x1400053d9  mov     rcx, [rax+8]
0x1400053dd  cmp     [rcx], rax
0x1400053e0  jnz     loc_140005481
0x1400053e6  mov     [rcx], rdx
0x1400053e9  xor     eax, eax
0x1400053eb  mov     [rdx+8], rcx
0x1400053ef  lea     rdx, [rbx+548h]
0x1400053f6  mov     rcx, [rdx]
0x1400053f9  cmp     rcx, rdx
0x1400053fc  lea     rsi, [rcx-20h]
0x140005400  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140005405  cmovz   rsi, rax
0x140005409  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140005410  nop     dword ptr [rax+rax+00h]
0x140005415  lea     rax, [rbx+518h]
0x14000541c  cmp     rdi, rax
0x14000541f  jnz     short loc_14000542A
0x140005421  mov     byte ptr [rbx+510h], 0
0x140005428  jmp     short loc_14000543B
0x14000542a  xor     edx, edx; Tag
0x14000542c  mov     rcx, rdi; P
0x14000542f  call    cs:__imp_ExFreePoolWithTag
0x140005436  nop     dword ptr [rax+rax+00h]
0x14000543b  test    rsi, rsi
0x14000543e  jz      short loc_14000545D
0x140005440  mov     rdx, [rsi+18h]; WorkerRoutine
0x140005444  mov     r9, rsi; Context
0x140005447  mov     rcx, [rbx+0C8h]; IoWorkItem
0x14000544e  xor     r8d, r8d; QueueType
0x140005451  call    cs:__imp_IoQueueWorkItem
0x140005458  nop     dword ptr [rax+rax+00h]
0x14000545d  lea     rcx, [rbx+508h]; RunRef
0x140005464  call    cs:__imp_ExReleaseRundownProtection
0x14000546b  nop     dword ptr [rax+rax+00h]
0x140005470  mov     rbx, [rsp+48h+arg_0]
0x140005475  mov     rsi, [rsp+48h+arg_8]
0x14000547a  add     rsp, 40h
0x14000547e  pop     rdi
0x14000547f  retn
0x140005481  mov     ecx, 3
0x140005486  int     29h; Win8: RtlFailFast(ecx)
```
