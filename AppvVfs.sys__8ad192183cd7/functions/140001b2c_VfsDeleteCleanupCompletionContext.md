# VfsDeleteCleanupCompletionContext

- ea: `0x140001b2c`
- end: `0x140001b85`
- name: `VfsDeleteCleanupCompletionContext`
- size: `89`
- prototype: `void __fastcall(PFLT_CONTEXT *Entry)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400019e8`
- `0x14000a8d0`

## callees

- `0x140001b2c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001b40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001b40`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140001b72`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140001b72`
- `FLTMGR!FltReleaseContext` at `0x140001b5c`
- `FLTMGR!FltReleaseContext` at `0x140001b5c`

## pseudocode

```c
void __fastcall VfsDeleteCleanupCompletionContext(PFLT_CONTEXT *Entry)
{
  PFLT_CONTEXT v2; // rcx

  v2 = Entry[2];
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    Entry[2] = 0;
  }
  if ( *Entry )
    FltReleaseContext(*Entry);
  ExFreeToPagedLookasideList(&Lookaside, Entry);
}

```

## disassembly

```asm
0x140001b2c  push    rbx
0x140001b2e  sub     rsp, 20h
0x140001b32  mov     rbx, rcx
0x140001b35  mov     rcx, [rcx+10h]; P
0x140001b39  test    rcx, rcx
0x140001b3c  jz      short loc_140001B54
0x140001b3e  xor     edx, edx; Tag
0x140001b40  call    cs:__imp_ExFreePoolWithTag
0x140001b47  nop     dword ptr [rax+rax+00h]
0x140001b4c  mov     qword ptr [rbx+10h], 0
0x140001b54  mov     rcx, [rbx]; Context
0x140001b57  test    rcx, rcx
0x140001b5a  jz      short loc_140001B68
0x140001b5c  call    cs:__imp_FltReleaseContext
0x140001b63  nop     dword ptr [rax+rax+00h]
0x140001b68  mov     rdx, rbx; Entry
0x140001b6b  lea     rcx, Lookaside; Lookaside
0x140001b72  call    cs:__imp_ExFreeToPagedLookasideList
0x140001b79  nop     dword ptr [rax+rax+00h]
0x140001b7e  add     rsp, 20h
0x140001b82  pop     rbx
0x140001b83  retn
```
