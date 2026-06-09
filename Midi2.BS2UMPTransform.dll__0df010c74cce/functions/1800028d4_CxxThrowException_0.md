# _CxxThrowException_0

- ea: `0x1800028d4`
- end: `0x1800028da`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800024e0`
- `0x180004768`
- `0x180007680`
- `0x180008180`
- `0x18000acb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800028d4`

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
0x1800028d4  jmp     cs:__imp__CxxThrowException
```
