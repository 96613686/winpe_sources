# MbbAdapterGetDataClass(_MINIPORT_ADAPTER_CONTEXT *,ulong *)

- ea: `0x1400030d8`
- end: `0x14000311e`
- name: `?MbbAdapterGetDataClass@@YAXPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAK@Z`
- size: `70`
- prototype: `void __fastcall(PKSPIN_LOCK SpinLock, unsigned int *)`
- caller_count: `4`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14002e470`
- `0x140030bc0`
- `0x1400327d0`
- `0x14003ac60`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140003106`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003106`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400030e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400030e8`

## pseudocode

```c
void __fastcall MbbAdapterGetDataClass(PKSPIN_LOCK SpinLock, unsigned int *a2)
{
  KIRQL v4; // al
  unsigned int v5; // r8d

  v4 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  v5 = *((_DWORD *)SpinLock + 271);
  *((_BYTE *)SpinLock + 8) = v4;
  *a2 = v5;
  KeReleaseSpinLock(SpinLock, v4);
}

```

## disassembly

```asm
0x1400030d8  mov     [rsp+arg_0], rbx
0x1400030dd  push    rdi
0x1400030de  sub     rsp, 20h
0x1400030e2  mov     rbx, rdx
0x1400030e5  mov     rdi, rcx
0x1400030e8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400030ef  nop     dword ptr [rax+rax+00h]
0x1400030f4  mov     r8d, [rdi+43Ch]
0x1400030fb  mov     rcx, rdi; SpinLock
0x1400030fe  mov     dl, al; NewIrql
0x140003100  mov     [rdi+8], al
0x140003103  mov     [rbx], r8d
0x140003106  call    cs:__imp_KeReleaseSpinLock
0x14000310d  nop     dword ptr [rax+rax+00h]
0x140003112  mov     rbx, [rsp+28h+arg_0]
0x140003117  add     rsp, 20h
0x14000311b  pop     rdi
0x14000311c  retn
```
