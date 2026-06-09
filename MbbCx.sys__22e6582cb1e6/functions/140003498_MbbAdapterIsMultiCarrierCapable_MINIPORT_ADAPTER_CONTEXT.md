# MbbAdapterIsMultiCarrierCapable(_MINIPORT_ADAPTER_CONTEXT *)

- ea: `0x140003498`
- end: `0x1400034dc`
- name: `?MbbAdapterIsMultiCarrierCapable@@YAEPEAU_MINIPORT_ADAPTER_CONTEXT@@@Z`
- size: `68`
- prototype: `unsigned __int8 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140014730`
- `0x140014ea0`
- `0x140015710`
- `0x14002e470`
- `0x140030bc0`
- `0x1400327d0`
- `0x14003ac60`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400034c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400034a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400034a5`

## pseudocode

```c
char __fastcall MbbAdapterIsMultiCarrierCapable(PKSPIN_LOCK SpinLock)
{
  KIRQL v2; // al
  char v3; // bl

  v2 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  v3 = SpinLock[136] & 1;
  *((_BYTE *)SpinLock + 8) = v2;
  KeReleaseSpinLock(SpinLock, v2);
  return v3;
}

```

## disassembly

```asm
0x140003498  mov     [rsp+arg_0], rbx
0x14000349d  push    rdi
0x14000349e  sub     rsp, 20h
0x1400034a2  mov     rdi, rcx
0x1400034a5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400034ac  nop     dword ptr [rax+rax+00h]
0x1400034b1  mov     bl, [rdi+440h]
0x1400034b7  mov     rcx, rdi; SpinLock
0x1400034ba  and     bl, 1
0x1400034bd  mov     [rdi+8], al
0x1400034c0  mov     dl, al; NewIrql
0x1400034c2  call    cs:__imp_KeReleaseSpinLock
0x1400034c9  nop     dword ptr [rax+rax+00h]
0x1400034ce  mov     al, bl
0x1400034d0  mov     rbx, [rsp+28h+arg_0]
0x1400034d5  add     rsp, 20h
0x1400034d9  pop     rdi
0x1400034da  retn
```
