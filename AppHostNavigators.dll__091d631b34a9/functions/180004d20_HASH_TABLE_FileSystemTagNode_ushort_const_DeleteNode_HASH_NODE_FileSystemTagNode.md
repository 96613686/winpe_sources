# HASH_TABLE<FileSystemTagNode,ushort const *>::DeleteNode(HASH_NODE<FileSystemTagNode> *)

- ea: `0x180004d20`
- end: `0x180004d53`
- name: `?DeleteNode@?$HASH_TABLE@VFileSystemTagNode@@PEBG@@AEAAXPEAV?$HASH_NODE@VFileSystemTagNode@@@@@Z`
- size: `51`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800044ec`
- `0x180007808`
- `0x180009a24`
- `0x18000a2fc`
- `0x180012cc8`

## callees

- `0x1800011d4`
- `0x180004d20`
- `0x180014010`

## pseudocode

```c
void __fastcall HASH_TABLE<FileSystemTagNode,unsigned short const *>::DeleteNode(__int64 a1, _QWORD *a2)
{
  if ( a2[1] )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    a2[1] = 0;
  }
  operator delete(a2);
}

```

## disassembly

```asm
0x180004d20  push    rbx
0x180004d22  sub     rsp, 20h
0x180004d26  mov     rbx, rdx
0x180004d29  mov     rdx, [rdx+8]
0x180004d2d  test    rdx, rdx
0x180004d30  jz      short loc_180004D46
0x180004d32  mov     rax, [rcx]
0x180004d35  mov     rax, [rax+10h]
0x180004d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3e  mov     qword ptr [rbx+8], 0
0x180004d46  mov     rcx, rbx; Block
0x180004d49  add     rsp, 20h
0x180004d4d  pop     rbx
0x180004d4e  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
