# _CxxThrowException_0

- ea: `0x1800024ec`
- end: `0x1800024f2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800014a8`
- `0x1800014e8`
- `0x180001514`
- `0x180004328`
- `0x18000ab27`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800024ec`

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
0x1800024ec  jmp     cs:__imp__CxxThrowException
```
