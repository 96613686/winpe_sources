# _CxxThrowException

- ea: `0x18002c810`
- end: `0x18002c816`
- name: `_CxxThrowException`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180011458`
- `0x180011478`
- `0x18001385c`
- `0x180013b0b`
- `0x180013d85`
- `0x180013dd2`
- `0x18002b83d`
- `0x18002b8d5`

## import_xrefs

- `VCRUNTIME140!_CxxThrowException` at `0x18002c810`

## pseudocode

```c
// attributes: thunk
void __stdcall __noreturn CxxThrowException(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _CxxThrowException(pExceptionObject, pThrowInfo);
}

```

## disassembly

```asm
0x18002c810  jmp     cs:__imp__CxxThrowException
```
