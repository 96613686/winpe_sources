# _CxxThrowException_0

- ea: `0x18000255c`
- end: `0x180002562`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e88`
- `0x180001ec8`
- `0x180001ef4`
- `0x18000740b`
- `0x180007531`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000255c`

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
0x18000255c  jmp     cs:__imp__CxxThrowException
```
