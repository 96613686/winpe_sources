# _CxxThrowException_0

- ea: `0x180001cec`
- end: `0x180001cf2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015a8`
- `0x1800015d0`
- `0x1800015fc`
- `0x180006a30`
- `0x18000df50`
- `0x1800109e0`
- `0x18001472f`
- `0x1800147a7`
- `0x180014875`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001cec`

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
0x180001cec  jmp     cs:__imp__CxxThrowException
```
