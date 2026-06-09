# XspLogEvent_0

- ea: `0x140004f0c`
- end: `0x140004f12`
- name: `XspLogEvent_0`
- size: `6`
- prototype: `__int64(__int64, __int64, ...)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x14000210c`
- `0x1400021b8`
- `0x140002704`
- `0x140003f4c`
- `0x140003f98`

## import_xrefs

- `webengine4!XspLogEvent` at `0x140004f0c`

## pseudocode

```c
// attributes: thunk
__int64 XspLogEvent_0(__int64 a1, __int64 a2, ...)
{
  return XspLogEvent(a1, a2);
}

```

## disassembly

```asm
0x140004f0c  jmp     cs:__imp_XspLogEvent
```
