# USBSTOR_DataCompletion

- ea: `0x1400023b0`
- end: `0x140002a69`
- name: `USBSTOR_DataCompletion`
- size: `1721`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140001008`
- `0x140001130`
- `0x1400023b0`
- `0x140002a70`
- `0x140003630`
- `0x140004910`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140002931`
- `ntoskrnl!KeSetEvent` at `0x140002931`
- `ntoskrnl!IoFreeMdl` at `0x14000281b`
- `ntoskrnl!IoFreeMdl` at `0x14000281b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002410`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400024de`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000256f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002644`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002729`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000295e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002410`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400024de`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000256f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002644`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002729`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000295e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000246d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000250a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400025cc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400026a1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002786`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400028eb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400029b7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000246d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000250a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400025cc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400026a1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002786`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400028eb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400029b7`

## pseudocode

```c
__int64 __fastcall USBSTOR_DataCompletion(_QWORD *a1, IRP *a2)
{
  __int64 Status; // rbx
  __int64 v5; // rax
  _DWORD *v6; // rbx
  PIO_SECURITY_CONTEXT SecurityContext; // r15
  struct _MDL *v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // r12
  char v11; // cl
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v15; // rdi
  __int64 v16; // rax
  _DWORD *v17; // rdi
  bool v18; // zf
  char v19; // al
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-20h] BYREF
  PVOID Context; // [rsp+90h] [rbp+40h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+98h] [rbp+48h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 154, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    Status = a2->IoStatus.Status;
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1128549186;
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
    Context = v6;
    v6 = (_DWORD *)a1[8];
  }
  else
  {
    Context = 0;
    if ( *v6 != 558842950 )
    {
      v6 = 0;
      a1 = 0;
    }
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( SecurityContext == *((PIO_SECURITY_CONTEXT *)v6 + 146) )
  {
    v8 = (struct _MDL *)*((_QWORD *)v6 + 55);
    if ( v8 != a2->MdlAddress )
      IoFreeMdl(v8);
  }
  v9 = a1[8];
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v9 + 144), &LockHandle);
  *(_DWORD *)(v9 + 128) &= ~2u;
  if ( (*(_DWORD *)(v9 + 128) & 8) != 0 )
  {
    USBSTOR_LogEntry(827609667, a1, a2, SecurityContext);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v22 = *(_QWORD *)(v9 + 1168);
    a2->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId = v22;
    a2->IoStatus.Status = -1073741643;
    a2->IoStatus.Information = 0;
    *(_BYTE *)(v22 + 3) = 9;
    USBSTOR_TranslateCDBComplete(a1, (__int64)a2, v22);
    KeSetEvent((PRKEVENT)(v9 + 336), 0, 0);
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 828664674;
      *(_QWORD *)(qword_14001A190 + 8) = a1;
      *(_QWORD *)(qword_14001A190 + 16) = a2;
      *(_QWORD *)(qword_14001A190 + 24) = SecurityContext;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v23 = qword_14001A198 - 32;
      else
        v23 = qword_14001A190 - 32;
      qword_14001A190 = v23;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 3221225494LL;
  }
  *(_QWORD *)(v9 + 328) = 0;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v10 = a2->IoStatus.Status;
  if ( (int)v10 >= 0 )
  {
    v11 = 18;
    if ( v6[107] >= SecurityContext->DesiredAccess )
      v11 = 1;
    BYTE3(SecurityContext->SecurityQos) = v11;
    SecurityContext->DesiredAccess = v6[107];
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      v12 = (unsigned int)v6[107];
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 895773538;
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
    USBSTOR_CswTransfer(a1, a2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 3221225494LL;
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    v15 = (int)v6[99];
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 845441890;
    *(_QWORD *)(qword_14001A190 + 8) = v10;
    *(_QWORD *)(qword_14001A190 + 16) = v15;
    *(_QWORD *)(qword_14001A190 + 24) = 0;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v16 = qword_14001A198 - 32;
    else
      v16 = qword_14001A190 - 32;
    qword_14001A190 = v16;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  v17 = v6 + 99;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v17 = v6 + 99;
    WPP_SF_DD(
      WPP_GLOBAL_Control->AttachedDevice,
      156,
      WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
      (unsigned int)a2->IoStatus.Status,
      v6[99]);
  }
  if ( (*v17 & 0xFFFFFFF) == 4 )
  {
    ++v6[428];
    v18 = (HIDWORD(SecurityContext->AccessState) & 0x800) == 0;
    SecurityContext->DesiredAccess = v6[107];
    v19 = 6;
    if ( v18 )
      v19 = 18;
    BYTE3(SecurityContext->SecurityQos) = v19;
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 862219106;
      *(_QWORD *)(qword_14001A190 + 8) = a1;
      *(_QWORD *)(qword_14001A190 + 16) = a2;
      *(_QWORD *)(qword_14001A190 + 24) = SecurityContext;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v20 = qword_14001A198 - 32;
      else
        v20 = qword_14001A190 - 32;
      qword_14001A190 = v20;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    USBSTOR_BulkQueueResetPipe(a1, a2);
    return 3221225494LL;
  }
  USBSTOR_LogEntry(878996322, a1, a2, SecurityContext);
  v21 = *((_QWORD *)v6 + 146);
  CurrentStackLocation->Parameters.WMI.ProviderId = v21;
  a2->IoStatus.Status = -1073741435;
  a2->IoStatus.Information = 0;
  *(_BYTE *)(v21 + 3) = 14;
  USBSTOR_TranslateCDBComplete(a1, (__int64)a2, v21);
  USBSTOR_QueueResetDevice(a1, Context);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 157, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return 3221225861LL;
}

```

