# _CxxThrowException

- ea: `0x18000619a`
- end: `0x1800061a0`
- name: `_CxxThrowException`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180004ab4`
- `0x180006140`
- `0x180006168`
- `0x180008148`
- `0x1800082b0`
- `0x180008440`
- `0x180008b00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x18000619a`

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
0x18000619a  jmp     cs:__imp__CxxThrowException
```
