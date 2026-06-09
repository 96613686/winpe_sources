# operator delete(void *,unsigned __int64)

- ea: `0x180001bc8`
- end: `0x180001bcd`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `131`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002aac`
- `0x180003090`
- `0x180003210`
- `0x180003250`
- `0x180004060`
- `0x1800040a0`
- `0x180006cd0`
- `0x180007420`
- `0x180008600`
- `0x1800090e0`
- `0x180009640`
- `0x18000a3e0`
- `0x18000a600`
- `0x18000a6e0`
- `0x18000bb7c`
- `0x18000bbd8`
- `0x18000bc80`
- `0x18000d290`
- `0x18000d920`
- `0x18000ed34`
- `0x18000fc4c`
- `0x18000fca8`
- `0x18000feb8`
- `0x18000fedc`
- `0x18000ff4c`
- `0x18000ffb8`
- `0x180010678`
- `0x180012140`
- `0x1800125f4`
- `0x1800136b8`
- `0x180013770`
- `0x18001505c`
- `0x1800151f0`
- `0x180015280`
- `0x1800152e0`
- `0x180015370`
- `0x180016680`
- `0x180018020`
- `0x18001c650`
- `0x18001ceb8`
- `0x18001d0dc`
- `0x18001d38c`
- `0x18001d3e8`
- `0x18001d484`
- `0x18001d4e0`
- `0x18001d5fc`
- `0x18001d774`
- `0x18001d878`
- `0x18001e388`
- `0x18001eb54`

## callees

- `0x1800021b0`

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
0x180001bc8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
