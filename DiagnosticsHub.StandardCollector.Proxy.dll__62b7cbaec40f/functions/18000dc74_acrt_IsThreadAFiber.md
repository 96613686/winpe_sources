# __acrt_IsThreadAFiber

- ea: `0x18000dc74`
- end: `0x18000dc7b`
- name: `__acrt_IsThreadAFiber`
- size: `7`
- prototype: `BOOL __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!IsThreadAFiber` at `0x18000dc74`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall _acrt_IsThreadAFiber()
{
  return IsThreadAFiber();
}

```

## disassembly

```asm
0x18000dc74  jmp     cs:__imp_IsThreadAFiber
```
