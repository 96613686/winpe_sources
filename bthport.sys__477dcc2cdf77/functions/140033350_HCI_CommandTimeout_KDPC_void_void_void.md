# HCI_CommandTimeout(_KDPC *,void *,void *,void *)

- ea: `0x140033350`
- end: `0x1400336bc`
- name: `?HCI_CommandTimeout@@YAXPEAU_KDPC@@PEAX11@Z`
- size: `876`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000113c`
- `0x140001358`
- `0x140005608`
- `0x140005690`
- `0x140005b4c`
- `0x140006f70`
- `0x14001facc`
- `0x140033250`
- `0x140033350`
- `0x1400af954`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14003363c`
- `ntoskrnl!IoQueueWorkItem` at `0x14003363c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14003361c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14003361c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033553`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033553`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400335ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400335ce`

## string_xrefs

- `0x14003360e`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hcicommand.cpp`

## pseudocode

```c
void __fastcall HCI_CommandTimeout(
        struct _KDPC *Dpc,
        struct _BIP *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  struct _BIP *v4; // rdi
  char v5; // bl
  __int16 DeviceType; // ax
  char *Context; // rbp
  unsigned __int16 *v8; // rsi
  int v9; // edx
  int v10; // r8d
  struct DEVICE_EXTENSION *BtDevice; // r15
  struct HCI_INTERFACE *PhysicalDeviceObject; // r14
  int v13; // ecx
  int v14; // r9d
  int v15; // edx
  __int64 *v16; // r8
  KIRQL v17; // al
  _QWORD *v18; // rdx
  KIRQL v19; // r13
  __int64 v20; // r8
  _QWORD *v21; // rcx
  _LIST_ENTRY *Blink; // r8
  int v23; // r8d
  __int16 v24; // ax
  __int64 *v25; // rdx
  __int16 v26[2]; // [rsp+50h] [rbp-68h] BYREF
  int v27; // [rsp+54h] [rbp-64h] BYREF
  _GUID *p_DeviceExtensionSessionId; // [rsp+58h] [rbp-60h] BYREF
  __int64 v29[11]; // [rsp+60h] [rbp-58h] BYREF
  char v30; // [rsp+C8h] [rbp+10h] BYREF

  v4 = DeferredContext;
  v5 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
    || (LOBYTE(DeferredContext) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
  {
    LOBYTE(DeferredContext) = 0;
  }
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)DeferredContext || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)DeferredContext,
      DeviceType != 0,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      25,
      (__int64)WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids,
      (char)v4);
  Context = (char *)v4->PacketContexts[1].Context;
  v8 = (unsigned __int16 *)(Context + 244);
  HCI_CommandIndexFromOpCode(*((_WORD *)Context + 122));
  BtDevice = (struct DEVICE_EXTENSION *)v4->BtDevice;
  PhysicalDeviceObject = (struct HCI_INTERFACE *)v4->BtDevice[11].PhysicalDeviceObject;
  if ( (unsigned int)dword_140197150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140197150, 0x400000000114LL) )
  {
    v26[0] = *v8;
    p_DeviceExtensionSessionId = &BtDevice->DeviceExtensionSessionId;
    v30 = v10;
    v27 = v14;
    v29[0] = 50333696;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
      v13,
      (unsigned int)&unk_140189998,
      v10,
      v14,
      (__int64)v29,
      (__int64)&p_DeviceExtensionSessionId,
      (__int64)v26,
      (__int64)&v27,
      (__int64)&v30);
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    LOBYTE(v9) = 0;
  LOBYTE(v10) = 1;
  WPP_RECORDER_AND_TRACE_SF_d(
    WPP_GLOBAL_Control->AttachedDevice,
    v9,
    v10,
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    2,
    26,
    (__int64)WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids,
    *v8);
  if ( BthCancelBipEx(v4, 0) )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v15) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v15) = 0;
    v16 = WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids;
    LOBYTE(v16) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v15,
      (_DWORD)v16,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      2,
      27,
      (__int64)WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids);
  }
  v17 = KeAcquireSpinLockRaiseToDpc(&PhysicalDeviceObject->HciLock);
  v18 = Context + 184;
  v19 = v17;
  v20 = *((_QWORD *)Context + 23);
  if ( *(char **)(v20 + 8) != Context + 184
    || (v21 = (_QWORD *)*((_QWORD *)Context + 24), (_QWORD *)*v21 != v18)
    || (*v21 = v20,
        *(_QWORD *)(v20 + 8) = v21,
        *((_QWORD *)Context + 24) = Context + 184,
        *v18 = v18,
        v4->Status = -1073741643,
        Blink = PhysicalDeviceObject->BipQueue.Blink,
        Blink->Flink != &PhysicalDeviceObject->BipQueue) )
  {
    __fastfail(3u);
  }
  v4->ListEntry.Flink = &PhysicalDeviceObject->BipQueue;
  v4->ListEntry.Blink = Blink;
  Blink->Flink = &v4->ListEntry;
  PhysicalDeviceObject->BipQueue.Blink = &v4->ListEntry;
  HCI_ThreadSignalEvent(PhysicalDeviceObject, HCI_EVENT_IDX_BIP);
  KeReleaseSpinLock(&PhysicalDeviceObject->HciLock, v19);
  BthReportError(BtDevice, -2147155965, *v8, Context + 244, (unsigned __int8)Context[246] + 3);
  IoAcquireRemoveLockEx(
    &BtDevice->RemoveLock,
    HCI_CommandTimeout,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcicommand.cpp",
    0x750u,
    0x20u);
  IoQueueWorkItem(*((PIO_WORKITEM *)Context + 17), HCI_CommandTimeoutWorker, DelayedWorkQueue, (PVOID)v4);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v5 = 0;
  v24 = WPP_GLOBAL_Control->DeviceType;
  if ( v5 || v24 )
  {
    v25 = WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids;
    LOBYTE(v25) = v5;
    LOBYTE(v23) = v24 != 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v25,
      v23,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      28,
      (__int64)WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids);
  }
}

