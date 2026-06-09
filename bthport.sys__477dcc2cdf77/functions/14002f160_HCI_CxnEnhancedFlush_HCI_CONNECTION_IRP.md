# HCI_CxnEnhancedFlush(_HCI_CONNECTION *,_IRP *)

- ea: `0x14002f160`
- end: `0x14002f44c`
- name: `?HCI_CxnEnhancedFlush@@YAJPEAU_HCI_CONNECTION@@PEAU_IRP@@@Z`
- size: `748`
- prototype: `__int64 __fastcall(struct _HCI_CONNECTION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002f770`

## callees

- `0x140005c04`
- `0x14000764c`
- `0x14002702c`
- `0x14002f160`
- `0x1400350f0`
- `0x140161a44`
- `0x140161d7c`
- `0x140162008`
- `0x140162670`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f201`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f201`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f30b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f30b`

## string_xrefs

- `0x14002f228`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`
- `0x14002f2d6`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`
- `0x14002f36e`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`

## pseudocode

```c
__int64 __fastcall HCI_CxnEnhancedFlush(struct _HCI_CONNECTION *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rbp
  char v3; // si
  char v5; // bl
  __int16 DeviceType; // ax
  _LIST_ENTRY *Flink; // r12
  __int64 v8; // r9
  __int64 v9; // r8
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // r14d
  __int16 v13; // ax
  int v14; // edx
  int v15; // r8d
  _IO_SECURITY_CONTEXT *SecurityContext; // rdx
  unsigned __int16 ConnectionHandle; // ax
  __int16 v18; // ax
  __int64 v20; // [rsp+48h] [rbp-60h]
  GUID ActivityId; // [rsp+60h] [rbp-48h] BYREF
  KIRQL NewIrql; // [rsp+B0h] [rbp+8h]
  _BYTE v23[6]; // [rsp+C0h] [rbp+18h] BYREF

  v2 = a2;
  v3 = 0;
  memset(v23, 0, sizeof(v23));
  v5 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_qi(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      DeviceType != 0,
      a1->Dib->IfrLog,
      5,
      2,
      73,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
      (char)a1,
      v2);
  NewIrql = KeAcquireSpinLockRaiseToDpc(&a1->StateLock);
  Flink = a1->EnhancedFlushIrpList.LockedList.ListHead.Flink;
  RefObj_AddRefEx(&a1->RefObj, v2, 2382, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
  LOBYTE(v8) = 1;
  v12 = IrpList_EnqueueLocked(&a1->EnhancedFlushIrpList, v2, v9, v8);
  if ( v12 == 259 )
  {
    if ( Flink == (_LIST_ENTRY *)&a1->EnhancedFlushIrpList )
      v3 = 1;
  }
  else
  {
    LOBYTE(v10) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    v13 = WPP_GLOBAL_Control->DeviceType;
    if ( (_BYTE)v10 || v13 )
    {
      LODWORD(v20) = v12;
      LOBYTE(v11) = v13 != 0;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        v11,
        a1->Dib->IfrLog,
        5,
        2,
        74,
        (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
        (char)v2,
        v20);
    }
    RefObj_ReleaseEx(&a1->RefObj, v2, 2389, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
  }
  KeReleaseSpinLock(&a1->StateLock, NewIrql);
  if ( v3 )
  {
    SecurityContext = v2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
    *(_WORD *)v23 = 3167;
    ConnectionHandle = a1->Info.ConnectionHandle;
    v23[5] = 0;
    *(_WORD *)&v23[3] = ConnectionHandle;
    v23[2] = 3;
    v23[5] = SecurityContext[5].SecurityQos;
    ActivityId = *(GUID *)BthGetActivityID(&ActivityId);
    RefObj_AddRefEx(
      &a1->RefObj,
      HCI_CxnEnhancedFlushCallback,
      2420,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
    HCI_SendCommandEx(
      a1->Hci,
      (struct _HCI_COMMAND_HEADER *)v23,
      &ActivityId,
      (void (*)(struct DEVICE_EXTENSION *, void *, struct _HCI_CALLBACK_DATA *))HCI_CxnEnhancedFlushCallback,
      a1,
      0,
      0);
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v5 = 0;
  v18 = WPP_GLOBAL_Control->DeviceType;
  if ( v5 || v18 )
  {
    LOBYTE(v14) = v5;
    LOBYTE(v15) = v18 != 0;
    WPP_RECORDER_AND_TRACE_SF_qqDd(
      WPP_GLOBAL_Control->AttachedDevice,
      v14,
      v15,
      a1->Dib->IfrLog,
      5,
      2,
      75,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
      (char)a1,
      (char)v2,
      v3,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x14002f160  mov     r11, rsp
0x14002f163  mov     [r11+10h], rbx
0x14002f167  push    rbp
0x14002f168  push    rsi
0x14002f169  push    rdi
0x14002f16a  push    r12
0x14002f16c  push    r13
0x14002f16e  push    r14
0x14002f170  push    r15
0x14002f172  sub     rsp, 70h
0x14002f176  xor     r9d, r9d
0x14002f179  mov     rbp, rdx
0x14002f17c  xor     eax, eax
0x14002f17e  movzx   esi, r9b
0x14002f182  mov     [r11+18h], eax
0x14002f186  mov     rdi, rcx
0x14002f189  mov     [r11+1Ch], ax
0x14002f18e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f195  lea     ebx, [r9+1]
0x14002f199  mov     eax, [rcx+2Ch]
0x14002f19c  test    al, 2
0x14002f19e  jz      short loc_14002F1A8
0x14002f1a0  cmp     byte ptr [rcx+29h], 5
0x14002f1a4  mov     dl, bl
0x14002f1a6  jnb     short loc_14002F1AB
0x14002f1a8  mov     dl, r9b
0x14002f1ab  movzx   eax, word ptr [rcx+48h]
0x14002f1af  lea     r10, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14002f1b6  test    ax, ax
0x14002f1b9  setnz   r8b
0x14002f1bd  test    dl, dl
0x14002f1bf  jnz     short loc_14002F1C6
0x14002f1c1  test    ax, ax
0x14002f1c4  jz      short loc_14002F1FD
0x14002f1c6  mov     r9, [rdi+30h]
0x14002f1ca  mov     rcx, [rcx+18h]
0x14002f1ce  mov     [rsp+0A8h+var_60], rbp
0x14002f1d3  mov     [rsp+0A8h+var_68], rdi
0x14002f1d8  mov     r9, [r9+838h]
0x14002f1df  mov     [rsp+0A8h+var_70], r10
0x14002f1e4  mov     word ptr [rsp+0A8h+var_78], 49h ; 'I'
0x14002f1eb  mov     [rsp+0A8h+var_80], 2
0x14002f1f3  mov     byte ptr [rsp+0A8h+var_88], 5
0x14002f1f8  call    WPP_RECORDER_AND_TRACE_SF_qi
0x14002f1fd  lea     rcx, [rdi+50h]; SpinLock
0x14002f201  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f208  nop     dword ptr [rax+rax+00h]
0x14002f20d  lea     r13, [rdi+8]
0x14002f211  mov     r8d, 94Eh
0x14002f217  lea     r15, [rdi+1E8h]
0x14002f21e  mov     [rsp+0A8h+NewIrql], al
0x14002f225  mov     r12, [r15]
0x14002f228  lea     r9, aOnecoreDrivers_32; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14002f22f  mov     rcx, r13
0x14002f232  mov     rdx, rbp
0x14002f235  call    RefObj_AddRefEx
0x14002f23a  mov     r9b, bl
0x14002f23d  mov     rdx, rbp
0x14002f240  mov     rcx, r15
0x14002f243  call    IrpList_EnqueueLocked
0x14002f248  mov     r14d, eax
0x14002f24b  cmp     eax, 103h
0x14002f250  jz      loc_14002F2F0
0x14002f256  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f25d  mov     ecx, [r10+2Ch]
0x14002f261  test    cl, 2
0x14002f264  jz      short loc_14002F274
0x14002f266  cmp     byte ptr [r10+29h], 5
0x14002f26b  jb      short loc_14002F274
0x14002f26d  mov     dl, bl
0x14002f26f  xor     r15d, r15d
0x14002f272  jmp     short loc_14002F27A
0x14002f274  xor     r15d, r15d
0x14002f277  mov     dl, r15b
0x14002f27a  movzx   eax, word ptr [r10+48h]
0x14002f27f  test    ax, ax
0x14002f282  setnz   r8b
0x14002f286  test    dl, dl
0x14002f288  jnz     short loc_14002F28F
0x14002f28a  test    ax, ax
0x14002f28d  jz      short loc_14002F2CF
0x14002f28f  mov     r9, [rdi+30h]
0x14002f293  lea     r12, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14002f29a  mov     rcx, [r10+18h]
0x14002f29e  mov     dword ptr [rsp+0A8h+var_60], r14d
0x14002f2a3  mov     [rsp+0A8h+var_68], rbp
0x14002f2a8  mov     r9, [r9+838h]
0x14002f2af  mov     [rsp+0A8h+var_70], r12
0x14002f2b4  mov     word ptr [rsp+0A8h+var_78], 4Ah ; 'J'
0x14002f2bb  mov     [rsp+0A8h+var_80], 2
0x14002f2c3  mov     byte ptr [rsp+0A8h+var_88], 5
0x14002f2c8  call    WPP_RECORDER_AND_TRACE_SF_qL
0x14002f2cd  jmp     short loc_14002F2D6
0x14002f2cf  lea     r12, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14002f2d6  lea     r9, aOnecoreDrivers_32; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14002f2dd  mov     r8d, 955h
0x14002f2e3  mov     rdx, rbp
0x14002f2e6  mov     rcx, r13
0x14002f2e9  call    RefObj_ReleaseEx
0x14002f2ee  jmp     short loc_14002F300
0x14002f2f0  cmp     r12, r15
0x14002f2f3  lea     r12, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14002f2fa  cmovz   esi, ebx
0x14002f2fd  xor     r15d, r15d
0x14002f300  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x14002f307  lea     rcx, [rdi+50h]; SpinLock
0x14002f30b  call    cs:__imp_KeReleaseSpinLock
0x14002f312  nop     dword ptr [rax+rax+00h]
0x14002f317  test    sil, sil
0x14002f31a  jz      loc_14002F3BF
0x14002f320  mov     rax, [rbp+0B8h]
0x14002f327  lea     rcx, [rsp+0A8h+ActivityId]; ActivityId
0x14002f32c  mov     rdx, [rax+8]
0x14002f330  mov     eax, 0C5Fh
0x14002f335  mov     [rsp+0A8h+arg_10.Op_Code], ax
0x14002f33d  movzx   eax, word ptr [rdi+80h]
0x14002f344  mov     [rsp+0A8h+arg_15], r15b
0x14002f34c  mov     [rsp+0A8h+arg_13], ax
0x14002f354  mov     [rsp+0A8h+arg_10.Parameter_Total_Length], 3
0x14002f35c  mov     al, [rdx+78h]
0x14002f35f  mov     rdx, rbp
0x14002f362  mov     [rsp+0A8h+arg_15], al
0x14002f369  call    BthGetActivityID
0x14002f36e  lea     r9, aOnecoreDrivers_32; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14002f375  mov     r8d, 974h
0x14002f37b  lea     rdx, ?HCI_CxnEnhancedFlushCallback@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z; HCI_CxnEnhancedFlushCallback(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *)
0x14002f382  mov     rcx, r13
0x14002f385  movups  xmm0, xmmword ptr [rax]
0x14002f388  movdqu  xmmword ptr [rsp+0A8h+ActivityId.Data1], xmm0
0x14002f38e  call    RefObj_AddRefEx
0x14002f393  mov     rcx, [rdi+38h]; struct HCI_INTERFACE *
0x14002f397  lea     r9, ?HCI_CxnEnhancedFlushCallback@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z; void (*)(struct DEVICE_EXTENSION *, void *, struct _HCI_CALLBACK_DATA *)
0x14002f39e  mov     [rsp+0A8h+var_78], r15; void *
0x14002f3a3  lea     r8, [rsp+0A8h+ActivityId]; struct _GUID *
0x14002f3a8  mov     [rsp+0A8h+var_80], r15d; unsigned int
0x14002f3ad  lea     rdx, [rsp+0A8h+arg_10]; struct _HCI_COMMAND_HEADER *
0x14002f3b5  mov     [rsp+0A8h+var_88], rdi; void *
0x14002f3ba  call    ?HCI_SendCommandEx@@YAJPEAUHCI_INTERFACE@@PEAU_HCI_COMMAND_HEADER@@PEAU_GUID@@P6AXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z4K4@Z; HCI_SendCommandEx(HCI_INTERFACE *,_HCI_COMMAND_HEADER *,_GUID *,void (*)(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *),void *,ulong,void *)
0x14002f3bf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f3c6  mov     eax, [rcx+2Ch]
0x14002f3c9  test    al, 2
0x14002f3cb  jz      short loc_14002F3D3
0x14002f3cd  cmp     byte ptr [rcx+29h], 5
0x14002f3d1  jnb     short loc_14002F3D6
0x14002f3d3  mov     bl, r15b
0x14002f3d6  movzx   eax, word ptr [rcx+48h]
0x14002f3da  test    ax, ax
0x14002f3dd  setnz   r8b
0x14002f3e1  test    bl, bl
0x14002f3e3  jnz     short loc_14002F3EA
0x14002f3e5  test    ax, ax
0x14002f3e8  jz      short loc_14002F430
0x14002f3ea  mov     r9, [rdi+30h]
0x14002f3ee  mov     dl, bl
0x14002f3f0  mov     rcx, [rcx+18h]
0x14002f3f4  mov     [rsp+0A8h+var_50], r14d
0x14002f3f9  movzx   eax, sil
0x14002f3fd  mov     r9, [r9+838h]
0x14002f404  mov     [rsp+0A8h+var_58], eax
0x14002f408  mov     [rsp+0A8h+var_60], rbp
0x14002f40d  mov     [rsp+0A8h+var_68], rdi
0x14002f412  mov     [rsp+0A8h+var_70], r12
0x14002f417  mov     word ptr [rsp+0A8h+var_78], 4Bh ; 'K'
0x14002f41e  mov     [rsp+0A8h+var_80], 2
0x14002f426  mov     byte ptr [rsp+0A8h+var_88], 5
0x14002f42b  call    WPP_RECORDER_AND_TRACE_SF_qqDd
0x14002f430  mov     rbx, [rsp+0A8h+arg_8]
0x14002f438  mov     eax, r14d
0x14002f43b  add     rsp, 70h
0x14002f43f  pop     r15
0x14002f441  pop     r14
0x14002f443  pop     r13
0x14002f445  pop     r12
0x14002f447  pop     rdi
0x14002f448  pop     rsi
0x14002f449  pop     rbp
0x14002f44a  retn
```
