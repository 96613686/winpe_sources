# operator delete(void *,unsigned __int64)

- ea: `0x1800036e4`
- end: `0x1800036e9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `121`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005f9c`
- `0x180006220`
- `0x180006280`
- `0x1800062b0`
- `0x1800062f0`
- `0x180006320`
- `0x180006370`
- `0x1800063b0`
- `0x1800063f0`
- `0x180006460`
- `0x180008100`
- `0x18000a730`
- `0x18000a750`
- `0x18000b5c0`
- `0x18000b7ac`
- `0x18000ba98`
- `0x18000babc`
- `0x18000bbac`
- `0x18000c840`
- `0x18000c8a0`
- `0x18000c8e0`
- `0x18000c920`
- `0x18000d0d0`
- `0x18000d0f0`
- `0x18000d988`
- `0x18000ed54`
- `0x18000f010`
- `0x18000f8f0`
- `0x18000f930`
- `0x18000f970`
- `0x18000f9e0`
- `0x18000fa40`
- `0x18000ff10`
- `0x180014f2c`
- `0x1800151a0`
- `0x1800153f8`
- `0x180015470`
- `0x180015578`
- `0x180015888`
- `0x180015dfc`
- `0x18001600c`
- `0x180016030`
- `0x1800160ac`
- `0x18001613c`
- `0x1800161b0`
- `0x1800162c8`
- `0x1800162f8`
- `0x1800163c8`
- `0x180016448`
- `0x1800164d0`

## callees

- `0x1800036d8`

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
0x1800036e4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