```

## disassembly

```asm
0x140033350  push    rbx
0x140033352  push    rbp
0x140033353  push    rsi
0x140033354  push    rdi
0x140033355  push    r12
0x140033357  push    r13
0x140033359  push    r14
0x14003335b  push    r15
0x14003335d  sub     rsp, 78h
0x140033361  mov     rdi, rdx
0x140033364  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003336b  xor     r12d, r12d
0x14003336e  mov     eax, [rcx+2Ch]
0x140033371  lea     r13d, [r12+2]
0x140033376  lea     ebx, [r12+1]
0x14003337b  test    r13b, al
0x14003337e  jz      short loc_140033388
0x140033380  cmp     byte ptr [rcx+29h], 5
0x140033384  mov     dl, bl
0x140033386  jnb     short loc_14003338B
0x140033388  mov     dl, r12b
0x14003338b  movzx   eax, word ptr [rcx+48h]
0x14003338f  lea     r9, WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids
0x140033396  test    ax, ax
0x140033399  setnz   r8b
0x14003339d  test    dl, dl
0x14003339f  jnz     short loc_1400333A6
0x1400333a1  test    ax, ax
0x1400333a4  jz      short loc_1400333CE
0x1400333a6  mov     [rsp+0B8h+var_78], rdi
0x1400333ab  mov     [rsp+0B8h+var_80], r9
0x1400333b0  mov     r9, [rcx+40h]
0x1400333b4  mov     rcx, [rcx+18h]
0x1400333b8  mov     word ptr [rsp+0B8h+var_88], 19h
0x1400333bf  mov     dword ptr [rsp+0B8h+var_90], r13d
0x1400333c4  mov     byte ptr [rsp+0B8h+RemlockSize], 5
0x1400333c9  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400333ce  mov     rbp, [rdi+98h]
0x1400333d5  lea     rsi, [rbp+0F4h]
0x1400333dc  movzx   ecx, word ptr [rsi]; unsigned __int16
0x1400333df  call    ?HCI_CommandIndexFromOpCode@@YAKG@Z; HCI_CommandIndexFromOpCode(ushort)
0x1400333e4  mov     r15, [rdi]
0x1400333e7  mov     r14, [r15+170h]
0x1400333ee  movzx   eax, word ptr [r14+1030h]
0x1400333f6  test    ax, ax
0x1400333f9  jz      short loc_14003340C
0x1400333fb  cmp     ax, [rsi]
0x1400333fe  jnz     short loc_14003340C
0x140033400  mov     r8b, [rbp+0F7h]
0x140033407  mov     r9d, ebx
0x14003340a  jmp     short loc_140033412
0x14003340c  mov     r8b, r12b
0x14003340f  mov     r9d, r12d
0x140033412  mov     eax, cs:dword_140197150
0x140033418  cmp     eax, 4
0x14003341b  jbe     loc_1400334A6
0x140033421  mov     rdx, 400000000114h
0x14003342b  lea     rcx, dword_140197150
0x140033432  call    _tlgKeywordOn
0x140033437  test    al, al
0x140033439  jz      short loc_1400334A6
0x14003343b  movzx   eax, word ptr [rsi]
0x14003343e  lea     rdx, unk_140189998
0x140033445  mov     [rsp+0B8h+var_68], ax
0x14003344a  lea     rax, [r15+2D0h]
0x140033451  mov     [rsp+0B8h+var_60], rax
0x140033456  lea     rax, [rsp+0B8h+arg_8]
0x14003345e  mov     [rsp+0B8h+var_78], rax
0x140033463  lea     rax, [rsp+0B8h+var_64]
0x140033468  mov     [rsp+0B8h+var_80], rax
0x14003346d  lea     rax, [rsp+0B8h+var_68]
0x140033472  mov     [rsp+0B8h+var_88], rax
0x140033477  lea     rax, [rsp+0B8h+var_60]
0x14003347c  mov     [rsp+0B8h+var_90], rax
0x140033481  lea     rax, [rsp+0B8h+var_58]
0x140033486  mov     qword ptr [rsp+0B8h+RemlockSize], rax
0x14003348b  mov     [rsp+0B8h+arg_8], r8b
0x140033493  mov     [rsp+0B8h+var_64], r9d
0x140033498  mov     [rsp+0B8h+var_58], 3000800h
0x1400334a1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x1400334a6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400334ad  mov     eax, [rcx+2Ch]
0x1400334b0  test    r13b, al
0x1400334b3  jz      short loc_1400334BD
0x1400334b5  mov     dl, bl
0x1400334b7  cmp     [rcx+29h], r13b
0x1400334bb  jnb     short loc_1400334C0
0x1400334bd  mov     dl, r12b
0x1400334c0  movzx   eax, word ptr [rsi]
0x1400334c3  mov     r8b, bl
0x1400334c6  mov     r9, [rcx+40h]
0x1400334ca  mov     rcx, [rcx+18h]
0x1400334ce  mov     dword ptr [rsp+0B8h+var_78], eax
0x1400334d2  lea     rax, WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids
0x1400334d9  mov     [rsp+0B8h+var_80], rax
0x1400334de  mov     word ptr [rsp+0B8h+var_88], 1Ah
0x1400334e5  mov     dword ptr [rsp+0B8h+var_90], r13d
0x1400334ea  mov     byte ptr [rsp+0B8h+RemlockSize], r13b
0x1400334ef  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400334f4  xor     edx, edx; bool
0x1400334f6  mov     rcx, rdi; struct _BIP *
0x1400334f9  call    ?BthCancelBipEx@@YAEPEAU_BIP@@_N@Z; BthCancelBipEx(_BIP *,bool)
0x1400334fe  test    al, al
0x140033500  jz      short loc_140033549
0x140033502  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033509  mov     eax, [rcx+2Ch]
0x14003350c  test    r13b, al
0x14003350f  jz      short loc_140033519
0x140033511  cmp     byte ptr [rcx+29h], 3
0x140033515  mov     dl, bl
0x140033517  jnb     short loc_14003351C
0x140033519  mov     dl, r12b
0x14003351c  mov     r9, [rcx+40h]
0x140033520  lea     r8, WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids
0x140033527  mov     rcx, [rcx+18h]
0x14003352b  mov     [rsp+0B8h+var_80], r8
0x140033530  mov     r8b, bl
0x140033533  mov     word ptr [rsp+0B8h+var_88], 1Bh
0x14003353a  mov     dword ptr [rsp+0B8h+var_90], r13d
0x14003353f  mov     byte ptr [rsp+0B8h+RemlockSize], 3
0x140033544  call    WPP_RECORDER_AND_TRACE_SF_
0x140033549  lea     r12, [r14+7B0h]
0x140033550  mov     rcx, r12; SpinLock
0x140033553  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003355a  nop     dword ptr [rax+rax+00h]
0x14003355f  lea     rdx, [rbp+0B8h]
0x140033566  mov     r13b, al
0x140033569  mov     r8, [rdx]
0x14003356c  cmp     [r8+8], rdx
0x140033570  jnz     loc_1400336B5
0x140033576  mov     rcx, [rdx+8]
0x14003357a  cmp     [rcx], rdx
0x14003357d  jnz     loc_1400336B5
0x140033583  mov     [rcx], r8
0x140033586  mov     [r8+8], rcx
0x14003358a  mov     [rdx+8], rdx
0x14003358e  mov     [rdx], rdx
0x140033591  lea     rdx, [r14+9A0h]
0x140033598  mov     dword ptr [rdi+0Ch], 0C00000B5h
0x14003359f  mov     r8, [rdx+8]
0x1400335a3  cmp     [r8], rdx
0x1400335a6  jnz     loc_1400336B5
0x1400335ac  lea     rax, [rdi+58h]
0x1400335b0  mov     rcx, r14; struct HCI_INTERFACE *
0x1400335b3  mov     [rax], rdx
0x1400335b6  mov     [rax+8], r8
0x1400335ba  mov     [r8], rax
0x1400335bd  mov     [rdx+8], rax
0x1400335c1  mov     edx, ebx; enum HciThreadEventIndex
0x1400335c3  call    ?HCI_ThreadSignalEvent@@YAXPEAUHCI_INTERFACE@@W4HciThreadEventIndex@@@Z; HCI_ThreadSignalEvent(HCI_INTERFACE *,HciThreadEventIndex)
0x1400335c8  mov     dl, r13b; NewIrql
0x1400335cb  mov     rcx, r12; SpinLock
0x1400335ce  call    cs:__imp_KeReleaseSpinLock
0x1400335d5  nop     dword ptr [rax+rax+00h]
0x1400335da  movzx   eax, byte ptr [rbp+0F6h]
0x1400335e1  mov     r9, rsi; void *
0x1400335e4  movzx   r8d, word ptr [rsi]; unsigned int
0x1400335e8  add     eax, 3
0x1400335eb  mov     edx, 80050003h; int
0x1400335f0  mov     [rsp+0B8h+RemlockSize], eax; unsigned int
0x1400335f4  mov     rcx, r15; struct DEVICE_EXTENSION *
0x1400335f7  call    ?BthReportError@@YAXPEAUDEVICE_EXTENSION@@JKPEAXK@Z; BthReportError(DEVICE_EXTENSION *,long,ulong,void *,ulong)
0x1400335fc  lea     rcx, [r15+38h]; RemoveLock
0x140033600  mov     [rsp+0B8h+RemlockSize], 20h ; ' '; RemlockSize
0x140033608  mov     r9d, 750h; Line
0x14003360e  lea     r8, aOnecoreDrivers_61; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140033615  lea     rdx, ?HCI_CommandTimeout@@YAXPEAU_KDPC@@PEAX11@Z; Tag
0x14003361c  call    cs:__imp_IoAcquireRemoveLockEx
0x140033623  nop     dword ptr [rax+rax+00h]
0x140033628  mov     rcx, [rbp+88h]; IoWorkItem
0x14003362f  lea     rdx, ?HCI_CommandTimeoutWorker@@YAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x140033636  mov     r9, rdi; Context
0x140033639  mov     r8d, ebx; QueueType
0x14003363c  call    cs:__imp_IoQueueWorkItem
0x140033643  nop     dword ptr [rax+rax+00h]
0x140033648  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003364f  mov     eax, [rcx+2Ch]
0x140033652  test    al, 2
0x140033654  jz      short loc_14003365C
0x140033656  cmp     byte ptr [rcx+29h], 5
0x14003365a  jnb     short loc_140033660
0x14003365c  xor     edx, edx
0x14003365e  mov     bl, dl
0x140033660  movzx   eax, word ptr [rcx+48h]
0x140033664  test    ax, ax
0x140033667  setnz   r8b
0x14003366b  test    bl, bl
0x14003366d  jnz     short loc_140033674
0x14003366f  test    ax, ax
0x140033672  jz      short loc_1400336A3
0x140033674  mov     r9, [rcx+40h]
0x140033678  lea     rdx, WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids
0x14003367f  mov     rcx, [rcx+18h]
0x140033683  mov     [rsp+0B8h+var_80], rdx
0x140033688  mov     dl, bl
0x14003368a  mov     word ptr [rsp+0B8h+var_88], 1Ch
0x140033691  mov     dword ptr [rsp+0B8h+var_90], 2
0x140033699  mov     byte ptr [rsp+0B8h+RemlockSize], 5
0x14003369e  call    WPP_RECORDER_AND_TRACE_SF_
0x1400336a3  add     rsp, 78h
0x1400336a7  pop     r15
0x1400336a9  pop     r14
0x1400336ab  pop     r13
0x1400336ad  pop     r12
0x1400336af  pop     rdi
0x1400336b0  pop     rsi
0x1400336b1  pop     rbp
0x1400336b2  pop     rbx
0x1400336b3  retn
0x1400336b5  mov     ecx, 3
0x1400336ba  int     29h; Win8: RtlFailFast(ecx)
```
