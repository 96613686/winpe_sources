# USBSTOR_FreeDumpPointers

- ea: `0x14000e494`
- end: `0x14000e713`
- name: `USBSTOR_FreeDumpPointers`
- size: `639`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x14000e494`
- `0x1400105e8`
- `0x140010664`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000e5c1`
- `ntoskrnl!IoFreeIrp` at `0x14000e616`
- `ntoskrnl!IoFreeIrp` at `0x14000e5c1`
- `ntoskrnl!IoFreeIrp` at `0x14000e616`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000e5ae`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000e5ae`
- `ntoskrnl!IofCallDriver` at `0x14000e5d9`
- `ntoskrnl!IofCallDriver` at `0x14000e5d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e635`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e646`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e678`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e69f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e635`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e646`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e678`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e69f`
- `ntoskrnl!KeInitializeEvent` at `0x14000e555`
- `ntoskrnl!KeInitializeEvent` at `0x14000e555`
- `ntoskrnl!IofCompleteRequest` at `0x14000e6bf`
- `ntoskrnl!IofCompleteRequest` at `0x14000e6bf`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e604`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e604`
- `ntoskrnl!IoAllocateIrp` at `0x14000e52b`
- `ntoskrnl!IoAllocateIrp` at `0x14000e52b`

## pseudocode

```c
__int64 __fastcall USBSTOR_FreeDumpPointers(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  unsigned int Status; // ebx
  struct _IRP *MasterIrp; // r14
  __int64 v6; // rsi
  PIRP v7; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _EPROCESS *Process; // r15
  PVOID *p_Flink; // rdi
  __int64 v12; // rcx
  __int64 v13; // rdi
  void *v14; // rcx
  void *v15; // rcx
  struct _KEVENT Event; // [rsp+40h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 208, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  if ( Irp->RequestorMode )
  {
    Status = -1073741808;
  }
  else
  {
    if ( Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options >= 0x68 )
    {
      MasterIrp = Irp->AssociatedIrp.MasterIrp;
      v6 = *(_QWORD *)(*((_QWORD *)DeviceObject->DeviceExtension + 2) + 64LL);
      v7 = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(v6 + 24) + 76LL), 0);
      if ( v7 )
      {
        KeInitializeEvent(&Event, SynchronizationEvent, 0);
        CurrentStackLocation = v7->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].MajorFunction = 15;
        CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4789256;
        Process = MasterIrp->MdlAddress[1].Process;
        v7->AssociatedIrp.MasterIrp = (struct _IRP *)((char *)Process + 216);
        CurrentStackLocation[-1].Parameters.Create.Options = 88;
        if ( IoSetCompletionRoutineEx(DeviceObject, v7, USBSTOR_SyncCompletionRoutine, &Event, 1u, 1u, 1u) >= 0 )
        {
          Status = IofCallDriver(*(PDEVICE_OBJECT *)(v6 + 24), v7);
          if ( Status == 259 )
          {
            KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
            Status = v7->IoStatus.Status;
          }
          IoFreeIrp(v7);
          p_Flink = (PVOID *)&MasterIrp->ThreadListEntry.Blink->Flink;
          if ( p_Flink )
          {
            if ( *p_Flink )
              ExFreePoolWithTag(*p_Flink, 0);
            ExFreePoolWithTag(p_Flink, 0);
          }
          v12 = 0;
          while ( *(struct _EPROCESS **)(v6 + 8 * v12 + 1896) != Process )
          {
            v12 = (unsigned int)(v12 + 1);
            if ( (unsigned int)v12 >= 2 )
            {
              if ( (_DWORD)v12 == 2 )
                goto LABEL_27;
              break;
            }
          }
          v13 = (unsigned int)v12;
          v14 = *(void **)(v6 + 8 * v12 + 1896);
          if ( v14 )
          {
            ExFreePoolWithTag(v14, 0);
            *(_QWORD *)(v6 + 8 * v13 + 1896) = 0;
          }
          v15 = *(void **)(v6 + 8 * v13 + 1912);
          if ( v15 )
          {
            ExFreePoolWithTag(v15, 0);
            *(_QWORD *)(v6 + 8 * v13 + 1912) = 0;
          }
          goto LABEL_27;
        }
        IoFreeIrp(v7);
      }
      return 3221225626LL;
    }
    Status = -1073741789;
  }
LABEL_27:
  Irp->IoStatus.Status = Status;
  IofCompleteRequest(Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 209, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return Status;
}

```

## disassembly

