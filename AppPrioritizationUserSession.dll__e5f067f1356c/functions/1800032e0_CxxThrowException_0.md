# _CxxThrowException_0

- ea: `0x1800032e0`
- end: `0x1800032e6`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003148`
- `0x180005ce8`
- `0x180005f50`
- `0x1800061f0`
- `0x180006d90`
- `0x18000ae0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800032e0`

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
0x1800032e0  jmp     cs:__imp__CxxThrowException
```
