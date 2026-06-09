# HCI_DibFinalDestroy(DEVICE_INFO_BLOCK *)

- ea: `0x140055a50`
- end: `0x140055b99`
- name: `?HCI_DibFinalDestroy@@YAXPEAUDEVICE_INFO_BLOCK@@@Z`
- size: `329`
- prototype: `void __fastcall(struct DEVICE_INFO_BLOCK *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140055748`
- `0x14005aa60`

## callees

- `0x14000764c`
- `0x140050e1c`
- `0x1400512e8`
- `0x140055a50`
- `0x140130dac`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140055af5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055af5`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140055b3a`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140055b3a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140055b1b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140055b1b`

## pseudocode

```c
void __fastcall HCI_DibFinalDestroy(struct DEVICE_INFO_BLOCK *a1, __int64 a2, __int64 a3)
{
  PDEVICE_OBJECT v4; // rcx
  char v5; // dl
  __int16 DeviceType; // ax
  RECORDER_LOG__ *IfrLog; // rdi
  DeviceDeferredPairing *MyRealVal; // rdx
  struct DEVICE_INFO_BLOCK *v9; // [rsp+60h] [rbp+8h] BYREF

  v9 = a1;
  v4 = WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v5 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v5 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  LOBYTE(a3) = DeviceType != 0;
  if ( v5 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_qi(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      a3,
      a1->Hci->IfrLog,
      5,
      2,
      10,
      (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
      (char)a1,
      a1->DeviceInfo.address);
  if ( a1->ProtocolRbTree )
  {
    HCI_DibFreeProtocolTree(a1);
    ExFreePoolWithTag(a1->ProtocolRbTree, 0);
    a1->ProtocolRbTree = 0;
  }
  IfrLog = a1->IfrLog;
  if ( IfrLog && (RECORDER_LOG__ *)imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control) != IfrLog )
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
  MyRealVal = a1->DeferredPairing._MyDat._MyRealVal;
  a1->DeferredPairing._MyDat._MyRealVal = 0;
  if ( MyRealVal )
    utl::default_delete<DeviceDeferredPairing>::operator()(v4, MyRealVal, a3);
  RefObj_ReleaseEx(&a1->Hci->RefObj, a1, 169, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcidib.cpp");
  utl::unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>::~unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>(&v9);
}

```

## disassembly

```asm
0x140055a50  mov     [rsp+arg_8], rbx
0x140055a55  mov     [rsp+arg_10], rsi
0x140055a5a  push    rdi
0x140055a5b  sub     rsp, 50h
0x140055a5f  mov     rbx, rcx
0x140055a62  mov     [rsp+58h+arg_0], rcx
0x140055a67  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140055a6e  xor     esi, esi
0x140055a70  mov     eax, [rcx+2Ch]
0x140055a73  test    al, 2
0x140055a75  jz      short loc_140055A7F
0x140055a77  cmp     byte ptr [rcx+29h], 5
0x140055a7b  mov     dl, 1
0x140055a7d  jnb     short loc_140055A82
0x140055a7f  mov     dl, sil
0x140055a82  movzx   eax, word ptr [rcx+48h]
0x140055a86  test    ax, ax
0x140055a89  setnz   r8b
0x140055a8d  test    dl, dl
0x140055a8f  jnz     short loc_140055A96
0x140055a91  test    ax, ax
0x140055a94  jz      short loc_140055ADB
0x140055a96  mov     rax, [rbx+20h]
0x140055a9a  mov     r9, [rbx+378h]
0x140055aa1  mov     rcx, [rcx+18h]
0x140055aa5  mov     [rsp+58h+var_10], rax
0x140055aaa  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x140055ab1  mov     [rsp+58h+var_18], rbx
0x140055ab6  mov     r9, [r9+10B0h]
0x140055abd  mov     [rsp+58h+var_20], rax
0x140055ac2  mov     [rsp+58h+var_28], 0Ah
0x140055ac9  mov     [rsp+58h+var_30], 2
0x140055ad1  mov     [rsp+58h+var_38], 5
0x140055ad6  call    WPP_RECORDER_AND_TRACE_SF_qi
0x140055adb  cmp     [rbx+3B8h], rsi
0x140055ae2  jz      short loc_140055B08
0x140055ae4  mov     rcx, rbx; struct DEVICE_INFO_BLOCK *
0x140055ae7  call    ?HCI_DibFreeProtocolTree@@YAXPEAUDEVICE_INFO_BLOCK@@@Z; HCI_DibFreeProtocolTree(DEVICE_INFO_BLOCK *)
0x140055aec  mov     rcx, [rbx+3B8h]; P
0x140055af3  xor     edx, edx; Tag
0x140055af5  call    cs:__imp_ExFreePoolWithTag
0x140055afc  nop     dword ptr [rax+rax+00h]
0x140055b01  mov     [rbx+3B8h], rsi
0x140055b08  mov     rdi, [rbx+838h]
0x140055b0f  test    rdi, rdi
0x140055b12  jz      short loc_140055B46
0x140055b14  mov     rcx, cs:WPP_GLOBAL_Control
0x140055b1b  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140055b22  nop     dword ptr [rax+rax+00h]
0x140055b27  cmp     rax, rdi
0x140055b2a  jz      short loc_140055B46
0x140055b2c  mov     rdx, [rbx+838h]
0x140055b33  mov     rcx, cs:WPP_GLOBAL_Control
0x140055b3a  call    cs:__imp_imp_WppRecorderLogDelete
0x140055b41  nop     dword ptr [rax+rax+00h]
0x140055b46  mov     rdx, [rbx+918h]
0x140055b4d  mov     [rbx+918h], rsi
0x140055b54  test    rdx, rdx
0x140055b57  jz      short loc_140055B5E
0x140055b59  call    ??R?$default_delete@VDeviceDeferredPairing@@@utl@@QEBAXPEAVDeviceDeferredPairing@@@Z; utl::default_delete<DeviceDeferredPairing>::operator()(DeviceDeferredPairing *)
0x140055b5e  mov     rcx, [rbx+378h]
0x140055b65  lea     r9, aOnecoreDrivers_11; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140055b6c  add     rcx, 8
0x140055b70  mov     r8d, 0A9h
0x140055b76  mov     rdx, rbx
0x140055b79  call    RefObj_ReleaseEx
0x140055b7e  lea     rcx, [rsp+58h+arg_0]
0x140055b83  call    ??1?$unique_ptr@UDEVICE_INFO_BLOCK@@U?$default_delete@UDEVICE_INFO_BLOCK@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>::~unique_ptr<DEVICE_INFO_BLOCK,utl::default_delete<DEVICE_INFO_BLOCK>>(void)
0x140055b88  mov     rbx, [rsp+58h+arg_8]
0x140055b8d  mov     rsi, [rsp+58h+arg_10]
0x140055b92  add     rsp, 50h
0x140055b96  pop     rdi
0x140055b97  retn
```
