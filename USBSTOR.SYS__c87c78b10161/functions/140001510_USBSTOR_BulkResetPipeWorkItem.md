# USBSTOR_BulkResetPipeWorkItem

- ea: `0x140001510`
- end: `0x140001944`
- name: `USBSTOR_BulkResetPipeWorkItem`
- size: `1076`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001510`
- `0x140001950`
- `0x140002a70`
- `0x1400105e8`
- `0x140010664`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140001696`
- `ntoskrnl!ExAllocatePool2` at `0x140001696`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400016cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400016cb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000154e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000161c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001712`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400017b3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000154e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000161c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001712`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400017b3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001831`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001831`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400015ac`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000167a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001773`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001811`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400015ac`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000167a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001773`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001811`

## pseudocode

```c
void __fastcall USBSTOR_BulkResetPipeWorkItem(_QWORD *IoObject, IRP *Context, PIO_WORKITEM IoWorkItem)
{
  __int64 v5; // rax
  __int64 v6; // rbp
  __int64 v7; // r14
  __int64 v8; // rax
  __int64 Pool2; // rax
  void *v10; // rsi
  int v11; // r14d
  __int64 v12; // rax
  __int64 v13; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-68h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1464881730;
    *(_QWORD *)(qword_14001A190 + 8) = IoObject;
    *(_QWORD *)(qword_14001A190 + 16) = Context;
    *(_QWORD *)(qword_14001A190 + 24) = 0;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v5 = qword_14001A198 - 32;
    else
      v5 = qword_14001A190 - 32;
    qword_14001A190 = v5;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  v6 = IoObject[8];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 169, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  v7 = *(_QWORD *)(v6 + 416);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 166, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1347634514;
    *(_QWORD *)(qword_14001A190 + 8) = IoObject;
    *(_QWORD *)(qword_14001A190 + 16) = v7;
    *(_QWORD *)(qword_14001A190 + 24) = 0;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v8 = qword_14001A198 - 32;
    else
      v8 = qword_14001A190 - 32;
    qword_14001A190 = v8;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  Pool2 = ExAllocatePool2(64, 40, 1396788565);
  v10 = (void *)Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 1966120;
    *(_QWORD *)(Pool2 + 24) = v7;
    v11 = USBSTOR_SyncSendUsbRequest(IoObject, Pool2);
    ExFreePoolWithTag(v10, 0);
  }
  else
  {
    v11 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 167, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1886610802;
    *(_QWORD *)(qword_14001A190 + 8) = v11;
    *(_QWORD *)(qword_14001A190 + 16) = 0;
    *(_QWORD *)(qword_14001A190 + 24) = 0;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v12 = qword_14001A198 - 32;
    else
      v12 = qword_14001A190 - 32;
    qword_14001A190 = v12;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( Context )
    USBSTOR_CswTransfer(IoObject, Context);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 2003858018;
    *(_QWORD *)(qword_14001A190 + 8) = IoObject;
    *(_QWORD *)(qword_14001A190 + 16) = Context;
    *(_QWORD *)(qword_14001A190 + 24) = 0;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v13 = qword_14001A198 - 32;
    else
      v13 = qword_14001A190 - 32;
    qword_14001A190 = v13;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v6 + 1832), USBSTOR_BulkResetPipeWorkItem, 0x20u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 170, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
}

```

## disassembly

