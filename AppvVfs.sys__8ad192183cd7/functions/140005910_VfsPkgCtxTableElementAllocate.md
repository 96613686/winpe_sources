# VfsPkgCtxTableElementAllocate

- ea: `0x140005910`
- end: `0x140005949`
- name: `VfsPkgCtxTableElementAllocate`
- size: `57`
- prototype: `PVOID()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140005910`
- `0x140014000`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000591d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000591d`

## pseudocode

```c
PVOID VfsPkgCtxTableElementAllocate()
{
  PVOID v0; // rax
  PVOID v1; // rbx

  v0 = ExAllocateFromPagedLookasideList(&stru_14001F500);
  v1 = v0;
  if ( v0 )
    memset(v0, 0, 0x60u);
  return v1;
}

```

## disassembly

```asm
0x140005910  push    rbx
0x140005912  sub     rsp, 20h
0x140005916  lea     rcx, stru_14001F500; Lookaside
0x14000591d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140005924  nop     dword ptr [rax+rax+00h]
0x140005929  mov     rbx, rax
0x14000592c  test    rax, rax
0x14000592f  jz      short loc_14000593F
0x140005931  xor     edx, edx; Val
0x140005933  mov     rcx, rax; void *
0x140005936  lea     r8d, [rdx+60h]; Size
0x14000593a  call    memset
0x14000593f  mov     rax, rbx
0x140005942  add     rsp, 20h
0x140005946  pop     rbx
0x140005947  retn
```
