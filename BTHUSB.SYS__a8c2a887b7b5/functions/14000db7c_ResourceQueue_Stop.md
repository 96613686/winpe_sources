# ResourceQueue_Stop

- ea: `0x14000db7c`
- end: `0x14000dbbd`
- name: `ResourceQueue_Stop`
- size: `65`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140007ea0`
- `0x140007f8c`
- `0x140009800`
- `0x1400098bc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000dba5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dba5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000db8d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000db8d`

## pseudocode

```c
void __fastcall ResourceQueue_Stop(__int64 a1)
{
  KIRQL v2; // al

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  *(_DWORD *)a1 = -1073741790;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v2);
}

```

## disassembly

```asm
0x14000db7c  mov     [rsp+arg_0], rbx
0x14000db81  push    rdi
0x14000db82  sub     rsp, 20h
0x14000db86  mov     rbx, rcx
0x14000db89  add     rcx, 8; SpinLock
0x14000db8d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000db94  nop     dword ptr [rax+rax+00h]
0x14000db99  lea     rcx, [rbx+8]; SpinLock
0x14000db9d  mov     dword ptr [rbx], 0C0000022h
0x14000dba3  mov     dl, al; NewIrql
0x14000dba5  call    cs:__imp_KeReleaseSpinLock
0x14000dbac  nop     dword ptr [rax+rax+00h]
0x14000dbb1  mov     rbx, [rsp+28h+arg_0]
0x14000dbb6  add     rsp, 20h
0x14000dbba  pop     rdi
0x14000dbbb  retn
```