```asm
0x140001510  push    rbx
0x140001512  push    rbp
0x140001513  push    rsi
0x140001514  push    rdi
0x140001515  push    r12
0x140001517  push    r13
0x140001519  push    r14
0x14000151b  push    r15
0x14000151d  sub     rsp, 48h
0x140001521  xor     eax, eax
0x140001523  xor     r12d, r12d
0x140001526  cmp     cs:P, rax
0x14000152d  xorps   xmm0, xmm0
0x140001530  mov     rdi, rdx
0x140001533  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x140001538  mov     rbx, rcx
0x14000153b  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x140001540  jz      short loc_1400015B8
0x140001542  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x140001547  lea     rcx, SpinLock; SpinLock
0x14000154e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140001555  nop     dword ptr [rax+rax+00h]
0x14000155a  mov     rax, cs:qword_14001A190
0x140001561  mov     dword ptr [rax], 57505242h
0x140001567  mov     rax, cs:qword_14001A190
0x14000156e  mov     [rax+8], rbx
0x140001572  mov     rax, cs:qword_14001A190
0x140001579  mov     [rax+10h], rdi
0x14000157d  mov     rax, cs:qword_14001A190
0x140001584  mov     [rax+18h], r12
0x140001588  mov     rax, cs:qword_14001A190
0x14000158f  cmp     rax, cs:P
0x140001596  jbe     loc_140001871
0x14000159c  sub     rax, 20h ; ' '
0x1400015a0  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x1400015a5  mov     cs:qword_14001A190, rax
0x1400015ac  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400015b3  nop     dword ptr [rax+rax+00h]
0x1400015b8  mov     rbp, [rbx+40h]
0x1400015bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015c3  lea     r15, WPP_GLOBAL_Control
0x1400015ca  cmp     rcx, r15
0x1400015cd  jz      short loc_1400015DA
0x1400015cf  mov     eax, [rcx+2Ch]
0x1400015d2  test    al, 1
0x1400015d4  jnz     loc_1400018B1
0x1400015da  mov     r14, [rbp+1A0h]
0x1400015e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015e8  cmp     rcx, r15
0x1400015eb  jz      short loc_1400015F8
0x1400015ed  mov     eax, [rcx+2Ch]
0x1400015f0  test    al, 1
0x1400015f2  jnz     loc_1400018D5
0x1400015f8  xor     eax, eax
0x1400015fa  xorps   xmm0, xmm0
0x1400015fd  cmp     cs:P, rax
0x140001604  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x140001609  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14000160e  jz      short loc_140001686
0x140001610  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x140001615  lea     rcx, SpinLock; SpinLock
0x14000161c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140001623  nop     dword ptr [rax+rax+00h]
0x140001628  mov     rax, cs:qword_14001A190
0x14000162f  mov     dword ptr [rax], 50534552h
0x140001635  mov     rax, cs:qword_14001A190
0x14000163c  mov     [rax+8], rbx
0x140001640  mov     rax, cs:qword_14001A190
0x140001647  mov     [rax+10h], r14
0x14000164b  mov     rax, cs:qword_14001A190
0x140001652  mov     [rax+18h], r12
0x140001656  mov     rax, cs:qword_14001A190
0x14000165d  cmp     rax, cs:P
0x140001664  jbe     loc_140001881
0x14000166a  sub     rax, 20h ; ' '
0x14000166e  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x140001673  mov     cs:qword_14001A190, rax
0x14000167a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140001681  nop     dword ptr [rax+rax+00h]
0x140001686  mov     edx, 28h ; '('
0x14000168b  mov     ecx, 40h ; '@'
0x140001690  mov     r8d, 53414D55h
0x140001696  call    cs:__imp_ExAllocatePool2
0x14000169d  nop     dword ptr [rax+rax+00h]
0x1400016a2  mov     rsi, rax
0x1400016a5  test    rax, rax
0x1400016a8  jz      loc_140001866
0x1400016ae  mov     rdx, rax
0x1400016b1  mov     dword ptr [rax], 1E0028h
0x1400016b7  mov     rcx, rbx
0x1400016ba  mov     [rax+18h], r14
0x1400016be  call    USBSTOR_SyncSendUsbRequest
0x1400016c3  xor     edx, edx; Tag
0x1400016c5  mov     rcx, rsi; P
0x1400016c8  mov     r14d, eax
0x1400016cb  call    cs:__imp_ExFreePoolWithTag
0x1400016d2  nop     dword ptr [rax+rax+00h]
0x1400016d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400016de  cmp     rcx, r15
0x1400016e1  jz      short loc_1400016EE
0x1400016e3  mov     eax, [rcx+2Ch]
0x1400016e6  test    al, 1
0x1400016e8  jnz     loc_1400018F9
0x1400016ee  xor     eax, eax
0x1400016f0  xorps   xmm0, xmm0
0x1400016f3  cmp     cs:P, rax
0x1400016fa  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x1400016ff  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x140001704  jz      short loc_14000177F
0x140001706  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14000170b  lea     rcx, SpinLock; SpinLock
0x140001712  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140001719  nop     dword ptr [rax+rax+00h]
0x14000171e  mov     rax, cs:qword_14001A190
0x140001725  movsxd  rcx, r14d
0x140001728  mov     dword ptr [rax], 70736572h
0x14000172e  mov     rax, cs:qword_14001A190
0x140001735  mov     [rax+8], rcx
0x140001739  mov     rax, cs:qword_14001A190
0x140001740  mov     [rax+10h], r12
0x140001744  mov     rax, cs:qword_14001A190
0x14000174b  mov     [rax+18h], r12
0x14000174f  mov     rax, cs:qword_14001A190
0x140001756  cmp     rax, cs:P
0x14000175d  jbe     loc_140001891
0x140001763  sub     rax, 20h ; ' '
0x140001767  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14000176c  mov     cs:qword_14001A190, rax
0x140001773  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000177a  nop     dword ptr [rax+rax+00h]
0x14000177f  test    rdi, rdi
0x140001782  jz      short loc_14000178F
0x140001784  mov     rdx, rdi; Irp
0x140001787  mov     rcx, rbx; Object
0x14000178a  call    USBSTOR_CswTransfer
0x14000178f  xor     eax, eax
0x140001791  xorps   xmm0, xmm0
0x140001794  cmp     cs:P, rax
0x14000179b  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x1400017a0  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x1400017a5  jz      short loc_14000181D
0x1400017a7  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x1400017ac  lea     rcx, SpinLock; SpinLock
0x1400017b3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400017ba  nop     dword ptr [rax+rax+00h]
0x1400017bf  mov     rax, cs:qword_14001A190
0x1400017c6  mov     dword ptr [rax], 77707262h
0x1400017cc  mov     rax, cs:qword_14001A190
0x1400017d3  mov     [rax+8], rbx
0x1400017d7  mov     rax, cs:qword_14001A190
0x1400017de  mov     [rax+10h], rdi
0x1400017e2  mov     rax, cs:qword_14001A190
0x1400017e9  mov     [rax+18h], r12
0x1400017ed  mov     rax, cs:qword_14001A190
0x1400017f4  cmp     rax, cs:P
0x1400017fb  jbe     loc_1400018A1
0x140001801  sub     rax, 20h ; ' '
0x140001805  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14000180a  mov     cs:qword_14001A190, rax
0x140001811  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140001818  nop     dword ptr [rax+rax+00h]
0x14000181d  lea     rcx, [rbp+728h]; RemoveLock
0x140001824  mov     r8d, 20h ; ' '; RemlockSize
0x14000182a  lea     rdx, USBSTOR_BulkResetPipeWorkItem; Tag
0x140001831  call    cs:__imp_IoReleaseRemoveLockEx
0x140001838  nop     dword ptr [rax+rax+00h]
0x14000183d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001844  cmp     rcx, r15
0x140001847  jz      short loc_140001854
0x140001849  mov     eax, [rcx+2Ch]
0x14000184c  test    al, 1
0x14000184e  jnz     loc_140001920
0x140001854  add     rsp, 48h
0x140001858  pop     r15
0x14000185a  pop     r14
0x14000185c  pop     r13
0x14000185e  pop     r12
0x140001860  pop     rdi
0x140001861  pop     rsi
0x140001862  pop     rbp
0x140001863  pop     rbx
0x140001864  retn
0x140001866  mov     r14d, 0C000009Ah
0x14000186c  jmp     loc_1400016D7
0x140001871  mov     rax, cs:qword_14001A198
0x140001878  add     rax, 0FFFFFFFFFFFFFFE0h
0x14000187c  jmp     loc_1400015A0
0x140001881  mov     rax, cs:qword_14001A198
0x140001888  add     rax, 0FFFFFFFFFFFFFFE0h
0x14000188c  jmp     loc_14000166E
0x140001891  mov     rax, cs:qword_14001A198
0x140001898  add     rax, 0FFFFFFFFFFFFFFE0h
0x14000189c  jmp     loc_140001767
0x1400018a1  mov     rax, cs:qword_14001A198
0x1400018a8  add     rax, 0FFFFFFFFFFFFFFE0h
0x1400018ac  jmp     loc_140001805
0x1400018b1  cmp     byte ptr [rcx+29h], 5
0x1400018b5  jb      loc_1400015DA
0x1400018bb  mov     rcx, [rcx+18h]
0x1400018bf  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400018c6  mov     edx, 0A9h
0x1400018cb  call    WPP_SF_
0x1400018d0  jmp     loc_1400015DA
0x1400018d5  cmp     byte ptr [rcx+29h], 4
0x1400018d9  jb      loc_1400015F8
0x1400018df  mov     rcx, [rcx+18h]
0x1400018e3  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400018ea  mov     edx, 0A6h
0x1400018ef  call    WPP_SF_
0x1400018f4  jmp     loc_1400015F8
0x1400018f9  cmp     byte ptr [rcx+29h], 4
0x1400018fd  jb      loc_1400016EE
0x140001903  mov     rcx, [rcx+18h]
0x140001907  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14000190e  mov     edx, 0A7h
0x140001913  mov     r9d, r14d
0x140001916  call    WPP_SF_d
0x14000191b  jmp     loc_1400016EE
0x140001920  cmp     byte ptr [rcx+29h], 5
0x140001924  jb      loc_140001854
0x14000192a  mov     rcx, [rcx+18h]
0x14000192e  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140001935  mov     edx, 0AAh
0x14000193a  call    WPP_SF_
0x14000193f  jmp     loc_140001854
```
