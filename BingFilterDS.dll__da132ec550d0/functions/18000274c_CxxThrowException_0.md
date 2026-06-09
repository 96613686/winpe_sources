# _CxxThrowException_0

- ea: `0x18000274c`
- end: `0x180002752`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001fa8`
- `0x180001fd0`
- `0x180001ff8`
- `0x180002024`
- `0x180005af8`
- `0x1800060e0`
- `0x180006230`
- `0x180006c00`
- `0x18000cc6c`
- `0x18000cce4`
- `0x18000cd0a`
- `0x18000cd33`
- `0x18000cfae`
- `0x18000cfd4`
- `0x18000d06a`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000274c`

## pseudocode

```c
// attributes: thunk
void __stdcall __noreturn CxxThrowException_0(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _CxxThrowException(pExceptionObject, pThrowInfo);
}

```

## disassembly

```asm
0x18000274c  jmp     cs:__imp__CxxThrowException
```
