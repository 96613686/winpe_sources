# VfsDeleteCreateCompletionContext

- ea: `0x140005308`
- end: `0x140005353`
- name: `VfsDeleteCreateCompletionContext`
- size: `75`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003f24`
- `0x14000414c`
- `0x14000a960`

## callees

- `0x140005308`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000531f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000531f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140005340`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140005340`

## pseudocode

```c
void __fastcall VfsDeleteCreateCompletionContext(_QWORD *Entry)
{
  void *v2; // rcx

  v2 = (void *)Entry[16];
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    Entry[16] = 0;
  }
  ExFreeToPagedLookasideList(&stru_14001F800, Entry);
}

```

## disassembly

```asm
0x140005308  push    rbx
0x14000530a  sub     rsp, 20h
0x14000530e  mov     rbx, rcx
0x140005311  mov     rcx, [rcx+80h]; P
0x140005318  test    rcx, rcx
0x14000531b  jz      short loc_140005336
0x14000531d  xor     edx, edx; Tag
0x14000531f  call    cs:__imp_ExFreePoolWithTag
0x140005326  nop     dword ptr [rax+rax+00h]
0x14000532b  mov     qword ptr [rbx+80h], 0
0x140005336  mov     rdx, rbx; Entry
0x140005339  lea     rcx, stru_14001F800; Lookaside
0x140005340  call    cs:__imp_ExFreeToPagedLookasideList
0x140005347  nop     dword ptr [rax+rax+00h]
0x14000534c  add     rsp, 20h
0x140005350  pop     rbx
0x140005351  retn
```
