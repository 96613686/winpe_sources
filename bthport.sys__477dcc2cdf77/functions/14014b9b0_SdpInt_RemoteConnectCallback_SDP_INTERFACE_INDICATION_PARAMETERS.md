# SdpInt_RemoteConnectCallback(_SDP_INTERFACE *,_INDICATION_PARAMETERS *)

- ea: `0x14014b9b0`
- end: `0x14014bc90`
- name: `?SdpInt_RemoteConnectCallback@@YAXPEAU_SDP_INTERFACE@@PEAU_INDICATION_PARAMETERS@@@Z`
- size: `736`
- prototype: `void __fastcall(struct _SDP_INTERFACE *, struct _INDICATION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14014b920`

## callees

- `0x140005608`
- `0x140005b4c`
- `0x140007910`
- `0x140146fc8`
- `0x140148150`
- `0x14014b9b0`
- `0x14014c09c`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14014bc76`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14014bc76`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14014baff`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14014baff`
- `ntoskrnl!IoAllocateIrp` at `0x14014bb1f`
- `ntoskrnl!IoAllocateIrp` at `0x14014bb1f`
- `ntoskrnl!IoFreeIrp` at `0x14014bc5d`
- `ntoskrnl!IoFreeIrp` at `0x14014bc5d`
- `ntoskrnl!rand` at `0x14014ba4c`
- `ntoskrnl!rand` at `0x14014ba4c`
- `ntoskrnl!ExAllocatePool2` at `0x14014ba38`
- `ntoskrnl!ExAllocatePool2` at `0x14014ba38`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014bb93`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014bb93`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014bc3f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014bc3f`

## pseudocode

```c
void __fastcall SdpInt_RemoteConnectCallback(struct _SDP_INTERFACE *a1, struct _INDICATION_PARAMETERS *a2)
{
  struct _INDICATION_PARAMETERS *v2; // rsi
  __int16 DeviceType; // ax
  int v5; // edx
  __int64 Pool2; // rbx
  int v7; // r8d
  __int16 v8; // ax
  PIRP Irp; // rbx
  struct _BRB *Brb; // rax
  unsigned __int64 *p_L2capConnectionListLock; // rbp
  KIRQL v12; // r14
  int v13; // edx
  char v14; // al
  _LIST_ENTRY *Blink; // rcx
  _LIST_ENTRY *p_L2capConnectionList; // rdi
  void *v17; // [rsp+30h] [rbp-58h]
  void *v18; // [rsp+38h] [rbp-50h]
  void *v19; // [rsp+40h] [rbp-48h]

  v2 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      DeviceType != 0,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      8,
      85,
      (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
      (char)v2->ConnectionHandle);
  Pool2 = ExAllocatePool2(64, 1136, 1346917442);
  if ( Pool2 )
  {
    v8 = rand();
    *(_BYTE *)(Pool2 + 1074) = 0;
    *(_WORD *)(Pool2 + 1080) = v8 + 1;
    if ( (int)SdpL2cap_Init((struct _SDP_L2CAP_CONNECTION *)Pool2, a1) >= 0 )
    {
      p_L2capConnectionListLock = &a1->L2capConnectionListLock;
      v12 = KeAcquireSpinLockRaiseToDpc(&a1->L2capConnectionListLock);
      *(_QWORD *)(Pool2 + 968) = v2->BtAddress;
      *(_QWORD *)(Pool2 + 960) = v2->ConnectionHandle;
      *(_DWORD *)(Pool2 + 40) = 0;
      v13 = 4;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (v14 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        v14 = 0;
      LOBYTE(v13) = v14;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v13,
        1,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        8,
        86,
        (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
        Pool2);
      Blink = a1->L2capConnectionList.Blink;
      p_L2capConnectionList = &a1->L2capConnectionList;
      if ( Blink->Flink != p_L2capConnectionList )
        __fastfail(3u);
      *(_QWORD *)(Pool2 + 184) = Blink;
      *(_QWORD *)(Pool2 + 176) = p_L2capConnectionList;
      Blink->Flink = (_LIST_ENTRY *)(Pool2 + 176);
      p_L2capConnectionList->Blink = (_LIST_ENTRY *)(Pool2 + 176);
      KeReleaseSpinLock(p_L2capConnectionListLock, v12);
      SdpL2cap_SendOpenChannelBrb((struct _SDP_L2CAP_CONNECTION *)Pool2, 0, 0);
      return;
    }
    RefObj_ReleaseEx(Pool2, Pool2, 561, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\SdpInterfacep.h");
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    LOBYTE(v5) = 0;
  LOBYTE(v7) = 1;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v5,
    v7,
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    8,
    87,
    (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids);
  if ( IoAcquireRemoveLockEx(
         &a1->DevExt->RemoveLock,
         SdpL2cap_DenyOpenChannelComplete,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\sdpinterface.cpp",
         0xB57u,
         0x20u) >= 0 )
  {
    Irp = IoAllocateIrp(a1->DevExt->BtDevice.FunctionalDeviceObject->StackSize, 0);
    if ( Irp )
    {
      Brb = BthAllocateBrb(BRB_L2CA_OPEN_CHANNEL_RESPONSE, 0x49706453u);
      if ( Brb )
      {
        Brb->BrbL2caOpenChannel.BtAddress = v2->BtAddress;
        Brb->BrbL2caRegisterServer.BtAddress = (unsigned __int64)v2->ConnectionHandle;
        Brb->BrbGetDeviceInterfaceString.DeviceInterfaceStringCbLength = 4;
        Brb->BrbHeader.ClientContext[0] = a1;
        SdpInt_SendBrbAsync(a1, Irp, Brb, SdpL2cap_DenyOpenChannelComplete, Brb, 0, v17, v18, v19);
        return;
      }
      IoFreeIrp(Irp);
    }
    IoReleaseRemoveLockEx(&a1->DevExt->RemoveLock, SdpL2cap_DenyOpenChannelComplete, 0x20u);
  }
}

```

## disassembly

```asm
0x14014b9b0  push    rbx
0x14014b9b2  push    rbp
0x14014b9b3  push    rsi
0x14014b9b4  push    rdi
0x14014b9b5  push    r14
0x14014b9b7  push    r15
0x14014b9b9  sub     rsp, 58h
0x14014b9bd  mov     rsi, rdx
0x14014b9c0  mov     rdi, rcx
0x14014b9c3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014b9ca  xor     r15d, r15d
0x14014b9cd  mov     eax, [rcx+2Ch]
0x14014b9d0  test    al, al
0x14014b9d2  jns     short loc_14014B9DC
0x14014b9d4  cmp     byte ptr [rcx+29h], 5
0x14014b9d8  mov     dl, 1
0x14014b9da  jnb     short loc_14014B9DF
0x14014b9dc  mov     dl, r15b
0x14014b9df  movzx   eax, word ptr [rcx+48h]
0x14014b9e3  lea     rbp, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x14014b9ea  test    ax, ax
0x14014b9ed  setnz   r8b
0x14014b9f1  test    dl, dl
0x14014b9f3  jnz     short loc_14014B9FA
0x14014b9f5  test    ax, ax
0x14014b9f8  jz      short loc_14014BA28
0x14014b9fa  mov     rax, [rsi]
0x14014b9fd  mov     r9, [rcx+40h]
0x14014ba01  mov     rcx, [rcx+18h]
0x14014ba05  mov     [rsp+88h+var_48], rax; void *
0x14014ba0a  mov     [rsp+88h+var_50], rbp
0x14014ba0f  mov     word ptr [rsp+88h+var_58], 55h ; 'U'
0x14014ba16  mov     dword ptr [rsp+88h+var_60], 8
0x14014ba1e  mov     byte ptr [rsp+88h+RemlockSize], 5
0x14014ba23  call    WPP_RECORDER_AND_TRACE_SF_q
0x14014ba28  mov     edx, 470h
0x14014ba2d  mov     ecx, 40h ; '@'
0x14014ba32  mov     r8d, 50485442h
0x14014ba38  call    cs:__imp_ExAllocatePool2
0x14014ba3f  nop     dword ptr [rax+rax+00h]
0x14014ba44  mov     rbx, rax
0x14014ba47  test    rax, rax
0x14014ba4a  jz      short loc_14014BA94
0x14014ba4c  call    cs:__imp_rand
0x14014ba53  nop     dword ptr [rax+rax+00h]
0x14014ba58  mov     rdx, rdi; struct _SDP_INTERFACE *
0x14014ba5b  mov     [rbx+432h], r15b
0x14014ba62  inc     ax
0x14014ba65  mov     rcx, rbx; struct _SDP_L2CAP_CONNECTION *
0x14014ba68  mov     [rbx+438h], ax
0x14014ba6f  call    ?SdpL2cap_Init@@YAJPEAU_SDP_L2CAP_CONNECTION@@PEAU_SDP_INTERFACE@@@Z; SdpL2cap_Init(_SDP_L2CAP_CONNECTION *,_SDP_INTERFACE *)
0x14014ba74  test    eax, eax
0x14014ba76  jns     loc_14014BB8C
0x14014ba7c  lea     r9, aOnecoreDrivers_20; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14014ba83  mov     r8d, 231h
0x14014ba89  mov     rdx, rbx
0x14014ba8c  mov     rcx, rbx
0x14014ba8f  call    RefObj_ReleaseEx
0x14014ba94  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014ba9b  mov     eax, [rcx+2Ch]
0x14014ba9e  test    al, al
0x14014baa0  jns     short loc_14014BAAA
0x14014baa2  cmp     byte ptr [rcx+29h], 2
0x14014baa6  mov     dl, 1
0x14014baa8  jnb     short loc_14014BAAD
0x14014baaa  mov     dl, r15b
0x14014baad  mov     r9, [rcx+40h]
0x14014bab1  mov     r8b, 1
0x14014bab4  mov     rcx, [rcx+18h]
0x14014bab8  mov     [rsp+88h+var_50], rbp; void *
0x14014babd  mov     word ptr [rsp+88h+var_58], 57h ; 'W'; void *
0x14014bac4  mov     dword ptr [rsp+88h+var_60], 8
0x14014bacc  mov     byte ptr [rsp+88h+RemlockSize], 2
0x14014bad1  call    WPP_RECORDER_AND_TRACE_SF_
0x14014bad6  mov     rcx, [rdi]
0x14014bad9  lea     rbp, ?SdpL2cap_DenyOpenChannelComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SdpL2cap_DenyOpenChannelComplete(_DEVICE_OBJECT *,_IRP *,void *)
0x14014bae0  mov     r14d, 20h ; ' '
0x14014bae6  lea     r8, aOnecoreDrivers_28; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14014baed  add     rcx, 38h ; '8'; RemoveLock
0x14014baf1  mov     [rsp+88h+RemlockSize], r14d; RemlockSize
0x14014baf6  mov     r9d, 0B57h; Line
0x14014bafc  mov     rdx, rbp; Tag
0x14014baff  call    cs:__imp_IoAcquireRemoveLockEx
0x14014bb06  nop     dword ptr [rax+rax+00h]
0x14014bb0b  test    eax, eax
0x14014bb0d  js      loc_14014BC82
0x14014bb13  mov     rax, [rdi]
0x14014bb16  xor     edx, edx; ChargeQuota
0x14014bb18  mov     rcx, [rax+8]
0x14014bb1c  mov     cl, [rcx+4Ch]; StackSize
0x14014bb1f  call    cs:__imp_IoAllocateIrp
0x14014bb26  nop     dword ptr [rax+rax+00h]
0x14014bb2b  mov     rbx, rax
0x14014bb2e  test    rax, rax
0x14014bb31  jz      loc_14014BC69
0x14014bb37  mov     edx, 49706453h; unsigned int
0x14014bb3c  mov     ecx, 103h; enum _BRB_TYPE
0x14014bb41  call    ?BthAllocateBrb@@YAPEAU_BRB@@W4_BRB_TYPE@@K@Z; BthAllocateBrb(_BRB_TYPE,ulong)
0x14014bb46  test    rax, rax
0x14014bb49  jz      loc_14014BC5A
0x14014bb4f  mov     rcx, [rsi+8]
0x14014bb53  mov     r9, rbp; int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)
0x14014bb56  mov     [rax+80h], rcx
0x14014bb5d  mov     r8, rax; struct _BRB *
0x14014bb60  mov     rcx, [rsi]
0x14014bb63  mov     rdx, rbx; struct _IRP *
0x14014bb66  mov     [rax+70h], rcx
0x14014bb6a  mov     rcx, rdi; struct _SDP_INTERFACE *
0x14014bb6d  mov     [rsp+88h+var_60], r15; void *
0x14014bb72  mov     dword ptr [rax+78h], 4
0x14014bb79  mov     [rax+48h], rdi
0x14014bb7d  mov     qword ptr [rsp+88h+RemlockSize], rax; void *
0x14014bb82  call    ?SdpInt_SendBrbAsync@@YAJPEAU_SDP_INTERFACE@@PEAU_IRP@@PEAU_BRB@@P6AJPEAU_DEVICE_OBJECT@@1PEAX@Z44444@Z; SdpInt_SendBrbAsync(_SDP_INTERFACE *,_IRP *,_BRB *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *,void *,void *,void *,void *)
0x14014bb87  jmp     loc_14014BC82
0x14014bb8c  lea     rbp, [rdi+8]
0x14014bb90  mov     rcx, rbp; SpinLock
0x14014bb93  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14014bb9a  nop     dword ptr [rax+rax+00h]
0x14014bb9f  mov     rcx, [rsi+8]
0x14014bba3  mov     r14b, al
0x14014bba6  mov     [rbx+3C8h], rcx
0x14014bbad  mov     rcx, [rsi]
0x14014bbb0  mov     [rbx+3C0h], rcx
0x14014bbb7  mov     [rbx+28h], r15d
0x14014bbbb  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014bbc2  mov     edx, 4
0x14014bbc7  mov     ecx, [r10+2Ch]
0x14014bbcb  test    cl, cl
0x14014bbcd  jns     short loc_14014BBD7
0x14014bbcf  mov     al, 1
0x14014bbd1  cmp     [r10+29h], dl
0x14014bbd5  jnb     short loc_14014BBDA
0x14014bbd7  mov     al, r15b
0x14014bbda  mov     r9, [r10+40h]
0x14014bbde  lea     r8, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x14014bbe5  mov     rcx, [r10+18h]
0x14014bbe9  mov     [rsp+88h+var_48], rbx
0x14014bbee  mov     [rsp+88h+var_50], r8
0x14014bbf3  mov     r8b, 1
0x14014bbf6  mov     word ptr [rsp+88h+var_58], 56h ; 'V'
0x14014bbfd  mov     dword ptr [rsp+88h+var_60], 8
0x14014bc05  mov     byte ptr [rsp+88h+RemlockSize], dl
0x14014bc09  mov     dl, al
0x14014bc0b  call    WPP_RECORDER_AND_TRACE_SF_q
0x14014bc10  mov     rcx, [rdi+18h]
0x14014bc14  add     rdi, 10h
0x14014bc18  cmp     [rcx], rdi
0x14014bc1b  jz      short loc_14014BC24
0x14014bc1d  mov     ecx, 3
0x14014bc22  int     29h; Win8: RtlFailFast(ecx)
0x14014bc24  lea     rax, [rbx+0B0h]
0x14014bc2b  mov     dl, r14b; NewIrql
0x14014bc2e  mov     [rax+8], rcx
0x14014bc32  mov     [rax], rdi
0x14014bc35  mov     [rcx], rax
0x14014bc38  mov     rcx, rbp; SpinLock
0x14014bc3b  mov     [rdi+8], rax
0x14014bc3f  call    cs:__imp_KeReleaseSpinLock
0x14014bc46  nop     dword ptr [rax+rax+00h]
0x14014bc4b  xor     r8d, r8d; unsigned __int16
0x14014bc4e  xor     edx, edx; unsigned __int8
0x14014bc50  mov     rcx, rbx; struct _SDP_L2CAP_CONNECTION *
0x14014bc53  call    ?SdpL2cap_SendOpenChannelBrb@@YAJPEAU_SDP_L2CAP_CONNECTION@@EG@Z; SdpL2cap_SendOpenChannelBrb(_SDP_L2CAP_CONNECTION *,uchar,ushort)
0x14014bc58  jmp     short loc_14014BC82
0x14014bc5a  mov     rcx, rbx; Irp
0x14014bc5d  call    cs:__imp_IoFreeIrp
0x14014bc64  nop     dword ptr [rax+rax+00h]
0x14014bc69  mov     rcx, [rdi]
0x14014bc6c  mov     r8d, r14d; RemlockSize
0x14014bc6f  add     rcx, 38h ; '8'; RemoveLock
0x14014bc73  mov     rdx, rbp; Tag
0x14014bc76  call    cs:__imp_IoReleaseRemoveLockEx
0x14014bc7d  nop     dword ptr [rax+rax+00h]
0x14014bc82  add     rsp, 58h
0x14014bc86  pop     r15
0x14014bc88  pop     r14
0x14014bc8a  pop     rdi
0x14014bc8b  pop     rsi
0x14014bc8c  pop     rbp
0x14014bc8d  pop     rbx
0x14014bc8e  retn
```
