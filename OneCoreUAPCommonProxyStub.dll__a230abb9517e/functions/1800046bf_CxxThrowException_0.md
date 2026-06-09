# _CxxThrowException_0

- ea: `0x1800046bf`
- end: `0x1800046c5`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004674`
- `0x180008b68`
- `0x180008ff0`
- `0x180009180`
- `0x180009840`
- `0x180009c28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800046bf`

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
0x1800046bf  jmp     cs:__imp__CxxThrowException
```
