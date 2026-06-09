# _CxxThrowException_0

- ea: `0x180009ddb`
- end: `0x180009de1`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180004a38`
- `0x180004c10`
- `0x180004db0`
- `0x1800054e0`
- `0x180007f90`
- `0x18000a602`
- `0x18000a681`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180009ddb`

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
0x180009ddb  jmp     cs:__imp__CxxThrowException
```
