# _CxxThrowException_0

- ea: `0x180004190`
- end: `0x180004196`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180004014`
- `0x18000403c`
- `0x180006908`
- `0x180006ac0`
- `0x180006c50`
- `0x1800072e0`
- `0x18000c110`
- `0x18000c3d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180004190`

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
0x180004190  jmp     cs:__imp__CxxThrowException
```
