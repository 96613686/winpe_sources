# _CxxThrowException_0

- ea: `0x180002090`
- end: `0x180002096`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f0c`
- `0x180001f34`
- `0x18000499c`
- `0x180004b70`
- `0x180004cc0`
- `0x180005770`
- `0x180006700`
- `0x180006edc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002090`

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
0x180002090  jmp     cs:__imp__CxxThrowException
```
