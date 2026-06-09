# HCI_CxnDestroyRef(_REF_OBJ *)

- ea: `0x14003b790`
- end: `0x14003bb2f`
- name: `?HCI_CxnDestroyRef@@YAXPEAU_REF_OBJ@@@Z`
- size: `927`
- prototype: `void __fastcall(struct _REF_OBJ *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140005b4c`
- `0x14003b790`
- `0x14003cb4c`
- `0x14003f26c`
- `0x14004b768`
- `0x14015ce38`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14003bb0a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14003bb0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003baf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003baf1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003b836`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003b836`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003b9bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003b9bc`

## pseudocode

```c
void __fastcall HCI_CxnDestroyRef(struct _REF_OBJ *a1)
{
  struct _HCI_CONNECTION *p_DebugInfo; // rdi
  struct _REF_OBJ *v2; // r14
  struct _REF_OBJ_DEBUG_INFO *DebugInfo; // r13
  char v4; // bl
  char v5; // dl
  __int16 DeviceType; // ax
  HCI_INTERFACE *Hci; // rsi
  __int64 v8; // rdx
  _LIST_ENTRY *p_ListEntry; // rcx
  _LIST_ENTRY *v10; // rdx
  _LIST_ENTRY *v11; // rax
  __int64 v12; // rdx
  PDEVICE_OBJECT v13; // rcx
  char v14; // dl
  const char *v15; // rsi
  __int16 v16; // r11
  _LIST_ENTRY *Flink; // r8
  _LIST_ENTRY *Blink; // rax
  _LIST_ENTRY **p_Flink; // r8
  _LIST_ENTRY *v20; // rax
  _LIST_ENTRY *p_ChannelPropertyList; // rcx
  _LIST_ENTRY *v22; // rdx
  _LIST_ENTRY *v23; // rcx
  __int16 v24; // ax
  HCI_INTERFACE *v25; // rcx
  DEVICE_EXTENSION *DevExt; // rbx
  KSPIN_LOCK *SpinLock; // [rsp+50h] [rbp-28h]
  struct _LIST_ENTRY v28; // [rsp+58h] [rbp-20h] BYREF
  KIRQL NewIrql; // [rsp+C8h] [rbp+50h]
  _LIST_ENTRY *p_HciCxnZombie; // [rsp+D0h] [rbp+58h] BYREF
  _LIST_ENTRY *p_HciCxnPending; // [rsp+D8h] [rbp+60h] BYREF

  p_DebugInfo = (struct _HCI_CONNECTION *)&a1[-1].DebugInfo;
  v2 = a1;
  DebugInfo = a1[1].DebugInfo;
  v4 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v5 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v5 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v5 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      DeviceType != 0,
      *((_QWORD *)DebugInfo + 263),
      5,
      2,
      59,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
      a1);
  Hci = p_DebugInfo->Hci;
  HCI_CxnReconnect(p_DebugInfo);
  SpinLock = &Hci->HciLock;
  NewIrql = KeAcquireSpinLockRaiseToDpc(&Hci->HciLock);
  p_HciCxnZombie = &Hci->HciCxnZombie;
  if ( !(unsigned __int8)_contains___base_list_impl_U__intrusive_member_hook_traits__MPEQ_HCI_CONNECTION__U_LIST_ENTRY__0CA__Foundation_Bluetooth_Microsoft__V__intrusive_list_ref_t_U__intrusive_member_hook_traits__MPEQ_HCI_CONNECTION__U_LIST_ENTRY__0CA__Foundation_Bluetooth_Microsoft___234__Details_Foundation_Bluetooth_Microsoft__QEBA_NAEBU_HCI_CONNECTION___Z(
                           &p_HciCxnZombie,
                           p_DebugInfo) )
  {
    p_HciCxnZombie = &Hci->HciCxnList;
    p_HciCxnPending = &Hci->HciCxnPending;
    if ( (unsigned __int8)_contains___base_list_impl_U__intrusive_member_hook_traits__MPEQ_HCI_CONNECTION__U_LIST_ENTRY__0CA__Foundation_Bluetooth_Microsoft__V__intrusive_list_ref_t_U__intrusive_member_hook_traits__MPEQ_HCI_CONNECTION__U_LIST_ENTRY__0CA__Foundation_Bluetooth_Microsoft___234__Details_Foundation_Bluetooth_Microsoft__QEBA_NAEBU_HCI_CONNECTION___Z(
                            &p_HciCxnZombie,
                            v8) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v14 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        v14 = 0;
      v15 = "Destroyed connection still in active list.";
      v16 = 60;
    }
    else if ( (unsigned __int8)_contains___base_list_impl_U__intrusive_member_hook_traits__MPEQ_HCI_CONNECTION__U_LIST_ENTRY__0CA__Foundation_Bluetooth_Microsoft__V__intrusive_list_ref_t_U__intrusive_member_hook_traits__MPEQ_HCI_CONNECTION__U_LIST_ENTRY__0CA__Foundation_Bluetooth_Microsoft___234__Details_Foundation_Bluetooth_Microsoft__QEBA_NAEBU_HCI_CONNECTION___Z(
                                 &p_HciCxnPending,
                                 v12) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v14 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        v14 = 0;
      v15 = "Destroyed connection still in pending list.";
      v16 = 61;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v14 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        v14 = 0;
      v15 = "Destroyed connection still in some list.";
      v16 = 62;
    }
    WPP_RECORDER_AND_TRACE_SF_q(
      v13->AttachedDevice,
      v14,
      1,
      *((_QWORD *)DebugInfo + 263),
      2,
      2,
      v16,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
      p_DebugInfo);
    MicrosoftTelemetryAssertTriggeredMsgKM(v15);
    Flink = p_DebugInfo->ListEntry.Flink;
    if ( Flink->Blink == &p_DebugInfo->ListEntry )
    {
      Blink = p_DebugInfo->ListEntry.Blink;
      if ( Blink->Flink == &p_DebugInfo->ListEntry )
      {
        v2 = a1;
        Blink->Flink = Flink;
        Flink->Blink = Blink;
        goto LABEL_28;
      }
    }
LABEL_41:
    __fastfail(3u);
  }
  p_ListEntry = &p_DebugInfo->ListEntry;
  v10 = p_DebugInfo->ListEntry.Flink;
  if ( v10->Blink != &p_DebugInfo->ListEntry )
    goto LABEL_41;
  v11 = p_DebugInfo->ListEntry.Blink;
  if ( v11->Flink != p_ListEntry )
    goto LABEL_41;
  v11->Flink = v10;
  v10->Blink = v11;
  p_DebugInfo->ListEntry.Blink = &p_DebugInfo->ListEntry;
  p_ListEntry->Flink = p_ListEntry;
