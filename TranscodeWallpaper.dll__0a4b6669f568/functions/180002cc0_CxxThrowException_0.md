# _CxxThrowException_0

- ea: `0x180002cc0`
- end: `0x180002cc6`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b44`
- `0x180002b6c`
- `0x18000571c`
- `0x1800058e0`
- `0x180005a30`
- `0x180005aa0`
- `0x180006570`
- `0x180006cc4`
- `0x18000d4ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002cc0`

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
0x180002cc0  jmp     cs:__imp__CxxThrowException
```
