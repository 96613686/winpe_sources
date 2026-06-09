# VfsDeleteScb

- ea: `0x14000d72c`
- end: `0x14000d7b2`
- name: `VfsDeleteScb`
- size: `134`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000d868`

## callees

- `0x140009368`
- `0x14000d72c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d789`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d789`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14000d735`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14000d735`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000d749`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000d749`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000d79f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000d79f`
- `FLTMGR!FltReleaseContext` at `0x14000d772`
- `FLTMGR!FltReleaseContext` at `0x14000d772`

## pseudocode

```c
void __fastcall VfsDeleteScb(PVOID Entry)
{
  void *v2; // rcx
  void *v3; // rcx

  FsRtlTeardownPerStreamContexts((PFSRTL_ADVANCED_FCB_HEADER)Entry);
  ExDeleteResourceLite((PERESOURCE)(*((_QWORD *)Entry + 15) + 56LL));
  v2 = (void *)*((_QWORD *)Entry + 18);
  if ( v2 )
    VfsReleaseMappingEntry(v2);
  v3 = (void *)*((_QWORD *)Entry + 16);
  if ( v3 )
    FltReleaseContext(v3);
  ExFreeToNPagedLookasideList(&stru_14001F700, *((PVOID *)Entry + 15));
  ExFreeToPagedLookasideList(&stru_14001F680, Entry);
}

```

## disassembly

```asm
0x14000d72c  push    rbx
0x14000d72e  sub     rsp, 20h
0x14000d732  mov     rbx, rcx
0x14000d735  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x14000d73c  nop     dword ptr [rax+rax+00h]
0x14000d741  mov     rcx, [rbx+78h]
0x14000d745  add     rcx, 38h ; '8'; Resource
0x14000d749  call    cs:__imp_ExDeleteResourceLite
0x14000d750  nop     dword ptr [rax+rax+00h]
0x14000d755  mov     rcx, [rbx+90h]; P
0x14000d75c  test    rcx, rcx
0x14000d75f  jz      short loc_14000D766
0x14000d761  call    VfsReleaseMappingEntry
0x14000d766  mov     rcx, [rbx+80h]; Context
0x14000d76d  test    rcx, rcx
0x14000d770  jz      short loc_14000D77E
0x14000d772  call    cs:__imp_FltReleaseContext
0x14000d779  nop     dword ptr [rax+rax+00h]
0x14000d77e  mov     rdx, [rbx+78h]; Entry
0x14000d782  lea     rcx, stru_14001F700; Lookaside
0x14000d789  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000d790  nop     dword ptr [rax+rax+00h]
0x14000d795  mov     rdx, rbx; Entry
0x14000d798  lea     rcx, stru_14001F680; Lookaside
0x14000d79f  call    cs:__imp_ExFreeToPagedLookasideList
0x14000d7a6  nop     dword ptr [rax+rax+00h]
0x14000d7ab  add     rsp, 20h
0x14000d7af  pop     rbx
0x14000d7b0  retn
```
