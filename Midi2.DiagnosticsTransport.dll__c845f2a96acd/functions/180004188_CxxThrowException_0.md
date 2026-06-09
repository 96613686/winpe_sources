# _CxxThrowException_0

- ea: `0x180004188`
- end: `0x18000418e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003ff0`
- `0x180006018`
- `0x180008f30`
- `0x180009a30`
- `0x180010038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180004188`

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
0x180004188  jmp     cs:__imp__CxxThrowException
```
