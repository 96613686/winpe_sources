# ResourceQueue_StopAndWait

- ea: `0x14000dbc4`
- end: `0x14000dc37`
- name: `ResourceQueue_StopAndWait`
- size: `115`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400077c4`
- `0x140007f8c`
- `0x140009000`
- `0x1400098bc`

## callees

- `0x14000dbc4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000dbf5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dbf5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dbda`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dbda`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000dc1a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000dc1a`

## pseudocode

```c
void __fastcall ResourceQueue_StopAndWait(__int64 a1)
{
  KIRQL v2; // al
  int v3; // ebx

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v3 = *(_DWORD *)(a1 + 32);
  *(_DWORD *)a1 = -1073741790;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v2);
  if ( v3 )
    KeWaitForSingleObject((PVOID)(a1 + 40), Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x14000dbc4  mov     [rsp+arg_0], rbx
0x14000dbc9  mov     [rsp+arg_8], rsi
0x14000dbce  push    rdi
0x14000dbcf  sub     rsp, 30h
0x14000dbd3  mov     rsi, rcx
0x14000dbd6  add     rcx, 8; SpinLock
0x14000dbda  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000dbe1  nop     dword ptr [rax+rax+00h]
0x14000dbe6  mov     ebx, [rsi+20h]
0x14000dbe9  lea     rcx, [rsi+8]; SpinLock
0x14000dbed  mov     dl, al; NewIrql
0x14000dbef  mov     dword ptr [rsi], 0C0000022h
0x14000dbf5  call    cs:__imp_KeReleaseSpinLock
0x14000dbfc  nop     dword ptr [rax+rax+00h]
0x14000dc01  test    ebx, ebx
0x14000dc03  jz      short loc_14000DC26
0x14000dc05  lea     rcx, [rsi+28h]; Object
0x14000dc09  mov     [rsp+38h+Timeout], 0; Timeout
0x14000dc12  xor     r9d, r9d; Alertable
0x14000dc15  xor     r8d, r8d; WaitMode
0x14000dc18  xor     edx, edx; WaitReason
0x14000dc1a  call    cs:__imp_KeWaitForSingleObject
0x14000dc21  nop     dword ptr [rax+rax+00h]
0x14000dc26  mov     rbx, [rsp+38h+arg_0]
0x14000dc2b  mov     rsi, [rsp+38h+arg_8]
0x14000dc30  add     rsp, 30h
0x14000dc34  pop     rdi
0x14000dc35  retn
```
