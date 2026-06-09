# HampIpcChannelObjectComparePayloadForTree

- ea: `0x1800095a0`
- end: `0x1800095ad`
- name: `HampIpcChannelObjectComparePayloadForTree`
- size: `13`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800090c0`
- `0x1800092d0`
- `0x180009400`

## callees

- `0x18001c010`

## pseudocode

```c
__int64 __fastcall HampIpcChannelObjectComparePayloadForTree(__int64 a1, __int64 a2)
{
  return (*(__int64 (**)(void))(*(_QWORD *)(a2 + 40) + 72LL))();
}

```

## disassembly

```asm
0x1800095a0  mov     rax, [rdx+28h]
0x1800095a4  mov     rax, [rax+48h]
0x1800095a8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
