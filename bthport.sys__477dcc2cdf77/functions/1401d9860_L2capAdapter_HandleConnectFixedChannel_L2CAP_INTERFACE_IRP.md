# L2capAdapter_HandleConnectFixedChannel(L2CAP_INTERFACE *,_IRP *)

- ea: `0x1401d9860`
- end: `0x1401d9a2c`
- name: `?L2capAdapter_HandleConnectFixedChannel@@YAJPEAUL2CAP_INTERFACE@@PEAU_IRP@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(struct L2CAP_INTERFACE *, struct _IRP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001e010`

## callees

- `0x140005690`
- `0x140007910`
- `0x140007cc0`
- `0x1400db300`
- `0x1401d9860`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1401d99a0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1401d99a0`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1401d989c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1401d989c`
- `ntoskrnl!IoAllocateIrp` at `0x1401d9910`
- `ntoskrnl!IoAllocateIrp` at `0x1401d9910`
- `ntoskrnl!IofCallDriver` at `0x1401d9974`
- `ntoskrnl!IofCallDriver` at `0x1401d9974`

## pseudocode

```c
__int64 __fastcall L2capAdapter_HandleConnectFixedChannel(struct L2CAP_INTERFACE *a1, _LIST_ENTRY *a2)
{
  char v4; // si
  NTSTATUS v5; // ebx
  _IRP::<unnamed_type_AssociatedIrp> v6; // r14
  struct _BRB *Brb; // rax
  ULONG_PTR v8; // rbx
  PIRP Irp; // rax
  _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  _IO_STACK_LOCATION *v11; // rcx
  int v12; // edx
  int v13; // r8d
  __int16 DeviceType; // ax

  v4 = 1;
  v5 = IoAcquireRemoveLockEx(
         &a1->DevExt->RemoveLock,
         L2capAdapter_BrbCompletionRoutine,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\l2capfixedcidadapter.cpp",
         0x3DBu,
         0x20u);
  if ( v5 < 0 )
    goto LABEL_7;
  v6.MasterIrp = (_IRP *)a2[1].Blink;
  Brb = BthAllocateBrb((enum _BRB_TYPE)49416, 0x4143324Cu);
  v8 = (ULONG_PTR)Brb;
  if ( !Brb )
  {
LABEL_6:
    v5 = -1073741670;
LABEL_7:
    IoReleaseRemoveLockEx(&a1->DevExt->RemoveLock, L2capAdapter_BrbCompletionRoutine, 0x20u);
    goto LABEL_8;
  }
  Brb->BrbHeader.ClientContext[0] = a1;
  Brb->BrbL2caUnregisterServer.ServerHandle = *(void **)&v6.MasterIrp->Type;
  Brb->BrbL2caAclTransfer.TransferFlags = (unsigned int)v6.MasterIrp->MdlAddress;
  Brb->BrbL2caRegisterServer.BtAddress = (unsigned __int64)L2capAdapter_GetFixedChannelServerHandleFromFileObject(
                                                             a1,
                                                             (struct _FILE_OBJECT *)a2[11].Blink[3].Flink);
  Irp = IoAllocateIrp(a1->DevExt->BtDevice.FunctionalDeviceObject->StackSize, 0);
  if ( !Irp )
  {
    BthFreeBrb(v8);
    goto LABEL_6;
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].Context = (void *)v8;
  CurrentStackLocation[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))L2capAdapter_BrbCompletionRoutine;
  CurrentStackLocation[-1].Control = -32;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = a2;
  --Irp->Tail.Overlay.CurrentStackLocation;
  --Irp->CurrentLocation;
  v11 = Irp->Tail.Overlay.CurrentStackLocation;
  v11[-1].Parameters.WMI.ProviderId = v8;
  v5 = 259;
  v11[-1].MajorFunction = 15;
  v11[-1].Parameters.Read.ByteOffset.LowPart = 4259843;
  BYTE3(a2[11].Blink->Flink) |= 1u;
  IofCallDriver(a1->DevExt->BtDevice.FunctionalDeviceObject, Irp);
LABEL_8:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v4 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v4 || DeviceType )
  {
    LOBYTE(v12) = v4;
    LOBYTE(v13) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      v13,
      a1->DevExt->Hci->IfrLog,
      5,
      3,
      33,
      (__int64)WPP_aac7878291ab3466cf4003e69b0eed30_Traceguids,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1401d9860  push    rbx
0x1401d9862  push    rbp
0x1401d9863  push    rsi
0x1401d9864  push    rdi
0x1401d9865  push    r12
0x1401d9867  push    r14
0x1401d9869  push    r15
0x1401d986b  sub     rsp, 50h
0x1401d986f  mov     rdi, rcx
0x1401d9872  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x1401d987a  mov     rcx, [rcx+50h]
0x1401d987e  lea     r12, ?L2capAdapter_BrbCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; L2capAdapter_BrbCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1401d9885  mov     rbp, rdx
0x1401d9888  lea     r8, aOnecoreDrivers_14; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1401d988f  add     rcx, 38h ; '8'; RemoveLock
0x1401d9893  mov     r9d, 3DBh; Line
0x1401d9899  mov     rdx, r12; Tag
0x1401d989c  call    cs:__imp_IoAcquireRemoveLockEx
0x1401d98a3  nop     dword ptr [rax+rax+00h]
0x1401d98a8  xor     r15d, r15d
0x1401d98ab  mov     sil, 1
0x1401d98ae  mov     ebx, eax
0x1401d98b0  test    eax, eax
0x1401d98b2  js      loc_1401D998F
0x1401d98b8  mov     r14, [rbp+18h]
0x1401d98bc  mov     edx, 4143324Ch; unsigned int
0x1401d98c1  mov     ecx, 0C108h; enum _BRB_TYPE
0x1401d98c6  call    ?BthAllocateBrb@@YAPEAU_BRB@@W4_BRB_TYPE@@K@Z; BthAllocateBrb(_BRB_TYPE,ulong)
0x1401d98cb  mov     rbx, rax
0x1401d98ce  test    rax, rax
0x1401d98d1  jz      loc_1401D998A
0x1401d98d7  mov     [rax+48h], rdi
0x1401d98db  mov     rcx, [r14]
0x1401d98de  mov     [rax+78h], rcx
0x1401d98e2  mov     ecx, [r14+8]
0x1401d98e6  mov     [rax+80h], ecx
0x1401d98ec  mov     rcx, rdi; struct L2CAP_INTERFACE *
0x1401d98ef  mov     rdx, [rbp+0B8h]
0x1401d98f6  mov     rdx, [rdx+30h]; struct _FILE_OBJECT *
0x1401d98fa  call    ?L2capAdapter_GetFixedChannelServerHandleFromFileObject@@YAPEAXPEAUL2CAP_INTERFACE@@PEAU_FILE_OBJECT@@@Z; L2capAdapter_GetFixedChannelServerHandleFromFileObject(L2CAP_INTERFACE *,_FILE_OBJECT *)
0x1401d98ff  mov     [rbx+70h], rax
0x1401d9903  xor     edx, edx; ChargeQuota
0x1401d9905  mov     rax, [rdi+50h]
0x1401d9909  mov     rcx, [rax+8]
0x1401d990d  mov     cl, [rcx+4Ch]; StackSize
0x1401d9910  call    cs:__imp_IoAllocateIrp
0x1401d9917  nop     dword ptr [rax+rax+00h]
0x1401d991c  mov     rdx, rax; Irp
0x1401d991f  test    rax, rax
0x1401d9922  jz      short loc_1401D9982
0x1401d9924  mov     rcx, [rax+0B8h]
0x1401d992b  mov     [rcx-8], rbx
0x1401d992f  mov     [rcx-10h], r12
0x1401d9933  mov     byte ptr [rcx-45h], 0E0h
0x1401d9937  mov     [rax+78h], rbp
0x1401d993b  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x1401d9943  dec     byte ptr [rax+43h]
0x1401d9946  mov     rcx, [rax+0B8h]
0x1401d994d  mov     [rcx-40h], rbx
0x1401d9951  mov     ebx, 103h
0x1401d9956  mov     byte ptr [rcx-48h], 0Fh
0x1401d995a  mov     dword ptr [rcx-30h], 410003h
0x1401d9961  mov     rax, [rbp+0B8h]
0x1401d9968  or      [rax+3], sil
0x1401d996c  mov     rcx, [rdi+50h]
0x1401d9970  mov     rcx, [rcx+8]; DeviceObject
0x1401d9974  call    cs:__imp_IofCallDriver
0x1401d997b  nop     dword ptr [rax+rax+00h]
0x1401d9980  jmp     short loc_1401D99AC
0x1401d9982  mov     rcx, rbx; BugCheckParameter2
0x1401d9985  call    ?BthFreeBrb@@YAXPEAU_BRB@@@Z; BthFreeBrb(_BRB *)
0x1401d998a  mov     ebx, 0C000009Ah
0x1401d998f  mov     rcx, [rdi+50h]
0x1401d9993  mov     r8d, 20h ; ' '; RemlockSize
0x1401d9999  add     rcx, 38h ; '8'; RemoveLock
0x1401d999d  mov     rdx, r12; Tag
0x1401d99a0  call    cs:__imp_IoReleaseRemoveLockEx
0x1401d99a7  nop     dword ptr [rax+rax+00h]
0x1401d99ac  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d99b3  mov     eax, [rcx+2Ch]
0x1401d99b6  test    al, 4
0x1401d99b8  jz      short loc_1401D99C0
0x1401d99ba  cmp     byte ptr [rcx+29h], 5
0x1401d99be  jnb     short loc_1401D99C3
0x1401d99c0  mov     sil, r15b
0x1401d99c3  movzx   eax, word ptr [rcx+48h]
0x1401d99c7  test    ax, ax
0x1401d99ca  setnz   r8b
0x1401d99ce  test    sil, sil
0x1401d99d1  jnz     short loc_1401D99D8
0x1401d99d3  test    ax, ax
0x1401d99d6  jz      short loc_1401D9A1A
0x1401d99d8  mov     rax, [rdi+50h]
0x1401d99dc  mov     dl, sil
0x1401d99df  mov     rcx, [rcx+18h]
0x1401d99e3  mov     [rsp+88h+var_48], ebx
0x1401d99e7  mov     r9, [rax+170h]
0x1401d99ee  lea     rax, WPP_aac7878291ab3466cf4003e69b0eed30_Traceguids
0x1401d99f5  mov     [rsp+88h+var_50], rax
0x1401d99fa  mov     [rsp+88h+var_58], 21h ; '!'
0x1401d9a01  mov     [rsp+88h+var_60], 3
0x1401d9a09  mov     r9, [r9+10B0h]
0x1401d9a10  mov     byte ptr [rsp+88h+RemlockSize], 5
0x1401d9a15  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401d9a1a  mov     eax, ebx
0x1401d9a1c  add     rsp, 50h
0x1401d9a20  pop     r15
0x1401d9a22  pop     r14
0x1401d9a24  pop     r12
0x1401d9a26  pop     rdi
0x1401d9a27  pop     rsi
0x1401d9a28  pop     rbp
0x1401d9a29  pop     rbx
0x1401d9a2a  retn
```
