# _CxxThrowException_0

- ea: `0x180001f68`
- end: `0x180001f6e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001eb4`
- `0x180001edc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180001f68`

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
0x180001f68  jmp     cs:__imp__CxxThrowException
```
