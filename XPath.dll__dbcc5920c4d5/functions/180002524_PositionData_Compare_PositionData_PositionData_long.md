# PositionData::Compare(PositionData &,PositionData &,long *)

- ea: `0x180002524`
- end: `0x180002538`
- name: `?Compare@PositionData@@SAJAEAV1@0PEAJ@Z`
- size: `20`
- prototype: `__int64 __fastcall(struct PositionData *, struct PositionData *, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002464`
- `0x180002784`
- `0x180008380`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall PositionData::Compare(struct PositionData *a1, struct PositionData *a2, int *a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)a1 + 1) + 96LL))(
           *((_QWORD *)a1 + 1),
           *((_QWORD *)a2 + 1),
           a3);
}

```

## disassembly

```asm
0x180002524  mov     rcx, [rcx+8]
0x180002528  mov     rdx, [rdx+8]
0x18000252c  mov     rax, [rcx]
0x18000252f  mov     rax, [rax+60h]
0x180002533  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
