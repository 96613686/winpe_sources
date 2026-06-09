# USBSTOR_FdoRemoveDevice

- ea: `0x140028da0`
- end: `0x14002912b`
- name: `USBSTOR_FdoRemoveDevice`
- size: `907`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x14000fe70`
- `0x1400105e8`
- `0x140010664`
- `0x14001f188`
- `0x140028da0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x140028e58`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x140028e58`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140028e91`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140028e91`
- `ntoskrnl!PoFxUnregisterDevice` at `0x14002906e`
- `ntoskrnl!PoFxUnregisterDevice` at `0x14002906e`
- `ntoskrnl!IoDetachDevice` at `0x1400290bc`
- `ntoskrnl!IoDetachDevice` at `0x1400290bc`
- `ntoskrnl!IoFreeIrp` at `0x140029030`
- `ntoskrnl!IoFreeIrp` at `0x14002904f`
- `ntoskrnl!IoFreeIrp` at `0x140029030`
- `ntoskrnl!IoFreeIrp` at `0x14002904f`
- `ntoskrnl!IoDeleteDevice` at `0x140028ee3`
- `ntoskrnl!IoDeleteDevice` at `0x1400290cb`
- `ntoskrnl!IoDeleteDevice` at `0x140028ee3`
- `ntoskrnl!IoDeleteDevice` at `0x1400290cb`
- `ntoskrnl!IoFreeMdl` at `0x140028f06`
- `ntoskrnl!IoFreeMdl` at `0x140028f06`
- `ntoskrnl!KeCancelTimer` at `0x140028e7e`
- `ntoskrnl!KeCancelTimer` at `0x140028e7e`
- `ntoskrnl!IofCallDriver` at `0x140029096`
- `ntoskrnl!IofCallDriver` at `0x140029096`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028faf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028fc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029007`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028faf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028fc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029007`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140028e9d`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140028e9d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140028e20`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140028e20`
- `ntoskrnl!IoFreeWorkItem` at `0x140028f25`
- `ntoskrnl!IoFreeWorkItem` at `0x140028f44`
- `ntoskrnl!IoFreeWorkItem` at `0x140028f63`
- `ntoskrnl!IoFreeWorkItem` at `0x140028f25`
- `ntoskrnl!IoFreeWorkItem` at `0x140028f44`
- `ntoskrnl!IoFreeWorkItem` at `0x140028f63`

## pseudocode

```c
__int64 __fastcall USBSTOR_FdoRemoveDevice(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char *DeviceExtension; // rdi
  _QWORD *v5; // rbx
  _QWORD *v6; // rsi
  _QWORD *v7; // rax
  struct _MDL *v8; // rcx
  struct _IO_WORKITEM *v9; // rcx
  struct _IO_WORKITEM *v10; // rcx
  struct _IO_WORKITEM *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  __int64 i; // rbx
  void *v17; // rcx
  void *v18; // rcx
  IRP *v19; // rcx
  IRP *v20; // rcx
  __int64 v21; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1447904594, DeviceObject, Irp, 0);
  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 1832), Irp, File, 1u, 0x20u);
  USBSTOR_CancelInterruptIrp(DeviceExtension);
  USBSTOR_WmiDeregister(DeviceExtension);
  USBSTOR_LogEntry(829252978, DeviceObject, 0, 0);
  IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)(DeviceExtension + 1832), Irp, 0x20u);
  USBSTOR_LogEntry(846030194, DeviceObject, 0, 0);
  KeCancelTimer((PKTIMER)DeviceExtension + 3);
  KeRemoveQueueDpc((PRKDPC)DeviceExtension + 4);
  KeFlushQueuedDpcs();
  v5 = DeviceExtension + 32;
  while ( (_QWORD *)*v5 != v5 )
  {
    v6 = (_QWORD *)*((_QWORD *)DeviceExtension + 5);
    if ( (_QWORD *)*v6 != v5 || (v7 = (_QWORD *)v6[1], (_QWORD *)*v7 != v6) )
      __fastfail(3u);
    *((_QWORD *)DeviceExtension + 5) = v7;
    *v7 = v5;
    USBSTOR_LogEntry(1668113778, DeviceObject, *(v6 - 2), 0);
    IoDeleteDevice((PDEVICE_OBJECT)*(v6 - 2));
  }
  v8 = (struct _MDL *)*((_QWORD *)DeviceExtension + 213);
  if ( v8 )
  {
    IoFreeMdl(v8);
    *((_QWORD *)DeviceExtension + 213) = 0;
  }
  v9 = (struct _IO_WORKITEM *)*((_QWORD *)DeviceExtension + 46);
  if ( v9 )
  {
    IoFreeWorkItem(v9);
    *((_QWORD *)DeviceExtension + 46) = 0;
  }
  v10 = (struct _IO_WORKITEM *)*((_QWORD *)DeviceExtension + 47);
  if ( v10 )
  {
    IoFreeWorkItem(v10);
    *((_QWORD *)DeviceExtension + 47) = 0;
  }
  v11 = (struct _IO_WORKITEM *)*((_QWORD *)DeviceExtension + 48);
  if ( v11 )
  {
    IoFreeWorkItem(v11);
    *((_QWORD *)DeviceExtension + 48) = 0;
  }
  v12 = (void *)*((_QWORD *)DeviceExtension + 6);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  v13 = (void *)*((_QWORD *)DeviceExtension + 7);
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  v14 = (void *)*((_QWORD *)DeviceExtension + 9);
  if ( v14 )
    ExFreePoolWithTag(v14, 0);
  v15 = (void *)*((_QWORD *)DeviceExtension + 11);
  if ( v15 )
    ExFreePoolWithTag(v15, 0);
  for ( i = 0; i != 2; ++i )
  {
    v17 = *(void **)&DeviceExtension[8 * i + 1896];
    if ( v17 )
    {
      ExFreePoolWithTag(v17, 0);
      *(_QWORD *)&DeviceExtension[8 * i + 1896] = 0;
    }
    v18 = *(void **)&DeviceExtension[8 * i + 1912];
    if ( v18 )
    {
      ExFreePoolWithTag(v18, 0);
      *(_QWORD *)&DeviceExtension[8 * i + 1912] = 0;
    }
  }
  v19 = (IRP *)*((_QWORD *)DeviceExtension + 235);
  if ( v19 )
  {
    IoFreeIrp(v19);
    *((_QWORD *)DeviceExtension + 235) = 0;
  }
  v20 = (IRP *)*((_QWORD *)DeviceExtension + 45);
  if ( v20 )
  {
    IoFreeIrp(v20);
    *((_QWORD *)DeviceExtension + 45) = 0;
  }
  if ( *((_QWORD *)DeviceExtension + 246) )
  {
    PoFxUnregisterDevice();
    *((_QWORD *)DeviceExtension + 246) = 0;
  }
  ++Irp->CurrentLocation;
  ++Irp->Tail.Overlay.CurrentStackLocation;
  Irp->IoStatus.Status = 0;
  v21 = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 3), Irp);
  USBSTOR_LogEntry(862807410, DeviceObject, 0, 0);
  IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 3));
  IoDeleteDevice(DeviceObject);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1986880882, v21, 0, 0);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140028da0  push    rbx
