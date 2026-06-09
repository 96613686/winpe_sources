# BfpDeleteInstanceTierNode

- ea: `0x140020228`
- end: `0x140020277`
- name: `BfpDeleteInstanceTierNode`
- size: `79`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140020280`

## callees

- `0x14001e854`
- `0x14001e8c0`
- `0x140020228`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020264`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020264`
- `FLTMGR!FltReleaseContext` at `0x140020250`
- `FLTMGR!FltReleaseContext` at `0x140020250`

## pseudocode

```c
void __fastcall BfpDeleteInstanceTierNode(_QWORD *P)
{
  _QWORD *v2; // rcx

  BfpDeletePathTree(P[3], P[2]);
  v2 = (_QWORD *)P[4];
  if ( v2 )
    BfpDeletePathTierNode(v2);
  FltReleaseContext((PFLT_CONTEXT)P[2]);
  ExFreePoolWithTag(P, 0x706D4642u);
}

```

## disassembly

```asm
0x140020228  push    rbx
0x14002022a  sub     rsp, 20h
0x14002022e  mov     rdx, [rcx+10h]
0x140020232  mov     rbx, rcx
0x140020235  mov     rcx, [rcx+18h]; P
0x140020239  call    BfpDeletePathTree
0x14002023e  mov     rcx, [rbx+20h]; P
0x140020242  test    rcx, rcx
0x140020245  jz      short loc_14002024C
0x140020247  call    BfpDeletePathTierNode
0x14002024c  mov     rcx, [rbx+10h]; Context
0x140020250  call    cs:__imp_FltReleaseContext
0x140020257  nop     dword ptr [rax+rax+00h]
0x14002025c  mov     edx, 706D4642h; Tag
0x140020261  mov     rcx, rbx; P
0x140020264  call    cs:__imp_ExFreePoolWithTag
0x14002026b  nop     dword ptr [rax+rax+00h]
0x140020270  add     rsp, 20h
0x140020274  pop     rbx
0x140020275  retn
```
