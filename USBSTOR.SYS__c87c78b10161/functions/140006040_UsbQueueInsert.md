# UsbQueueInsert

- ea: `0x140006040`
- end: `0x140006902`
- name: `UsbQueueInsert`
- size: `2242`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140004ed0`

## callees

- `0x140003630`
- `0x140006040`
- `0x14000acd0`
- `0x14000f9f0`
- `0x1400105e8`
- `0x140010664`
- `0x140010e74`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140006552`
- `ntoskrnl!IofCompleteRequest` at `0x140006552`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400060c4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000614c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400061da`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006480`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400060c4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000614c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400061da`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006480`
- `ntoskrnl!IoGetSfioStreamIdentifier` at `0x1400062c3`
- `ntoskrnl!IoGetSfioStreamIdentifier` at `0x140006349`
- `ntoskrnl!IoGetSfioStreamIdentifier` at `0x140006824`
- `ntoskrnl!IoGetSfioStreamIdentifier` at `0x1400062c3`
- `ntoskrnl!IoGetSfioStreamIdentifier` at `0x140006349`
- `ntoskrnl!IoGetSfioStreamIdentifier` at `0x140006824`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006122`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006238`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006249`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400064de`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400064ef`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006122`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006238`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006249`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400064de`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400064ef`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400062db`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400062db`

## pseudocode

