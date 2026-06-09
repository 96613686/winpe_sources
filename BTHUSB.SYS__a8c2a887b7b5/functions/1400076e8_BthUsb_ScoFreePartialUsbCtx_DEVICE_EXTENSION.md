# BthUsb_ScoFreePartialUsbCtx(_DEVICE_EXTENSION *)

- ea: `0x1400076e8`
- end: `0x1400077bb`
- name: `?BthUsb_ScoFreePartialUsbCtx@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `211`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400077c4`
- `0x140007ea0`
- `0x140007f8c`

## callees

- `0x14000187c`
- `0x1400076e8`
- `0x140007c5c`
- `0x14000d85c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140007727`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007727`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007704`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007704`

## string_xrefs

- `0x14000778e`: `onecore\drivers\wdm\bluetooth\drivers\bthusb\scousbread.cpp`

## pseudocode

```c
void __fastcall BthUsb_ScoFreePartialUsbCtx(struct _DEVICE_EXTENSION *a1)
{
  unsigned __int64 *p_ReadLock; // rbx
  KIRQL v3; // al
  _SCO_USB_TRANSFER_CTX *PartialReadCtx; // rsi
  int v5; // edx
  int v6; // r8d

  p_ReadLock = &a1->Sco.ReadLock;
  v3 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.ReadLock);
  PartialReadCtx = a1->Sco.PartialReadCtx;
  a1->Sco.PartialReadCtx = 0;
  KeReleaseSpinLock(p_ReadLock, v3);
  if ( PartialReadCtx )
  {
    LOBYTE(v5) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      v6,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      10,
      (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids,
      (char)PartialReadCtx);
    RefObj_ReleaseEx(
      &PartialReadCtx->RefObj,
      PartialReadCtx,
      109,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\scousbread.cpp");
    BthUsb_ScoReadData(a1, 1u);
  }
}

```

## disassembly

```asm
0x1400076e8  mov     [rsp+arg_0], rbx
0x1400076ed  mov     [rsp+arg_8], rsi
0x1400076f2  push    rdi
0x1400076f3  sub     rsp, 50h
0x1400076f7  lea     rbx, [rcx+248h]
0x1400076fe  mov     rdi, rcx
0x140007701  mov     rcx, rbx; SpinLock
0x140007704  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000770b  nop     dword ptr [rax+rax+00h]
0x140007710  mov     rsi, [rdi+258h]
0x140007717  mov     rcx, rbx; SpinLock
0x14000771a  mov     dl, al; NewIrql
0x14000771c  mov     qword ptr [rdi+258h], 0
0x140007727  call    cs:__imp_KeReleaseSpinLock
0x14000772e  nop     dword ptr [rax+rax+00h]
0x140007733  test    rsi, rsi
0x140007736  jz      short loc_1400077AA
0x140007738  mov     rcx, cs:WPP_GLOBAL_Control
0x14000773f  mov     eax, [rcx+2Ch]
0x140007742  test    al, 10h
0x140007744  jz      short loc_140007750
0x140007746  cmp     byte ptr [rcx+29h], 4
0x14000774a  jb      short loc_140007750
0x14000774c  mov     dl, 1
0x14000774e  jmp     short loc_140007752
0x140007750  xor     dl, dl
0x140007752  mov     r9, [rcx+40h]
0x140007756  lea     rax, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x14000775d  mov     rcx, [rcx+18h]
0x140007761  mov     [rsp+58h+var_18], rsi
0x140007766  mov     [rsp+58h+var_20], rax
0x14000776b  mov     [rsp+58h+var_28], 0Ah
0x140007772  mov     [rsp+58h+var_30], 5
0x14000777a  mov     [rsp+58h+var_38], 4
0x14000777f  call    WPP_RECORDER_AND_TRACE_SF_q
0x140007784  lea     rcx, [rsi+8]
0x140007788  mov     r8d, 6Dh ; 'm'
0x14000778e  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140007795  mov     rdx, rsi
0x140007798  call    RefObj_ReleaseEx
0x14000779d  mov     edx, 1; unsigned int
0x1400077a2  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400077a5  call    ?BthUsb_ScoReadData@@YAJPEAU_DEVICE_EXTENSION@@K@Z; BthUsb_ScoReadData(_DEVICE_EXTENSION *,ulong)
0x1400077aa  mov     rbx, [rsp+58h+arg_0]
0x1400077af  mov     rsi, [rsp+58h+arg_8]
0x1400077b4  add     rsp, 50h
0x1400077b8  pop     rdi
0x1400077b9  retn
```
