# std::vector<void *,std::allocator<void *>>::_Xlen(void)

- ea: `0x180010b18`
- end: `0x180010b29`
- name: `?_Xlen@?$vector@PEAXV?$allocator@PEAX@std@@@std@@IEBAXXZ_2`
- size: `17`
- prototype: `void __fastcall __noreturn(_QWORD)`
- caller_count: `26`
- callee_count: `1`
- tags: ``

## callers

- `0x180010b2c`
- `0x180011f70`
- `0x180013620`
- `0x180014260`
- `0x180018644`
- `0x1800190f0`
- `0x180019670`
- `0x18001b4bc`
- `0x18001b71c`
- `0x18001d690`
- `0x18001d730`
- `0x18001d7e0`
- `0x18001d9b0`
- `0x18001ed8c`
- `0x18001fb00`
- `0x180020558`
- `0x180022a00`
- `0x180022b90`
- `0x180022cb0`
- `0x180022e30`
- `0x180023720`
- `0x180024b2c`
- `0x180025b58`
- `0x18002ea2e`
- `0x18002faf7`
- `0x18002fe77`

## callees

- `0x180028e0c`

## pseudocode

```c
void __noreturn std::vector<void *>::_Xlen()
{
  sub_180028E0C("invalid string_view position");
}

```

## disassembly

```asm
0x180010b18  sub     rsp, 28h
0x180010b1c  lea     rcx, aInvalidStringV
0x180010b23  call    sub_180028E0C
```