```c
__int64 __fastcall UsbQueueInsert(__int64 a1, __int64 a2, int a3, int a4)
{
  int *v8; // r13
  __int64 v9; // rbx
  __int64 v10; // rax
  unsigned __int8 v11; // di
  __int64 v12; // rbx
  __int64 v13; // rax
  _QWORD *v14; // r12
  unsigned int v15; // ebx
  __int64 v16; // rcx
  IRP *v17; // rdi
  IO_PRIORITY_HINT IoPriorityHint; // eax
  char *v19; // rbp
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // rdx
  int v23; // ecx
  _QWORD *i; // rax
  _QWORD *v25; // rcx
  __int64 v26; // r8
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // r9
  __int64 v30; // rax
  char v31; // si
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v35; // rcx
  _QWORD *v36; // rax
  _QWORD *v37; // rax
  char *SfioStreamIdentifier; // rax
  _QWORD *j; // r8
  int v40; // r9d
  struct _KLOCK_QUEUE_HANDLE v41; // [rsp+20h] [rbp-58h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-40h] BYREF

  memset(&v41, 0, sizeof(v41));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  v8 = (int *)(a1 + 300);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    v9 = *v8;
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1920167497;
    *(_QWORD *)(qword_14001A190 + 8) = a1;
    *(_QWORD *)(qword_14001A190 + 16) = a2;
    *(_QWORD *)(qword_14001A190 + 24) = v9;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v10 = qword_14001A198 - 32;
    else
      v10 = qword_14001A190 - 32;
    qword_14001A190 = v10;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  *(_DWORD *)(a2 + 136) = a3;
  v11 = 0;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 288), &v41);
  if ( a4 == 1 )
  {
    if ( *v8 >= *(_DWORD *)(a1 + 296) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
        v8 = (int *)(a1 + 300);
      }
      v11 = 1;
      v35 = 1114861129;
    }
    else
    {
      *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
      ++*v8;
      *(_QWORD *)(a1 + 352) = a2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
        v8 = (int *)(a1 + 300);
      }
      v35 = 1348693577;
    }
    USBSTOR_LogEntry(v35, a1, a2, *v8);
    goto LABEL_17;
  }
  if ( a4 != 2 && *v8 < *(_DWORD *)(a1 + 296) && !*(_BYTE *)(a1 + 304) )
  {
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    ++*v8;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
    }
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      v12 = *v8;
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 1331916361;
      *(_QWORD *)(qword_14001A190 + 8) = a1;
      *(_QWORD *)(qword_14001A190 + 16) = a2;
      *(_QWORD *)(qword_14001A190 + 24) = v12;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v13 = qword_14001A198 - 32;
      else
        v13 = qword_14001A190 - 32;
      qword_14001A190 = v13;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
LABEL_17:
    KeReleaseInStackQueuedSpinLock(&v41);
    goto LABEL_59;
  }
  *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  v14 = (_QWORD *)(a2 + 120);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  v15 = 2;
  v16 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
  if ( v16 )
  {
    v17 = *(IRP **)(v16 + 56);
    if ( v17 )
    {
      if ( IoGetSfioStreamIdentifier(v17->Tail.Overlay.OriginalFileObject, (PVOID)(a1 + 256)) )
      {
        IoPriorityHint = IoPriorityCritical|IoPriorityNormal;
      }
      else
      {
        IoPriorityHint = IoGetIoPriorityHint(v17);
        if ( (unsigned int)IoPriorityHint <= IoPriorityLow )
          IoPriorityHint = IoPriorityNormal;
      }
      v15 = IoPriorityHint;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
    }
  }
  v19 = 0;
  v20 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
  if ( v20 )
  {
    v21 = *(_QWORD *)(v20 + 56);
    if ( v21 )
    {
      if ( IoGetSfioStreamIdentifier(*(PFILE_OBJECT *)(v21 + 192), (PVOID)(a1 + 256)) )
      {
        SfioStreamIdentifier = (char *)IoGetSfioStreamIdentifier(*(PFILE_OBJECT *)(v21 + 192), (PVOID)(a1 + 256));
        v19 = SfioStreamIdentifier + 24;
        if ( !SfioStreamIdentifier )
          v19 = 0;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids, v19);
  }
  if ( v15 > 5 )
  {
    PortListInsertRequest(v19, a2 + 120);
  }
  else
  {
    if ( v15 != 4 )
    {
      v22 = a1 + 56LL * (v15 - 1) + 88;
      v23 = *(_DWORD *)(v22 + 48);
      if ( !v23 )
      {
        for ( i = *(_QWORD **)v22; i != (_QWORD *)v22; i = (_QWORD *)*i )
        {
          if ( *(_QWORD *)(a2 + 136) < i[2] )
            break;
        }
        v25 = (_QWORD *)i[1];
        if ( (_QWORD *)*v25 == i )
        {
          *v14 = i;
          *(_QWORD *)(a2 + 128) = v25;
          *v25 = v14;
          i[1] = v14;
          v26 = *(_QWORD *)(v22 + 16);
          if ( v26 == v22 )
          {
            *(_QWORD *)(v22 + 16) = *(_QWORD *)v22;
          }
          else
          {
            v27 = *(_QWORD *)(v22 + 40);
            v28 = *(_QWORD *)(a2 + 136);
            if ( v28 >= v27 )
            {
              v29 = *(_QWORD *)(v26 + 16);
              if ( v28 < v29 || v29 < v27 )
                *(_QWORD *)(v22 + 16) = v14;
            }
          }
          goto LABEL_48;
        }
LABEL_69:
        __fastfail(3u);
      }
      if ( v23 == 2 )
      {
        for ( j = *(_QWORD **)v22; j != (_QWORD *)v22; j = (_QWORD *)*j )
        {
          v40 = 0;
          while ( *((_DWORD *)v14 + (unsigned int)(1 - v40) + 4) == *((_DWORD *)j + (unsigned int)(1 - v40) + 4) )
          {
            if ( (unsigned int)++v40 >= 2 )
            {
              if ( v40 == 2 )
                goto LABEL_115;
              break;
            }
          }
          if ( *((_DWORD *)v14 + (unsigned int)(1 - v40) + 4) <= *((_DWORD *)j + (unsigned int)(1 - v40) + 4) )
            break;
LABEL_115:
          ;
        }
        v37 = (_QWORD *)j[1];
        if ( (_QWORD *)*v37 != j )
          goto LABEL_69;
        *v14 = j;
        *(_QWORD *)(a2 + 128) = v37;
        *v37 = v14;
        j[1] = v14;
        *(_QWORD *)(v22 + 16) = *(_QWORD *)v22;
      }
      else
      {
        v36 = *(_QWORD **)(v22 + 8);
        if ( *v36 != v22 )
          goto LABEL_69;
        *v14 = v22;
        *(_QWORD *)(a2 + 128) = v36;
        *v36 = v14;
        *(_QWORD *)(v22 + 8) = v14;
        *(_QWORD *)(v22 + 16) = *(_QWORD *)v22;
      }
LABEL_48:
      v30 = *(_QWORD *)(v22 + 32);
      ++*(_DWORD *)(v22 + 24);
      if ( v30 )
        ++*(_DWORD *)(v30 + 4);
      goto LABEL_50;
    }
    PortListInsertRequest(a1 + 32, a2 + 120);
  }
LABEL_50:
  v31 = 0;
  _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)&UsbCancelIo);
  if ( *(_BYTE *)(a2 + 68) && _InterlockedExchange64((volatile __int64 *)(a2 + 104), 0) )
  {
    UsbRemoveIrp(a1, a2);
    v31 = 1;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  v11 = 1;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    v32 = *v8;
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1232301641;
    *(_QWORD *)(qword_14001A190 + 8) = a1;
    *(_QWORD *)(qword_14001A190 + 16) = a2;
    *(_QWORD *)(qword_14001A190 + 24) = v32;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v33 = qword_14001A198 - 32;
    else
      v33 = qword_14001A190 - 32;
    qword_14001A190 = v33;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  KeReleaseInStackQueuedSpinLock(&v41);
  if ( v31 )
  {
    *(_DWORD *)(a2 + 48) = -1073741536;
    *(_QWORD *)(a2 + 56) = 0;
    IofCompleteRequest((PIRP)a2, 0);
  }
LABEL_59:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  return v11;
}

```

