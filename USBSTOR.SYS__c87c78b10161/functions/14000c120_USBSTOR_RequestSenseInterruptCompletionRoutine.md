# USBSTOR_RequestSenseInterruptCompletionRoutine

- ea: `0x14000c120`
- end: `0x14000c56a`
- name: `USBSTOR_RequestSenseInterruptCompletionRoutine`
- size: `1098`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140001008`
- `0x140003630`
- `0x140004910`
- `0x14000c120`
- `0x14000fafc`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000c453`
- `ntoskrnl!KeSetEvent` at `0x14000c453`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000c17e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000c236`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000c2b5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000c17e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000c236`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000c2b5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000c1dc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000c267`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000c313`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000c40a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000c1dc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000c267`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000c313`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000c40a`

## pseudocode

```c
__int64 __fastcall USBSTOR_RequestSenseInterruptCompletionRoutine(_QWORD *a1, IRP *a2)
{
  __int64 Status; // rdi
  __int64 v5; // rax
  _DWORD *v6; // rdi
  void *v7; // r12
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v9; // rsi
  __int64 SecurityContext; // r13
  __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rax
  unsigned int v15; // ebx
  __int64 v17; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 130, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    Status = a2->IoStatus.Status;
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1128878930;
    *(_QWORD *)(qword_14001A190 + 8) = a1;
    *(_QWORD *)(qword_14001A190 + 16) = a2;
    *(_QWORD *)(qword_14001A190 + 24) = Status;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v5 = qword_14001A198 - 32;
    else
      v5 = qword_14001A190 - 32;
    qword_14001A190 = v5;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  v6 = (_DWORD *)a1[8];
  if ( *v6 == 558842960 )
  {
    a1 = (_QWORD *)*((_QWORD *)v6 + 2);
    v7 = v6;
    v6 = (_DWORD *)a1[8];
  }
  else
  {
    v7 = 0;
    if ( *v6 != 558842950 )
    {
      v6 = 0;
      a1 = 0;
    }
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v9 = a1[8];
  memset(&LockHandle, 0, sizeof(LockHandle));
  SecurityContext = (__int64)CurrentStackLocation->Parameters.Create.SecurityContext;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v9 + 144), &LockHandle);
  *(_DWORD *)(v9 + 128) &= ~2u;
  if ( (*(_DWORD *)(v9 + 128) & 8) != 0 )
  {
    USBSTOR_LogEntry(827609667, a1, a2, SecurityContext);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v17 = *(_QWORD *)(v9 + 1168);
    a2->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId = v17;
    a2->IoStatus.Status = -1073741643;
    a2->IoStatus.Information = 0;
    *(_BYTE *)(v17 + 3) = 9;
    USBSTOR_TranslateCDBComplete(a1, (__int64)a2, v17);
    KeSetEvent((PRKEVENT)(v9 + 336), 0, 0);
    USBSTOR_LogEntry(828994418, a1, a2, SecurityContext);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 131, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 3221225494LL;
  }
  else
  {
    *(_QWORD *)(v9 + 328) = 0;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v11 = a2->IoStatus.Status;
    if ( (int)v11 < 0 )
    {
      USBSTOR_LogEntry(845771634, a2->IoStatus.Status, (int)v6[99], 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DD(
          WPP_GLOBAL_Control->AttachedDevice,
          132,
          WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
          (unsigned int)a2->IoStatus.Status,
          v6[99]);
      }
      a2->IoStatus.Status = -1073741435;
      a2->IoStatus.Information = 0;
      *(_BYTE *)(SecurityContext + 3) = 14;
      USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
      USBSTOR_QueueResetDevice(a1, v7);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 133, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      return 3221225861LL;
    }
    else
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( P )
      {
        v12 = (unsigned int)v6[107];
        v13 = (int)v6[99];
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_DWORD *)qword_14001A190 = 862548850;
        *(_QWORD *)(qword_14001A190 + 8) = v11;
        *(_QWORD *)(qword_14001A190 + 16) = v13;
        *(_QWORD *)(qword_14001A190 + 24) = v12;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v14 = qword_14001A198 - 32;
        else
          v14 = qword_14001A190 - 32;
        qword_14001A190 = v14;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      v15 = USBSTOR_ProcessRequestSenseCompletion(a1, a2);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 134, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      return v15;
    }
  }
}

