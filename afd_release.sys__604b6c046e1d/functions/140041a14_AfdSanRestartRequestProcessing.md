# AfdSanRestartRequestProcessing

- ea: `0x140041a14`
- end: `0x140041cec`
- name: `AfdSanRestartRequestProcessing`
- size: `728`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140020970`
- `0x140041928`
- `0x140058b70`
- `0x140059700`
- `0x14005c880`
- `0x14005d0f0`

## callees

- `0x140041a14`
- `0x14005aa70`
- `0x14005d69c`

## import_xrefs

- `ntoskrnl!MmIsKernelAddress` at `0x140041a93`
- `ntoskrnl!MmIsKernelAddress` at `0x140041bb4`
- `ntoskrnl!MmIsKernelAddress` at `0x140041a93`
- `ntoskrnl!MmIsKernelAddress` at `0x140041bb4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140041c92`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140041c92`
- `ntoskrnl!IofCompleteRequest` at `0x140041b6a`
- `ntoskrnl!IofCompleteRequest` at `0x140041caf`
- `ntoskrnl!IofCompleteRequest` at `0x140041b6a`
- `ntoskrnl!IofCompleteRequest` at `0x140041caf`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140041c83`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140041c83`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041b1a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041b7f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041c16`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041cc9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041b1a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041b7f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041c16`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041cc9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140041a46`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140041a46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041c43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041c43`

## pseudocode

```c
__int64 __fastcall AfdSanRestartRequestProcessing(__int64 a1, int a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // r14d
  __int64 v7; // rcx
  _QWORD *v8; // rax
  _QWORD *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rsi
  int v12; // edi
  __int64 v13; // r15
  int v14; // esi
  IRP *v15; // rax
  CCHAR v16; // dl
  _QWORD *v18; // rsi
  void *v19; // rdi
  __int64 v20; // rcx
  _QWORD **v21; // rcx
  _QWORD *v22; // rax
  _QWORD *v23; // rdx
  _QWORD *v24; // rdi
  CCHAR v25; // dl
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF
  KIRQL Irql; // [rsp+90h] [rbp+48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  while ( 1 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
    if ( *(_WORD *)a1 != 6909 )
      break;
    v6 = *(_DWORD *)(a1 + 156);
    if ( a2 < 0 )
    {
      v18 = 0;
      v19 = 0;
      if ( v6 == -1073741802 )
      {
        v20 = *(_QWORD *)(a1 + 112);
        if ( v20 )
        {
          if ( (unsigned __int8)MmIsKernelAddress(v20, v4, v5) )
          {
            v19 = *(void **)(a1 + 112);
            *(_QWORD *)(a1 + 112) = 0;
            *(_DWORD *)(a1 + 144) = 0;
          }
        }
      }
      *(_DWORD *)(a1 + 156) = a2;
      v21 = (_QWORD **)(a1 + 128);
      while ( 1 )
      {
        v22 = *v21;
        if ( *v21 == v21 )
          break;
        if ( (_QWORD **)v22[1] != v21 || (v23 = (_QWORD *)*v22, *(_QWORD **)(*v22 + 8LL) != v22) )
          __fastfail(3u);
        *v21 = v23;
        v23[1] = v21;
        v22[1] = v18;
        v18 = v22;
        *v22 = 0;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( v19 )
      {
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 96) + 132LL), 0xFFFFFFFE);
        ExFreePoolWithTag(v19, 0x78646641u);
      }
      while ( v18 )
      {
        v24 = v18 - 21;
        v18 = (_QWORD *)v18[1];
        if ( v24[15] )
          _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 96) + 132LL), 0xFFFFFFFE);
        if ( !_InterlockedExchange64(v24 + 13, 0) )
        {
          Irql = 0;
          IoAcquireCancelSpinLock(&Irql);
          IoReleaseCancelSpinLock(Irql);
        }
        v25 = AfdPriorityBoost;
        *((_DWORD *)v24 + 12) = a2;
        v24[7] = 0;
        IofCompleteRequest((PIRP)v24, v25);
      }
      return v6;
    }
    if ( v6 != 259
      && (v6 != -1073741802 || (v7 = *(_QWORD *)(a1 + 112)) == 0 || (unsigned __int8)MmIsKernelAddress(v7, v4, v5)) )
    {
LABEL_24:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      return v6;
    }
    v8 = *(_QWORD **)(a1 + 128);
    do
    {
      if ( v8 == (_QWORD *)(a1 + 128) )
      {
        *(_DWORD *)(a1 + 156) = a2;
        goto LABEL_24;
      }
      v9 = v8;
      v8 = (_QWORD *)*v8;
    }
    while ( *(v9 - 6) );
    v10 = v9[2];
    if ( *(_BYTE *)v10 == 3 )
    {
      v12 = 1;
      goto LABEL_16;
    }
    if ( *(_BYTE *)v10 == 4 )
    {
      v12 = 2;
LABEL_16:
      v11 = *(unsigned int *)(v10 + 8);
      goto LABEL_17;
    }
    v11 = *(v9 - 4);
    v12 = 3;
LABEL_17:
    v13 = (unsigned int)(v12 + 8 * *(_DWORD *)(a1 + 148));
    *(v9 - 6) = v13;
    ++*(_DWORD *)(a1 + 148);
    if ( v12 == 3 )
      *(_DWORD *)(a1 + 156) = 259;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v14 = AfdSanNotifyRequest(a1, v13, 0, v11);
    if ( v14 < 0 )
    {
      v15 = (IRP *)AfdSanDequeueRequest(a1);
      if ( v15 )
      {
        v16 = AfdPriorityBoost;
        v15->IoStatus.Status = v14;
        IofCompleteRequest(v15, v16);
      }
    }
    else if ( v12 == 3 )
    {
      return v6;
    }
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return 3221225480LL;
}

```

