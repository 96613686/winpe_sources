# IsThreadAFiber_0

- ea: `0x180032a9d`
- end: `0x180032aa3`
- name: `IsThreadAFiber_0`
- size: `6`
- prototype: `BOOL __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!IsThreadAFiber` at `0x180032a9d`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall IsThreadAFiber_0()
{
  return IsThreadAFiber();
}

```

## disassembly

```asm
0x180032a9d  jmp     cs:__imp_IsThreadAFiber
```
