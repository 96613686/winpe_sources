# operator delete(void *,unsigned __int64)

- ea: `0x18000a0d0`
- end: `0x18000a0d5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `47`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180008fd4`
- `0x18000a12c`
- `0x18000a208`
- `0x18000a250`
- `0x18000a4e0`
- `0x18000b6a0`
- `0x18000bb80`
- `0x180013e30`
- `0x1800154a0`
- `0x180015610`
- `0x180015650`
- `0x180018130`
- `0x18001992c`
- `0x18001a420`
- `0x18001a4ac`
- `0x18001cfc0`
- `0x18001d050`
- `0x18001d190`
- `0x18001e170`
- `0x18001ea80`
- `0x18001eac0`
- `0x1800200b0`
- `0x180020270`
- `0x180023d10`
- `0x180025860`
- `0x180026650`
- `0x180027ed0`
- `0x180027f10`
- `0x1800285cc`
- `0x180028800`
- `0x180028840`
- `0x180029d70`
- `0x180029db0`
- `0x18002dd80`
- `0x18002df30`
- `0x180031084`
- `0x180033cec`
- `0x18003409c`
- `0x180034fc0`
- `0x180036698`
- `0x180036bc0`
- `0x180039544`
- `0x180039c8a`
- `0x180039cc2`
- `0x180039d75`
- `0x18003a799`
- `0x18003ab06`

## callees

- `0x18000a100`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x18000a0d0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