## disassembly

```asm
0x140041a14  push    rbp
0x140041a16  push    rbx
0x140041a17  push    rsi
0x140041a18  push    rdi
0x140041a19  push    r12
0x140041a1b  push    r13
0x140041a1d  push    r14
0x140041a1f  push    r15
0x140041a21  mov     rbp, rsp
0x140041a24  sub     rsp, 48h
0x140041a28  xorps   xmm0, xmm0
0x140041a2b  xor     eax, eax
0x140041a2d  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140041a31  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140041a35  mov     r12d, edx
0x140041a38  mov     rbx, rcx
0x140041a3b  xor     r15d, r15d
0x140041a3e  lea     rdx, [rbp+LockHandle]; LockHandle
0x140041a42  lea     rcx, [rbx+38h]; SpinLock
0x140041a46  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140041a4d  nop     dword ptr [rax+rax+00h]
0x140041a52  mov     eax, 1AFDh
0x140041a57  cmp     [rbx], ax
0x140041a5a  jnz     loc_140041CC5
0x140041a60  mov     r14d, [rbx+9Ch]
0x140041a67  test    r12d, r12d
0x140041a6a  js      loc_140041B9C
0x140041a70  cmp     r14d, 103h
0x140041a77  jz      short loc_140041AA7
0x140041a79  cmp     r14d, 0C0000016h
0x140041a80  jnz     loc_140041B7B
0x140041a86  mov     rcx, [rbx+70h]
0x140041a8a  test    rcx, rcx
0x140041a8d  jz      loc_140041B7B
0x140041a93  call    cs:__imp_MmIsKernelAddress
0x140041a9a  nop     dword ptr [rax+rax+00h]
0x140041a9f  test    al, al
0x140041aa1  jnz     loc_140041B7B
0x140041aa7  lea     rcx, [rbx+80h]
0x140041aae  mov     rax, [rcx]
0x140041ab1  cmp     rax, rcx
0x140041ab4  jz      loc_140041B93
0x140041aba  mov     rdx, rax
0x140041abd  mov     rax, [rax]
0x140041ac0  cmp     [rdx-30h], r15
0x140041ac4  jnz     short loc_140041AB1
0x140041ac6  mov     r8, [rdx+10h]
0x140041aca  movzx   ecx, byte ptr [r8]
0x140041ace  sub     ecx, 3
0x140041ad1  jz      short loc_140041AEA
0x140041ad3  cmp     ecx, 1
0x140041ad6  jz      short loc_140041AE3
0x140041ad8  mov     rsi, [rdx-20h]
0x140041adc  mov     edi, 3
0x140041ae1  jmp     short loc_140041AF3
0x140041ae3  mov     edi, 2
0x140041ae8  jmp     short loc_140041AEF
0x140041aea  mov     edi, 1
0x140041aef  mov     esi, [r8+8]
0x140041af3  mov     eax, [rbx+94h]
0x140041af9  lea     r15d, [rdi+rax*8]
0x140041afd  mov     [rdx-30h], r15
0x140041b01  inc     dword ptr [rbx+94h]
0x140041b07  cmp     edi, 3
0x140041b0a  jnz     short loc_140041B16
0x140041b0c  mov     dword ptr [rbx+9Ch], 103h
0x140041b16  lea     rcx, [rbp+LockHandle]; LockHandle
0x140041b1a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140041b21  nop     dword ptr [rax+rax+00h]
0x140041b26  mov     r9, rsi
0x140041b29  xor     r8d, r8d
0x140041b2c  mov     rdx, r15
0x140041b2f  mov     rcx, rbx
0x140041b32  call    AfdSanNotifyRequest
0x140041b37  mov     esi, eax
0x140041b39  test    eax, eax
0x140041b3b  js      short loc_140041B47
0x140041b3d  cmp     edi, 3
0x140041b40  jz      short loc_140041B8B
0x140041b42  jmp     loc_140041A3B
0x140041b47  mov     rdx, r15
0x140041b4a  mov     rcx, rbx
0x140041b4d  call    AfdSanDequeueRequest
0x140041b52  xor     r15d, r15d
0x140041b55  test    rax, rax
0x140041b58  jz      loc_140041A3E
0x140041b5e  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140041b64  mov     rcx, rax; Irp
0x140041b67  mov     [rax+30h], esi
0x140041b6a  call    cs:__imp_IofCompleteRequest
0x140041b71  nop     dword ptr [rax+rax+00h]
0x140041b76  jmp     loc_140041A3E
0x140041b7b  lea     rcx, [rbp+LockHandle]; LockHandle
0x140041b7f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140041b86  nop     dword ptr [rax+rax+00h]
0x140041b8b  mov     eax, r14d
0x140041b8e  jmp     loc_140041CDA
0x140041b93  mov     [rbx+9Ch], r12d
0x140041b9a  jmp     short loc_140041B7B
0x140041b9c  mov     rsi, r15
0x140041b9f  mov     rdi, r15
0x140041ba2  cmp     r14d, 0C0000016h
0x140041ba9  jnz     short loc_140041BD3
0x140041bab  mov     rcx, [rbx+70h]
0x140041baf  test    rcx, rcx
0x140041bb2  jz      short loc_140041BD3
0x140041bb4  call    cs:__imp_MmIsKernelAddress
0x140041bbb  nop     dword ptr [rax+rax+00h]
0x140041bc0  test    al, al
0x140041bc2  jz      short loc_140041BD3
0x140041bc4  mov     rdi, [rbx+70h]
0x140041bc8  mov     [rbx+70h], r15
0x140041bcc  mov     [rbx+90h], r15d
0x140041bd3  mov     [rbx+9Ch], r12d
0x140041bda  lea     rcx, [rbx+80h]
0x140041be1  mov     rax, [rcx]
0x140041be4  cmp     rax, rcx
0x140041be7  jz      short loc_140041C12
0x140041be9  cmp     [rax+8], rcx
0x140041bed  jnz     short loc_140041C0B
0x140041bef  mov     rdx, [rax]
0x140041bf2  cmp     [rdx+8], rax
0x140041bf6  jnz     short loc_140041C0B
0x140041bf8  mov     [rcx], rdx
0x140041bfb  mov     [rdx+8], rcx
0x140041bff  mov     [rax+8], rsi
0x140041c03  mov     rsi, rax
0x140041c06  mov     [rax], r15
0x140041c09  jmp     short loc_140041BE1
0x140041c0b  mov     ecx, 3
0x140041c10  int     29h; Win8: RtlFailFast(ecx)
0x140041c12  lea     rcx, [rbp+LockHandle]; LockHandle
0x140041c16  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140041c1d  nop     dword ptr [rax+rax+00h]
0x140041c22  mov     r13d, 84h
0x140041c28  test    rdi, rdi
0x140041c2b  jz      loc_140041CBB
0x140041c31  mov     rax, [rbx+60h]
0x140041c35  lock add dword ptr [rax+r13], 0FFFFFFFEh
0x140041c3b  mov     edx, 78646641h; Tag
0x140041c40  mov     rcx, rdi; P
0x140041c43  call    cs:__imp_ExFreePoolWithTag
0x140041c4a  nop     dword ptr [rax+rax+00h]
0x140041c4f  jmp     short loc_140041CBB
0x140041c51  lea     rdi, [rsi-0A8h]
0x140041c58  mov     rsi, [rdi+0B0h]
0x140041c5f  cmp     [rdi+78h], r15
0x140041c63  jz      short loc_140041C6F
0x140041c65  mov     rax, [rbx+60h]
0x140041c69  lock add dword ptr [rax+r13], 0FFFFFFFEh
0x140041c6f  mov     rax, r15
0x140041c72  xchg    rax, [rdi+68h]
0x140041c76  test    rax, rax
0x140041c79  jnz     short loc_140041C9E
0x140041c7b  lea     rcx, [rbp+Irql]; Irql
0x140041c7f  mov     [rbp+Irql], r15b
0x140041c83  call    cs:__imp_IoAcquireCancelSpinLock
0x140041c8a  nop     dword ptr [rax+rax+00h]
0x140041c8f  mov     cl, [rbp+Irql]; Irql
0x140041c92  call    cs:__imp_IoReleaseCancelSpinLock
0x140041c99  nop     dword ptr [rax+rax+00h]
0x140041c9e  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140041ca4  mov     rcx, rdi; Irp
0x140041ca7  mov     [rdi+30h], r12d
0x140041cab  mov     [rdi+38h], r15
0x140041caf  call    cs:__imp_IofCompleteRequest
0x140041cb6  nop     dword ptr [rax+rax+00h]
0x140041cbb  test    rsi, rsi
0x140041cbe  jnz     short loc_140041C51
0x140041cc0  jmp     loc_140041B8B
0x140041cc5  lea     rcx, [rbp+LockHandle]; LockHandle
0x140041cc9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140041cd0  nop     dword ptr [rax+rax+00h]
0x140041cd5  mov     eax, 0C0000008h
0x140041cda  add     rsp, 48h
0x140041cde  pop     r15
0x140041ce0  pop     r14
0x140041ce2  pop     r13
0x140041ce4  pop     r12
0x140041ce6  pop     rdi
0x140041ce7  pop     rsi
0x140041ce8  pop     rbx
0x140041ce9  pop     rbp
0x140041cea  retn
```