## disassembly

```asm
0x140006040  push    rbp
0x140006042  push    rsi
0x140006043  push    rdi
0x140006044  push    r14
0x140006046  push    r15
0x140006048  sub     rsp, 50h
0x14000604c  xorps   xmm0, xmm0
0x14000604f  xor     eax, eax
0x140006051  movups  xmmword ptr [rsp+78h+var_58.LockQueue.Next], xmm0
0x140006056  mov     qword ptr [rsp+78h+var_58.OldIrql], rax
0x14000605b  mov     esi, r9d
0x14000605e  mov     edi, r8d
0x140006061  mov     r14, rdx
0x140006064  mov     r15, rcx
0x140006067  mov     rcx, cs:WPP_GLOBAL_Control
0x14000606e  lea     rbp, WPP_GLOBAL_Control
0x140006075  cmp     rcx, rbp
0x140006078  jz      short loc_140006085
0x14000607a  mov     eax, [rcx+2Ch]
0x14000607d  test    al, 20h
0x14000607f  jnz     loc_1400066E1
0x140006085  xor     eax, eax
0x140006087  mov     [rsp+78h+arg_0], rbx
0x14000608f  cmp     cs:P, rax
0x140006096  xorps   xmm0, xmm0
0x140006099  mov     [rsp+78h+arg_10], r13
0x1400060a1  lea     r13, [r15+12Ch]
0x1400060a8  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1400060ad  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x1400060b2  jz      short loc_14000612E
0x1400060b4  movsxd  rbx, dword ptr [r13+0]
0x1400060b8  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1400060bd  lea     rcx, SpinLock; SpinLock
0x1400060c4  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400060cb  nop     dword ptr [rax+rax+00h]
0x1400060d0  mov     rax, cs:qword_14001A190
0x1400060d7  mov     dword ptr [rax], 72736E49h
0x1400060dd  mov     rax, cs:qword_14001A190
0x1400060e4  mov     [rax+8], r15
0x1400060e8  mov     rax, cs:qword_14001A190
0x1400060ef  mov     [rax+10h], r14
0x1400060f3  mov     rax, cs:qword_14001A190
0x1400060fa  mov     [rax+18h], rbx
0x1400060fe  mov     rax, cs:qword_14001A190
0x140006105  cmp     rax, cs:P
0x14000610c  jbe     loc_1400065B8
0x140006112  sub     rax, 20h ; ' '
0x140006116  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000611b  mov     cs:qword_14001A190, rax
0x140006122  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140006129  nop     dword ptr [rax+rax+00h]
0x14000612e  mov     [r14+88h], edi
0x140006135  lea     rcx, [r15+120h]; SpinLock
0x14000613c  lea     rdx, [rsp+78h+var_58]; LockHandle
0x140006141  mov     [rsp+78h+arg_8], r12
0x140006149  xor     dil, dil
0x14000614c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140006153  nop     dword ptr [rax+rax+00h]
0x140006158  cmp     esi, 1
0x14000615b  jz      loc_1400065E0
0x140006161  cmp     esi, 2
0x140006164  jz      loc_14000625A
0x14000616a  mov     eax, [r15+128h]
0x140006171  cmp     [r13+0], eax
0x140006175  jge     loc_14000625A
0x14000617b  cmp     [r15+130h], dil
0x140006182  jnz     loc_14000625A
0x140006188  mov     rax, [r14+0B8h]
0x14000618f  or      byte ptr [rax+3], 1
0x140006193  inc     dword ptr [r13+0]
0x140006197  mov     r9d, [r13+0]
0x14000619b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400061a2  cmp     rcx, rbp
0x1400061a5  jz      short loc_1400061B2
0x1400061a7  mov     eax, [rcx+2Ch]
0x1400061aa  test    al, 20h
0x1400061ac  jnz     loc_14000665B
0x1400061b2  xor     eax, eax
0x1400061b4  xorps   xmm0, xmm0
0x1400061b7  cmp     cs:P, rax
0x1400061be  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1400061c3  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x1400061c8  jz      short loc_140006244
0x1400061ca  movsxd  rbx, dword ptr [r13+0]
0x1400061ce  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1400061d3  lea     rcx, SpinLock; SpinLock
0x1400061da  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400061e1  nop     dword ptr [rax+rax+00h]
0x1400061e6  mov     rax, cs:qword_14001A190
0x1400061ed  mov     dword ptr [rax], 4F636E49h
0x1400061f3  mov     rax, cs:qword_14001A190
0x1400061fa  mov     [rax+8], r15
0x1400061fe  mov     rax, cs:qword_14001A190
0x140006205  mov     [rax+10h], r14
0x140006209  mov     rax, cs:qword_14001A190
0x140006210  mov     [rax+18h], rbx
0x140006214  mov     rax, cs:qword_14001A190
0x14000621b  cmp     rax, cs:P
0x140006222  jbe     loc_14000664B
0x140006228  sub     rax, 20h ; ' '
0x14000622c  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140006231  mov     cs:qword_14001A190, rax
0x140006238  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000623f  nop     dword ptr [rax+rax+00h]
0x140006244  lea     rcx, [rsp+78h+var_58]; LockHandle
0x140006249  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140006250  nop     dword ptr [rax+rax+00h]
0x140006255  jmp     loc_140006500
0x14000625a  mov     rax, [r14+0B8h]
0x140006261  or      byte ptr [rax+3], 1
0x140006265  mov     rcx, cs:WPP_GLOBAL_Control
0x14000626c  cmp     rcx, rbp
0x14000626f  jz      short loc_14000627C
0x140006271  mov     eax, [rcx+2Ch]
0x140006274  test    al, 20h
0x140006276  jnz     loc_140006772
0x14000627c  lea     r12, [r14+78h]
0x140006280  mov     rcx, cs:WPP_GLOBAL_Control
0x140006287  cmp     rcx, rbp
0x14000628a  jz      short loc_140006297
0x14000628c  mov     eax, [rcx+2Ch]
0x14000628f  test    al, 20h
0x140006291  jnz     loc_140006796
0x140006297  mov     rax, [r14+0B8h]
0x14000629e  mov     ebx, 2
0x1400062a3  mov     rcx, [rax+8]
0x1400062a7  test    rcx, rcx
0x1400062aa  jz      short loc_1400062F2
0x1400062ac  mov     rdi, [rcx+38h]
0x1400062b0  test    rdi, rdi
0x1400062b3  jz      short loc_1400062F2
0x1400062b5  mov     rcx, [rdi+0C0h]; FileObject
0x1400062bc  lea     rdx, [r15+100h]; Signature
0x1400062c3  call    cs:__imp_IoGetSfioStreamIdentifier
0x1400062ca  nop     dword ptr [rax+rax+00h]
0x1400062cf  test    rax, rax
0x1400062d2  jnz     loc_1400067BA
0x1400062d8  mov     rcx, rdi; Irp
0x1400062db  call    cs:__imp_IoGetIoPriorityHint
0x1400062e2  nop     dword ptr [rax+rax+00h]
0x1400062e7  cmp     eax, 1
0x1400062ea  jbe     loc_1400067C4
0x1400062f0  mov     ebx, eax
0x1400062f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062f9  cmp     rcx, rbp
0x1400062fc  jz      short loc_140006320
0x1400062fe  mov     eax, [rcx+2Ch]
0x140006301  test    al, 20h
0x140006303  jnz     loc_1400067CB
0x140006309  mov     rcx, cs:WPP_GLOBAL_Control
0x140006310  cmp     rcx, rbp
0x140006313  jz      short loc_140006320
0x140006315  mov     eax, [rcx+2Ch]
0x140006318  test    al, 20h
0x14000631a  jnz     loc_1400067F2
0x140006320  mov     rax, [r14+0B8h]
0x140006327  xor     ebp, ebp
0x140006329  mov     rcx, [rax+8]
0x14000632d  test    rcx, rcx
0x140006330  jz      short loc_14000635E
0x140006332  mov     rdi, [rcx+38h]
0x140006336  test    rdi, rdi
0x140006339  jz      short loc_14000635E
0x14000633b  mov     rcx, [rdi+0C0h]; FileObject
0x140006342  lea     rdx, [r15+100h]; Signature
0x140006349  call    cs:__imp_IoGetSfioStreamIdentifier
0x140006350  nop     dword ptr [rax+rax+00h]
0x140006355  test    rax, rax
0x140006358  jnz     loc_140006816
0x14000635e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006365  lea     rax, WPP_GLOBAL_Control
0x14000636c  cmp     rcx, rax
0x14000636f  jz      short loc_14000637C
0x140006371  mov     eax, [rcx+2Ch]
0x140006374  test    al, 20h
0x140006376  jnz     loc_140006842
0x14000637c  cmp     ebx, 5
0x14000637f  ja      loc_14000667F
0x140006385  cmp     ebx, 4
0x140006388  jz      loc_1400065CF
0x14000638e  lea     ecx, [rbx-1]
0x140006391  imul    rdx, rcx, 38h ; '8'
0x140006395  add     rdx, 58h ; 'X'
0x140006399  add     rdx, r15
0x14000639c  mov     ecx, [rdx+30h]
0x14000639f  test    ecx, ecx
0x1400063a1  jnz     loc_140006869
0x1400063a7  mov     rax, [rdx]
0x1400063aa  cmp     rax, rdx
0x1400063ad  jz      short loc_1400063C2
0x1400063af  mov     rcx, [r12+10h]
0x1400063b4  cmp     rcx, [rax+10h]
0x1400063b8  jb      short loc_1400063C2
0x1400063ba  mov     rax, [rax]
0x1400063bd  cmp     rax, rdx
0x1400063c0  jnz     short loc_1400063B4
0x1400063c2  mov     rcx, [rax+8]
0x1400063c6  cmp     [rcx], rax
0x1400063c9  jnz     loc_1400065C8
0x1400063cf  mov     [r12], rax
0x1400063d3  mov     [r12+8], rcx
0x1400063d8  mov     [rcx], r12
0x1400063db  mov     [rax+8], r12
0x1400063df  mov     r8, [rdx+10h]
0x1400063e3  cmp     r8, rdx
0x1400063e6  jz      loc_140006560
0x1400063ec  mov     rcx, [rdx+28h]
0x1400063f0  mov     rax, [r12+10h]
0x1400063f5  cmp     rax, rcx
0x1400063f8  jb      short loc_140006410
0x1400063fa  mov     r9, [r8+10h]
0x1400063fe  cmp     rax, r9
0x140006401  jb      loc_14000658D
0x140006407  cmp     r9, rcx
0x14000640a  jb      loc_14000658D
0x140006410  mov     rax, [rdx+20h]
0x140006414  inc     dword ptr [rdx+18h]
0x140006417  test    rax, rax
0x14000641a  jz      short loc_14000641F
0x14000641c  inc     dword ptr [rax+4]
0x14000641f  lea     rax, UsbCancelIo
0x140006426  xor     sil, sil
0x140006429  xchg    rax, [r14+68h]
0x14000642d  cmp     [r14+44h], sil
0x140006431  jnz     loc_140006596
0x140006437  mov     rcx, cs:WPP_GLOBAL_Control
0x14000643e  lea     rbp, WPP_GLOBAL_Control
0x140006445  cmp     rcx, rbp
0x140006448  jz      short loc_140006455
0x14000644a  mov     eax, [rcx+2Ch]
0x14000644d  test    al, 20h
0x14000644f  jnz     loc_1400068DE
0x140006455  xor     eax, eax
0x140006457  xorps   xmm0, xmm0
0x14000645a  cmp     cs:P, rax
0x140006461  mov     dil, 1
0x140006464  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140006469  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14000646e  jz      short loc_1400064EA
0x140006470  movsxd  rbx, dword ptr [r13+0]
0x140006474  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140006479  lea     rcx, SpinLock; SpinLock
0x140006480  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140006487  nop     dword ptr [rax+rax+00h]
0x14000648c  mov     rax, cs:qword_14001A190
0x140006493  mov     dword ptr [rax], 49736E49h
0x140006499  mov     rax, cs:qword_14001A190
0x1400064a0  mov     [rax+8], r15
0x1400064a4  mov     rax, cs:qword_14001A190
0x1400064ab  mov     [rax+10h], r14
0x1400064af  mov     rax, cs:qword_14001A190
0x1400064b6  mov     [rax+18h], rbx
0x1400064ba  mov     rax, cs:qword_14001A190
0x1400064c1  cmp     rax, cs:P
0x1400064c8  jbe     loc_14000663B
0x1400064ce  sub     rax, 20h ; ' '
0x1400064d2  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400064d7  mov     cs:qword_14001A190, rax
0x1400064de  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400064e5  nop     dword ptr [rax+rax+00h]
0x1400064ea  lea     rcx, [rsp+78h+var_58]; LockHandle
0x1400064ef  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400064f6  nop     dword ptr [rax+rax+00h]
0x1400064fb  test    sil, sil
0x1400064fe  jnz     short loc_14000653D
0x140006500  mov     rcx, cs:WPP_GLOBAL_Control
0x140006507  cmp     rcx, rbp
0x14000650a  jz      short loc_140006514
0x14000650c  mov     edx, [rcx+2Ch]
0x14000650f  test    dl, 20h
0x140006512  jnz     short loc_14000656C
0x140006514  mov     r13, [rsp+78h+arg_10]
0x14000651c  movzx   eax, dil
0x140006520  mov     r12, [rsp+78h+arg_8]
0x140006528  mov     rbx, [rsp+78h+arg_0]
0x140006530  add     rsp, 50h
0x140006534  pop     r15
0x140006536  pop     r14
0x140006538  pop     rdi
0x140006539  pop     rsi
0x14000653a  pop     rbp
0x14000653b  retn
0x14000653d  xor     edx, edx; PriorityBoost
0x14000653f  mov     dword ptr [r14+30h], 0C0000120h
0x140006547  mov     rcx, r14; Irp
0x14000654a  mov     qword ptr [r14+38h], 0
0x140006552  call    cs:__imp_IofCompleteRequest
0x140006559  nop     dword ptr [rax+rax+00h]
0x14000655e  jmp     short loc_140006500
0x140006560  mov     rax, [rdx]
0x140006563  mov     [rdx+10h], rax
0x140006567  jmp     loc_140006410
0x14000656c  cmp     byte ptr [rcx+29h], 4
0x140006570  jb      short loc_140006514
0x140006572  mov     rcx, [rcx+18h]
0x140006576  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x14000657d  movzx   r9d, dil
0x140006581  mov     edx, 17h
0x140006586  call    WPP_SF_d
0x14000658b  jmp     short loc_140006514
  ... truncated ...
```
