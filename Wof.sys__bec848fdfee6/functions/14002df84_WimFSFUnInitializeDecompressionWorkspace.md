# WimFSFUnInitializeDecompressionWorkspace

- ea: `0x14002df84`
- end: `0x14002e002`
- name: `WimFSFUnInitializeDecompressionWorkspace`
- size: `126`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022e2c`

## callees

- `0x14002df84`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002dfd8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002dfeb`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002dfd8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002dfeb`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002df9f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002dfb2`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002dfc5`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002df9f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002dfb2`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002dfc5`

## pseudocode

```c
void __fastcall WimFSFUnInitializeDecompressionWorkspace(__int64 a1)
{
  if ( (*(_DWORD *)(a1 + 96) & 2) != 0 && (*(_DWORD *)(a1 + 100) & 1) != 0 )
  {
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 128));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 512));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 320));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 640));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 768));
    *(_DWORD *)(a1 + 100) &= ~1u;
  }
}

```

## disassembly

```asm
0x14002df84  push    rbx
0x14002df86  sub     rsp, 20h
0x14002df8a  mov     eax, [rcx+60h]
0x14002df8d  mov     rbx, rcx
0x14002df90  test    al, 2
0x14002df92  jz      short loc_14002DFFB
0x14002df94  mov     eax, [rcx+64h]
0x14002df97  test    al, 1
0x14002df99  jz      short loc_14002DFFB
0x14002df9b  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x14002df9f  call    cs:__imp_ExDeletePagedLookasideList
0x14002dfa6  nop     dword ptr [rax+rax+00h]
0x14002dfab  lea     rcx, [rbx+200h]; Lookaside
0x14002dfb2  call    cs:__imp_ExDeletePagedLookasideList
0x14002dfb9  nop     dword ptr [rax+rax+00h]
0x14002dfbe  lea     rcx, [rbx+140h]; Lookaside
0x14002dfc5  call    cs:__imp_ExDeletePagedLookasideList
0x14002dfcc  nop     dword ptr [rax+rax+00h]
0x14002dfd1  lea     rcx, [rbx+280h]; Lookaside
0x14002dfd8  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002dfdf  nop     dword ptr [rax+rax+00h]
0x14002dfe4  lea     rcx, [rbx+300h]; Lookaside
0x14002dfeb  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002dff2  nop     dword ptr [rax+rax+00h]
0x14002dff7  and     dword ptr [rbx+64h], 0FFFFFFFEh
0x14002dffb  add     rsp, 20h
0x14002dfff  pop     rbx
0x14002e000  retn
```
