# L2capAdapter_HandleSendFixedChannelData(L2CAP_INTERFACE *,_IRP *)

- ea: `0x1401d9c20`
- end: `0x1401d9e32`
- name: `?L2capAdapter_HandleSendFixedChannelData@@YAJPEAUL2CAP_INTERFACE@@PEAU_IRP@@@Z`
- size: `530`
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
- `0x1401d9c20`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1401d9da6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1401d9da6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1401d9c5e`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1401d9c5e`
- `ntoskrnl!IoAllocateIrp` at `0x1401d9d0f`
- `ntoskrnl!IoAllocateIrp` at `0x1401d9d0f`
- `ntoskrnl!IofCallDriver` at `0x1401d9d73`
- `ntoskrnl!IofCallDriver` at `0x1401d9d73`

## pseudocode

```c
__int64 __fastcall L2capAdapter_HandleSendFixedChannelData(struct L2CAP_INTERFACE *a1, _LIST_ENTRY *a2)
{
  NTSTATUS v4; // eax
  _IRP::<unnamed_type_AssociatedIrp> v5; // r14
  _IO_STACK_LOCATION *Blink; // r15
  unsigned int v7; // ebx
  char v8; // di
  struct _BRB *Brb; // rax
  ULONG_PTR v10; // rbx
  PIRP Irp; // rax
  IRP *v12; // rdx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v14; // rax
  int v15; // edx
  int v16; // r8d
  __int16 DeviceType; // ax

  v4 = IoAcquireRemoveLockEx(
         &a1->DevExt->RemoveLock,
         L2capAdapter_BrbCompletionRoutine,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\l2capfixedcidadapter.cpp",
         0x38Eu,
         0x20u);
  v5.MasterIrp = (_IRP *)a2[1].Blink;
  Blink = (_IO_STACK_LOCATION *)a2[11].Blink;
  v7 = v4;
  v8 = 1;
  if ( Blink->Parameters.Create.Options < (unsigned __int64)HIWORD(v5.MasterIrp->MdlAddress) + 23 )
  {
    v7 = -1073741811;
LABEL_9:
    IoReleaseRemoveLockEx(&a1->DevExt->RemoveLock, L2capAdapter_BrbCompletionRoutine, 0x20u);
    goto LABEL_10;
  }
  if ( v4 < 0 )
    goto LABEL_9;
  Brb = BthAllocateBrb(BRB_L2CA_PING|0xC000, 0x4143324Cu);
  v10 = (ULONG_PTR)Brb;
  if ( !Brb )
  {
LABEL_8:
    v7 = -1073741670;
    goto LABEL_9;
  }
  Brb->BrbHeader.ClientContext[0] = a1;
  Brb->BrbL2caUnregisterServer.ServerHandle = *(void **)&v5.MasterIrp->Type;
  Brb->BrbL2caAclTransfer.TransferFlags = (unsigned int)v5.MasterIrp->MdlAddress;
  Brb->BrbL2caPing.PingRequestData[11] = BYTE4(v5.MasterIrp->MdlAddress);
  Brb->BrbScoOpenChannel.Reserved = HIWORD(v5.MasterIrp->MdlAddress);
  Brb->BrbL2caRegisterServer.IndicationCallbackContext = &v5.MasterIrp->Flags;
  Brb->BrbL2caRegisterServer.BtAddress = (unsigned __int64)L2capAdapter_GetFixedChannelServerHandleFromFileObject(
                                                             a1,
                                                             Blink->FileObject);
  Irp = IoAllocateIrp(a1->DevExt->BtDevice.FunctionalDeviceObject->StackSize, 0);
  v12 = Irp;
  if ( !Irp )
  {
    BthFreeBrb(v10);
    goto LABEL_8;
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].Context = (void *)v10;
  CurrentStackLocation[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))L2capAdapter_BrbCompletionRoutine;
  CurrentStackLocation[-1].Control = -32;
  v12->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = a2;
  --v12->Tail.Overlay.CurrentStackLocation;
  --v12->CurrentLocation;
  v14 = v12->Tail.Overlay.CurrentStackLocation;
  v14[-1].Parameters.WMI.ProviderId = v10;
  v7 = 259;
  v14[-1].MajorFunction = 15;
  v14[-1].Parameters.Read.ByteOffset.LowPart = 4259843;
  BYTE3(a2[11].Blink->Flink) |= 1u;
  IofCallDriver(a1->DevExt->BtDevice.FunctionalDeviceObject, v12);
LABEL_10:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v8 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v8 || DeviceType )
  {
    LOBYTE(v15) = v8;
    LOBYTE(v16) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v15,
      v16,
      a1->DevExt->Hci->IfrLog,
      5,
      3,
      32,
      (__int64)WPP_aac7878291ab3466cf4003e69b0eed30_Traceguids,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x1401d9c20  push    rbx
0x1401d9c22  push    rbp
0x1401d9c23  push    rsi
0x1401d9c24  push    rdi
0x1401d9c25  push    r12
0x1401d9c27  push    r13
0x1401d9c29  push    r14
0x1401d9c2b  push    r15
0x1401d9c2d  sub     rsp, 58h
0x1401d9c31  mov     rsi, rcx
0x1401d9c34  mov     [rsp+98h+RemlockSize], 20h ; ' '; RemlockSize
0x1401d9c3c  mov     rcx, [rcx+50h]
0x1401d9c40  lea     r13, ?L2capAdapter_BrbCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; L2capAdapter_BrbCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1401d9c47  mov     rbp, rdx
0x1401d9c4a  lea     r8, aOnecoreDrivers_14; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1401d9c51  add     rcx, 38h ; '8'; RemoveLock
0x1401d9c55  mov     r9d, 38Eh; Line
0x1401d9c5b  mov     rdx, r13; Tag
0x1401d9c5e  call    cs:__imp_IoAcquireRemoveLockEx
0x1401d9c65  nop     dword ptr [rax+rax+00h]
0x1401d9c6a  mov     r14, [rbp+18h]
0x1401d9c6e  xor     r12d, r12d
0x1401d9c71  mov     r15, [rbp+0B8h]
0x1401d9c78  mov     ebx, eax
0x1401d9c7a  mov     dil, 1
0x1401d9c7d  movzx   ecx, word ptr [r14+0Eh]
0x1401d9c82  mov     eax, [r15+10h]
0x1401d9c86  add     rcx, 17h
0x1401d9c8a  cmp     rax, rcx
0x1401d9c8d  jnb     short loc_1401D9C99
0x1401d9c8f  mov     ebx, 0C000000Dh
0x1401d9c94  jmp     loc_1401D9D93
0x1401d9c99  test    ebx, ebx
0x1401d9c9b  js      loc_1401D9D93
0x1401d9ca1  mov     edx, 4143324Ch; unsigned int
0x1401d9ca6  mov     ecx, 0C107h; enum _BRB_TYPE
0x1401d9cab  call    ?BthAllocateBrb@@YAPEAU_BRB@@W4_BRB_TYPE@@K@Z; BthAllocateBrb(_BRB_TYPE,ulong)
0x1401d9cb0  mov     rbx, rax
0x1401d9cb3  test    rax, rax
0x1401d9cb6  jz      loc_1401D9D8E
0x1401d9cbc  mov     [rax+48h], rsi
0x1401d9cc0  mov     rcx, rsi; struct L2CAP_INTERFACE *
0x1401d9cc3  mov     rax, [r14]
0x1401d9cc6  mov     [rbx+78h], rax
0x1401d9cca  mov     eax, [r14+8]
0x1401d9cce  mov     [rbx+80h], eax
0x1401d9cd4  mov     al, [r14+0Ch]
0x1401d9cd8  mov     [rbx+84h], al
0x1401d9cde  movzx   eax, word ptr [r14+0Eh]
0x1401d9ce3  mov     [rbx+86h], ax
0x1401d9cea  lea     rax, [r14+10h]
0x1401d9cee  mov     [rbx+88h], rax
0x1401d9cf5  mov     rdx, [r15+30h]; struct _FILE_OBJECT *
0x1401d9cf9  call    ?L2capAdapter_GetFixedChannelServerHandleFromFileObject@@YAPEAXPEAUL2CAP_INTERFACE@@PEAU_FILE_OBJECT@@@Z; L2capAdapter_GetFixedChannelServerHandleFromFileObject(L2CAP_INTERFACE *,_FILE_OBJECT *)
0x1401d9cfe  mov     [rbx+70h], rax
0x1401d9d02  xor     edx, edx; ChargeQuota
0x1401d9d04  mov     rax, [rsi+50h]
0x1401d9d08  mov     rcx, [rax+8]
0x1401d9d0c  mov     cl, [rcx+4Ch]; StackSize
0x1401d9d0f  call    cs:__imp_IoAllocateIrp
0x1401d9d16  nop     dword ptr [rax+rax+00h]
0x1401d9d1b  mov     rdx, rax; Irp
0x1401d9d1e  test    rax, rax
0x1401d9d21  jz      short loc_1401D9D86
0x1401d9d23  mov     rax, [rax+0B8h]
0x1401d9d2a  mov     [rax-8], rbx
0x1401d9d2e  mov     [rax-10h], r13
0x1401d9d32  mov     byte ptr [rax-45h], 0E0h
0x1401d9d36  mov     [rdx+78h], rbp
0x1401d9d3a  add     qword ptr [rdx+0B8h], 0FFFFFFFFFFFFFFB8h
0x1401d9d42  dec     byte ptr [rdx+43h]
0x1401d9d45  mov     rax, [rdx+0B8h]
0x1401d9d4c  mov     [rax-40h], rbx
0x1401d9d50  mov     ebx, 103h
0x1401d9d55  mov     byte ptr [rax-48h], 0Fh
0x1401d9d59  mov     dword ptr [rax-30h], 410003h
0x1401d9d60  mov     rax, [rbp+0B8h]
0x1401d9d67  or      [rax+3], dil
0x1401d9d6b  mov     rcx, [rsi+50h]
0x1401d9d6f  mov     rcx, [rcx+8]; DeviceObject
0x1401d9d73  call    cs:__imp_IofCallDriver
0x1401d9d7a  nop     dword ptr [rax+rax+00h]
0x1401d9d7f  mov     ebp, 20h ; ' '
0x1401d9d84  jmp     short loc_1401D9DB2
0x1401d9d86  mov     rcx, rbx; BugCheckParameter2
0x1401d9d89  call    ?BthFreeBrb@@YAXPEAU_BRB@@@Z; BthFreeBrb(_BRB *)
0x1401d9d8e  mov     ebx, 0C000009Ah
0x1401d9d93  mov     rcx, [rsi+50h]
0x1401d9d97  mov     ebp, 20h ; ' '
0x1401d9d9c  add     rcx, 38h ; '8'; RemoveLock
0x1401d9da0  mov     r8d, ebp; RemlockSize
0x1401d9da3  mov     rdx, r13; Tag
0x1401d9da6  call    cs:__imp_IoReleaseRemoveLockEx
0x1401d9dad  nop     dword ptr [rax+rax+00h]
0x1401d9db2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d9db9  mov     eax, [rcx+2Ch]
0x1401d9dbc  test    al, 4
0x1401d9dbe  jz      short loc_1401D9DC6
0x1401d9dc0  cmp     byte ptr [rcx+29h], 5
0x1401d9dc4  jnb     short loc_1401D9DC9
0x1401d9dc6  mov     dil, r12b
0x1401d9dc9  movzx   eax, word ptr [rcx+48h]
0x1401d9dcd  test    ax, ax
0x1401d9dd0  setnz   r8b
0x1401d9dd4  test    dil, dil
0x1401d9dd7  jnz     short loc_1401D9DDE
0x1401d9dd9  test    ax, ax
0x1401d9ddc  jz      short loc_1401D9E1E
0x1401d9dde  mov     r9, [rsi+50h]
0x1401d9de2  lea     rax, WPP_aac7878291ab3466cf4003e69b0eed30_Traceguids
0x1401d9de9  mov     rcx, [rcx+18h]
0x1401d9ded  mov     dl, dil
0x1401d9df0  mov     [rsp+98h+var_58], ebx
0x1401d9df4  mov     [rsp+98h+var_60], rax
0x1401d9df9  mov     r9, [r9+170h]
0x1401d9e00  mov     [rsp+98h+var_68], bp
0x1401d9e05  mov     [rsp+98h+var_70], 3
0x1401d9e0d  mov     byte ptr [rsp+98h+RemlockSize], 5
0x1401d9e12  mov     r9, [r9+10B0h]
0x1401d9e19  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401d9e1e  mov     eax, ebx
0x1401d9e20  add     rsp, 58h
0x1401d9e24  pop     r15
0x1401d9e26  pop     r14
0x1401d9e28  pop     r13
0x1401d9e2a  pop     r12
0x1401d9e2c  pop     rdi
0x1401d9e2d  pop     rsi
0x1401d9e2e  pop     rbp
0x1401d9e2f  pop     rbx
0x1401d9e30  retn
```
