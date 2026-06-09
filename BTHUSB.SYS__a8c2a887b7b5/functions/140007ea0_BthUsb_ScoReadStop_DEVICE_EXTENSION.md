# BthUsb_ScoReadStop(_DEVICE_EXTENSION *)

- ea: `0x140007ea0`
- end: `0x140007f85`
- name: `?BthUsb_ScoReadStop@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `229`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400081b0`

## callees

- `0x14000175c`
- `0x1400076e8`
- `0x140007ea0`
- `0x14000db7c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140007f1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f1a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007f02`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007f02`

## pseudocode

```c
void __fastcall BthUsb_ScoReadStop(struct _DEVICE_EXTENSION *a1, __int64 a2, int a3)
{
  char v4; // di
  bool v5; // dl
  KIRQL v6; // al
  int v7; // r8d

  v4 = 1;
  v5 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v5,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    17,
    (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
  v6 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.ReadLock);
  a1->Sco.ReadsEnabled = 0;
  KeReleaseSpinLock(&a1->Sco.ReadLock, v6);
  ResourceQueue_Stop(&a1->Sco.ReadCtxQueue);
  BthUsb_ScoFreePartialUsbCtx(a1);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v4,
    v7,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    18,
    (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
}

```

## disassembly

```asm
0x140007ea0  push    rbx
0x140007ea2  push    rsi
0x140007ea3  push    rdi
0x140007ea4  push    r14
0x140007ea6  sub     rsp, 48h
0x140007eaa  mov     rsi, rcx
0x140007ead  mov     rcx, cs:WPP_GLOBAL_Control
0x140007eb4  mov     dil, 1
0x140007eb7  mov     eax, [rcx+2Ch]
0x140007eba  test    al, 8
0x140007ebc  jz      short loc_140007EC9
0x140007ebe  cmp     byte ptr [rcx+29h], 4
0x140007ec2  jb      short loc_140007EC9
0x140007ec4  mov     dl, dil
0x140007ec7  jmp     short loc_140007ECB
0x140007ec9  xor     dl, dl
0x140007ecb  mov     r9, [rcx+40h]
0x140007ecf  lea     r14, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140007ed6  mov     rcx, [rcx+18h]
0x140007eda  mov     [rsp+68h+var_30], r14
0x140007edf  mov     [rsp+68h+var_38], 11h
0x140007ee6  mov     [rsp+68h+var_40], 4
0x140007eee  mov     [rsp+68h+var_48], 4
0x140007ef3  call    WPP_RECORDER_AND_TRACE_SF_
0x140007ef8  lea     rbx, [rsi+248h]
0x140007eff  mov     rcx, rbx; SpinLock
0x140007f02  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007f09  nop     dword ptr [rax+rax+00h]
0x140007f0e  mov     rcx, rbx; SpinLock
0x140007f11  mov     byte ptr [rsi+256h], 0
0x140007f18  mov     dl, al; NewIrql
0x140007f1a  call    cs:__imp_KeReleaseSpinLock
0x140007f21  nop     dword ptr [rax+rax+00h]
0x140007f26  lea     rcx, [rsi+198h]
0x140007f2d  call    ResourceQueue_Stop
0x140007f32  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x140007f35  call    ?BthUsb_ScoFreePartialUsbCtx@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoFreePartialUsbCtx(_DEVICE_EXTENSION *)
0x140007f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f41  mov     eax, [rcx+2Ch]
0x140007f44  test    al, 8
0x140007f46  jz      short loc_140007F4E
0x140007f48  cmp     byte ptr [rcx+29h], 4
0x140007f4c  jnb     short loc_140007F51
0x140007f4e  xor     dil, dil
0x140007f51  mov     r9, [rcx+40h]
0x140007f55  mov     dl, dil
0x140007f58  mov     rcx, [rcx+18h]
0x140007f5c  mov     [rsp+68h+var_30], r14
0x140007f61  mov     [rsp+68h+var_38], 12h
0x140007f68  mov     [rsp+68h+var_40], 4
0x140007f70  mov     [rsp+68h+var_48], 4
0x140007f75  call    WPP_RECORDER_AND_TRACE_SF_
0x140007f7a  add     rsp, 48h
0x140007f7e  pop     r14
0x140007f80  pop     rdi
0x140007f81  pop     rsi
0x140007f82  pop     rbx
0x140007f83  retn
```