0x140028da2  push    rbp
0x140028da3  push    rsi
0x140028da4  push    rdi
0x140028da5  push    r14
0x140028da7  push    r15
0x140028da9  sub     rsp, 38h
0x140028dad  mov     rbp, rdx
0x140028db0  mov     r14, rcx
0x140028db3  mov     rcx, cs:WPP_GLOBAL_Control
0x140028dba  lea     r15, WPP_GLOBAL_Control
0x140028dc1  cmp     rcx, r15
0x140028dc4  jz      short loc_140028DE8
0x140028dc6  mov     eax, [rcx+2Ch]
0x140028dc9  test    al, 2
0x140028dcb  jz      short loc_140028DE8
0x140028dcd  cmp     byte ptr [rcx+29h], 4
0x140028dd1  jb      short loc_140028DE8
0x140028dd3  mov     rcx, [rcx+18h]
0x140028dd7  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140028dde  mov     edx, 61h ; 'a'
0x140028de3  call    WPP_SF_
0x140028de8  xor     r9d, r9d
0x140028deb  mov     r8, rbp
0x140028dee  mov     rdx, r14
0x140028df1  mov     ecx, 564D4552h
0x140028df6  call    USBSTOR_LogEntry
0x140028dfb  mov     rdi, [r14+40h]
0x140028dff  lea     r8, File; File
0x140028e06  mov     esi, 20h ; ' '
0x140028e0b  mov     rdx, rbp; Tag
0x140028e0e  mov     [rsp+68h+RemlockSize], esi; RemlockSize
0x140028e12  lea     rbx, [rdi+728h]
0x140028e19  mov     rcx, rbx; RemoveLock
0x140028e1c  lea     r9d, [rsi-1Fh]; Line
0x140028e20  call    cs:__imp_IoAcquireRemoveLockEx
0x140028e27  nop     dword ptr [rax+rax+00h]
0x140028e2c  mov     rcx, rdi
0x140028e2f  call    USBSTOR_CancelInterruptIrp
0x140028e34  mov     rcx, rdi
0x140028e37  call    USBSTOR_WmiDeregister
0x140028e3c  xor     r9d, r9d
0x140028e3f  xor     r8d, r8d
0x140028e42  mov     rdx, r14
0x140028e45  mov     ecx, 316D6572h
0x140028e4a  call    USBSTOR_LogEntry
0x140028e4f  mov     r8d, esi; RemlockSize
0x140028e52  mov     rdx, rbp; Tag
0x140028e55  mov     rcx, rbx; RemoveLock
0x140028e58  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x140028e5f  nop     dword ptr [rax+rax+00h]
0x140028e64  xor     r9d, r9d
0x140028e67  xor     r8d, r8d
0x140028e6a  mov     rdx, r14
0x140028e6d  mov     ecx, 326D6572h
0x140028e72  call    USBSTOR_LogEntry
0x140028e77  lea     rcx, [rdi+0C0h]; PKTIMER
0x140028e7e  call    cs:__imp_KeCancelTimer
0x140028e85  nop     dword ptr [rax+rax+00h]
0x140028e8a  lea     rcx, [rdi+100h]; Dpc
0x140028e91  call    cs:__imp_KeRemoveQueueDpc
0x140028e98  nop     dword ptr [rax+rax+00h]
0x140028e9d  call    cs:__imp_KeFlushQueuedDpcs
0x140028ea4  nop     dword ptr [rax+rax+00h]
0x140028ea9  lea     rbx, [rdi+20h]
0x140028ead  cmp     [rbx], rbx
0x140028eb0  jz      short loc_140028EF8
0x140028eb2  mov     rsi, [rbx+8]
0x140028eb6  cmp     [rsi], rbx
0x140028eb9  jnz     short loc_140028EF1
0x140028ebb  mov     rax, [rsi+8]
0x140028ebf  cmp     [rax], rsi
0x140028ec2  jnz     short loc_140028EF1
0x140028ec4  mov     [rbx+8], rax
0x140028ec8  xor     r9d, r9d
0x140028ecb  mov     [rax], rbx
0x140028ece  mov     rdx, r14
0x140028ed1  mov     r8, [rsi-10h]
0x140028ed5  mov     ecx, 636D6572h
0x140028eda  call    USBSTOR_LogEntry
0x140028edf  mov     rcx, [rsi-10h]; DeviceObject
0x140028ee3  call    cs:__imp_IoDeleteDevice
0x140028eea  nop     dword ptr [rax+rax+00h]
0x140028eef  jmp     short loc_140028EAD
0x140028ef1  mov     ecx, 3
0x140028ef6  int     29h; Win8: RtlFailFast(ecx)
0x140028ef8  mov     rcx, [rdi+6A8h]; Mdl
0x140028eff  xor     esi, esi
0x140028f01  test    rcx, rcx
0x140028f04  jz      short loc_140028F19
0x140028f06  call    cs:__imp_IoFreeMdl
0x140028f0d  nop     dword ptr [rax+rax+00h]
0x140028f12  mov     [rdi+6A8h], rsi
0x140028f19  mov     rcx, [rdi+170h]; IoWorkItem
0x140028f20  test    rcx, rcx
0x140028f23  jz      short loc_140028F38
0x140028f25  call    cs:__imp_IoFreeWorkItem
0x140028f2c  nop     dword ptr [rax+rax+00h]
0x140028f31  mov     [rdi+170h], rsi
0x140028f38  mov     rcx, [rdi+178h]; IoWorkItem
0x140028f3f  test    rcx, rcx
0x140028f42  jz      short loc_140028F57
0x140028f44  call    cs:__imp_IoFreeWorkItem
0x140028f4b  nop     dword ptr [rax+rax+00h]
0x140028f50  mov     [rdi+178h], rsi
0x140028f57  mov     rcx, [rdi+180h]; IoWorkItem
0x140028f5e  test    rcx, rcx
0x140028f61  jz      short loc_140028F76
0x140028f63  call    cs:__imp_IoFreeWorkItem
0x140028f6a  nop     dword ptr [rax+rax+00h]
0x140028f6f  mov     [rdi+180h], rsi
0x140028f76  mov     rcx, [rdi+30h]; P
0x140028f7a  test    rcx, rcx
0x140028f7d  jz      short loc_140028F8D
0x140028f7f  xor     edx, edx; Tag
0x140028f81  call    cs:__imp_ExFreePoolWithTag
0x140028f88  nop     dword ptr [rax+rax+00h]
0x140028f8d  mov     rcx, [rdi+38h]; P
0x140028f91  test    rcx, rcx
0x140028f94  jz      short loc_140028FA4
0x140028f96  xor     edx, edx; Tag
0x140028f98  call    cs:__imp_ExFreePoolWithTag
0x140028f9f  nop     dword ptr [rax+rax+00h]
0x140028fa4  mov     rcx, [rdi+48h]; P
0x140028fa8  test    rcx, rcx
0x140028fab  jz      short loc_140028FBB
0x140028fad  xor     edx, edx; Tag
0x140028faf  call    cs:__imp_ExFreePoolWithTag
0x140028fb6  nop     dword ptr [rax+rax+00h]
0x140028fbb  mov     rcx, [rdi+58h]; P
0x140028fbf  test    rcx, rcx
0x140028fc2  jz      short loc_140028FD2
0x140028fc4  xor     edx, edx; Tag
0x140028fc6  call    cs:__imp_ExFreePoolWithTag
0x140028fcd  nop     dword ptr [rax+rax+00h]
0x140028fd2  mov     rbx, rsi
0x140028fd5  mov     rcx, [rdi+rbx*8+768h]; P
0x140028fdd  test    rcx, rcx
0x140028fe0  jz      short loc_140028FF8
0x140028fe2  xor     edx, edx; Tag
0x140028fe4  call    cs:__imp_ExFreePoolWithTag
0x140028feb  nop     dword ptr [rax+rax+00h]
0x140028ff0  mov     [rdi+rbx*8+768h], rsi
0x140028ff8  mov     rcx, [rdi+rbx*8+778h]; P
0x140029000  test    rcx, rcx
0x140029003  jz      short loc_14002901B
0x140029005  xor     edx, edx; Tag
0x140029007  call    cs:__imp_ExFreePoolWithTag
0x14002900e  nop     dword ptr [rax+rax+00h]
0x140029013  mov     [rdi+rbx*8+778h], rsi
0x14002901b  inc     rbx
0x14002901e  cmp     rbx, 2
0x140029022  jnz     short loc_140028FD5
0x140029024  mov     rcx, [rdi+758h]; Irp
0x14002902b  test    rcx, rcx
0x14002902e  jz      short loc_140029043
0x140029030  call    cs:__imp_IoFreeIrp
0x140029037  nop     dword ptr [rax+rax+00h]
0x14002903c  mov     [rdi+758h], rsi
0x140029043  mov     rcx, [rdi+168h]; Irp
0x14002904a  test    rcx, rcx
0x14002904d  jz      short loc_140029062
0x14002904f  call    cs:__imp_IoFreeIrp
0x140029056  nop     dword ptr [rax+rax+00h]
0x14002905b  mov     [rdi+168h], rsi
0x140029062  mov     rcx, [rdi+7B0h]
0x140029069  test    rcx, rcx
0x14002906c  jz      short loc_140029081
0x14002906e  call    cs:__imp_PoFxUnregisterDevice
0x140029075  nop     dword ptr [rax+rax+00h]
0x14002907a  mov     [rdi+7B0h], rsi
0x140029081  inc     byte ptr [rbp+43h]
0x140029084  mov     rdx, rbp; Irp
0x140029087  add     qword ptr [rbp+0B8h], 48h ; 'H'
0x14002908f  mov     [rbp+30h], esi
0x140029092  mov     rcx, [rdi+18h]; DeviceObject
0x140029096  call    cs:__imp_IofCallDriver
0x14002909d  nop     dword ptr [rax+rax+00h]
0x1400290a2  xor     r9d, r9d
0x1400290a5  xor     r8d, r8d
0x1400290a8  mov     rdx, r14
0x1400290ab  movsxd  rbx, eax
0x1400290ae  mov     ecx, 336D6572h
0x1400290b3  call    USBSTOR_LogEntry
0x1400290b8  mov     rcx, [rdi+18h]; TargetDevice
0x1400290bc  call    cs:__imp_IoDetachDevice
0x1400290c3  nop     dword ptr [rax+rax+00h]
0x1400290c8  mov     rcx, r14; DeviceObject
0x1400290cb  call    cs:__imp_IoDeleteDevice
0x1400290d2  nop     dword ptr [rax+rax+00h]
0x1400290d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400290de  cmp     rcx, r15
0x1400290e1  jz      short loc_140029108
0x1400290e3  mov     eax, [rcx+2Ch]
0x1400290e6  test    al, 2
0x1400290e8  jz      short loc_140029108
0x1400290ea  cmp     byte ptr [rcx+29h], 4
0x1400290ee  jb      short loc_140029108
0x1400290f0  mov     rcx, [rcx+18h]
0x1400290f4  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400290fb  mov     edx, 62h ; 'b'
0x140029100  mov     r9d, ebx
0x140029103  call    WPP_SF_d
0x140029108  mov     rdx, rbx
0x14002910b  xor     r9d, r9d
0x14002910e  xor     r8d, r8d
0x140029111  mov     ecx, 766D6572h
0x140029116  call    USBSTOR_LogEntry
0x14002911b  mov     eax, ebx
0x14002911d  add     rsp, 38h
0x140029121  pop     r15
0x140029123  pop     r14
0x140029125  pop     rdi
0x140029126  pop     rsi
0x140029127  pop     rbp
0x140029128  pop     rbx
0x140029129  retn
```
