# HCI_CxnEnhancedFlushCallback(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *)

- ea: `0x14002f460`
- end: `0x14002f634`
- name: `?HCI_CxnEnhancedFlushCallback@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z`
- size: `468`
- prototype: `void __fastcall(struct DEVICE_EXTENSION *, void *, struct _HCI_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140005608`
- `0x14002f460`
- `0x1400ba080`
- `0x140161d7c`
- `0x14016241c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f505`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f505`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f574`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f574`

## string_xrefs

- `0x14002f540`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`
- `0x14002f608`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`

## pseudocode

```c
void __fastcall HCI_CxnEnhancedFlushCallback(
        struct DEVICE_EXTENSION *a1,
        KSPIN_LOCK *a2,
        struct _HCI_CALLBACK_DATA *a3)
{
  struct _HCI_CALLBACK_DATA *v3; // r14
  KSPIN_LOCK *v4; // rdi
  char v6; // bl
  __int16 DeviceType; // ax
  int Status; // r12d
  KIRQL v9; // r13
  _LIST_ENTRY *Blink; // rdx
  __int64 v11; // rax
  int v12; // r8d
  __int16 v13; // ax
  __int64 *v14; // rdx
  struct _LIST_ENTRY v15; // [rsp+40h] [rbp-18h] BYREF

