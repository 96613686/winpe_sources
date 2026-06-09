# PplpLazyInitializeLookasideList

- ea: `0x14000ab3c`
- end: `0x14000abcc`
- name: `PplpLazyInitializeLookasideList`
- size: `144`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140005f20`
- `0x140006580`
- `0x140006ad0`
- `0x140009190`
- `0x14000a9e8`
- `0x14000aab4`

## callees

- `0x14000ab3c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ab4f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ab4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ab6b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ab6b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000abba`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000abba`

## pseudocode

```c
void __fastcall PplpLazyInitializeLookasideList(__int64 a1, __int64 a2)
{
  KIRQL v4; // bp

  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 104));
  if ( !*(_BYTE *)(a2 + 112) )
  {
    ExInitializeLookasideListEx(
      (PLOOKASIDE_LIST_EX)a2,
      PplpGenericAllocateFunction,
      PplpGenericFreeFunction,
      *(POOL_TYPE *)(a1 + 32),
      *(_DWORD *)(a1 + 4),
      *(_QWORD *)(a1 + 16),
      *(_DWORD *)(a1 + 8),
      *(_WORD *)(a1 + 36));
    *(_BYTE *)(a2 + 112) = 1;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 104), v4);
}

```

## disassembly

```asm
0x14000ab3c  push    rbx
0x14000ab3e  push    rbp
0x14000ab3f  push    rsi
0x14000ab40  push    rdi
0x14000ab41  sub     rsp, 48h
0x14000ab45  mov     rdi, rcx
0x14000ab48  mov     rbx, rdx
0x14000ab4b  lea     rcx, [rdx+68h]; SpinLock
0x14000ab4f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ab56  nop     dword ptr [rax+rax+00h]
0x14000ab5b  cmp     byte ptr [rbx+70h], 0
0x14000ab5f  mov     bpl, al
0x14000ab62  jz      short loc_14000AB81
0x14000ab64  mov     dl, bpl; NewIrql
0x14000ab67  lea     rcx, [rbx+68h]; SpinLock
0x14000ab6b  call    cs:__imp_KeReleaseSpinLock
0x14000ab72  nop     dword ptr [rax+rax+00h]
0x14000ab77  add     rsp, 48h
0x14000ab7b  pop     rdi
0x14000ab7c  pop     rsi
0x14000ab7d  pop     rbp
0x14000ab7e  pop     rbx
0x14000ab7f  retn
0x14000ab81  movzx   r8d, word ptr [rdi+24h]
0x14000ab86  mov     rcx, rbx; Lookaside
0x14000ab89  mov     edx, [rdi+4]
0x14000ab8c  mov     r9d, [rdi+20h]; PoolType
0x14000ab90  mov     [rsp+68h+Depth], r8w; Depth
0x14000ab96  mov     r8d, [rdi+8]
0x14000ab9a  mov     [rsp+68h+Tag], r8d; Tag
0x14000ab9f  mov     r8, [rdi+10h]
0x14000aba3  mov     [rsp+68h+Size], r8; Size
0x14000aba8  lea     r8, PplpGenericFreeFunction; Free
0x14000abaf  mov     [rsp+68h+Flags], edx; Flags
0x14000abb3  lea     rdx, PplpGenericAllocateFunction; Allocate
0x14000abba  call    cs:__imp_ExInitializeLookasideListEx
0x14000abc1  nop     dword ptr [rax+rax+00h]
0x14000abc6  mov     byte ptr [rbx+70h], 1
0x14000abca  jmp     short loc_14000AB64
```
