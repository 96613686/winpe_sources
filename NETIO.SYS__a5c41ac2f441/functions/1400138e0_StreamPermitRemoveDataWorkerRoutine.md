# StreamPermitRemoveDataWorkerRoutine

- ea: `0x1400138e0`
- end: `0x140013c32`
- name: `StreamPermitRemoveDataWorkerRoutine`
- size: `850`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x140001464`
- `0x1400138e0`
- `0x140013c38`
- `0x140013dc8`
- `0x14001771c`
- `0x140078080`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013971`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400139c0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013a58`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013aed`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013971`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400139c0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013a58`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013aed`
- `ntoskrnl!IoFreeWorkItem` at `0x140013acd`
- `ntoskrnl!IoFreeWorkItem` at `0x140013acd`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001393d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013a23`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001393d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013a23`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140013954`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140013a3b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140013954`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140013a3b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400139ee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013b1b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400139ee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013b1b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140013b5b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140013b9b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140013b5b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140013b9b`

## pseudocode

```c
void __fastcall StreamPermitRemoveDataWorkerRoutine(PDEVICE_OBJECT DeviceObject, _QWORD *Context)
{
  __int64 v3; // rdi
  int v4; // r13d
  __int64 v5; // r12
  __int64 **v6; // r14
  KIRQL CurrentIrql; // bl
  __int64 v8; // rdx
  __int64 *v9; // rsi
  __int64 v10; // rbp
  _DWORD *v11; // rdx
  KIRQL v12; // bl
  __int64 v13; // rdx
  __int64 *v14; // rax
  __int64 *v15; // rcx
  _DWORD *v16; // rdx
  char *v17; // rbx
  char *v18; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int8 v20; // [rsp+A8h] [rbp+10h]

  v3 = *Context;
  v4 = 0;
  v5 = Context[1];
  v20 = *((_BYTE *)Context + 16);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_75c4a08dd9c13bf229d1b4be1d6eefab_Traceguids, v3 + 64, v5);
  }
  v6 = (__int64 **)(v3 + 80);
  do
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    CurrentIrql = KeGetCurrentIrql();
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 72), &LockHandle);
    if ( CurrentIrql != 2 && gWfpPerProContext )
    {
      v8 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v8 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v8 = 4;
    }
    v9 = *v6;
    v10 = *(_QWORD *)(v3 + 96);
    if ( *v6 == (__int64 *)v6 )
      v9 = 0;
    if ( gWfpPerProContext )
    {
      v11 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v11 == 4 )
        *v11 = 0;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v10 )
      StreamRemoveDataHelper(v5, v10, v20);
    if ( v9 )
      StreamPermitDataHelper(v9, v5);
    v12 = KeGetCurrentIrql();
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 72), &LockHandle);
    if ( v12 != 2 && gWfpPerProContext )
    {
      v13 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v13 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v13 = 4;
    }
    if ( v9 )
    {
      v14 = *v6;
      if ( (__int64 **)(*v6)[1] != v6 || (v15 = (__int64 *)*v14, *(__int64 **)(*v14 + 8) != v14) )
        __fastfail(3u);
      *v6 = v15;
      v15[1] = (__int64)v6;
    }
    *(_QWORD *)(v3 + 96) -= v10;
    if ( *v6 == (__int64 *)v6 && !*(_QWORD *)(v3 + 96) )
    {
      v4 = 1;
      IoFreeWorkItem(*(PIO_WORKITEM *)(v3 + 64));
      *(_QWORD *)(v3 + 64) = 0;
    }
    if ( gWfpPerProContext )
    {
      v16 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v16 == 4 )
        *v16 = 0;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v9 )
    {
      v17 = (char *)*(&xmmword_14009AA10 + 1)
          + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v17[176] )
        PplpLazyInitializeLookasideList(*(&xmmword_14009AA10 + 1), v17 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v17 + 64), v9);
    }
  }
  while ( !v4 );
  v18 = (char *)P + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
  if ( !v18[176] )
    PplpLazyInitializeLookasideList(P, v18 + 64);
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v18 + 64), Context);
  ((void (__fastcall *)(__int64, __int64))qword_14009A988)(v5, 3);
}

```

## disassembly

