# VfsUserCtxTableElementFree

- ea: `0x140005b10`
- end: `0x140005b3f`
- name: `VfsUserCtxTableElementFree`
- size: `47`
- prototype: `void __fastcall(struct _RTL_AVL_TABLE *Table, PVOID Buffer)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1400059e8`
- `0x140005b10`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140005b2d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140005b2d`

## pseudocode

```c
void __fastcall VfsUserCtxTableElementFree(struct _RTL_AVL_TABLE *Table, PVOID Buffer)
{
  if ( (*((_DWORD *)Buffer + 29) & 1) != 0 )
    VfsUserCtxRelease((__int64)Buffer + 32);
  else
    ExFreeToPagedLookasideList(&stru_14001F580, Buffer);
}

```

## disassembly

```asm
0x140005b10  sub     rsp, 28h
0x140005b14  lea     rcx, [rdx+20h]
0x140005b18  mov     eax, [rcx+54h]
0x140005b1b  test    al, 1
0x140005b1d  jz      short loc_140005B26
0x140005b1f  call    VfsUserCtxRelease
0x140005b24  jmp     short loc_140005B39
0x140005b26  lea     rcx, stru_14001F580; Lookaside
0x140005b2d  call    cs:__imp_ExFreeToPagedLookasideList
0x140005b34  nop     dword ptr [rax+rax+00h]
0x140005b39  add     rsp, 28h
0x140005b3d  retn
```
