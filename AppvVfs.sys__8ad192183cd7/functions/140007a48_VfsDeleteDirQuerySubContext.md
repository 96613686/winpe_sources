# VfsDeleteDirQuerySubContext

- ea: `0x140007a48`
- end: `0x140007ac4`
- name: `VfsDeleteDirQuerySubContext`
- size: `124`
- prototype: `void __fastcall(PVOID *Entry)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140007124`
- `0x14000748c`
- `0x14000783c`

## callees

- `0x140007a48`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140007a5c`
- `ntoskrnl!ObfDereferenceObject` at `0x140007a5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007a9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007a9b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140007ab1`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140007ab1`
- `FLTMGR!FltObjectDereference` at `0x140007a81`
- `FLTMGR!FltObjectDereference` at `0x140007a81`
- `FLTMGR!FltClose` at `0x140007a6c`
- `FLTMGR!FltClose` at `0x140007a6c`

## pseudocode

```c
void __fastcall VfsDeleteDirQuerySubContext(PVOID *Entry)
{
  PVOID v2; // rcx
  PVOID v3; // rcx

  if ( Entry[5] )
  {
    ObfDereferenceObject(Entry[4]);
    FltClose(Entry[5]);
  }
  v2 = Entry[3];
  if ( v2 )
    FltObjectDereference(v2);
  v3 = Entry[6];
  if ( v3 )
    ExFreePoolWithTag(v3, 0x62444656u);
  ExFreeToPagedLookasideList(&stru_14001FA00, Entry);
}

```

## disassembly

```asm
0x140007a48  push    rbx
0x140007a4a  sub     rsp, 20h
0x140007a4e  cmp     qword ptr [rcx+28h], 0
0x140007a53  mov     rbx, rcx
0x140007a56  jz      short loc_140007A78
0x140007a58  mov     rcx, [rcx+20h]; Object
0x140007a5c  call    cs:__imp_ObfDereferenceObject
0x140007a63  nop     dword ptr [rax+rax+00h]
0x140007a68  mov     rcx, [rbx+28h]; FileHandle
0x140007a6c  call    cs:__imp_FltClose
0x140007a73  nop     dword ptr [rax+rax+00h]
0x140007a78  mov     rcx, [rbx+18h]; FltObject
0x140007a7c  test    rcx, rcx
0x140007a7f  jz      short loc_140007A8D
0x140007a81  call    cs:__imp_FltObjectDereference
0x140007a88  nop     dword ptr [rax+rax+00h]
0x140007a8d  mov     rcx, [rbx+30h]; P
0x140007a91  test    rcx, rcx
0x140007a94  jz      short loc_140007AA7
0x140007a96  mov     edx, 62444656h; Tag
0x140007a9b  call    cs:__imp_ExFreePoolWithTag
0x140007aa2  nop     dword ptr [rax+rax+00h]
0x140007aa7  mov     rdx, rbx; Entry
0x140007aaa  lea     rcx, stru_14001FA00; Lookaside
0x140007ab1  call    cs:__imp_ExFreeToPagedLookasideList
0x140007ab8  nop     dword ptr [rax+rax+00h]
0x140007abd  add     rsp, 20h
0x140007ac1  pop     rbx
0x140007ac2  retn
```