  v3 = a3;
  v15 = 0;
  v4 = a2;
  v6 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
  {
    LOBYTE(a3) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      a1->Hci->IfrLog,
      5,
      2,
      71,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
  }
  Status = v3->Status;
  v15.Blink = &v15;
  v15.Flink = &v15;
  v9 = KeAcquireSpinLockRaiseToDpc(v4 + 10);
  while ( 1 )
  {
    v11 = IrpList_DequeueLocked(v4 + 61);
    if ( !v11 )
      break;
    Blink = v15.Blink;
    if ( v15.Blink->Flink != &v15 )
      __fastfail(3u);
    *(_QWORD *)(v11 + 176) = v15.Blink;
    *(_QWORD *)(v11 + 168) = &v15;
    Blink->Flink = (_LIST_ENTRY *)(v11 + 168);
    v15.Blink = (_LIST_ENTRY *)(v11 + 168);
    RefObj_ReleaseEx(v4 + 1, v11, 2311, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
  }
  KeReleaseSpinLock(v4 + 10, v9);
  if ( v15.Flink != &v15 )
    HCI_CompleteBrbIrps(a1, &v15, Status);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v6 = 0;
  v13 = WPP_GLOBAL_Control->DeviceType;
  if ( v6 || v13 )
  {
    v14 = WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids;
    LOBYTE(v14) = v6;
    LOBYTE(v12) = v13 != 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v14,
      v12,
      a1->Hci->IfrLog,
      5,
      2,
      72,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
  }
  RefObj_ReleaseEx(
    v4 + 1,
    HCI_CxnEnhancedFlushCallback,
    2333,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
}

```

## disassembly

```asm
0x14002f460  push    rbp
0x14002f462  push    rbx
0x14002f463  push    rsi
0x14002f464  push    rdi
0x14002f465  push    r12
0x14002f467  push    r13
0x14002f469  push    r14
0x14002f46b  push    r15
0x14002f46d  mov     rbp, rsp
0x14002f470  sub     rsp, 58h
0x14002f474  xorps   xmm0, xmm0
0x14002f477  mov     r14, r8
0x14002f47a  movups  xmmword ptr [rbp+var_18.Flink], xmm0
0x14002f47e  mov     rdi, rdx
0x14002f481  mov     rsi, rcx
0x14002f484  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f48b  xor     r9d, r9d
0x14002f48e  mov     bl, 1
0x14002f490  mov     eax, [rcx+2Ch]
0x14002f493  test    al, 2
0x14002f495  jz      short loc_14002F49F
0x14002f497  cmp     byte ptr [rcx+29h], 5
0x14002f49b  mov     dl, bl
0x14002f49d  jnb     short loc_14002F4A2
0x14002f49f  mov     dl, r9b
0x14002f4a2  movzx   eax, word ptr [rcx+48h]
0x14002f4a6  lea     r10, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14002f4ad  test    ax, ax
0x14002f4b0  setnz   r8b
0x14002f4b4  test    dl, dl
0x14002f4b6  jnz     short loc_14002F4BD
0x14002f4b8  test    ax, ax
0x14002f4bb  jz      short loc_14002F4ED
0x14002f4bd  mov     r9, [rsi+170h]
0x14002f4c4  mov     rcx, [rcx+18h]
0x14002f4c8  mov     [rsp+58h+var_20], r10
0x14002f4cd  mov     [rsp+58h+var_28], 47h ; 'G'
0x14002f4d4  mov     r9, [r9+10B0h]
0x14002f4db  mov     [rsp+58h+var_30], 2
0x14002f4e3  mov     [rsp+58h+var_38], 5
0x14002f4e8  call    WPP_RECORDER_AND_TRACE_SF_
0x14002f4ed  mov     r12d, [r14+18h]
0x14002f4f1  lea     rax, [rbp+var_18]
0x14002f4f5  mov     [rbp+var_18.Blink], rax
0x14002f4f9  lea     rcx, [rdi+50h]; SpinLock
0x14002f4fd  lea     rax, [rbp+var_18]
0x14002f501  mov     [rbp+var_18.Flink], rax
0x14002f505  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f50c  nop     dword ptr [rax+rax+00h]
0x14002f511  mov     r13b, al
0x14002f514  lea     r15, [rdi+1E8h]
0x14002f51b  jmp     short loc_14002F560
0x14002f51d  mov     rdx, [rbp+var_18.Blink]
0x14002f521  lea     rcx, [rbp+var_18]
0x14002f525  cmp     [rdx], rcx
0x14002f528  jnz     loc_14002F62D
0x14002f52e  lea     rcx, [rax+0A8h]
0x14002f535  mov     [rcx+8], rdx
0x14002f539  lea     r8, [rbp+var_18]
0x14002f53d  mov     [rcx], r8
0x14002f540  lea     r9, aOnecoreDrivers_32; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14002f547  mov     [rdx], rcx
0x14002f54a  mov     r8d, 907h
0x14002f550  mov     [rbp+var_18.Blink], rcx
0x14002f554  mov     rdx, rax
0x14002f557  lea     rcx, [rdi+8]
0x14002f55b  call    RefObj_ReleaseEx
0x14002f560  mov     rcx, r15
0x14002f563  call    IrpList_DequeueLocked
0x14002f568  test    rax, rax
0x14002f56b  jnz     short loc_14002F51D
0x14002f56d  mov     dl, r13b; NewIrql
0x14002f570  lea     rcx, [rdi+50h]; SpinLock
0x14002f574  call    cs:__imp_KeReleaseSpinLock
0x14002f57b  nop     dword ptr [rax+rax+00h]
0x14002f580  lea     rax, [rbp+var_18]
0x14002f584  cmp     [rbp+var_18.Flink], rax
0x14002f588  jz      short loc_14002F599
0x14002f58a  mov     r8d, r12d; int
0x14002f58d  lea     rdx, [rbp+var_18]; struct _LIST_ENTRY *
0x14002f591  mov     rcx, rsi; struct DEVICE_EXTENSION *
0x14002f594  call    ?HCI_CompleteBrbIrps@@YAXPEAUDEVICE_EXTENSION@@PEAU_LIST_ENTRY@@J@Z; HCI_CompleteBrbIrps(DEVICE_EXTENSION *,_LIST_ENTRY *,long)
0x14002f599  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f5a0  mov     eax, [rcx+2Ch]
0x14002f5a3  test    al, 2
0x14002f5a5  jz      short loc_14002F5AD
0x14002f5a7  cmp     byte ptr [rcx+29h], 5
0x14002f5ab  jnb     short loc_14002F5B1
0x14002f5ad  xor     edx, edx
0x14002f5af  mov     bl, dl
0x14002f5b1  movzx   eax, word ptr [rcx+48h]
0x14002f5b5  test    ax, ax
0x14002f5b8  setnz   r8b
0x14002f5bc  test    bl, bl
0x14002f5be  jnz     short loc_14002F5C5
0x14002f5c0  test    ax, ax
0x14002f5c3  jz      short loc_14002F5FE
0x14002f5c5  mov     r9, [rsi+170h]
0x14002f5cc  lea     rdx, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14002f5d3  mov     rcx, [rcx+18h]
0x14002f5d7  mov     [rsp+58h+var_20], rdx
0x14002f5dc  mov     dl, bl
0x14002f5de  mov     [rsp+58h+var_28], 48h ; 'H'
0x14002f5e5  mov     r9, [r9+10B0h]
0x14002f5ec  mov     [rsp+58h+var_30], 2
0x14002f5f4  mov     [rsp+58h+var_38], 5
0x14002f5f9  call    WPP_RECORDER_AND_TRACE_SF_
0x14002f5fe  lea     rcx, [rdi+8]
0x14002f602  mov     r8d, 91Dh
0x14002f608  lea     r9, aOnecoreDrivers_32; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14002f60f  lea     rdx, ?HCI_CxnEnhancedFlushCallback@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z; HCI_CxnEnhancedFlushCallback(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *)
0x14002f616  call    RefObj_ReleaseEx
0x14002f61b  add     rsp, 58h
0x14002f61f  pop     r15
0x14002f621  pop     r14
0x14002f623  pop     r13
0x14002f625  pop     r12
0x14002f627  pop     rdi
0x14002f628  pop     rsi
0x14002f629  pop     rbx
0x14002f62a  pop     rbp
0x14002f62b  retn
0x14002f62d  mov     ecx, 3
0x14002f632  int     29h; Win8: RtlFailFast(ecx)
```
