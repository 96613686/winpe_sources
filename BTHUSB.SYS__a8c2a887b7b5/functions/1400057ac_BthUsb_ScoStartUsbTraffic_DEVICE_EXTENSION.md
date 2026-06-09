# BthUsb_ScoStartUsbTraffic(_DEVICE_EXTENSION *)

- ea: `0x1400057ac`
- end: `0x140005816`
- name: `?BthUsb_ScoStartUsbTraffic@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `106`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400030e0`
- `0x140005180`
- `0x140018910`

## callees

- `0x14000465c`
- `0x1400057ac`
- `0x140007da8`
- `0x14000de00`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400057bb`
- `ntoskrnl!KfRaiseIrql` at `0x1400057bb`
- `ntoskrnl!KeLowerIrql` at `0x1400057fe`
- `ntoskrnl!KeLowerIrql` at `0x1400057fe`

## pseudocode

```c
void __fastcall BthUsb_ScoStartUsbTraffic(struct _DEVICE_EXTENSION *a1)
{
  KIRQL v2; // di
  struct _DEVICE_EXTENSION *v3; // rcx

  v2 = KfRaiseIrql(2u);
  if ( BthUsb_ScoAnyTransfer(a1, 0) )
    ((void (*)(void))a1->Sco.UsbAltSetting->WriteStart)();
  if ( BthUsb_ScoAnyTransfer(a1, 1u) )
    BthUsb_ScoReadStart(v3);
  KeLowerIrql(v2);
}

```

## disassembly

```asm
0x1400057ac  mov     [rsp+arg_0], rbx
0x1400057b1  push    rdi
0x1400057b2  sub     rsp, 20h
0x1400057b6  mov     rbx, rcx
0x1400057b9  mov     cl, 2; NewIrql
0x1400057bb  call    cs:__imp_KfRaiseIrql
0x1400057c2  nop     dword ptr [rax+rax+00h]
0x1400057c7  xor     edx, edx; unsigned __int8
0x1400057c9  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x1400057cc  mov     dil, al
0x1400057cf  call    ?BthUsb_ScoAnyTransfer@@YAEPEAU_DEVICE_EXTENSION@@E@Z; BthUsb_ScoAnyTransfer(_DEVICE_EXTENSION *,uchar)
0x1400057d4  test    al, al
0x1400057d6  jz      short loc_1400057E8
0x1400057d8  mov     rdx, [rbx+478h]
0x1400057df  mov     rax, [rdx+20h]
0x1400057e3  call    _guard_dispatch_icall
0x1400057e8  mov     dl, 1; unsigned __int8
0x1400057ea  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x1400057ed  call    ?BthUsb_ScoAnyTransfer@@YAEPEAU_DEVICE_EXTENSION@@E@Z; BthUsb_ScoAnyTransfer(_DEVICE_EXTENSION *,uchar)
0x1400057f2  test    al, al
0x1400057f4  jz      short loc_1400057FB
0x1400057f6  call    ?BthUsb_ScoReadStart@@YAJPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoReadStart(_DEVICE_EXTENSION *)
0x1400057fb  mov     cl, dil; NewIrql
0x1400057fe  call    cs:__imp_KeLowerIrql
0x140005805  nop     dword ptr [rax+rax+00h]
0x14000580a  mov     rbx, [rsp+28h+arg_0]
0x14000580f  add     rsp, 20h
0x140005813  pop     rdi
0x140005814  retn
```
