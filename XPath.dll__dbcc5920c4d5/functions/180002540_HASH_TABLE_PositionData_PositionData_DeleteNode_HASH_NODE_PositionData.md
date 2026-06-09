# HASH_TABLE<PositionData,PositionData *>::DeleteNode(HASH_NODE<PositionData> *)

- ea: `0x180002540`
- end: `0x180002573`
- name: `?DeleteNode@?$HASH_TABLE@VPositionData@@PEAV1@@@AEAAXPEAV?$HASH_NODE@VPositionData@@@@@Z`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002664`
- `0x180002c48`
- `0x18000e7bc`

## callees

- `0x1800010b8`
- `0x180002540`
- `0x180012010`

## pseudocode

```c
void __fastcall HASH_TABLE<PositionData,PositionData *>::DeleteNode(__int64 a1, _QWORD *a2)
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
0x180002540  push    rbx
0x180002542  sub     rsp, 20h
0x180002546  mov     rbx, rdx
0x180002549  mov     rdx, [rdx+8]
0x18000254d  test    rdx, rdx
0x180002550  jz      short loc_180002566
0x180002552  mov     rax, [rcx]
0x180002555  mov     rax, [rax+10h]
0x180002559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000255e  mov     qword ptr [rbx+8], 0
0x180002566  mov     rcx, rbx; Block
0x180002569  add     rsp, 20h
0x18000256d  pop     rbx
0x18000256e  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
