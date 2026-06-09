# VfsDriverCleanup

- ea: `0x140024008`
- end: `0x140024130`
- name: `VfsDriverCleanup`
- size: `296`
- prototype: `void()`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140008100`
- `0x140024140`

## callees

- `0x14000535c`
- `0x140008584`
- `0x1400086e8`
- `0x140024008`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002404d`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140024060`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140024073`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140024086`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140024099`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400240ac`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400240bf`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400240e5`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400240f8`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002410b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002411e`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002404d`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140024060`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140024073`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140024086`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140024099`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400240ac`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400240bf`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400240e5`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400240f8`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002410b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002411e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400240d2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400240d2`
- `FLTMGR!FltUnregisterFilter` at `0x140024018`
- `FLTMGR!FltUnregisterFilter` at `0x140024018`

## pseudocode

```c
void VfsDriverCleanup()
{
  if ( VfsData )
    FltUnregisterFilter(VfsData);
  VfsDeleteControlDevice();
  VfsCtxTableDelete(&Table);
  VfsCtxTableDelete(&stru_14001F470);
  VfsCleanupPrefixTreeLibrary();
  ExDeletePagedLookasideList(&stru_14001FA80);
  ExDeletePagedLookasideList(&stru_14001FA00);
  ExDeletePagedLookasideList(&stru_14001F980);
  ExDeletePagedLookasideList(&stru_14001F900);
  ExDeletePagedLookasideList(&Lookaside);
  ExDeletePagedLookasideList(&stru_14001F800);
  ExDeletePagedLookasideList(&stru_14001F780);
  ExDeleteNPagedLookasideList(&stru_14001F700);
  ExDeletePagedLookasideList(&stru_14001F680);
  ExDeletePagedLookasideList(&stru_14001F600);
  ExDeletePagedLookasideList(&stru_14001F500);
  ExDeletePagedLookasideList(&stru_14001F580);
}

```

## disassembly

```asm
0x140024008  sub     rsp, 28h
0x14002400c  mov     rcx, cs:VfsData; Filter
0x140024013  test    rcx, rcx
0x140024016  jz      short loc_140024024
0x140024018  call    cs:__imp_FltUnregisterFilter
0x14002401f  nop     dword ptr [rax+rax+00h]
0x140024024  call    VfsDeleteControlDevice
0x140024029  lea     rcx, Table; Table
0x140024030  call    VfsCtxTableDelete
0x140024035  lea     rcx, stru_14001F470; Table
0x14002403c  call    VfsCtxTableDelete
0x140024041  call    VfsCleanupPrefixTreeLibrary
0x140024046  lea     rcx, stru_14001FA80; Lookaside
0x14002404d  call    cs:__imp_ExDeletePagedLookasideList
0x140024054  nop     dword ptr [rax+rax+00h]
0x140024059  lea     rcx, stru_14001FA00; Lookaside
0x140024060  call    cs:__imp_ExDeletePagedLookasideList
0x140024067  nop     dword ptr [rax+rax+00h]
0x14002406c  lea     rcx, stru_14001F980; Lookaside
0x140024073  call    cs:__imp_ExDeletePagedLookasideList
0x14002407a  nop     dword ptr [rax+rax+00h]
0x14002407f  lea     rcx, stru_14001F900; Lookaside
0x140024086  call    cs:__imp_ExDeletePagedLookasideList
0x14002408d  nop     dword ptr [rax+rax+00h]
0x140024092  lea     rcx, Lookaside; Lookaside
0x140024099  call    cs:__imp_ExDeletePagedLookasideList
0x1400240a0  nop     dword ptr [rax+rax+00h]
0x1400240a5  lea     rcx, stru_14001F800; Lookaside
0x1400240ac  call    cs:__imp_ExDeletePagedLookasideList
0x1400240b3  nop     dword ptr [rax+rax+00h]
0x1400240b8  lea     rcx, stru_14001F780; Lookaside
0x1400240bf  call    cs:__imp_ExDeletePagedLookasideList
0x1400240c6  nop     dword ptr [rax+rax+00h]
0x1400240cb  lea     rcx, stru_14001F700; Lookaside
0x1400240d2  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400240d9  nop     dword ptr [rax+rax+00h]
0x1400240de  lea     rcx, stru_14001F680; Lookaside
0x1400240e5  call    cs:__imp_ExDeletePagedLookasideList
0x1400240ec  nop     dword ptr [rax+rax+00h]
0x1400240f1  lea     rcx, stru_14001F600; Lookaside
0x1400240f8  call    cs:__imp_ExDeletePagedLookasideList
0x1400240ff  nop     dword ptr [rax+rax+00h]
0x140024104  lea     rcx, stru_14001F500; Lookaside
0x14002410b  call    cs:__imp_ExDeletePagedLookasideList
0x140024112  nop     dword ptr [rax+rax+00h]
0x140024117  lea     rcx, stru_14001F580; Lookaside
0x14002411e  call    cs:__imp_ExDeletePagedLookasideList
0x140024125  nop     dword ptr [rax+rax+00h]
0x14002412a  add     rsp, 28h
0x14002412e  retn
```
