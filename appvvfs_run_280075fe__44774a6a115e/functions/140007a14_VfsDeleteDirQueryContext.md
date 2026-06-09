# VfsDeleteDirQueryContext

- ea: `0x140007a14`
- end: `0x140007a3f`
- name: `VfsDeleteDirQueryContext`
- size: `43`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400018c4`
- `0x140001d70`
- `0x140006710`
- `0x1400074f4`
- `0x14000d618`

## callees

- `0x14000748c`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140007a2c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140007a2c`

## pseudocode

```c
void __fastcall VfsDeleteDirQueryContext(PVOID Entry)
{
  VfsCleanupDirQueryContext();
  ExFreeToPagedLookasideList(&stru_14001F980, Entry);
}

```

## disassembly

```asm
0x140007a14  push    rbx
0x140007a16  sub     rsp, 20h
0x140007a1a  mov     rbx, rcx
0x140007a1d  call    VfsCleanupDirQueryContext
0x140007a22  mov     rdx, rbx; Entry
0x140007a25  lea     rcx, stru_14001F980; Lookaside
0x140007a2c  call    cs:__imp_ExFreeToPagedLookasideList
0x140007a33  nop     dword ptr [rax+rax+00h]
0x140007a38  add     rsp, 20h
0x140007a3c  pop     rbx
0x140007a3d  retn
```
