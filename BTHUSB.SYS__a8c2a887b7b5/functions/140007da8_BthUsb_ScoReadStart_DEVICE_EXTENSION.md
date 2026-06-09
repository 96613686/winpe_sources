# BthUsb_ScoReadStart(_DEVICE_EXTENSION *)

- ea: `0x140007da8`
- end: `0x140007e99`
- name: `?BthUsb_ScoReadStart@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400057ac`

## callees

- `0x14000175c`
- `0x140007c5c`
- `0x140007da8`
- `0x14000db18`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140007e22`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007e22`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007e0a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007e0a`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoReadStart(struct _DEVICE_EXTENSION *a1, __int64 a2, int a3)
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
    15,
    (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
  v6 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.ReadLock);
  a1->Sco.ReadsEnabled = 1;
  KeReleaseSpinLock(&a1->Sco.ReadLock, v6);
  ResourceQueue_Start(&a1->Sco.ReadCtxQueue);
  BthUsb_ScoReadData(a1, a1->Sco.UsbAltSetting->MAX_PENDING_READS);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v4,
    v7,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    16,
    (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140007da8  push    rbx
0x140007daa  push    rsi
0x140007dab  push    rdi
0x140007dac  push    r14
0x140007dae  sub     rsp, 48h
0x140007db2  mov     rsi, rcx
0x140007db5  mov     rcx, cs:WPP_GLOBAL_Control
0x140007dbc  mov     dil, 1
0x140007dbf  mov     eax, [rcx+2Ch]
0x140007dc2  test    al, 8
0x140007dc4  jz      short loc_140007DD1
0x140007dc6  cmp     byte ptr [rcx+29h], 4
0x140007dca  jb      short loc_140007DD1
0x140007dcc  mov     dl, dil
0x140007dcf  jmp     short loc_140007DD3
0x140007dd1  xor     dl, dl
0x140007dd3  mov     r9, [rcx+40h]
0x140007dd7  lea     r14, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140007dde  mov     rcx, [rcx+18h]
0x140007de2  mov     [rsp+68h+var_30], r14
0x140007de7  mov     [rsp+68h+var_38], 0Fh
0x140007dee  mov     [rsp+68h+var_40], 4
0x140007df6  mov     [rsp+68h+var_48], 4
0x140007dfb  call    WPP_RECORDER_AND_TRACE_SF_
0x140007e00  lea     rbx, [rsi+248h]
0x140007e07  mov     rcx, rbx; SpinLock
0x140007e0a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007e11  nop     dword ptr [rax+rax+00h]
0x140007e16  mov     rcx, rbx; SpinLock
0x140007e19  mov     [rsi+256h], dil
0x140007e20  mov     dl, al; NewIrql
0x140007e22  call    cs:__imp_KeReleaseSpinLock
0x140007e29  nop     dword ptr [rax+rax+00h]
0x140007e2e  lea     rcx, [rsi+198h]
0x140007e35  call    ResourceQueue_Start
0x140007e3a  mov     rdx, [rsi+478h]
0x140007e41  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x140007e44  mov     edx, [rdx+4Ch]; unsigned int
0x140007e47  call    ?BthUsb_ScoReadData@@YAJPEAU_DEVICE_EXTENSION@@K@Z; BthUsb_ScoReadData(_DEVICE_EXTENSION *,ulong)
0x140007e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e53  mov     eax, [rcx+2Ch]
0x140007e56  test    al, 8
0x140007e58  jz      short loc_140007E60
0x140007e5a  cmp     byte ptr [rcx+29h], 4
0x140007e5e  jnb     short loc_140007E63
0x140007e60  xor     dil, dil
0x140007e63  mov     r9, [rcx+40h]
0x140007e67  mov     dl, dil
0x140007e6a  mov     rcx, [rcx+18h]
0x140007e6e  mov     [rsp+68h+var_30], r14
0x140007e73  mov     [rsp+68h+var_38], 10h
0x140007e7a  mov     [rsp+68h+var_40], 4
0x140007e82  mov     [rsp+68h+var_48], 4
0x140007e87  call    WPP_RECORDER_AND_TRACE_SF_
0x140007e8c  xor     eax, eax
0x140007e8e  add     rsp, 48h
0x140007e92  pop     r14
0x140007e94  pop     rdi
0x140007e95  pop     rsi
0x140007e96  pop     rbx
0x140007e97  retn
```
