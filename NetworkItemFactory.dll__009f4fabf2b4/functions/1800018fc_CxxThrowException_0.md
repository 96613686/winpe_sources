# _CxxThrowException_0

- ea: `0x1800018fc`
- end: `0x180001902`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001218`
- `0x180001240`
- `0x18000126c`
- `0x18000ab56`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800018fc`

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
0x1800018fc  jmp     cs:__imp__CxxThrowException
```