```

## disassembly

```asm
0x14000c120  mov     [rsp+arg_8], rbx
0x14000c125  mov     [rsp+arg_10], rbp
0x14000c12a  push    rsi
0x14000c12b  push    rdi
0x14000c12c  push    r13
0x14000c12e  push    r14
0x14000c130  push    r15
0x14000c132  sub     rsp, 50h
0x14000c136  mov     r15, r8
0x14000c139  mov     rbp, rdx
0x14000c13c  mov     rbx, rcx
0x14000c13f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c146  lea     r14, WPP_GLOBAL_Control
0x14000c14d  cmp     rcx, r14
0x14000c150  jnz     loc_14000C3AC
0x14000c156  xor     eax, eax
0x14000c158  xorps   xmm0, xmm0
0x14000c15b  cmp     cs:P, rax
0x14000c162  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14000c167  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14000c16c  jz      short loc_14000C1E8
0x14000c16e  movsxd  rdi, dword ptr [rbp+30h]
0x14000c172  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14000c177  lea     rcx, SpinLock; SpinLock
0x14000c17e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000c185  nop     dword ptr [rax+rax+00h]
0x14000c18a  mov     rax, cs:qword_14001A190
0x14000c191  mov     dword ptr [rax], 43495352h
0x14000c197  mov     rax, cs:qword_14001A190
0x14000c19e  mov     [rax+8], rbx
0x14000c1a2  mov     rax, cs:qword_14001A190
0x14000c1a9  mov     [rax+10h], rbp
0x14000c1ad  mov     rax, cs:qword_14001A190
0x14000c1b4  mov     [rax+18h], rdi
0x14000c1b8  mov     rax, cs:qword_14001A190
0x14000c1bf  cmp     rax, cs:P
0x14000c1c6  jbe     loc_14000C38C
0x14000c1cc  sub     rax, 20h ; ' '
0x14000c1d0  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000c1d5  mov     cs:qword_14001A190, rax
0x14000c1dc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000c1e3  nop     dword ptr [rax+rax+00h]
0x14000c1e8  mov     rdi, [rbx+40h]
0x14000c1ec  mov     [rsp+78h+arg_0], r12
0x14000c1f4  mov     eax, [rdi]
0x14000c1f6  cmp     eax, 214F4450h
0x14000c1fb  jnz     loc_14000C3DB
0x14000c201  mov     rbx, [rdi+10h]
0x14000c205  mov     r12, rdi
0x14000c208  mov     rdi, [rbx+40h]
0x14000c20c  mov     rax, [rbp+0B8h]
0x14000c213  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14000c218  mov     rsi, [rbx+40h]
0x14000c21c  xorps   xmm0, xmm0
0x14000c21f  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14000c224  mov     r13, [rax+8]
0x14000c228  xor     eax, eax
0x14000c22a  lea     rcx, [rsi+90h]; SpinLock
0x14000c231  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14000c236  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000c23d  nop     dword ptr [rax+rax+00h]
0x14000c242  and     dword ptr [rsi+80h], 0FFFFFFFDh
0x14000c249  mov     eax, [rsi+80h]
0x14000c24f  test    al, 8
0x14000c251  jnz     loc_14000C3F2
0x14000c257  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000c25c  mov     qword ptr [rsi+148h], 0
0x14000c267  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000c26e  nop     dword ptr [rax+rax+00h]
0x14000c273  movsxd  r14, dword ptr [rbp+30h]
0x14000c277  test    r14d, r14d
0x14000c27a  js      loc_14000C4AA
0x14000c280  xor     eax, eax
0x14000c282  xorps   xmm0, xmm0
0x14000c285  cmp     cs:P, rax
0x14000c28c  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14000c291  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14000c296  jz      loc_14000C31F
0x14000c29c  mov     esi, [rdi+1ACh]
0x14000c2a2  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14000c2a7  movsxd  rdi, dword ptr [rdi+18Ch]
0x14000c2ae  lea     rcx, SpinLock; SpinLock
0x14000c2b5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000c2bc  nop     dword ptr [rax+rax+00h]
0x14000c2c1  mov     rax, cs:qword_14001A190
0x14000c2c8  mov     dword ptr [rax], 33697372h
0x14000c2ce  mov     rax, cs:qword_14001A190
0x14000c2d5  mov     [rax+8], r14
0x14000c2d9  mov     rax, cs:qword_14001A190
0x14000c2e0  mov     [rax+10h], rdi
0x14000c2e4  mov     rax, cs:qword_14001A190
0x14000c2eb  mov     [rax+18h], rsi
0x14000c2ef  mov     rax, cs:qword_14001A190
0x14000c2f6  cmp     rax, cs:P
0x14000c2fd  jbe     loc_14000C39C
0x14000c303  sub     rax, 20h ; ' '
0x14000c307  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000c30c  mov     cs:qword_14001A190, rax
0x14000c313  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000c31a  nop     dword ptr [rax+rax+00h]
0x14000c31f  mov     r8, r15
0x14000c322  mov     rdx, rbp; Irp
0x14000c325  mov     rcx, rbx; Object
0x14000c328  call    USBSTOR_ProcessRequestSenseCompletion
0x14000c32d  mov     ebx, eax
0x14000c32f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c336  lea     rsi, WPP_GLOBAL_Control
0x14000c33d  cmp     rcx, rsi
0x14000c340  jz      short loc_14000C368
0x14000c342  mov     edx, [rcx+2Ch]
0x14000c345  test    dl, 1
0x14000c348  jz      short loc_14000C368
0x14000c34a  cmp     byte ptr [rcx+29h], 5
0x14000c34e  jb      short loc_14000C368
0x14000c350  mov     rcx, [rcx+18h]
0x14000c354  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000c35b  mov     edx, 86h
0x14000c360  mov     r9d, eax
0x14000c363  call    WPP_SF_d
0x14000c368  mov     eax, ebx
0x14000c36a  mov     r12, [rsp+78h+arg_0]
0x14000c372  lea     r11, [rsp+78h+var_28]
0x14000c377  mov     rbx, [r11+38h]
0x14000c37b  mov     rbp, [r11+40h]
0x14000c37f  mov     rsp, r11
0x14000c382  pop     r15
0x14000c384  pop     r14
0x14000c386  pop     r13
0x14000c388  pop     rdi
0x14000c389  pop     rsi
0x14000c38a  retn
0x14000c38c  mov     rax, cs:qword_14001A198
0x14000c393  add     rax, 0FFFFFFFFFFFFFFE0h
0x14000c397  jmp     loc_14000C1D0
0x14000c39c  mov     rax, cs:qword_14001A198
0x14000c3a3  add     rax, 0FFFFFFFFFFFFFFE0h
0x14000c3a7  jmp     loc_14000C307
0x14000c3ac  mov     eax, [rcx+2Ch]
0x14000c3af  test    al, 1
0x14000c3b1  jz      loc_14000C156
0x14000c3b7  cmp     byte ptr [rcx+29h], 5
0x14000c3bb  jb      loc_14000C156
0x14000c3c1  mov     rcx, [rcx+18h]
0x14000c3c5  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000c3cc  mov     edx, 82h
0x14000c3d1  call    WPP_SF_
0x14000c3d6  jmp     loc_14000C156
0x14000c3db  xor     r12d, r12d
0x14000c3de  cmp     eax, 214F4446h
0x14000c3e3  jz      loc_14000C20C
0x14000c3e9  xor     edi, edi
0x14000c3eb  xor     ebx, ebx
0x14000c3ed  jmp     loc_14000C20C
0x14000c3f2  mov     r9, r13
0x14000c3f5  mov     r8, rbp
0x14000c3f8  mov     rdx, rbx
0x14000c3fb  mov     ecx, 31545243h
0x14000c400  call    USBSTOR_LogEntry
0x14000c405  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000c40a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000c411  nop     dword ptr [rax+rax+00h]
0x14000c416  mov     r8, [rsi+490h]
0x14000c41d  mov     rdx, rbp
0x14000c420  mov     rax, [rbp+0B8h]
0x14000c427  mov     rcx, rbx; Object
0x14000c42a  mov     [rax+8], r8
0x14000c42e  mov     dword ptr [rbp+30h], 0C00000B5h
0x14000c435  mov     qword ptr [rbp+38h], 0
0x14000c43d  mov     byte ptr [r8+3], 9
0x14000c442  call    USBSTOR_TranslateCDBComplete
0x14000c447  lea     rcx, [rsi+150h]; Event
0x14000c44e  xor     r8d, r8d; Wait
0x14000c451  xor     edx, edx; Increment
0x14000c453  call    cs:__imp_KeSetEvent
0x14000c45a  nop     dword ptr [rax+rax+00h]
0x14000c45f  mov     r9, r13
0x14000c462  mov     r8, rbp
0x14000c465  mov     rdx, rbx
0x14000c468  mov     ecx, 31697372h
0x14000c46d  call    USBSTOR_LogEntry
0x14000c472  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c479  cmp     rcx, r14
0x14000c47c  jz      short loc_14000C4A0
0x14000c47e  mov     eax, [rcx+2Ch]
0x14000c481  test    al, 1
0x14000c483  jz      short loc_14000C4A0
0x14000c485  cmp     byte ptr [rcx+29h], 2
0x14000c489  jb      short loc_14000C4A0
0x14000c48b  mov     rcx, [rcx+18h]
0x14000c48f  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000c496  mov     edx, 83h
0x14000c49b  call    WPP_SF_
0x14000c4a0  mov     eax, 0C0000016h
0x14000c4a5  jmp     loc_14000C36A
0x14000c4aa  movsxd  r8, dword ptr [rdi+18Ch]
0x14000c4b1  mov     rdx, r14
0x14000c4b4  xor     r9d, r9d
0x14000c4b7  mov     ecx, 32697372h
0x14000c4bc  call    USBSTOR_LogEntry
0x14000c4c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c4c8  lea     rsi, WPP_GLOBAL_Control
0x14000c4cf  cmp     rcx, rsi
0x14000c4d2  jz      short loc_14000C504
0x14000c4d4  mov     eax, [rcx+2Ch]
0x14000c4d7  test    al, 1
0x14000c4d9  jz      short loc_14000C504
0x14000c4db  cmp     byte ptr [rcx+29h], 2
0x14000c4df  jb      short loc_14000C504
0x14000c4e1  mov     eax, [rdi+18Ch]
0x14000c4e7  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000c4ee  mov     r9d, [rbp+30h]
0x14000c4f2  mov     edx, 84h
0x14000c4f7  mov     rcx, [rcx+18h]
0x14000c4fb  mov     [rsp+78h+var_58], eax
0x14000c4ff  call    WPP_SF_DD
0x14000c504  mov     dword ptr [rbp+30h], 0C0000185h
0x14000c50b  mov     r8, r13
0x14000c50e  mov     qword ptr [rbp+38h], 0
0x14000c516  mov     rdx, rbp
0x14000c519  mov     rcx, rbx; Object
0x14000c51c  mov     byte ptr [r13+3], 0Eh
0x14000c521  call    USBSTOR_TranslateCDBComplete
0x14000c526  mov     rdx, r12; Context
0x14000c529  mov     rcx, rbx; Object
0x14000c52c  call    USBSTOR_QueueResetDevice
0x14000c531  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c538  cmp     rcx, rsi
0x14000c53b  jz      short loc_14000C560
0x14000c53d  mov     edx, [rcx+2Ch]
0x14000c540  test    dl, 1
0x14000c543  jz      short loc_14000C560
0x14000c545  cmp     byte ptr [rcx+29h], 2
0x14000c549  jb      short loc_14000C560
0x14000c54b  mov     rcx, [rcx+18h]
0x14000c54f  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000c556  mov     edx, 85h
0x14000c55b  call    WPP_SF_
0x14000c560  mov     eax, 0C0000185h
0x14000c565  jmp     loc_14000C36A
```
