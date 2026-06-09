# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800021b4`
- end: `0x1800021b9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003390`
- `0x1800033c0`
- `0x1800033f0`
- `0x180003450`
- `0x180004ef0`
- `0x1800053f0`
- `0x180005a90`
- `0x180005b78`
- `0x18000c1c4`
- `0x180011ca0`
- `0x180012900`
- `0x180012eb0`
- `0x1800130c0`
- `0x1800138f0`
- `0x180013ec0`
- `0x180014510`
- `0x180014d98`
- `0x1800152a0`
- `0x180015748`

## callees

- `0x180001984`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1800021b4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