```asm
0x1400138e0  push    rbx
0x1400138e2  push    rbp
0x1400138e3  push    rsi
0x1400138e4  push    rdi
0x1400138e5  push    r12
0x1400138e7  push    r13
0x1400138e9  push    r14
0x1400138eb  push    r15
0x1400138ed  sub     rsp, 58h
0x1400138f1  movzx   eax, byte ptr [rdx+10h]
0x1400138f5  mov     r15, rdx
0x1400138f8  mov     rdi, [rdx]
0x1400138fb  xor     r13d, r13d
0x1400138fe  mov     r12, [rdx+8]
0x140013902  mov     [rsp+98h+arg_8], al
0x140013909  mov     rcx, cs:WPP_GLOBAL_Control
0x140013910  lea     rax, WPP_GLOBAL_Control
0x140013917  cmp     rcx, rax
0x14001391a  jz      short loc_140013926
0x14001391c  cmp     byte ptr [rcx+29h], 4
0x140013920  jnb     loc_140013C02
0x140013926  lea     r14, [rdi+50h]
0x14001392a  xorps   xmm0, xmm0
0x14001392d  lea     rsi, [rdi+48h]
0x140013931  xor     eax, eax
0x140013933  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x140013938  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x14001393d  call    cs:__imp_KeGetCurrentIrql
0x140013944  nop     dword ptr [rax+rax+00h]
0x140013949  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x14001394e  mov     rcx, rsi; SpinLock
0x140013951  movzx   ebx, al
0x140013954  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001395b  nop     dword ptr [rax+rax+00h]
0x140013960  cmp     bl, 2
0x140013963  jz      short loc_1400139A5
0x140013965  cmp     cs:gWfpPerProContext, 0
0x14001396d  jz      short loc_1400139A5
0x14001396f  xor     ecx, ecx; ProcNumber
0x140013971  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140013978  nop     dword ptr [rax+rax+00h]
0x14001397d  imul    eax, cs:gWfpPerProContextSize
0x140013984  mov     ecx, eax
0x140013986  mov     rax, cs:gWfpPerProContext
0x14001398d  mov     rdx, [rcx+rax]
0x140013991  mov     rax, ds:0FFFFF78000000008h
0x14001399b  mov     [rdx+8], rax
0x14001399f  mov     dword ptr [rdx], 4
0x1400139a5  mov     rsi, [r14]
0x1400139a8  xor     eax, eax
0x1400139aa  mov     rbp, [rdi+60h]
0x1400139ae  cmp     rsi, r14
0x1400139b1  cmovz   rsi, rax
0x1400139b5  cmp     cs:gWfpPerProContext, rax
0x1400139bc  jz      short loc_1400139E9
0x1400139be  xor     ecx, ecx; ProcNumber
0x1400139c0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400139c7  nop     dword ptr [rax+rax+00h]
0x1400139cc  imul    eax, cs:gWfpPerProContextSize
0x1400139d3  mov     ecx, eax
0x1400139d5  mov     rax, cs:gWfpPerProContext
0x1400139dc  mov     rdx, [rcx+rax]
0x1400139e0  cmp     dword ptr [rdx], 4
0x1400139e3  jz      loc_140013BCD
0x1400139e9  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x1400139ee  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400139f5  nop     dword ptr [rax+rax+00h]
0x1400139fa  test    rbp, rbp
0x1400139fd  jz      short loc_140013A13
0x1400139ff  movzx   r8d, [rsp+98h+arg_8]
0x140013a08  mov     rdx, rbp
0x140013a0b  mov     rcx, r12
0x140013a0e  call    StreamRemoveDataHelper
0x140013a13  test    rsi, rsi
0x140013a16  jz      short loc_140013A23
0x140013a18  mov     rdx, r12
0x140013a1b  mov     rcx, rsi
0x140013a1e  call    StreamPermitDataHelper
0x140013a23  call    cs:__imp_KeGetCurrentIrql
0x140013a2a  nop     dword ptr [rax+rax+00h]
0x140013a2f  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x140013a34  movzx   ebx, al
0x140013a37  lea     rcx, [rdi+48h]; SpinLock
0x140013a3b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140013a42  nop     dword ptr [rax+rax+00h]
0x140013a47  cmp     bl, 2
0x140013a4a  jz      short loc_140013A8C
0x140013a4c  cmp     cs:gWfpPerProContext, 0
0x140013a54  jz      short loc_140013A8C
0x140013a56  xor     ecx, ecx; ProcNumber
0x140013a58  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140013a5f  nop     dword ptr [rax+rax+00h]
0x140013a64  imul    eax, cs:gWfpPerProContextSize
0x140013a6b  mov     ecx, eax
0x140013a6d  mov     rax, cs:gWfpPerProContext
0x140013a74  mov     rdx, [rcx+rax]
0x140013a78  mov     rax, ds:0FFFFF78000000008h
0x140013a82  mov     [rdx+8], rax
0x140013a86  mov     dword ptr [rdx], 4
0x140013a8c  test    rsi, rsi
0x140013a8f  jz      short loc_140013AB1
0x140013a91  mov     rax, [r14]
0x140013a94  cmp     [rax+8], r14
0x140013a98  jz      short loc_140013AA1
0x140013a9a  mov     ecx, 3
0x140013a9f  int     29h; Win8: RtlFailFast(ecx)
0x140013aa1  mov     rcx, [rax]
0x140013aa4  cmp     [rcx+8], rax
0x140013aa8  jnz     short loc_140013A9A
0x140013aaa  mov     [r14], rcx
0x140013aad  mov     [rcx+8], r14
0x140013ab1  sub     [rdi+60h], rbp
0x140013ab5  mov     rax, [rdi+60h]
0x140013ab9  cmp     [r14], r14
0x140013abc  jnz     short loc_140013AE1
0x140013abe  test    rax, rax
0x140013ac1  jnz     short loc_140013AE1
0x140013ac3  mov     rcx, [rdi+40h]; IoWorkItem
0x140013ac7  mov     r13d, 1
0x140013acd  call    cs:__imp_IoFreeWorkItem
0x140013ad4  nop     dword ptr [rax+rax+00h]
0x140013ad9  mov     qword ptr [rdi+40h], 0
0x140013ae1  cmp     cs:gWfpPerProContext, 0
0x140013ae9  jz      short loc_140013B16
0x140013aeb  xor     ecx, ecx; ProcNumber
0x140013aed  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140013af4  nop     dword ptr [rax+rax+00h]
0x140013af9  imul    eax, cs:gWfpPerProContextSize
0x140013b00  mov     ecx, eax
0x140013b02  mov     rax, cs:gWfpPerProContext
0x140013b09  mov     rdx, [rcx+rax]
0x140013b0d  cmp     dword ptr [rdx], 4
0x140013b10  jz      loc_140013BD8
0x140013b16  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140013b1b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140013b22  nop     dword ptr [rax+rax+00h]
0x140013b27  test    rsi, rsi
0x140013b2a  jz      short loc_140013B67
0x140013b2c  mov     eax, gs:1A4h
0x140013b34  mov     r8, qword ptr cs:xmmword_14009AA10+8
0x140013b3b  lea     ebx, [rax+1]
0x140013b3e  shl     rbx, 7
0x140013b42  add     rbx, r8
0x140013b45  movzx   eax, byte ptr [rbx+0B0h]
0x140013b4c  test    al, al
0x140013b4e  jz      loc_140013BE3
0x140013b54  mov     rdx, rsi; Entry
0x140013b57  lea     rcx, [rbx+40h]; Lookaside
0x140013b5b  call    cs:__imp_ExFreeToLookasideListEx
0x140013b62  nop     dword ptr [rax+rax+00h]
0x140013b67  test    r13d, r13d
0x140013b6a  jz      loc_14001392A
0x140013b70  mov     eax, gs:1A4h
0x140013b78  mov     r8, cs:P
0x140013b7f  lea     ebx, [rax+1]
0x140013b82  shl     rbx, 7
0x140013b86  add     rbx, r8
0x140013b89  movzx   eax, byte ptr [rbx+0B0h]
0x140013b90  test    al, al
0x140013b92  jz      short loc_140013BF4
0x140013b94  mov     rdx, r15; Entry
0x140013b97  lea     rcx, [rbx+40h]; Lookaside
0x140013b9b  call    cs:__imp_ExFreeToLookasideListEx
0x140013ba2  nop     dword ptr [rax+rax+00h]
0x140013ba7  mov     rax, cs:qword_14009A988
0x140013bae  mov     edx, 3
0x140013bb3  mov     rcx, r12
0x140013bb6  call    _guard_dispatch_icall
0x140013bbb  add     rsp, 58h
0x140013bbf  pop     r15
0x140013bc1  pop     r14
0x140013bc3  pop     r13
0x140013bc5  pop     r12
0x140013bc7  pop     rdi
0x140013bc8  pop     rsi
0x140013bc9  pop     rbp
0x140013bca  pop     rbx
0x140013bcb  retn
0x140013bcd  mov     dword ptr [rdx], 0
0x140013bd3  jmp     loc_1400139E9
0x140013bd8  mov     dword ptr [rdx], 0
0x140013bde  jmp     loc_140013B16
0x140013be3  lea     rdx, [rbx+40h]
0x140013be7  mov     rcx, r8
0x140013bea  call    PplpLazyInitializeLookasideList
0x140013bef  jmp     loc_140013B54
0x140013bf4  lea     rdx, [rbx+40h]
0x140013bf8  mov     rcx, r8
0x140013bfb  call    PplpLazyInitializeLookasideList
0x140013c00  jmp     short loc_140013B94
0x140013c02  test    dword ptr [rcx+2Ch], 4000h
0x140013c09  jz      loc_140013926
0x140013c0f  mov     rcx, [rcx+18h]
0x140013c13  lea     r9, [rdi+40h]
0x140013c17  mov     edx, 24h ; '$'
0x140013c1c  mov     [rsp+98h+var_78], r12
0x140013c21  lea     r8, WPP_75c4a08dd9c13bf229d1b4be1d6eefab_Traceguids
0x140013c28  call    WPP_SF_qq
0x140013c2d  jmp     loc_140013926
```
