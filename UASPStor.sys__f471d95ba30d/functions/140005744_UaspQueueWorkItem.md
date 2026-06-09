# UaspQueueWorkItem

- ea: `0x140005744`
- end: `0x14000593c`
- name: `UaspQueueWorkItem`
- size: `504`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140002320`
- `0x140004070`
- `0x140007010`
- `0x1400072c0`
- `0x140008430`
- `0x140008720`
- `0x140008e00`
- `0x14000a450`

## callees

- `0x140004adc`
- `0x1400052b8`
- `0x140005744`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400058a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400058a2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400057f7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000586b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400057f7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000586b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400057ad`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400057ad`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000577a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000577a`
- `ntoskrnl!IoQueueWorkItem` at `0x14000588c`
- `ntoskrnl!IoQueueWorkItem` at `0x14000588c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140005806`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140005806`
- `storport!StorPortNotification` at `0x1400058c4`
- `storport!StorPortNotification` at `0x1400058c4`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400058f5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400058f5`

## pseudocode

```c
__int64 __fastcall UaspQueueWorkItem(__int64 a1, IO_WORKITEM_ROUTINE *a2, __int64 a3, __int64 a4)
{
  struct _EX_RUNDOWN_REF *v4; // rdi
  __int64 v9; // rcx
  int v10; // ebx
  _QWORD *Pool; // rbp
  _QWORD *v12; // r14
  _QWORD *v13; // r13
  _QWORD *v14; // rcx
  _QWORD *v15; // rdi
  _QWORD *v16; // rcx
  __int64 Default; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-68h] BYREF

  v4 = (struct _EX_RUNDOWN_REF *)(a1 + 1288);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 1288)) )
  {
    v10 = -1073741738;
LABEL_21:
    if ( a3 )
    {
      *(_BYTE *)(a3 + 3) = 4;
      StorPortNotification(0, a1, a3);
    }
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_iD(Default, 2u, 1u, 0x14u, (__int64)WPP_36185c522d943f8d0ee1935152861c3e_Traceguids, a3, v10);
    }
    return (unsigned int)v10;
  }
  Pool = (_QWORD *)UaspAllocatePool(v9, 48);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 128), &LockHandle);
  v12 = (_QWORD *)(a1 + 1352);
  v13 = *(_QWORD **)(a1 + 1352);
  v14 = v13;
  if ( v13 != (_QWORD *)(a1 + 1352) )
  {
    while ( (IO_WORKITEM_ROUTINE *)*(v14 - 1) != a2 || *(v14 - 2) != a4 )
    {
      v14 = (_QWORD *)*v14;
      if ( v14 == v12 )
        goto LABEL_7;
    }
    v10 = -2147483631;
    goto LABEL_10;
  }
LABEL_7:
  if ( *(_BYTE *)(a1 + 1296) )
  {
    if ( !Pool )
    {
      v10 = -1073741670;
LABEL_10:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      ExReleaseRundownProtection(v4);
      goto LABEL_18;
    }
    v15 = Pool;
    Pool = 0;
  }
  else
  {
    v15 = (_QWORD *)(a1 + 1304);
    *(_BYTE *)(a1 + 1296) = 1;
  }
  *v15 = a1;
  v15[3] = a2;
  v15[1] = a3;
  v15[2] = a4;
  v16 = *(_QWORD **)(a1 + 1360);
  if ( (_QWORD *)*v16 != v12 )
    __fastfail(3u);
  v10 = 0;
  v15[5] = v16;
  v15[4] = v12;
  *v16 = v15 + 4;
  *(_QWORD *)(a1 + 1360) = v15 + 4;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v13 == v12 )
    IoQueueWorkItem(*(PIO_WORKITEM *)(a1 + 200), a2, CriticalWorkQueue, v15);
LABEL_18:
  if ( Pool )
    ExFreePoolWithTag(Pool, 0);
  if ( v10 < 0 )
    goto LABEL_21;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005744  push    rbx
0x140005746  push    rbp
0x140005747  push    rsi
0x140005748  push    rdi
0x140005749  push    r12
0x14000574b  push    r13
0x14000574d  push    r14
0x14000574f  push    r15
0x140005751  sub     rsp, 68h
0x140005755  lea     rdi, [rcx+508h]
0x14000575c  mov     rsi, rcx
0x14000575f  xorps   xmm0, xmm0
0x140005762  xor     eax, eax
0x140005764  mov     rcx, rdi; RunRef
0x140005767  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14000576c  mov     rbx, r9
0x14000576f  mov     r15, r8
0x140005772  mov     r12, rdx
0x140005775  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14000577a  call    cs:__imp_ExAcquireRundownProtection
0x140005781  nop     dword ptr [rax+rax+00h]
0x140005786  test    al, al
0x140005788  jnz     short loc_140005794
0x14000578a  mov     ebx, 0C0000056h
0x14000578f  jmp     loc_1400058B2
0x140005794  mov     edx, 30h ; '0'
0x140005799  call    UaspAllocatePool
0x14000579e  lea     rcx, [rsi+80h]; SpinLock
0x1400057a5  mov     rbp, rax
0x1400057a8  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x1400057ad  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400057b4  nop     dword ptr [rax+rax+00h]
0x1400057b9  lea     r14, [rsi+548h]
0x1400057c0  mov     r13, [r14]
0x1400057c3  mov     rcx, r13
0x1400057c6  cmp     r13, r14
0x1400057c9  jz      short loc_1400057DF
0x1400057cb  cmp     [rcx-8], r12
0x1400057cf  jnz     short loc_1400057D7
0x1400057d1  cmp     [rcx-10h], rbx
0x1400057d5  jz      short loc_140005817
0x1400057d7  mov     rcx, [rcx]
0x1400057da  cmp     rcx, r14
0x1400057dd  jnz     short loc_1400057CB
0x1400057df  cmp     byte ptr [rsi+510h], 0
0x1400057e6  jz      short loc_140005825
0x1400057e8  test    rbp, rbp
0x1400057eb  jnz     short loc_14000581E
0x1400057ed  mov     ebx, 0C000009Ah
0x1400057f2  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x1400057f7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400057fe  nop     dword ptr [rax+rax+00h]
0x140005803  mov     rcx, rdi; RunRef
0x140005806  call    cs:__imp_ExReleaseRundownProtection
0x14000580d  nop     dword ptr [rax+rax+00h]
0x140005812  jmp     loc_140005898
0x140005817  mov     ebx, 80000011h
0x14000581c  jmp     short loc_1400057F2
0x14000581e  mov     rdi, rbp
0x140005821  xor     ebp, ebp
0x140005823  jmp     short loc_140005833
0x140005825  lea     rdi, [rsi+518h]
0x14000582c  mov     byte ptr [rsi+510h], 1
0x140005833  mov     [rdi], rsi
0x140005836  mov     [rdi+18h], r12
0x14000583a  mov     [rdi+8], r15
0x14000583e  mov     [rdi+10h], rbx
0x140005842  mov     rcx, [r14+8]
0x140005846  cmp     [rcx], r14
0x140005849  jz      short loc_140005852
0x14000584b  mov     ecx, 3
0x140005850  int     29h; Win8: RtlFailFast(ecx)
0x140005852  lea     rax, [rdi+20h]
0x140005856  xor     ebx, ebx
0x140005858  mov     [rax+8], rcx
0x14000585c  mov     [rax], r14
0x14000585f  mov     [rcx], rax
0x140005862  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140005867  mov     [r14+8], rax
0x14000586b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140005872  nop     dword ptr [rax+rax+00h]
0x140005877  cmp     r13, r14
0x14000587a  jnz     short loc_140005898
0x14000587c  mov     rcx, [rsi+0C8h]; IoWorkItem
0x140005883  mov     r9, rdi; Context
0x140005886  xor     r8d, r8d; QueueType
0x140005889  mov     rdx, r12; WorkerRoutine
0x14000588c  call    cs:__imp_IoQueueWorkItem
0x140005893  nop     dword ptr [rax+rax+00h]
0x140005898  test    rbp, rbp
0x14000589b  jz      short loc_1400058AE
0x14000589d  xor     edx, edx; Tag
0x14000589f  mov     rcx, rbp; P
0x1400058a2  call    cs:__imp_ExFreePoolWithTag
0x1400058a9  nop     dword ptr [rax+rax+00h]
0x1400058ae  test    ebx, ebx
0x1400058b0  jns     short loc_140005928
0x1400058b2  test    r15, r15
0x1400058b5  jz      short loc_1400058D0
0x1400058b7  mov     r8, r15
0x1400058ba  mov     byte ptr [r15+3], 4
0x1400058bf  mov     rdx, rsi
0x1400058c2  xor     ecx, ecx
0x1400058c4  call    cs:__imp_StorPortNotification
0x1400058cb  nop     dword ptr [rax+rax+00h]
0x1400058d0  cmp     cs:gTracingEnabled, 0
0x1400058d7  jz      short loc_140005928
0x1400058d9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400058e0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400058e7  jz      short loc_140005928
0x1400058e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400058f0  mov     edi, 14h
0x1400058f5  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400058fc  nop     dword ptr [rax+rax+00h]
0x140005901  mov     [rsp+0A8h+var_78], ebx
0x140005905  lea     r8d, [rdi-13h]
0x140005909  mov     rcx, rax
0x14000590c  mov     [rsp+0A8h+var_80], r15
0x140005911  lea     rax, WPP_36185c522d943f8d0ee1935152861c3e_Traceguids
0x140005918  movzx   r9d, di
0x14000591c  mov     dl, 2
0x14000591e  mov     [rsp+0A8h+var_88], rax
0x140005923  call    WPP_RECORDER_SF_iD
0x140005928  mov     eax, ebx
0x14000592a  add     rsp, 68h
0x14000592e  pop     r15
0x140005930  pop     r14
0x140005932  pop     r13
0x140005934  pop     r12
0x140005936  pop     rdi
0x140005937  pop     rsi
0x140005938  pop     rbp
0x140005939  pop     rbx
0x14000593a  retn
```
