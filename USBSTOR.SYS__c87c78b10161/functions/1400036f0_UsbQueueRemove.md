# UsbQueueRemove

- ea: `0x1400036f0`
- end: `0x140003b7b`
- name: `UsbQueueRemove`
- size: `1163`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003b90`

## callees

- `0x1400036f0`
- `0x140006a70`
- `0x1400105e8`
- `0x140010664`
- `0x140010e74`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140003a43`
- `ntoskrnl!KeSetEvent` at `0x140003a43`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003763`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400037de`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400039c0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003a7e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003763`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400037de`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400039c0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003a7e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400037c1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000389e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003a1e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003ad8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400037c1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000389e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003a1e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003ad8`

## pseudocode

```c
__int64 *__fastcall UsbQueueRemove(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rax
  __int64 *v4; // rsi
  _QWORD *v5; // rdi
  __int64 *v6; // rax
  __int64 **v7; // rcx
  __int64 v8; // rax
  int v10; // eax
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE v16; // [rsp+38h] [rbp-20h] BYREF

  memset(&v16, 0, sizeof(v16));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    v2 = *(int *)(a1 + 300);
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1986880850;
    *(_QWORD *)(qword_14001A190 + 8) = a1;
    *(_QWORD *)(qword_14001A190 + 16) = 0;
    *(_QWORD *)(qword_14001A190 + 24) = v2;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v3 = qword_14001A198 - 32;
    else
      v3 = qword_14001A190 - 32;
    qword_14001A190 = v3;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 288), &v16);
  if ( *(_BYTE *)(a1 + 304) )
  {
    v4 = 0;
LABEL_32:
    v10 = *(_DWORD *)(a1 + 300);
    if ( v10 >= *(_DWORD *)(a1 + 296) )
    {
      *(_DWORD *)(a1 + 300) = v10 - 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
      }
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( P )
      {
        v11 = *(int *)(a1 + 300);
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_DWORD *)qword_14001A190 = 1331914052;
        *(_QWORD *)(qword_14001A190 + 8) = a1;
        *(_QWORD *)(qword_14001A190 + 16) = 0;
        *(_QWORD *)(qword_14001A190 + 24) = v11;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v12 = qword_14001A198 - 32;
        else
          v12 = qword_14001A190 - 32;
        qword_14001A190 = v12;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      if ( *(_BYTE *)(a1 + 304) )
      {
        KeSetEvent((PRKEVENT)(a1 + 328), 0, 0);
        memset(&LockHandle, 0, sizeof(LockHandle));
        if ( P )
        {
          v13 = *(int *)(a1 + 300);
          KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
          *(_DWORD *)qword_14001A190 = 1196639569;
          *(_QWORD *)(qword_14001A190 + 8) = a1;
          *(_QWORD *)(qword_14001A190 + 16) = 0;
          *(_QWORD *)(qword_14001A190 + 24) = v13;
          if ( qword_14001A190 <= (unsigned __int64)P )
            v14 = qword_14001A198 - 32;
          else
            v14 = qword_14001A190 - 32;
          qword_14001A190 = v14;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
      }
    }
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  do
  {
    v4 = 0;
    if ( !*(_DWORD *)(a1 + 4) )
      break;
    v5 = (_QWORD *)(a1 + 32);
    if ( (_QWORD *)*v5 == v5 )
    {
      PortAvioSchedulerTransferBatch(a1);
      if ( (_QWORD *)*v5 == v5 )
        continue;
    }
    v4 = *(__int64 **)(a1 + 48);
    *(_QWORD *)(a1 + 48) = *v4;
    *(_QWORD *)(a1 + 72) = v4[2] + 1;
    v6 = (__int64 *)*v4;
    if ( *(__int64 **)(*v4 + 8) != v4 || (v7 = (__int64 **)v4[1], *v7 != v4) )
      __fastfail(3u);
    *v7 = v6;
    v6[1] = (__int64)v7;
    v8 = *(_QWORD *)(a1 + 64);
    --*(_DWORD *)(a1 + 56);
    if ( v8 )
      --*(_DWORD *)(v8 + 4);
    if ( *(_QWORD *)(a1 + 48) == a1 + 32 )
      *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 32);
    v4 -= 15;
  }
  while ( !_InterlockedExchange64(v4 + 13, 0) );
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids, v4);
  }
  if ( !v4 )
    goto LABEL_32;
