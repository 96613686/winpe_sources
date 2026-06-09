# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001cc8`
- end: `0x180001ccd`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `26`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002de4`
- `0x180003200`
- `0x1800039c0`
- `0x18000533c`
- `0x18000796c`
- `0x180007ac0`
- `0x180007b00`
- `0x180007f4c`
- `0x180008bd4`
- `0x18000c980`
- `0x18000cfc4`
- `0x18000d590`
- `0x18000db20`
- `0x18000e034`
- `0x18000e40c`
- `0x18000e888`
- `0x18000ef24`
- `0x1800114a4`
- `0x180015e1c`
- `0x1800163f4`
- `0x180019620`
- `0x1800197c0`
- `0x18001a450`
- `0x18001b670`
- `0x18001b9b4`
- `0x18001c720`

## callees

- `0x180001d0c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001cc8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
