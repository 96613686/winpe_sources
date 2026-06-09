# BthUsbAltSetting6_ScoWriteStart(_DEVICE_EXTENSION *)

- ea: `0x140008f40`
- end: `0x140008fbc`
- name: `?BthUsbAltSetting6_ScoWriteStart@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140008f40`
- `0x140009740`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140008f9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008f9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008f57`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008f57`

## pseudocode

```c
__int64 __fastcall BthUsbAltSetting6_ScoWriteStart(struct _DEVICE_EXTENSION *a1)
{
  unsigned __int64 *p_Lock; // rdi
  KIRQL v3; // al
  unsigned __int16 i; // r8
  __int64 v5; // rdx
  __int64 v6; // rdx
  int v7; // r8d

  p_Lock = &a1->Sco.Channel[0].Lock;
  v3 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.Channel[0].Lock);
  for ( i = 0; i < a1->Sco.NumChannels; a1->Sco.Channel[v5].WriteFrameInterval = 7 )
    v5 = i++;
  KeReleaseSpinLock(p_Lock, v3);
  return BthUsb_ScoWriteStart(a1, v6, v7);
}

```

## disassembly

```asm
0x140008f40  mov     [rsp+arg_0], rbx
0x140008f45  push    rdi
0x140008f46  sub     rsp, 20h
0x140008f4a  lea     rdi, [rcx+2B8h]
0x140008f51  mov     rbx, rcx
0x140008f54  mov     rcx, rdi; SpinLock
0x140008f57  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008f5e  nop     dword ptr [rax+rax+00h]
0x140008f63  xor     r8d, r8d
0x140008f66  xor     edx, edx
0x140008f68  mov     cl, al
0x140008f6a  cmp     dx, [rbx+2ACh]
0x140008f71  jnb     short loc_140008F97
0x140008f73  movzx   edx, r8w
0x140008f77  inc     r8w
0x140008f7b  imul    rax, rdx, 98h
0x140008f82  mov     dword ptr [rax+rbx+344h], 7
0x140008f8d  cmp     r8w, [rbx+2ACh]
0x140008f95  jb      short loc_140008F73
0x140008f97  mov     dl, cl; NewIrql
0x140008f99  mov     rcx, rdi; SpinLock
0x140008f9c  call    cs:__imp_KeReleaseSpinLock
0x140008fa3  nop     dword ptr [rax+rax+00h]
0x140008fa8  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140008fab  call    ?BthUsb_ScoWriteStart@@YAJPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoWriteStart(_DEVICE_EXTENSION *)
0x140008fb0  mov     rbx, [rsp+28h+arg_0]
0x140008fb5  add     rsp, 20h
0x140008fb9  pop     rdi
0x140008fba  retn
```
