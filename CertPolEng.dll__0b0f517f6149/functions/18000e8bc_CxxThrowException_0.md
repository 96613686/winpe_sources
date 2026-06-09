# _CxxThrowException_0

- ea: `0x18000e8bc`
- end: `0x18000e8c2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000df98`
- `0x18000dfc0`
- `0x18000dfec`
- `0x180011470`
- `0x180011c00`
- `0x18001a9b3`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000e8bc`

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
0x18000e8bc  jmp     cs:__imp__CxxThrowException
```
