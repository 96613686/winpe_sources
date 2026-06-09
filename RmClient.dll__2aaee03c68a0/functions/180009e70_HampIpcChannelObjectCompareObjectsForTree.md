# HampIpcChannelObjectCompareObjectsForTree

- ea: `0x180009e70`
- end: `0x180009e7d`
- name: `HampIpcChannelObjectCompareObjectsForTree`
- size: `13`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009d40`

## callees

- `0x18001c010`

## pseudocode

```c
__int64 __fastcall HampIpcChannelObjectCompareObjectsForTree(__int64 a1)
{
  return (*(__int64 (**)(void))(*(_QWORD *)(a1 + 40) + 64LL))();
}

```

## disassembly

```asm
0x180009e70  mov     rax, [rcx+28h]
0x180009e74  mov     rax, [rax+40h]
0x180009e78  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