LABEL_20:
  KeReleaseInStackQueuedSpinLock(&v16);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x1400036f0  mov     [rsp+arg_10], rbx
0x1400036f5  mov     [rsp+arg_18], rbp
0x1400036fa  push    r14
0x1400036fc  sub     rsp, 50h
0x140003700  xorps   xmm0, xmm0
0x140003703  xor     eax, eax
0x140003705  movups  xmmword ptr [rsp+58h+var_20.LockQueue.Next], xmm0
0x14000370a  mov     qword ptr [rsp+58h+var_20.OldIrql], rax
0x14000370f  mov     rbx, rcx
0x140003712  mov     rcx, cs:WPP_GLOBAL_Control
0x140003719  lea     rbp, WPP_GLOBAL_Control
0x140003720  cmp     rcx, rbp
0x140003723  jz      short loc_140003730
0x140003725  mov     eax, [rcx+2Ch]
0x140003728  test    al, 20h
0x14000372a  jnz     loc_140003B33
0x140003730  xor     eax, eax
0x140003732  mov     [rsp+58h+arg_8], rdi
0x140003737  xor     r14d, r14d
0x14000373a  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x14000373f  cmp     cs:P, rax
0x140003746  xorps   xmm0, xmm0
0x140003749  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x14000374e  jz      short loc_1400037CD
0x140003750  movsxd  rdi, dword ptr [rbx+12Ch]
0x140003757  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x14000375c  lea     rcx, SpinLock; SpinLock
0x140003763  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000376a  nop     dword ptr [rax+rax+00h]
0x14000376f  mov     rax, cs:qword_14001A190
0x140003776  mov     dword ptr [rax], 766D6552h
0x14000377c  mov     rax, cs:qword_14001A190
0x140003783  mov     [rax+8], rbx
0x140003787  mov     rax, cs:qword_14001A190
0x14000378e  mov     [rax+10h], r14
0x140003792  mov     rax, cs:qword_14001A190
0x140003799  mov     [rax+18h], rdi
0x14000379d  mov     rax, cs:qword_14001A190
0x1400037a4  cmp     rax, cs:P
0x1400037ab  jbe     loc_140003AFF
0x1400037b1  sub     rax, 20h ; ' '
0x1400037b5  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x1400037ba  mov     cs:qword_14001A190, rax
0x1400037c1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400037c8  nop     dword ptr [rax+rax+00h]
0x1400037cd  lea     rcx, [rbx+120h]; SpinLock
0x1400037d4  mov     [rsp+58h+arg_0], rsi
0x1400037d9  lea     rdx, [rsp+58h+var_20]; LockHandle
0x1400037de  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400037e5  nop     dword ptr [rax+rax+00h]
0x1400037ea  cmp     [rbx+130h], r14b
0x1400037f1  jnz     loc_14000395E
0x1400037f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037fe  cmp     rcx, rbp
0x140003801  jnz     loc_1400038FD
0x140003807  mov     rsi, r14
0x14000380a  cmp     [rbx+4], r14d
0x14000380e  jz      short loc_140003880
0x140003810  lea     rdi, [rbx+20h]
0x140003814  cmp     [rdi], rdi
0x140003817  jz      loc_140003AE9
0x14000381d  mov     rsi, [rdi+10h]
0x140003821  mov     rax, [rsi]
0x140003824  mov     [rdi+10h], rax
0x140003828  mov     rax, [rsi+10h]
0x14000382c  inc     rax
0x14000382f  mov     [rdi+28h], rax
0x140003833  mov     rax, [rsi]
0x140003836  cmp     [rax+8], rsi
0x14000383a  jnz     loc_140003B0F
0x140003840  mov     rcx, [rsi+8]
0x140003844  cmp     [rcx], rsi
0x140003847  jnz     loc_140003B0F
0x14000384d  mov     [rcx], rax
0x140003850  mov     [rax+8], rcx
0x140003854  mov     rax, [rdi+20h]
0x140003858  dec     dword ptr [rdi+18h]
0x14000385b  test    rax, rax
0x14000385e  jz      short loc_140003863
0x140003860  dec     dword ptr [rax+4]
0x140003863  cmp     [rdi+10h], rdi
0x140003867  jnz     short loc_140003870
0x140003869  mov     rax, [rdi]
0x14000386c  mov     [rdi+10h], rax
0x140003870  add     rsi, 0FFFFFFFFFFFFFF88h
0x140003874  mov     rax, r14
0x140003877  xchg    rax, [rsi+68h]
0x14000387b  test    rax, rax
0x14000387e  jz      short loc_140003807
0x140003880  mov     rcx, cs:WPP_GLOBAL_Control
0x140003887  cmp     rcx, rbp
0x14000388a  jnz     loc_14000392C
0x140003890  test    rsi, rsi
0x140003893  jz      loc_140003961
0x140003899  lea     rcx, [rsp+58h+var_20]; LockHandle
0x14000389e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400038a5  nop     dword ptr [rax+rax+00h]
0x1400038aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038b1  cmp     rcx, rbp
0x1400038b4  jnz     short loc_1400038D5
0x1400038b6  mov     rdi, [rsp+58h+arg_8]
0x1400038bb  mov     rax, rsi
0x1400038be  mov     rsi, [rsp+58h+arg_0]
0x1400038c3  mov     rbx, [rsp+58h+arg_10]
0x1400038c8  mov     rbp, [rsp+58h+arg_18]
0x1400038cd  add     rsp, 50h
0x1400038d1  pop     r14
0x1400038d3  retn
0x1400038d5  mov     edx, [rcx+2Ch]
0x1400038d8  test    dl, 20h
0x1400038db  jz      short loc_1400038B6
0x1400038dd  cmp     byte ptr [rcx+29h], 4
0x1400038e1  jb      short loc_1400038B6
0x1400038e3  mov     rcx, [rcx+18h]
0x1400038e7  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x1400038ee  mov     edx, 1Ah
0x1400038f3  mov     r9, rsi
0x1400038f6  call    WPP_SF_q
0x1400038fb  jmp     short loc_1400038B6
0x1400038fd  mov     eax, [rcx+2Ch]
0x140003900  test    al, 20h
0x140003902  jz      loc_140003807
0x140003908  cmp     byte ptr [rcx+29h], 4
0x14000390c  jb      loc_140003807
0x140003912  mov     rcx, [rcx+18h]
0x140003916  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x14000391d  mov     edx, 22h ; '"'
0x140003922  call    WPP_SF_
0x140003927  jmp     loc_140003807
0x14000392c  mov     eax, [rcx+2Ch]
0x14000392f  test    al, 20h
0x140003931  jz      loc_140003890
0x140003937  cmp     byte ptr [rcx+29h], 4
0x14000393b  jb      loc_140003890
0x140003941  mov     rcx, [rcx+18h]
0x140003945  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x14000394c  mov     edx, 23h ; '#'
0x140003951  mov     r9, rsi
0x140003954  call    WPP_SF_q
0x140003959  jmp     loc_140003890
0x14000395e  mov     rsi, r14
0x140003961  mov     eax, [rbx+12Ch]
0x140003967  cmp     eax, [rbx+128h]
0x14000396d  jl      loc_140003899
0x140003973  lea     r9d, [rax-1]
0x140003977  mov     [rbx+12Ch], r9d
0x14000397e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003985  cmp     rcx, rbp
0x140003988  jz      short loc_140003995
0x14000398a  mov     eax, [rcx+2Ch]
0x14000398d  test    al, 20h
0x14000398f  jnz     loc_140003B57
0x140003995  xor     eax, eax
0x140003997  xorps   xmm0, xmm0
0x14000399a  cmp     cs:P, rax
0x1400039a1  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x1400039a6  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x1400039ab  jz      short loc_140003A2A
0x1400039ad  movsxd  rdi, dword ptr [rbx+12Ch]
0x1400039b4  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x1400039b9  lea     rcx, SpinLock; SpinLock
0x1400039c0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400039c7  nop     dword ptr [rax+rax+00h]
0x1400039cc  mov     rax, cs:qword_14001A190
0x1400039d3  mov     dword ptr [rax], 4F636544h
0x1400039d9  mov     rax, cs:qword_14001A190
0x1400039e0  mov     [rax+8], rbx
0x1400039e4  mov     rax, cs:qword_14001A190
0x1400039eb  mov     [rax+10h], r14
0x1400039ef  mov     rax, cs:qword_14001A190
0x1400039f6  mov     [rax+18h], rdi
0x1400039fa  mov     rax, cs:qword_14001A190
0x140003a01  cmp     rax, cs:P
0x140003a08  jbe     loc_140003B16
0x140003a0e  sub     rax, 20h ; ' '
0x140003a12  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x140003a17  mov     cs:qword_14001A190, rax
0x140003a1e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003a25  nop     dword ptr [rax+rax+00h]
0x140003a2a  cmp     [rbx+130h], r14b
0x140003a31  jz      loc_140003899
0x140003a37  lea     rcx, [rbx+148h]; Event
0x140003a3e  xor     r8d, r8d; Wait
0x140003a41  xor     edx, edx; Increment
0x140003a43  call    cs:__imp_KeSetEvent
0x140003a4a  nop     dword ptr [rax+rax+00h]
0x140003a4f  xor     eax, eax
0x140003a51  xorps   xmm0, xmm0
0x140003a54  cmp     cs:P, rax
0x140003a5b  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x140003a60  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x140003a65  jz      loc_140003899
0x140003a6b  movsxd  rdi, dword ptr [rbx+12Ch]
0x140003a72  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x140003a77  lea     rcx, SpinLock; SpinLock
0x140003a7e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003a85  nop     dword ptr [rax+rax+00h]
0x140003a8a  mov     rax, cs:qword_14001A190
0x140003a91  mov     dword ptr [rax], 47534551h
0x140003a97  mov     rax, cs:qword_14001A190
0x140003a9e  mov     [rax+8], rbx
0x140003aa2  mov     rax, cs:qword_14001A190
0x140003aa9  mov     [rax+10h], r14
0x140003aad  mov     rax, cs:qword_14001A190
0x140003ab4  mov     [rax+18h], rdi
0x140003ab8  mov     rax, cs:qword_14001A190
0x140003abf  cmp     rax, cs:P
0x140003ac6  jbe     short loc_140003B26
0x140003ac8  sub     rax, 20h ; ' '
0x140003acc  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x140003ad1  mov     cs:qword_14001A190, rax
0x140003ad8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003adf  nop     dword ptr [rax+rax+00h]
0x140003ae4  jmp     loc_140003899
0x140003ae9  mov     rcx, rbx
0x140003aec  call    PortAvioSchedulerTransferBatch
0x140003af1  cmp     [rdi], rdi
0x140003af4  jnz     loc_14000381D
0x140003afa  jmp     loc_140003870
0x140003aff  mov     rax, cs:qword_14001A198
0x140003b06  add     rax, 0FFFFFFFFFFFFFFE0h
0x140003b0a  jmp     loc_1400037B5
0x140003b0f  mov     ecx, 3
0x140003b14  int     29h; Win8: RtlFailFast(ecx)
0x140003b16  mov     rax, cs:qword_14001A198
0x140003b1d  add     rax, 0FFFFFFFFFFFFFFE0h
0x140003b21  jmp     loc_140003A12
0x140003b26  mov     rax, cs:qword_14001A198
0x140003b2d  add     rax, 0FFFFFFFFFFFFFFE0h
0x140003b31  jmp     short loc_140003ACC
0x140003b33  cmp     byte ptr [rcx+29h], 4
0x140003b37  jb      loc_140003730
0x140003b3d  mov     rcx, [rcx+18h]
0x140003b41  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x140003b48  mov     edx, 18h
0x140003b4d  call    WPP_SF_
0x140003b52  jmp     loc_140003730
0x140003b57  cmp     byte ptr [rcx+29h], 4
0x140003b5b  jb      loc_140003995
0x140003b61  mov     rcx, [rcx+18h]
0x140003b65  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x140003b6c  mov     edx, 19h
0x140003b71  call    WPP_SF_d
0x140003b76  jmp     loc_140003995
```
