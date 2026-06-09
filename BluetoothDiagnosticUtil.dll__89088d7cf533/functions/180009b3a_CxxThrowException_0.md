# _CxxThrowException_0

- ea: `0x180009b3a`
- end: `0x180009b40`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180006c88`
- `0x180007090`
- `0x1800071e0`
- `0x180007b00`
- `0x18000a5d8`
- `0x18000a657`
- `0x18000a67d`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180009b3a`

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
0x180009b3a  jmp     cs:__imp__CxxThrowException
```