LABEL_28:
  KeReleaseSpinLock(SpinLock, NewIrql);
  v28.Blink = &v28;
  p_Flink = &p_DebugInfo->ChannelPropertyList.Flink;
  v28.Flink = &v28;
  while ( 1 )
  {
    v20 = *p_Flink;
    if ( *p_Flink == (_LIST_ENTRY *)p_Flink )
      break;
    p_ChannelPropertyList = &p_DebugInfo->ChannelPropertyList;
    if ( v20->Blink != &p_DebugInfo->ChannelPropertyList )
      goto LABEL_41;
    v22 = v20->Flink;
    if ( v20->Flink->Blink != v20 )
      goto LABEL_41;
    p_ChannelPropertyList->Flink = v22;
    v22->Blink = p_ChannelPropertyList;
    LODWORD(v20[3].Blink) = -1073741667;
    v23 = v28.Blink;
    if ( v28.Blink->Flink != &v28 )
      goto LABEL_41;
    v20->Blink = v28.Blink;
    v20->Flink = &v28;
    v23->Flink = v20;
    v28.Blink = v20;
  }
  HCI_CxnDrainUpdateList(&v28);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v4 = 0;
  v24 = WPP_GLOBAL_Control->DeviceType;
  if ( v4 || v24 )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      v24 != 0,
      *((_QWORD *)DebugInfo + 263),
      5,
      2,
      63,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
      v2);
  RefObj_ReleaseEx(
    p_DebugInfo->Dib,
    p_DebugInfo,
    1739,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciconnection.cpp");
  v25 = p_DebugInfo->Hci;
  DevExt = v25->DevExt;
  RefObj_ReleaseEx(
    &v25->RefObj,
    p_DebugInfo,
    1749,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciconnection.cpp");
  p_DebugInfo->Dib = 0;
  p_DebugInfo->Hci = 0;
  p_DebugInfo->Signature = -559038737;
  ExFreePoolWithTag(p_DebugInfo, 0);
  IoReleaseRemoveLockEx(&DevExt->RemoveLock, p_DebugInfo, 0x20u);
}

```

## disassembly

```asm
0x14003b790  mov     [rsp-40h+arg_0], rcx
0x14003b795  push    rbp
0x14003b796  push    rbx
0x14003b797  push    rsi
0x14003b798  push    rdi
0x14003b799  push    r12
0x14003b79b  push    r13
0x14003b79d  push    r14
0x14003b79f  push    r15
0x14003b7a1  mov     rbp, rsp
0x14003b7a4  sub     rsp, 78h
0x14003b7a8  lea     rdi, [rcx-8]
0x14003b7ac  mov     r14, rcx
0x14003b7af  mov     r13, [rdi+30h]
0x14003b7b3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003b7ba  xor     r15d, r15d
0x14003b7bd  mov     bl, 1
0x14003b7bf  mov     eax, [rcx+2Ch]
0x14003b7c2  lea     r12d, [r15+2]
0x14003b7c6  test    r12b, al
0x14003b7c9  jz      short loc_14003B7D3
0x14003b7cb  cmp     byte ptr [rcx+29h], 5
0x14003b7cf  mov     dl, bl
0x14003b7d1  jnb     short loc_14003B7D6
0x14003b7d3  mov     dl, r15b
0x14003b7d6  movzx   eax, word ptr [rcx+48h]
0x14003b7da  lea     r9, WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids
0x14003b7e1  test    ax, ax
0x14003b7e4  setnz   r8b
0x14003b7e8  test    dl, dl
0x14003b7ea  jnz     short loc_14003B7F1
0x14003b7ec  test    ax, ax
0x14003b7ef  jz      short loc_14003B81C
0x14003b7f1  mov     rcx, [rcx+18h]
0x14003b7f5  mov     [rsp+78h+var_38], r14
0x14003b7fa  mov     [rsp+78h+var_40], r9
0x14003b7ff  mov     r9, [r13+838h]
0x14003b806  mov     [rsp+78h+var_48], 3Bh ; ';'
0x14003b80d  mov     [rsp+78h+var_50], r12d
0x14003b812  mov     [rsp+78h+var_58], 5
0x14003b817  call    WPP_RECORDER_AND_TRACE_SF_q
0x14003b81c  mov     rsi, [rdi+38h]
0x14003b820  mov     rcx, rdi; struct _HCI_CONNECTION *
0x14003b823  call    ?HCI_CxnReconnect@@YAJPEAU_HCI_CONNECTION@@@Z; HCI_CxnReconnect(_HCI_CONNECTION *)
0x14003b828  lea     rax, [rsi+7B0h]
0x14003b82f  mov     rcx, rax; SpinLock
0x14003b832  mov     [rbp+SpinLock], rax
0x14003b836  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003b83d  nop     dword ptr [rax+rax+00h]
0x14003b842  lea     rcx, [rsi+7C8h]
0x14003b849  mov     rdx, rdi
0x14003b84c  mov     [rbp+NewIrql], al
0x14003b84f  mov     [rbp+arg_10], rcx
0x14003b853  lea     rcx, [rbp+arg_10]
0x14003b857  call    ?contains@?$base_list_impl@U?$intrusive_member_hook_traits@$MPEQ_HCI_CONNECTION@@U_LIST_ENTRY@@0CA@@Foundation@Bluetooth@Microsoft@@V?$intrusive_list_ref_t@U?$intrusive_member_hook_traits@$MPEQ_HCI_CONNECTION@@U_LIST_ENTRY@@0CA@@Foundation@Bluetooth@Microsoft@@@234@@Details@Foundation@Bluetooth@Microsoft@@QEBA_NAEBU_HCI_CONNECTION@@@Z
0x14003b85c  test    al, al
0x14003b85e  jz      short loc_14003B891
0x14003b860  lea     rcx, [rdi+20h]
0x14003b864  mov     rdx, [rcx]
0x14003b867  cmp     [rdx+8], rcx
0x14003b86b  jnz     loc_14003BB28
0x14003b871  mov     rax, [rcx+8]
0x14003b875  cmp     [rax], rcx
0x14003b878  jnz     loc_14003BB28
0x14003b87e  mov     [rax], rdx
0x14003b881  mov     [rdx+8], rax
0x14003b885  mov     [rcx+8], rcx
0x14003b889  mov     [rcx], rcx
0x14003b88c  jmp     loc_14003B9B5
0x14003b891  lea     rax, [rsi+7B8h]
0x14003b898  mov     [rbp+arg_10], rax
0x14003b89c  lea     rcx, [rbp+arg_10]
0x14003b8a0  lea     rax, [rsi+7D8h]
0x14003b8a7  mov     [rbp+arg_18], rax
0x14003b8ab  call    ?contains@?$base_list_impl@U?$intrusive_member_hook_traits@$MPEQ_HCI_CONNECTION@@U_LIST_ENTRY@@0CA@@Foundation@Bluetooth@Microsoft@@V?$intrusive_list_ref_t@U?$intrusive_member_hook_traits@$MPEQ_HCI_CONNECTION@@U_LIST_ENTRY@@0CA@@Foundation@Bluetooth@Microsoft@@@234@@Details@Foundation@Bluetooth@Microsoft@@QEBA_NAEBU_HCI_CONNECTION@@@Z
0x14003b8b0  test    al, al
0x14003b8b2  jz      short loc_14003B8DD
0x14003b8b4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003b8bb  mov     eax, [rcx+2Ch]
0x14003b8be  test    r12b, al
0x14003b8c1  jz      short loc_14003B8CB
0x14003b8c3  mov     dl, bl
0x14003b8c5  cmp     [rcx+29h], r12b
0x14003b8c9  jnb     short loc_14003B8CE
0x14003b8cb  mov     dl, r15b
0x14003b8ce  lea     rsi, aDestroyedConne_0; __annotation("Debug", "TelemetryAssert", "false", "Destroyed connection still in active list.")
0x14003b8d5  mov     r11d, 3Ch ; '<'
0x14003b8db  jmp     short loc_14003B93A
0x14003b8dd  lea     rcx, [rbp+arg_18]
0x14003b8e1  call    ?contains@?$base_list_impl@U?$intrusive_member_hook_traits@$MPEQ_HCI_CONNECTION@@U_LIST_ENTRY@@0CA@@Foundation@Bluetooth@Microsoft@@V?$intrusive_list_ref_t@U?$intrusive_member_hook_traits@$MPEQ_HCI_CONNECTION@@U_LIST_ENTRY@@0CA@@Foundation@Bluetooth@Microsoft@@@234@@Details@Foundation@Bluetooth@Microsoft@@QEBA_NAEBU_HCI_CONNECTION@@@Z
0x14003b8e6  test    al, al
0x14003b8e8  jz      short loc_14003B913
0x14003b8ea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003b8f1  mov     eax, [rcx+2Ch]
0x14003b8f4  test    r12b, al
0x14003b8f7  jz      short loc_14003B901
0x14003b8f9  mov     dl, bl
0x14003b8fb  cmp     [rcx+29h], r12b
0x14003b8ff  jnb     short loc_14003B904
0x14003b901  mov     dl, r15b
0x14003b904  lea     rsi, aDestroyedConne; __annotation("Debug", "TelemetryAssert", "false", "Destroyed connection still in pending list.")
0x14003b90b  mov     r11d, 3Dh ; '='
0x14003b911  jmp     short loc_14003B93A
0x14003b913  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003b91a  mov     eax, [rcx+2Ch]
0x14003b91d  test    r12b, al
0x14003b920  jz      short loc_14003B92A
0x14003b922  mov     dl, bl
0x14003b924  cmp     [rcx+29h], r12b
0x14003b928  jnb     short loc_14003B92D
0x14003b92a  mov     dl, r15b
0x14003b92d  lea     rsi, aDestroyedConne_1; __annotation("Debug", "TelemetryAssert", "false", "Destroyed connection still in some list.")
0x14003b934  mov     r11d, 3Eh ; '>'
0x14003b93a  mov     rcx, [rcx+18h]
0x14003b93e  lea     r14, WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids
0x14003b945  mov     [rsp+78h+var_38], rdi
0x14003b94a  mov     r10d, r12d
0x14003b94d  mov     [rsp+78h+var_40], r14
0x14003b952  mov     al, r12b
0x14003b955  mov     [rsp+78h+var_48], r11w
0x14003b95b  mov     r9d, 838h
0x14003b961  mov     [rsp+78h+var_50], r10d
0x14003b966  mov     r8b, bl
0x14003b969  mov     r15, rdi
0x14003b96c  mov     [rsp+78h+var_58], al
0x14003b970  mov     r12, r13
0x14003b973  mov     r9, [r13+r9+0]
0x14003b978  call    WPP_RECORDER_AND_TRACE_SF_q
0x14003b97d  mov     rcx, rsi
0x14003b980  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003b985  lea     rdx, [rdi+20h]
0x14003b989  mov     r8, [rdx]
0x14003b98c  cmp     [r8+8], rdx
0x14003b990  jnz     loc_14003BB28
0x14003b996  mov     rax, [rdx+8]
0x14003b99a  cmp     [rax], rdx
0x14003b99d  jnz     loc_14003BB28
0x14003b9a3  mov     r14, [rbp+arg_0]
0x14003b9a7  xor     r15d, r15d
0x14003b9aa  mov     [rax], r8
0x14003b9ad  mov     [r8+8], rax
0x14003b9b1  lea     r12d, [r15+2]
0x14003b9b5  mov     dl, [rbp+NewIrql]; NewIrql
0x14003b9b8  mov     rcx, [rbp+SpinLock]; SpinLock
0x14003b9bc  call    cs:__imp_KeReleaseSpinLock
0x14003b9c3  nop     dword ptr [rax+rax+00h]
0x14003b9c8  lea     rax, [rbp+var_20]
0x14003b9cc  mov     [rbp+var_20.Blink], rax
0x14003b9d0  lea     r8, [rdi+158h]
0x14003b9d7  lea     rax, [rbp+var_20]
0x14003b9db  mov     [rbp+var_20.Flink], rax
0x14003b9df  mov     rax, [r8]
0x14003b9e2  cmp     rax, r8
0x14003b9e5  jz      short loc_14003BA38
0x14003b9e7  lea     rcx, [rdi+158h]
0x14003b9ee  cmp     [rax+8], rcx
0x14003b9f2  jnz     loc_14003BB28
0x14003b9f8  mov     rdx, [rax]
0x14003b9fb  cmp     [rdx+8], rax
0x14003b9ff  jnz     loc_14003BB28
0x14003ba05  mov     [rcx], rdx
0x14003ba08  mov     [rdx+8], rcx
0x14003ba0c  lea     rdx, [rbp+var_20]
0x14003ba10  mov     dword ptr [rax+38h], 0C000009Dh
0x14003ba17  mov     rcx, [rbp+var_20.Blink]
0x14003ba1b  cmp     [rcx], rdx
0x14003ba1e  jnz     loc_14003BB28
0x14003ba24  mov     [rax+8], rcx
0x14003ba28  lea     rdx, [rbp+var_20]
0x14003ba2c  mov     [rax], rdx
0x14003ba2f  mov     [rcx], rax
0x14003ba32  mov     [rbp+var_20.Blink], rax
0x14003ba36  jmp     short loc_14003B9DF
0x14003ba38  lea     rcx, [rbp+var_20]; struct _LIST_ENTRY *
0x14003ba3c  call    ?HCI_CxnDrainUpdateList@@YAXPEAU_LIST_ENTRY@@@Z; HCI_CxnDrainUpdateList(_LIST_ENTRY *)
0x14003ba41  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003ba48  mov     eax, [rcx+2Ch]
0x14003ba4b  test    r12b, al
0x14003ba4e  jz      short loc_14003BA56
0x14003ba50  cmp     byte ptr [rcx+29h], 5
0x14003ba54  jnb     short loc_14003BA59
0x14003ba56  mov     bl, r15b
0x14003ba59  movzx   eax, word ptr [rcx+48h]
0x14003ba5d  test    ax, ax
0x14003ba60  setnz   r8b
0x14003ba64  test    bl, bl
0x14003ba66  jnz     short loc_14003BA6D
0x14003ba68  test    ax, ax
0x14003ba6b  jz      short loc_14003BAA1
0x14003ba6d  mov     r9, [r13+838h]
0x14003ba74  lea     rdx, WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids
0x14003ba7b  mov     rcx, [rcx+18h]
0x14003ba7f  mov     [rsp+78h+var_38], r14
0x14003ba84  mov     [rsp+78h+var_40], rdx
0x14003ba89  mov     dl, bl
0x14003ba8b  mov     [rsp+78h+var_48], 3Fh ; '?'
0x14003ba92  mov     [rsp+78h+var_50], r12d
0x14003ba97  mov     [rsp+78h+var_58], 5
0x14003ba9c  call    WPP_RECORDER_AND_TRACE_SF_q
0x14003baa1  mov     rcx, [rdi+30h]
0x14003baa5  lea     r9, aOnecoreDrivers_26; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14003baac  mov     r8d, 6CBh
0x14003bab2  mov     rdx, rdi
0x14003bab5  call    RefObj_ReleaseEx
0x14003baba  mov     rcx, [rdi+38h]
0x14003babe  lea     r9, aOnecoreDrivers_26; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14003bac5  mov     r8d, 6D5h
0x14003bacb  mov     rdx, rdi
0x14003bace  mov     rbx, [rcx+4A8h]
0x14003bad5  add     rcx, 8
0x14003bad9  call    RefObj_ReleaseEx
0x14003bade  xor     edx, edx; Tag
0x14003bae0  mov     [rdi+30h], r15
0x14003bae4  mov     rcx, rdi; P
0x14003bae7  mov     [rdi+38h], r15
0x14003baeb  mov     dword ptr [rdi], 0DEADBEEFh
0x14003baf1  call    cs:__imp_ExFreePoolWithTag
0x14003baf8  nop     dword ptr [rax+rax+00h]
0x14003bafd  mov     r8d, 20h ; ' '; RemlockSize
0x14003bb03  lea     rcx, [rbx+38h]; RemoveLock
0x14003bb07  mov     rdx, rdi; Tag
0x14003bb0a  call    cs:__imp_IoReleaseRemoveLockEx
0x14003bb11  nop     dword ptr [rax+rax+00h]
0x14003bb16  add     rsp, 78h
0x14003bb1a  pop     r15
0x14003bb1c  pop     r14
0x14003bb1e  pop     r13
0x14003bb20  pop     r12
0x14003bb22  pop     rdi
0x14003bb23  pop     rsi
0x14003bb24  pop     rbx
0x14003bb25  pop     rbp
0x14003bb26  retn
0x14003bb28  mov     ecx, 3
0x14003bb2d  int     29h; Win8: RtlFailFast(ecx)
```