## disassembly

```asm
0x1400023b0  mov     [rsp-38h+arg_10], rbx
0x1400023b5  push    rbp
0x1400023b6  push    rsi
0x1400023b7  push    rdi
0x1400023b8  push    r12
0x1400023ba  push    r13
0x1400023bc  push    r14
0x1400023be  push    r15
0x1400023c0  mov     rbp, rsp
0x1400023c3  sub     rsp, 50h
0x1400023c7  mov     r14, rdx
0x1400023ca  mov     rsi, rcx
0x1400023cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023d4  lea     r12, WPP_GLOBAL_Control
0x1400023db  cmp     rcx, r12
0x1400023de  jz      short loc_1400023EB
0x1400023e0  mov     eax, [rcx+2Ch]
0x1400023e3  test    al, 1
0x1400023e5  jnz     loc_14000282C
0x1400023eb  xor     eax, eax
0x1400023ed  xorps   xmm0, xmm0
0x1400023f0  cmp     cs:P, rax
0x1400023f7  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400023fb  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400023ff  jz      short loc_140002479
0x140002401  movsxd  rbx, dword ptr [r14+30h]
0x140002405  lea     rdx, [rbp+LockHandle]; LockHandle
0x140002409  lea     rcx, SpinLock; SpinLock
0x140002410  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002417  nop     dword ptr [rax+rax+00h]
0x14000241c  mov     rax, cs:qword_14001A190
0x140002423  mov     dword ptr [rax], 43444B42h
0x140002429  mov     rax, cs:qword_14001A190
0x140002430  mov     [rax+8], rsi
0x140002434  mov     rax, cs:qword_14001A190
0x14000243b  mov     [rax+10h], r14
0x14000243f  mov     rax, cs:qword_14001A190
0x140002446  mov     [rax+18h], rbx
0x14000244a  mov     rax, cs:qword_14001A190
0x140002451  cmp     rax, cs:P
0x140002458  jbe     loc_1400027E1
0x14000245e  sub     rax, 20h ; ' '
0x140002462  lea     rcx, [rbp+LockHandle]; LockHandle
0x140002466  mov     cs:qword_14001A190, rax
0x14000246d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002474  nop     dword ptr [rax+rax+00h]
0x140002479  mov     rbx, [rsi+40h]
0x14000247d  xor     r13d, r13d
0x140002480  mov     eax, [rbx]
0x140002482  cmp     eax, 214F4450h
0x140002487  jnz     loc_140002801
0x14000248d  mov     rsi, [rbx+10h]
0x140002491  mov     [rbp+Context], rbx
0x140002495  mov     rbx, [rsi+40h]
0x140002499  mov     rax, [r14+0B8h]
0x1400024a0  mov     [rbp+arg_8], rax
0x1400024a4  mov     r15, [rax+8]
0x1400024a8  cmp     r15, [rbx+490h]
0x1400024af  jnz     short loc_1400024C2
0x1400024b1  mov     rcx, [rbx+1B8h]; Mdl
0x1400024b8  cmp     rcx, [r14+8]
0x1400024bc  jnz     loc_14000281B
0x1400024c2  mov     rdi, [rsi+40h]
0x1400024c6  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400024ca  xorps   xmm0, xmm0
0x1400024cd  xor     eax, eax
0x1400024cf  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400024d3  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400024d7  lea     rcx, [rdi+90h]; SpinLock
0x1400024de  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400024e5  nop     dword ptr [rax+rax+00h]
0x1400024ea  and     dword ptr [rdi+80h], 0FFFFFFFDh
0x1400024f1  mov     eax, [rdi+80h]
0x1400024f7  test    al, 8
0x1400024f9  jnz     loc_1400028D4
0x1400024ff  lea     rcx, [rbp+LockHandle]; LockHandle
0x140002503  mov     [rdi+148h], r13
0x14000250a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002511  nop     dword ptr [rax+rax+00h]
0x140002516  movsxd  r12, dword ptr [r14+30h]
0x14000251a  xorps   xmm0, xmm0
0x14000251d  test    r12d, r12d
0x140002520  js      loc_14000261F
0x140002526  mov     eax, [r15+10h]
0x14000252a  mov     ecx, 12h
0x14000252f  cmp     [rbx+1ACh], eax
0x140002535  mov     edx, 1
0x14000253a  cmovnb  ecx, edx
0x14000253d  mov     [r15+3], cl
0x140002541  mov     eax, [rbx+1ACh]
0x140002547  mov     [r15+10h], eax
0x14000254b  xor     eax, eax
0x14000254d  cmp     cs:P, rax
0x140002554  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140002558  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14000255c  jz      short loc_1400025D8
0x14000255e  mov     ebx, [rbx+1ACh]
0x140002564  lea     rdx, [rbp+LockHandle]; LockHandle
0x140002568  lea     rcx, SpinLock; SpinLock
0x14000256f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002576  nop     dword ptr [rax+rax+00h]
0x14000257b  mov     rax, cs:qword_14001A190
0x140002582  mov     dword ptr [rax], 35646B62h
0x140002588  mov     rax, cs:qword_14001A190
0x14000258f  mov     [rax+8], rsi
0x140002593  mov     rax, cs:qword_14001A190
0x14000259a  mov     [rax+10h], r14
0x14000259e  mov     rax, cs:qword_14001A190
0x1400025a5  mov     [rax+18h], rbx
0x1400025a9  mov     rax, cs:qword_14001A190
0x1400025b0  cmp     rax, cs:P
0x1400025b7  jbe     loc_1400027F1
0x1400025bd  sub     rax, 20h ; ' '
0x1400025c1  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400025c5  mov     cs:qword_14001A190, rax
0x1400025cc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400025d3  nop     dword ptr [rax+rax+00h]
0x1400025d8  mov     rdx, r14; Irp
0x1400025db  mov     rcx, rsi; Object
0x1400025de  call    USBSTOR_CswTransfer
0x1400025e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025ea  lea     r12, WPP_GLOBAL_Control
0x1400025f1  cmp     rcx, r12
0x1400025f4  jz      short loc_140002601
0x1400025f6  mov     eax, [rcx+2Ch]
0x1400025f9  test    al, 1
0x1400025fb  jnz     loc_140002A3F
0x140002601  mov     eax, 0C0000016h
0x140002606  mov     rbx, [rsp+50h+arg_10]
0x14000260e  add     rsp, 50h
0x140002612  pop     r15
0x140002614  pop     r14
0x140002616  pop     r13
0x140002618  pop     r12
0x14000261a  pop     rdi
0x14000261b  pop     rsi
0x14000261c  pop     rbp
0x14000261d  retn
0x14000261f  xor     eax, eax
0x140002621  cmp     cs:P, rax
0x140002628  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14000262c  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140002630  jz      short loc_1400026AD
0x140002632  movsxd  rdi, dword ptr [rbx+18Ch]
0x140002639  lea     rdx, [rbp+LockHandle]; LockHandle
0x14000263d  lea     rcx, SpinLock; SpinLock
0x140002644  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000264b  nop     dword ptr [rax+rax+00h]
0x140002650  mov     rax, cs:qword_14001A190
0x140002657  mov     dword ptr [rax], 32646B62h
0x14000265d  mov     rax, cs:qword_14001A190
0x140002664  mov     [rax+8], r12
0x140002668  mov     rax, cs:qword_14001A190
0x14000266f  mov     [rax+10h], rdi
0x140002673  mov     rax, cs:qword_14001A190
0x14000267a  mov     [rax+18h], r13
0x14000267e  mov     rax, cs:qword_14001A190
0x140002685  cmp     rax, cs:P
0x14000268c  jbe     loc_1400028B4
0x140002692  sub     rax, 20h ; ' '
0x140002696  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000269a  mov     cs:qword_14001A190, rax
0x1400026a1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400026a8  nop     dword ptr [rax+rax+00h]
0x1400026ad  lea     rdi, [rbx+18Ch]
0x1400026b4  lea     r9, [r14+30h]
0x1400026b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026bf  lea     r12, WPP_GLOBAL_Control
0x1400026c6  cmp     rcx, r12
0x1400026c9  jnz     loc_1400027A2
0x1400026cf  mov     eax, [rdi]
0x1400026d1  and     eax, 0FFFFFFFh
0x1400026d6  cmp     eax, 4
0x1400026d9  jnz     loc_140002850
0x1400026df  inc     dword ptr [rbx+6B0h]
0x1400026e5  mov     ecx, 12h
0x1400026ea  mov     eax, [rbx+1ACh]
0x1400026f0  xorps   xmm0, xmm0
0x1400026f3  test    dword ptr [r15+0Ch], 800h
0x1400026fb  mov     [r15+10h], eax
0x1400026ff  mov     eax, 6
0x140002704  cmovz   eax, ecx
0x140002707  mov     [r15+3], al
0x14000270b  xor     eax, eax
0x14000270d  cmp     cs:P, rax
0x140002714  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140002718  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14000271c  jz      short loc_140002792
0x14000271e  lea     rdx, [rbp+LockHandle]; LockHandle
0x140002722  lea     rcx, SpinLock; SpinLock
0x140002729  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002730  nop     dword ptr [rax+rax+00h]
0x140002735  mov     rax, cs:qword_14001A190
0x14000273c  mov     dword ptr [rax], 33646B62h
0x140002742  mov     rax, cs:qword_14001A190
0x140002749  mov     [rax+8], rsi
0x14000274d  mov     rax, cs:qword_14001A190
0x140002754  mov     [rax+10h], r14
0x140002758  mov     rax, cs:qword_14001A190
0x14000275f  mov     [rax+18h], r15
0x140002763  mov     rax, cs:qword_14001A190
0x14000276a  cmp     rax, cs:P
0x140002771  jbe     loc_1400028C4
0x140002777  sub     rax, 20h ; ' '
0x14000277b  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000277f  mov     cs:qword_14001A190, rax
0x140002786  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000278d  nop     dword ptr [rax+rax+00h]
0x140002792  mov     rdx, r14; Context
0x140002795  mov     rcx, rsi; Object
0x140002798  call    USBSTOR_BulkQueueResetPipe
0x14000279d  jmp     loc_140002601
0x1400027a2  mov     eax, [rcx+2Ch]
0x1400027a5  test    al, 1
0x1400027a7  jz      loc_1400026CF
0x1400027ad  cmp     byte ptr [rcx+29h], 2
0x1400027b1  jb      loc_1400026CF
0x1400027b7  mov     r9d, [r9]
0x1400027ba  lea     rdi, [rbx+18Ch]
0x1400027c1  mov     eax, [rdi]
0x1400027c3  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400027ca  mov     rcx, [rcx+18h]
0x1400027ce  mov     edx, 9Ch
0x1400027d3  mov     [rsp+50h+var_30], eax
0x1400027d7  call    WPP_SF_DD
0x1400027dc  jmp     loc_1400026CF
0x1400027e1  mov     rax, cs:qword_14001A198
0x1400027e8  add     rax, 0FFFFFFFFFFFFFFE0h
0x1400027ec  jmp     loc_140002462
0x1400027f1  mov     rax, cs:qword_14001A198
0x1400027f8  add     rax, 0FFFFFFFFFFFFFFE0h
0x1400027fc  jmp     loc_1400025C1
0x140002801  mov     [rbp+Context], r13
0x140002805  cmp     eax, 214F4446h
0x14000280a  jz      loc_140002499
0x140002810  mov     rbx, r13
0x140002813  mov     rsi, r13
0x140002816  jmp     loc_140002499
0x14000281b  call    cs:__imp_IoFreeMdl
0x140002822  nop     dword ptr [rax+rax+00h]
0x140002827  jmp     loc_1400024C2
0x14000282c  cmp     byte ptr [rcx+29h], 5
0x140002830  jb      loc_1400023EB
0x140002836  mov     rcx, [rcx+18h]
0x14000283a  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140002841  mov     edx, 9Ah
0x140002846  call    WPP_SF_
0x14000284b  jmp     loc_1400023EB
0x140002850  mov     r9, r15
0x140002853  mov     r8, r14
0x140002856  mov     rdx, rsi
0x140002859  mov     ecx, 34646B62h
0x14000285e  call    USBSTOR_LogEntry
0x140002863  mov     r8, [rbx+490h]
0x14000286a  mov     rdx, r14
0x14000286d  mov     rax, [rbp+arg_8]
0x140002871  mov     rcx, rsi; Object
0x140002874  mov     [rax+8], r8
0x140002878  mov     dword ptr [r14+30h], 0C0000185h
0x140002880  mov     [r14+38h], r13
0x140002884  mov     byte ptr [r8+3], 0Eh
0x140002889  call    USBSTOR_TranslateCDBComplete
0x14000288e  mov     rdx, [rbp+Context]; Context
0x140002892  mov     rcx, rsi; Object
0x140002895  call    USBSTOR_QueueResetDevice
0x14000289a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028a1  cmp     rcx, r12
0x1400028a4  jnz     loc_140002A0F
0x1400028aa  mov     eax, 0C0000185h
0x1400028af  jmp     loc_140002606
0x1400028b4  mov     rax, cs:qword_14001A198
0x1400028bb  add     rax, 0FFFFFFFFFFFFFFE0h
0x1400028bf  jmp     loc_140002696
0x1400028c4  mov     rax, cs:qword_14001A198
0x1400028cb  add     rax, 0FFFFFFFFFFFFFFE0h
0x1400028cf  jmp     loc_14000277B
0x1400028d4  mov     r9, r15
0x1400028d7  mov     r8, r14
0x1400028da  mov     rdx, rsi
0x1400028dd  mov     ecx, 31545243h
0x1400028e2  call    USBSTOR_LogEntry
0x1400028e7  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400028eb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400028f2  nop     dword ptr [rax+rax+00h]
0x1400028f7  mov     r8, [rdi+490h]
0x1400028fe  mov     rdx, r14
0x140002901  mov     rax, [r14+0B8h]
0x140002908  mov     rcx, rsi; Object
0x14000290b  mov     [rax+8], r8
0x14000290f  mov     dword ptr [r14+30h], 0C00000B5h
0x140002917  mov     [r14+38h], r13
0x14000291b  mov     byte ptr [r8+3], 9
0x140002920  call    USBSTOR_TranslateCDBComplete
0x140002925  lea     rcx, [rdi+150h]; Event
0x14000292c  xor     r8d, r8d; Wait
0x14000292f  xor     edx, edx; Increment
0x140002931  call    cs:__imp_KeSetEvent
0x140002938  nop     dword ptr [rax+rax+00h]
0x14000293d  xor     eax, eax
0x14000293f  xorps   xmm0, xmm0
  ... truncated ...
```
