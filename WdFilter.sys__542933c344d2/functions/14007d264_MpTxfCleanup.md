# MpTxfCleanup

- ea: `0x14007d264`
- end: `0x14007d2bc`
- name: `MpTxfCleanup`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14007bef0`
- `0x14008f314`

## callees

- `0x14007d264`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14007d292`
- `ntoskrnl!ExDeleteResourceLite` at `0x14007d292`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d2aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d2aa`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007d278`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007d278`

## pseudocode

```c
void MpTxfCleanup()
{
  if ( MpTxfData )
  {
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpTxfData + 64));
    ExDeleteResourceLite((PERESOURCE)((char *)MpTxfData + 192));
    ExFreePoolWithTag(MpTxfData, 0x6474504Du);
  }
}

```

## disassembly

```asm
0x14007d264  sub     rsp, 28h
0x14007d268  mov     rcx, cs:MpTxfData
0x14007d26f  test    rcx, rcx
0x14007d272  jz      short loc_14007D2B6
0x14007d274  add     rcx, 40h ; '@'; Lookaside
0x14007d278  call    cs:__imp_ExDeletePagedLookasideList
0x14007d27f  nop     dword ptr [rax+rax+00h]
0x14007d284  mov     rcx, cs:MpTxfData
0x14007d28b  add     rcx, 0C0h; Resource
0x14007d292  call    cs:__imp_ExDeleteResourceLite
0x14007d299  nop     dword ptr [rax+rax+00h]
0x14007d29e  mov     rcx, cs:MpTxfData; P
0x14007d2a5  mov     edx, 6474504Dh; Tag
0x14007d2aa  call    cs:__imp_ExFreePoolWithTag
0x14007d2b1  nop     dword ptr [rax+rax+00h]
0x14007d2b6  add     rsp, 28h
0x14007d2ba  retn
```
