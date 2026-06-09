# _CxxThrowException_0

- ea: `0x18000290c`
- end: `0x180002912`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002784`
- `0x1800027ac`
- `0x180006210`
- `0x1800066c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x18000290c`

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
0x18000290c  jmp     cs:__imp__CxxThrowException
```
