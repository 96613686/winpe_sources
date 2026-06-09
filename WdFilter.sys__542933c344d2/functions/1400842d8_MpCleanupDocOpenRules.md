# MpCleanupDocOpenRules

- ea: `0x1400842d8`
- end: `0x14008433d`
- name: `MpCleanupDocOpenRules`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14007bef0`
- `0x14008f314`

## callees

- `0x1400762c8`
- `0x1400842d8`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140084313`
- `ntoskrnl!ExDeleteResourceLite` at `0x140084313`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008432b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008432b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400842fc`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400842fc`

## pseudocode

```c
void MpCleanupDocOpenRules()
{
  if ( MpBmDocOpenRules )
  {
    MpDeleteDocOpenRules((char *)MpBmDocOpenRules + 8);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpBmDocOpenRules + 1);
    ExDeleteResourceLite((PERESOURCE)((char *)MpBmDocOpenRules + 16));
    ExFreePoolWithTag(MpBmDocOpenRules, 0x6F64504Du);
  }
}

```

## disassembly

```asm
0x1400842d8  sub     rsp, 28h
0x1400842dc  mov     rcx, cs:MpBmDocOpenRules
0x1400842e3  test    rcx, rcx
0x1400842e6  jz      short loc_140084337
0x1400842e8  add     rcx, 8
0x1400842ec  call    MpDeleteDocOpenRules
0x1400842f1  mov     rcx, cs:MpBmDocOpenRules
0x1400842f8  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x1400842fc  call    cs:__imp_ExDeletePagedLookasideList
0x140084303  nop     dword ptr [rax+rax+00h]
0x140084308  mov     rcx, cs:MpBmDocOpenRules
0x14008430f  add     rcx, 10h; Resource
0x140084313  call    cs:__imp_ExDeleteResourceLite
0x14008431a  nop     dword ptr [rax+rax+00h]
0x14008431f  mov     rcx, cs:MpBmDocOpenRules; P
0x140084326  mov     edx, 6F64504Dh; Tag
0x14008432b  call    cs:__imp_ExFreePoolWithTag
0x140084332  nop     dword ptr [rax+rax+00h]
0x140084337  add     rsp, 28h
0x14008433b  retn
```
