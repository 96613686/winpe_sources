# _CxxThrowException_0

- ea: `0x18000231a`
- end: `0x180002320`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800022e8`
- `0x1800084e0`
- `0x180008f10`
- `0x18000b408`
- `0x18000c01c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x18000231a`

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
0x18000231a  jmp     cs:__imp__CxxThrowException
```
