# _CxxThrowException_0

- ea: `0x180001ba8`
- end: `0x180001bae`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180001308`
- `0x180001330`
- `0x18000135c`
- `0x180005d5c`
- `0x18000c50c`
- `0x18000c532`
- `0x18000c864`
- `0x18000c8e1`
- `0x18000c96a`
- `0x18000c9bc`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001ba8`

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
0x180001ba8  jmp     cs:__imp__CxxThrowException
```
