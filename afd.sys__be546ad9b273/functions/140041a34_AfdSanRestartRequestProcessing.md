# AfdSanRestartRequestProcessing

- ea: `0x140041a34`
- end: `0x140041d0c`
- name: `AfdSanRestartRequestProcessing`
- size: `728`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140020970`
- `0x140041948`
- `0x140058d10`
- `0x1400598a0`
- `0x14005ca20`
- `0x14005d290`

## callees

- `0x140041a34`
- `0x14005ac10`
- `0x14005d83c`

## import_xrefs

- `ntoskrnl!MmIsKernelAddress` at `0x140041ab3`
- `ntoskrnl!MmIsKernelAddress` at `0x140041bd4`
- `ntoskrnl!MmIsKernelAddress` at `0x140041ab3`
- `ntoskrnl!MmIsKernelAddress` at `0x140041bd4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140041cb2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140041cb2`
- `ntoskrnl!IofCompleteRequest` at `0x140041b8a`
- `ntoskrnl!IofCompleteRequest` at `0x140041ccf`
- `ntoskrnl!IofCompleteRequest` at `0x140041b8a`
- `ntoskrnl!IofCompleteRequest` at `0x140041ccf`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140041ca3`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140041ca3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041b3a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041b9f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041c36`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041ce9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041b3a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041b9f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041c36`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041ce9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140041a66`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140041a66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041c63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041c63`

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
0x140041a34  push    rbp
0x140041a36  push    rbx
0x140041a37  push    rsi
0x140041a38  push    rdi
0x140041a39  push    r12
0x140041a3b  push    r13
0x140041a3d  push    r14
0x140041a3f  push    r15
0x140041a41  mov     rbp, rsp
0x140041a44  sub     rsp, 48h
0x140041a48  xorps   xmm0, xmm0
0x140041a4b  xor     eax, eax
0x140041a4d  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140041a51  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140041a55  mov     r12d, edx
0x140041a58  mov     rbx, rcx
0x140041a5b  xor     r15d, r15d
0x140041a5e  lea     rdx, [rbp+LockHandle]; LockHandle
0x140041a62  lea     rcx, [rbx+38h]; SpinLock
0x140041a66  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140041a6d  nop     dword ptr [rax+rax+00h]
0x140041a72  mov     eax, 1AFDh
0x140041a77  cmp     [rbx], ax
0x140041a7a  jnz     loc_140041CE5
0x140041a80  mov     r14d, [rbx+9Ch]
0x140041a87  test    r12d, r12d
0x140041a8a  js      loc_140041BBC
0x140041a90  cmp     r14d, 103h
0x140041a97  jz      short loc_140041AC7
0x140041a99  cmp     r14d, 0C0000016h
0x140041aa0  jnz     loc_140041B9B
0x140041aa6  mov     rcx, [rbx+70h]
0x140041aaa  test    rcx, rcx
0x140041aad  jz      loc_140041B9B
0x140041ab3  call    cs:__imp_MmIsKernelAddress
0x140041aba  nop     dword ptr [rax+rax+00h]
0x140041abf  test    al, al
0x140041ac1  jnz     loc_140041B9B
0x140041ac7  lea     rcx, [rbx+80h]
0x140041ace  mov     rax, [rcx]
0x140041ad1  cmp     rax, rcx
0x140041ad4  jz      loc_140041BB3
0x140041ada  mov     rdx, rax
0x140041add  mov     rax, [rax]
0x140041ae0  cmp     [rdx-30h], r15
0x140041ae4  jnz     short loc_140041AD1
0x140041ae6  mov     r8, [rdx+10h]
0x140041aea  movzx   ecx, byte ptr [r8]
0x140041aee  sub     ecx, 3
0x140041af1  jz      short loc_140041B0A
0x140041af3  cmp     ecx, 1
0x140041af6  jz      short loc_140041B03
0x140041af8  mov     rsi, [rdx-20h]
0x140041afc  mov     edi, 3
0x140041b01  jmp     short loc_140041B13
0x140041b03  mov     edi, 2
0x140041b08  jmp     short loc_140041B0F
0x140041b0a  mov     edi, 1
0x140041b0f  mov     esi, [r8+8]
0x140041b13  mov     eax, [rbx+94h]
0x140041b19  lea     r15d, [rdi+rax*8]
0x140041b1d  mov     [rdx-30h], r15
0x140041b21  inc     dword ptr [rbx+94h]
0x140041b27  cmp     edi, 3
0x140041b2a  jnz     short loc_140041B36
0x140041b2c  mov     dword ptr [rbx+9Ch], 103h
0x140041b36  lea     rcx, [rbp+LockHandle]; LockHandle
0x140041b3a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140041b41  nop     dword ptr [rax+rax+00h]
0x140041b46  mov     r9, rsi
0x140041b49  xor     r8d, r8d
0x140041b4c  mov     rdx, r15
0x140041b4f  mov     rcx, rbx
0x140041b52  call    AfdSanNotifyRequest
0x140041b57  mov     esi, eax
0x140041b59  test    eax, eax
0x140041b5b  js      short loc_140041B67
0x140041b5d  cmp     edi, 3
0x140041b60  jz      short loc_140041BAB
0x140041b62  jmp     loc_140041A5B
0x140041b67  mov     rdx, r15
0x140041b6a  mov     rcx, rbx
0x140041b6d  call    AfdSanDequeueRequest
0x140041b72  xor     r15d, r15d
0x140041b75  test    rax, rax
0x140041b78  jz      loc_140041A5E
0x140041b7e  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140041b84  mov     rcx, rax; Irp
0x140041b87  mov     [rax+30h], esi
0x140041b8a  call    cs:__imp_IofCompleteRequest
0x140041b91  nop     dword ptr [rax+rax+00h]
0x140041b96  jmp     loc_140041A5E
0x140041b9b  lea     rcx, [rbp+LockHandle]; LockHandle
0x140041b9f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140041ba6  nop     dword ptr [rax+rax+00h]
0x140041bab  mov     eax, r14d
0x140041bae  jmp     loc_140041CFA
0x140041bb3  mov     [rbx+9Ch], r12d
0x140041bba  jmp     short loc_140041B9B
0x140041bbc  mov     rsi, r15
0x140041bbf  mov     rdi, r15
0x140041bc2  cmp     r14d, 0C0000016h
0x140041bc9  jnz     short loc_140041BF3
0x140041bcb  mov     rcx, [rbx+70h]
0x140041bcf  test    rcx, rcx
0x140041bd2  jz      short loc_140041BF3
0x140041bd4  call    cs:__imp_MmIsKernelAddress
0x140041bdb  nop     dword ptr [rax+rax+00h]
0x140041be0  test    al, al
0x140041be2  jz      short loc_140041BF3
0x140041be4  mov     rdi, [rbx+70h]
0x140041be8  mov     [rbx+70h], r15
0x140041bec  mov     [rbx+90h], r15d
0x140041bf3  mov     [rbx+9Ch], r12d
0x140041bfa  lea     rcx, [rbx+80h]
0x140041c01  mov     rax, [rcx]
0x140041c04  cmp     rax, rcx
0x140041c07  jz      short loc_140041C32
0x140041c09  cmp     [rax+8], rcx
0x140041c0d  jnz     short loc_140041C2B
0x140041c0f  mov     rdx, [rax]
0x140041c12  cmp     [rdx+8], rax
0x140041c16  jnz     short loc_140041C2B
0x140041c18  mov     [rcx], rdx
0x140041c1b  mov     [rdx+8], rcx
0x140041c1f  mov     [rax+8], rsi
0x140041c23  mov     rsi, rax
0x140041c26  mov     [rax], r15
0x140041c29  jmp     short loc_140041C01
0x140041c2b  mov     ecx, 3
0x140041c30  int     29h; Win8: RtlFailFast(ecx)
0x140041c32  lea     rcx, [rbp+LockHandle]; LockHandle
0x140041c36  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140041c3d  nop     dword ptr [rax+rax+00h]
0x140041c42  mov     r13d, 84h
0x140041c48  test    rdi, rdi
0x140041c4b  jz      loc_140041CDB
0x140041c51  mov     rax, [rbx+60h]
0x140041c55  lock add dword ptr [rax+r13], 0FFFFFFFEh
0x140041c5b  mov     edx, 78646641h; Tag
0x140041c60  mov     rcx, rdi; P
0x140041c63  call    cs:__imp_ExFreePoolWithTag
0x140041c6a  nop     dword ptr [rax+rax+00h]
0x140041c6f  jmp     short loc_140041CDB
0x140041c71  lea     rdi, [rsi-0A8h]
0x140041c78  mov     rsi, [rdi+0B0h]
0x140041c7f  cmp     [rdi+78h], r15
0x140041c83  jz      short loc_140041C8F
0x140041c85  mov     rax, [rbx+60h]
0x140041c89  lock add dword ptr [rax+r13], 0FFFFFFFEh
0x140041c8f  mov     rax, r15
0x140041c92  xchg    rax, [rdi+68h]
0x140041c96  test    rax, rax
0x140041c99  jnz     short loc_140041CBE
0x140041c9b  lea     rcx, [rbp+Irql]; Irql
0x140041c9f  mov     [rbp+Irql], r15b
0x140041ca3  call    cs:__imp_IoAcquireCancelSpinLock
0x140041caa  nop     dword ptr [rax+rax+00h]
0x140041caf  mov     cl, [rbp+Irql]; Irql
0x140041cb2  call    cs:__imp_IoReleaseCancelSpinLock
0x140041cb9  nop     dword ptr [rax+rax+00h]
0x140041cbe  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140041cc4  mov     rcx, rdi; Irp
0x140041cc7  mov     [rdi+30h], r12d
0x140041ccb  mov     [rdi+38h], r15
0x140041ccf  call    cs:__imp_IofCompleteRequest
0x140041cd6  nop     dword ptr [rax+rax+00h]
0x140041cdb  test    rsi, rsi
0x140041cde  jnz     short loc_140041C71
0x140041ce0  jmp     loc_140041BAB
0x140041ce5  lea     rcx, [rbp+LockHandle]; LockHandle
0x140041ce9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140041cf0  nop     dword ptr [rax+rax+00h]
0x140041cf5  mov     eax, 0C0000008h
0x140041cfa  add     rsp, 48h
0x140041cfe  pop     r15
0x140041d00  pop     r14
0x140041d02  pop     r13
0x140041d04  pop     r12
0x140041d06  pop     rdi
0x140041d07  pop     rsi
0x140041d08  pop     rbx
0x140041d09  pop     rbp
0x140041d0a  retn
```
