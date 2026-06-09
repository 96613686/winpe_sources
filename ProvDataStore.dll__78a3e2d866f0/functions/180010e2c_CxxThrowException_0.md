# _CxxThrowException_0

- ea: `0x180010e2c`
- end: `0x180010e32`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x1800051a8`
- `0x1800054c0`
- `0x180005610`
- `0x180006060`
- `0x1800116bc`
- `0x18001178f`
- `0x180011993`
- `0x180011a18`
- `0x180011a3e`
- `0x180011b3d`
- `0x180011b63`
- `0x180011b89`
- `0x180011bb2`
- `0x180011c97`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180010e2c`

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
0x180010e2c  jmp     cs:__imp__CxxThrowException
```
