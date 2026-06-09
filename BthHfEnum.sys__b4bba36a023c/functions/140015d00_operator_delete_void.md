# operator delete(void *)

- ea: `0x140015d00`
- end: `0x140015d20`
- name: `??3@YAXPEAX@Z`
- size: `32`
- prototype: `void __fastcall(void *)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140015d30`
- `0x140015d70`
- `0x140015db0`
- `0x140015de8`
- `0x140017910`
- `0x140017950`
- `0x140017988`
- `0x1400186b0`
- `0x140018740`
- `0x14002eb38`

## callees

- `0x140015d00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015d0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d0e`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0x646D4370u);
}

```

## disassembly

```asm
0x140015d00  sub     rsp, 28h
0x140015d04  test    rcx, rcx
0x140015d07  jz      short loc_140015D1A
0x140015d09  mov     edx, 646D4370h; Tag
0x140015d0e  call    cs:__imp_ExFreePoolWithTag
0x140015d15  nop     dword ptr [rax+rax+00h]
0x140015d1a  add     rsp, 28h
0x140015d1e  retn
```
