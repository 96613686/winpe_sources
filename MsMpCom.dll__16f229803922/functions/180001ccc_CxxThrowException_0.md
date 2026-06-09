# _CxxThrowException_0

- ea: `0x180001ccc`
- end: `0x180001cd2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001418`
- `0x180001440`
- `0x18000146c`
- `0x180007c10`
- `0x180007cbc`
- `0x180009b09`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001ccc`

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
0x180001ccc  jmp     cs:__imp__CxxThrowException
```
