# _CxxThrowException_0

- ea: `0x18000229e`
- end: `0x1800022a4`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002244`
- `0x18000226c`
- `0x180007930`
- `0x180008890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x18000229e`

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
0x18000229e  jmp     cs:__imp__CxxThrowException
```
