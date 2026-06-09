# operator delete(void *,unsigned __int64)

- ea: `0x180002c74`
- end: `0x180002c79`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `102`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003780`
- `0x180003970`
- `0x180003c40`
- `0x180003d50`
- `0x180003ef0`
- `0x1800040c0`
- `0x180004230`
- `0x1800043e0`
- `0x180004560`
- `0x180005070`
- `0x180005330`
- `0x180005570`
- `0x1800059d0`
- `0x180005a20`
- `0x180005a60`
- `0x180005aa0`
- `0x180005af0`
- `0x180005b40`
- `0x180005cb0`
- `0x180005d90`
- `0x1800064a0`
- `0x1800064f0`
- `0x180006c60`
- `0x180006fb0`
- `0x180008170`
- `0x1800084e0`
- `0x180008620`
- `0x180008770`
- `0x18000a640`
- `0x18000a680`
- `0x18000a6c0`
- `0x18000a730`
- `0x18000a770`
- `0x18000a7e0`
- `0x18001234c`
- `0x180012810`
- `0x180012860`
- `0x1800128a0`
- `0x1800128f0`
- `0x180012930`
- `0x180012970`
- `0x1800129f0`
- `0x180012a30`
- `0x180012aa0`
- `0x180012ae0`
- `0x180012b20`
- `0x180012b70`
- `0x180012bb0`
- `0x180012bf0`
- `0x180012c40`

## callees

- `0x180003468`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002c74  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
