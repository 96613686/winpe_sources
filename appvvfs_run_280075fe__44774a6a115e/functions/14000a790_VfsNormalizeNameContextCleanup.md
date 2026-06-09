# VfsNormalizeNameContextCleanup

- ea: `0x14000a790`
- end: `0x14000a7c7`
- name: `VfsNormalizeNameContextCleanup`
- size: `55`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation`

## callees

- `0x140009368`
- `0x14000a790`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000a7b4`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000a7b4`

## pseudocode

```c
void __fastcall VfsNormalizeNameContextCleanup(void **Entry)
{
  void *v2; // rcx

  if ( Entry )
  {
    v2 = *Entry;
    if ( v2 )
      VfsReleaseMappingEntry(v2);
    ExFreeToPagedLookasideList(&stru_14001F900, Entry);
  }
}

```

## disassembly

```asm
0x14000a790  test    rcx, rcx
0x14000a793  jz      short locret_14000A7C5
0x14000a795  push    rbx
0x14000a796  sub     rsp, 20h
0x14000a79a  mov     rbx, rcx
0x14000a79d  mov     rcx, [rcx]; P
0x14000a7a0  test    rcx, rcx
0x14000a7a3  jz      short loc_14000A7AA
0x14000a7a5  call    VfsReleaseMappingEntry
0x14000a7aa  mov     rdx, rbx; Entry
0x14000a7ad  lea     rcx, stru_14001F900; Lookaside
0x14000a7b4  call    cs:__imp_ExFreeToPagedLookasideList
0x14000a7bb  nop     dword ptr [rax+rax+00h]
0x14000a7c0  add     rsp, 20h
0x14000a7c4  pop     rbx
0x14000a7c5  retn
```