```asm
0x14000e494  push    rbx
0x14000e496  push    rbp
0x14000e497  push    rsi
0x14000e498  push    rdi
0x14000e499  push    r14
0x14000e49b  push    r15
0x14000e49d  sub     rsp, 68h
0x14000e4a1  xorps   xmm0, xmm0
0x14000e4a4  xor     eax, eax
0x14000e4a6  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x14000e4ab  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x14000e4b0  mov     rbp, rdx
0x14000e4b3  mov     rbx, rcx
0x14000e4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4bd  lea     rax, WPP_GLOBAL_Control
0x14000e4c4  cmp     rcx, rax
0x14000e4c7  jz      short loc_14000E4EB
0x14000e4c9  mov     eax, [rcx+2Ch]
0x14000e4cc  test    al, 1
0x14000e4ce  jz      short loc_14000E4EB
0x14000e4d0  cmp     byte ptr [rcx+29h], 5
0x14000e4d4  jb      short loc_14000E4EB
0x14000e4d6  mov     rcx, [rcx+18h]
0x14000e4da  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000e4e1  mov     edx, 0D0h
0x14000e4e6  call    WPP_SF_
0x14000e4eb  cmp     byte ptr [rbp+40h], 0
0x14000e4ef  jz      short loc_14000E4FB
0x14000e4f1  mov     ebx, 0C0000010h
0x14000e4f6  jmp     loc_14000E6B7
0x14000e4fb  mov     rax, [rbp+0B8h]
0x14000e502  cmp     dword ptr [rax+10h], 68h ; 'h'
0x14000e506  jnb     short loc_14000E512
0x14000e508  mov     ebx, 0C0000023h
0x14000e50d  jmp     loc_14000E6B7
0x14000e512  mov     rax, [rbx+40h]
0x14000e516  xor     edx, edx; ChargeQuota
0x14000e518  mov     r14, [rbp+18h]
0x14000e51c  mov     rcx, [rax+10h]
0x14000e520  mov     rsi, [rcx+40h]
0x14000e524  mov     rcx, [rsi+18h]
0x14000e528  mov     cl, [rcx+4Ch]; StackSize
0x14000e52b  call    cs:__imp_IoAllocateIrp
0x14000e532  nop     dword ptr [rax+rax+00h]
0x14000e537  mov     rdi, rax
0x14000e53a  test    rax, rax
0x14000e53d  jnz     short loc_14000E549
0x14000e53f  mov     eax, 0C000009Ah
0x14000e544  jmp     loc_14000E705
0x14000e549  xor     r8d, r8d; State
0x14000e54c  lea     rcx, [rsp+98h+Event]; Event
0x14000e551  lea     edx, [r8+1]; Type
0x14000e555  call    cs:__imp_KeInitializeEvent
0x14000e55c  nop     dword ptr [rax+rax+00h]
0x14000e561  mov     rcx, [rdi+0B8h]
0x14000e568  lea     r9, [rsp+98h+Event]; Context
0x14000e56d  mov     [rsp+98h+InvokeOnCancel], 1; InvokeOnCancel
0x14000e572  lea     r8, USBSTOR_SyncCompletionRoutine; CompletionRoutine
0x14000e579  mov     [rsp+98h+InvokeOnError], 1; InvokeOnError
0x14000e57e  mov     rdx, rdi; Irp
0x14000e581  mov     [rsp+98h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14000e586  mov     byte ptr [rcx-48h], 0Fh
0x14000e58a  mov     dword ptr [rcx-30h], 491408h
0x14000e591  mov     rax, [r14+8]
0x14000e595  mov     r15, [rax+40h]
0x14000e599  lea     rax, [r15+0D8h]
0x14000e5a0  mov     [rdi+18h], rax
0x14000e5a4  mov     dword ptr [rcx-38h], 58h ; 'X'
0x14000e5ab  mov     rcx, rbx; DeviceObject
0x14000e5ae  call    cs:__imp_IoSetCompletionRoutineEx
0x14000e5b5  nop     dword ptr [rax+rax+00h]
0x14000e5ba  test    eax, eax
0x14000e5bc  jns     short loc_14000E5D2
0x14000e5be  mov     rcx, rdi; Irp
0x14000e5c1  call    cs:__imp_IoFreeIrp
0x14000e5c8  nop     dword ptr [rax+rax+00h]
0x14000e5cd  jmp     loc_14000E53F
0x14000e5d2  mov     rcx, [rsi+18h]; DeviceObject
0x14000e5d6  mov     rdx, rdi; Irp
0x14000e5d9  call    cs:__imp_IofCallDriver
0x14000e5e0  nop     dword ptr [rax+rax+00h]
0x14000e5e5  mov     ebx, eax
0x14000e5e7  cmp     eax, 103h
0x14000e5ec  jnz     short loc_14000E613
0x14000e5ee  xor     r9d, r9d; Alertable
0x14000e5f1  mov     qword ptr [rsp+98h+InvokeOnSuccess], 0; Timeout
0x14000e5fa  xor     r8d, r8d; WaitMode
0x14000e5fd  lea     rcx, [rsp+98h+Event]; Object
0x14000e602  xor     edx, edx; WaitReason
0x14000e604  call    cs:__imp_KeWaitForSingleObject
0x14000e60b  nop     dword ptr [rax+rax+00h]
0x14000e610  mov     ebx, [rdi+30h]
0x14000e613  mov     rcx, rdi; Irp
0x14000e616  call    cs:__imp_IoFreeIrp
0x14000e61d  nop     dword ptr [rax+rax+00h]
0x14000e622  mov     rdi, [r14+28h]
0x14000e626  test    rdi, rdi
0x14000e629  jz      short loc_14000E652
0x14000e62b  mov     rcx, [rdi]; P
0x14000e62e  test    rcx, rcx
0x14000e631  jz      short loc_14000E641
0x14000e633  xor     edx, edx; Tag
0x14000e635  call    cs:__imp_ExFreePoolWithTag
0x14000e63c  nop     dword ptr [rax+rax+00h]
0x14000e641  xor     edx, edx; Tag
0x14000e643  mov     rcx, rdi; P
0x14000e646  call    cs:__imp_ExFreePoolWithTag
0x14000e64d  nop     dword ptr [rax+rax+00h]
0x14000e652  xor     ecx, ecx
0x14000e654  cmp     [rsi+rcx*8+768h], r15
0x14000e65c  jz      short loc_14000E667
0x14000e65e  inc     ecx
0x14000e660  cmp     ecx, 2
0x14000e663  jb      short loc_14000E654
0x14000e665  jz      short loc_14000E6B7
0x14000e667  mov     edi, ecx
0x14000e669  mov     rcx, [rsi+rcx*8+768h]; P
0x14000e671  test    rcx, rcx
0x14000e674  jz      short loc_14000E690
0x14000e676  xor     edx, edx; Tag
0x14000e678  call    cs:__imp_ExFreePoolWithTag
0x14000e67f  nop     dword ptr [rax+rax+00h]
0x14000e684  mov     qword ptr [rsi+rdi*8+768h], 0
0x14000e690  mov     rcx, [rsi+rdi*8+778h]; P
0x14000e698  test    rcx, rcx
0x14000e69b  jz      short loc_14000E6B7
0x14000e69d  xor     edx, edx; Tag
0x14000e69f  call    cs:__imp_ExFreePoolWithTag
0x14000e6a6  nop     dword ptr [rax+rax+00h]
0x14000e6ab  mov     qword ptr [rsi+rdi*8+778h], 0
0x14000e6b7  xor     edx, edx; PriorityBoost
0x14000e6b9  mov     [rbp+30h], ebx
0x14000e6bc  mov     rcx, rbp; Irp
0x14000e6bf  call    cs:__imp_IofCompleteRequest
0x14000e6c6  nop     dword ptr [rax+rax+00h]
0x14000e6cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e6d2  lea     rax, WPP_GLOBAL_Control
0x14000e6d9  cmp     rcx, rax
0x14000e6dc  jz      short loc_14000E703
0x14000e6de  mov     eax, [rcx+2Ch]
0x14000e6e1  test    al, 1
0x14000e6e3  jz      short loc_14000E703
0x14000e6e5  cmp     byte ptr [rcx+29h], 5
0x14000e6e9  jb      short loc_14000E703
0x14000e6eb  mov     rcx, [rcx+18h]
0x14000e6ef  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000e6f6  mov     edx, 0D1h
0x14000e6fb  mov     r9d, ebx
0x14000e6fe  call    WPP_SF_d
0x14000e703  mov     eax, ebx
0x14000e705  add     rsp, 68h
0x14000e709  pop     r15
0x14000e70b  pop     r14
0x14000e70d  pop     rdi
0x14000e70e  pop     rsi
0x14000e70f  pop     rbp
0x14000e710  pop     rbx
0x14000e711  retn
```
