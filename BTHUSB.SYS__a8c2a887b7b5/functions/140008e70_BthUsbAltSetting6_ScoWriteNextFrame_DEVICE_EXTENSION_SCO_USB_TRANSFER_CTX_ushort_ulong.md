# BthUsbAltSetting6_ScoWriteNextFrame(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong)

- ea: `0x140008e70`
- end: `0x140008f38`
- name: `?BthUsbAltSetting6_ScoWriteNextFrame@@YAKPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@GK@Z`
- size: `200`
- prototype: `unsigned int __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140006638`
- `0x140008e70`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140008ece`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008ece`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008e9d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008e9d`

## pseudocode

```c
__int64 __fastcall BthUsbAltSetting6_ScoWriteNextFrame(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_TRANSFER_CTX *a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v6; // rdi
  KSPIN_LOCK *v7; // rsi
  KIRQL v8; // al
  int v9; // ebx
  char v10; // r14
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // ebx

  v6 = 152 * (a3 + 3LL);
  v7 = (KSPIN_LOCK *)((char *)&a1->DeviceExtensionSessionId.Data1 + v6);
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)((char *)&a1->Sco.UsbBusInterface.Size + v6));
  v9 = *(_DWORD *)((char *)&a1->Sco.WriteCtxQueue.FnGetItem + v6 + 4);
  v10 = 1;
  *(_DWORD *)((char *)&a1->Sco.WriteCtxQueue.FnGetItem + v6 + 4) = (v9 & 1) + 7;
  KeReleaseSpinLock(v7 + 30, v8);
  v13 = a4 + v9;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v10 = 0;
  LOBYTE(v11) = v10;
  WPP_RECORDER_AND_TRACE_SF_LL(WPP_GLOBAL_Control->AttachedDevice, v11, v12, WPP_GLOBAL_Control->DeviceExtension);
  return v13;
}

```

## disassembly

```asm
0x140008e70  push    rbx
0x140008e72  push    rbp
0x140008e73  push    rsi
0x140008e74  push    rdi
0x140008e75  push    r14
0x140008e77  push    r15
0x140008e79  sub     rsp, 58h
0x140008e7d  movzx   eax, r8w
0x140008e81  mov     rbp, rcx
0x140008e84  add     rax, 3
0x140008e88  mov     r15d, r9d
0x140008e8b  imul    rdi, rax, 98h
0x140008e92  lea     rsi, [rdi+rcx]
0x140008e96  lea     rcx, [rsi+0F0h]; SpinLock
0x140008e9d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008ea4  nop     dword ptr [rax+rax+00h]
0x140008ea9  mov     ebx, [rdi+rbp+17Ch]
0x140008eb0  lea     rcx, [rsi+0F0h]; SpinLock
0x140008eb7  mov     edx, ebx
0x140008eb9  mov     r14d, 1
0x140008ebf  and     edx, r14d
0x140008ec2  add     edx, 7
0x140008ec5  mov     [rdi+rbp+17Ch], edx
0x140008ecc  mov     dl, al; NewIrql
0x140008ece  call    cs:__imp_KeReleaseSpinLock
0x140008ed5  nop     dword ptr [rax+rax+00h]
0x140008eda  add     ebx, r15d
0x140008edd  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ee4  mov     eax, [rcx+2Ch]
0x140008ee7  test    al, 10h
0x140008ee9  jz      short loc_140008EF1
0x140008eeb  cmp     byte ptr [rcx+29h], 4
0x140008eef  jnb     short loc_140008EF4
0x140008ef1  xor     r14b, r14b
0x140008ef4  mov     r9, [rcx+40h]
0x140008ef8  lea     rax, WPP_5fbab361c58e305795b7101c701f7776_Traceguids
0x140008eff  mov     rcx, [rcx+18h]
0x140008f03  mov     dl, r14b
0x140008f06  mov     [rsp+88h+var_40], ebx
0x140008f0a  mov     [rsp+88h+var_48], r15d
0x140008f0f  mov     [rsp+88h+var_50], rax
0x140008f14  mov     [rsp+88h+var_58], 0Ah
0x140008f1b  mov     [rsp+88h+var_60], 5
0x140008f23  call    WPP_RECORDER_AND_TRACE_SF_LL
0x140008f28  mov     eax, ebx
0x140008f2a  add     rsp, 58h
0x140008f2e  pop     r15
0x140008f30  pop     r14
0x140008f32  pop     rdi
0x140008f33  pop     rsi
0x140008f34  pop     rbp
0x140008f35  pop     rbx
0x140008f36  retn
```
