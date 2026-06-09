# operator delete(void *,unsigned __int64)

- ea: `0x180002e18`
- end: `0x180002e1d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `63`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800063b0`
- `0x180006b00`
- `0x1800101c0`
- `0x180010410`
- `0x180021dc0`
- `0x180022ba0`
- `0x1800276f0`
- `0x180029700`
- `0x1800298a0`
- `0x180029d00`
- `0x18002a4a0`
- `0x18002c4d0`
- `0x18002ced0`
- `0x18002cf40`
- `0x1800420e0`
- `0x180048320`
- `0x180049730`
- `0x18004ad50`
- `0x18004cc00`
- `0x18004d7c0`
- `0x18004eea0`
- `0x18004ffd0`
- `0x1800505d0`
- `0x180050ee0`
- `0x18005bcb0`
- `0x18005c430`
- `0x18005c6c0`
- `0x18005caa0`
- `0x18005e6e0`
- `0x18005e790`
- `0x18005ed30`
- `0x18005f230`
- `0x1800704d0`
- `0x180095b58`
- `0x180095c60`
- `0x180095c90`
- `0x180095cd0`
- `0x180095d00`
- `0x180095d40`
- `0x180095d80`
- `0x18009855c`
- `0x180098800`
- `0x180098840`
- `0x180098890`
- `0x1800988e0`
- `0x180098930`
- `0x180098980`
- `0x1800989c0`
- `0x1800994fc`
- `0x18009f060`

## callees

- `0x180003344`

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
0x180002e18  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
